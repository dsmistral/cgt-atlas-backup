## Session 53 machine runs — batch 2 (Chunk 53c-II: tree-decomposition DP lab + discharging/Euler) — 2026-10-12

### C1 — from optimal elimination order to a verified tree decomposition
- **Construction:** the exact-tw DP's argmin reconstructs an optimal elimination order; replaying the elimination game yields the fill graph and bags B_i = {v_i} ∪ (later fill-neighbors of v_i); bag i attaches to the bag of the first-eliminated later neighbor (parents strictly increase in elimination index).
- **Validated on 9 graphs** (K4, C5, octahedron, wheelW5, Petersen, grid2x3, grid3x3, icosahedron, grid4x4): width = tw ✓ (every graph), every vertex covered ✓, every edge in some bag ✓, running intersection (bags containing each vertex form a connected subtree) ✓, unique root + connected tree ✓.
- Honest catch: the first validator's tree check was defective (BFS started at node 0 and only traversed downward, but the root is the LAST bag) — corrected check all-green on all 9.
- **Worked example (grid3x3, tw 3):** order 0,1,2,3,4,6,5,7,8; bags {0,1,3},{1,2,3,4},{2,3,4,5},{3,4,5,6},{4,5,6,7},{5,6,7},{5,7,8},{7,8},{8} — a PATH decomposition of width 3 (each bag ≤ 4 vertices).

### C2 — DP on the decomposition vs brute force (all match)
- **Max independent set** (DP table per bag-subset, children agree on bag intersections, each vertex counted at its topmost bag): K4 1, C5 2, octahedron 2, wheelW5 2, Petersen 4, grid2x3 3, grid3x3 5, icosahedron 3, **grid4x4 8** — DP == brute force (2^n enumeration) on all 9.
- **Proper 3-coloring counts** (DP per bag-coloring, agreement on intersections): K4 0, C5 30, octahedron 6, wheelW5 0, **Petersen 120**, grid2x3 54, grid3x3 246, icosahedron 0 — DP == brute force (3^n enumeration) on all 8. (grid4x4 count skipped: 3^16 exceeds the brute oracle budget; α covers that graph.)
- Both DPs run on the SAME validated decompositions of C1 — the lab's point: tw bounds what is efficiently computable.

### C3 — discharging / Euler identities (stacked triangulations)
- **GOTCHA (recorded):** the first stacker used 32-bit vertex bitmasks at n=60 — JS bitwise ops truncate at 32 bits, so the identities broke spuriously from vertex 31 on (a single stack hand-checks clean). Rewritten with plain neighbor arrays (no bitmasks).
- **Stacked triangulations** (start K4, repeatedly stack a vertex into a uniformly chosen face), 3 seeds (20261012, 77031, 998877), n=300 each, identities checked at EVERY stacking step: n − m + f = 2 ✓, m = 3n−6 ✓, f = 2n−4 ✓, **Σ(6 − d(v)) = 12** ✓ (the discharging identity), min degree 3 ✓. All steps green, all seeds.
- **Light edge (Kotzig) on the sample set:** min d(u)+d(v) = stacked 7 (all 3 seeds), octahedron 8, icosahedron 10, W4 6, W5 6, W6 6, W9 6 — all ≤ 11 (the triangulation light-edge bound; the 3-connected bound 13 holds trivially on the samples).
- **Greedy 4-coloring in degeneracy order:** stacked triangulations are 3-degenerate ⟹ 4 colors suffice — proper 4-colorings on all seeds, exactly 4 colors used.
- **Planar sample chromatic numbers (exact backtracking):** octahedron 3 (K_{2,2,2}), icosahedron 4, W4 3, W5 4, W6 3, W9 4 (even/odd rim).
- Degree histograms recorded (deg-3 vertices ≈ 95–104 of 300; max degree 25–27) — the raw material for the L4 discharging narrative.

All numbers computed in-run (TS); no prior receipt reused. Seeds: LCG 20261012, 77031, 998877 (stacked-triangulation face choices; high-bit sampler).
