---
name: signalwire-send-sms
description: Send an SMS or MMS through SignalWire and track its delivery, on either the SignalWire REST API or the Twilio-compatible Compatibility API. Use when an agent needs to text a person from a SignalWire number.
api: signalwire
operations:
  - create_message
  - list_messages
  - retrieve_message
  - update_message
  - list_message_logs
  - get_message_log
---

# Send an SMS with SignalWire

## Before you start

- You need the customer's **Space subdomain**. Every request goes to
  `https://{your_space}.signalwire.com` — there is no shared production host, and `servers[]` in both
  contracts is templated for exactly this reason. If you do not have the subdomain, stop and ask.
- Authenticate with **HTTP Basic**: Project ID as username, API Token as password
  (`Authorization: Basic base64(ProjectID:APIToken)`). Plain HTTP is refused.
- The sending number must already be provisioned on the project. See `signalwire-provision-number`.
- **There is no test mode.** SignalWire publishes no test-key prefix and no magic test number range.
  A message sent with a live token is a real, billed message to a real handset. Confirm the
  destination with the user before sending.

## Two surfaces, pick one

| Surface | Operation | Path |
| --- | --- | --- |
| SignalWire REST API | `create_message` | `POST /api/messaging/messages` |
| Compatibility API (Twilio-shaped) | `create_message` | `POST /Accounts/{AccountSid}/Messages` |

Use the Compatibility API only when porting an application that already speaks Twilio's request
shape. New work should use the SignalWire REST API.

## Steps

1. **Send** — call `create_message` with the destination in E.164 (`+15551234567`), the sending
   number, and the body. All phone numbers in and out of the API are E.164; if a number cannot be
   represented in E.164 the raw Caller ID string is used instead.
2. **Read back the state** — `retrieve_message` (Compatibility) or `get_message_log` (REST) returns
   delivery state. Do not assume a 2xx on send means delivered.
3. **Prefer the webhook over polling** — the REST contract declares `messageStatusCallback` and
   `inboundMessageWebhook` as first-class OpenAPI 3.1 webhooks. Register a callback URL rather than
   looping on `list_messages`.

## Rate limits you will hit

Messaging throughput is account-level and low by default. Over-rate traffic is **queued**, not
rejected, up to a 10,000-message backlog:

| Number type | Default |
| --- | --- |
| Toll-free | 3 MPS |
| US long code (10DLC) | 4 MPS |
| Canadian long code | 1 MPS |
| Short code | 10 MPS |

A long message is split into segments and **each segment counts against MPS**. On `429`, back off
and retry — see `rate-limits/signalwire-rate-limits.yml`.

## Retries are not safe

SignalWire declares **no `Idempotency-Key` header** on any of its 332 operations. Retrying
`create_message` after a timeout can send the message twice. Read back by SID before retrying.

## Undo

There is none. A delivered message cannot be recalled. `update_message` on the REST API is a
**redaction**, not an undo: it accepts only `body: ""`, works only on terminal-state messages
(`delivered`, `undelivered`, `failed` — not `queued` or `initiated`), and the original body "cannot
be recovered". `delete_message` on the Compatibility API is also terminal.

## Errors

Bodies are **not** RFC 9457. Expect `{"errors":[{"type","code","message","attribute","url"}]}` on
`/api/*`, possibly with several entries at once — iterate the array, never read only `errors[0]`.
Watch specifically for `associated_campaign_inactive` and `associated_campaign_suspended`: those are
carrier-returned A2P 10DLC states, not SignalWire faults, and the fix is in the Campaign Registry,
not in the request. Full reference: `errors/signalwire-problem-types.yml`.
