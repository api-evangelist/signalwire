---
name: signalwire-video-room
description: Create a SignalWire video room, mint a join token for a participant, stream or record the session, and read back what happened. Use when an agent needs to set up a browser-based video meeting.
api: signalwire
operations:
  - create_room
  - list_rooms
  - get_room
  - get_room_by_name
  - update_room
  - delete_room
  - create_room_token
  - create_room_stream
  - list_room_streams
  - list_room_sessions
  - get_room_session
  - list_room_session_members
  - list_room_session_recordings
  - list_room_recordings
  - get_room_recording
  - delete_room_recording
---

# Run a video room on SignalWire

## Model

Three things, and they are not the same:

- **Room** — the durable configuration (`create_room`, `get_room_by_name`).
- **Room Session** — one actual occupancy of that room (`list_room_sessions`,
  `list_room_session_members`). Sessions are read-only history.
- **Room Token** — a short-lived credential a single participant uses to join (`create_room_token`).

## Steps

1. `create_room` — `POST /api/video/rooms`. Give it a stable name; `get_room_by_name` lets you look
   it up later without storing the id.
2. `create_room_token` — `POST /api/video/room_tokens`, one per participant. Mint these
   **server-side**. The published guidance is explicit: keep API credentials server-side and hand
   clients a short-lived Bearer token instead.
3. Hand the token to the browser client (`@signalwire/js`, or the `sw-click-to-call` /
   `sw-call-status` web components — see `components/signalwire-components.yml`).
4. Optionally `create_room_stream` to push the room to an RTMP destination.
5. Afterwards, `list_room_sessions` → `list_room_session_recordings` → `get_room_recording`.

## Tokens expire; credentials do not

A Bearer token that has expired returns `401`. Refresh before expiry rather than catching the 401 —
`refresh_subscriber_token` exists for the subscriber case. API tokens themselves never expire, which
is exactly why they must not reach a browser.

## Deletion is terminal

`delete_room`, `delete_room_recording` and `delete_stream` have no restore path and no published
retention window. Download a recording before deleting it.

## Errors and limits

Standard `{"errors":[...]}` envelope, not RFC 9457. Writes (`POST`/`PUT`/`PATCH`) share the platform
limit of 13,800 requests per 10 seconds; reads are effectively unlimited. There is no
`Idempotency-Key`, so a retried `create_room` can leave you with two rooms — look up by name first.
