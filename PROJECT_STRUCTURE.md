# VoiceBox Project Structure

## Purpose

VoiceBox is a self-hosted video dubbing platform designed to process
video, speech, translation, voice, timing, audio mixing, and rendering
through a controlled development pipeline.

## Planned Structure

- `docs/` — Project documentation
- `backend/` — Backend services and processing pipeline
- `frontend/` — User interface
- `models/` — Local AI model configuration and documentation
- `scripts/` — Development and maintenance scripts
- `tests/` — Automated and manual test resources
- `data/` — Local development data
- `output/` — Generated development output

## Development Principle

The project will be built incrementally.

Each major component will be:
1. Added on the `develop` branch.
2. Tested before being considered stable.
3. Committed as a checkpoint.
4. Promoted to `main` only after verification.

## Current Status

No application code has been created yet.

Phase 2 — Backup & Stability is complete.
Phase 3 — Project Structure is starting.
