# mcp-agent8-pr-assets

Image hosting for [planetarium/mcp-agent8](https://github.com/planetarium/mcp-agent8) PRs and audit documents.

**This is not a source-of-code repository.** It only stores PNG/JPG evidence (measurement outputs, screenshots, audit visuals) referenced from PRs, issues, and `docs/*.md` in `mcp-agent8`. Image binaries live here so they don't bloat the main repo's git history and so they have stable raw URLs for inline use in markdown.

## Directory convention

```
<topic>/<YYYY-MM-DD>[-<purpose>]/<group>/<file>.png
```

Examples:

- `spritesheet-audit/2026-05-19-realistic-phase16/orthogonality/anime_grid4_01.png`
- `spritesheet-audit/2026-05-19-realistic-phase16/main-n5/realistic_grid4_01.png`

## Inline usage

Files are addressed by their raw URL pattern:

```
https://raw.githubusercontent.com/planetarium/mcp-agent8-pr-assets/main/<path>
```

These render inline in any GitHub markdown context (PR body, issue, README).

## Collaboration

This repo is `public` so anyone — including external PR reviewers — can see inline images without authentication. Write access follows planetarium org membership; org members can push new evidence directly.
