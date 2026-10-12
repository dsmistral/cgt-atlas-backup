# RESUME — session 51 (F1: Ch. 14 The Probabilistic Method, Act II) — in-flight checkpoint

**Read first on retry: the CH. 14 CHUNK STATE table + the CHECKPOINT 51x paragraphs in KNOWLEDGE.md; resume at the last ✅ row; never redo a completed sub-step.**

## Working point (updated 2026-10-12 after the retry)

- 51a ✅ DONE: canvases restored (27), atlas row 51 IN PROGRESS + map row 14 🚧, buffer entry 58 + chunk state + RESUME, GitHub push db8619c.
- 51b ✅ DONE: canon pins verified (CHECKPOINT 51b-1 — FKG/AD/Kleitman/Janson/JLR/Spencer-1985/Bregman-Minc/Moser-Tardos/Talagrand/Shamir-Spencer/Alon-Krivelevich/Banaszczyk/Lovett-Meka/ER/Gilbert/Bollobas-1984/Egorychev-Falikman/Kahn/Komlos).
- 51c 🚧 IN PROGRESS:
  - Batch 1 (correlation + Hadamard) ✅ CLEAN — CHECKPOINT 51c-1; receipts 51runs-1.md. Key numbers: Kleitman 0 violations (400 + 28,224 pairs); G(5,½) △/C₄ correlation 0.3818 vs 0.2887; rank-flattened μ log-supermodular 0/87,380; AD 0/3,000; FKG-under-nonproduct-μ 0/28,224; Hadamard FULL-system exact disc = 2/4/4/4/6 (Sylvester-4/8/16, Paley-12/20) all ≥ √n; sliced system has disc 1 (design correction recorded).
  - Batch 2a (Janson/Poisson/thresholds) ⚠️ RAN DEFECTIVE — CHECKPOINT 51c-2: JS 32-bit shift gotcha (`1 << (j & 63)` aliases) corrupted the bitset MCs; the receipts in 51runs-2.md are GARBAGE except B1 (pair identities 90/210 ✓, Janson numbers μ/Δ at 100/1000/10000 ✓) and B4 (m(H): K₃=1, K₄=1.5, C₄=1, K₄−e=1.25, K₅=2, paw=1 ✓). RE-RUN B2/B3/B4b with 32-bit words (`j >> 5`, `1 << (j & 31)`) — the immediate next step.
  - Batch 3 (Azuma/martingales), batch 4 (evolution MC), batch 5 (discrepancy optima), batch 6 (Brégman census + vdW + M–T resampler) — NOT STARTED.
- Platform drift noted: 14 chapter canvases lost their trailing \n (known benign drift; masters = source of truth; all 27 resynced 2026-10-12, verified diff-clean).
- GitHub: last push db8619c (session open). PUSH after this checkpoint (buffer + RESUME + receipts 51runs-1/2).

## Chapter design (locked at 51a, see entry 58)

6 lectures: L1 Correlation (FKG + Kleitman + four-functions); L2 Janson + Poisson paradigm; L3 Martingales + Azuma–Hoeffding + Talagrand (st.); L4 Random-graph evolution (thresholds, giant, phase transition); L5 Discrepancy (Spencer six standard deviations + partial coloring); L6 Entropy method (Brégman + Moser–Tardos entropy compression). 18 exercises (12 graded + 3◆ + 3◐), 15 answers, lab 6 parts, Trick Bag + formula box, appendix + footer. Master: cgt-atlas-project/cgt-ch14-probabilistic-ii.md; canvas folder cgt-ch14-probabilistic-ii; web cgt-ch14-web + .html export.

## House rules in force

Machine-verify every claim before install; checkpoint after every sub-step; GitHub = main source of truth (push after every milestone); canonical UTF-8 path (read → in-memory verify → write → readback-equal; bash ASCII-only); scratch in cgt-backlog-buffer; quiet mode; **NEW GOTCHA: JS/TS bitwise ops are 32-bit — use 31-bit words (`j >> 5`, `1 << (j & 31)`) for bitset adjacency, never `1 << (j & 63)`**.
