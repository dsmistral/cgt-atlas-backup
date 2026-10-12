## Session 53 machine runs — batch 4 (Chunk 53d-II: nowhere-zero flows) — 2026-10-12

### Solver machinery (final — after two bugs found and fixed BEFORE trusting any number)
- Bug 1: the root was handled as a non-root vertex, so its (necessarily zero) balance tv=0 was wrongly treated as invalid → the first harness reported everything false. Fix: the root is exempt from the branch value check; its balance is checked last and must be 0 by construction.
- Bug 2: the forced tree-edge sign ignored whether the child was the head or the tail of the tree edge → per-vertex signed balance wrong by one sign per tree edge. Fix: sign = +value if the child is the head, −value if it is the tail.
- **Final machinery:** (a) *eager Z_k-flow solver* — reverse-BFS spanning tree; chord edges branch on values 1..k−1 in Z_k; tree edges forced with the correct head/tail sign; root balance checked last; (b) *integer NZ k-flow solver* — same search shape, signed values ±1..±(k−1) with exact integer per-vertex balance; (c) *mod-3 orientation search* — no pruning, m ≤ 16 only.
- First validator also had a BFS-from-node-0 tree check bug (caught in 53c-style testing; the tree check now verifies parent structure, not BFS reachability from 0).

### F1 — named flow numbers (least k with a nowhere-zero k-flow)
K4→4, K5→**2** (all degrees even — surprising at first glance but verified: an Eulerian graph has an NZ 2-flow), K_3,3→3, octahedron→2, cube→3, triangular prism→4, wheelW5→4, C4→2, Petersen→**5** (NO NZ 4-flow — machine-proved by exhaustive search), icosahedron→3 (the eager Z_3 search needed β=19 branch nodes).

### F2 — witnesses (hand-checkable)
- **Petersen NZ 5-flow** (edge values in order: outer cycle edges i→(i+1)%5 for i=0..4, interleaved with spokes i→i+5 and inner star edges (i+5)→((i+2)%5)+5): [2,2,3,−1,3,2,1,−2,1,2,−1,1,4,−2,−1].
- **K4 NZ 4-flow** (edge order K4 vertices 0,1,2,3, edges 01,02,03,12,13,23): [3,−1,−2,2,1,1].

### F3 — equivalences
- **Tutte lift, Z_k-flow ⟺ integer NZ k-flow:** TRUE on all named graphs × k ∈ {3,4,5}.
- **mod-3 orientation ⟺ Z_3-flow:** TRUE on all named graphs with m ≤ 16.

### F4 — planar duality: flow number(G) = χ(G*) — ALL_OK on 7 embedded planar samples
K4 self-dual 4=4; C4 2=2; octahedron/cube dual pair 2=2; wheelW5 self-dual 4=4; prism/bipyramid dual pair 4=4; icosahedron/dodecahedron dual pair 3=3; stacked-6 (seed 20261012) 3=3. Euler n−m+f=2 verified on every embedding.

### F5 — censuses (flow number of every connected bridgeless graph)
- **n ≤ 5 full:** 264 connected bridgeless graphs; flow-number histogram **{2:42, 3:191, 4:31}; none ≥ 5.**
- **n = 6 FULL (all 32,768 labeled graphs, two 16,384-mask runs):** 4,624 + 7,344 = **11,968 bridgeless graphs**; histogram first half {2:320, 3:3762, 4:542}, second half {2:400, 3:6199, 4:745} → totals **{2:720, 3:9961, 4:1287}; ZERO need k = 5.**
- **Consequence (census-scoped, honest wording):** every 2-edge-connected graph on n ≤ 6 vertices has an NZ 5-flow (indeed an NZ 4-flow) — Tutte's 5-flow conjecture (1954, open) and the 4-flow case are machine-verified in census range only; Seymour's 6-flow theorem (1981) remains the proved general statement. The Petersen graph (n = 10) shows flow number 5 is attainable — outside the census range, as it must be.


### F6 — AUTHORING-TIME CORRECTION (recorded before any chapter prose quotes a witness)
- The F2 witness arrays as first recorded ([2,2,3,−1,3,2,1,−2,1,2,−1,1,4,−2,−1] for Petersen, [3,−1,−2,2,1,1] for K4) do NOT balance under their recorded edge-order glosses — the compacted run-summary garbled the edge order. DEAD as quotable witnesses; the numbers stay on record.
- Fresh re-derivation (independent solver, authoring chunk 53e), edge lists explicit, every vertex balance re-verified in-run:
  - **Petersen NZ 5-flow** — edge order: outer cycle 0→1, 1→2, 2→3, 3→4, 4→0; spokes 0→5, 1→6, 2→7, 3→8, 4→9; inner star 5→7, 6→8, 7→9, 8→5, 9→6 — values **[1, −1, 1, −1, 2, 1, 2, −2, 2, −3, 4, 1, 2, 3, −1]**.
  - **K4 NZ 4-flow** — edge order 01, 02, 03, 12, 13, 23 — values **[1, 1, −2, 2, −1, 3]**.
- The full named flow-number table was independently re-verified by the fresh solver at the same time: C4→2, K5→2, K4→4, K_3,3→3, octahedron→2, cube→3, triangular prism→4, wheel W5→4, Petersen→5, icosahedron→3 — ALL MATCH F1. (Duality pair, both directions: phi(octahedron) = 2 = chi(cube); phi(cube) = 3 = chi(octahedron); phi(prism) = 4 = chi(triangular bipyramid).)
- Standing lesson, added to the scars ledger: compacted witness arrays must be re-derived, never quoted from a session summary; the census-level numbers (tables, histograms) survived compaction intact — every one re-checked or consistent with the fresh solver.
