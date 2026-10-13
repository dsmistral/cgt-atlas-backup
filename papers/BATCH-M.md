# Batch M - Modern structural and algorithmic heavy hitters (gathered and mined; work style v2)

Chunk 13 under work style v2: three sub-chunks of three papers, each pushed as its own commit. This file is created at sub-chunk 13a and extended at every sub-chunk close. Watch items for this batch: CAND-A4 entropy compression (watch M), WATCH Boolean influence (B3, watch M), WATCH spread induction (B6, watch M). Two origin WATCH items opened at 13a (flag algebras; Luks-framework group recursion).

| Sub-chunk | Papers | Status |
|-----------|--------|--------|
| 13a | M1 Luks; M2 Babai; M3 Razborov flag algebras | DONE (section below) |
| 13b | M4 Razborov triangle density; M5 Alon-Shapira; M6 Alon-Fischer-Newman-Shapira | PENDING |
| 13c | M7 Hopcroft-Tarjan; M8 Kruskal MST; M9 Grohe | PENDING |

## Sub-chunk 13a (M1-M3) - gathered and mined 2026-10-13

All 3 papers metadata-verified; moves at flagged-sketch level from publisher/author/arXiv records and standard survey material; zero paywalled fetches. HEADLINES: the isomorphism column M1 -> M2 is ONE engine firing twice (the Luks framework) - a WATCH item opened for a NO-Atlas-pattern coverage-gap engine; the flag-algebras calculus opens its origin WATCH with the built-in second-batch test at M4 (13b); THREE honest seed misses (M1 P19, M2 P8, M2 P30 - all direction-wrong).

### Verification table

| ID | Verified citation | Corrections vs seed |
|----|------------------|---------------------|
| M1 | Luks, "Isomorphism of graphs of bounded valence can be tested in polynomial time", J. Comput. System Sci. 25(1): 42-65 (1982), DOI 10.1016/0022-0000(82)90009-5 | TITLE corrected: "decided" -> "tested"; vol/issue/pages/DOI pinned; the 1980 FOCS conference-abstract priority noted (ADS record) |
| M2 | Babai, "Graph isomorphism in quasipolynomial time [extended abstract]", Proc. 48th ACM STOC (2016): 684-697, DOI 10.1145/2897518.2897542; full version arXiv:1512.03547 (v1 11 Dec 2015) | Title/year CONFIRMED; pages/DOI pinned via the author's Chicago page; journal version NOT pinned (extended abstract + arXiv is the canonical citation - recorded honestly); the Jan 2017 gap-and-fix episode verified and recorded |
| M3 | Razborov, "Flag algebras", J. Symbolic Logic 72(4): 1239-1282 (December 2007), DOI 10.2178/jsl/1203350785 | Venue CONFIRMED as seeded; pages/DOI pinned (Project Euclid + Cambridge + the Bulletin of Symbolic Logic all agree) |

### Pattern census (sub-chunk 13a)

| P-ID | Fires in | Notes |
|------|----------|-------|
| P25 reduction / encoding | M1 (genuine), M2 (genuine), M3 (flagship) | the isomorphism column carries the pattern twice: M1 - GI encoded as the color-automorphism problem for permutation groups with bounded simple sections (the reduction IS the title move); M2 - GI reduced to String Isomorphism / Coset Intersection under group action (the Luks-framework vehicle; quasipolynomial in the largest orbit). M3: asymptotic extremal questions encoded as elements of the flag algebra with positivity constraints - the model-theoretic translation is the whole framework |
| P18 algorithmic proof | M1, M2 (genuine) | the isomorphism column: proof = procedure - polynomial-time bounded-valence testing (M1), the quasipolynomial general test (M2); correctness and complexity analysis are one; the pattern's first GI-batch exemplars |
| P4 recurrence + induction | M1 (partial), M2 (genuine) | M1: divide-and-conquer down the composition series (trivalent case elementary; higher valence via primitive-group observations). M2: the aggregate-consumption recursion over the permutation domain is load-bearing in the quasipolynomial bound |
| P19 rank / linear algebra | M3 (partial) | the flag algebra's sum-of-squares positivity lives in the inner-product algebra of the flag vector space - Cauchy-Schwarz as the framework's fundamental inequality; a fifth-batch touch (C4/F5, I, J, L, now M3 partial) |
| P37 duality | M3 (partial) | the density inequalities certified by SDP duals (sum-of-squares certificates) - the I11 Delsarte-LP lineage's density-era descendant; family note widens (E4 planar, H10 Konig, I11 LP, J2 optimization duality, now M3 SDP) |
| WATCH flag algebras (new) | M3 (ORIGIN) | the seed's own expected candidate executed: the calculus formalized; the in-paper Fisher re-proof is the first application; the built-in second-batch test is M4 (the minimal-triangle-density theorem, 13b) |
| WATCH Luks-framework group recursion (new) | M1 (ORIGIN), M2 (second firing) | a coverage-gap engine matching NO Atlas pattern: P25 records the reduction, P18 the algorithmic character, P4 the recursion - but the load-bearing engine is finite permutation-group theory (bounded simple sections; primitive-group observations; the split-or-Johnson dichotomy). Two firings in one sub-chunk is the survey's fastest recurrence evidence for a coverage gap; synthesis call on Atlas naming |

