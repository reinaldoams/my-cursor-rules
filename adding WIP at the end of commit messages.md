---
description: Require WIP suffix on commit messages for incomplete work
alwaysApply: true
---

# Incomplete work commits

When drafting a commit message for work that is not end-to-end complete, append a `WIP:` line at the end.
Always make a oneline message.

## Format

Follow the project's commit style (lowercase, gerund phrases, semicolon-separated summary), then add a blank line and:

```
WIP: <what is still missing and what it is blocked on>
```

- Use uppercase `WIP:`
- SIngle line commit message;
- State what is missing and any blocker (ticket, API, dependency)
- Apply when the user asks for a commit message, not only when merging or sharing

## Example

```
adding product tag attach/detach control on products hq edit; proxying tag-side core api attach and detach via bff

WIP: blocked on FLC-374 staging — attach must use product_ids sync semantics and product show must expose tags
```
