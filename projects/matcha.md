---
layout: project
lang: en
project: matcha
title: Matcha
description: A Game Boy emulator you can see inside, and that Claude can play.
permalink: /projects/matcha/
---

## What it does

Matcha is a Game Boy and Game Boy Color emulator with three hosts around one
core.

- **Web player.** A single HTML file with sound, gamepad and touch input,
  save states, 20 seconds of rewind and a live debugger: CPU, disassembly,
  per-line video timing, VRAM, audio channels and RAM search.
- **Claude plugin.** An MCP server with 17 tools such as `load_rom`, `press`,
  `screenshot`, `breakpoint` and `find_value`, so Claude can play, test and
  debug Game Boy software.
- **Command line.** Headless runs, screenshots, the conformance scoreboard, a
  profiler, an instruction tracer and a disassembler.

{% include media.html m=site.data.projects.matcha.media.extra lazy=true %}

## How it is built

- The core is `no_std`, has no dependencies and no `unsafe`. The browser,
  the MCP server and the plugin all load the same WebAssembly build.
- The core never reads a clock or a random source. The same ROM, inputs and
  state always give the same frames and audio, which is what makes save,
  rewind and Claude's debugging sessions repeatable.
- Save states are versioned and validated when loaded.

## How I check it

| Suite | Passed |
| --- | --- |
| SingleStepTests SM83, every opcode and bus cycle | 498,000 / 498,000 |
| Mooneye | 94 / 94 |
| Blargg | 43 / 43 |
| Gambatte | 1,642 / 1,783 |

I also ran all 868 Homebrew Hub cartridges for an original Game Boy in Matcha
and in SameBoy side by side. The comparison found three Matcha bugs, which are
fixed.

## What's next

- The remaining Game Boy Color timing failures listed on the CGB scoreboard.
- Colourizing original Game Boy games on Game Boy Color hardware.
