# Report contents

This guide reorganizes the supplied assessment into a learning-oriented sequence. It describes a March 2026 snapshot, not the current behavior of every Juice Shop release.

## Orientation

- [Assessment overview](00-overview.md)
- [Isolated lab setup](01-lab-setup.md)
- [Scope, method, and evidence handling](02-scope-and-method.md)

## Findings

| # | Finding | Reported severity |
|---|---|---|
| 1 | [Public information disclosure](03-public-information-disclosure.md) | Critical* |
| 2 | [Client-side route discovery](04-client-route-discovery.md) | High* |
| 3 | [SQL injection in login](05-login-sql-injection.md) | Critical |
| 4 | [Administration access control](06-administration-access-control.md) | High |
| 5 | [Unauthenticated configuration API](07-configuration-api.md) | High |
| 6 | [Public file exposure](08-public-file-exposure.md) | High |
| 7 | [Account-takeover chain](09-account-takeover-chain.md) | Critical* |
| 8 | [DOM-based XSS](10-dom-xss.md) | Critical |
| 9 | [Reflected HTML injection](11-reflected-html-injection.md) | High |
| 10 | [SQL injection in product search](12-product-search-sql-injection.md) | Critical |
| 11 | [Weak password storage](13-password-storage.md) | Critical |
| 12 | [JWT validation and data exposure](14-jwt-validation.md) | High |

\* Context-dependent labels from the source assessment; the report's severity roll-up conflicts with its twelve individual findings. See [caveats](00-overview.md#severity-and-reporting-caveats).

## Close out

- [Remediation priorities](15-remediation.md)
- [References](16-references.md)
- [Glossary](17-glossary.md)
- [OWASP mapping and learner checklist](18-owasp-mapping-and-checklist.md)

The source PDF and screenshots are not redistributed. Images contained session data and account/credential material; the guide retains the lessons while omitting those artifacts.
