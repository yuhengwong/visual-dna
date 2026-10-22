# Visual QA and revision

Inspect actual images side by side with the DNA and an approved anchor when available. Match comparable view/scale; perspective and deliberate expression are not automatically drift. Prompt review alone is labeled prompt lint, never visual QA.

## Per-image checks

Use the rule IDs and their specified tolerances. Record observed value/description, expected rule, confidence, severity and evidence location (e.g. left eye, lower contour). Use pass / fail / uncertain / N/A. Unknown or obscured geometry stays uncertain. Distinguish a measured deviation from a subjective visual judgment.

Check silhouette and geometry; face placement; identity cues; palette roles/value hierarchy; line; texture/material/shadows; composition; and requested delivery properties. Validate actual file type, dimensions and alpha where inspectable. A checkerboard painted into an image is not transparency. Do not claim editable vectors from a raster preview. Inspect both full-size and intended small-size appearance when size is relevant.

## Cross-series checks

Create rows for assets and columns for critical rules. Compare to the anchor and to peers: head scale after normalization, eye/mouth relationships, silhouette cues, palette allocation, line weight, lighting, texture density, margins and optical weight. Check family-level similarity separately from same-character identity. If no anchor is approved, label the comparison provisional. Log systematic drift even when each image looks acceptable alone.

Default release gate: all critical constraints pass and no critical checks remain uncertain. Treat this as a design-review recommendation, not technical certification. Critical rules normally include identity (when required), geometry, palette hierarchy and the brief's required delivery properties. Report failed items individually; do not let an average conceal a missing identity feature.

Optional scoring, only if useful: geometry 25, identity 20, color 15, line 10, rendering/texture 10, composition 10, delivery 10. Score each applicable category 0–4 (0 contradicts, 1 major drift, 2 partial, 3 minor drift, 4 matches); total = 100 × sum(weight × score / 4) / sum(applicable weights). Unknown categories stay unscored; report assessed weight coverage and never use an incomplete score to pass a batch. State these are heuristic reviewer judgments, not calibrated similarity or originality metrics. Critical gates override the score.

## Targeted revision

1. Pick the top 1–3 observable failures, citing rule and image IDs.
2. Write a patch: preserve [passing locks]; change [specific feature] from [observed deviation] to [target]; vary nothing else unless the edit requires it.
3. Use editing when available and appropriate; otherwise regenerate from the frozen full prompt with the targeted correction. Record what was actually done.
4. Reinspect the new image and check regressions in previously passing critical rules.
5. Keep previous versions and record status. Stop after the user's budget or the default two rounds. Explain unresolved issues rather than declaring success.

Do not loosen DNA tolerances just to make an output pass. When an intended design direction changes, explicitly increment the DNA version and identify which past outputs need re-review.
