# Yang-Mills Mass Gap: A Geometric Framework

> *"The medium is the message. The message constraints are the medium constraints. The denomination is set by the geometry of the mint — and the mint's blueprint is printed on the currency it produces."*
>
> — James Squire

---

## Overview

This repository documents a conjectural geometric research programme toward a proof of the **Yang-Mills Mass Gap** — one of the seven [Millennium Prize Problems](https://www.claymath.org/millennium-problems/) posed by the Clay Mathematics Institute in 2000.

The central thesis is that the mass gap Δ > 0 is not a phenomenon that *emerges* from summing quantum interactions, but rather the **geometric rigidity of the gauge orbit space expressing itself as a minimum energy denomination**. The configuration space is bounded, curved, and incompressible — and the mass gap is the direct fingerprint of that incompressibility.

Three documents compose this programme:

| Document | Author | Role |
|---|---|---|
| `YangMills.txt` | James Squire | Original geometric proposal & framework |
| `YMCurvature.txt` | Chiko Roll | Rigorous proof of curvature scaling K ~ 1/λ₀ |
| `YMLowerBound.txt` | Lamington Roo | Research programme for uniform interior curvature bound |

---

## Table of Contents

1. [The Problem](#1-the-problem)
2. [Why Standard Approaches Fail](#2-why-standard-approaches-fail)
3. [The Geometric Framework](#3-the-geometric-framework)
4. [The Unification Identity](#4-the-unification-identity)
5. [The Core Equations](#5-the-core-equations)
6. [Proof Strategy & Conditions](#6-proof-strategy--conditions)
7. [Current Status: What Has Been Proven](#7-current-status-what-has-been-proven)
8. [Open Programme: The Uniform Lower Bound](#8-open-programme-the-uniform-lower-bound)
9. [Relationship to Existing Work](#9-relationship-to-existing-work)
10. [Open Questions](#10-open-questions)
11. [References](#11-references)

---

## 1. The Problem

**Yang-Mills theory** is defined on a principal G-bundle over ℝ⁴, where G is a compact simple Lie group (e.g. SU(2) or SU(3)). The action functional is:

```
S[A] = (1 / 2g²) ∫ Tr(F_μν F^μν) d⁴x
```

where `F_μν = ∂_μ A_ν − ∂_ν A_μ + [A_μ, A_ν]` is the curvature (field strength). The commutator term is non-vanishing precisely because G is non-abelian.

**Classically:** The equations of motion admit massless wave solutions. The field can be excited at arbitrarily low energy.

**Quantum mechanically:** Experimental data and lattice simulations consistently demonstrate a minimum energy **Δ > 0**, below which no excitation of the field exists. This is the **mass gap**.

No rigorous mathematical proof of its existence has been established. It is one of the seven Millennium Prize Problems.

---

## 2. Why Standard Approaches Fail

Perturbative quantum field theory expands the path integral in powers of the coupling constant `g`. This works at weak coupling but the series **diverges** at strong coupling — precisely the regime where confinement and the mass gap are physically operative.

The perturbative approach cannot reach the answer because **the answer lives outside the radius of convergence of the method**.

This framework sidesteps perturbation theory entirely by treating the mass gap as a *geometric constraint* rather than a *sum of interactions*.

---

## 3. The Geometric Framework

### 3.1 The Gauge Orbit Space

The space of all gauge connections `𝒜` carries a natural L² metric:

```
‖δA‖² = ∫ Tr(δA_μ δA^μ) d⁴x
```

Under gauge transformations, physically equivalent configurations are identified. The **physical configuration space** is the orbit space:

```
M = 𝒜 / 𝒢
```

This is an infinite-dimensional curved Riemannian manifold with non-trivial topology and — crucially — a **boundary**.

### 3.2 The Faddeev-Popov Operator

In Landau gauge (`∂_μ A^μ = 0`), the **Faddeev-Popov operator** is:

```
M^ab = −D^ab_μ D^μ
```

This operator governs the geometry of gauge fixing. Its spectral properties encode everything about how configurations are constrained.

### 3.3 The Gribov Horizon

The **Gribov region** Ω is defined as the set of gauge-fixed connections on which M is strictly positive definite:

```
Ω = { A ∈ 𝒜 : ∂_μ A^μ = 0, M^ab > 0 }
```

The **Gribov horizon** ∂Ω is the boundary of this region — the locus where the lowest eigenvalue λ₀ of M vanishes:

```
∂Ω = { A ∈ 𝒜 : λ₀(M) = 0 }
```

**Physical meaning:** As a field configuration approaches ∂Ω, gauge fixing breaks down completely. The interaction space is saturated. No further compression of the configuration is possible.

### 3.4 Curvature Divergence at the Horizon

The sectional curvature κ of the orbit space `M = 𝒜/𝒢` diverges as configurations approach the Gribov horizon:

```
κ(A) ~ 1 / λ₀(A)
```

This encodes the physical picture directly:

| Regime | λ₀ | Curvature | Physical State |
|---|---|---|---|
| Sparse interactions | High | Low | Field easily excited; perturbation theory valid |
| Dense interactions | Low | High | Field becoming rigid; perturbation theory fails |
| At horizon | 0 | ∞ | Complete saturation; no new configurations accessible |

---

## 4. The Unification Identity

### 4.1 The Central Claim

The Gribov horizon and the spectral zero of the Faddeev-Popov operator are not merely *correlated*. They are **the same geometric object described in two languages**:

```
∂Ω ≡ { λ₀(M) = 0 }
```

And since `κ(A) ≡ 1/λ₀(A)`:

> **The curvature of the medium = the inverse spectral gap of propagation**

### 4.2 The Medium Is the Message

In standard field theory, the manifold is the *stage* and physics plays out on it — space and dynamics are separable.

In the infinite-dimensional orbit space `𝒜/𝒢`, **this separation collapses entirely**.

The manifold is constituted by the field configurations themselves. The field's configuration history is the space it must propagate through. There is no background. The medium and the message are the same object.

The implication is precise: **the boundary conditions of the configuration space are identical to the propagation rules of the field.** You cannot change one without changing the other.

---

## 5. The Core Equations

### 5.1 The Mass Gap Bound (Lichnerowicz Analogy)

By analogy with the Lichnerowicz theorem — which bounds the first eigenvalue of the Laplacian below by the Ricci curvature on compact Riemannian manifolds — we apply this principle to the gauge orbit space:

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│    Δ ≥ √( inf_{A∈Ω} κ(A) · g²N / V_Ω )                    │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

Where:
- **Δ** — the mass gap (minimum energy of any excitation)
- **κ(A)** — sectional curvature of the gauge orbit space at A
- **g** — the Yang-Mills coupling constant
- **N** — rank of the gauge group (N=2 for SU(2), N=3 for SU(3))
- **V_Ω** — volume of the Gribov region Ω

### 5.2 The Interaction Spectrum

The eigenvalues λₙ of M correspond to distinct interaction modes, each constrained by the same Δ:

```
g²N · κₙ = ( Δ² · V_Ω ) / λₙ
```

Where n=0 corresponds to two-gluon coupling, n=1 to three-gluon coupling, and so on. **The mass gap does not emerge from the interactions — it organises them.**

### 5.3 The Bootstrap Fixed-Point Equation

Combining the two equations above yields the self-consistency condition:

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│    Δ² = g²N · inf_n ( κₙ · V_Ω / λₙ )                     │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

Δ is the **unique value** at which the curvature of configuration space, the volume of the Gribov region, and the eigenspectrum of all interaction modes are simultaneously consistent.

The mass gap is not derived from the interactions. It is the **attractor of the system** — the natural settling point of the interaction complexity itself.

### 5.4 The Unification Written Explicitly

```
∂Ω ≡ { λ₀(M) = 0 }
κ(A)  =  1 / λ₀(A)
Δ²    =  g²N · inf_n ( κₙ · V_Ω / λₙ )
```

These three lines are **one statement**. The geometric boundary of the accessible space, the spectral condition on propagation, and the minimum energy of excitation are projections of a single underlying object.

---

## 6. Proof Strategy & Conditions

The strict inequality Δ > 0 follows from three conditions:

### Condition I — Finite Volume

```
V_Ω < ∞   for SU(N) in four dimensions
```

Partial results exist via Zwanziger's work on the Gribov-Zwanziger action, which restricts the Yang-Mills path integral to the Gribov region. The four-dimensional case requires additional work.

### Condition II — Positive Curvature Bound

```
inf_{A∈Ω} κ(A) ≥ C(g, N) > 0
```

This is the **most technically demanding condition**. It requires establishing that the curvature of the infinite-dimensional orbit space is bounded uniformly away from zero throughout the Gribov region.

### Condition III — Spectral Positivity Inside Ω

```
λ₀(M) > 0   strictly inside Ω
```

This holds by definition of Ω. The challenge is to ensure the infimum over Ω is not achieved — that is, that the spectral gap does not collapse to zero except on the horizon itself.

If all three conditions are established rigorously, the fixed-point equation yields **Δ > 0** directly.

---

## 7. Current Status: What Has Been Proven

> *Source: `YMCurvature.txt` — Chiko Roll (2025–2026)*

Using **O'Neill's formula** for Riemannian submersions and **Faddeev-Popov spectral analysis**, the curvature scaling `K_M ~ 1/λ₀` has been rigorously proven.

### The Mathematical Setup

The projection `π: 𝒜 → M` is a Riemannian submersion. Since the total space `𝒜` is flat (K_𝒜 ≡ 0), O'Neill's formula (1966) simplifies to:

```
K_M(π_*X, π_*Y) = (3/4) ‖ Ω(X,Y) ‖²_{L²}
```

where Ω is the curvature form of the horizontal distribution `Ker d_A^*`, and ξ = M_A⁻¹(d_A^*[X,Y]) (invertible inside Ω).

### The Divergence Result

Near the horizon ∂Ω, decomposing the source term along the near-zero eigenmode ψ₀:

```
d_A^* [X,Y] = c₀ ψ₀ + η^⊥     (c₀ = ⟨d_A^* [X,Y], ψ₀⟩)
```

yields the dominant contribution:

```
K_M ~ (3/4) |c₀|² / λ₀(A)    as λ₀ → 0⁺
```

For generic 2-planes (where c₀ ≠ 0), **sectional curvature diverges as 1/λ₀**. This is now mathematically solid.

### Status Summary

| Claim | Status |
|---|---|
| `K_M ~ C / λ₀` near horizon (generic planes) | ✅ **Proven** |
| Curvature form Ω well-defined via FP inverse inside Ω | ✅ **Proven** |
| Uniform lower bound `inf_{A∈Ω} K_M ≥ C > 0` | ❌ **Open** |
| Lichnerowicz-type spectral bound in infinite dimensions | ❌ **Open** |
| Finite volume `V_Ω < ∞` in 4D | ❌ **Partial** |
| Uniqueness/stability of bootstrap fixed point | ❌ **Open** |

---

## 8. Open Programme: The Uniform Lower Bound

> *Source: `YMLowerBound.txt` — Lamington Roo (March 2026)*

While curvature diverges *near the horizon*, a mass gap requires curvature bounded **away from zero everywhere inside** Ω — including in weak-field regimes. The programme proposes using **Bakry-Émery Ricci curvature** with a horizon-repulsive weight function.

### The Weighted Geometry

Raw Ricci curvature may approach zero in weak-coupling directions. But the physical path integral restricts to Ω with an effective measure:

```
μ ≈ exp(-f) · vol_g
```

where `f` penalises proximity to ∂Ω. The relevant curvature operator becomes the **Bakry-Émery Ricci tensor**:

```
Ric_BE(f) = Ric_g + Hess_g f
```

If `Ric_BE ≥ Δ_BE > 0` uniformly, then modern Bakry-Émery–Lichnerowicz theorems yield a spectral gap, which projects to a mass gap in the quantized theory.

### Candidate Weight Functions

| Candidate | Formula | Motivation |
|---|---|---|
| FP trace regularization | `f(A) = α ∫ Tr((M_A⁻¹)^p) d⁴x` | Direct spectral penalty |
| Geodesic distance proxy | `f(A) ≈ β · dist_M(A, ∂Ω)²` | Geometric repulsion |
| Ghost propagator | `f(A) = γ · sup_x Tr(ghost propagator(x,x))` | Kugo-Ojima inspired |

### Six-Step Programme

1. **Local positivity near classical minima** — Linearize around almost-flat configurations, compute Hess f explicitly via perturbation theory, establish `Ric_BE ≥ ε > 0` in small geodesic balls.

2. **Exploit horizon as positivity barrier** — Use the proven `K_M → ∞` near ∂Ω to bound Hess f from below near the boundary. Apply comparison principles along minimizing geodesics.

3. **Global control via Bochner–Weitzenböck identities** — Derive the weighted Bochner formula for `Δ_f = Δ_g + ∇f · ∇`. Integrate over Ω to show `Ric_BE` cannot dip negative without contradicting boundary positivity.

4. **Curvature-dimension condition CD(Δ_BE, ∞)** — Verify displacement convexity of relative entropy along L²-Wasserstein geodesics. If `CD(Δ_BE, ∞)` holds, a log-Sobolev inequality yields exponential decay and a spectral gap ≥ Δ_BE/2 for `-Δ_f`.

5. **Asymptotics at spatial infinity** — Show `Ric_BE → 0` at infinity is incompatible via monotonicity along projected YM gradient flow or positive-mass analogs.

6. **Validation via lower-dimensional models** — Prove uniform `Ric_BE > 0` in 2+1D YM (known mass gap), compute discrete orbit-space `Ric_BE` on lattice, test SU(2) on T³ × ℝ.

### Timeline (2026 View)

| Stage | Difficulty | Estimate |
|---|---|---|
| Local positivity + Hessian near minima | Tractable | 1–2 years |
| Barrier patching + Bochner identities | Medium | 2–4 years |
| Rigorous CD(K,∞) in infinite dimensions + infinity control | Hard | 5–10 years |

---

## 9. Relationship to Existing Work

| Framework | Connection |
|---|---|
| **Gribov-Zwanziger theory** | Restriction of path integral to Ω; soft BRST breaking; ghost/gluon propagator consequences |
| **Kugo-Ojima criterion** | Confinement criterion expressed as a condition on the ghost form factor; inspires weight function candidates |
| **Lichnerowicz theorem** | Prototype for eigenvalue bounds from curvature on compact Riemannian manifolds; generalized here to infinite dimensions |
| **Bakry-Émery theory** | Weighted curvature-dimension conditions; log-Sobolev inequalities; the primary tool for the lower bound programme |
| **Functional renormalisation group** | Non-perturbative flow equations consistent with a mass gap; complementary approach |
| **O'Neill submersion formula** | The rigorous engine behind the curvature scaling proof |

The **novel contribution** of this framework is the explicit identification of the Gribov horizon and the spectral zero of M as the *same geometric object*, and the derivation of the bootstrap fixed-point equation as the natural consequence of this identity.

---

## 10. Open Questions

1. **Uniqueness of the fixed point** — The bootstrap equation may admit multiple solutions. Proving the physical mass gap corresponds to a unique, stable fixed point is essential.

2. **Functional analysis on 𝒜/𝒢** — The Lichnerowicz analogy applies to finite-dimensional compact Riemannian manifolds. Extending spectral bounds to infinite-dimensional orbit spaces requires new mathematical machinery.

3. **Finite volume in 4D** — Zwanziger's results are most complete in lower dimensions. The four-dimensional case requires additional work.

4. **Uniform curvature bound** — The hardest open condition: `inf_{A∈Ω} κ(A) ≥ C(g,N) > 0`. The Bakry-Émery programme described above is the current best strategy.

5. **Falsifiability check** — Any sequence `A_n ∈ Ω` with `Ric_BE(A_n) → 0` must hit the horizon or spatial infinity. This must be shown to contradict finite volume or the barrier — if such a sequence exists, the programme fails.

---

## 11. References

- Gribov, V.N. (1978). Quantization of non-Abelian gauge theories. *Nuclear Physics B*, 139(1), 1–19.
- Zwanziger, D. (1989). Local and renormalizable action from the Gribov horizon. *Nuclear Physics B*, 323(3), 513–544.
- Zwanziger, D. (2003). No confinement without Coulomb confinement. *Physical Review Letters*, 90(10), 102001.
- Singer, I.M. (1978). Some remarks on the Gribov ambiguity. *Communications in Mathematical Physics*, 60(1), 7–12.
- O'Neill, B. (1966). The fundamental equations of a submersion. *Michigan Mathematical Journal*.
- Narasimhan, M.S. & Ramadas, T.R. (1979). Geometry of SU(2) gauge fields. *Communications in Mathematical Physics*.
- Groisser & Parker (1987). The geometry of the Yang-Mills moduli space.
- Lichnerowicz, A. (1958). *Géométrie des groupes de transformations*. Dunod, Paris.
- Bakry, D. & Émery, M. (1985). Diffusions hypercontractives.
- Mondal, P. (2023). Bakry-Émery Ricci & YM orbit space. *JHEP*.
- Moncrief et al. (2018–2019). Curvature & mass in reduced YM-Hamiltonian.
- Dudal, D., Gracey, J.A., Sorella, S.P., Vandersickel, N., Verschelde, H. (2008). A refinement of the Gribov-Zwanziger approach. *Physical Review D*, 78(6), 065047.
- Squire, J. Yang-Mills Mass Gap: A Geometric Framework (original proposal).

---

## Document Status

| Document | Status |
|---|---|
| `YangMills.txt` — Original proposal | Conjectural framework; physically motivated; requires rigorous development |
| `YMCurvature.txt` — Curvature scaling | **Core result proven**: `K_M ~ C/λ₀` near horizon (O'Neill + FP spectral analysis) |
| `YMLowerBound.txt` — Uniform lower bound | Active research programme; grounded in partial results; requires significant new analysis |

> This repository represents a conjectural geometric research programme, not a completed proof. The equations presented are physically motivated and connect to established structures in the literature, but require rigorous mathematical development — in particular, functional analysis on infinite-dimensional Riemannian manifolds — to constitute a proof of the Millennium Prize problem.

---

*Framework initiated by James Squire (Tasmania). Curvature analysis by Chiko Roll. Lower bound programme by Lamington Roo. Last updated: March 2026.*
