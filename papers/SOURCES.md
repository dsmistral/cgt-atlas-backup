# Sources register - the books and papers behind the pattern survey

Added 2026-10-13 (user-directed): a durable record of every book and paper used so far for pattern finding, so the survey can be extended with new books and papers later. SOURCES.md is the register; CORPUS.md remains the authoritative seed list for gathered batches; the per-paper files and batch files are the gather record; papers/patterns/ is the accumulated pattern layer. Updated incrementally, never pruned silently.

## 1. The pattern source (the book)

The CGT Atlas - a multi-chapter combinatorics and graph theory book, the survey's raison d'etre. The 42-pattern Master Pattern Index is the Atlas's pattern layer; every P-ID in this repo refers to it. The Atlas exists as 35 chapter files plus web editions and a publishing toolkit (master copy in the cgt-atlas project; this repo backs up the survey, not the book). No other books were used for the survey: all paper metadata was web-verified from publisher/author/open-access records (see the verification-levels statements in each batch file). If future extensions use other books, they enter through this register with title, chapters used, and the patterns they exercise.

## 2. The test corpus gathered so far (papers A1-M9, chunks 0-13)

- Seed list: papers/CORPUS.md - 126 seed rows, 125 DISTINCT papers (L5 Ray-Chaudhuri-Wilson confirmed a duplicate of I3 at 12b; count 126 -> 125, flagged for the synthesis).
- Gather record: per-paper files papers/A1-*.md through papers/M9-*.md (template: metadata / flagged-sketch summary / decisive moves with P-ID tags / new-pattern candidates / full-text status / corrections log); batch files papers/BATCH-A.md through papers/BATCH-M.md (verification tables, pattern censuses, honest hypothesis-test results, lineages, verification-levels statements).
- Pattern layer: papers/patterns/ - INDEX.md + the 42 pattern dossiers in 11 family folders + candidates/ (7 CAND/WATCH dossiers).
- Batch themes: A probabilistic method, random graphs (9); B thresholds, entropy, containers (9); C enumerative counting (7); D matching, flows, greedy, algorithms (10); E coloring, list coloring, flows (11); F Ramsey theory (10); G regularity, density, removal (12); H extremal graph theory and structure (13); I algebraic and polynomial methods (12); J spectral methods (4); K shadows and compression (8); L designs, packing, codes (12 rows, 11 distinct); M modern structural and algorithmic (9).

## 3. Standing verification policy (user-directed, binding for all extensions)

1. ACCEPTED papers only: a row enters the corpus only with evidence of journal acceptance (a peer-reviewed venue with a pinned citation). Never proposals, never mere surveys.
2. Metadata web-verified; moves at flagged-sketch level from publisher/author/open-access records; zero paywalled fetches; open full text fetched only when a pattern decision needs it (the standing scope rule).
3. Corrections and honest misses logged, never silently.
4. New books or papers enter through this register first (seed rows with verification status), then gather per work style v2 (sub-chunks of about three papers, one push_files commit each, STATE.md + INDEX.md + touched dossiers updated in the same commit).

## 4. Batch N seed rows - youth-authored ACCEPTED papers (undergraduate and below)

Purpose (user-directed, 2026-10-13): the view of Atlas patterns ACCESSIBLE enough - and mostly used - at pre-doctoral levels: which patterns let high school, amateur, and undergraduate authors reach research-grade results. Gather = chunk 14 (sub-chunks N-a/N-b/N-c per work style v2); the synthesis moves to chunk 15. All 8 rows below are ACCEPTANCE-VERIFIED (2026-10-13); the expected patterns are seed hypotheses, to be honestly tested at gather.

