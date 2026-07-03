---
name: please-commit
description: Commit the current working-tree changes, splitting into multiple commits as needed.
---

Please commit these changes using multiple commits as needed.

## Co-authorship

By default, do NOT add a Claude co-author trailer to any commit.

If the argument `coauthor` is present (invoked as `/please-commit coauthor`), add the following trailer to the end of each commit message, separated from the body by a blank line:

```
Co-Authored-By: Claude Fable 5 <noreply@anthropic.com>
```

If the session is not running on a Fable 5 model, fall back to:

```
Co-Authored-By: Claude Opus 4.8 <noreply@anthropic.com>
```
