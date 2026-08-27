---
name: signalwire-place-call
description: Place, steer and cancel an outbound phone call on SignalWire, including the exact windows inside which a call can still be cancelled or hung up. Use when an agent needs to dial a person or hand a live call to an AI agent.
api: signalwire
operations:
  - create_a_call
  - retrieve_a_call
  - update_a_call
  - list_all_calls
  - call-commands
  - list_call_recordings
  - get_call_recording
---

# Place a call with SignalWire

## Before you start

- You need the **Space subdomain** (`https://{your_space}.signalwire.com`) and Basic credentials
  (Project ID + API Token). HTTPS only.
- **This places a real call and bills real money.** SignalWire publishes no test credentials and no
  magic test number range. Confirm the destination with the user first.

## Place the call

`create_a_call` — `POST /Accounts/{AccountSid}/Calls` on the Compatibility API. The call's behaviour
comes from the SWML (or cXML) document your webhook returns; see the `signalwire-swml` skill for the
document shape.

Live, in-progress control is a separate surface: the OpenRPC contract
(`openapi/signalwire-calling-openrpc.yml`) exposes `calling.dial`, `calling.update`, `calling.end`,
`calling.ai_hold`, `calling.ai_unhold`, `calling.ai_message`, `calling.live_transcribe` and
`calling.live_translate`, addressed by call UUID.

## Cancelling — read this before you dial

`update_a_call` takes `Status`, and the accepted value depends on **where the call already is**:

| Call state | Accepted `Status` | Effect |
| --- | --- | --- |
| Not yet connected | `canceled` | The call never happens |
| In progress | `completed` | Hang up |
| Completed | — | Rejected |

Attempting `canceled` on an in-progress call, or any update on a completed call, returns error
`10000`. So the reversal window for "do not make this call" closes the moment it connects; after
that the only reversal is hanging up, and the minutes already spent are billed.

## Throughput

Outbound calling defaults to **1 call per second** account-wide, with a 10,000-call backlog. Calls
above the rate are queued in order received, not rejected. Fax shares this limit because faxes are
sent over calls. Increases go through the Space Increase Request Form.

## Retries are not safe

No `Idempotency-Key` is declared anywhere in the contract. A retried `create_a_call` after a timeout
can dial the person twice. Look the call up by SID before retrying.

## Recordings are one-way doors

`delete_call_recording` / `delete_recording` have no restore path and no published retention window.
Fetch and store anything you need before deleting.

## Errors

`{"errors":[...]}`, not RFC 9457. `401` means bad credentials; `403` means the token is missing the
scope (scopes are set in the Dashboard, not requested over OAuth); `429` means back off. See
`errors/signalwire-problem-types.yml`.