| ID | Paper (verified) | Venue (verified) | Author level | Expected Atlas patterns (seed hypotheses) |
|----|------------------|------------------|--------------|--------------------------------------------|
| N1 | Jackson-Johnson, "Five or Ten New Proofs of the Pythagorean Theorem" | Amer. Math. Monthly 131(9): 739 (2024), DOI 10.1080/00029890.2024.2370240 (lead article, Nov 2024; presented at an AMS sectional meeting 2023) | HIGH SCHOOL (St. Mary's Academy, New Orleans) | P4? - a domain outlier (trigonometry, not combinatorics); the trig engine may match NO Atlas pattern, which is itself the interesting datum for the accessibility question |
| N2 | Sah-Sawhney-Stoner-Zhao, "The number of independent sets in an irregular graph" (settles Kahn's 2001 conjecture) | J. Combin. Theory Ser. B 138: 172-195 (2019) | UNDERGRADUATES (sophomore + junior at MIT, Harvard senior; per the MIT News record) | P29 (Kahn's entropy argument - the P29 flagship lineage), P25 (Zhao's bipartite-swapping reduction), P10, P9 |
| N3 | Jain-Sah-Sawhney, "Anticoncentration versus the number of subset sums" | Advances in Combinatorics 2021:6 (peer-reviewed) | UNDERGRAD-ERA (the Sah-Sawhney Morgan-Prize window) | P28-family? (anticoncentration - the K1 Littlewood-Offord lineage continuation), P10, P13 |
| N4 | Agrawal-Ge-Greene-Khovanova-Kim-Mandal-Parida-Pulugurtha-Redwine-Samanta-Xu, "Chip-Firing on Infinite k-ary Trees" | Enumerative Combinatorics and Applications 6:1 (2026), article #S2R7 (arXiv:2501.06675) | MIDDLE SCHOOL (PRIMES STEP, grades 6-9) | P5 (the fire-count sequences), P7 (chip-firing invariants and parity), P4 |
| N5 | Borodin-Chen-Duncan-Khovanova-Litchev-Liu-Moroz-Qian-Raghavan-Rastogi-Voigt, "The Stable Marriage Problem and Sudoku" | College Mathematics Journal 55(4) (2024) (a PRIMES STEP 2021 project) | MIDDLE SCHOOL (PRIMES STEP, grades 6-9) | P25 (the matching-Sudoku encoding), P9, P16? (stable matching augmenting structure) |
| N6 | The same PRIMES STEP circle, "Sequences of the Stable Matching Problem" | Journal of Integer Sequences (peer-reviewed; pin the volume/article at gather) | MIDDLE SCHOOL (PRIMES STEP) | P5, P2 (double counting of matchings), P23? |
| N7 | Kuszmaul, "Counting Permutations Modulo Pattern-Replacement Equivalences for Three-Letter Patterns" | The Electronic Journal of Combinatorics (2013; fully refereed) | HIGH SCHOOL (in PRIMES from 9th grade; the E-JC publication noted in the PRIMES record) | P1 (bijections on equivalence classes), P5, P23 (shuffling-like equivalence moves) |
| N8 | Sah-Sawhney-Stoner-Zhao, "A reverse Sidorenko inequality" | Inventiones mathematicae 221(2): 665-711 (2020), DOI 10.1007/s00222-020-00956-9 | UNDERGRAD-ERA (cited in the 2021 Morgan Prize award) | P10 (homomorphism-density averaging), P25, the P30/P31 quasirandomness family (the G-batch lineage) |

### Candidates pending acceptance verification (not seed rows yet - the rule is binding)

- PRIMES-USA representation-theory paper (arXiv:2406.06712) - reported secondhand as published in the Journal of Algebra; acceptance not yet verified from a journal record; verify before seeding.
- Inagaki-Khovanova-Luo, "On chip-firing on undirected binary trees" (arXiv:2410.00039) - arXiv only: EXCLUDED by the accepted-papers rule unless a journal acceptance appears.
- The PRIMES STEP "Cookie Monster Problem" line (arXiv:1309.5985) - arXiv only: excluded unless acceptance is verified.

### Standing extension rule

Future books or papers append their rows here (with verification status) before gather. Entries are never removed silently; superseded or excluded entries carry dated notes.
