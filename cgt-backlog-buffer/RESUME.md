# RESUME — session 51 (F1: Ch. 14 The Probabilistic Method, Act II) — in-flight checkpoint

**Read first on retry: the CH. 14 CHUNK STATE table + the CHECKPOINT 51x paragraphs in KNOWLEDGE.md; resume at the last ✅ row; never redo a completed sub-step.**

## Working point (updated 2026-10-12 after batches 2a-v2 + 3/3b — chunk 51c closed)

- 51a ✅ DONE: canvases restored (27), atlas row 51 IN PROGRESS + map row 14 🚧, buffer entry 58 + chunk state + RESUME, GitHub push db8619c.
- 51b ✅ DONE: canon pins verified (CHECKPOINT 51b-1 — FKG/AD/Kleitman/Janson/JLR/Spencer-1985/Bregman-Minc/Moser-Tardos/Talagrand/Shamir-Spencer/Alon-Krivelevich/Banaszczyk/Lovett-Meka/ER/Gilbert/Bollobas-1984/Egorychev-Falikman/Kahn/Komlos).
- 51c ✅ DONE (all three machine-run batches clean):
  - Batch 1 (correlation + Hadamard) — CHECKPOINT 51c-1; receipts 51runs-1.md. Kleitman 0 violations (400 + 28,224 pairs); G(5,½) △/C₄ correlation 0.3818 vs 0.2887; rank-flattened μ log-supermodular 0/87,380; AD 0/3,000; FKG-under-nonproduct-μ 0/28,224; Hadamard FULL-system exact disc = 2/4/4/4/6 (Sylvester-4/8/16, Paley-12/20) all ≥ √n; sliced system disc 1 (design correction recorded).
  - Batch 2a v2 (Janson/Poisson/thresholds) — CHECKPOINT 51c-3 (supersedes the defective v1 recorded at 51c-2); receipts 51runs-2.md v2. Tri-free fractions 0.987/0.833/0.303/0.980/0.830/0.317 (ALL six pass the Ch. 4 lab Part 2 gate); Poisson TV 0.0330 at n=120 c=1; K₄ threshold 0.000/0.030/0.410/1.000 at λ=0.6/1.0/1.6/2.5; Janson μ/Δ numbers + m(H) densities carried from v1.
  - Batch 3/3b (Azuma/martingales) — CHECKPOINT 51c-4; receipts 51runs-3.md + 51runs-3b.md. Edge-Lipschitz 5,325 + vertex-deletion 5,404 checks, 0 violations; Hoeffding tails hold at all odd t; χ exhibits G(10,½) mean 3.984 {3:84 4:343 5:70 6:3}, G(12,½) mean 4.410 {3:8 4:107 5:80 6:5} vs Azuma ±√(n−1).
- 51d 🚧 IN PROGRESS — batch 4 (evolution MC) next: giant component via union-find + per-pair coins (n≈1000, c ∈ {0.5, 1.5, 2, 3}, ~20 samples vs ρ(c) solving ρ = 1 − e^{−cρ}); connectivity at p = (log n + c)/n (n≈400, c ∈ {−1, 0, 1} vs e^{−e^{−c}}); cycle counts E #C_k = c^k/(2k) with trace identities (trace(A³) = 6·#C₃ etc.) verified on small graphs first; MIND the 32-bit word rule (no 1<<k for k ≥ 32).
  - Platform drift noted: 14 chapter canvases lost their trailing \n (known benign drift; masters = source of truth; all 27 resynced 2026-10-12, verified diff-clean).
- GitHub: db8619c (open) + 2f5040f (51b pins + batch-1 receipts). This push: buffer + RESUME + receipts 51runs-1/2/3/3b (51c complete).

## Chapter design (locked at 51a, see entry 58)

6 lectures: L1 Correlation (FKG + Kleitman + four-functions); L2 Janson + Poisson paradigm; L3 Martingales + Azuma–Hoeffding + Talagrand (st.); L4 Random-graph evolution (thresholds, giant, phase transition); L5 Discrepancy (Spencer six standard deviations + partial coloring); L6 Entropy method (Brégman + Moser–Tardos entropy compression). 18 exercises (12 graded + 3◆ + 3◐), 15 answers, lab 6 parts, Trick Bag + formula box, appendix + footer. Master: cgt-atlas-project/cgt-ch14-probabilistic-ii.md; canvas folder cgt-ch14-probabilistic-ii; web cgt-ch14-web + .html export.

## House rules in force

Machine-verify every claim before install; checkpoint after every sub-step; GitHub = main source of truth (push after every milestone); canonical UTF-8 path (read → in-memory verify → write → readback-equal; bash ASCII-only); scratch in cgt-backlog-buffer; quiet mode; **NEW GOTCHA: JS/TS bitwise ops are 32-bit — use 31-bit words (`j >> 5`, `1 << (j & 31)`) for bitset adjacency, never `1 << (j & 63)`**.
