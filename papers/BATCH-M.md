# Batch M - Modern structural and algorithmic heavy hitters (gathered and mined; work style v2)

Chunk 13 under work style v2: three sub-chunks of three papers, each pushed as its own commit. This file is created at sub-chunk 13a and extended at every sub-chunk close. Watch items for this batch: CAND-A4 entropy compression (watch M), WATCH Boolean influence (B3, watch M), WATCH spread induction (B6, watch M). Two origin WATCH items opened at 13a (flag algebras; Luks-framework group recursion).

| Sub-chunk | Papers | Status |
|-----------|--------|--------|
| 13a | M1 Luks; M2 Babai; M3 Razborov flag algebras | DONE (section below) |
| 13b | M4 Razborov triangle density; M5 Alon-Shapira; M6 Alon-Fischer-Newman-Shapira | DONE (section below) |
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

(13c pending; file extended at each sub-chunk close.)

## Sub-chunk 13b (M4-M6) - gathered and mined 2026-10-13

All 3 papers metadata-verified; moves at flagged-sketch level from publisher records, the author's research pages, and standard survey material; zero paywalled fetches. HEADLINES: the flag-algebras WATCH lands its second firing at M4 - but both firings are within Batch M (the cross-batch recurrence test cannot be satisfied in-corpus; the synthesis call mirrors the CAND-B5 single-batch precedent); P30's designed watch-M firing LANDS in the property-testing column (M5 genuine + M6 flagship - the subtitle IS the pattern).

### Verification table

| ID | Verified citation | Corrections vs seed |
|----|------------------|---------------------|
| M4 | Razborov, "On the minimal density of triangles in graphs", Combin. Probab. Comput. 17(4): 603-618 (2008) | VENUE CORRECTED: Algebra i Analiz (seed) -> CP&C; vol/issue/pages pinned (Cambridge Core + the author's research page; the author's verification Maple worksheet noted) |
| M5 | Alon-Shapira, "Every monotone graph property is testable", SIAM J. Comput. 38(2): 505-522 (2008); STOC 2005 preliminary | Title/venue/year CONFIRMED; vol(2)/pages pinned (the Princeton record + the M6 bibliography); the conference-version priority noted |
| M6 | Alon-Fischer-Newman-Shapira, "A combinatorial characterization of the testable graph properties: It's all about regularity", SIAM J. Comput. 39(1): 143-167 (2009); STOC'06 preliminary | SUBTITLE pinned; vol/issue/pages pinned (two bibliographies agreeing); year CONFIRMED |

### Pattern census (sub-chunk 13b)

| P-ID | Fires in | Notes |
|------|----------|-------|
| P30 regularity partitioning | M5 (genuine), M6 (flagship) | THE DESIGNED-BATCH FIRING: the property-testing column is regularity-powered end to end - M5: monotone testability via a regularity-based sampler (the finite forbidden-coloring characterization); M6: the title move - testability characterized by regular-reducibility, and the Szemeredi-partition property itself testable with a constant number of queries |
| P25 reduction / encoding | M4 (genuine), M5 (partial), M6 (partial) | M4: the flag-algebra encoding again (the framework's second in-corpus firing). M5/M6 partials: the finite forbidden-coloring encoding (M5); the regularity-profile encoding (M6) |
| P18 algorithmic proof | M5, M6 (genuine) | the property-testing column: the randomized tester IS the procedure - constant queries decide the property |
| P19 rank / linear algebra | M4 (partial) | the sum-of-squares/Cauchy-Schwarz engine inside the triangle-density proof - the same partial face as at M3 |
| P37 duality | M4 (partial) | the SDP certificates carry the triangle-density inequality - the same partial face as at M3; the Delsarte-LP lineage's density-era descendant repeats |
| WATCH flag algebras | M4 (SECOND firing) | the calculus's landmark application (the explicit piecewise formula for g3(rho)); both firings within batch M - the cross-batch test cannot be satisfied in-corpus; the synthesis call mirrors the CAND-B5 single-batch precedent |

### Honest hypothesis-test results (sub-chunk 13b's yield)

- M4 P25 CONFIRMED (expected by seed); P19/P37 partials confirmed (unplanned, same faces as at M3); the flag-algebras WATCH second firing recorded with the single-batch caveat (extend-never-guess: no cross-batch credit claimed).
- M5 P30 CONFIRMED (expected by seed, genuine); P18 genuine + P25 partial confirmed (unplanned).
- M6 P30 CONFIRMED (expected by seed, FLAGSHIP - the subtitle names the pattern); P18 genuine + P25 partial confirmed (unplanned).
- CAND-A4 entropy compression, WATCH Boolean influence, WATCH spread induction: NOT fired at 13b (no plausible firing in the flag-algebra or property-testing engines); final in-corpus chance 13c.

### Lineages recorded for teaching

- M3 -> M4: the origin-to-application arc inside one batch, complete - the flag-algebra calculus's landmark theorem; the external descendants carry the load-bearing story (the K_r clique-density program completed by Reiher's theorem; the pentagons-in-triangle-free-graphs line; Hatami's inequality-complexity framework) - recorded in the WATCH dossier.
- M5 -> M6: monotone testability as the special case feeding the combinatorial characterization; the sibling Alon-Shapira one-sided-error paper (SIAM J. Comput. 37 (2008): 1703-1727) is the companion record - the pair splits the characterization problem by error model, mirroring the Assmus-Mattson companion precedent.
- G7 -> M5/M6: the "regularity as algorithmic data" face that Frieze-Kannan opened in Batch G is realized here - the P30 family's algorithmic face, six batches later (cross-batch family continuity: F birthplace -> G flagship -> M application era).
- H5 -> M4: the triangle-density formula refines the supersaturation story - the exact boundary curve between the classic extremal era (Turan/Erdos-Stone, G2/H) and the modern density era.

### Verification levels statement (13b)

Metadata: web-verified (sources per paper: M4 Cambridge Core + the author's research page; M5 the Princeton research record + the M6 bibliography + citing papers; M6 two independent bibliographies (DROPS; Theory of Computing) agreeing on 39(1):143-167). Moves: flagged-sketch summaries. Zero full-text fetches. All three papers fully pinned (title + venue + vol/pages + year).
