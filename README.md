# SignalWire

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

SignalWire is a Programmable Unified Communications (PUC) platform for voice, messaging, video, fax, SIP and AI voice agents, built by the team behind FreeSWITCH. It publishes two first-party OpenAPI 3.1 contracts from its public documentation repository — a 253-operation SignalWire REST API covering calling, messaging, video rooms, phone number management, Campaign Registry/10DLC, WhatsApp, Datasphere, SIP resources, subscribers, AI agents and logs, and a 79-operation Twilio-compatible Compatibility (LaML) API at /api/laml/2010-04-01 — plus an OpenRPC 1.3.2 JSON-RPC contract for live call control, a JSON Schema for SWML (SignalWire Markup Language), and 19 OpenAPI 3.1 webhook definitions covering AI/SWAIG, calling and messaging callbacks. Every request is served from a per-customer Space subdomain, {space_name}.signalwire.com, over HTTPS only.

**Areas:** Company · Communications · CPaaS · Voice · Messaging · SMS · Video · WebRTC · SIP · Telephony · Fax · AI Agents

## SignalWire on APIs.io

Everything profiled for SignalWire is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/signalwire/](https://apis.io/providers/signalwire/)** — or go straight to one of the APIs or properties below.

### APIs (80)

- [SignalWire Calling API (JSON-RPC)](https://apis.io/apis/signalwire/signalwire-calling-rpc/) — An OpenRPC 1.3.2 contract for real-time control of live calls over RELAY — 8 methods (calling.dial, calling.update, calling.end, calling.ai_hold,…
- [SignalWire Accounts API](https://apis.io/apis/signalwire/signalwire-accounts-api/) — Manage SignalWire projects and subprojects.
- [SignalWire Addresses API](https://apis.io/apis/signalwire/signalwire-addresses-api/) — Client-side endpoints for listing and retrieving resource addresses using [subscriber](/docs/platform/subscribers) access tokens (SAT). Intended for use…
- [SignalWire AI Agents: Custom API](https://apis.io/apis/signalwire/signalwire-ai-agents-custom-api/) — Endpoints related to creating & managing SignalWire AI Agents
- [SignalWire AI Agents: Dialogflow API](https://apis.io/apis/signalwire/signalwire-ai-agents-dialogflow-api/) — Endpoints related to creating & managing Dialogflow Agents
- [SignalWire AI Chat API](https://apis.io/apis/signalwire/signalwire-ai-chat-api/) — Endpoints related to holding a text conversation with an AI agent
- [SignalWire AI Webhooks API](https://apis.io/apis/signalwire/signalwire-ai-webhooks-api/) — Callbacks an AI agent sends to your server. The same payloads apply to every surface an agent runs on — voice calls, Amazon Bedrock agents, sidecar agents,…
- [SignalWire Applications API](https://apis.io/apis/signalwire/signalwire-applications-api/) — Manage cXML applications for handling voice and messaging.
- [SignalWire Available Phone Numbers API](https://apis.io/apis/signalwire/signalwire-available-phone-numbers-api/) — Search for available phone numbers to purchase.
- [SignalWire Call Flows API](https://apis.io/apis/signalwire/signalwire-call-flows-api/) — Endpoints related to creating & managing Call Flows
- [SignalWire Calling Webhooks API](https://apis.io/apis/signalwire/signalwire-calling-webhooks-api/) — Callbacks about a call: the SWML document request sent when a call arrives, and the progress of work you started on it such as a transcription or a…
- [SignalWire Calls API](https://apis.io/apis/signalwire/signalwire-calls-api/) — Manage voice calls and call recordings.
- [SignalWire Campaign Registry: Brands API](https://apis.io/apis/signalwire/signalwire-campaign-registry-brands-api/) — Register and manage brands for 10DLC campaign registration.
- [SignalWire Campaign Registry: Campaigns API](https://apis.io/apis/signalwire/signalwire-campaign-registry-campaigns-api/) — Create and manage 10DLC campaigns for A2P messaging compliance.
- [SignalWire Campaign Registry: Phone Number Assignments API](https://apis.io/apis/signalwire/signalwire-campaign-registry-phone-number-assignments-api/) — Assign and manage phone numbers within 10DLC campaigns.
- [SignalWire Chat Tokens API](https://apis.io/apis/signalwire/signalwire-chat-tokens-api/) — Manage Chat tokens.
- [SignalWire Chunks API](https://apis.io/apis/signalwire/signalwire-chunks-api/) — Manage chunks within Datasphere documents.
- [SignalWire Conference Logs API](https://apis.io/apis/signalwire/signalwire-conference-logs-api/) — Manage and query conference log data.
- [SignalWire Conference Participants API](https://apis.io/apis/signalwire/signalwire-conference-participants-api/) — Manage participants in conference calls.
- [SignalWire Conference Recordings API](https://apis.io/apis/signalwire/signalwire-conference-recordings-api/) — Manage recordings for conference calls.
- [SignalWire Conference Rooms API](https://apis.io/apis/signalwire/signalwire-conference-rooms-api/) — Endpoints related to creating & managing Conference Rooms
- [SignalWire Conference Streams API](https://apis.io/apis/signalwire/signalwire-conference-streams-api/) — Manage media streams for conferences.
- [SignalWire Conference Tokens API](https://apis.io/apis/signalwire/signalwire-conference-tokens-api/) — Manage conference tokens
- [SignalWire Conferences API](https://apis.io/apis/signalwire/signalwire-conferences-api/) — Manage conference calls.
- [SignalWire cXML Applications API](https://apis.io/apis/signalwire/signalwire-cxml-applications-api/) — Endpoints related to creating & managing cXML Applications
- [SignalWire CXML Scripts API](https://apis.io/apis/signalwire/signalwire-cxml-scripts-api/) — Manage cXML scripts for storing XML instructions.
- [SignalWire cXML Webhook API](https://apis.io/apis/signalwire/signalwire-cxml-webhook-api/) — Endpoints related to creating & managing cXML Webhooks
- [SignalWire Documents API](https://apis.io/apis/signalwire/signalwire-documents-api/) — Manage Datasphere documents.
- [SignalWire Domain Applications API](https://apis.io/apis/signalwire/signalwire-domain-applications-api/) — Endpoints related to managing Domain Applications
- [SignalWire E911 Addresses API](https://apis.io/apis/signalwire/signalwire-e911-addresses-api/) — Manage E911 addresses for regulatory compliance and phone number provisioning.
- [SignalWire Fax Logs API](https://apis.io/apis/signalwire/signalwire-fax-logs-api/) — Endpoints related to accessing fax logs
- [SignalWire Fax Media API](https://apis.io/apis/signalwire/signalwire-fax-media-api/) — Manage fax media files.
- [SignalWire Faxes API](https://apis.io/apis/signalwire/signalwire-faxes-api/) — Send and manage faxes.
- [SignalWire FreeSWITCH Connector API](https://apis.io/apis/signalwire/signalwire-freeswitch-connector-api/) — Endpoints related to creating & managing FreeSWITCH Connectors
- [SignalWire Imported Phone Numbers API](https://apis.io/apis/signalwire/signalwire-imported-phone-numbers-api/) — Import phone numbers hosted elsewhere into your SignalWire Space.
- [SignalWire Incoming Phone Numbers API](https://apis.io/apis/signalwire/signalwire-incoming-phone-numbers-api/) — Manage phone numbers in your project.
- [SignalWire Message Logs API](https://apis.io/apis/signalwire/signalwire-message-logs-api/) — Endpoints related to accessing message logs
- [SignalWire Message Media API](https://apis.io/apis/signalwire/signalwire-message-media-api/) — Manage media files attached to messages.
- [SignalWire Messages API](https://apis.io/apis/signalwire/signalwire-messages-api/) — Send and manage SMS/MMS messages.
- [SignalWire Messaging Webhooks API](https://apis.io/apis/signalwire/signalwire-messaging-webhooks-api/) — Callbacks about a message: the SWML document request sent when a message arrives, delivery state for messages you send, and 10DLC registration state.
- [SignalWire Multi-Factor Authentication API](https://apis.io/apis/signalwire/signalwire-multi-factor-authentication-api/) — Multi-factor authentication adds security to your application by requesting a user to be verified via voice or via text message. It can also be used for One…
- [SignalWire Number Group Membership API](https://apis.io/apis/signalwire/signalwire-number-group-membership-api/) — Manage phone number memberships within number groups.
- [SignalWire Number Groups API](https://apis.io/apis/signalwire/signalwire-number-groups-api/) — Manage number groups for organizing phone numbers.
- [SignalWire Phone Number Lookup API](https://apis.io/apis/signalwire/signalwire-phone-number-lookup-api/) — Look up information about phone numbers.
- [SignalWire Phone Numbers API](https://apis.io/apis/signalwire/signalwire-phone-numbers-api/) — Manage phone numbers for your SignalWire project.
- [SignalWire Phone Routes API](https://apis.io/apis/signalwire/signalwire-phone-routes-api/) — Endpoints related to managing Phone Routes
- [SignalWire Project Tokens API](https://apis.io/apis/signalwire/signalwire-project-tokens-api/) — Manage API tokens for authentication.
- [SignalWire Projects API](https://apis.io/apis/signalwire/signalwire-projects-api/) — Manage projects and subprojects under the authenticated root project.
- [SignalWire PubSub Tokens API](https://apis.io/apis/signalwire/signalwire-pubsub-tokens-api/) — Endpoints related to creating & managing PubSub Tokens
- [SignalWire Queue Members API](https://apis.io/apis/signalwire/signalwire-queue-members-api/) — Manage members in call queues.
- [SignalWire Queues API](https://apis.io/apis/signalwire/signalwire-queues-api/) — Manage call queues.
- [SignalWire Recording Transcriptions API](https://apis.io/apis/signalwire/signalwire-recording-transcriptions-api/) — Manage transcriptions of recordings.
- [SignalWire Recordings API](https://apis.io/apis/signalwire/signalwire-recordings-api/) — Manage call recordings.
- [SignalWire Relay Application API](https://apis.io/apis/signalwire/signalwire-relay-application-api/) — Endpoints related to creating & managing Relay Applications
- [SignalWire Resources API](https://apis.io/apis/signalwire/signalwire-resources-api/) — Endpoints related to creating & managing Resources
- [SignalWire Room Recordings API](https://apis.io/apis/signalwire/signalwire-room-recordings-api/) — Manage room recordings
- [SignalWire Room Sessions API](https://apis.io/apis/signalwire/signalwire-room-sessions-api/) — Manage room sessions
- [SignalWire Room Tokens API](https://apis.io/apis/signalwire/signalwire-room-tokens-api/) — Manage room tokens
- [SignalWire Rooms API](https://apis.io/apis/signalwire/signalwire-rooms-api/) — Manage video rooms
- [SignalWire Short Codes API](https://apis.io/apis/signalwire/signalwire-short-codes-api/) — Manage short codes for SMS and MMS messaging.
- [SignalWire SIP Addresses API](https://apis.io/apis/signalwire/signalwire-sip-addresses-api/) — Endpoints related to creating & managing SIP Addresses — the SIP configuration (username, Domain, codecs, ciphers, encryption, IP authentication,…
- [SignalWire SIP Credentials API](https://apis.io/apis/signalwire/signalwire-sip-credentials-api/) — Manage SIP credentials for authenticating SIP endpoints.
- [SignalWire SIP Endpoints (Legacy) API](https://apis.io/apis/signalwire/signalwire-sip-endpoints-legacy-api/) — Manage SIP endpoints for voice communication. Use SIP Credentials for new integrations.
- [SignalWire SIP Gateway API](https://apis.io/apis/signalwire/signalwire-sip-gateway-api/) — Endpoints related to creating & managing SIP Gateways
- [SignalWire SIP Profile API](https://apis.io/apis/signalwire/signalwire-sip-profile-api/) — Manage SIP profile settings.
- [SignalWire Space Domain Applications API](https://apis.io/apis/signalwire/signalwire-space-domain-applications-api/) — Manage domain applications for call handling configuration.
- [SignalWire Streams API](https://apis.io/apis/signalwire/signalwire-streams-api/) — Manage media streams for calls.
- [SignalWire Subscriber SIP Credentials API](https://apis.io/apis/signalwire/signalwire-subscriber-sip-credentials-api/) — Endpoints related to creating & managing [Subscriber](/docs/platform/subscribers) SIP Endpoints.
- [SignalWire Subscriber Tokens API](https://apis.io/apis/signalwire/signalwire-subscriber-tokens-api/) — Endpoints related to creating & managing [Subscriber](/docs/platform/subscribers) tokens.
- [SignalWire Subscribers API](https://apis.io/apis/signalwire/signalwire-subscribers-api/) — Endpoints related to creating & managing [Subscribers](/docs/platform/subscribers).
- [SignalWire SWML Scripts API](https://apis.io/apis/signalwire/signalwire-swml-scripts-api/) — Endpoints related to creating & managing SWML Scripts
- [SignalWire SWML Webhook API](https://apis.io/apis/signalwire/signalwire-swml-webhook-api/) — Endpoints related to creating & managing SWML Webhooks
- [SignalWire Tokens API](https://apis.io/apis/signalwire/signalwire-tokens-api/) — Manage API tokens for authentication.
- [SignalWire Verified Caller ID API](https://apis.io/apis/signalwire/signalwire-verified-caller-id-api/) — Manage verified caller IDs for phone numbers not purchased through SignalWire.
- [SignalWire Video Conferences API](https://apis.io/apis/signalwire/signalwire-video-conferences-api/) — Manage video conferences
- [SignalWire Video Logs API](https://apis.io/apis/signalwire/signalwire-video-logs-api/) — View video logs
- [SignalWire Voice Logs API](https://apis.io/apis/signalwire/signalwire-voice-logs-api/) — Endpoints related to accessing voice logs
- [SignalWire WhatsApp Businesses API](https://apis.io/apis/signalwire/signalwire-whatsapp-businesses-api/) — List the WhatsApp Business Accounts connected to your Space.
- [SignalWire WhatsApp Numbers API](https://apis.io/apis/signalwire/signalwire-whatsapp-numbers-api/) — List and retrieve the WhatsApp numbers connected to your Space.
- [SignalWire WhatsApp Templates API](https://apis.io/apis/signalwire/signalwire-whatsapp-templates-api/) — Create and manage the Meta-approved templates required to start WhatsApp conversations.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Signalwire Webhooks](https://apis.io/asyncapis/signalwire/signalwire-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [SignalWire Documentation MCP Server](https://apis.io/servers/signalwire/signalwire-documentation-mcp-server/)

#### JSON Schema (1)

The data models the API reads and writes.

- [SWML Object](https://apis.io/schemas/signalwire/signalwire-swml/)

#### Overlays (2)

OpenAPI overlays, including conversational phrasing for each operation.

- [Signalwire Compatibility Overlay](https://apis.io/overlays/signalwire/signalwire-compatibility-overlay/)
- [Signalwire Rest Overlay](https://apis.io/overlays/signalwire/signalwire-rest-overlay/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Signalwire Authentication](https://apis.io/security/signalwire/signalwire-authentication/)
- [Signalwire Domain Security](https://apis.io/security/signalwire/signalwire-domain-security/)
- [Signalwire Trust Center](https://apis.io/security/signalwire/signalwire-trust-center/)
- [Signalwire Vulnerability Disclosure](https://apis.io/security/signalwire/signalwire-vulnerability-disclosure/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Signalwire Plans Pricing](https://apis.io/plans/signalwire/signalwire-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Signalwire Rate Limits](https://apis.io/rate-limits/signalwire/signalwire-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://signalwire.com)
- [Documentation](https://signalwire.com/docs)
- [Getting started](https://signalwire.com/docs/platform/getting-started)
- [API reference](https://signalwire.com/docs/apis)
- [Pricing](https://signalwire.com/pricing)
- [Sign up](https://signalwire.com/signup)
- [Support](https://support.signalwire.com/portal/en/home)
- [Blog](https://signalwire.com/blog)
- [Trust centre](https://compliance.signalwire.com)
- [Terms of service](https://signalwire.com/legal)
- [Privacy policy](https://signalwire.com/legal)
- [GitHub](https://github.com/signalwire)
- [Status](https://status.signalwire.com)

## API Evangelist rating

**Kin Score 66.9** — exemplar · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 75.0 |
| Contract quality | 62.9 |
| Contract governance | 18.2 |
| Operational transparency | 76.3 |
| Developer ergonomics | 90.5 |
| Access clarity | 60.5 |

**Agent readiness 40.0** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | documented (partial credit) |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | partial |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | yes |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | paginated |
| Operation Distinctiveness | mostly (partial credit) |

**Regulatory alignment 34.2** — Telecommunications

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/signalwire/](https://apis.io/providers/signalwire/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for SignalWire: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/signalwire/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
