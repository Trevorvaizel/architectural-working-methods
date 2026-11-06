---
name: vaizel-interior-rendering-physics
description: A gated interior architectural visualization workflow that turns a raw model screenshot or underdeveloped render into a controlled, photorealistic representation through sequential perceptual analysis, explicit locks, user approval, rendering, audit, and calibration. Use when the user wants to render, refine, relight, materialize, make luxurious, improve realism, or systematically evaluate an interior visualization while preserving architecture and design authorship.
metadata:
  short-description: Perception-led interior rendering with strict design fidelity
  version: "0.1"
  status: experimental
---

# Vaizel Interior Rendering Physics

Treat an architectural render as a **controlled inference surface**.

The objective is not merely to make an interior look attractive or photorealistic. The objective is to control what the viewer notices first, how the viewer reconstructs space, what makes materials believable, how light explains geometry, and how atmosphere emerges without quietly redesigning the project.

Rendering is not redesign.

## Non-negotiable operating laws

1. Preserve the user's architecture, proportions, camera, crop, perspective, furniture layout, built-in joinery, openings, ceiling geometry, fixtures, and material locations unless the user explicitly reopens them.
2. Do not generate or edit an image during analytical passes.
3. A user saying **"proceed"** advances exactly one workflow state.
4. Never skip unresolved passes merely because the likely final image is obvious.
5. At the end of each analytical pass, state what is proposed to be locked.
6. Locked variables remain fixed until the user explicitly reopens them.
7. "Improve", "luxury", "more realistic", "warmer", or "better lighting" are not permission to invent architecture, furniture, joinery, fixtures, styling, lighting features, or landscaping.
8. When a render is authorized, use the latest approved source and every accumulated lock.
9. An audit does not automatically authorize another render.
10. A calibration pass changes only the variables explicitly approved for calibration.
11. Never treat a calibration pass as a fresh generation.
12. If the user says to stop generating images, do not call image generation again until the user explicitly asks for a render or edit.
13. If fidelity and beauty conflict, preserve fidelity and explain the limitation.
14. Luxury is an emergent reading from restraint, spatial clarity, material differentiation, controlled light, visual silence, and precise detail. Do not add "luxury objects" as a shortcut.

## State machine

Maintain one explicit workflow state.

```text
SOURCE_LOCK
    -> REPRESENTATION
    -> ATTENTION
    -> LIGHT
    -> MATERIAL
    -> ATMOSPHERE
    -> READY_TO_RENDER
    -> RENDERED
    -> AUDIT
    -> CALIBRATION_READY
    -> CALIBRATION_ONLY
```

### Meaning of "proceed"

| Current state | Meaning of "proceed" |
|---|---|
| SOURCE_LOCK | Run Representation pass |
| REPRESENTATION | Run Attention pass |
| ATTENTION | Run Light pass |
| LIGHT | Run Material pass |
| MATERIAL | Run Atmosphere pass |
| ATMOSPHERE | Compile final render specification only |
| READY_TO_RENDER | Generate or edit the image |
| RENDERED | Run perceptual audit |
| AUDIT | Propose the smallest calibration set |
| CALIBRATION_READY | Apply only the approved calibration edits |
| CALIBRATION_ONLY | Audit the calibration without reopening the design |

Do not infer permission to generate an image before `READY_TO_RENDER`.

# Pass 0: Source Lock

## Objective

Separate design facts from rendering deficiencies.

## Inspect

Identify and record:

- camera position and eye level
- crop and aspect ratio
- perspective and lens character
- architectural shell
- openings and glazing
- floor and ceiling geometry
- stairs if present
- built-in joinery
- furniture positions and scale
- sanitary, electrical, lighting, and mechanical fixtures if visible
- material locations already defined
- exterior context
- user-declared non-negotiables
- ambiguous areas that must not be invented

## Questions

- What is definitely geometry?
- What is definitely an existing design decision?
- What is merely low-fidelity visualization?
- Which elements are ambiguous enough that changing them would become redesign?
- What has the user explicitly allowed us to change?

## Required output

