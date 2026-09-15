# Schemas

Machine-readable contracts for AXM Magic Box belong here only after experiments establish what information is actually required.

Likely future contracts include:

- `axm.node-cartridge/v1` — cartridge identity, body fingerprint, embedded/reference inventory, and host requirements;
- `axm.capability-node/v1` — one normalized dormant capability/state/primitive node;
- `axm.activation-plan/v1` — the exact dependency closure proposed for one request;
- `axm.activation-receipt/v1` — what was actually materialized/started, cost/evidence, result, and suspension state;
- `axm.cartridge-state/v1` — persistent canonical cartridge state separate from transient active runtime state.

## Schema principle

Do not design giant contracts from imagination. Grow schemas from real conversions of real AXM capabilities, and preserve `UNKNOWN` when a field cannot yet be grounded.
