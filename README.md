# Causal Set Explorer

Interactive visualization of causal sets, gauge fiber structure, and the derived Standard Model.

**[Live Demo](https://tomdif.github.io/causal-set-explorer/)**

## What You're Looking At

A 3+1D causal set — discrete spacetime atoms sprinkled by a Poisson process, with SU(3)×SU(2)×U(1) gauge fiber structure computed live. Time runs upward.

The visualization shows the complete derivation chain: from discrete causal atoms → causal links → holonomy on gauge fibers → K/P mass ratios → the Standard Model.

## Features

### Core Visualization
| Feature | What it shows |
|---|---|
| **Atoms** | Spacetime elements, colored by generation (red=3rd, orange=2nd, green=1st) |
| **Links** | Causal relations — the Hasse diagram of the partial order |
| **Longest chain** | Proper time along the longest timelike geodesic |
| **Light cones** | Past and future null cones from the newest element |
| **Trail** | History of the causal set's growth |
| **Generation colors** | Three generations from the K/P fiber projection |

### Physics Panels
| Panel | What it computes |
|---|---|
| **Mass hierarchy** | Live K/P projection: m_top, m_charm, m_up, m_bottom |
| **SU(3) fiber** | The effective source direction c_eff on CP² |
| **Decoherence bar** | K-sector decoherence progress toward classical limit |
| **Product rule** | (m_c/m_t)(m_t/m_b) — derived value 2√2/3 ≈ 0.943 |

### Interactive Demonstrations

| Button | What it does |
|---|---|
| **Big bang** | Reset and watch spacetime grow from nothing |
| **Pulse** | Propagate a signal through the causal set |
| **Bell test** | Find a spacelike pair, trace shared causal ancestry, show S²=8>4 |
| **Uniqueness** | **SM gauge group uniqueness** — animated elimination of all Cartan types |
| **d=4 squeeze** | **Dimension derivation** — Lovelock (d≤4) + graviton (d≥4) → d=4 |
| **Holonomy** | **SU(3) random walk** — live holonomy accumulation showing mass ratios |

## Theorem Visualizations

### SM Gauge Group Uniqueness (Uniqueness button)

Exhaustive elimination over the complete Cartan classification of compact simple Lie algebras. Each type is eliminated one by one:
- B_n, C_n, G₂, F₄, E₇, E₈: no complex representations → no chirality
- D_n even: no complex representations
- E₆: 27-dim fundamental → 111 fermions > 15
- D_n odd: spinor dim ≥ 16 → 67+ fermions > 15
- A_n (n≥3): fund dim ≥ 4 → 19+ fermions > 15
- **Only SU(3) × SU(2) survives.**

Proven: `sm_gauge_group_unique` (Lean 4, zero sorry).

### Dimension Squeeze (d=4 squeeze button)

Two independent constraints squeeze spacetime to exactly 4 dimensions:
- **Lower bound** (green wall): graviton propagation requires d(d-1)/2-1 > 0 → d ≥ 4
- **Upper bound** (blue wall): Lovelock uniqueness — Gauss-Bonnet rank 5 > d → d ≤ 4
- **Result**: d ≤ 4 ∧ d ≥ 4 → **d = 4 uniquely**. String theory's d=10 shown excluded.
- Cross-check: YM tracelessness tr(T) = (1-d/4)|F|² = 0 ↔ d=4.

Proven: `dimension_squeeze` (Lean 4, zero sorry).

### SU(3) Holonomy Walk (Holonomy button)

Live animation of the holonomy product W = U_n···U_1 projected to 2D:
- **Red dot**: source direction φ (reference section on CP²)
- **Green trail**: random walk as SU(3) holonomies accumulate along a causal chain
- **Orange line**: perpendicular component = mass ratio m_light/m_heavy
- **White line**: parallel component = heavy generation mass
- The perpendicular fraction grows with chain length, creating the mass hierarchy from geometry.

## Controls

| Control | What it does |
|---|---|
| Speed slider | Rate of spacetime atom creation |
| Links slider | Opacity of causal link display |
| β slider | Gauge coupling strength (lattice convention β = 2N/g²) |

## The Physics

This visualization accompanies the [Unified Theory](https://github.com/tomdif/unifiedtheory) project, which derives the Standard Model from 7 inputs with formal verification in Lean 4 (zero sorry, zero custom axioms, ~120 files).

### What is derived (zero free parameters)

- **Gauge group**: SU(3) × SU(2) × U(1) — unique over all Cartan types
- **Spacetime**: d = 3+1 — from Lovelock + graviton squeeze
- **Generations**: N_g = N_c = 3 — from fiber sections on CP²
- **Fermions**: 15 per generation — from color parity + chirality + minimality
- **All charges**: (2/3, -1/3, 0, -1, 1) — from anomaly cancellation
- **Weinberg angle**: sin²θ_W = 3/8 at unification
- **Proton stability**: B-violating operators have dimension 6
- **CPT invariance**: from linearity of φ + Born rule
- **No anti-gravity**: obs = Q² + P² ≥ 0, CPT-invariant
- **No 4th generation**: N_g = N_c = 3 is forced
- **No extra dimensions**: d = 4 is forced by the squeeze

### Key observations

- **No metric on the points** — geometry reconstructed from counting
- **Arrow of time built in** — causal partial order is irreversible
- **Chain lengths encode proper time** — longest chain ≈ geodesic distance
- **UV-finite** — finite sums replace divergent integrals (no renormalization needed)

## Related Repositories

- [Unified Theory (Lean 4)](https://github.com/tomdif/unifiedtheory) — formal verification, ~120 files, zero sorry, zero axioms
- [Causal Higgs Simulation](https://github.com/tomdif/causal-higgs-sim) — K/P mass ratio computations (Python/GPU)
