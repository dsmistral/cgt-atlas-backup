## Session 54 machine runs — batch 7 (Chunk 54c-VII: the ternary Golay code and the Witt designs) — 2026-10-12

### T1 — the cyclic code from Φ₁₁ over F₃
- **Factorization (machine):** x¹¹ − 1 = (x − 1)·g(x)·g'(x) over F₃, with the 11th cyclotomic Φ₁₁ = 1 + x + ⋯ + x¹⁰ splitting into exactly **two monic quintic factors**: g = x⁵ + x⁴ + 2x³ + x² + 2 (coeffs x⁵..x⁰: 1 1 2 1 0 2) and g' = x⁵ + 2x³ + x² + 2x + 2 (1 0 2 1 2 2). Both factors tested end-to-end.
- GOTCHA (dead first attempt, recorded): a sign bug in the synthetic division (correct: b_{j−1} = a_j + r·b_j, R = a₀ + r·b₀ for division by x − r) made the first run factor (x¹¹+1)/(x+1) instead — the run's own "remainder = 1 (expect 0)" flag caught it, but proceeding anyway produced a *negacyclic* twin that still passed the entire [11,6,5] battery (same weight distribution) while its −Σ extension was NOT self-dual. Lesson recorded: never proceed past a failed check; the correctly cyclic codes below extend self-dually.

### T2 — [11,6,5] from both factors (identical invariants)
- **Construction:** generator rows = the 6 cyclic shifts of g; all 3⁶ = 729 message vectors → **729 distinct codewords**; min distance = **5** — the code is **[11,6,5]**.
- **Weight distribution (byte-exact, both factors):** A₀ = 1, A₅ = 132, A₆ = 132, A₈ = 330, A₉ = 110, A₁₁ = 24 (sum 729) — the classical ternary Golay distribution.

### T3 — perfectness (direct machine check)
- All 729 codewords × all 243 error patterns of weight ≤ 2 (1 + 2·11 + 4·C(11,2) = 243) marked in a 3¹¹ = 177,147 counter: **overlap count = 0, uncovered = 0** — the 729 radius-2 balls **partition F₃¹¹** (perfect). (Arithmetic side: 729 × 243 = 177,147 = 3¹¹ ✓.)

### T4 — the Witt S(4,5,11)
- **132 weight-5 words, 66 distinct supports, exactly 2 codewords (c and −c) per support.**
- **S(4,5,11) machine proof:** all C(11,4) = 330 4-subsets covered exactly once by the 66 blocks (× C(5,4) = 5 each; multiply-covered = 0, uncovered = 0) — the supports ARE the Witt design blocks.

### T5 — the extension [12,6,6] and the Witt S(5,6,12)
- **Extension:** append −Σcᵢ (mod 3) to every codeword; from both factors: min distance = **6** — the **[12,6,6]** extended ternary Golay.
- **Self-dual (machine):** all pairwise dot products ≡ 0 mod 3, including self-products (⇒ all weights divisible by 3 ✓).
- **Weight distribution (byte-exact):** A₀ = 1, A₆ = 264, A₉ = 440, A₁₂ = 24 (sum 729).
- **The Witt S(5,6,12):** 264 weight-6 words → **132 distinct supports** (2 codewords each); all C(12,5) = 792 5-subsets covered exactly once (multiply-covered = 0, uncovered = 0) — the supports ARE the S(5,6,12) blocks (Aut = M12, web-pinned).

All numbers above are byte-exact outputs of these runs. Receipt for chunk 54c target (6), part 1 — ternary Golay.
