# VoiceBox Architecture

## Goal

VoiceBox is designed as a self-hosted, offline-first video dubbing
system.

The initial architecture prioritizes local processing, modular
components, reproducibility, and the ability to replace individual
processing engines without rebuilding the entire application.

## High-Level Pipeline

Video Input
    ↓
Media Analysis
    ↓
Audio Extraction
    ↓
Speech / Non-Speech Detection
    ↓
Speaker Detection
    ↓
Speech-to-Text
    ↓
Translation
    ↓
Voice Generation
    ↓
Timing / Duration Alignment
    ↓
Audio Mixing
    ↓
Video Rendering
    ↓
Final Dubbed Video

## Core Components

### 1. Media Analysis

Responsible for:

- Video metadata
- Resolution
- Frame rate
- Duration
- Audio streams
- Source language detection where supported

### 2. Audio Processing

Responsible for:

- Extracting audio
- Separating speech from non-speech audio where possible
- Preserving background audio
- Preparing audio segments for processing

### 3. Speaker System

Responsible for:

- Detecting different speakers
- Associating speech segments with speakers
- Managing temporary voice references
- Keeping speaker identity consistent within a project

### 4. Speech-to-Text

Converts detected speech into timestamped text.

Requirements:

- Local/self-hosted operation where practical
- Timestamp support
- Multi-language capability
- Segment-level processing

### 5. Translation

Translates recognized speech into the selected target language.

Requirements:

- Preserve proper names
- Preserve numbers and important entities
- Maintain segment timing information
- Support future language expansion

### 6. Voice Generation

Generates target-language speech while attempting to preserve
speaker characteristics.

Requirements:

- Local/self-hosted model support
- Speaker-specific voice references
- Segment-level generation
- Natural pacing
- No permanent voice storage unless explicitly required

### 7. Timing Engine

Aligns generated speech with the original speech timing.

Possible operations:

- Duration analysis
- Speech-rate adjustment
- Segment alignment
- Silence preservation

### 8. Audio Mixer

Combines:

- Dubbed speech
- Background audio
- Preserved non-speech expressions where appropriate

The mixer must avoid unnecessarily replacing laughter, crying,
shouting, or other meaningful non-speech sounds.

### 9. Renderer

Produces the final video.

Responsibilities:

- Replace or mix audio
- Preserve video quality where practical
- Maintain synchronization
- Produce a standard playable output

## Data Flow Principle

Each major component should communicate through clearly defined
intermediate data.

Components should remain replaceable.

No single AI model should permanently lock the entire architecture
to one provider or implementation.

## Offline-First Principle

The system should prefer local/self-hosted processing.

External paid APIs are not part of the initial architecture.

Any future optional online service must remain replaceable and must
not be required for the core local workflow.

## Security and Privacy

Uploaded media and temporary voice references should remain under
the user's control.

Temporary processing data should have a clearly defined lifecycle.

The system must not bypass DRM or other access controls.

## Development Rule

Architecture decisions are documented before implementation.

Major architecture changes require a checkpoint commit and should be
tested before promotion to the main branch.
