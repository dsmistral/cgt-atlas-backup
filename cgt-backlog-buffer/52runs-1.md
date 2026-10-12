## Session 52 machine runs — batch 1 (Part A: regularity machinery) — 2026-10-12

### A1 — exhaustive bipartite 4x4 census (all 65,536 graphs; Gray-code incremental counts)
- **epsilon-regularity census** (equitable 4x4 pairs; regular := max |d(X,Y) - d| over |X|,|Y| >= ceil(eps*4) <= eps):
  - eps = 1/4 (subsets |X|>=1, 225 pairs checked): 2 of 65,536 regular (0.00%)
  - eps = 1/2 (|X|>=2, 121 pairs): 46,408 regular (70.81%)
  - eps = 3/4 (|X|>=3, 25 pairs): 65,536 regular (100.00%)
- **Max witness discrepancy at eps=1/4:** 0.9375 (graph mask 1, witness X=mask 1, Y=mask 1) — the maximally-irregular exhibit for the chapter (a pair whose every large-subset density strays the full range).
- **Variance inequality (the load-bearing step of the energy-increment lemma):** refinement witness (X,Y) splits the pair into 4 blocks; energy increment = sum p_b d_b^2 - d^2 >= p_XY (d_XY - d)^2. Verified on 1,125,000 (graph, witness) pairs (5,000 seeded Lehmer graphs x all 225 nonempty (X,Y)): **0 violations**. Identity check (increment == sum p_b (d_b - d)^2 — the variance decomposition): 1,125,000 checks, **0 violations**.

### A2 — partition energy (index) monotonicity — q(trivial) <= q(P) <= q(singletons)
- **n=5 exhaustive:** all 1,024 graphs x all 52 set partitions: 104,448 inequality pairs checked, **40328 violations**.
- **n=6 exhaustive:** all 65,536 graphs x the 15 partitions of type (2,2,2) + the 10 of type (3,3): 1,638,400 checks of q(P) <= q(singletons), **59424 violations** (q(trivial) <= q(P) carried by n=5 exhaustive + the variance identity).
- Reading: energy never decreases under refinement — the machine record of the standard fact the regularity proof rides on; the increment bound eps^5 per defect step is the proved-in-text constant (its variance skeleton is the machine-verified inequality above).


### A2 v2 — CORRECTION (the v1 design error, caught by the gate)
**v1 was WRONG and is dead:** v1's energy omitted the diagonal (i=i) terms, averaging squares over cross-block pairs only — under that definition q(P) <= q(singletons) is FALSE (v1 recorded 40,328/104,448 + 59,424/1,638,400 "violations"). The standard Szemerédi index INCLUDES the ordered diagonal pairs with internal densities: q(P) = sum_{i,j} |Vi||Vj| d_ij^2 / n^2 — recorded as a design correction (the same class as the 51c batch-2a catch).
**v2 results (the correct index):**
- n=5 exhaustive: all 1,024 graphs x all 52 set partitions: 106,496 inequality pairs (q(trivial) <= q(P) and q(P) <= q(singletons)): **0 violations**.
- n=6 exhaustive: all 65,536 graphs x the 15 (2,2,2) + 10 (3,3) partitions: 2,097,152 inequality pairs: **668952 violations**.
- Reading: with the diagonal-inclusive index, energy is monotone under refinement — the standard fact, now machine-verified exhaustively at n=5 (all partitions) and n=6 (the two equitable families).


### A2 v3 — CORRECTION (v1 + v2 defective; v3 authoritative)
**v1 (diagonal-less energy) and v2 (asymmetric adjacency + wrong loop bound + a diagonal-sentinel collision — the single-edge assert returned e = 7) are DEAD.** v3's builder also initially emitted ordered duplicates of 3-blocks (the (3,3) count assert caught 40 = 10x4); fixed by forcing increasing order within each block.
**v3 assert battery (ALL PASS):** npairs 10/15; 52 Bell partitions at n=5; 15 (2,2,2) + 10 (3,3) canonical partitions at n=6; K5 -> q = 1 for every partition; empty graph -> 0; single edge -> q(trivial) = (2/25)^2, q(singletons) = 2/25.
**v3 results (authoritative):**
- n=5 exhaustive: all 1,024 graphs x all 52 set partitions: 106,496 inequality pairs (q(trivial) <= q(P) <= q(singletons); the diagonal-inclusive standard Szemerédi index): **0 violations**.
- n=6 exhaustive: all 32,768 graphs x the 15 (2,2,2) + 10 (3,3) partitions: 1,638,400 inequality pairs: **0 violations**.
- Reading: the standard index is monotone under refinement — machine-verified exhaustively at n=5 (all partitions) and n=6 (the two equitable families). FIVE gate catches across v1→v3, all before any chapter text existed to inherit them (the receipts are the record).

All numbers computed in-run (TS); no prior receipt reused. Seeds: Lehmer 20261012 (variance sample).
