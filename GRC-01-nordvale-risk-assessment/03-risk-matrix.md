# 03 — Risk Matrix (5×5)

## Current position

| | Impact 1 | Impact 2 | Impact 3 | Impact 4 | Impact 5 |
|---|---|---|---|---|---|
| **Likelihood 5** | | | | | |
| **Likelihood 4** | | | R3, R5 | R2 | **R1, R6** |
| **Likelihood 3** | | R10 | R8 | R4, R9 | |
| **Likelihood 2** | | | R7 | | |
| **Likelihood 1** | | | | | |

**Reading it:** the top-right corner is the fire. R1 (backups) and R6 (government data exposure) are both Critical (20) — they dominate the treatment roadmap. R2 (Severe, 16) follows. The Significant band (R3, R4, R5, R9) forms the second wave.

## Target position (post-treatment residual)

| | Impact 1 | Impact 2 | Impact 3 | Impact 4 | Impact 5 |
|---|---|---|---|---|---|
| **Likelihood 5** | | | | | |
| **Likelihood 4** | | | | | |
| **Likelihood 3** | | | | | |
| **Likelihood 2** | | R10 | R3, R5 | R2, R4, R9 | |
| **Likelihood 1** | | | R7, R8 | | **R1, R6** |

**Note:** treatment mostly attacks **likelihood** (controls make the event harder), not impact — losing all backups would still be severe (impact 5), but immutability makes it rare (likelihood 1). This is the honest way to show residual risk: impact often stays; likelihood falls.

## Rating bands
Insignificant 1–5 · Minor 6–10 · Significant 11–15 · Severe 16–19 · Critical 20–25
