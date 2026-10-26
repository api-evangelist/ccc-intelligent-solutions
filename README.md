# CCC Intelligent Solutions (ccc-intelligent-solutions)

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

CCC Intelligent Solutions (CCCIS, NASDAQ CCCS) is a Chicago-headquartered cloud software company that sits between US property and casualty insurance carriers and the auto claims economy. Its IX Cloud platform and CCC ONE estimating products run auto physical damage estimating, total-loss valuation, reinspection, subrogation, first- and third-party casualty medical bill review, parts procurement, and claim payments across tens of thousands of insurers, collision repair facilities, automakers, parts suppliers and lenders. CCC is a claims-technology intermediary rather than a risk carrier, and it is one of the software layers that accumulated value in a US market with no federal insurance regulator and no open-insurance mandate. Its API posture is honest to that seam and is entirely partner-gated — there is no public, self-serve developer portal, no downloadable OpenAPI, and no public API reference.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/ccc-intelligent-solutions/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/ccc-intelligent-solutions/refs/heads/main/apis.yml)

## Tags

- Insurance
- United States
- Property and Casualty
- Claims
- Auto Physical Damage
- Collision Repair
- Insurtech
- Claims Technology
- CIECA
- Partner Gated

## Timestamps

- **Created:** 2026-07-25
- **Modified:** 2026-07-25

## APIs

### CCC Secure Share API

CCC's only publicly named API product. Secure Share is described by CCC as "a network using cloud-based APIs to permit more than 22,000 collision repairers to connect to apps using the CIECA BMS data standard", replacing the legacy EMS local-file "data pump" model with a "RESTful cloud service API, JSON/XML". It moves collision assignment, estimate, final bill and part price change messages between CCC ONE Estimating licensees and registered third-party applications. No public API reference, no OpenAPI and no base URL are published — the app developer dashboard, "full API documentation including samples and technical documentation", is released only after registration, CCC review of the application, and active CIECA membership.

- **Human URL:** [https://www.cccsecureshare.com/Developers](https://www.cccsecureshare.com/Developers)

#### Tags

- Claims
- Collision Repair
- CIECA BMS
- Partner Gated

#### Properties

- [Documentation](https://www.cccsecureshare.com/Developers)
- [Documentation](https://www.cccsecureshare.com/Faq)
- [Sign Up](https://www.cccsecureshare.com/Register)
- [Login](https://www.cccsecureshare.com/Login)

## API Posture

CCC runs a substantial API estate and publishes none of it. Findings as of 2026-07-25:

- **No self-serve developer portal.** `developer.cccis.com` and `developers.cccis.com` do not resolve. `/developers`, `/api`, `/developer`, `/partners` and `/integrations` on `www.cccis.com` all return 404. The former CCC Developer Portal at `devportalcccis.com` is decommissioned — it now serves a Pantheon "404 - Unknown site".
- **`docs.cccis.com` is not a developer portal.** It returns 200, but it is a contractual/legal documentation hub for insurance carriers (Master Services Agreement, product terms, product documentation PDFs), served `noindex`.
- **A live, closed gateway.** `GET https://api.cccis.com/v1` returns HTTP 401 with an Apigee `oauth.v2.InvalidAccessToken` bearer challenge. Every discovery path on that host 404s.
- **Zero machine-readable API definitions.** No OpenAPI, Swagger, AsyncAPI, GraphQL SDL or protobuf document is published on any CCC-controlled host, so this repo has no `openapi/` directory.
- **Auth is OAuth 2.0 via Okta.** `auth.cccis.com` is an Okta custom domain serving OIDC discovery anonymously; `connect.cccis.com` redirects into an authorization-code + PKCE login with scope `connect:portal`.
- **Standards posture is CIECA, not ACORD.** CCC is a CIECA founding member, moved from EMS to CIECA BMS, and built Secure Share as the BMS-native replacement for EMS data pumps; CIECA named CCC its Electronic Commerce Company of the Year in January 2025. The only ACORD reference found on cccis.com is a citation of the ACORD Insurance Digital Maturity Study in a marketing post.
- **No quote / bind / issue.** CCC is claims technology; the claims workflow it does run is reachable only under contract with gated credentials.
- **No public webhooks, no public Postman workspace, and `github.com/cccis` has zero public repositories.**

See [review.yml](review.yml) for the full probe log, HTTP statuses and provenance.

## Links

- [Website](https://www.cccis.com/)
- [Documentation (contractual/product)](https://docs.cccis.com/)
- [News and Insights](https://www.cccis.com/news-and-insights)
- [Partners](https://www.cccis.com/about/partners)
- [Support](https://www.cccis.com/support)
- [Investor Relations](https://ir.cccis.com/)
- [GitHub](https://github.com/cccis)
- [LinkedIn](https://www.linkedin.com/company/ccc-intelligent-solutions)
