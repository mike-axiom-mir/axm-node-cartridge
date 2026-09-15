# Research

This directory holds experiments that test whether AXM capabilities can be represented as compact dormant nodes and state without losing truth, provenance, or practical usability.

## Starting evidence / inspirations

The project should begin from existing evidence rather than pretending the idea appeared from nowhere:

- prior AXM node/state experiments, including the RPG/node work;
- state-floor and deterministic-node research;
- connected monolith capability inventory and wiring evidence;
- dormant/on-demand capability direction from AXM monolith work;
- `axm-compute-substrate` research into computation as structure, substrate, movement, reclamation, persistent flow and host realization;
- software-carried runtime examples such as LinuxPDF as conceptual evidence that a compact carrier can encode a much larger executable machine structure once interpreted by a compatible host.

None of these individually proves the Magic Box architecture.

## Active questions

1. What is the smallest truthful node representation of one real AXM capability?
2. Which capability information must be embedded, and which can be referenced?
3. How much implementation duplication can be replaced by shared primitives and recipes?
4. Can a host activate only the transitive dependency closure required for one request?
5. Can active state be suspended and later resumed deterministically?
6. How do we measure stored size, active size, activation latency, dependency count, and reachable capability count separately?
7. When does node indirection become slower or larger than the implementation it replaces?
8. Which AXM capabilities cannot be meaningfully compressed into recipes because they contain irreducible data or unique implementation?
9. Can a cartridge remain inspectable when node counts become very large?
10. Can human users directly inspect and invoke the same node body without requiring AI?
11. Can compute-substrate research reveal a better primitive than today's assumed node/activation model before the cartridge implementation hardens around the wrong abstraction?

## Current timing

**Do not rush the first whole-capability conversion experiment yet.**

The Magic Box is an end-product direction, not the place to prematurely freeze today's partial understanding of compute, state, nodes, activation, storage, or dormant capability structure.

For now:

```text
compute-substrate research
        +
state/node research
        +
monolith wiring evidence
        +
RPG/node and other bounded experiments
        ↓
better primitives and measurements
        ↓
Magic Box implementation later
```

The project should absorb stronger findings from `axm-compute-substrate` and related state/node work before choosing a durable cartridge representation.

## Future experiment family

When the research is mature enough to justify implementation, begin with a bounded real test rather than trying to ingest all of AXM immediately:

```text
3–10 real AXM capabilities
       ↓
normalize each into node records
       ↓
build dependency graph
       ↓
choose one requested output
       ↓
resolve only required nodes
       ↓
materialize / invoke
       ↓
record result + activation receipt
       ↓
suspend
```

Then measure what actually got smaller, what merely moved elsewhere, what became more complicated, and whether the chosen representation deserves to scale toward the larger AXM body.

## Research discipline

- No claim of infinite or lossless arbitrary compression.
- No capability count inflation from theoretical combinations alone.
- Referenced payload size stays visible.
- A dormant declaration is not executable proof.
- A successful one-off activation is not universal correctness.
- Negative results belong here too.
- Do not let convenience-product pressure outrun the research needed to choose the right substrate.
