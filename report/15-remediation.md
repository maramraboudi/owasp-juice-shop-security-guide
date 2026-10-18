# Remediation priorities

Prioritize root causes that break multiple attack paths. Follow every patch with regression testing and review of neighboring endpoints.

## 1. Remove injection primitives

- Parameterize all database operations, including login and product search.
- Audit neighboring endpoints for the same query-construction pattern.
- Use least-privilege database permissions and generic client-facing errors.
- Add tests proving malformed values cannot change query structure.

This addresses both SQL injection findings and interrupts the account-takeover path that depends on the login flaw.

## 2. Enforce identity and authorization server-side

- Require authentication and role checks for every administrative API and protected resource.
- Deny by default; test direct API requests as anonymous, ordinary, and privileged users.
- Validate JWT signatures and claims against an explicit algorithm allowlist.
- Rotate keys and invalidate sessions if tokens or credentials may have been exposed.

## 3. Render untrusted input safely

- Render search terms as text, not HTML.
- Avoid unsafe DOM sinks; sanitize only when rich HTML is necessary.
- Apply context-sensitive output encoding and a restrictive CSP as defense in depth.
- Configure session cookies with appropriate security attributes.

## 4. Reduce unnecessary exposure

- Use display aliases in public content.
- Remove sensitive fields from unauthenticated configuration responses.
- Move backup files and credential stores outside the web root; disable directory listing.
- Review static files, source maps, API responses, and errors for unintended disclosures.

## 5. Modernize credential storage and operations

- Migrate from MD5 to an adaptive password-hashing algorithm.
- Reset passwords and revoke sessions when exposure warrants it.
- Monitor authentication anomalies, privileged actions, and sensitive file access.
- Retest every finding and document residual risk, affected versions, and evidence provenance.

Minification, a WAF, input filtering, or hidden frontend routes are not substitutes for fixing server-side vulnerabilities.
