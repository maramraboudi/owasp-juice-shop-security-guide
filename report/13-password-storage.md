# Finding 11: Weak password storage

**Reported severity:** Critical
**Themes:** OWASP A02:2021 Cryptographic Failures; CWE-328

## Observation

Following the database exposure described in Finding 10, the report identified MD5 password hashes in training-application records. MD5 is fast and unsuitable for password storage. Raw hashes and recovered test credentials are deliberately omitted.

## Safe validation in the lab

Review documented local challenge behavior or inspect only synthetic lab data. Do not submit hashes to online cracking services, publish them, or test recovered passwords against any other service.

## Impact

Fast general-purpose hashes are inexpensive to guess offline. Password reuse can turn one application's database exposure into compromise elsewhere; never include raw hashes or cracked passwords in evidence.

## Remediation

- Use a dedicated adaptive password-hashing function such as Argon2id, scrypt, or bcrypt, following current library guidance and cost parameters.
- Use unique per-password salts provided by the password-hashing library.
- Migrate legacy hashes on successful login where feasible; force resets when exposure risk warrants it.
- Invalidate sessions and notify users if credential data may have been exposed.
- Encourage unique passwords and phishing-resistant MFA where appropriate.

**References:** [OWASP Password Storage Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet.html) ? [CWE-328](https://cwe.mitre.org/data/definitions/328.html)
