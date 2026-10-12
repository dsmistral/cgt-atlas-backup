## Session 52 machine runs — batch 4 (Part E: the cap set machinery) — 2026-10-12

### E1. The Ellenberg–Gijswijt constant — exact minimizer + independent numeric check
Minimize f(x) = (1+x+x^2)/x^(2/3) on (0,1). The derivative condition reduces to 4x^2 + x - 2 = 0 (residual 0 at machine precision), so the minimizer is the closed form x* = (sqrt(33)-1)/8 = 0.593070330817 (sqrt(33) = 5.744562646538). The constant c = f(x*) = **2.755104613024**. Independently re-derived by dense scan (grid 1e-5 over (0,1)) + 200 golden-section refinements: the numeric minimizer 0.593070332624 agrees with x* to 1.8e-9 and f at both agrees to all 12 printed decimals (2.755104613024). The cap-set base constant for the chapter is c = 2.7551046130 (the literature's "2.756" is this value rounded).

### E2. EG monomial counts M(n, floor(2n/3)) — exact integers, DP over variables
Number of monomials in n variables with every exponent <= 2 and total degree <= floor(2n/3); slice-rank bound |A| <= 3*M:
- n=1: d=0, M=1, 3M=3 (true r_3(F_3^1) = 2)
- n=2: d=1, M=3, 3M=9 (true 4)
- n=3: d=2, M=10, 3M=30 (true 9)
- n=4: d=2, M=15, 3M=45 (true 20)
- n=5: d=3, M=51, 3M=153 (true 45)
- n=6: d=4, M=168, 3M=504
- n=7: d=4, M=274, 3M=822
- n=8: d=5, M=927, 3M=2781
The bound is honest but slack at small n — it is an asymptotic weapon; the chapter says so explicitly (the 2.7551^n decay only bites for large n).

### E3. Caps in F_3^n: verified maxima and exhibits
- n=1: exhaustive over all 8 subsets — max cap 2 (e.g. {0,1}).
- n=2: exhaustive over all 512 subsets — max cap 4 (e.g. the four points of {0,1}^2; 73 cap subsets in total across all sizes).
- n=3: EXACT — DFS over the 27 points, include/exclude with bound pruning, FULL tree explored (647,644 nodes, no abort): **max cap = 9**. Exhibit [(0,0,0) (1,0,0) (0,1,0) (1,1,0) (0,0,1) (1,0,1) (2,1,1) (2,2,1) (2,1,2)] — pairwise-verified (no distinct x,y in the set with -x-y also in the set).
- n=4: a **20-cap found and pairwise-verified** (seeded greedy, Lehmer seed 20261053, 2000 random-order restarts; exhibit below). OPTIMALITY NOT MACHINE-PROVED IN BUDGET — the DFS optimality attempt blew the process deadline (honest flag; r_3(F_3^4) = 20 is the known computational result, cited in the chapter as literature, not as a machine receipt).
- n=5: a **45-cap found and pairwise-verified** (iterated local search, Lehmer seed 20261055: plateau-accepting kicks k in 2..7, 80,000 iterations after 5000 greedy restarts; exhibit below). Search-difficulty note, recorded honestly: plain kick search (seed 20261054, 60,000 iterations, non-plateau) stalled at 39; the plateau-accepting variant reached 45, matching the literature r_3(F_3^5) = 45 (cited; optimality not machine-proved).

n=4 exhibit (20 points): [(1,0,1,2) (2,2,0,2) (1,0,2,0) (2,0,1,2) (2,2,1,1) (2,1,0,1) (1,1,2,2) (0,2,1,0) (2,0,1,1) (0,2,2,1) (2,2,1,0) (2,1,0,2) (0,1,0,1) (0,0,2,1) (0,1,2,0) (1,2,2,2) (1,1,2,0) (0,0,2,0) (1,2,0,0) (2,2,0,0)]

n=5 exhibit (45 points): [(0,2,2,0,2) (1,2,1,1,1) (0,2,1,1,0) (2,0,2,1,1) (0,0,2,0,2) (2,0,2,2,0) (2,1,0,1,2) (2,2,2,2,2) (1,0,0,0,1) (1,1,0,1,1) (1,1,2,0,2) (2,2,2,1,1) (1,0,1,2,0) (2,2,2,0,1) (2,1,1,0,2) (0,1,1,0,0) (1,0,2,2,2) (1,1,1,2,1) (1,2,1,2,0) (1,0,2,0,0) (0,2,1,2,0) (2,1,1,1,1) (1,2,2,2,1) (2,2,0,2,1) (0,1,1,1,1) (1,2,1,0,1) (2,0,0,2,2) (0,1,2,1,2) (1,1,2,2,2) (0,0,0,1,2) (2,1,1,2,1) (0,0,2,1,1) (1,0,0,1,2) (0,1,0,2,2) (0,1,0,0,1) (2,2,0,1,2) (1,2,0,0,0) (2,0,1,1,2) (0,0,0,2,2) (2,1,0,2,2) (0,2,1,0,1) (0,2,2,1,2) (2,0,1,0,1) (0,0,0,0,0) (1,1,0,0,1)]

### Reading for the chapter
c = 2.7551046130 with its closed-form minimizer anchors L6; the exact n=3 DFS (rung 9 machine-proved) plus the verified n=4/n=5 exhibits (20/45, literature-confirmed) give the honest finite ladder; the 3*M table shows the slice-rank bound's asymptotic (not exact) character at small n.
