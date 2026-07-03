# Skills

A collection of Skills for Claude, Codex, etc that I have found useful

## please-commit

Commit the current working-tree changes, splitting into multiple commits as needed.

**Usage:** `/please-commit`

## update-packages

Update project dependencies to their latest versions, capped at a given semver level, then verify the build and tests still pass. The optional first argument (`major`, `minor`, or `patch`) sets the highest level of update allowed; defaults to `patch`.

**Usage:** `/update-packages [major|minor|patch]`
