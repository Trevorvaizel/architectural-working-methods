# Resort Residence correction record

The owner approved the exterior maquette direction after rejecting a generic CAD viewer and several overlit or burnt attempts. Transfer its visual logic, not its exact geometry, camera coordinates or light powers.

## Light and material

- Rejected: mottled coloured bake atlases plus new lighting. Successful baseline: clean actual geometry and independently controlled material families with analytic lighting.
- glTF Transform palette merging retained the first material's extras and destroyed ivory/timber distinctions. Use `--palette false` when runtime material families rely on extras. Preserve architectural geometry; do not simplify fine screens by default.
- A brown visible sky does not require brown illumination everywhere. Neutral daylight, a fixed warm-neutral directional sun, restrained fill and local practicals keep ivory readable.
- Nearest-light selection lit rooms through walls and duplicated the kitchen rig. Assign by real room/fixture identity, direction and bounded influence. Never add a universal ceiling-light grid to compensate for darkness.
- Glow on fixture lenses alone does not illuminate furniture. Evaluate light on nearby timber, seating, ceiling and outside the opening; keep shadowed planes and protect highlights.
- Added wall/downlights and path bollards are a presentation lighting proposal, separate from the source CAD. Do not claim they were designed or built originally.
- Repeated thick screen-space glass panes turned opaque grey. Thin low-opacity glazing was a deliberate browser approximation. Exclude it from opaque shadow casting.
- Local VSM shadows produced severe sofa artifacts. Removing problematic practical shadows while retaining sun/contact depth was better than covering artifacts with more fill.
- Fine wood grain needs derivative filtering to avoid shimmering in the distance. Grain should be subtle, not orange striping. Procedural grain is not scanned timber.

## Geometry and composition

- Oversized source ground and distant copies inflate bounds. Inspect the primary building and remove irrelevant duplicates in a derivative; keep original source untouched.
- Base top coplanar with paving caused road flicker. Separate the surfaces geometrically.
- A presentation crop cut cars. Crop around complete entourage, not merely the main walls.
- A threshold view at a bench/glass wall did not communicate entering. Place the camera through the actual opening with a clear destination.
- Kitchen and lounge became repeated compositions. Give each beat a distinct design purpose and angle. Check small rooms for chair/desk intersections and excessive close-up.

## Interaction and delivery

- Renders are the default story; maquette is a clearly named alternate. Preserve the original render text, details and design decisions.
- Native vertical scroll and horizontal look must coexist (`touch-action: pan-y`, horizontal intent detection). Do not require WASD or capture every swipe.
- Async initialization must not scroll back to the first chapter. Guard hidden-frame resize/zero-height calculations.
- Lazy-load 3D; render story should not pay WebGL startup cost. Use a maquette preview while loading, not a stale green model render.
- Validate actual browser images, not just compilation. Capture every authored endpoint and representative transitions on portrait and landscape. Physical phone testing must be reported honestly.

## Transfer test

Pin-Point Accommodation, requested 2 November 2026: actual exported model, exterior-only cinematic route, same restrained maquette language. Existing Pin-Point render story and room render galleries remain the default. Judge transfer by source fidelity, facade detail, controlled light, composed exterior movement and usable touch-first scroll. Human approval of the new project remains distinct from approval of the Resort.
