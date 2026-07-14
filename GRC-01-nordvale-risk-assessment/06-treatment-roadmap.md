# 06 — Prioritised Treatment Roadmap

Sequenced by **risk reduction per unit of effort**, then dependency. The committee question this answers: *"What should be fixed in the next 30 days versus the next quarter?"*

## Next 30 days — quick wins & fires

| # | Action | Risks | Effort | Why now |
|---|---|---|---|---|
| 1 | Restrict the public channel, relocate government-related data, assess exposure window | R6 | Low | Critical risk, hours of effort — the exposure is live |
| 2 | Enable backup immutability / object lock + MFA-delete | R1 | Low–Med | Removes the catastrophic scenario (no recovery path) for configuration-level effort |
| 3 | Reset all credentials ever sent in plaintext by the MSP; notify MSP in writing | R8 | Low | Closes a live credential exposure immediately |
| 4 | Force security-agent updates estate-wide; enable auto-update | R2 | Med | 60% exposure on the endpoint front door |
| 5 | Enforce MFA on cloud services, vendor portals and email | R1 R3 R4 R5 | Med | One control, four risks — the highest-leverage identity fix |
| 6 | Set Secure/HttpOnly/SameSite cookie flags; enforce HTTPS | R5 | Low | Small dev change, closes session hijacking |

## Days 31–90 — programme actions

| # | Action | Risks | Effort |
|---|---|---|---|
| 7 | Individual named vendor-portal accounts + joiner-mover-leaver revocation process | R4 | Med |
| 8 | Sensitivity labelling + DLP policies (public locations, AI-tool uploads) | R6, R10 | Med–High |
| 9 | AI acceptable-use policy + approved enterprise AI tool with SSO/MFA | R10 | Med |
| 10 | Warehouse network discovery, asset inventory with owners, segmentation + NAC | R9 | High |
| 11 | Patch-compliance dashboard + conditional access blocking non-compliant devices | R2 | Med |
| 12 | Supplier remediation: due-diligence review, contractual security clauses, penetration test of subsidiary platform; cyber-insurance review | R7, R8 | Med |
| 13 | Backup restoration test + alerting on backup deletion/modification | R1 | Med |

## Ongoing / quarterly cadence

- Phishing simulations with per-market trend reporting; targeted refresher training (R3)
- Access reviews on privileged and vendor-portal accounts (R4)
- Vulnerability scanning of warehouse and corporate networks (R9)
- Automated scans for sensitive data in public channels (R6)
- Gateway/DLP report review for unapproved AI usage (R10)
- Re-assessment of this register: quarterly, or on trigger events (new supplier, new site, incident, major architecture change)

## The one-slide version for the committee

> **Two fires (backups, exposed government data) get put out this month for low effort. One identity fix — MFA plus named accounts — shrinks four risks at once. The quarter's real work is visibility and governance: find the warehouse networks, label the data, and give AI a sanctioned path instead of a blocked one.**
