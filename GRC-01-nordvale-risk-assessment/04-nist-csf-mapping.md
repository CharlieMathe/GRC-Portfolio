# 04 — NIST CSF 2.0 Mapping

Recommended controls mapped to the six NIST CSF 2.0 functions — **Govern, Identify, Protect, Detect, Respond, Recover** — showing that the treatment plan is a balanced programme, not just a patch list.

## By function

### GOVERN (GV)
| Control | Risks | CSF category |
|---|---|---|
| AI acceptable-use policy (approved tools & use cases) | R10 | GV.PO — Policy |
| Technology sign-off policy for new network deployments | R9 | GV.PO — Policy |
| Contractual security clauses with vendors/MSPs (audit rights, breach notification, secure transmission) | R7, R8 | GV.SC — Cybersecurity Supply Chain Risk Management |
| Vendor security due-diligence process | R7 | GV.SC |
| Cyber insurance (risk transfer decision) | R7 | GV.RM — Risk Management Strategy |

### IDENTIFY (ID)
| Control | Risks | CSF category |
|---|---|---|
| Warehouse network asset discovery & inventory with owners | R9 | ID.AM — Asset Management |
| Exposure-window assessment (who accessed the public channel) | R6 | ID.RA — Risk Assessment |
| Patch-compliance visibility across the endpoint estate | R2 | ID.AM / ID.RA |

### PROTECT (PR)
| Control | Risks | CSF category |
|---|---|---|
| MFA (cloud, portals, email, backup deletion) | R1, R3, R4, R5 | PR.AA — Identity Management, Authentication & Access Control |
| Least-privilege / RBAC on backup infrastructure | R1 | PR.AA |
| Individual named accounts; joiner-mover-leaver revocation | R4 | PR.AA |
| Backup immutability, encryption, account separation | R1 | PR.DS — Data Security |
| Sensitivity labelling + DLP (public channels, AI uploads) | R6, R10 | PR.DS |
| Secure cookie flags, HTTPS enforcement, session expiry | R5 | PR.DS / PR.PS — Platform Security |
| Automatic security-agent updates; conditional access for non-compliant devices | R2 | PR.PS |
| Network segmentation + NAC for warehouse sites | R9 | PR.IR — Technology Infrastructure Resilience |
| Security awareness training (phishing, data handling, AI use) | R3, R6, R10 | PR.AT — Awareness & Training |
| SPF / DKIM / DMARC enforcement | R3 | PR.PS |

### DETECT (DE)
| Control | Risks | CSF category |
|---|---|---|
| Alerts on backup deletion/modification | R1 | DE.CM — Continuous Monitoring |
| Access logging & monitoring on sensitive data locations | R6 | DE.CM |
| Vendor-portal access reviews and audit | R4 | DE.CM |
| Scheduled vulnerability scanning of warehouse networks | R9 | DE.CM |
| Gateway/DLP report review for AI-tool trends | R10 | DE.CM |
| Recurring scans for sensitive data in public channels | R6 | DE.CM |

### RESPOND (RS)
| Control | Risks | CSF category |
|---|---|---|
| Credential resets after plaintext exposure | R8 | RS.MI — Incident Mitigation |
| Immediate restriction & relocation of exposed data | R6 | RS.MI |
| Conditional-access response to risky sign-ins | R3 | RS.MI |

### RECOVER (RC)
| Control | Risks | CSF category |
|---|---|---|
| Periodic backup restoration testing | R1 | RC.RP — Incident Recovery Plan Execution |

## Observation

The register clusters heavily in **PR.AA (identity)** and **DE.CM (monitoring)** — consistent with the most common real-world weakness: identity and visibility. Govern appears in five controls, reflecting CSF 2.0's core message: without policy and supply-chain governance, technical fixes regrow the same risks.
