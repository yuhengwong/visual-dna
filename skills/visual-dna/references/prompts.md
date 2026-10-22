# Prompt construction

## Lock hierarchy

Use this order: explicit user brief → selected DNA version → character identity specification (if applicable) → approved anchor → task variation. If those sources contradict each other, surface the conflict instead of silently selecting one. An anchor is approved only when the user has selected it; a newly generated image is a candidate.

Copy the same fixed style block into each standalone prompt. Resolve rule IDs into actual wording: generators cannot interpret a local STYLE_DNA.md filename or S01 by themselves. Reference images must actually be attached/passed to the image tool; a filename in prose does not transmit an image. State each reference's role so a style reference is not accidentally used as the character identity.

## PROMPTS.md format

- Project, DNA version, identity version or N/A, anchor ID or none.
- Fixed STYLE LOCK: concrete geometry grammar, facial proportions when relevant, palette roles, line, light/material/texture and density. Use the most discriminating rules first.
- IDENTITY LOCK: original character's silhouette, features and signature cues; omit for non-character assets. Label same-character or same-family mode.
- Variable table: item ID, subject, pose/expression, view, composition, application/size and permitted variations.
- Each final prompt: fixed locks + that row's variables + delivery/background specification + concise exclusions.
- Reference attachment map and generation settings actually used, if any.

Prompt skeleton (replace fields with concrete content; do not leave placeholders in final prompts):

> Create [deliverable] for [use]. STYLE: [shape grammar and ratios], [palette and area roles], [outline behavior], [rendering and texture]. IDENTITY: [distinct silhouette and fixed face/marking/accessory arrangement, if applicable]. VARIATION: [pose, expression, action, camera]. COMPOSITION: [framing, spacing, background]. PRESERVE: [highest-priority invariants]. AVOID: [specific observable deviations]. OUTPUT: [requested format/size, subject to tool capabilities].

Prefer positive instructions plus 3–6 relevant exclusions. If the tool lacks a negative-prompt field, include exclusions in ordinary prose. Avoid contradictory pairs such as flat vector + photoreal material, no outline + heavy outline. Use model-specific syntax only when supported by the actual tool. Prompt wording may be Chinese or English per user preference; retain a stable terminology glossary when translating.

## Deliverable-specific decisions

| Asset | Lock | Vary | Validate |
| --- | --- | --- | --- |
| Mascot pose series | Identity + style | Pose, expression, prop interaction | Face grammar, silhouette cues, limbs, accessory placement |
| New characters in one family | Style | Species, silhouette, identity colors within palette rules | Family resemblance without cloning the anchor identity |
| Illustration series | Rendering, palette, shape and composition grammar | Story, environment, subjects | Foreground/background coherence and density |
| Icon family | Grid, optical size, stroke, corner and fill system | Symbol | Readability at target sizes, consistent visual weight |
| Brand campaign assets | Palette roles, motifs, rendering, margins | Message, composition and medium | Hierarchy, reuse of motifs, actual output constraints |

Do not force mascot facial ratios onto icons or landscapes. For icons, use a normalized grid and visual-weight checks; for brand visuals, identify motif and composition rules. Text, logos, true vectors, transparent background and exact pixel output need tool support and inspection; prompts alone do not establish them.

## Pilot and series

When the user requests a series without a test plan, propose a small pilot covering neutral front, three-quarter, profile, contrasting expressions and one prop/action. Generate only the requested scope/budget. For non-character work, substitute multiple symbols/scenes and a target small size. Compare pilots side by side before scaling. Keep a batch manifest with item ID, prompt version, output path, reference/anchor IDs, tool/settings if available and QA status. Seeds, when available, are repeatability aids, not identity locks or cross-tool guarantees.
