# 07 — Lessons Learned (peer review cycle)

The first version of this assessment went through peer review — a colleague with more assessment experience read it cold and challenged it. This file documents what changed and why, because acting on review is the job, and the corrections are more instructive than the parts that were right first time.

## 1. Rescored the phishing risk (Minor 9 → Significant 12)
**Original:** Impact 3 × Likelihood 3 = 9 (Minor).
**Review challenge:** with 10% of a market entering credentials, likelihood belongs at 4 — the enabling conditions are *observed*, not hypothetical. And if any compromised account has privileged access, the consequence escalates.
**Lesson:** score the credible consequence and the observed likelihood, not the comfortable average. A simulation result is *evidence*, and evidence moves scores.

## 2. Fixed a scope error in the shared-accounts risk (R4)
**Original:** mitigation list included patching unrelated servers.
**Review challenge:** shared vendor accounts are an **identity** risk — no accountability, audit failure, insider misuse without attribution. Patching is out of scope.
**Lesson:** every control in a risk entry must trace to *that risk's* causal chain. A control that doesn't reduce this risk's likelihood or impact belongs to a different register entry — mixing them reads as a laundry list and erodes credibility.

## 3. Governance over blocking for AI tools (R10)
**Original:** lead control was blocking unapproved AI tools at the gateway.
**Review challenge:** blocking alone drives shadow IT — usage moves to personal devices where there is zero visibility.
**Lesson:** when a risky behaviour meets a genuine business need, the durable control is a *sanctioned path* (approved tool, acceptable-use policy) with technical guardrails (DLP) — not prohibition alone. Controls that fight human incentives lose.

## 4. Added contractual enforcement for supplier risks (R7, R8)
**Original:** technical fixes only (password resets, TLS).
**Review challenge:** a supplier's behaviour is governed by the contract; without an updated SLA forbidding insecure transmission, the fix doesn't stick.
**Lesson:** supplier controls come in pairs — the technical fix *and* the contractual clause that makes it enforceable and repeatable.

## 5. Business impact first, controls second
**Original:** risks described technically; controls listed exhaustively.
**Review challenge:** for a mixed committee, lead with what the organisation loses ("if backups are deleted we lose the recovery path — days of order data, revenue, customer trust"), and name the one or two controls that reduce the most risk fastest.
**Lesson:** decision-makers fund consequences, not configurations. Slides tell the story; the register is the appendix.
