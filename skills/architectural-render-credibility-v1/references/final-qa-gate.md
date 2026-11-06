# Final Credibility Gate

## Hard Fails

Reject the output immediately if any apply:

- the original design controller `O0` is unavailable, unidentified, or omitted from revision-chain QA;
- a same-house render stack has no identified `P01` approved project canon when prior approved views exist;
- camera, crop, massing, openings, ceiling geometry, furniture layout, or approved floor pattern changed;
- fidelity was judged only against the previous generated variant instead of `O0`;
- a later view contradicts approved stack canon for material, lighting, fixture, styling, or photographic language without explicit instruction;
- perspective lines no longer share a coherent camera;
- a required luminaire is missing, duplicated, inconsistent, or emitting unexplained light;
- shadow direction conflicts with the declared source;
- reflection has no plausible source or erases the material;
- material scale, grain, joint, or boundary visibly drifts;
- required cars, people, signage, planters, balcony pots, or other countable visible-use elements disappear, multiply, or move to a contradictory role;
- vegetation reads as fused texture, repeated stamps, pasted leaves, or equal-detail green noise rather than distinct plant bodies with soil, stems, gaps, and contact shadows;
- domestic/commercial typology changes without instruction;
- melted, duplicated, floating, fused, or impossible details remain;
- the output claims approval-level truth while important areas are invented.

## Weighted Score

Score each category and record one sentence of evidence.

| Category | Weight |
|---|---:|
| Design and camera fidelity | 25 |
| Light and shadow causality | 15 |
| Reflection and gloss hierarchy | 15 |
| Material identity and scale | 15 |
| Fixture and construction logic | 10 |
| Spatial and optical clarity | 10 |
| Project specificity and typology | 5 |
| Photographic finish | 5 |
| **Total** | **100** |

Pass at `85/100` or above with zero hard fails.

## Prompt Audit

Before generation, confirm the prompt includes:

- `O0` identified as the immutable geometry and camera controller;
- for same-house stacks, `P01` identified as the approved project canon and separated from the current view's geometry controller;
- prior generated variants limited to named approved qualities;
- image roles and authority order;
- locked camera and geometry;
- exact floor-pattern protection;
- visible-use inventory with counts and placement roles;
- requested change only;
- dominant light source and time of day;
- fixture apparatus and on/off state;
- material-specific gloss/reflection behavior;
- cross-view continuity for approved timber, stone, tile, plaster, metal, glass, vegetation, fixture family, color temperature, and photographic grade;
- curtain-filtered shadow behavior where applicable;
- highlight and clarity targets;
- anti-slop avoid list.

## Output Audit

Inspect at:

1. thumbnail scale for hierarchy;
2. full frame for geometry and lighting;
3. close view for material boundaries, fixtures, curtains, foliage, and pattern continuity.

Always compare against `O0`, not only the previous generated variant.

For same-house stacks, compare against both:

- the current view's own `O0-viewNN` for geometry, camera, crop, fixed elements, and floor/wall/ceiling pattern;
- `P01` and any approved later canon view for shared material, lighting, fixture, styling, and photographic decisions.

Check matching full-frame keylines:

- outer crop and horizon or vanishing system;
- ceiling, wall, floor, and column junctions;
- door, window, opening, and mullion edges;
- fixed furniture and fixture positions;
- repeating floor, wall-panel, slat, and tile rhythm.

Use the prior approved variant only to verify that its explicitly praised deltas were retained.

Check stack continuity:

- timber color, grain direction, roughness, board scale, and stain level remain in the same family;
- stone, plaster, tile, metal, and glass keep the same identity and relative gloss hierarchy;
- cars, people, signage, planters, and balcony pots preserve approved count and placement logic;
- LEDs, downlights, sconces, switches, and trims belong to the same fixture family and color temperature;
- vegetation follows the same density, species logic, leaf scale, translucency, and shadow behavior;
- color grade, exposure, contrast, grain, and highlight roll-off feel like one commissioned set;
- repeated architectural details remain consistent where the same room, corridor, facade, or built-in reappears.

## Revision Rule

- Apply the one-generative-hop rule: for `R2` and later, return to `O0` and reapply cumulative approved deltas.
- For same-house stacks, start each new view from that view's own `O0-viewNN`, then apply the `P01` canon ledger and any user-approved cumulative deltas.
- Do not use the approved `P01` render as the geometry target for another camera angle. Use it as canon reference only.
- If fidelity fails, discard the derivative and restart from `O0`.
- Do not repair geometry drift by editing the drifted image again.
- If one detail fails, a targeted local correction to the best current output is permitted only with O0 supplied simultaneously as geometry controller and a passing full-frame keyline comparison, as specified in SKILL.md. Otherwise return to O0.
- If atmosphere fails, preserve technical correctness and adjust exposure, highlights, shadows, reflections, and grade.
- Never solve a local problem by reopening the whole design.
