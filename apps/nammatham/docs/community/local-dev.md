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

## Release Workflow Orchestration

References: scripts/release.ts

The …/release.ts file contains logic for automating the release process of a monorepo containing multiple packages. It allows bumping the version of all packages and dependencies, committing changes to git, publishing updated packages to npm, and tagging a new release in git.

The main entry point reads the current version, bumps the version accordingly based on release type, updates dependencies in package.json files, modifies the version in all package.json files, publishes packages to npm, and runs git commands to commit changes and tag the release.

Key parts of the release automation logic include:

- Increasing the version number based on the release type (major, minor, patch, alpha etc).

- Updating the dependencies in package.json files to the latest versions.

- Changing the version field in all package.json files within the monorepo.

- Publishing packages to npm, and handling publishing as a prerelease if the version contains 'alpha'.

- Running shell commands like git commit, tag and push. Allowing dry-run mode.
