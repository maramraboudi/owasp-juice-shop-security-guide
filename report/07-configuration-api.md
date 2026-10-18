# Finding 5: Unauthenticated application configuration API

**Reported severity:** High
**Themes:** OWASP A05:2021 Security Misconfiguration; CWE-200

## Observation

An application configuration endpoint reportedly returned a broad JSON response without authentication. Some service and integration details were not needed by public clients.

## Safe validation in the lab

Request the endpoint on the local training instance without a session. Record categories of exposed data, not full values or personal information. Determine which fields genuinely need to be public.

## Impact

Configuration details may aid reconnaissance or disclose internal endpoints, feature flags, and operational assumptions. The report describes configuration leakage, not proof that every field was a credential.

## Remediation

- Require server-side authorization for administrative configuration APIs.
- Separate public client configuration from server-only settings.
- Return an explicit allowlist of fields required by the frontend.
- Store secrets outside API responses, using a secrets manager or protected environment.
- Add tests for unauthenticated access to administrative routes.

**References:** [OWASP API Security Project](https://owasp.org/www-project-api-security/) ? [CWE-200](https://cwe.mitre.org/data/definitions/200.html)
