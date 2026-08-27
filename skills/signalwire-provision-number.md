---
name: signalwire-provision-number
description: Search, buy, configure and release a SignalWire phone number, and register it for A2P 10DLC so messages actually deliver. Use when an agent needs to stand up a new number or attach one to a call flow.
api: signalwire
operations:
  - search_available_phone_numbers
  - purchase_phone_number
  - list_phone_numbers
  - retrieve_phone_number
  - update_phone_number
  - release_phone_number
  - lookup_phone_number
  - create_imported_phone_number
---

# Provision a phone number on SignalWire

## Before you start

Space subdomain + Basic auth (Project ID / API Token), HTTPS only. **Buying a number is a billed,
recurring charge.** Confirm with the user before purchasing.

## Steps

1. **Search** — `search_available_phone_numbers`
   (`GET /api/relay/rest/phone_numbers/search`). Filter to the area code, region or capability set
   you need.
2. **Buy** — `purchase_phone_number` (`POST /api/relay/rest/phone_numbers`). This is the billed step.
3. **Point it at something** — `update_phone_number` attaches the number to a Resource. Resources
   are the routing layer: a SWML Script, a cXML Application, a Relay Application, an AI Agent, or a
   Call Flow. A number with no Resource does nothing useful on an inbound call.
4. **Verify** — `retrieve_phone_number` to confirm capabilities and routing.

`lookup_phone_number` (`GET /api/relay/rest/lookup/phone_number/{e164_number}`) inspects a number
without buying it. `create_imported_phone_number` brings a number hosted elsewhere into the Space.

## Do the 10DLC work or messages will fail

A US long-code number that is not registered will have messages rejected by carriers, and the error
arrives as `associated_campaign_inactive` or `associated_campaign_suspended` on the *message*, not
on the number. Register first, using the Campaign Registry surface:

- `Campaign Registry: Brands` — 3 operations
- `Campaign Registry: Campaigns` — 4 operations
- `Campaign Registry: Phone Number Assignments` — 5 operations

For outbound calling with a known Caller ID, `create_verified_caller_id` plus
`redial_verification_call` completes the verification loop. Emergency service needs an E911 address
(5 operations under `E911 Addresses`).

## Limits

1,000 phone numbers per Project by default. Going above that requires additional verification, a
documented use case, and auto top-up configured to the numbers' total monthly cost **before** the
limit is raised — otherwise service is suspended on insufficient balance.

## Releasing is permanent

`release_phone_number` (`DELETE /api/relay/rest/phone_numbers/{id}`) returns the number to the pool.
There is no restore, no grace period and no retention window published. You will very likely not get
that number back. Treat it as irreversible and confirm explicitly with the user.
