# Architecture v0.1 — Dormant Capability Body

Status: `RESEARCH`

This document defines vocabulary for experiments. It is not proof that the final cartridge architecture works at AXM scale.

## Three sizes

Always distinguish:

1. **stored size** — bytes required to represent the cartridge and any embedded payloads;
2. **active size** — RAM/CPU/GPU/process state currently materialized;
3. **reachable capability space** — capabilities and compositions that can potentially be realized from the stored structures plus declared external dependencies.

A major research target is allowing reachable capability space to grow much faster than active size without lying about stored size or dependencies.

## Cartridge layers

```text
CARTRIDGE
│
├── identity
│   ├── cartridge id/version
│   ├── source lineage
│   └── state fingerprints
│
├── node registry
│   ├── capability nodes
│   ├── primitive nodes
│   ├── state nodes
│   └── adapter/reference nodes
│
├── relationship graph
│   ├── requires
│   ├── provides
│   ├── consumes
│   ├── composes-with
│   └── conflicts-with
│
├── recipes
│   └── small graphs that compose reusable nodes
│
├── dormant payload/reference layer
│   ├── embedded implementation
│   ├── embedded data
│   └── external content-addressed reference
│
├── state
│   ├── canonical persistent state
│   ├── current activation state
│   └── evidence/receipts
│
└── host contract
    ├── required host abilities
    ├── activation/materialization
    └── suspend/export/resume
```

## Candidate node contract

A capability node may eventually contain fields similar to:

```json
{
  "id": "axm.node.example",
  "kind": "CAPABILITY",
  "state": "DORMANT",
  "inputs": [],
  "outputs": [],
  "requires": [],
  "provides": [],
  "implementation": {
    "mode": "EMBEDDED_OR_REFERENCE",
    "ref": null
  },
  "activation": {
    "conditions": [],
    "estimatedCost": "UNKNOWN"
  },
  "evidence": {
    "declared": true,
    "callable": false,
    "tested": false
  }
}
```

This is illustrative only; the schema belongs in `schemas/` once experiments justify it.

## Lifecycle

The desired lifecycle is:

```text
ABSENT
  ↓
INDEXED
  ↓
DORMANT
  ↓
RESOLVED
  ↓
MATERIALIZED
  ↓
ACTIVE
  ↓
RESULT / NEW STATE
  ↓
SUSPENDED
  ↓
DORMANT
```

A capability should not need to remain active merely because it is represented by the cartridge.

## Composition versus duplication

Prefer this where truthful:

```text
primitive A + primitive B + recipe C = capability D
```

instead of embedding a completely separate implementation of D when D is genuinely equivalent to the composition.

Never deduplicate merely because two capabilities sound similar. Equivalence requires evidence.

## Embedded versus referenced

A small cartridge may be small for different reasons. These must never be confused:

- implementation/data is genuinely compact and embedded;
- duplicated machinery was factored into reusable primitives;
- a capability is only a recipe over existing nodes;
- a large payload is content-addressed and stored externally;
- a host already provides the required primitive.

A cartridge that references 50 GB externally is not honestly a 2 MB self-contained cartridge.

## AI boundary

AI is optional at the architectural root.

Deterministic nodes, explicit state, human operation, recipes, and host adapters should remain useful without a neural model where practical. AI may improve interpretation, discovery, composition, planning, and growth, but it does not redefine the underlying node as an AI capability by default.

## First success condition

The first meaningful milestone is not "all AXM in one file."

It is:

> Convert a small set of real AXM capabilities into faithful dormant nodes, activate one minimal dependency closure on request, execute or materialize it, preserve evidence/state, suspend it, and prove that unrelated nodes never needed activation.

Then scale from evidence.
