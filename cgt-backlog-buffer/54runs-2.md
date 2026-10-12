## Session 54 machine runs — batch 2 (Chunk 54c-II: Möbius inversion) — 2026-10-12

### M1 — divisor lattice (the classical μ), n ≤ 10⁴
- **Setup (machine sieves):** μ by linear sieve; φ by the multiplicative sieve (initialized φ[m] = m, then once per prime p | m: φ[m] ← φ[m]/p·(p−1)); τ by divisor-sum accumulation.
- **Identities checked for EVERY n = 1..10,000, all mismatches = 0:**
  - Σ_{d|n} 1 = τ(n) — 0 mismatches;
  - Σ_{d|n} μ(d) = [n = 1] — 0 mismatches;
  - Σ_{d|n} d·μ(n/d) = φ(n) — 0 mismatches;
  - Σ_{d|n} φ(d) = n — 0 mismatches.
- **Spot values (byte-exact):** τ(60) = 12, φ(60) = 16, φ(1) = 1, μ(30) = −1, μ(12) = 0, μ(1) = 1, φ(9) = 6, τ(9) = 3, φ(100) = 40.
- GOTCHA (recorded, dead first attempt): the φ sieve was run without initializing φ[m] = m (Int32Array zero-init made every φ = 0) — the identity checks caught it immediately; fixed before any receipt number was recorded.

### M2 — Boolean lattice B_k, k ≤ 6
- **Recursion (the correct Möbius form):** μ(x,y) = −Σ_{x ≤ z < y} μ(x,z) — first argument FIXED, z over ALL interval elements strictly below y (not just covers); memoized.
- **Result:** μ(0̂,1̂) = (−1)^k for k = 1..6: −1, 1, −1, 1, −1, 1 — all OK.
- GOTCHA (dead first attempts, recorded): (a) the recursion was first run in the WRONG interval direction (μ(z,y) instead of μ(x,z)) → all-zero results; (b) the z-enumeration included z = y itself → infinite recursion. Both caught by the (−1)^k oracle; this is the same class of bug as the previously-recorded "all strictly-larger interval elements, not just covers" gotcha.

### M3 — partition lattice Π_n, n ≤ 5
- **Elements:** all set partitions of {0..n−1} by restricted-growth generation; order = refinement; μ(0̂, z) computed by the same correct recursion in rank order (μ(0̂,1̂) = −Σ_{0̂ ≤ w < 1̂} μ(0̂, w)).
- **Results (byte-exact):** |Π_n| = 1, 2, 5, 15, 52 (B₄ = 15, B₅ = 52 ✓); μ(0̂,1̂) = 1, −1, 2, −6, 24 = (−1)^(n−1)(n−1)! — all OK.

All numbers above are byte-exact outputs of this run. Receipt for chunk 54c target (2) — Möbius inversion.
