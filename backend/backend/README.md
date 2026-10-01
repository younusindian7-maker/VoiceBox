# VoiceBox Backend

## Purpose

The VoiceBox backend will coordinate the local video dubbing
pipeline.

It will eventually manage:

- Project management
- Media analysis
- Audio processing
- Speech recognition
- Speaker processing
- Translation
- Voice generation
- Timing synchronization
- Audio mixing
- Video rendering
- Job status and progress

## Architecture Rule

The backend must remain modular.

AI models and media-processing engines should be replaceable without
requiring a complete rewrite of the application.

## Processing Principle

The backend should prefer local/self-hosted processing.

No paid external API is required for the core workflow.

## Data Principle

User media should remain under user control.

Temporary processing files should have a defined lifecycle.

## Development Rule

New backend components are developed and tested on the `develop`
branch.

Stable, verified changes can later be promoted to `main`.

## Current Status

Backend implementation has not started.

This file defines the backend foundation before actual services are
implemented.
