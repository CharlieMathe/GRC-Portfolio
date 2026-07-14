# Qualitative Information Security Risk Assessment — Nordvale Components Ltd (fictional)

A hands-on GRC portfolio project: a qualitative risk assessment of a fictional mid-size industrial and electronics distributor, taken from a raw risk-register extract through scoring, evaluation, framework mapping and a prioritised treatment roadmap.

**Report site:** [charliemathe.github.io/GRC-Portfolio](https://charliemathe.github.io/GRC-Portfolio/) · Companion to the [Threat Hunting portfolio](https://charliemathe.github.io/Threat-Hunting/)

> **Scenario.** Nordvale Components Ltd is a fictional UK-headquartered distributor of industrial and electronic components, trading across Europe with warehouse operations, a subsidiary e-commerce platform, cloud (AWS/M365) infrastructure and several managed service providers. I play the role of a Risk Analyst asked to review ten entries from the corporate risk register and present findings to a Risk Management Committee that includes non-technical stakeholders. All organisations, figures and findings are fictional or fully sanitised.

## What this project demonstrates

- **Qualitative risk assessment** using a 5×5 impact × likelihood matrix with defined rating thresholds
- **Business-impact articulation** — every risk is expressed in terms of what it costs the business, not just the technology
- **Risk treatment decisions** — mitigate / transfer / avoid / accept, with target residual ratings
- **Framework mapping** — controls mapped to **NIST CSF 2.0** functions and **ISO/IEC 27001:2022 Annex A** controls, with a gap analysis
- **Prioritised roadmap** — 30-day quick wins vs 90-day programme actions, sequenced by risk reduction per unit of effort
- **Coachability** — the first draft went through peer review; [07-lessons-learned.md](07-lessons-learned.md) documents what the feedback changed and why

## Repository map

| File | Contents |
|---|---|
| [index.html](index.html) | GRC portfolio hub (GitHub Pages) |
| [risk-assessment.html](risk-assessment.html) | Full styled engagement report |
| [01-methodology.md](01-methodology.md) | Scoring scales, matrix thresholds, and how the approach aligns to ISO/IEC 27005 and NIST SP 800-30 |
| [02-risk-register.md](02-risk-register.md) | The ten risks: description, business impact, scores, rating, treatment decision, refined controls, residual target |
| [03-risk-matrix.md](03-risk-matrix.md) | 5×5 heatmap — current position and post-treatment target position |
| [04-nist-csf-mapping.md](04-nist-csf-mapping.md) | Recommended controls mapped to NIST CSF 2.0 functions and categories |
| [05-iso27001-annex-a-gap-analysis.md](05-iso27001-annex-a-gap-analysis.md) | Risks mapped to Annex A (2022) controls with gap status |
| [06-treatment-roadmap.md](06-treatment-roadmap.md) | 30-day / 90-day prioritised remediation roadmap |
| [07-lessons-learned.md](07-lessons-learned.md) | What peer review changed: rescoring, scope corrections, governance-over-blocking |

## Method in one paragraph

Each risk is scored for **impact** (1–5) and **likelihood** (1–5); the product places it in a rating band (Insignificant 1–5, Minor 6–10, Significant 11–15, Severe 16–19, Critical 20–25). Risks are evaluated against the organisation's context — a distributor's revenue lives in order flow, customer trust and contract compliance — then assigned a treatment decision and a control set chosen for **proportionality**: the cheapest controls that bring the risk inside appetite, sequenced so the highest risk-reduction-per-effort items land first. The flow follows ISO/IEC 27005 (context → identification → analysis → evaluation → treatment) with NIST SP 800-30 as the assessment method.

## Author

Károly (Charlie) Mathe — CompTIA A+ / Network+ / Security+ / CySA+ · Cyber Security Technician
