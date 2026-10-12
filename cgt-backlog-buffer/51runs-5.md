# 51runs-5.md — session 51, batch 5: discrepancy optima exhibit (machine receipts)

Seeds: Lehmer LCG x <- 48271x mod (2^31-1), seed 20261020+inst. Exact optimum by Gray-code exhaustive search over all 2^n colorings (n ≤ 16); random baseline = 10,000 uniform colorings per instance; entries ±1; m = n.

n | instance | exact opt disc | best of 10,000 random | mean random disc | Spencer 6√n
4 | #1 | 2 | 2 | 3.01 | 12.00
4 | #2 | 2 | 2 | 3.00 | 12.00
4 | #3 | 2 | 2 | 2.76 | 12.00
4 | #4 | 0 | 0 | 1.99 | 12.00
4 | #5 | 2 | 2 | 2.98 | 12.00
8 | #1 | 2 | 2 | 4.93 | 16.97
8 | #2 | 2 | 2 | 4.92 | 16.97
8 | #3 | 2 | 2 | 4.75 | 16.97
8 | #4 | 2 | 2 | 4.92 | 16.97
8 | #5 | 2 | 2 | 4.91 | 16.97
12 | #1 | 2 | 2 | 6.53 | 20.78
12 | #2 | 2 | 2 | 6.65 | 20.78
12 | #3 | 2 | 2 | 6.66 | 20.78
12 | #4 | 2 | 2 | 6.60 | 20.78
12 | #5 | 2 | 2 | 6.62 | 20.78
16 | #1 | 2 | 4 | 8.17 | 24.00
16 | #2 | 2 | 2 | 8.03 | 24.00
16 | #3 | 2 | 4 | 8.07 | 24.00
16 | #4 | 4 | 4 | 8.09 | 24.00
16 | #5 | 2 | 2 | 8.17 | 24.00

n=4: opt range 0–2 (5 seeded instances), Spencer 6√n = 12.00, √n = 2.00
n=8: opt range 2–2 (5 seeded instances), Spencer 6√n = 16.97, √n = 2.83
n=12: opt range 2–2 (5 seeded instances), Spencer 6√n = 20.78, √n = 3.46
n=16: opt range 2–4 (5 seeded instances), Spencer 6√n = 24.00, √n = 4.00

Hadamard cross-check (independent Gray-code re-verification of batch-1 exact values):
Sylvester-4 | 2 | (batch-1 exact: 2) | √n = 2.00
Sylvester-8 | 4 | (batch-1 exact: 4) | √n = 2.83
Sylvester-16 | 4 | (batch-1 exact: 4) | √n = 4.00

Reading: exact opt sits at 2–4 for n up to 16 (even n ⟹ even row sums, so opt is even), far below Spencer’s 6√n = 24 at n = 16; a single random coloring already gives expected max ≈ E max |N(0,n)| ≈ 2.8 (n=4) → 4.9 (n=8) → 8.1 (n=16), matching the mean-random column; best-of-10,000 random finds the optimum in 13 of 20 instances and is within 2 everywhere — the honest lesson is that Spencer’s theorem is an existence guarantee with a generous constant, while opt itself here stays a small constant multiple of √n’s lower reaches. The Hadamard lower bound √n is attained by Sylvester-4/16, beaten at Sylvester-8 (4 > 2.83).

Independent re-verification (naive full-recompute enumerator, no Gray-code incremental updates): n=4 inst#1: naive=2 gray=2 MATCH; n=4 inst#4: naive=0 gray=0 MATCH; n=8 inst#1: naive=2 gray=2 MATCH; n=12 inst#3: naive=2 gray=2 MATCH; n=16 inst#4: naive=4 gray=4 MATCH — ALL MATCH. Parity remark: for even n every row sum of a ±1 matrix is even for any coloring (100 machine checks), so the optimum is even — hence opt ∈ {0, 2, 4} in the table above; at n = 12 the binomial count predicts ~22 of the 4,096 colorings achieve max |row sum| ≤ 2, so opt = 2 is typical, matching all five instances.