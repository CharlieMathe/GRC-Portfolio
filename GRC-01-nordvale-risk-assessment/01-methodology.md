# 01 — Methodology

## Approach and standards alignment

This assessment follows the **ISO/IEC 27005** information security risk management flow, using **NIST SP 800-30 Rev. 1** as the assessment method:

1. **Establish context** — understand the business (distribution: order flow, warehouse operations, e-commerce, regulated customer data, government-related contracts) and its risk appetite.
2. **Risk identification** — the ten register entries (provided as the scenario input).
3. **Risk analysis** — score impact and likelihood on defined 1–5 scales.
4. **Risk evaluation** — rate against thresholds and rank; identify which risks exceed appetite.
5. **Risk treatment** — select mitigate / transfer / avoid / accept; define controls and target residual ratings.
6. **Communication & reporting** — business-language findings for a mixed technical/non-technical committee.
7. **Monitoring & review** — roadmap checkpoints and re-assessment triggers.

## Scoring scales

**Impact (1–5)**
| Score | Level | Meaning for Nordvale |
|---|---|---|
| 1 | Negligible | No material effect on operations, data or reputation |
| 2 | Low | Minor inconvenience; contained within one team |
| 3 | Moderate | Disruption to a business unit, limited data exposure, or minor compliance breach |
| 4 | Major | Significant operational disruption, regulated data exposure, or contract impact |
| 5 | Severe | Loss of critical capability (e.g. restoration), major regulatory/contractual breach, or sustained reputational damage |

**Likelihood (1–5)**
| Score | Level | Indicative frequency |
|---|---|---|
| 1 | Rare | Not expected within 3 years |
| 2 | Unlikely | Possible within 3 years |
| 3 | Possible | Could occur within 12 months |
| 4 | Likely | Expected within 12 months; enabling conditions already observed |
| 5 | Almost certain | Occurring now or imminent |

## Rating thresholds (Impact × Likelihood)

| Band | Score range |
|---|---|
| Insignificant | 1–5 |
| Minor | 6–10 |
| Significant | 11–15 |
| Severe | 16–19 |
| Critical | 20–25 |

## Principles applied

- **A risk only exists relative to a business objective.** Every register entry carries a business-impact statement, not just a technical description.
- **Score the credible consequence, not the average one.** Where a plausible escalation path exists (e.g. a compromised credential belonging to a privileged user), the impact score reflects it.
- **Proportionality.** Controls are chosen for risk reduction per unit of cost/effort, and gold-plating is treated as a cost, not a virtue.
- **Residual risk is owned.** Anything not fully mitigated is explicitly accepted by a named owner — never silently ignored.
