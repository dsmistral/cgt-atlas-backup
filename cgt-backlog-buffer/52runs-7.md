## Session 52 machine runs — batch 7 (52e authoring-time certification, per the Ch. 14 batch-8 precedent) — 2026-10-12

Purpose: certify every authoring-time numeric claim in the scratch chunks + the lab's port engines BEFORE c6b is written. All numbers computed in-run (TS); seeds recorded per part.

### C0 — the 4x4 epsilon-regularity census, port re-run (Lab Part 1's engine)
Independent re-implementation (Gray-code incremental subset-pair counts, integer-exact comparisons): at eps = 1/4 (test sets >= 1, 225 pairs/graph): **2 of 65,536** regular — masks 0 and 65,535 (the empty and complete pair; certifies Answer 1(c)); at eps = 1/2 (>= 2, 121 pairs): **46,408**; at eps = 3/4 (>= 3, 25 pairs): **65,536**; max witness discrepancy at eps = 1/4: **0.9375**. All four numbers = 52runs-1 A1 exactly.
**Port scar (recorded):** the first re-implementation iterated plain integers instead of the Gray-code masks g(i) = i ^ (i>>1) — an instant nonsense flag (max discrepancy 32767); fixed before any output was trusted. The gate catches ports too.

### C1 — the ex(6, C5) authoring-time catch, re-certified (Lecture 3)
Exhaustive over all 32,768 labeled graphs on 6 vertices (C5 detected via the 12 canonical 5-cycles on each 5-subset): **ex(6, C5) = 9, with 85 labeled extremal graphs** — confirms the c3 census that killed the recall guess "12". Also certified: the labeled K2,2,2 (12 edges) hosts the 5-cycle **0-2-4-1-3-0** (all five edges cross-part) — the exact witness c3 prints; K2,2,2 is tripartite, not bipartite, and the recall candidate is dead.

### C2 — stability at 11 edges re-confirmed + the 10-edge census (Lecture 3's Checkpoint promise)
11 edges (one below extremal): **240 labeled K4-free graphs, every one already 3-partite** (min deletions 0 over all 90 3-block partitions); edit distance to the nearest labeled K2,2,2: **180 at 1 + 60 at 3, mean 1.5** — all four numbers = 52runs-5 F2 exactly.
10 edges (two below extremal) — the promised surprise: **1,437 labeled K4-free graphs; 1,365 are 3-partite but 72 are NOT** (minimum deletions to 3-partite = 1). Edit distance to the nearest labeled K2,2,2: 945 at 2 (= K2,2,2 minus two edges), 492 at 4, mean 2.68; all 72 exotics sit at edit distance 4. A concrete exotic: the **wheel W5** (hub + 5-rim, 10 edges) — K4-free, NOT 3-partite (deletion distance 1, edit distance 4). Structure decays fast: one edge below extremal the whole universe is the Turan neighborhood; two below, 5% of it has left.

### C3 — the seeded 8x8 regularity sampler (Lab Part 1's second half)
Lehmer seed 20261056; 100 graphs; cells drawn (a, b)-lexicographic; edge iff the draw is even. At eps = 1/4 (test sets >= 2): **0 of 100 epsilon-regular**, max witness discrepancy 0.671875. At eps = 1/2 (>= 4): **100 of 100 epsilon-regular**, max discrepancy 0.484375. The tolerance, not the graph, decides — the lecture's vacuity lesson at sampler scale.

### C4 — cap exhibits re-verified + the n = 1, 2 exhaustive re-confirm (Lecture 6 / Lab Part 5)
The three receipt exhibits re-verified pairwise (no distinct x, y with -x-y in the set): the 9-cap in F_3^3, the 20-cap in F_3^4 (seed 20261053 exhibit), the 45-cap in F_3^5 (seed 20261055 exhibit) — all genuine caps. Exhaustive: max cap in F_3^1 = **2** (8 subsets); in F_3^2 = **4** (512 subsets; e.g. {0,1}^2).
**Honest bookkeeping correction:** the total number of cap subsets of F_3^2 is **172** (1 empty + 9 singletons + 36 pairs + 72 triples + 54 four-caps); maximal caps = 54 (all of size 4). 52runs-4's parenthetical "73 cap subsets in total across all sizes" is **not reproducible — dead as a count** (neither the total (172) nor the maximal count (54) matches; provenance unknown). The load-bearing maximum 4 stands re-confirmed. No chapter text quotes 73.

### C5 — the tower arithmetic re-print (Lecture 1 / Lab Part 6)
k -> k*2^k from k0 = 2: height 1: 8 (log10 0.903090); height 2: 2048 (log10 3.311330); height 3: log10 **619.820761**; height 4: float64 **overflow**. A true tower of 2's of height 5: 2^65536 = 10^19728.3018. eps-table (0.1 / 0.05 / 0.01): upper heights eps^-5 = 100,000 / 3,200,000 / 10^10 vs Gowers lower (1/eps)^(1/16) = 1.1548 / 1.2059 / 1.3335. All = 52runs-5 G.

### C6 — the variance identity re-confirm (Lecture 1's "defects pay rent" / Lab Part 2's side-run)
Independent re-implementation: 5,000 seeded 4x4 graphs (Lehmer seed 20261012, cells lexicographic, edge iff the draw is even) x all 225 nonempty witness pairs (X, Y): **1,125,000 checks, 0 violations** of either the identity increment = sum p_b (d_b - d)^2 or the inequality increment >= p_XY (d_XY - d)^2. = 52runs-1 A1.

### C7 — the Lab Part 3 port sample (new, seed 20261057)
The exact TS port of the printed Lab Part 3 Python (draw rule recorded in full: one Lehmer draw per cell, (a, b)-lexicographic within each pair, pairs (0,1),(1,2),(2,0) in order, edge iff (x mod 10^6)/10^6 < t): config 1 (targets 0.5/0.5/0.5): realized 0.4911/0.4911/0.4867, **3,176 triangles vs product 3,169 (100.2%)**, window 1,597 — above it, as the lemma promises; config 2 (0.7/0.4/0.55): realized 0.7033/0.3889/0.5456, **4,011 vs 4,029 (99.6%)**, window 2,097 — above it. The hi/lo exhibit re-print: pair counts 128/128/128 (all densities 1/2), **0 triangles**, witness discrepancy **0.5000** — = 52runs-2 B1 exactly.
The Lecture 2 rows (52runs-2 B2, seed 20261052: 3,307 vs 3,285, window 1,670; 4,202 vs 4,215, window 2,224) remain the lecture's recorded sample; B2's receipt did NOT record its per-cell draw rule, so the lab prints this port's rows (fully documented rule) rather than claiming unverified bit-reproduction. **Receipt-hygiene lesson (standing): ALWAYS record the draw rule with the seed.**

Seeds: 20261012 (C6), 20261056 (C3), 20261057 (C7). All numbers computed in-run (TS); no prior receipt number reused as output.
