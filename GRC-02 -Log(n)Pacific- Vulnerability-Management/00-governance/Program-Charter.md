# Vulnerability Management Program Charter

## Purpose

This program exists to reduce risk exposure across LogN Pacific's IT estate
through systematic identification, evaluation, and remediation of
vulnerabilities — replacing ad-hoc, reactive patching with a scheduled,
accountable cycle that a change board can govern and a scan can verify.

## Scope

All IT assets owned or operated by LogN Pacific: networks, servers,
endpoints, and associated applications. Full detail in
`Vulnerability Management Policy_ Production.md` §2.

## Program Objectives

- **Coverage:** every in-scope asset scanned on the policy's defined cadence,
  with no asset silently excluded from a scan cycle.
- **Timeliness:** findings remediated within the severity-based SLA defined
  in Policy §5, with the threat-intelligence override (CISA KEV / EPSS > 0.5)
  applied consistently rather than case-by-case.
- **Verifiability:** every closed finding is closed because a rescan
  confirmed it, not because a remediation script reported success. Detect
  scripts are read-only for exactly this reason — they're the same
  instrument used to open and close a finding.
- **Honest measurement:** where a scanner can't detect a control at all (see
  CHG-2026-007), the program states that limitation up front and measures
  success against an instrument that can, rather than reporting a
  scanner-invisible finding as unresolved.

## Governance Structure

- **Executive Sponsor:** Chief Information Security Officer (CISO)
- **Program Owner (operational):** Security Analyst — Vulnerability Management
- **Standing Change Body:** Change Advisory Board (CAB), weekly cadence with
  the Server Team
- **Full role definitions and decision authority:** see `RACI-Matrix.md`

## Authority

Two decisions are pre-delegated rather than routed through CAB each time,
because routing them would slow response without adding oversight value:

- **Rollback during an active deployment window** sits with the Lead Systems
  Engineer and does not require a further CAB approval — established at the
  CAB meeting that approved the tiered rollout model.
- **SLA escalation under the threat-intelligence override** (KEV listing or
  EPSS > 0.5) is automatic per Policy §5, not a case-by-case exception
  request — the point of writing the override into policy is that it doesn't
  need re-approving every time it fires.

Everything else — new changes, scope changes, risk acceptances — goes through
CAB.

## Success Metrics

- % of Critical/High findings remediated within SLA
- % of scan cycles completed on the defined cadence with no asset excluded
- CIS Benchmark compliance trend, checkpoint over checkpoint
- Finding count trend, read alongside severity mix — a shrinking count with
  the same severity mix closed is a different result than the same count
  shrinking because only Low findings closed

Current-cycle performance against these targets is tracked in
`Metrics, Prioritization and Cadence.md`, not restated here — a charter
states what's being aimed at, not what's already been hit.

## Review Cadence

Reviewed annually alongside the policy (Policy §9), or sooner if program
scope or governance structure changes materially.
