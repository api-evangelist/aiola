# aiOla

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

aiOla is a deep-tech voice, speech and conversational AI lab that sells enterprise Speech AI
as an API. Its Jargonic family of multilingual automatic speech recognition models
(Jargonic-v2, Jargonic-v2-Flash and the earlier Jargonic-v1) is built around zero-shot
jargon and keyword spotting, so a caller can supply a dictionary of domain terms — drug
names, case-law phrases, part numbers — and have them transcribed accurately without
retraining. Alongside it aiOla ships a low-latency text-to-speech model that can be
conditioned on a recording of how a word should be pronounced, and a speech-understanding
layer covering summarization, sentiment, entity and topic detection, key phrases, auto
chapters, content moderation and PII redaction. The same technology is packaged
commercially as field voice agents that capture data into Salesforce.

## What this profile found

- **No published machine-readable contract.** There is no OpenAPI, Swagger, GraphQL or
  AsyncAPI document. `/openapi.json`, `/openapi.yaml`, `/swagger.json`, `/api-docs` and
  `/api-reference` were probed on both web hosts, and the documentation sitemap lists
  nineteen pages with no API reference section among them.
- **The operation surface is real and readable anyway** — it is published as source, in
  aiOla's own MIT-licensed SDKs: `POST /api/speech-to-text/file`, `POST /api/tts/synthesize`,
  `POST /api/tts/stream`, a Socket.IO stream at `/api/voice-streaming/socket.io`, and a
  three-call auth exchange on a separate host. Every artifact here that describes an
  operation cites the SDK file it was read from; none is a generated spec.
- **A live, unauthenticated MCP server** at `https://docs.aiola.ai/_mcp/server`, advertised
  on every docs page. It answers `tools/list` with one tool — documentation search. It is
  not a product API server.
- **SOC 2 Type II and ISO 27001:2022**, both recorded as fully implemented in aiOla's own
  Scytale Trust Center; GDPR and CCPA are recorded there as in progress, though the
  marketing footer shows badges for all four.
- **Four of aiOla's own advertised hosts did not answer** an anonymous public client on
  2026-09-14. `platform.aiola.ai` — the console the quickstart tells developers to visit
  for an API key — is a dangling CNAME to a CloudFront distribution with no A record.

## Artifacts

| Path | What it holds |
|---|---|
| `authentication/` | The API-key-to-JWT exchange, session lifecycle, and the docs/SDK disagreement over the default host |
| `conformance/` | Eighteen standards assertions, each with the evidence that establishes it |
| `conventions/` | Transport, streaming events, payload limits, idempotency (none) and reversibility (n/a) |
| `errors/` | The error-code catalog assembled from the auth guide and the SDK error taxonomy |
| `lifecycle/` | Status page components, model generations, and the host-liveness findings |
| `llms/` | aiOla's own `llms.txt`, saved verbatim |
| `mcp/` | The probed MCP server manifest and its verbatim `tools/list` response |
| `packages/` | Six first-party SDKs with registry versions and publish dates |
| `plans/`, `rate-limits/` | Honest zeros — aiOla publishes neither pricing nor limits |
| `security/` | Domain security probe, Trust Center certifications, and the absent disclosure program |
| `well-known/` | The `/.well-known/` probe across all six hosts |
