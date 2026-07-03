---
name: update-packages
description: Update project dependencies to their latest versions, capped at a given semver level (patch by default), then verify the build and tests still pass.
---

Please update this project's dependencies to their latest versions, honoring the update-level cap below.

## Update level

The first argument, if present, sets the highest level of update allowed: `major`, `minor`, or `patch`. If no argument is provided, default to `patch`.

- `/update-packages` → patch updates only
- `/update-packages patch` → patch updates only
- `/update-packages minor` → minor and patch updates
- `/update-packages major` → all updates, including major versions

## Process

1. Detect the package ecosystem(s) in the repo (e.g. NuGet via csproj/Directory.Packages.props, npm via package.json) and enumerate outdated dependencies.
2. Apply every available update at or below the allowed level.
3. Build and run the test suite. If an update causes breakage, fix it when the fix is small and obvious; otherwise roll that update back and note it in the summary.
4. Summarize each package as old → new version, and separately list updates that were available but above the allowed level so they can be revisited.

Do not commit anything — end by offering to run /please-commit.
