# VoiceBox Backend Technology

## Language

Python

Python will be used as the primary backend language because the
planned AI, audio, video, and machine-learning ecosystem has strong
Python support.

## API Framework

FastAPI

FastAPI will provide the HTTP API layer between the frontend and
backend processing services.

## Environment

The backend will use an isolated Python virtual environment.

Recommended environment:

.venv

Project dependencies will be documented and version-controlled
through dependency files rather than committing the environment itself.

## API Architecture

The backend will expose modular REST endpoints.

Initial logical areas:

- Health
- Projects
- Media
- Transcription
- Translation
- Speakers
- Voice Generation
- Processing Jobs
- Rendering

The exact endpoint design will be finalized during implementation.

## Processing Architecture

Long-running video and AI processing should not block normal API
requests.

The backend will therefore be designed so that processing jobs can
run independently from request handling.

## AI Model Integration

AI models must remain separate from the API layer.

The API should communicate with model-processing modules through
defined interfaces.

This allows individual models to be replaced without rewriting the
entire backend.

## Local-First Requirement

The core VoiceBox workflow should operate using local/self-hosted
components.

Paid external APIs are not required for the core system.

## Dependency Management

Dependencies will be explicitly documented.

The project should use pinned or appropriately constrained versions
when reproducibility requires them.

The virtual environment itself must never be committed to Git.

## Security

The backend must validate:

- File types
- File sizes
- Input paths
- Processing parameters
- Output paths

User-provided paths must not be allowed to escape the intended
workspace.

## Development Rule

Backend development happens on the `develop` branch.

Each major implementation milestone requires:

1. Implementation
2. Testing
3. Checkpoint commit
4. Verification
5. Later promotion to `main`

## Current Status

Technology decision documented.

Backend implementation has not started yet.
