## Session 54 machine runs — batch 8 (Chunk 54c-VIII: the binary Golay code, the octads, S(5,8,24)) — 2026-10-12

### H1 — the generator, found by machine
- **Factorization (machine, exhaustive over all 2¹¹ monic degree-11 polynomials):** (x²³+1)/(x+1) splits over F₂ into exactly **two monic degree-11 factors**: **g₀ = x¹¹ + x⁹ + x⁷ + x⁶ + x⁵ + x + 1** (coeffs x¹¹..x⁰: 101011100011) and **g₁ = x¹¹ + x¹⁰ + x⁶ + x⁵ + x⁴ + x² + 1** (110001110101). Both tested end-to-end with IDENTICAL invariants.
- GOTCHA (dead first attempt, recorded): the run was first given the pinned-from-memory polynomial x¹¹+x¹⁰+x⁶+x⁵+x⁴+x²+1 — which IS a true factor (= g₁) — but the hand-transcribed coefficient vector dropped the leading x¹¹ term (11 entries for a degree-11 polynomial), producing a bogus code with d = 5 that failed every Golay check (the run's own remainder flag + d-check caught it). Lesson: coefficients for machine runs must be machine-derived, never retyped; both factors below were found and used by enumeration.

### H2 — the [23,12,7] perfect code (both factors)
- **Construction:** generator rows = the 12 cyclic shifts of g; 4096 messages → **4096 distinct codewords**; min distance = **7** — **[23,12,7]**.
- **Weight distribution (byte-exact, machine; A₀..A₂₃):** 1, 0, 0, 0, 0, 0, 0, **253**, **506**, 0, 0, **1288**, **1288**, 0, 0, **506**, **253**, 0, 0, 0, 0, 0, 0, **1** (sum 4096 ✓). (The remembered distribution was correct — now machine-verified, not memory.)
- **Perfectness (machine):** minimum pairwise distance over ALL 8,386,560 pairs = 7 (⇒ radius-3 balls disjoint); V(23,3) = 1 + 23 + 253 + 1771 = **2048**; 4096 × 2048 = **8,388,608 = 2²³** ⇒ the 4096 radius-3 balls partition F₂²³ — the code is PERFECT.

### H3 — the extension [24,12,8] (both factors)
- **Construction:** append the overall parity bit; min distance = **8** — **[24,12,8]**.
- **Weight distribution (byte-exact, machine; A₀..A₂₄):** 1, 0, 0, 0, 0, 0, 0, 0, **759**, 0, 0, 0, **2576**, 0, 0, 0, **759**, 0, 0, 0, 0, 0, 0, 0, **1** — weights only 0, 8, 12, 16, 24; **octads = 759, dodecads = 2576**.
- **Self-dual (machine):** the 12 extended generator rows pairwise orthogonal including self-products (dim 12 = 24/2 ⇒ C = C⊥).

### H4 — the octads ARE the Witt S(5,8,24)
- **Machine proof:** all 759 weight-8 supports; every 5-subset of the 24 coordinates (colex-ranked, C(24,5) = **42,504** keys) covered by **exactly one** octad: multiply-covered = 0, uncovered = 0 (759 × C(8,5) = 759 × 56 = 42,504 ✓). The octad set is the block set of the Witt design S(5,8,24) (Aut = M24, order 244,823,040 = 2¹⁰·3³·5·7·11·23, web-pinned).

All numbers above are byte-exact outputs of these runs. Receipt for chunk 54c target (6), part 2 — binary Golay.
