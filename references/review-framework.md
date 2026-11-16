# Review and feedback protocol

## Severity (impact, not moral certainty)
- Critical: plausible major harm to rights, safety, money or ability to make informed choices; strong evidence or urgent verification needed.
- High: significant misleading, coercive or exclusionary mechanism.
- Medium: meaningful usability/ethical risk with constrained impact or unresolved facts.
- Low: small but useful improvement.
Use `Needs verification` rather than fabricated certainty where backend facts are missing.

## Evidence labels
- Observed: directly visible in supplied artifact or demonstrated behavior.
- Inferred: plausible consequence requiring user research or technical verification.
- Unknown: cannot determine from supplied context.
Confidence: high/medium/low, separately from severity.

## Default actionable feedback
**Finding:** concise mechanism and where it occurs.
**Evidence:** what is observed vs unknown; confidence.
**Why it matters:** likely user effect, relevant rule IDs.
**Severity:** critical/high/medium/low with one-sentence justification.
**Recommended direction:** concrete change, including interaction and microcopy if relevant.
**Alternatives:** 2–3 structurally different patterns with trade-offs when a design choice warrants it.
**Validate:** behavioral test, implementation inspection, accessibility check or research question.
Keep routine responses shorter than full audits. No universal score without a justified method.

## Quality calibration
Rate each case 0–2 for: detection correctness; evidence discipline; actionable solution; genuine alternative diversity; proportional interruption. Compare across benchmark runs. Record false positives explicitly. Avoid inventing quantitative conversion uplift.
