## Session 51 machine runs — batch 3 v2 (martingales + Azuma + Hoeffding; C2 re-run adjacency-safe; supersedes v1 C2)

NOTE: the v1 C2 exhibit was corrupted by the 32-bit shift gotcha (edge masks of 45/66 bits) — recorded in CHECKPOINT 51c-4. The C1 censuses (n<=5, E<=10) and C3 were always safe.

```
chiDP-adj asserts: K5=5(5) K4=4(4) K3,3=2(2) C5=3(3) Petersen=3(3) empty5=1(1) ALL=PASS
C2 G(10,1/2) exact-chi 500 samples (adjacency-safe): mean=3.984 dist {3:84 4:343 5:70 6:3}; observed values 3..6 (window 3); Azuma window +-3.00 => [0.98, 6.98]
C2 G(12,1/2) exact-chi 200 samples (adjacency-safe): mean=4.410 dist {3:8 4:107 5:80 6:5}; observed values 3..6 (window 3); Azuma window +-3.32 => [1.09, 7.73]
```

Carried from v1 (safe, no big masks): C1 edge-flip census 5,325 checks 0 violations; C1-vertex census (batch 3b, fixed relabeling) 5,404 checks 0 violations; C3 Hoeffding exact tails n=20: HOLDS at all odd t, worst slack 0.
