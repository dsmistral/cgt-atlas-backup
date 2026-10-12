## Session 52 machine runs — batch 6 (52d: machine runs II — the Ruzsa–Szemerédi censuses) — 2026-10-12

### R1. The (6,3) census on 6 vertices — graphs where EVERY edge lies in exactly one triangle
Exhaustive over all 32,768 labeled graphs on 6 vertices: **max edges = 6**, with **100 labeled graphs at the max** (90 bowties — two triangles sharing one vertex, e.g. edges 01, 02, 03, 04, 14, 23 with triangles {0,1,4} and {0,2,3} — plus 10 disjoint triangle pairs) and **121 labeled graphs with the property in total** (20 single triangles + 90 + 10 + the empty graph, which counts vacuously). The unique-triangle structure already caps a 6-vertex graph at n = 6 edges — the small-scale echo of the (6,3)-problem's rigidity (compare the Roth construction G(A): n|A| edges on 3n vertices, every edge in exactly one triangle).

### R2. The bipartite induced-matching partition census (the RS matching formulation)
For m+m bipartite graphs: the maximum number of edges of a graph whose edge set partitions into induced matchings each of size ≥ k — exhaustive over ALL labeled graphs, exact partition search (blocks enumerated around the lowest remaining edge, per-graph memoization):
- m = 3: k ≥ 2 → **max 6 edges (= m² − m)**; the 6 labeled extremals are EXACTLY the complements of the perfect matchings, blocks = the transposition pairs {(i,j),(j,i)}. k ≥ 3 → **max 3 edges** (the 6 induced perfect matchings themselves).
- m = 4: k ≥ 2 → **max 12 edges (= m² − m)**; the 24 labeled extremals are EXACTLY the complements of the 24 perfect matchings. k ≥ 3 → **max 4 edges**; k ≥ 4 → **max 4 edges** (the induced perfect matchings; no 5- or 6-edge partition exists — exhaustively confirmed).
The honest RS lesson at brute-force scale: partitioning into induced matchings of size ≥ 2 (a constant) still permits the full n² − n (complement-of-a-matching extremals); demanding matchings of size ≥ 3n/4 collapses the maximum to n. The δn matching-size hypothesis of the Ruzsa–Szemerédi theorem is exactly what separates the two regimes.

### Honest defect log (v3 authoritative)
v1 checked each block's cross-pairs against the REMAINING edge set rather than the ORIGINAL graph (cross-pairs belonging to earlier blocks could in principle be missed) — v2 fixed the check; in this census the two agreed on maxima and counts happened to match, but v2's logic is the sound one. v1/v2's labeled COUNTS were double-counted: a redundant second counting pass re-counted masks already counted in the first pass (reported 11/11/47/47/47). v3 removed the redundant pass: **6/6/24/24/24** — each exactly m!, the perfect-matching count, as the structural analysis predicts. Max-edge values were correct throughout. v3 is authoritative; v1/v2 counts are dead.

### Reading for the chapter
R1 + the 52runs-3 unique-triangle equivalence give L2/L4 the (6,3)-problem's small-scale skeleton; R2 gives L2 the induced-matching formulation with the honest size-threshold tableau.
