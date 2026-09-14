# Pre-authentication IDOR in registrodiclasse.it

## Summary

A **pre-authentication Insecure Direct Object Reference (IDOR)** vulnerability affected the hosted **registrodiclasse.it** platform.

The issue was responsibly reported to **Arvea** on **30 June 2026** and was confirmed as remediated on **5 September 2026**.

To comply with the coordinated disclosure agreement, this advisory intentionally excludes:

* Exploitation payloads
* Extracted information
* Extracted database metadata
* Details of additional test endpoints

## Affected Service

| Field                       | Details                                  |
| --------------------------- | ---------------------------------------- |
| **Supplier**                | Arvea                                    |
| **Service**                 | `registrodiclasse.it`                    |
| **Component**               | `/geopcfp2/modal/modal_alunno.asp`       |
| **Parameter**               | `idAlunno`                               |
| **Authentication Required** | No                                       |
| **Weakness**                | IDOR — CWE-639                           |
| **Affected Versions**       | Hosted service prior to 5 September 2026 |
| **Status**                  | Remediated                               |

## Impact

The vulnerable endpoint was accessible without authentication.

An unauthenticated remote attacker could manipulate the `idAlunno` identifier and access information associated with other records.

Arvea confirmed, through application log analysis, that testing performed before remediation enabled the extraction of limited database metadata.

No payloads, extracted data, or extracted metadata are included in this advisory.

## Remediation

Arvea reported implementing additional validation measures, including an additional parameter and a hashing mechanism, to prevent unauthorized manipulation of record identifiers.

Arvea completed verification of the remediation on **5 September 2026**.

According to Arvea, subsequent traffic-log analysis confirmed that the relevant attack patterns were successfully blocked.

## Timeline

* **30 June 2026** — Initial vulnerability report submitted to Arvea.
* **July–August 2026** — Analysis and iterative remediation.
* **5 September 2026** — Remediation verification completed and written confirmation issued.
* **9 September 2026** — Public advisory prepared.

## Credit

Discovered and responsibly reported by **"Houdini"**.

## Disclosure Authorization

Arvea authorized publication of its remediation confirmation and attribution of the IDOR discovery affecting **registrodiclasse.it**, provided that the publication remains limited to this platform and excludes:

* Operational payloads
* Additional test endpoints
* Extracted data
* Extracted metadata

This advisory has been prepared in accordance with those conditions.

## CVE

**CVE ID:** Requested — assignment pending.

---

### References

* **CWE-639:** Authorization Bypass Through User-Controlled Key
* **Vendor:** Arvea
* **Affected platform:** `registrodiclasse.it`
