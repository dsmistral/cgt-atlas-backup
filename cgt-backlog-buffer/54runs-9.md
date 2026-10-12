## Session 54 machine runs — batch 9 (Chunk 54d-I: bracelets + PG(2,3) + Bruck–Ryser census) — 2026-10-12

### K1 — bracelets, 2 colors (brute dihedral orbits vs Burnside over D_n)
- **Algorithm (both sides machine-run):** brute = canonical representative of each 2^n string under all n rotations AND n reflections (dihedral), collected in a Set; Burnside = (1/2n)·(Σ_{k=0..n−1} 2^gcd(n,k) + reflections), reflections fixing 2^((n+1)/2) each for n odd, and split 2^(n/2+1) / 2^(n/2) each for n even.
- **Result n = 1..12, brute = Burnside, all EQUAL:** 2, 3, 4, 6, 8, 13, 18, 30, 46, 78, 126, 224.
- **Necklace-vs-bracelet contrast (machine):** n = 6: necklace 14 vs bracelet 13; n = 12: necklace 352 vs bracelet 224. The necklace Burnside side re-printed 2, 3, 4, 6, 8, 14, 20, 36, 60, 108, 188, 352 — identical to the 54runs-1 record.
- **Verification note:** this batch's numbers were re-confirmed byte-exact in a post-compaction verification pass (same values on both sides, all EQUAL).

### K2 — PG(2,3): the projective plane of order 3 as S(2,4,13)
- **Construction:** points = the 13 nonzero vectors of F₃³ modulo scaling (representatives canonically chosen); **machine count = 13 points**.
- **Collinearity oracle:** 4 distinct projective points are collinear iff their representative vectors have F₃-rank exactly 2 (Gaussian elimination over F₃; 13 lines found, each of exactly 4 points).
- **Pair coverage:** all C(13,2) = 78 pairs lie in EXACTLY ONE line — machine-verified. So the 13 lines form an S(2,4,13): **b = 13 = v**, Fisher's inequality b ≥ v TIGHT at the equality case.
- **GOTCHA (recorded, caught by the run itself):** the first two collinearity tests were WRONG — (a) det(b−a, c−a, d−a) ≡ 0 (mod 3) is necessary but not sufficient (211 raw 4-sets, pair-coverage 78 with multiplicities ≠ 1); (b) affine proportionality of differences is meaningless for projective points because representatives are only defined up to scaling (0 lines found). The rank-2 test is the correct one.

### K3 — Bruck–Ryser–Chowla census, q = 2..16 (machine a²+b² table)
- **Theorem applied:** if a projective plane of order q ≡ 1 or 2 (mod 4) exists, then q is a sum of two squares (Bruck–Ryser 1949 / Chowla–Ryser 1950); for q ≡ 0 or 3 (mod 4) the theorem is silent.
- **Machine census (sum-of-two-squares over all a,b):** q = 6 and q = 14 are ≡ 2 (mod 4) and NOT sums of two squares → **RULED OUT**; q = 10 ≡ 2 (mod 4) but 10 = 1² + 3² → BRC SILENT (ruled out only by Lam–Swiercz–Hoffman 1989, the coding-theory + search proof); q = 12 ≡ 0 (mod 4) → outside BRC (the smallest open order); q = 2 = 1²+1², q = 5 = 1²+2², q = 9 = 0²+3², q = 13 = 2²+3² pass; q = 3, 7, 11, 15 (≡ 3 mod 4) and q = 4, 8, 12, 16 (≡ 0 mod 4) silent.

All numbers above are byte-exact outputs of these runs. Receipt for chunk 54d targets (bracelets; PG(2,3)/Fisher equality; Bruck–Ryser arithmetic).
