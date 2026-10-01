# VoiceBox Technology Stack

## Selection Principles

VoiceBox will prioritize:

- Free and open-source software
- Local/self-hosted processing
- Offline-first operation
- No mandatory paid API
- Modular components
- Replaceable AI models
- Reproducible development
- Privacy-preserving processing

## Planned Technology Areas

### Media Processing

Primary role:

- Video metadata
- Audio extraction
- Audio replacement
- Video rendering
- Format conversion

The implementation should use a mature local media-processing
framework.

### Speech-to-Text

Required capabilities:

- Local inference
- Multiple languages
- Timestamped transcription
- Segment-level output
- Speaker-aware processing compatibility

The exact model will be selected after compatibility and hardware
testing.

### Speaker Detection

Required capabilities:

- Multiple speaker identification
- Speaker segmentation
- Timestamp association
- Compatibility with the transcription pipeline

The implementation must remain modular.

### Translation

Required capabilities:

- Local/self-hosted translation
- Multiple language pairs
- Proper-name preservation
- Segment-level translation
- Future language expansion

Translation models will be selected after benchmarking.

### Voice Generation

Required capabilities:

- Local/self-hosted inference
- Speaker reference support
- Multiple speakers
- Target-language speech generation
- Natural pacing
- Segment-level generation

The project will evaluate open-source voice-generation systems rather
than depending on a paid cloud voice API.

### Audio Processing

Required capabilities:

- Speech and background audio handling
- Volume control
- Silence handling
- Segment alignment
- Audio mixing
- Preservation of meaningful non-speech sounds where possible

### Timing and Synchronization

Required capabilities:

- Timestamp alignment
- Duration comparison
- Speech-rate adjustment
- Segment synchronization
- Final audio/video synchronization

### Application Layer

The application layer should remain separate from AI models and media
processing engines.

This allows individual components to be replaced without redesigning
the complete application.

## Model Selection Rule

No model is considered final before testing.

Each candidate model must be evaluated for:

1. License
2. Local execution capability
3. Hardware requirements
4. Language support
5. Quality
6. Processing speed
7. Memory requirements
8. Integration complexity
9. Offline operation
10. Redistribution requirements

## Hardware Rule

Hardware requirements will be measured before committing to a
production configuration.

The system must have a documented fallback path for machines with
limited resources.

## Dependency Rule

Required dependencies should be:

- Open-source where practical
- Version-pinned when appropriate
- Documented
- Reproducible
- Replaceable

## Current Status

Technology selection is planned but not finalized.

No AI model or external service has been selected as a permanent
dependency yet.

The next phase will evaluate the available local technologies before
implementation.
