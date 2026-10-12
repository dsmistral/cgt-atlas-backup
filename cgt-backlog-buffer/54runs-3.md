## Session 54 machine runs — batch 3 (Chunk 54c-III: designs I — STS(7)/STS(9), the S(2,3,6) non-existence proof, Fisher census) — 2026-10-12

### D1 — STS(7): full labeled enumeration + uniqueness
- **Algorithm:** backtracking on the lowest uncovered pair (a,b), trying every c > b with both cross-pairs uncovered; leaves = exact covers of all C(7,2) = 21 pairs; every leaf validity-checked independently (each pair covered exactly once).
- **Results (byte-exact):** labeled STS(7) count = **30**; all 30 valid; b = 7 blocks; canonical forms over all 7! = 5040 relabelings (lex-min sorted block list): **1 distinct class** — the Fano plane is unique. Fisher census: b = 7 = v (Fisher TIGHT — b = v), r = 3 equal at every point.

### D2 — STS(9): full labeled enumeration + uniqueness
- **Algorithm:** same lowest-pair backtracking; propagation-based isomorphism test (assign point images; any block of A with two assigned points forces the third through B's pair→third map; contradiction → backtrack with an UNDO TRAIL; self-test passed: identity + a relabeled copy both accepted).
- **Results (byte-exact):** labeled STS(9) count = **840**; all valid; b = 12; all 840 isomorphic to the first (one orbit) — **STS(9) unique** (AG(2,3)). Fisher census: b = 12 > v = 9, r = 4 = (v−1)/2 equal at every point.

### D3 — S(2,3,6): the non-existence machine proof (the chapter's worked exhibit)
- **Algorithm:** exhaustive over ALL C(20,5) = 15,504 five-block subsets of the C(6,3) = 20 triples on 6 points (pruned subset recursion, each pruned branch verified to skip only pair-conflicting subsets); an exact cover = all 15 pairs covered exactly once.
- **Result:** exact covers found = **0** — S(2,3,6) does NOT exist (machine proof).
- **Divisibility record:** r = λ(v−1)/(k−1) = 5/2 = 2.5 non-integer (the obstruction); b = λ·C(6,2)/C(3,2) = 15/3 = 5 IS integer — b alone does not save it, r kills it. (λ = 1: any pair in exactly one block is forced λ = 1 here by k = 3, v = 6 counting.)

### D4 — Fisher inequality census (so far)
- STS(7): b = 7 = v (tight); STS(9): b = 12 > v = 9; both with r = (v−1)/2 consistent at every point. The STS(13) census (b = 26 > 13) lands with the batch-4 run.

All numbers above are byte-exact outputs of this run. Receipt for chunk 54c target (3), first part — designs I basics.
