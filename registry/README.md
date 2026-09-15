# Node Registry

This directory is reserved for the cartridge's normalized node body once experiments justify stable records.

## Intended purpose

The registry should answer, without relying on chat memory:

- what nodes exist;
- what each node represents;
- what it requires and provides;
- whether implementation/data is embedded, referenced, or host-provided;
- whether the node is merely declared, resolvable, callable, tested, or currently active;
- where the node came from;
- which state/provenance/evidence applies to it.

## Proposed evidence ladder

Do not flatten these states:

```text
DISCOVERED
  ↓
NORMALIZED
  ↓
DORMANT
  ↓
RESOLVABLE
  ↓
CALLABLE
  ↓
OBSERVED
  ↓
COMPOSABLE
```

A node may remain useful at an earlier state without pretending it reached a later one.

## Registry rule

The registry represents capability potential and relationships. It must not silently grant execution authority, host access, source ownership, or proof of correctness.
