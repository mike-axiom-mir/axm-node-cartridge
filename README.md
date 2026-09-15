# AXM Magic Box

Technical repository: `axm-node-cartridge`

**AXM Magic Box** is the long-horizon convenience form of AXM: research toward representing AXM capabilities as compact deterministic nodes, relationships, state, activation rules, recipes, and dormant payload references so that a small cartridge can expose a much larger capability world without keeping everything active at once.

The working idea is simple:

```text
AXM capabilities
      ↓
normalize into nodes + contracts + relationships
      ↓
encode dormant capability potential
      ↓
small cartridge / state body
      ↓
universal host loads the cartridge
      ↓
activate only what the current state requires
      ↓
compose a much larger usable capability world
```

This repository does **not** claim that arbitrary information can be compressed without limit, that dormant nodes cost zero storage, or that a small file can violate information or energy limits. The research question is how much AXM can be represented through reusable primitives, deterministic state, relationships, recipes, references, and on-demand realization rather than duplicated always-active implementations.

## Product principle

**Pay for convenience, not permission.**

The intended AXM direction remains:

- underlying human-accessible capabilities stay reachable through free/public AXM work where their own licenses permit;
- research can be inspected and discussed;
- yearly wired monoliths and other free paths can remain available;
- a technically capable person should be able to assemble an equivalent capability path themselves from available material;
- the paid/support product, if this matures, is the finished convenience layer: compacted, indexed, wired, dormant-by-default, portable, maintained, and easy to use.

The Magic Box is not intended to become an artificial permission gate around capabilities that are otherwise available.

## Current status

`EXPERIMENTAL / RESEARCH`

Today this repository is a research body, not a finished cartridge runtime. The immediate work is to learn how to represent real AXM capabilities faithfully as nodes and state without destroying source truth, capability boundaries, provenance, or inspectability.

## Repository map

- [`docs/MAGIC_BOX.md`](docs/MAGIC_BOX.md) — human-facing product/end-goal description.
- [`docs/ARCHITECTURE.md`](docs/ARCHITECTURE.md) — current technical model and vocabulary.
- [`docs/PRODUCT_PRINCIPLE.md`](docs/PRODUCT_PRINCIPLE.md) — convenience-not-permission boundary.
- [`research/README.md`](research/README.md) — active research questions and experiments.
- [`registry/README.md`](registry/README.md) — future node/capability registry direction.
- [`schemas/README.md`](schemas/README.md) — future machine-readable contracts.
- [`LICENSE`](LICENSE) — research-visible proprietary terms for this repository's original implementation/materials.

## Core truth boundary

Keep these separate:

- **stored** != active;
- **declared node** != executable capability;
- **capability present** != capability tested;
- **recipe** != materialized implementation;
- **reference** != embedded payload;
- **small active state** != small total information;
- **large reachable state space** != every state being stored explicitly;
- **publicly visible research** != open-source permission to copy the implementation.

The goal is a tiny-feeling box with honest internals, not fake compression claims.
