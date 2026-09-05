# RACI Matrix — Vulnerability Management Program

Roles match those already established across the policy, CAB minutes, and
remediation email — no new roles introduced here, just their authority made
explicit across the full lifecycle.

**R** = Responsible (does the work) · **A** = Accountable (owns the outcome,
signs off) · **C** = Consulted (input sought before) · **I** = Informed
(told after)

| Activity | CISO | CIO | Security Analyst | Server Team Manager | Lead Systems Engineer | CAB |
|---|---|---|---|---|---|---|
| Scan scheduling & execution | I | I | R / A | C | I | — |
| Finding triage & prioritization | I | I | R / A | C | I | — |
| Remediation script development (detect/remediate/rollback) | I | — | R / A | C | C | — |
| Change approval | A | I | R | C | C | R |
| Tiered deployment (pilot → pre-prod → prod) | I | — | C | A | R | — |
| Post-deployment verification | I | — | R / A | C | C | — |
| Rollback during deployment window | I | — | C | I | R / A | — |
| Risk acceptance / exception approval | A | C | R | C | C | I |
| Program reporting | A | I | R | I | I | I |

## Notes on the non-obvious rows

**Rollback** breaks the "Security Analyst owns remediation work" pattern on
purpose. The Analyst builds the rollback script, but authority to *execute*
it during an active window sits with the Lead Systems Engineer — the person
present when something goes wrong shouldn't need to wait for the person who
wrote the script to be reachable. This matches what CAB actually decided, not
just a theoretical ideal.

**Risk acceptance** is the one row where the CISO holds Accountable rather
than the Security Analyst. Choosing not to fix something is a risk decision
made on the organization's behalf, not a technical judgment call — it belongs
with the role that owns risk tolerance, even though the Analyst is the one
who identifies the candidate and drafts the compensating control.

**Change approval** lists CAB as Responsible rather than Accountable because
CAB is a body, not a single accountable owner — the CISO remains ultimately
accountable for the program approving something that later goes wrong, even
though the board is what actually reviews and approves each change.