### Honest hypothesis-test results (sub-chunk 13a's yield)

- M1 P19 MISSED (expected by seed; direction-wrong): no rank/dimension bound; the engine is finite permutation-group theory - recorded as the THIRD Atlas-coverage-gap engine (after Wilson's PBD-closure number theory and Gleason's invariant theory). P25 CONFIRMED (expected; flagship). P18 and P4 confirmed (both unplanned by seed).
- M2 P8 AND P30 BOTH MISSED (both expected; direction-wrong): no extremal-object analysis, no regularity partition - the Design Lemma's split-or-Johnson dichotomy (hereditary quasirandomness or a canonical UPC structure) is neither. P25/P18/P4 confirmed (all unplanned by seed).
- M3 P25 CONFIRMED (expected, flagship); P19/P37 partials confirmed (unplanned); the seed's own "candidate: flag algebras" executed - WATCH opened at the origin with the M4 second-batch test pending (13b).
- CAND-A4 entropy compression, WATCH Boolean influence, WATCH spread induction: NOT tested in 13a (no plausible firing in the isomorphism column or flag algebras; the watch-M tests run at 13b/13c).

### Lineages recorded for teaching

- M1 -> M2: the Luks framework - bounded-valence polynomial time (1982) -> quasipolynomial general GI (2016); Babai's own abstract names the Luks-era exp(O(sqrt(n log n))) record the new algorithm breaks. One engine, two papers, 34 years - the survey's longest same-engine arc inside one sub-chunk.
- The gap-and-fix episode as VERIFICATION-process material (not an engine): the Dec 2015 announcement -> the Jan 2017 Split-or-Johnson error (Helfgott) -> the Jan 9 fix (Babai) -> the Bourbaki confirmation (Jan 14) - recorded because the M2 record must cite the FIXED version.
- M3 -> M4 (planned, 13b): the origin-to-application arc inside one batch - the flag-algebra calculus applied to the minimal triangle density; mirrors the L6 -> L8 nibble arc compressed into consecutive sub-chunks.
- M3 -> I11 Delsarte: the SDP certificates are the density-era descendant of the association-scheme LP (the P37 lineage widened).
- L1 (12a) -> M1/M2: the 12a L1 partial recorded "combinatorics and group theory carried together"; the isomorphism column is that theme made algorithmic.

### Verification levels statement (13a)

Metadata: web-verified (sources per paper: M1 ScienceDirect + the author's open Oregon PDF + the ADS record; M2 the arXiv abstract page + the author's Chicago publications page (DOI/pages) + the ICALP 2020 and SIAM J. Comput. citing bibliographies + Babai's own "update, January 9, 2017" note + the Aperiodical/Quanta timeline; M3 Project Euclid + Cambridge Core + the Bulletin of Symbolic Logic review). Moves: flagged-sketch summaries. Zero full-text fetches. Honesty record: M2's journal version unpinned (recorded, never guessed); M1/M3 fully pinned.

(13b and 13c pending; file extended at each sub-chunk close.)
