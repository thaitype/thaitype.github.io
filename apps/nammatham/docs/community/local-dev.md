---
sidebar_position: 1
---

# Local Development

## Local Dev Setup

```bash
# Install dependencies
pnpm install
# Before dev (Update workspace to local dependencies)
pnpm pre-local && pnpm install
# While dev
pnpm dev
# After dev before submitting PRs (Update workspace to actual dependencies), `pnpm install` for making sure lockfile is correct.
pnpm post-local && pnpm install
# Release package
pnpm release
```
