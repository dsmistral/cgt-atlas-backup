## Session 52 machine runs — batch 3 (Part C/D: the Roth reduction construction, exhaustive) — 2026-10-12

### The construction (verified form)
G(A) on parts Z_n (n odd): E12 = {(x, x+s): s in A}; E23 = {(x, x+s): s in A}; E31 = {(z, x): z - x = 2s, s in A}. Triangles (x, y, z): s1 = y-x in A, s2 = z-y in A, s1+s2 = 2s3 with s3 in A <=> mid = (s1+s2)/2 in A — i.e., every triangle is a 3-AP of A in disguise (genuine if s1 != s2, degenerate if s1 = s2).

### Exhaustive verification, ALL subsets A of Z_n, n = 5, 7, 9
- n = 5: all 32 subsets checked. **AP-free <=> every edge in exactly one triangle: 32/32 agree, 0 mismatches** (the equivalence is machine-exact); 16 AP-free sets; 16 sets with the unique-triangle property; max AP-free size = 2 (e.g. {0,1}); for EVERY AP-free A: #triangles = n*|A| exactly (only the degenerate triples survive) and #edges = 3n*|A| — both asserted, zero failures.
- n = 7: all 128 subsets checked. **AP-free <=> every edge in exactly one triangle: 128/128 agree, 0 mismatches** (the equivalence is machine-exact); 43 AP-free sets; 43 sets with the unique-triangle property; max AP-free size = 3 (e.g. {0,1,3}); for EVERY AP-free A: #triangles = n*|A| exactly (only the degenerate triples survive) and #edges = 3n*|A| — both asserted, zero failures.
- n = 9: all 512 subsets checked. **AP-free <=> every edge in exactly one triangle: 512/512 agree, 0 mismatches** (the equivalence is machine-exact); 127 AP-free sets; 127 sets with the unique-triangle property; max AP-free size = 4 (e.g. {0,1,3,4}); for EVERY AP-free A: #triangles = n*|A| exactly (only the degenerate triples survive) and #edges = 3n*|A| — both asserted, zero failures.

### The Roth deduction, machine-checked at n=5, all singleton A (v2 — corrected)
For every singleton A ⊂ Z_5 (5/5, all AP-free): edges 15, triangles 5, and the **brute-force minimum number of edge deletions killing all triangles = 5 = #triangles** (exhaustive over all 2^15 deletion subsets). This is forced by the machine-exact edge-disjointness (every edge in exactly one triangle): one deletion per triangle is necessary and sufficient. The contradiction skeleton: triangle removal promises o(n^2) deletions; the construction forces exactly n*|A| = delta*n^2 — Roth.

### v2 correction record (honest defect log — v2 authoritative)
The original deletion check computed ((z-x)*inv2)%5 with raw JS remainder: z < x yields a NEGATIVE difference and triangles were missed, so hasTri under-counted and the original reported minDeletion = 1 for n=5, A={2} — contradicting the machine-verified edge-disjointness, which forces 5. v2 re-runs the ENTIRE batch with fully normalized modular arithmetic (((z-x)+n)%n everywhere): the exhaustive equivalence results are unchanged and re-confirmed — AP-free ⟺ every edge in exactly one triangle with 0 mismatches over all 5/7/9 subsets (16/43/127 AP-free sets, 16/43/127 unique-triangle sets, max AP-free sizes 2/3/4, zero assertion failures on #triangles = n|A| and #edges = 3n|A|); the deletion minimum is 5 = #triangles for all five singletons (A = 0,1,2,3,4). v1's deletion number is dead; everything else stands re-confirmed.

### Reading for the chapter
The exhaustive equivalence (AP-free ⟺ unique-triangle) is the load-bearing machine check for L4's reduction; the n=9 max AP-free set (size 4) gives the honest small-scale exhibit of the density-vs-n trade-off.
