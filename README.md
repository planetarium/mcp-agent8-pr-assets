# mcp-agent8-pr-assets

Image hosting for [planetarium/mcp-agent8](https://github.com/planetarium/mcp-agent8) PRs and audit documents.

**This is not a source-of-code repository.** It only stores media evidence (measurement outputs, screenshots, audit visuals, generated video samples) referenced from PRs, issues, and `docs/*.md` in `mcp-agent8`. Binaries live here so they don't bloat the main repo's git history and so they have stable raw URLs for inline use in markdown.

Accepted formats: **PNG/JPG** for stills, **GIF** for motion previews, **MP4** for originals.

## Directory convention

```
<topic>/<YYYY-MM-DD>[-<purpose>]/<group>/<file>.{png,jpg,gif,mp4}
```

Examples:

- `spritesheet-audit/2026-05-19-realistic-phase16/orthogonality/anime_grid4_01.png`
- `spritesheet-audit/2026-05-19-realistic-phase16/main-n5/realistic_grid4_01.png`
- `cinematic-h3/2026-08-05/r2v/h3.gif`

## Inline usage

Files are addressed by their raw URL pattern:

```
https://raw.githubusercontent.com/planetarium/mcp-agent8-pr-assets/main/<path>
```

PNG/JPG/GIF render inline in any GitHub markdown context (PR body, issue, README).

**MP4 does not render inline from a raw URL.** `raw.githubusercontent.com` serves video as
`application/octet-stream` with `X-Content-Type-Options: nosniff`, so the browser refuses to
decode it, and GitHub's markdown sanitizer strips `<video>`/`<source>` tags outright. Store
MP4s here as downloadable originals and link to them, and publish a GIF alongside for the
inline preview. Keep each GIF under ~4 MB — GitHub's camo image proxy fails on large files.
The only way to get a native inline video player is drag-and-drop upload through the GitHub
web UI, which mints a `github.com/user-attachments/assets/...` URL and has no API equivalent.

## Collaboration

This repo is `public` so anyone — including external PR reviewers — can see inline images without authentication. Write access follows planetarium org membership; org members can push new evidence directly.
