## Session 54 machine runs — batch 5 (Chunk 54c-V: SQS(8) uniqueness + the Barrau S(3,4,10)) — 2026-10-12

### S1 — SQS(8) = S(3,4,8): full labeled enumeration, uniqueness, Aut order
- **Algorithm:** backtracking on the lowest uncovered triple (a,b,c), trying every d > c with all four contained triples uncovered; leaves = exact covers of all C(8,3) = 56 triples in 14 blocks; every leaf independently validity-checked (each triple exactly once; every pair in exactly λ₂ = (v−2)/2 = 3 blocks). 3-uniform propagation isomorphism (a block of A with 3 assigned points forces the 4th through the unique B-block containing the images; full blocks checked against B's block set; undo trail).
- **Results (byte-exact):** labeled SQS(8) count = **30** (= 8!/1344), 366 search nodes; all 30 valid, λ₂ = 3 at every pair; **all 30 isomorphic to the first — one orbit ⇒ SQS(8) UNIQUE** (max iso steps 36); **|Aut| machine-counted = 1344** (= AGL(3,2); consistent: 30 × 1344 = 8!).
- **Witness (the AG(3,2) system):** 0123 0145 0167 0246 0257 0347 0356 1247 1256 1346 1357 2345 2367 4567.

### S2 — SQS(10) = S(3,4,10): full labeled enumeration, uniqueness (Barrau 1908 machine-confirmed), Aut order
- **Algorithm:** identical (65,683 search nodes; every leaf validity-checked: 30 blocks, every triple exactly once, λ₂ = 4 at every pair).
- **Results (byte-exact):** labeled SQS(10) count = **2,520**; **all 2,520 isomorphic to the first — one orbit ⇒ SQS(10) UNIQUE** (Barrau 1908 machine-confirmed; max iso steps 55); **|Aut| machine-counted = 1,440**; consistency: 2,520 × 1,440 = 3,628,800 = 10!.
- **HONEST CATCH (recorded for authoring):** the remembered "Aut = PΓL(2,9) of order 15,120 / 240 labeled" was WRONG. Machine truth: |Aut| = 1,440 — which IS PΓL(2,9): PSL(2,9) ≅ A₆ order 360, PGL(2,9) = 9·80 = 720, ×2 (the field automorphism of F₉) = 1,440; labeled count 10!/1,440 = 2,520. The chapter uses the MACHINE numbers (unique, |Aut| = 1,440, 2,520 labeled).
- **Witness:** 0123 0145 0167 0189 0246 0258 0279 0349 0357 0368 0478 0569 1247 1259 1268 1348 1356 1379 1469 1578 2345 2369 2378 2489 2567 3467 3589 4568 4579 6789.

All numbers above are byte-exact outputs of this run. Receipt for chunk 54c target (4) — SQS(8) uniqueness + Barrau's S(3,4,10) verified (and strengthened: full uniqueness by enumeration).
