# r3f

React Three Fiber bridge experiments for native React Native renderers.

This repository is a reserved public shell. It does not yet contain migrated production code.

## Intended Scope

- Native R3F scene bridge experiments
- Pointer and hit-testing helpers for native renderers
- Test helper patterns for React Native, Three.js, R3F, and WebGPU/Dawn
- Integration points that remain renderer-neutral where possible

## Migration Handoff

Sortessori is the reference app for validating native WebGPU/R3F compatibility, but this
repo should receive reusable bridge code only after the app proves the physical iOS
cutover. The current source of truth is
`../sortessori/docs/unruly-systems-migration-plan.json`, backed by
`../sortessori/docs/webgpu-cutover-audit.md`.

Import gate: physical iOS cutover evidence verified and package-boundary checks green.

Import production code here only after `../sortessori` has physical manual evidence for
touch, VoiceOver, sensory feedback, and Expo GL rollback, and passes:

```bash
bun run ci
bun run verify:webgpu-cutover
bun run verify:package-boundaries
```

The first eligible slice is renderer adapter patterns after Drei/R3F module-boundary
workaround is stable. Keep gameplay state, physics, and Sortessori-specific labels in
their existing packages.

## Non-Goals

- Forking R3F without a concrete compatibility requirement
- Coupling Sortessori game logic to one renderer too early
- Replacing existing fallback renderers before E2E coverage proves parity
