---
name: architectural-cinematic-maquette
description: Build cinematic, scroll-driven architectural maquettes from actual project models, using ivory architecture, tactile brown landscape and restrained spatial lighting. Use for an interactive architecture project story or an exterior maquette sequence.
---

# Architectural cinematic maquette

Create an authored architectural experience, preserving the actual building and its design reasoning. The target is a carefully lit physical architectural model in a dark world. White architecture must retain planes, depth and shadow; brown landscape and timber must retain texture. Warm light belongs to openings and credible fixtures.

Before building, read [the correction record](references/corrections.md). It contains the expensive lessons from the Resort Residence prototype; adapt its principles, not its project coordinates.

Carry the iterative making loop forward: source → candidate → exposure → human response → revision → inheritance. The actual project is the source kernel; accepted refinements are accumulated evidence. Returning to the first prototype must not erase the later lighting, gesture, narrative or fidelity corrections. Record the precise target a person accepted; approval of the Resort exterior is not approval of every interior or of Pin-Point. Browser checks establish observed behavior, while the person judges whether the feeling lands.

## Establish the project

Identify the actual FBX/glTF/Blender source and current renders. Inspect model bounds, orientation, duplicate buildings, loose furniture and ground extent before framing cameras. Preserve original sources; prepare a separate presentation derivative. A clean web export is not proof that its geometry matches the final project. Remove a misidentified render rather than inventing a substitute.

Write a short direction with: the intended feeling, authoritative sources, scope (exterior/interior), palette, light sources, and a sequence of spatial decisions. Preserve project-specific privacy rules. Define which project images, drawings and model derivatives may be published before packaging the presentation.

## Build the world

Prepare geometry in Blender when cropping duplicate source geometry, repairing normals, grouping fixtures or exporting a compact glTF is necessary. Three.js handles the browser scene, materials, light, camera and interaction. State which tool actually performed each task. A Blender bridge is optional; headless Blender is a valid preparation route.

Retain intricate silhouette and facade details. Use named material families: ivory, timber, earth, bronze, glass, foliage, cloth and emitter as applicable. Avoid palette optimization that merges their metadata. Start clean rather than carrying rejected coloured bake atlases into a new analytic lighting setup.

Separate the visible charcoal/brown sky from neutral daylight illumination. Fix a coherent sun direction across the journey. Match practical lights to actual apertures, aim and scale; bound their range. Warmth should read on nearby material and spill through real openings. A slight glow is secondary to lit surfaces. Artistic bounce proxies are approximations, not global illumination. Do not promise path-traced quality from a simple browser rig.

Build a tactile brown presentation base, restrained fine foliage and readable negative space. Context must frame the actual architecture, not obstruct it or invent site facts. Clearly distinguish presentation context and proposed lighting from documented construction.

## Direct the journey

Use one persistent model with composed camera positions and targets. Give each beat a distinct purpose: establish the whole, approach its public edge, reveal depth/shelter, return to the larger composition. Curves must remain outside geometry for exterior-only work. Do not cross walls to connect unrelated rooms; use a deliberate transition when spatial continuity is unavailable.

Native vertical scrolling advances the story. Horizontal dragging/swiping gives local look without stealing vertical touch scrolling. Include a small gesture nudge and an obvious reset. No keyboard dependency. Reduced motion should keep the same views and decisions accessible.

Where a project has both renders and a maquette, retain renders as the default project story and make “3D maquette” an explicit choice. Preserve design-decision explanations and final render order. Do not silently replace a strong project narrative with a model viewer. An isolated 3D proof can open directly in maquette mode when explicitly requested.

Load the web model only when needed. The loading preview must show the approved maquette or an honest neutral loading state, never a conflicting green/PBR scene. Keep the canvas hidden until the first composed frame. Do not reset a visitor's scroll when an asynchronous load finishes.

For a phone and metered-network delivery, defer the engine as well as the model until 3D is chosen. Do not prefetch models or hidden renders. Respect Save-Data/constrained connections. Consider a separately validated mobile derivative, keeping full-detail sources unchanged; inspect screens, silhouette and fixtures before accepting simplification. Use small compressed previews and content-versioned model URLs for persistent caching. Never upgrade the model automatically during rotation. Preserve chapter progress before resize-triggered scroll events reinterpret it. Bound pixel work and test gesture cancellation and scroll resumption after a turn.

## Judge the result

Inspect real browser frames at every camera beat, transition midpoints and reverse scroll. Check portrait as well as landscape: whole architecture where intended, no cut cars, ceiling-filled compositions, wall intersections, repeated views, bleached whites, moiré, opaque glass or flickering paving. Verify vertical touch intent and sideways look independently; distinguish emulation from a physical-phone test.

Compare against the reference as layers: silhouette/composition, material value hierarchy, directional light, contact/shadow, local warm spill, context and annotation. Fix the failed layer instead of globally increasing brightness. A successful build validates code, not visual quality.

Measure cold-network requests, download time and movement under a CPU slowdown using a production build. Verify that rotation, turning and mode changes do not re-download the model; movement should work after disconnecting once the scene is loaded. Do not equate this with offline page reload support. Discard background-tab/occlusion frame-rate measurements. Emulation and laptop GPU timings do not certify real Android/iPhone smoothness. Wait for loading fades to finish before comparing screenshots.

Record actual assets, camera beats, accepted/rejected frames, limitations and the next user's corrections in the project ledger. Update this skill only with reusable lessons. Validate a transfer on a different actual project before claiming the method transfers.

When live transfers fail, verify real body downloads rather than relying on HEAD status or local emulation. If the host supports ranges, bounded small-piece downloads and a best-effort cache can preserve completed work across a retry. Test an interrupted piece, recovery, repeat visits and storage-unavailable behavior; avoid parallel duplicate full downloads on hosts that ignore Range. Keep a usable render fallback.
