# 05 — ISO/IEC 27001:2022 Annex A Gap Analysis

Each risk mapped to the Annex A controls it implicates, with a gap status based on the register evidence. Annex A (2022) organises 93 controls into four themes: **Organisational (5.x), People (6.x), Physical (7.x), Technological (8.x).**

| Risk | Primary Annex A controls | Gap status | Gap summary |
|---|---|---|---|
| R1 Backups | **8.13** Information backup · 8.5 Secure authentication · 5.15 Access control | **Major gap** | Backups exist but are not protected against tampering/deletion — 8.13 requires backups to be protected and tested |
| R2 Endpoint agent | **8.8** Management of technical vulnerabilities · 8.19 Installation of software on operational systems | **Major gap** | 60% of estate outdated = failing vulnerability management on endpoints |
| R3 Phishing | **6.3** Awareness, education & training · 8.5 Secure authentication · 8.23 Web filtering | **Partial gap** | Training/simulations exist (evidence: the simulation itself) but effectiveness is insufficient; MFA coverage unconfirmed |
| R4 Shared accounts | **5.16** Identity management · 5.15 Access control · 5.18 Access rights · 8.15 Logging | **Major gap** | Shared identities break the one-person-one-identity principle and destroy log attribution |
| R5 Cookies | **8.26** Application security requirements · 8.24 Use of cryptography | **Major gap** | Session management fails baseline secure-development requirements |
| R6 Public data exposure | **5.12** Classification of information · 5.13 Labelling · 5.15 Access control · 8.12 Data leakage prevention · 8.16 Monitoring activities | **Critical gap** | No effective classification/DLP regime — sensitive data reached a public location undetected |
| R7 Third-party hosting | **5.19** Information security in supplier relationships · 5.20 Addressing security in supplier agreements · 5.22 Monitoring of supplier services | **Major gap** | Supplier onboarded without meeting security standards; agreement lacks enforceable clauses |
| R8 MSP plaintext credentials | **5.14** Information transfer · 5.20 Supplier agreements · 5.17 Authentication information | **Major gap** | Authentication information transferred insecurely; no contractual control over supplier practice |
| R9 Warehouse networks | **8.20** Networks security · 8.21 Security of network services · 5.9 Inventory of information & assets · 8.22 Segregation of networks | **Major gap** | Unknown assets and unmanaged networks — inventory (5.9) is the prerequisite control that failed |
| R10 AI tools | **5.10** Acceptable use of information & assets · 8.12 DLP · 6.3 Awareness | **Partial gap** | Usage visible (monitoring works) but no acceptable-use policy or DLP guardrails yet |

## Themes across the gaps

1. **Identity & access (5.15/5.16/8.5)** appears in four risks — the single most repeated control family. Fix identity once (MFA, named accounts, JML process) and four risks shrink together.
2. **Supplier management (5.19–5.22)** appears in three risks — supplier controls are contractual as much as technical.
3. **Classification & DLP (5.12/5.13/8.12)** is the root-cause gap behind both the public-channel exposure and the AI-tool risk — the same fix serves both.
4. **Asset inventory (5.9)** failing at the warehouses proves the oldest rule in the framework: every other control assumes you know what you have.

## Honest scope note

This is a **risk-driven gap analysis** — it assesses Annex A controls implicated by these ten risks. It is not a full Statement of Applicability review across all 93 controls, which would be the next step in an ISO 27001 programme.
