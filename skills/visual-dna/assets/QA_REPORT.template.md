# QA_REPORT

- Batch / date / round: [values]
- STYLE_DNA version / CHARACTER_DNA version or N/A: [values]
- Anchor / approval state: [ID or none]
- Inspected assets: [paths or attachment IDs]
- Review type: [actual visual inspection / prompt lint only]
- Missing evidence / tool limitations: [items]

## Image findings

| Image ID | Rule ID | Expected | Observed + location | Method / confidence | Status | Severity | Repair |
| --- | --- | --- | --- | --- | --- | --- | --- |
| [ID] | [S/C ID] | [target] | [evidence] | [measured / visual estimate] | [pass/fail/uncertain/N/A] | [critical/major/minor] | [patch] |

## Series consistency matrix

| Image | Geometry | Identity or N/A | Color | Line | Rendering | Composition | Delivery | Critical gate |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| [ID] | [status + rule IDs] | [status] | [status] | [status] | [status] | [status] | [status] | [pass / fail / unresolved] |

- Systematic drift: [cross-image observation]
- Optional score and assessed weight coverage: [heuristic or omitted]
- Release recommendation: [pass / revise / insufficient evidence; reason]

## Revision record

| Round | Input → output IDs | Preserved locks | Targeted correction | Recheck and regressions | Remaining issues |
| --- | --- | --- | --- | --- | --- |
| [round] | [IDs] | [rules] | [change] | [evidence] | [items] |

- Next action / stopping reason: [done, budget exhausted, missing views, or user decision]
