# VoiceBox Python Version

## Initial Target

Python 3.12

## Reason

VoiceBox will use Python for its backend and AI-processing ecosystem.

Python 3.12 is the initial target because it provides a modern
Python environment while allowing us to evaluate compatibility with
the required AI, audio, and video dependencies.

## Compatibility Rule

Before adding any major dependency, its compatibility with the
selected Python version must be verified.

If a required model or dependency requires a different supported
Python version, that requirement must be documented before changing
the project environment.

## Environment Rule

The project must use an isolated virtual environment.

Recommended environment name:

.venv

The `.venv` directory must never be committed to Git.

## Current Status

Python has not yet been installed or configured for VoiceBox.

This document records the initial Python version target.
