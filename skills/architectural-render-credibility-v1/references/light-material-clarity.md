# Light, Material, Reflection, and Clarity

## Same-House Continuity Rule

When a render belongs to an approved sequence for the same house, compare material and light behavior against the approved project canon, not only the current source image.

Require continuity in:

- timber species family, tone, grain direction, board scale, roughness, and edge highlights;
- stone identity, relief depth, vein or aggregate scale, joint logic, and response to grazing light;
- tile pattern, grout readability, polish level, and reflection softness;
- plaster or paint roughness, color cast, and highlight roll-off;
- metal finish, fixture trim color, and brushed or polished behavior;
- glass reflectance, transparency, mullion visibility, and exterior brightness handling;
- correlated imperfection level: do not make one view sterile and another aged unless specified.

Lighting continuity does not mean identical light in every view. It means the same house obeys one lighting doctrine: matching color temperature ranges, visible fixture families, plausible switching logic, and a consistent relationship between daylight, practical light, reflections, and shadows.

## Reflection Rule

Reflection must reveal material identity and light direction. It must not become an independent decorative layer.

Check every reflection for:

- a matching source;
- correct location and orientation;
- plausible brightness;
- roughness-dependent sharpness;
- Fresnel behavior at grazing angles;
- occlusion near contacts;
- continuity across one surface;
- subordination to the surface's base color, pattern, and joints.

If a reflection hides the material, reduce its intensity, increase roughness, or improve highlight roll-off.

## Relative Gloss Hierarchy

Use these as visual targets, not rigid numerical specifications.

### Polished patterned tile, terrazzo, or glazed ceramic

- Low-to-medium roughness.
- Preserve crisp local highlights at grazing angles.
- Reflections remain dimmer and softer than the window or luminaire causing them.
- Grout and pattern stay readable through reflected bands.
- Avoid mirror behavior, duplicated light bars, and perfect black/white clipping.

Approximate PBR roughness starting range: `0.18–0.35`, adjusted to the real product.

### Honed stone or satin tile

- Medium roughness.
- Broad, low-contrast reflection.
- Vein, aggregate, or pattern remains primary.

Approximate starting range: `0.35–0.55`.

### Sealed pale timber

- Medium-to-high roughness with directional grain.
- Soft elongated highlights follow the finish and board direction.
- Board variation is subtle and non-repeating.
- Edges may catch a narrow highlight; faces must not read as plastic.

Approximate starting range: `0.42–0.65`.

### Mineral plaster or matte paint

- High roughness.
- No readable mirror reflection.
- Show fine grain through uneven diffuse response and grazing light.

Approximate starting range: `0.72–0.92`.

### Brushed champagne bronze

- Medium roughness.
- Small controlled highlights reveal the cylindrical or planar form.
- Brushing direction remains coherent.
- Avoid chrome-like mirror response or flat brown paint.

Approximate starting range: `0.28–0.48`.

### Clear architectural glass

- Very low microsurface roughness but physically layered with transmission and environmental reflection.
- Preserve thickness and frame contact.
- Exterior brightness must not erase mullions or turn the pane into a white rectangle.

Approximate starting range: `0.02–0.12`, adjusted for coatings and cleanliness.

### Linen sheer

- High roughness with transmission and fabric weave.
- Diffuse warm sunlight without self-luminescence.
- Preserve gravity-led folds, weighted hem, track, and slight overlap variation.
- Do not cast hard mullion shadows after filtering the same sunlight.

## Shadow Hierarchy

### Direct sun through uncovered glazing

- Crisp near the mullion projection.
- Softer with receiver distance.
- Warm light with neutral-to-cool ambient fill.
- Shadow geometry must correspond to actual mullions.

### Sun through sheers

- Wider penumbra.
- Lower contrast.
- Reduced specular reflection.
- Fabric weave may create very subtle modulation, never a sharp duplicate window grid.

### Contact shadow

- Densest at object-surface contact.
- Softens quickly with separation.
- Required beneath planters, hems, frames, fixtures, leaves, hardware, and furniture feet.

### Practical light

- Distribution follows the fixture type and optical aperture.
- Daylight scenes: off or clearly subordinate.
- Night scenes: visible source, plausible IES-like falloff, reflected response on nearby materials.

## Clarity Hierarchy

Judge three kinds of clarity independently:

1. **Spatial clarity:** openings, circulation, depth, destination, scale.
2. **Material clarity:** each surface remains recognisably distinct.
3. **Optical clarity:** detail survives without HDR harshness, clipping, halos, or uniform sharpness.

Improve clarity by:

- compressing highlights rather than globally darkening;
- deepening local midtones and contact shadows;
- reducing competing reflection bands;
- separating similar pale materials through roughness and subtle hue, not arbitrary contrast;
- reserving strongest contrast and sharpness for the architectural subject;
- retaining calm secondary areas.

For a bright interior, a useful correction sequence is:

1. lower exposure slightly (`~0.2–0.4 stop`);
2. recover window and curtain highlights;
3. restore local midtone depth;
4. soften only physically filtered shadows;
5. reduce floor reflections until pattern and grout read;
6. re-check timber grain and plaster response;
7. add subtle grain last.