```text
SOURCE LOCK

Locked architecture:
Locked camera:
Locked layout:
Locked material locations:
Allowed rendering changes:
Prohibited changes:
Ambiguities to preserve:
```

Do not render.

# Pass 1: Representation

## Objective

Define what the image is actually trying to make perceptible.

A render cannot communicate everything equally. Decide the representational bargain.

## Questions

1. What is the architectural subject?
2. What spatial or material relationship matters most?
3. What should the viewer understand in the first second?
4. What is supporting evidence rather than the subject?
5. What may safely recede?
6. What should this image say at thumbnail scale?
7. What would count as representational failure even if the image looked beautiful?

## Required output

State:

- architectural subject
- supporting spatial event
- tertiary information
- first-second reading
- one-sentence perceptual thesis

End with:

```text
LOCK PROPOSAL: REPRESENTATION
...
```

Do not render.

# Pass 2: Attention and Composition

## Objective

Construct the visual priority field without redesigning the room.

The eye does not inspect every pixel equally. Decide what wins, what supports, and what stays quiet.

## Diagnose the current read

Estimate:

```text
first read -> second read -> third read -> background
```

Then define the intended read.

## Questions

1. Where does the eye currently go first?
2. Is that where it should go?
3. Which element wins because of brightness rather than architectural importance?
4. Which important element is too quiet?
5. What are the three to five major perceptual masses?
6. Which elements already group correctly?
7. Which unrelated elements accidentally group?
8. Does any dark object become an undifferentiated mass?
9. Which edges need to be strong?
10. Which edges should soften or disappear?
11. What should remain high-information?
12. What should become visual silence?
13. Does the composition work at thumbnail scale?
14. Which elements should be perceptually sharp even if the image remains optically in focus?

## Required output

Lock:

- first read
- second read
- supporting field
- quiet zones
- contrast hierarchy
- edge hierarchy
- sharpness hierarchy
- elements whose dominance must decrease
- elements whose dominance must increase

End with:

```text
LOCK PROPOSAL: ATTENTION
...
```

Do not render.

# Pass 3: Light and Spatial Reading

## Objective

Use light as information about geometry, depth, orientation, and material.

Do not ask first, "Where should we add lights?"

Ask, "What spatial relationship must the light reveal?"

## Separate the lighting system

Identify:

- dominant daylight source
- direct sun if present
- diffuse sky contribution
- major bounce surfaces
- practical lighting already present
- shadow zones that must remain

## Questions

1. What is the believable primary light source?
2. What should direct light reveal?
3. What should remain in soft sky light?
4. Which planes require grazing light?
5. Which recesses require shadow to read as depth?
6. Where should bounce light recover information without flattening the room?
7. Which objects need contact shadow?
8. Which surfaces need form shadow?
9. Which cast shadows explain direction or distance?
10. Does the ceiling need a gradient to explain volume?
11. How should curtains mediate the transition between exterior and interior?
12. Which background spaces should remain one exposure level quieter?
13. What tonal range preserves both luminous openings and readable dark objects?
14. Where should practical lighting remain secondary?
15. Is warmth coming from believable sources or from a global color cast?

## Required output

Define:

```text
Primary source:
Direct-light role:
Diffuse-fill role:
Bounce strategy:
Contact-shadow strategy:
Form-shadow strategy:
Cast-shadow strategy:
Dark-object recovery:
Ceiling treatment:
Curtain treatment:
Background exposure:
Practical-light limit:
```

End with:

```text
LOCK PROPOSAL: LIGHT
...
```

Do not render.

# Pass 4: Material Evidence

## Objective

Make materials believable through their response to light, not through texture density.

Use this relationship:

```text
material perception =
surface structure
x reflectance behavior
x illumination
x geometry
x viewing angle
```

## For every major material ask

1. What property must the eye infer?
2. What visible cue would support that inference?
3. What cue is currently missing?
4. Does the texture scale match the architecture?
5. Is roughness too uniform?
6. Are highlights appropriate for this material?
7. Does the material require grazing light?
8. Does it need micro-shadow rather than more texture?
9. Is the material visually louder than its architectural importance?
10. Can two similarly colored materials still be distinguished by light behavior?

