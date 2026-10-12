## Session 54 machine runs — batch 1 (Chunk 54c-I: Pólya/Burnside censuses vs brute force) — 2026-10-12

### N1 — necklaces, 2 colors (brute orbit count vs Burnside)
- **Algorithm (both sides machine-run):** brute = for each of the 2^n binary strings, the canonical representative = the lex-min over all n rotations, collected in a Set; Burnside = (1/n)·Σ_{k=0..n−1} 2^gcd(n,k).
- **Result n = 1..12, brute = Burnside, all EQUAL:** 2, 3, 4, 6, 8, 14, 20, 36, 60, 108, 188, 352.

### N2 — the colored cube (24 face-rotations)
- **Group:** closure of the two quarter-turns r1 = (F L B R) fixing U,D and r2 = (U R D L) fixing F,B (face labels U,D,F,B,L,R = 0..5) under composition; machine-verified |G| = 24.
- **Cycle-type census on the 6 faces (machine):** 1⁶:1, 2²1²:3, 2³:6, 3²:8, 4·1²:6 — sum 24 ✓.
- **Brute orbit count of k-colorings (canonical coloring = lex-min image under all 24 perms) vs the cycle-index closed form (k⁶+3k⁴+12k³+8k²)/24, k = 1..5, all EQUAL:** 1, 10, 57, 240, 800.

### N3 — unlabeled tree shapes (pays Ch. 2's X1 seed)
- **Rooted shapes:** multiset generation (a rooted tree of size n = a sorted multiset of rooted trees of total size n−1; items enumerated in nondecreasing size+string order, so each multiset is generated exactly once). Counts n = 1..8: **1, 1, 2, 4, 9, 20, 48, 115** (A000081).
- **Unrooted shapes:** centroid/bicentroid generation — single centroid = a multiset of rooted trees of total size n−1 with every branch ≤ ⌊(n−1)/2⌋ (rooted at the centroid); bicentroid (n even) = an unordered pair of rooted trees each of size n/2 (the two constructions are disjoint: a tree has exactly 1 or 2 centroids). Counts n = 1..8: **1, 1, 1, 2, 3, 6, 11, 23** (A000055).
- **Independent cross-checks, ALL EQUAL:** (a) full Prüfer enumeration (every n^{n−2} sequence → labeled tree → AHU canonical form, min over the 1–2 centroid rootings) → distinct forms n = 1..8: 1, 1, 1, 2, 3, 6, 11, 23 — EQUAL to the generation counts; (b) rooted shapes from Prüfer trees rooted at every vertex, n = 1..6: 1, 1, 2, 4, 9, 20 — EQUAL to the multiset generation.

All numbers above are byte-exact outputs of this run. Receipt for chunk 54c target (1) — Burnside/Pólya censuses vs brute force.
