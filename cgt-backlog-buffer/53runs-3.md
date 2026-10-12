## Session 53 machine runs — batch 3 (Chunk 53d-II: list coloring) — 2026-10-12

### LC1 — choosability, exhaustive 2-list census (5-bit masks, palette {1..5})
- **K_2,4 is NOT 2-choosable:** all 1,000,000 two-list assignments enumerated (nonempty 5-bit masks; the b-side carries the two a-side masks plus the four b-side masks over the same 31-mask space); **720/1,000,000 fail.**
- The lexicographically-first failing assignment IS the classic textbook witness: a-side {1,2},{3,4}; b-side {1,3},{1,4},{2,3},{2,4}.
- **K_2,3 IS 2-choosable:** 0/100,000 fail.
- **ch(K_2,4) = 3:** all 1,000,000 three-list assignments (two runs of 500,000) are choosable — 0 failures. So the choice number of K_2,4 is exactly 3, with the 2-list witness above.

### LC2 — Galvin territory (edge-choosability of bipartite graphs: ch' = Δ)
- C4 (Δ=2): 10^4 exhaustive edge-list assignments — **0 non-choosable.**
- C6 (Δ=2): 10^6 exhaustive — **0 non-choosable.**
- K_3,3 (Δ=3): 3-lists sampled, seed 20261012 — **2000/2000 choosable.**

### LC3 — Thomassen territory (5-list planar sampler)
- 5-lists per vertex drawn from palette {1..8} (56 five-subsets per vertex), seed 777333; 300 samples per graph: octahedron 300, icosahedron 300 (avg 13 search nodes), wheelW5 300, grid3x3 300, stacked40 300 — **ALL 1500/1500 choosable.**
- stacked40: exactly 41 search nodes per sample — the 3-degenerate stacked triangulation colored by the reverse-peel greedy with **zero backtracking** (every vertex takes its first usable list color).

### Gotchas (record for the ledger)
- **Greedy order matters for the LAB narrative, not for correctness:** forward-peel (naive low-degeneracy-first) caused rare massive backtracking on hub vertices of the stacked triangulation; reverse-peel (peel order reversed for the coloring pass) is provably backtrack-free for a k-degenerate graph with (k+1)-lists — every vertex has at most k colored neighbors when reached, so one of its k+1 list colors is always free. Choosability verdicts were unaffected; only the search effort differed.
- LCG lowest-bit alternation (the standing 53c gotcha): all random draws use the high bits (rnd()>>16).

All numbers computed in-run (TS); no prior receipt reused. Seeds: LCG 20261012 (K_3,3), 777333 (Thomassen sampler).
