# OWASP mapping and learner checklist

## How the findings map to the OWASP Top 10

The original assessment referenced the OWASP Top 10:2021. Category mappings are useful labels, not a substitute for analyzing the root cause, affected version, and impact. This assessment covers only a subset of the categories.

| OWASP Top 10:2021 category | Related findings | Learning point |
|---|---|---|
| [A01 Broken Access Control](https://owasp.org/Top10/A01_2021-Broken_Access_Control/) | 4, 7, 12 | Enforce resource- and action-level checks on the server. |
| [A02 Cryptographic Failures](https://owasp.org/Top10/A02_2021-Cryptographic_Failures/) | 11 | Select password-hashing algorithms designed for password storage. |
| [A03 Injection](https://owasp.org/Top10/A03_2021-Injection/) | 3, 5, 7, 8, 9, 10 | Keep untrusted input from becoming SQL, HTML, or script syntax. |
| [A05 Security Misconfiguration](https://owasp.org/Top10/A05_2021-Security_Misconfiguration/) | 1, 5, 6 | Expose only intended data and files; make secure settings the default. |
| [A07 Identification and Authentication Failures](https://owasp.org/Top10/A07_2021-Identification_and_Authentication_Failures/) | 3, 7, 12 | Protect credentials, sessions, and identity assertions. |

Some issues span multiple categories. For example, a public identifier can make an authentication flaw easier to exploit, while a token-validation bug can become an authorization failure. The mappings are guideposts, not exclusive classifications.

## Practice checklist

Before an exercise, confirm that the target is your loopback-only Juice Shop instance and that no real data or accounts are involved. During the exercise, capture the minimum evidence, note what must be true for the issue to work, and distinguish client-side behavior from server-side enforcement. Afterward, describe the root cause, recommend a control that addresses it, and retest with a harmless input after applying the fix.

A clear finding should let another learner understand the affected component, preconditions, observed result, impact, confidence, and remediation without exposing passwords, hashes, session tokens, or unrelated user records.

## Further learning

- Work through the relevant Juice Shop challenge using its current [official documentation](https://github.com/juice-shop/juice-shop).
- Use the [OWASP Web Security Testing Guide](https://owasp.org/www-project-web-security-testing-guide/) to structure authorized testing.
- Read the relevant OWASP prevention cheat sheet listed in [references](16-references.md), then verify that the fix addresses the root cause rather than hiding evidence in the UI.
