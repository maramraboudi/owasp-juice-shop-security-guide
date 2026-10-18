# Finding 8: DOM-based cross-site scripting

**Reported severity:** Critical
**Themes:** OWASP A03:2021 Injection; CWE-79

## Observation

The assessment reported that a URL-controlled search value reached a browser DOM sink without safe handling. In the local lab, the behavior allowed script execution in the application's origin. The source report displayed session data during testing; this guide omits the token and any extraction steps.

## Safe validation in the lab

Use the local Juice Shop DOM XSS challenge and a harmless visible marker to determine whether input is interpreted as markup or script. Do not read, copy, or transmit cookies or tokens. Record the input context and whether the marker ran.

## Impact

Script execution in a trusted origin can act with the victim browser's privileges. HttpOnly cookies reduce direct JavaScript access to cookies but do not remove other XSS impact.

## Remediation

- Prefer safe DOM APIs such as `textContent` when rendering text.
- Avoid `innerHTML` for untrusted input; if rich HTML is required, use a maintained sanitizer with a strict allowlist.
- Apply context-aware output encoding and framework-safe templating.
- Deploy a restrictive Content Security Policy as defense in depth, not as a substitute for safe rendering.
- Set session cookies with appropriate `HttpOnly`, `Secure`, and `SameSite` attributes.

**References:** [OWASP XSS Prevention Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Cross_Site_Scripting_Prevention_Cheat_Sheet.html) ? [DOM-based XSS Prevention Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/DOM_based_XSS_Prevention_Cheat_Sheet.html)
