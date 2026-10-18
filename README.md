# OWASP Juice Shop Security Guide

A structured learning resource for assessing web application security in the intentionally vulnerable [OWASP Juice Shop](https://owasp.org/www-project-juice-shop/). It organizes a security assessment into an isolated lab guide, twelve findings, remediation priorities, and references.

> **Lab only:** Juice Shop is deliberately insecure. Run it on loopback for training, and test only systems for which you have explicit written authorization. Never expose this container to a public or shared network.

## Start here

- [Assessment overview](report/00-overview.md) ? attack paths and severity caveats.
- [Build an isolated lab](report/01-lab-setup.md) ? run Juice Shop locally and inspect your own traffic.
- [Scope and method](report/02-scope-and-method.md) ? safe evidence handling and a repeatable workflow.
- [Findings index](report/INDEX.md) ? twelve findings with impact and remediation.
- [Figure index](report/figures/README.md) ? all 48 figures, with sensitive details redacted.
- [OWASP mapping and learner checklist](report/18-owasp-mapping-and-checklist.md)
- [Severity and assessment limitations](report/19-severity-and-assessment-notes.md) ? [OWASP Top 10 context](report/20-owasp-top-ten-context.md)
- [Contributing](CONTRIBUTING.md)
- [Remediation priorities](report/15-remediation.md) ? [References](report/16-references.md) ? [Glossary](report/17-glossary.md)

## What the assessment found

The report describes weaknesses across injection, authentication, authorization, cross-site scripting, and security configuration. High-leverage fixes include parameterized database queries, server-side authorization, safe browser rendering, and robust session validation. Public identifiers and exposed files can make technical flaws easier to exploit, so consider them together.

The individual entries contain **12 findings**, while the source report's executive summary gives conflicting totals. Severity labels are preserved as reported, not independently rescored; see [assessment caveats](report/00-overview.md#severity-and-reporting-caveats).

## Suggested learning path

1. Deploy Juice Shop locally and verify the service is bound to `127.0.0.1`.
2. Browse without an account and map public pages, routes, and API traffic.
3. Reproduce each issue only in the local lab; record minimum evidence.
4. Explain the root cause, apply the remediation concepts, then retest.

The source PDF is not included. All 48 report figures are represented in a [figure index](report/figures/README.md) and embedded in their related sections. Sensitive screenshot details (account data, tokens, hashes, credentials, and phishing destinations) are redacted; Figure 11 is an explicitly labeled illustration because the PDF captioned it without embedding its image.

## Contents

```text
README.md
report/
  INDEX.md
  00-overview.md
  01-lab-setup.md
  02-scope-and-method.md
  03-public-information-disclosure.md ... 14-jwt-validation.md
  figures/ ? numbered, sanitized report figures
  15-remediation.md
  16-references.md
  17-glossary.md
```

This guide does not grant a license to third-party names, products, or source material. No blanket reuse license is asserted.
