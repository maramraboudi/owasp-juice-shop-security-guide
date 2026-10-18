# Finding 7: Account-takeover chain

**Reported severity:** Critical (chain, not a separate root-cause flaw)
**Themes:** OWASP A03 Injection; CWE-89 and CWE-200

## Observation

The report connected two weaknesses: a user identifier was visible in public content, and the login query accepted input that bypassed password verification. The same authentication flaw could therefore apply to any account whose identifier was known. This overlaps with [public information disclosure](03-public-information-disclosure.md) and [login SQL injection](05-login-sql-injection.md).

## Safe validation in the lab

Use only a local Juice Shop challenge with synthetic accounts. Document the dependency between the public identifier and the separate login flaw; do not test real accounts or retain session tokens.

## Impact

A chain can have greater impact than either weakness alone. Account access may expose personal or order data and can provide a path to privilege escalation if authorization is also weak.

## Remediation

Fix the root causes rather than treating the chain as a separate issue: parameterize the login query, avoid publishing internal identifiers, enforce role checks server-side, and invalidate sessions issued before remediation. Retest each link independently.
