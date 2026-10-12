## Session 52 machine runs — batch 2 (Part B: counting lemma empirical) — 2026-10-12 — v2

**v1 design correction (record):** the A-B regularity check enumerated ALL (X, Y) subset pairs of sizes >= 4 — ~1.5e9 pairs, killed by the process-safety deadline BEFORE any result. v2 checks a structured witness + 2,000 seeded random pairs — the right tool for an exhibit (bounded, reproducible). (Same lesson as 51d's "split per part".)

### B1 — the "lying densities" dichotomy exhibit (m = 16 per part, hi/lo split)
Construction: A-B edges iff hi(a) = hi(b); B-C iff hi(b) = hi(c); C-A iff hi(c) != hi(a). Pairwise edge counts 128/128/128 of 256 — all three densities = 1/2 — yet TRIANGLES = 0 (a triangle needs hi(a) = hi(b) = hi(c) and hi(c) != hi(a) — a contradiction). The A-B pair is maximally irregular: the structured witness (all-high X = {0,1,2,3} vs all-low Y = {8,9,10,11}) has d(X,Y) = 0/16 = 0.000 vs d = 1/2 — discrepancy 0.5000; max discrepancy over 2,000 seeded (X,Y) samples = 0.5000. Chapter exhibit: dense-but-irregular tripartite graphs can have ZERO triangles — regularity, not density, is what the counting lemma buys.

### B2 — uniform tripartite graphs (n = 30 per part; Lehmer seed 20261052): triangles vs the density product
Config 1 (target 0.5/0.5/0.5): realized 0.4911/0.4911/0.5044; triangles = 3,307; product prediction = 3,285; counting-lemma lower window ((d-0.1)^3 * n^3) = 1,670; observed = 100.7% of product (rel dev 0.67%); regularity spot-check max discrepancy per pair (100 seeded subsets, |X|,|Y| >= 6): 0.155 / 0.132 / 0.141 (empirical spot-check, honestly not a proof); observed ABOVE the lower window, as the counting lemma promises.
Config 2 (target 0.7/0.4/0.55): realized 0.7033/0.4011/0.5533; triangles = 4,202; product prediction = 4,215; counting-lemma lower window ((d-0.1)^3 * n^3) = 2,224; observed = 99.7% of product (rel dev 0.3%); regularity spot-check max discrepancy per pair (100 seeded subsets, |X|,|Y| >= 6): 0.119 / 0.127 / 0.127 (empirical spot-check, honestly not a proof); observed ABOVE the lower window, as the counting lemma promises.

All numbers computed in-run (TS); seed: Lehmer 20261052.
