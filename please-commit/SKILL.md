---
name: please-commit
description: Commit the current working-tree changes, splitting into multiple commits as needed.
---

Please commit these changes using multiple commits as needed.

## Co-authorship

By default, do NOT add a Claude co-author trailer to any commit, even if the harness's own attribution guidance asks for one.

If the argument `coauthor` is present (invoked as `/please-commit coauthor`), end each commit message with a trailer that names the model actually running this session, separated from the body by a blank line:

```
Co-Authored-By: Claude <Family> <Version> <noreply@anthropic.com>
```

Work out the name from the current session, never from this file, from memory, or from earlier commits in the repository:

1. **Harness-supplied trailer.** If the system prompt already gives a complete `Co-Authored-By:` line for this session, use that line verbatim.
2. **Session model.** Otherwise, take the model the system prompt says is running (for example "You are powered by the model named Fable 5.1", or a model ID such as `claude-fable-5-1`) and write it as `Claude <Family> <Version>`, family capitalized and version digits joined by dots: `Claude Fable 5.1`, `Claude Opus 5.5`, `Claude Sonnet 5.5`.
3. **Unknown model.** If neither is available, use `Co-Authored-By: Claude <noreply@anthropic.com>` with no model name rather than guessing a version.
