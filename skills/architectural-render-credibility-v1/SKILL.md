---
name: architectural-render-credibility-v1
description: Direct, edit, and quality-check AI-assisted architectural and interior renders for design fidelity, multi-view project consistency, physical lighting, shadow causality, reflection and gloss hierarchy, material identity, construction logic, optical clarity, project specificity, and anti-AI-slop credibility. Use for client-facing render creation or revision from Lumion, D5, Enscape, V-Ray, Corona, SketchUp, BIM, CAD, or image references; especially when asked for photorealism, premium interiors, better materials, corrected daytime/night lighting, visible fixtures, preserved architecture, realistic reflections, less AI-looking results, final render approval, or a consistent render stack for the same house across views 01-10.
---

# Architectural Render Credibility V1

Produce an authored architectural image in which geometry, camera, light, matter, use, and client intent agree. Treat AI as a controlled enhancement layer, never as the source of spatial truth.

## Non-Negotiable Rule

Reject a prettier image if it changes approved architecture, camera, material identity, fixture logic, or project typology.

Never promote an AI-generated derivative into the permanent geometry controller. Keep the first source design render or drawing as the immutable spatial truth throughout the revision chain.

For a same-house render stack, treat the first approved render as project canon for visual decisions, not as a replacement for each later view's geometry source.

## Workflow

### 1. Declare the Image Contract

Classify the output before editing:

- `concept`: atmospheric exploration; invented detail is permitted when labelled.
- `material study`: geometry is locked; finishes may vary.
- `design development`: geometry and approved materials are locked; unresolved details must be explicit.
- `approval evidence`: all visible decisions must be source-backed, buildable, and revision-safe.

Use the strictest contract implied by the user. Never let photorealism imply more certainty than the sources provide.

### 2. Pin the Original Controller and Assign Source Authority

Inspect every image before editing. Assign each input one or more explicit roles:

- `geometry controller`: camera, crop, perspective, openings, planes, furniture, floor pattern.
- `material controller`: approved finish family, scale, grain, joints, roughness.
- `lighting controller`: time of day, sun direction, practical-light hierarchy.
- `styling controller`: curtains, art, planting, props, emotional cues.

Designate the earliest trustworthy design render or drawing as `O0 — original controller`. Record its exact file and never replace it with a prettier generated variant.

If sources conflict, `O0` outranks every generated variant for camera, crop, perspective, geometry, openings, fixed elements, and repeating patterns. State the authority order in every edit prompt.

Generated revisions may control only explicitly approved deltas:

- `R1 lighting reference`: praised exposure, fixture effect, or shadow quality;
- `R1 material reference`: praised finish, roughness, or reflection response;
- `R1 styling reference`: praised planting, curtains, art, or props.

Do not let a generated revision control unlisted qualities by inheritance.

For external mood references, extract only transferable qualities such as contrast ratio, highlight roll-off, tactile material response, planted depth, or occupancy mood. Do not copy unrelated sky color, setting, architecture, vegetation species, car placement, or composition unless the user explicitly requests that exact transfer.

Create three lists:

- `locked`: all source-backed invariants.
- `allowed`: only requested changes.
- `unknown`: details requiring conservative inference.
- `inventory`: countable visible-use elements that must persist across revisions, such as cars, people, planters, balcony pots, signage, light fixtures, and furniture.

#### Enforce the One-Generative-Hop Rule

Do not repeatedly edit an AI-generated revision into another AI-generated revision.

- For `R2` and later, return to `O0` as the edit target and reapply all approved deltas in one controlled prompt.
- Supply the preferred prior revision only as a secondary reference for its named approved qualities.
- For a truly local correction, a current revision may be the edit target only when `O0` is supplied simultaneously as geometry controller and the full-frame keyline comparison passes.
- If camera, crop, openings, ceiling/wall junctions, fixed furniture, fixture positions, or floor-pattern rhythm differ from `O0`, discard the derivative. Do not attempt to repair drift by editing the drifted image again.

#### Establish the View-Set Canon

When the user is producing multiple renders of the same house, room family, or structure, identify the first user-approved render in the stack as `P01 -- approved project canon`.

`P01` controls shared visual continuity:

- material passports: timber species/tone, stone identity, tile gloss, plaster roughness, metal finish, glass response;
- lighting language: time of day, dominant source, color temperature, fixture family, intensity restraint, shadow softness;
- camera language: architectural verticals, lens discipline, exposure style, highlight roll-off, grain, sharpening;
- styling language: curtains, planting density, art, decor restraint, client-specific atmosphere;
- construction language: reveal depth, trims, joints, handles, fixture visibility, LED channel logic.

For every later view, assign a local original controller such as `O0-view02`, `O0-view03`, or `O0-view10`.

Authority order for same-house stacks:

1. `O0-viewNN`: geometry, camera, crop, openings, fixed furniture, floor pattern, and view-specific spatial facts.
2. `P01`: shared project canon and approved visual decisions.
3. User-approved later renders: only the named deltas approved for that view.
4. External references: only their assigned lighting, material, styling, or mood role.

Do not copy `P01` geometry into other views. Translate its canon through the later view's own architecture. If a canon decision cannot be seen or plausibly caused in the new view, omit it or mark it unknown instead of inventing it.

When a later render is approved, add it to the canon ledger as `P02`, `P03`, etc. It may extend the canon for its visible area, but it must not contradict `P01` unless the user explicitly changes the house direction.

