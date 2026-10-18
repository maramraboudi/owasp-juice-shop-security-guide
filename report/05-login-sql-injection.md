# Finding 3: SQL injection in login

**Reported severity:** Critical
**Themes:** OWASP A03:2021 Injection; CWE-89

## Observation

The report describes unsafe construction of the login database query from user-controlled input. A crafted login identifier altered the query logic and bypassed password verification, yielding an authenticated session in the training application.

## Safe validation in the lab

Use the local Juice Shop challenge and a dedicated synthetic account. Compare server behavior for ordinary invalid input and the challenge's harmless local test. Do not run payload lists against external hosts or copy the returned session token. Challenge feedback is sufficient evidence in this deliberately vulnerable environment.

## Impact

An authentication query modified by user input may permit authentication bypass or database access, depending on the query and database permissions. This flaw also underpins the [account-takeover chain](09-account-takeover-chain.md).

## Remediation

- Replace string concatenation with parameterized queries or prepared statements throughout the application.
- Keep query structure separate from untrusted values; validation is useful but not a substitute for parameterization.
- Give the database identity only required permissions.
- Use generic login errors, rate limits, and anomaly monitoring as defense in depth.
- Add regression tests proving malformed input remains data, not query syntax.

**References:** [OWASP SQL Injection Prevention Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/SQL_Injection_Prevention_Cheat_Sheet.html) ? [CWE-89](https://cwe.mitre.org/data/definitions/89.html)

## Report figures

![Figure 18: Captured login request; account and request values redacted.](figures/figure-18.jpg)

*Figure 18. Captured login request; account and request values redacted.*

![Figure 19: Proxy Intruder configuration; payload details redacted.](figures/figure-19.jpg)

*Figure 19. Proxy Intruder configuration; payload details redacted.*

![Figure 20: Local login test results; response data redacted.](figures/figure-20.jpg)

*Figure 20. Local login test results; response data redacted.*

![Figure 21: Login form during local SQL-injection challenge; input redacted.](figures/figure-21.jpg)

*Figure 21. Login form during local SQL-injection challenge; input redacted.*

![Figure 22: Local challenge completion notification.](figures/figure-22.jpg)

*Figure 22. Local challenge completion notification.*