## Typical evidence

### Stone
- large-scale tonal variation
- correct texture scale
- restrained reflection
- micro-shadow
- relief revealed by grazing light
- material weight
- detail subordinate to the overall mineral field

### Timber
- correct grain direction
- correct grain scale
- restrained panel-to-panel variation
- satin reflection
- soft directional highlight
- warm reflected light
- real separation between slats or boards

### Fabric
- diffuse response
- soft highlights
- cushion or fold separation
- edge rounding
- subtle weave or nap
- compression and seam evidence
- preserved dark values without black clipping

### Curtains
- transmission
- opacity variation through folds
- soft edges
- density variation
- light passing through fabric, not merely brightening it

### Glass
- controlled transparency
- selective reflection
- environmental context
- edge or mullion depth
- angle-dependent response

### Metal
- precise highlights
- environmental reflection
- stronger specular behavior than fabric or plaster
- controlled, not universally glossy

### Painted plaster
- broad diffuse behavior
- very subtle surface variation
- light gradients
- low visual information

### Floor
- contact grounding
- broad low-intensity reflection
- restrained roughness
- enough light carriage to support depth
- no accidental mirror effect unless designed

## Required output

Rank materials:

```text
Highest material attention:
Medium material attention:
Low material attention:
```

Then state the dominant material relationship, for example:

```text
stone = weight
timber = warmth
dark fabric = softness
```

End with:

```text
LOCK PROPOSAL: MATERIAL
...
```

Do not render.

# Pass 5: Atmosphere and Luxury

## Objective

Let emotional reading emerge from a physically coherent room.

Atmosphere comes after architecture, attention, lighting, and material evidence.

## Questions

1. What emotional reading suits the design?
2. Should the interior be warm-neutral, cool-neutral, evening-warm, overcast-soft, or another clearly stated condition?
3. Which source creates warmth?
4. Is contrast deep or aggressive?
5. Where do midtones need to carry material richness?
6. Which areas need visual silence?
7. How much styling already exists?
8. Would adding objects become redesign?
9. Which practical lights may enrich the scene without becoming the subject?
10. What imperfections prevent mathematical perfection without becoming visible distress?
11. How much highlight rolloff, bloom, atmospheric depth, or depth of field is appropriate?
12. Does anything look like it is trying too hard to signal luxury?

## Luxury test

Ask:

> Does anything look like it is trying to convince me that this room is luxurious?

If yes, reduce it.

## Required output

Lock:

- emotional reading
- white-balance relationship
- contrast character
- practical-light intensity ceiling
- styling limit
- imperfection level
- visual-silence zones
- photographic treatment
- explicit things not to add

End with:

```text
LOCK PROPOSAL: ATMOSPHERE
...
```

Do not render.

# Pass 6: Render Specification

Enter `READY_TO_RENDER`.

Compile the approved locks into one concise production specification.

## Required sections

```text
RENDER SPECIFICATION

SOURCE FIDELITY
ATTENTION HIERARCHY
LIGHTING
MATERIAL RESPONSE
ATMOSPHERE
DO NOT CHANGE
DO NOT ADD
SUCCESS TEST
```

### Success test must include

- first read lands on intended subject
- architecture remains unchanged
- major spatial layers remain readable
- lighting direction is coherent
- dark objects retain information
- each major material is distinguishable by light behavior
- windows do not overpower the architecture unless intended
- quiet zones stay quiet
- luxury emerges from restraint rather than added decoration

Stop after compiling the specification unless the user explicitly authorizes rendering.

# Rendering Gate

Only generate or edit when:

1. state is `READY_TO_RENDER`, and
2. user explicitly says to render, generate, edit, apply, or says "proceed" while already in `READY_TO_RENDER`.

When editing a supplied image, use that exact source as the geometry authority.

Do not rebuild the scene from scratch if an image edit can preserve the source more faithfully.

# Pass 7: Perceptual Audit

