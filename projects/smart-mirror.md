---
layout: project
lang: en
project: smart-mirror
title: Smart mirror vision gateway
description: Real-time exercise coaching on a smart mirror, built by a team of three.
permalink: /projects/smart-mirror/
---

## The system

A smart mirror that sets an exercise routine, watches you do it and coaches you
afterwards. Three people built three parts:

- the mirror UI, in Tauri and React;
- the vision gateway, which I built;
- an AI coaching server that writes routines and feedback with NVIDIA models and
  retrieval.

The mirror only talks to the gateway, and only the gateway talks to the coaching
server.

## What I built

- Posture analysis with MediaPipe, repetition counting and live updates to the
  mirror over WebSocket.
- Validation of the baseline photos each user takes before training.
- The local record for every user in SQLite: profile, baseline, daily routines,
  body weight, results and coaching history.
- The requests to the coaching server and the JSON the mirror shows from its
  answers.
- The combined repository and the scripts that start and test all three parts
  on one machine.

{% include media.html m=site.data.projects.smart-mirror.media.extra lazy=true %}

## Decisions

- **Camera data stays on the gateway.** Raw frames, video, full landmarks and
  face features are never sent to the coaching server; it only gets the summary
  it needs.
- **No fake success.** When the coaching server is down, the gateway says so
  instead of returning a made-up routine.
- **One source of truth.** Daily routines, progress and coaching history come
  from the gateway's own database, not from asking the coaching server each
  time.
