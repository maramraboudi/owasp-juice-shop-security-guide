# Scope, method, and evidence handling

## Scope

This guide concerns a local OWASP Juice Shop instance, a purpose-built training target. Testing other systems requires explicit written authorization and a defined scope. Public reachability or a discoverable challenge does not imply permission to test.

The assessment is a point-in-time snapshot. It does not establish security of other versions, deployments, integrations, or production environments. Retest the exact version under review.

## Learning workflow

1. **Prepare:** record the local target, version, time window, and permitted test accounts.
2. **Map:** browse anonymously and inventory visible pages, routes, API calls, and trust boundaries.
3. **Test:** change one input or access condition at a time in the local lab; prefer a harmless proof over data extraction.
4. **Record:** note the component, prerequisites, behavior, impact, version, and minimal evidence. Redact tokens and personal data.
5. **Remediate:** address the root cause in code or configuration, not only through a client-side workaround.
6. **Retest:** repeat the minimal safe test and confirm server-side enforcement.

## Evidence handling

Evidence should demonstrate a finding with the minimum necessary data. Do not capture or publish raw cookies, JWTs, passwords, password hashes, full user lists, private documents, or live credentials. Some source report screenshots contained this type of material. The figures are included with sensitive areas redacted; Figure 11 is an illustrative replacement for a caption whose image was missing from the PDF.

Behavior and impact statements reflect the supplied assessment, not independent verification of the current application. Severity labels are discussed in the [overview](00-overview.md#severity-and-reporting-caveats).
