# Ethical UX pattern library — v0.1.0
For each pattern, investigate actual system behavior before assigning intent or legal status. Positive alternatives are distinct interaction strategies, not cosmetic variants.

## 1 Consent and permissions
**Risk cues:** preselected optional marketing consent; bundled consent with terms; asymmetric accept/reject; permission demanded before feature context.
**Questions:** What is the legal basis? Is the request optional? What happens on refusal? Can consent be withdrawn?
**Better patterns:** (A) separate unchecked opt-in at decision point; (B) contextual just-in-time permission when feature is invoked; (C) granular preference center with easy later changes.
**Trade-off:** More choice may add friction; avoid overwhelming users with needless toggles.
**Rules:** AUT-01, AUT-04, PRV-02, PRV-04, MAN-04.

## 2 Checkout and pricing
**Risk cues:** fees revealed only at final step; silent cart additions; forced add-ons; ambiguous recurring charges; fake stock counters.
**Questions:** Is the cost truly mandatory? Are charges recurring? Is availability real? Is the summary editable?
**Better patterns:** (A) upfront itemized price summary; (B) explicit optional add-on selector with no preselection; (C) progressive price disclosure with persistent total when complexity warrants it.
**Trade-off:** Early comprehensive pricing can increase density; progressive disclosure must not hide material cost.
**Rules:** AUT-03, TRN-02, TRN-03, MAN-01, MAN-03.

## 3 Choice architecture
**Risk cues:** misleading visual hierarchy, deceptive defaults, guilt-based refusal, confusing alternatives.
**Questions:** What is recommended and why? Are consequences equivalent? Is the less prominent path discoverable?
**Better patterns:** (A) neutral side-by-side choices; (B) evidence-based recommendation with clear explanation and easy alternative; (C) guided decision aid based on expressed user preferences.
**Trade-off:** Visual hierarchy is not inherently manipulative; assess intent, context and material consequences.
**Rules:** AUT-01, AUT-02, MAN-02, MAN-04, FAR-03.

## 4 Onboarding and forms
**Risk cues:** unnecessary mandatory fields; coercive permission prompts; blameful errors; inaccessible form validation.
**Questions:** Which data is required now? Can the user skip? Are errors actionable? Is keyboard flow intact?
**Better patterns:** (A) minimal onboarding with deferred optional data; (B) progressive profile completion tied to feature value; (C) guest mode or try-before-signup when feasible.
**Trade-off:** Deferring information may complicate later fulfillment; justify mandatory fields by task.
**Rules:** PRV-01, AUT-02, FAR-04, ACC-01, ACC-03.

## 5 Notifications and engagement
**Risk cues:** unsolicited nonessential notifications; re-enabled settings after refusal; streak pressure; meaningless re-engagement.
**Questions:** Is this alert timely and useful? Can it be bundled, muted or scheduled? Is urgency real?
**Better patterns:** (A) essential-event notifications only; (B) digest with frequency controls; (C) user-triggered reminders and granular preferences.
**Trade-off:** Some safety-critical alerts may require prominent interruption; do not suppress genuine warnings.
**Rules:** WEL-01, WEL-02, WEL-03, WEL-04, AUT-02.

## 6 Cancellation and account control
**Risk cues:** hidden cancel entry; forced phone call when signup was self-service; repeated emotional retention prompts; inaccessible deletion controls.
**Questions:** What commitments remain? What happens to data? Is a confirmation required for irreversible action?
**Better patterns:** (A) direct self-service cancellation with transparent consequences; (B) pause/downgrade offered as an optional parallel path, not a barrier; (C) clear account/data controls with explicit confirmation for irreversible actions.
**Trade-off:** Protect against accidental irreversible deletion without turning confirmation into obstruction.
**Rules:** AUT-02, AUT-03, MAN-05, PRV-05, ACC-03.
