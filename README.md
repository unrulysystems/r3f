# r3f

React Three Fiber bridge experiments for native React Native renderers.

This repository is a reserved public shell. It does not yet contain migrated production code.

## Intended Scope

- Native R3F scene bridge experiments
- Pointer and hit-testing helpers for native renderers
- Test helper patterns for React Native, Three.js, R3F, and WebGPU/Dawn
- Integration points that remain renderer-neutral where possible

## Non-Goals

- Forking R3F without a concrete compatibility requirement
- Coupling Sortessori game logic to one renderer too early
- Replacing existing fallback renderers before E2E coverage proves parity