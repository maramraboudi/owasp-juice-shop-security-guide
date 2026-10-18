# Finding 9: Reflected HTML injection in search heading

**Reported severity:** High
**Themes:** OWASP A03:2021 Injection; CWE-79

## Observation

The report describes a search term reflected into a results heading as HTML rather than rendered as plain text. This allowed attacker-controlled link markup to appear within the trusted page. No external link or phishing payload is reproduced here.

## Safe validation in the lab

Enter a harmless text marker in the local search field and inspect whether it renders as text or markup. Keep tests within the local lab and do not direct users to a third-party destination.

## Impact

Attacker-controlled markup can mislead users or alter page content; it becomes script execution if the browser context permits. HTML injection and XSS are related but not identical, so assess what the browser actually does.

## Remediation

- Render user-controlled values as text using safe framework interpolation.
- Avoid binding untrusted values to HTML-rendering properties.
- Apply context-aware output encoding; validate allowed URL schemes when links are required.
- Use a restrictive Content Security Policy as defense in depth.
- Test that special characters remain text in the search heading.

**Reference:** [OWASP XSS Prevention Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html)
