# CCC Intelligent Solutions (ccc-intelligent-solutions)

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
