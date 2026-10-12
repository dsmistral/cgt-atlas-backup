## Session 53 machine runs — batch 5 (Chunk 53d-III: perfect graphs) — 2026-10-12

### PG0 — machinery + cross-check
- Perfection test: chi(G[S]) === omega(G[S]) on EVERY nonempty induced subgraph S. chi via the independent-set-partition DP over subsets (chi[mask] = 1 + min over nonempty independent submasks, submask enumeration 3^n); omega via branching memo (omega[mask] = max(omega[mask minus v], 1 + omega[N(v) & mask])); alpha via the twin branching on non-neighbors.
- Cross-check: 200 sampled n=6 graphs re-verified with an INDEPENDENT brute force (backtracking k-color search for chi, clique recursion for omega): **0 mismatches**; spot values empty 1/1, K6 6/6, C5-type witnesses 3/2.
- Harness bugs caught BEFORE any census number was trusted (same class as the 53d flow-solver bugs): (1) the first complement builder forgot to clear the self-bit → complement omega inflated → 1,086 fake WPGT violations; (2) the induced-C5 test compared the edge count to 10 (an ordered-pair relic) → C5 never detected. Both fixed; all numbers below are from the corrected machinery.

### PG1 — perfection census (full, all labeled graphs)
- n=1..4: ALL perfect (1 / 2 / 8 / 64 graphs).
- n=5: 1,024 graphs — 1,012 perfect, **12 imperfect** = exactly the 12 labeled C5's.
- n=6 FULL (32,768): **30,824 perfect, 1,944 imperfect** (halves 972 + 972).

### PG2 — SPGT in range (imperfect ⟺ induced C5)
- Every imperfect n<=6 graph contains an induced C5 (5 edges, all in-subset degrees 2): n=5 12/12, n=6 1,944/1,944 — **0 exceptions**; no perfect graph contains one (0). At n<=6 the SPGT prediction holds exactly: odd holes >= 7 and odd antiholes >= C7-bar need 7+ vertices, and C5-bar = C5.
- Witness (n=6, edge mask 684): edges 0-3, 0-4, 1-2, 1-4, 2-3 = C5 on {0,1,2,3,4} (cycle 0-3-2-1-4-0) plus isolated vertex 5; chi=3, omega=2.

### PG3 — WPGT census
- perfect(G) ⟺ perfect(complement G) on ALL 1,099 (n<=5) + 32,768 (n=6) graphs: **0 violations.**

### PG4 — Lovász characterization census
- perfect(G) ⟺ every induced subgraph H satisfies alpha(H)*omega(H) >= |V(H)|: **0 violations** on all n<=6 graphs, both directions (C5: 2*2 = 4 < 5 fails, C5 imperfect; the 12 C5's are the only n=5 failures, inside the 1,944 at n=6).

### PG5 — Lovász replication
- G.v (v replaced by adjacent twins, each with neighborhood N(v)) on ALL n<=4 graphs x every vertex = 285 replications: **every result perfect — 0 imperfect results** (the replication lemma verified in range).
- chi(G.v) always in [chi(G), chi(G)+1]: 0 upper, 0 lower violations.
- **HONEST CATCH: the tempting formula chi(G.v) = max(chi(G), d(v)+1) is FALSE** — 167/285 violations. Smallest witness: K2 (replicate either endpoint → triangle, chi = 3 vs max(2, 2) = 2). The P3 middle-vertex example (→ K4 minus edge, chi = 3 = max(2, 3)) satisfies it only coincidentally — there the twins plus the two neighbors happen to form a triangle. The replication lemma is about PERFECTION, not about chi; authoring must not state the formula.

### PG6 — minimal-imperfect units
- **C5:** chi=3, omega=2, alpha=2 (alpha*omega = 4 < 5); ALL proper induced subgraphs perfect → minimal imperfect. C5-bar ≅ C5 (isomorphism i → 2i mod 5 machine-verified) — hole = antihole at n=5.
- **C7:** chi=3, omega=2, alpha=3 (6 < 7); all proper induced subgraphs perfect.
- **C7-bar (the 7-antihole): NOT isomorphic to C7** — it is 4-regular (vs 2), chi=4 > omega=3 (imperfect), alpha=2 (alpha*omega = 6 < 7), all proper induced subgraphs perfect → minimal imperfect. HONEST CATCH vs the working note "C7-bar ≅ C7": FALSE — C_n-bar ≅ C_n holds ONLY at n=5 (n−3 ≠ 2 once n >= 6).
- **P3 unit:** replicating the middle vertex gives K4 minus edge (adjacency machine-verified edge by edge), chi=3, perfect.

All numbers computed in-run (TS); no prior receipt reused. Census covers every labeled graph on n <= 6 vertices.
