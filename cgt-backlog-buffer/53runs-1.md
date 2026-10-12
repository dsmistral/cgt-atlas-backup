## Session 53 machine runs — batch 1 (Chunk 53c-I: exact treewidth + graph minors) — 2026-10-12

### B1 — exact treewidth (elimination-game DP with fill)
- **Algorithm** (pure TS, bitmask adjacency): f(S) = min over v ∉ S of max(cost(S,v), f(S∪{v})), base f(V) = 0, subsets iterated descending; cost(S,v) = |adjUnion(component of v in G[S∪{v}]) ∖ (S∪{v})| — the eliminated degree in the fill graph (the remaining vertices reachable from v through already-eliminated vertices); answer tw(G) = f(∅). The component term IS the fill: an earlier attempt without it computed degeneracy-like values and is DEAD.
- **Battery (16 graphs, ALL MATCH the canon):** K3→2, C5→2, C7→2, K4→3, K5→4, K3,3→3, Petersen→4, P6→1, subdivK4→3, octahedron→4, wheelW5→3, K2,3→2, icosahedron→6, grid2x2→2, grid3x3→3, grid4x4→4. In particular tw(k×k grid) = k machine-confirmed for k = 2, 3, 4.
- Degeneracies recorded alongside (all ≤ tw ✓): subdivK4→2, icosahedron→5, Petersen→3, grid3x3→2, grid4x4→2.

### B2 — the branch-set minor oracle (replacing the defective contraction oracle)
- The pre-53c contraction-minor oracle produced FALSE NEGATIVES (its Petersen K5 search returned false while a hand-verifiable witness exists) — DEAD. **Replacement: direct model search** — K_k minor ⟺ k pairwise-disjoint nonempty connected vertex subsets, pairwise adjacent; canonical enumeration by strictly increasing branch-set minima; DFS with adjacency pruning.
- **Unit battery (ALL PASS):** K5→K5 ✓, K4→K4 ✓, Petersen→K5 ✓, Petersen→K6 ✗ ✓ (tw 4 < 5 forbids it), subdivK4→K4 ✓, C5→K4 ✗ ✓, C5→K3 ✓, W5→K4 ✓, K2→K3 ✗ ✓.
- **K3,3 → K4 = TRUE** — the census falsified the draft claim "bipartite ⟹ K4-minor-free" (edge contraction does NOT preserve bipartiteness). Witness branch sets {a1},{a2},{a3},{b1,b2,b3}.
- **Witnesses (hand-verified vertex by vertex):** Petersen K5: {0,1},{2,3},{4,9},{5,7},{6,8} (all 10 pairs adjacent, each branch set connected); grid3x3 K4: {0,1},{2,5},{3,6,7,8},{4}.

### B3 — censuses (all labeled graphs)
- **n≤5 (1,099 graphs):** Hadwiger k=3 (χ≥3 ⟹ K3 minor): **0 violations**; Hadwiger k=4 (χ≥4 ⟹ K4 minor): **0 violations** (67 χ≥4 graphs, all with K4 minor); tw≥3 ⟺ K4-minor: **0 violations both directions** (112 graphs with a K4 minor); degeneracy ≤ tw: **0**; tw≤1 ⟺ forest: **0**; K4-minor-free ⟹ 2-degenerate: **0**.
- **Oracle lesson (honest catch):** the biconditional "K3-minor ⟺ non-bipartite" is FALSE — 88 bipartite graphs n≤5 carry a K3 minor (K2,3-type; contraction creates odd cycles). The correct biconditional is K3-minor ⟺ non-forest, **0 violations**.
- tw distribution (tw0/1/2/3/4): n=3: 1/6/1/–/–; n=4: 1/37/25/1/–; n=5: 1/290/622/110/1.
- **n=6 FULL (all 32,768 labeled graphs):** χ≥4 count **5,214** (matches the pre-53c record); **all 5,214 have a K4 minor — 0 violations.** Side count: 27,591 non-bipartite.
- **n=6 seeded sample (2,000 graphs):** tw≥3⟺K4, deg≤tw, tw≤1⟺forest, K4-free⟹2-deg: **0 violations each**; 642 with K4 minor; tw histogram (tw 0–4) = 0/214/1143/618/24. **GOTCHA:** the LCG's lowest bit alternates deterministically — the first sample was degenerate (alternating edge pattern, zero K4 minors, uniform near-bipartite structure); the high-bit sampler is the fix.
- **subdivK4 machine record:** degeneracy 2, K4 minor present, tw 3 — "2-degenerate ⟹ K4-minor-free" is FALSE; the correct chain is tw≤2 ⟺ K4-minor-free ⟹ 2-degenerate ⟹ 3-colorable.

All numbers computed in-run (TS); no prior receipt reused. Seeds: LCG 20261012 (n=6 sample; high-bit sampler).
