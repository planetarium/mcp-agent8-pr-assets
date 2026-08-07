# static_3d_generate e2e prop fixture

**This directory is a live test dependency, not one-off PR evidence — do not move or delete it.**

`shield/round-shield.png` is the source image for the `static-3d-prop-generation`
case in `packages/server/e2e/specs/3d.spec.ts` (mcp-agent8). The spec hard-codes
its raw URL, so renaming this path breaks that e2e case.

## Why a prop and not a character

`static_3d_generate` exists because of a routing split: humanoid characters go to
`claythis_3d_generate` (which force-binds a 13-joint skeleton for animation), and
everything else — weapons, armor, props — goes to the static tool, precisely
because claythis would rig them too. Testing the static tool with a character
would exercise the wrong side of that split, and would also flatter the provider:
props are the harder reconstruction (thin rims, flat faces, hard edges are where
image-to-3D degrades), characters are the easy case.

## Why hosted here rather than generated per-run

The e2e harness runs the tools in-process with no HTTP server, so an image
generated during the run only ever gets a `file://` (or at best `localhost`) URL.
fal must fetch the reference image over public HTTP, so a generated fixture is
structurally unusable. Every other spec in the repo uses a stable hosted URL for
the same reason.

## Provenance

Generated through the repo's own `image_asset_generate` tool (fal `gpt-image-2`,
`style: realistic`, `assetType: item`, background removed), so the fixture matches
what the tool actually consumes in production, where static_3d_generate is fed
image_asset_generate output.
