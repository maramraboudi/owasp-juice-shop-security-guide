# Severity and assessment notes

## Rating scale used in the assessment

The report says its ratings are based on CVSS v3 and potential impact, and gives these bands:

| Label | Reported score range | General meaning in the report |
|---|---:|---|
| Critical | 9.0?10.0 | Straightforward exploitation with severe compromise or authentication bypass. |
| High | 7.0?8.9 | Significant privilege or data exposure risk. |
| Moderate | 4.0?6.9 | Exploitation requires additional conditions. |
| Low | 0.1?3.9 | Lower direct impact or limited exploitability. |
| Informational | N/A | An observation without a direct vulnerability score. |

No full CVSS vectors are given for each issue, and the overall counts do not match the twelve individual entries. These labels are therefore presented as the report's own estimates, not as independently reproducible CVSS calculations. A real assessment should document a score vector, affected version, preconditions, and environmental factors for each finding.

Some labels need context. Public disclosure of an account identifier may assist targeting but does not, by itself, amount to administrator compromise. Finding 7 describes the combined effect of findings 1 and 3 rather than an independent root cause. Likewise, discovering a client-side route is not proof that server authorization is broken.

## Limitations

The assessment reflects one application version and a limited testing window. It does not establish that all Juice Shop versions behave the same way, nor does it test production deployments. The guide summarizes the reported behavior and adds defensive learning context; it does not provide fresh test evidence or claim that the findings remain present upstream.
