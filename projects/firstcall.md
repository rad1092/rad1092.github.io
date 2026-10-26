---
layout: project
lang: en
project: firstcall
title: FirstCall
description: Turn an API request into a tool an AI client can call.
permalink: /projects/firstcall/
---

## What it does

An HTTP request needs more than a URL before an AI client can use it: a call
that is known to work, inputs the model understands, and a safe place for the
token. FirstCall takes a request you already have and walks it through four
steps: read it, send it with real values, describe it, export it.

It reads curl commands, OpenAPI specs, HAR files from the browser, Postman and
Bruno collections, `.http` files and Hurl. The export is a folder that
FirstCall's own command-line runner serves as an MCP server, so there is no
generated code to build and nothing to install from npm or PyPI.

## How it is built

- One Rust codebase builds the desktop app (egui) and `firstcall-cli`, the
  runtime that serves exported tools over stdio.
- Exported tools only use GET and HEAD unless you allow more when exporting.
  Each call goes to the declared endpoint and nowhere else; redirects are
  refused.
- Responses come back as structured JSON with secrets redacted. A response over
  the size limit is refused rather than cut off.
- Tokens are saved per API in the OS keychain. One server process can carry
  many tools without handing one API's token to another.
- Request history and verified requests stay in a local SQLite database. There
  is no backend.

## Decisions

- **Export from a request that worked.** A tool starts from a request that was
  sent and answered, and the package keeps that verification record, so the AI
  client gets a call that is known to work.
- **No generated code.** Early versions exported TypeScript projects that had to
  be built. Now the runtime ships inside the app, and an export runs as it is.
- **Read-only by default.** Writing methods are an explicit choice at export
  time, because the tool will be called by a model, not a person.

## What's next

- A second package format without the legacy TypeScript and YAML exporters.
- Exporting several operations from one OpenAPI file at once.
