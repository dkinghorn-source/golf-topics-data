# golf-topics-data — DEPRECATED

This repository is deprecated as of **2026-05-27**.

The AI Coach golf topics database has migrated to **motionedge.ai**:

```
https://motionedge.ai/api/v1/topics/
```

Same JSON schema, same file layout, new host. The MotionEdge app's `TopicStore` now reads from the new URL by default; existing installs auto-migrate their cached source URL on first launch post-update.

## Why

- Unifies remote content serving with Tip of the Day (`/api/v1/suggestions/`)
- Gains proper `Cache-Control`, CORS, and analytics via Vercel
- Eliminates a public GitHub repo whose only purpose was serving JSON
- Edits to topics now flow through the `motionedge-web` repo's `public/api/v1/topics/` directory, same workflow as suggestions

## Soak period

This mirror will be kept alive and up-to-date through approximately **2026-07-08** (~6 weeks) as a fallback safety net for any MotionEdge installs that haven't yet picked up the new default URL.

**After 2026-07-08:** this repo will be archived (kept read-only for git history).

## Where to go now

- **Topics live URL:** https://motionedge.ai/api/v1/topics/topics-index.json
- **Source of truth:** `dkinghorn-source/golfproto` repo, `Topics/*.json`
- **Publishing:** `./scripts/push-topics.sh` in the golfproto repo (now pushes to motionedge-web)
- **Spec:** `markdowns/design_architecture/golf-topics-json.md` in the golfproto repo

Migration tracked in dkinghorn-source/golfproto issue #621.
