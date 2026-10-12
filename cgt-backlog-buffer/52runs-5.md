## Session 52 machine runs — batch 5 (Part F: Erdos–Stone + stability, exhaustive; Part G: the tower honesty exhibit) — 2026-10-12

### F1. Exhaustive extremal numbers — all labeled graphs, no heuristics
- **ex(5, K4) = 8**: all 1024 labeled graphs on 5 vertices enumerated. The 15 extremal labeled graphs are EXACTLY the complete 3-partite T_3(5) with parts 2,2,1 (partition-wise machine check).
- **ex(6, K3) = 9**: all 32768 labeled graphs on 6 vertices. The 10 extremal labeled graphs are EXACTLY K_{3,3} (complete bipartite 3+3; checked over all 3+3 bipartitions).
- **ex(6, K4) = 12**: same enumeration. The 15 extremal labeled graphs are EXACTLY K_{2,2,2} (complete 3-partite, parts 2,2,2).
Turan equality at n = 5, 6 is machine-exact: extremal graphs are precisely the Turan graphs — structure AND labeled count (15 / 10 / 15).

### F2. The stability exhibit (Simonovits), 6 vertices, one edge below extremal
- There are **240 labeled 11-edge K4-free graphs** on 6 vertices. EVERY ONE is already 3-partite: minimum edge deletions to become 3-partite = 0 for all 240 (min over all 90 partitions of 6 vertices into 3 nonempty blocks). One below extremal at n = 6, the deletion distance to the 3-partite class has collapsed to zero — stronger than the stability theorem promises.
- Finer distance to THE Turan graph (min symmetric-difference edit distance over the 15 labeled K_{2,2,2}): **min 1, max 3, mean 1.5** — and exactly two structural types: 180 labeled graphs at distance 1 (= K_{2,2,2} minus one edge: 15 x 12 = 180) and 60 at distance 3 (= K_{3,2,1}: 6!/(3!2!1!) = 60 labeled copies). One edge below extremal, the K4-free world is precisely the Turan neighborhood — the small-scale Simonovits tableau.

### G. The tower honesty exhibit
The refinement iteration k -> k*2^k (the shape of the regularity blow-up) from k0 = 2, log10 tracked in floats: height 1: k = 8 (log10 0.9031); height 2: k = 2048 (log10 3.3113); height 3: k = 2048*2^2048, log10 = 619.8208; height 4: the recurrence l' = l + 10^l * log10(2) overflows float64 (a 10^(10^619.8)-scale number). The iteration passes the atoms-in-the-universe scale (10^80) AND a googol (10^100) both at height 3. A true tower of 2's of height 5 is 2^65536 = 10^19728.3 (arithmetic: 65536 * log10 2).
The bound arithmetic at sample epsilons (upper = the regularity-proof tower height of order eps^(-5); lower = Gowers' Omega(eps^(-1/16)); exact statements quoted from the 52b canon at authoring):
- eps = 0.1: upper height 100,000; lower 10^(1/16) = 1.1548
- eps = 0.05: upper height 3,200,000; lower 20^(1/16) = 1.2059
- eps = 0.01: upper height 10,000,000,000; lower 100^(1/16) = 1.3335
The honesty lesson for the chapter: at eps = 0.01 the regularity proof's tower has ten billion levels while the lower bound only certifies that no proof can do materially better than height ~1.33 — the Moshkovitz–Shapira tight form (52b canon) pins where the truth actually lies.

### Reading for the chapter
F1/F2 feed L3 (Erdos–Stone + stability: machine-exact Turan equalities at n = 5, 6 and the 240-graph tableau as the stability exhibit); G feeds L1/L5 (the tower discussion: the iteration exhibit + the honest upper/lower gap table).
