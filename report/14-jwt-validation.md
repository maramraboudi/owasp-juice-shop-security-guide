# Finding 12: JWT data exposure and validation

**Reported severity:** High
**Themes:** OWASP A07:2021 Identification and Authentication Failures; CWE-347

## Observation

The report describes readable identity/role claims in the JWT payload and acceptance of an invalid or unsigned algorithm configuration. JWT payloads are usually encoded, not encrypted, so claims should not be treated as confidential. No token values, claim data, or token-tampering recipe are reproduced here.

## Safe validation in the lab

Inspect only a synthetic token issued by the local Juice Shop and confirm it contains no secrets. Within the local challenge, verify that invalidly signed or unsupported-algorithm tokens are rejected. Never publish a token or send a modified token to any non-lab service.

## Impact

If a server trusts a client-controlled algorithm or fails to verify signatures, an attacker may forge identity claims. Even with correct signing, sensitive values in a readable token can be exposed to anyone who obtains it.

## Remediation

- Configure an explicit algorithm allowlist; reject missing, unsigned, or unexpected algorithms.
- Verify signature, issuer, audience, expiry, and required claims on the server.
- Protect and rotate signing keys under a defined process.
- Put only necessary, non-sensitive claims in the token; do not trust client-supplied roles.
- Use short lifetimes and a refresh/revocation strategy suitable for the application.

**References:** [OWASP REST Security Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/REST_Security_Cheat_Sheet.html) ? [RFC 8725: JWT Best Current Practices](https://www.rfc-editor.org/rfc/rfc8725)
