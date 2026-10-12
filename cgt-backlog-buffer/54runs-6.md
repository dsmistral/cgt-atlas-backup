## Session 54 machine runs — batch 6 (Chunk 54c-VI: code bounds — GV greedy, Plotkin tightness, binary MDS triviality) — 2026-10-12

### C1 — Gilbert–Varshamov greedy witnesses (binary)
- **Algorithm:** lexicographic greedy (accept a vector iff at distance ≥ d from all accepted); pairwise distances of the accepted set fully re-verified; GV lower bound ⌈2^n / Σ_{j=0}^{d−1} C(n,j)⌉.
- **Results (byte-exact):** (7,3): greedy size 16 ≥ ⌈128/29⌉ = 5, V = 29; (8,3): 16 ≥ ⌈256/37⌉ = 7, V = 37; (10,4): 32 ≥ ⌈1024/176⌉ = 6, V = 176; (12,4): 128 ≥ ⌈4096/299⌉ = 14, V = 299. All pairwise ≥ d ✓, all greedy ≥ the bound ✓. (For scale vs. truth, Ch. 8's machine records — cited forward, not recomputed here: A(7,3) = 16, A(7,4) = 8, A(8,4) = 16, A(8,5) = 4.)

### C2 — Plotkin tightness witnesses
- **(6,4):** witness {000000, 111100, 110011, 001111}: size 4, min pairwise distance 4; Plotkin bound 2⌊d/(2d−n)⌋ = 2⌊4/2⌋ = 4 → **TIGHT** ✓.
- **(7,4):** the binary simplex [7,3] (all 8 codewords = evaluations of the linear forms on the 7 nonzero points of F₂³): size 8, min pairwise distance 4, all nonzero weights = 4 (equidistant); Plotkin bound 2⌊4/(8−7)⌋ = 8 → **TIGHT** ✓.

### C3 — binary MDS triviality census (n ≤ 7)
- **Algorithm:** every binary [n,k] linear code with 2 ≤ k ≤ min(n−2, ⌊n/2⌋) enumerated via full Gauss-Jordan RREF canonical keys over all k-subsets of nonzero vectors (duality: [n,k] MDS ⟺ [n,n−k] MDS, so k ≤ ⌊n/2⌋ covers all nontrivial k); min distance computed over all 2^k codewords; subspace counts cross-checked against the Gaussian binomial ∏(2^n−2^i)/(2^k−2^i).
- **Results (byte-exact):** n=4,k=2: 35 subspaces (GB 35 ✓), max d = 2 < 3; n=5,k=2: 155 ✓, max d = 3 < 4; n=6,k=2: 651 ✓, max d = 4 < 5; n=6,k=3: 1,395 ✓, max d = 3 < 4; n=7,k=2: 2,667 ✓, max d = 4 < 6; n=7,k=3: 11,811 ✓, max d = 4 < 5 (the simplex is the [7,3] optimum — one short of Singleton). **NO binary MDS code in the nontrivial range n ≤ 7 — triviality machine-confirmed.**
- **Trivial families reach Singleton equality (n = 2..8):** repetition [n,1,n] ✓; parity [n,n−1,2] (min nonzero even weight = 2) ✓; whole space [n,n,1] by definition ✓.
- GOTCHA (dead first attempt, recorded): the RREF pushed pivot-row copies before later columns eliminated their entries — keys were not canonical and subspace counts overshot the Gaussian binomials (e.g., 93,186 ≠ 11,811 at (7,3)); the Gaussian cross-check caught it; fixed before any receipt number was recorded.

All numbers above are byte-exact outputs of these runs. Receipt for chunk 54c target (5) — code bounds.
