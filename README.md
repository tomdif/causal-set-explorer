# Causal Set Explorer

Interactive visualization of causal sets — the discrete substrate of spacetime.

**[Live Demo](https://tomdif.github.io/causal-set-explorer/)**

## What You're Looking At

Each dot is a spacetime atom — one element of the causal set, randomly sprinkled (Poisson process) into a 1+1 dimensional causal diamond. Time runs upward, space runs horizontally.

- **Links** — causal links connecting nearest causal neighbors (the Hasse diagram edges)
- **Longest chain** — approximates the proper time along the longest timelike geodesic
- **Grow** — watch spacetime grow one element at a time (sequential growth)
- **Density** — increase it and watch the continuum emerge from discrete atoms

## Controls

| Control | What it does |
|---|---|
| Density slider | Number of spacetime atoms in the causal diamond |
| Show Links | Display causal links (nearest causal neighbors) |
| Longest Chain | Highlight the longest causal chain (proper time) |
| Grow | Sequential growth — spacetime atoms born one at a time |

## The Physics

This visualization accompanies the [Unified Theory](https://github.com/tomdif/unifiedtheory) project, which derives the Standard Model gauge group, fermion content, and mass ratios from a causal set substrate with a single primitive — the source functional.

The causal set is fundamental; the smooth spacetime is emergent. At low density, the discrete structure is visible. At high density, it approximates the continuum. The transition is the emergence of spacetime from combinatorics.

### Key observations

- **No metric on the points** — the geometry is reconstructed from counting (how many elements in each chain, which chains are longest)
- **The arrow of time is built in** — the causal partial order is irreversible; you can't un-birth an element
- **Chain angles encode velocity** — vertical chains are stationary, tilted chains move through space, 45° is the speed of light

## Related

- [Unified Theory (Lean 4)](https://github.com/tomdif/unifiedtheory) — formal verification of SM derivation
- [Causal Higgs Simulation](https://github.com/tomdif/causal-higgs-sim) — K/P mass ratio computations