After rendering, do not immediately create another version.

Enter `AUDIT`.

Evaluate the actual result against the locked representation.

## Audit questions

### Representation
- Does the image communicate the approved thesis before detail?
- Does the thumbnail read correctly?

### Attention
- Where does the eye actually go first?
- Does anything unintended outrank the subject?
- Are the major perceptual masses still correct?
- Did any new styling or lighting create a competing focal point?

### Grouping
- Do intended object families read together?
- Did unrelated elements accidentally fuse?
- Did dark furniture become a black mass?

### Depth
- Are foreground, middle ground, and background distinct?
- Do occlusion, perspective, contrast falloff, shadow, and detail agree?

### Lighting
- Is the source direction coherent?
- Do bounce and shadow explain geometry?
- Are contact, form, and cast shadows doing different jobs?
- Is any sunlight or practical light too theatrical?

### Materials
- Does each major material read from light behavior?
- Is any surface relying on texture alone?
- Is stone reading as mass before detail?
- Are black materials distinguishable from one another?

### Atmosphere
- Does warmth come from plausible sources?
- Are quiet zones still quiet?
- Does luxury feel restrained?

### Fidelity
- Did the render invent architecture, joinery, furniture, fixtures, lighting, styling, or landscape?
- Did proportions, camera, crop, or perspective drift?

## Audit verdict

Use:

```text
PASS
STRONG PASS
PARTIAL PASS
FAIL
```

for each category, but do not average them into a meaningless numerical score.

Then identify the **smallest useful correction set**.

Do not render it yet.

# Pass 8: Calibration Protocol

Enter `CALIBRATION_READY`.

A calibration pass is surgical.

## Rules

1. List the exact variables to change.
2. List every major variable that must remain frozen.
3. Use the successful render as the parent/source.
4. Do not return to the raw source unless explicitly requested.
5. Do not introduce new styling, fixtures, furniture, materials, or geometry.
6. Do not change the camera, crop, perspective, lighting direction, or general exposure unless explicitly named.
7. If the image system cannot guarantee a surgical edit, say so before generating rather than pretending the result is calibrated.

## Required calibration proposal

```text
CALIBRATION ONLY

Change:
1.
2.
3.

Freeze:
- architecture
- camera
- crop
- furniture
- material locations
- lighting direction
- styling
- overall hierarchy
- all unnamed variables

Expected perceptual effect:
...
```

Only after user approval may the edit be executed.

# Error recovery

## If an analytical pass accidentally triggers image generation
Acknowledge the workflow breach, return to the prior approved state, and do not generate again until the proper gate.

## If a calibration drifts
Do not calibrate the drifted image again by default.

Return to the last approved benchmark render and restate:

- approved parent image
- named calibration variables
- frozen variables

Then retry only if the user asks.

## If the user changes the design mid-workflow
Explicitly reopen `SOURCE_LOCK` for the changed variables only. Preserve all unrelated locks where still valid.

# Compact invocation language

The skill should understand these user commands consistently:

- **"Start the workflow"** -> Source Lock
- **"Proceed"** -> exactly one state forward
- **"Lock it"** -> accept the current pass
- **"Render"** -> render only if READY_TO_RENDER
- **"Audit it"** -> run audit only, no generation
- **"Calibrate"** -> propose calibration variables, no generation
- **"Apply calibration"** -> edit only if calibration proposal is approved
- **"Reopen lighting"** -> reopen LIGHT and all dependent later states, preserving earlier locks
- **"Reopen material"** -> reopen MATERIAL and later states only
- **"Stop rendering"** -> disable image generation until explicitly reauthorized

# Core perceptual model

Use the compact perceptual model below to structure deeper reasoning. This portable experimental edition includes the model inline.

The compact model is:

```text
scene gist
-> priority
-> grouping
-> edge hierarchy
-> depth construction
-> light/form coupling
-> material evidence
-> shadow relationships
-> detail allocation
-> atmosphere
-> perceptual verification
```

A good render is not the image with the most information.

It is the image in which the right information becomes easiest to perceive.
