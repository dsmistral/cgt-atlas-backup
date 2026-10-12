# 51runs-4.md — session 51, batch 4: random-graph evolution (machine receipts)

Seeds: Lehmer LCG x <- 48271x mod (2^31-1); E1 20261012, E2 20261013, E3 20261014. Adjacency arrays only (32-bit word rule); all counting exact.

E0: trace(A^3) = 6*#C3 verified on ALL 33792 graphs (n=5: 1024, n=6: 32768); DFS cycle counter (k=3,4,5) matches brute-force permutation enumeration on every graph; total checks=236544, violations=0

E1 giant component, G(1000, c/1000), 20 samples/cell, Lehmer seed 20261012:
c | mean largest-frac | rho(c) (rho=1-e^{-c rho}) | mean isolated-frac | e^{-c} | mean edges vs c(n-1)/2
0.5 | 0.0112 | 0.000 | 0.6082 | 0.607 | 250.4 vs 249.8
1.5 | 0.5706 | 0.583 | 0.2244 | 0.223 | 743.0 vs 749.3
2 | 0.7940 | 0.797 | 0.1341 | 0.135 | 994.9 vs 999.0
3 | 0.9405 | 0.940 | 0.0500 | 0.050 | 1497.0 vs 1498.5

E2 connectivity, G(400, (ln 400 + c)/400), 200 samples/cell, Lehmer seed 20261013:
c | p | frac connected | frac no-isolated-vertex | limit e^{-e^{-c}}
-1 | 0.01248 | 0.070 | 0.080 | 0.0660
0 | 0.01498 | 0.390 | 0.390 | 0.3679
1 | 0.01748 | 0.755 | 0.755 | 0.6922

E3 cycle counts, G(1000, c/1000), 40 samples/cell, Lehmer seed 20261014 (DFS counter, E0-certified):
c | k | MC mean | exact finite-n E#C_k = (n)_k p^k/(2k) | asymptotic c^k/(2k)
1 | 3 | 0.2250 | 0.1662 | 0.1667
1 | 4 | 0.0500 | 0.1243 | 0.1250
1 | 5 | 0.0250 | 0.0990 | 0.1000
2 | 3 | 1.4000 | 1.3293 | 1.3333
2 | 4 | 1.9500 | 1.9880 | 2.0000
2 | 5 | 2.6750 | 3.1681 | 3.2000

E3b cycle-count re-run (tighter error bars; AUTHORITATIVE for the chapter — supersedes the noisy 40-sample E3 pilot): G(500, c/500), 200 samples/cell, Lehmer seeds 20261015 (c=1), 20261016 (c=2). Poisson SE in brackets.
c | k | MC mean | exact finite-n | asymptotic c^k/(2k)
1 | 3 | 0.1300 [0.071] | 0.1657 | 0.1667
1 | 4 | 0.0950 [0.071] | 0.1235 | 0.1250
1 | 5 | 0.1350 [0.071] | 0.0980 | 0.1000
2 | 3 | 1.3700 [0.081] | 1.3253 | 1.3333
2 | 4 | 2.0300 [0.099] | 1.9761 | 2.0000
2 | 5 | 3.0250 [0.125] | 3.1364 | 3.2000
