# Finding 1: Public account information disclosure

**Reported severity:** Critical (context-dependent)
**Themes:** OWASP A05:2021 Security Misconfiguration; CWE-200

## Observation

The assessment reported that an anonymous visitor could see an administrator account identifier in a public product review. Another user identifier was similarly exposed. Public identifiers can make phishing and account targeting easier, but are not passwords or session tokens.

## Safe validation in the lab

Browse product reviews in the local Juice Shop while logged out. Record whether account identifiers are displayed. Do not use the identifier to attempt access to any real account, and do not publish account lists.

## Impact

A public identifier can supply a login name or help tailor social engineering. Risk rises when combined with a separate authentication weakness, poor password controls, or credential reuse.

## Remediation

- Use display aliases in public content instead of internal login identifiers.
- Review comments, product reviews, support pages, and errors for unintended personal data.
- Make identity fields private by default and document what is intentionally public.
- Do not treat email obfuscation as a substitute for strong authentication.

**Related:** [Login SQL injection](05-login-sql-injection.md) ? [Account-takeover chain](09-account-takeover-chain.md)