If an approved render contains a local flaw the user has already tolerated, do not propagate that flaw. Record it as a local exception, not a house-wide rule.

Track visible-use inventory across the stack. If a user approves cars at the entry, driveway, or undercroft, or people in midground activity zones, keep their count, placement logic, and role unless changed. Treat disappearing cars, invented extra vehicles, foreground posing, or crowding as fidelity failures.

### 3. Write the Typology and Emotion Sentence

Complete:

> This is a [domestic/commercial/ceremonial/service] space for [users] performing [ritual], and it must feel [emotion] rather than [wrong adjacent typology].

Use this sentence to reject generic boutique-hotel, showroom, spa, or Pinterest styling that contradicts the project.

### 4. Lock Camera and Composition

Preserve source camera position, eye height, focal behavior, crop, vanishing system, and controlled verticals unless change is requested.

Establish:

- one primary subject or spatial sequence;
- foreground, middle distance, and destination;
- clear leading lines without warped geometry;
- calm areas where detail and contrast recede.

Do not use depth of field to hide design evidence. Keep wide architectural views legible.

### 5. Build a Motivated Light Hierarchy

Choose one dominant source:

- daylight: sun/sky/windows dominate; practicals are subordinate or off;
- night: visible fixtures motivate pools, wall effects, and reflections;
- overcast: soft sky dominates; shadows and reflections remain low contrast.

For every important highlight, shadow, reflection, or glow, identify:

1. source;
2. direction;
3. receiver;
4. occluder;
5. softness;
6. scene-wide consequence.

Require visible physical apparatus for practical lighting. A bright pool without a plausible fixture is a hard fail.

For daylight with curtains:

- uncovered glazing may cast crisp mullion shadows;
- sheers must widen, soften, and weaken transmitted shadows;
- shadow softness should increase with distance from the occluder;
- practical fixtures should not compete with strong sun.

### 6. Establish Material Passports

For every hero material, record:

- real-world identity;
- module or texture scale;
- grain/vein direction;
- joint and edge logic;
- relative roughness and specular response;
- behavior in highlight and shade;
- appropriate correlated imperfection.

Read `references/light-material-clarity.md` when gloss, reflection, curtains, glass, timber, metal, tile, plaster, or shadow quality is important.

### 7. Run the Anti-Slop Force Scan

Read `references/anti-slop-forces.md` for critique, final work, or whenever an output feels generically luxurious, overly polished, physically ungrounded, or subtly wrong.

Check:

- statistical gravity;
- causal debt;
- fidelity drift;
- coherence horizon;
- motivated light;
- material identity;
- construction residue;
- correlated imperfection;
- typological pressure;
- truth gradient.

### 8. Shape the Edit Prompt

Use a precise local-edit operation supported by the available image tool when preserving an existing render. Supply the source and named change boundaries; if the tool cannot preserve them, report that limitation before editing.

Order the prompt:

1. input roles and authority;
2. exact locked invariants;
3. visible-use inventory count and placement logic;
4. smallest requested changes;
5. material passports;
6. light and reflection hierarchy;
7. construction and fixture logic;
8. optical finish;
9. anti-slop avoid list.

Repeat geometry, camera, floor-pattern, and approved-material invariants in every iteration.

For `R2` and later, make `O0` the edit target by default. Describe cumulative approved changes as explicit deltas and use the preferred prior variant only as a lighting, material, styling, or atmosphere reference.

For a same-house stack, include the view-set canon ledger in every prompt: `O0-viewNN` holds the current view's geometry, while `P01` and approved later renders hold shared material, lighting, fixture, styling, and photographic decisions.

Prefer one controlled revision over simultaneous unrelated experimentation. If design fidelity already drifted, return to `O0`; never heal a mutated derivative by generating from it again.

### 9. Apply Photographic Restraint

Use:

- highlight roll-off that preserves texture;
- readable midtones and dense local contact shadows;
- natural tonal falloff;
- subtle fine grain;
- restrained sharpening;
- coherent color temperature.

Avoid:

- bloom and halos;
- HDR crunch;
- global amber wash;
- clipped curtains or windows;
- uniformly sharp detail at every depth;
- reflections brighter than their causes;
- black levels so crushed that materials disappear.

### 10. Run the Final Credibility Gate

Read `references/final-qa-gate.md` and score the output.

Hard-fail and revise if:

- geometry, opening rhythm, camera, or approved floor pattern changed;
- the output was checked only against the immediately previous derivative rather than `O0`;
- a same-house stack render contradicts the approved `P01` canon without explicit user instruction;
- a required fixture is absent or a glow lacks apparatus;
- shadow direction or perspective is inconsistent;
- reflection obscures the material it belongs to;
- the intended domestic/commercial typology changed;
- the image contains melted, duplicated, warped, or implausible details.

Pass only at `85/100` or above with zero hard fails.

### 11. Save Non-Destructively

Never overwrite the source or an approved prior version unless explicitly requested.

For final project work:

- create a clearly named final-render folder inside the project;
- use a versioned, descriptive filename;
- retain the original generated file and copy the selected final into the project;
- report the skill location, final asset path, and remaining known limitations.

## Skill Boundary

This skill directs still-image credibility. Use geometry-native 3D/BIM tools for deterministic multi-view coordination, construction documentation, exact photometrics, or technical approval that cannot tolerate generative drift.
