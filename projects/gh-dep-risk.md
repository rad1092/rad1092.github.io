---
layout: project
lang: en
project: gh-dep-risk
title: gh-dep-risk
description: Scores a pull request's dependency changes and says what to check first.
permalink: /projects/gh-dep-risk/
---

## What it does

`gh dep-risk pr 123` reads the dependency changes in a pull request, scores
each one, and starts the report with the three things a reviewer should check,
such as reading an install script before installing.

```text
left-pad 1.0.0 -> 2.0.0 score=48 (10 major version bump + 18 recently published version + 20 install script)
```

It can post one pull request comment and keep it updated, fail CI above a
level you choose, and write JSON or Markdown. A GitHub Action runs the same
check on every pull request.

## How it is built

- GitHub's Dependency Review API comes first and covers eleven ecosystems,
  including npm, pip, Go, Maven, Cargo and RubyGems.
- When that API is not available, it reads lockfiles itself for npm, pnpm,
  Yarn, Bun, Python and Go. There is no resolver and no full dependency graph;
  the supported cases are listed in a support matrix.
- Every point in a score comes from a named signal in one file, and the JSON
  output lists the breakdown for each change.
- Release checks install the extension and run it against real pull requests in
  two fixture repositories.

## Decisions

- **A command, not a service.** No server, webhook, database or GitHub App. A
  reviewer runs it when they need it, signed in with the GitHub CLI they already
  use.
- **Scores you can follow.** A number without reasons gets ignored, so every
  point names its source and the report says what to do next.
- **One comment, owned.** It updates its own comment and never edits or deletes
  someone else's.
