# Batch L - Designs, packing and codes (gathered and mined; work style v2)

Chunk 12 under work style v2: four sub-chunks of three papers, each pushed as its own commit. This file is created at sub-chunk 12a and extended at every sub-chunk close. Designed home of the silent P41 (divisibility) and P42 (words-as-designs).

| Sub-chunk | Papers | Status |
|-----------|--------|--------|
| 12a | L1 Witt; L2 Bruck-Ryser; L3 Hanani | DONE (sections below) |
| 12b | L4 Wilson; L5 Ray-Chaudhuri-Wilson; L6 Rodl | DONE (sections below) |
| 12c | L7 Teirlinck; L8 Keevash; L9 Pippenger-Spencer | DONE (sections below) |
| 12d | L10 Assmus-Mattson; L11 MacWilliams; L12 Gleason | PENDING |

## Sub-chunk 12a (L1-L3) - gathered and mined 2026-10-13

All 3 papers metadata-verified; move descriptions at flagged-sketch level from publisher pages, the Cambridge Core abstract (L3 partly quoted), and general knowledge; zero paywalled fetches (scope rule unused). P42's in-corpus home is expected at L10 (Assmus-Mattson); see the honest miss below.

### Verification table

| ID | Verified citation | Corrections vs seed |
|----|------------------|---------------------|
| L1 | Witt, "Die 5-fach transitiven Gruppen von Mathieu", Abh. Math. Sem. Univ. Hamburg 12: 256-264 (1938), DOI 10.1007/BF02948947; companion "Uber Steinersche Systeme", 12: 265-275 (1938), DOI 10.1007/BF02948948 | TITLE pinned; the TWO-PAPER unit recorded (the design construction lives largely in the companion); Semantic Scholar's 1937 variant recorded as citation error |
| L2 | Bruck-Ryser, "The nonexistence of certain finite projective planes", Canad. J. Math. 1(1): 88-93 (1949), DOI 10.4153/CJM-1949-009-2 | AUTHORSHIP corrected: the 1949 paper is Bruck-Ryser; Chowla is the 1950 symmetric-design generalization (Ryser-Chowla); the 88-92 page-range variant recorded as citation error |
| L3 | Hanani, "On some tactical configurations", Canad. J. Math. 15: 702-722 (1963), DOI 10.4153/CJM-1963-069-5 | YEAR corrected 1960 -> 1963 (conflation with Hanani's other CJM papers documented via the Utah CJM toc); DOI pinned |

### Pattern census (sub-chunk 12a)

| P-ID | Fires in | Notes |
|------|----------|-------|
| P41 double-counting & divisibility | L2 (flagship: the origin paper), L3 (genuine: the sufficiency converse), L1 (partial: admissibility checks) | THE DESIGNED-HOME HARVEST: P41 EXITS the silent registry in its origin paper - L2 Bruck-Ryser, the arithmetic-nonexistence move (sum of two squares / quadratic-form solvability forbids existence before any search); the converse already fires in the same sub-chunk - L3 Hanani proves admissibility SUFFICIENT for C[3,2,1], C[4,2,1], C[4,3,1] (the SQS theorem); L1 partial - the divisibility checks precondition Witt's stepwise construction |
| P11 explicit construction | L1 (flagship), L3 | L1: the Witt designs built block-by-block, the groups read off - the corpus's canonical build-the-object design paper; L3: explicit base cases feeding the recursion |
| P4 recurrence / induction | L3, L1 (partial) | L3: the whole existence proof is an induction on v via recursive PBD/hole constructions; L1 partial: stepwise extension S(5,6,12) from S(4,5,11) - the recursive skeleton is present but the blocks are placed by hand |
| P19 rank / linear algebra | L2 | the incidence-matrix identity NN^T = nI + J plus the determinant/quadratic-form integrality argument - the matrix algebra is the engine of the nonexistence theorem; a THIRD BATCH firing for P19 (I, J, now L) |
| P2 double counting | L2 (partial) | the incidence identity is double counting of point pairs - the arithmetic root under L2's P19 engine |
| P25 reduction / encoding | L1 (partial) | the Mathieu groups constructed as the design automorphism groups - combinatorics and group theory carried together; the successive transitive extensions mirror the design extensions |

### Honest hypothesis-test results (sub-chunk 12a's yield)

- L1 P42 MISSED (expected): Witt's route is designs -> groups (the Steiner systems are built explicitly, the groups read off); the words-as-designs engine (code weight classes carrying Steiner structure) is RETROSPECTIVE for Witt - the Golay-code route to the Witt designs is the Assmus-Mattson era. P42's real in-corpus home is L10 (pending). The seed's P42@L1 expectation is recorded as a direction miss, not a miss of the pattern.
- L2 P41 CONFIRMED (expected, flagship origin); the authorship correction (Chowla 1950) does not change the firing.
- L3 P11 AND P4 CONFIRMED (both expected); P41 gains an unplanned GENUINE firing - the sufficiency direction (admissibility implies existence for these families) is the strongest possible form of the birth-certificate pattern.
- L1 P11 confirmed beyond the seed's expectation.

### Lineages recorded for teaching

- L2 -> (Ryser-Chowla 1950) -> the BRC generalization arc; the arithmetic-nonexistence tradition continues into L4 Wilson (divisibility as the existence theory's backbone) - and L8 Keevash is its constructive counterpoint.
- L3 -> L4 Wilson: Hanani's recursive/PBD machinery feeds Wilson's existence theory.
- L1 <- L10 (planned): the Witt designs recovered from the Golay code's weight classes - the P42 engine's flagship arc (Golay -> Witt), retrospective for L1.

### Verification levels statement (12a)

Metadata: web-verified (sources per paper: L1 Springer Nature Link + the Mathieu group reference list; L2 Cambridge Core + the BRC theorem page; L3 Cambridge Core + the Hanani publication list + the Utah CJM toc). Moves: flagged-sketch summaries (L3's abstract partly quoted). Zero full-text fetches. Open records located: L2 and L3 Cambridge Core pages; L1 Springer record paywalled with standard textbook treatments - scope rule unused.

## Sub-chunk 12b (L4-L6) - gathered and mined 2026-10-13

All 3 papers metadata-verified; moves at flagged-sketch level from publisher/repository records, the open Osaka-U first-page PDF (L5), and standard survey material; zero paywalled fetches. HEADLINE: CAND-A2's ORIGIN paper lands (L6) - the nibble is born here; P41's continuation fires at L4 - divisibility becomes the WHOLE story of design existence. AND a corpus fact: L5 is a CONFIRMED DUPLICATE of I3.

### Verification table

| ID | Verified citation | Corrections vs seed |
|----|------------------|---------------------|
| L4 | Wilson, "An existence theory for pairwise balanced designs": I. "Composition theorems and morphisms", JCTA 13: 220-245 (1972); II. "The structure of PBD-closed sets and the existence conjectures", JCTA 13: 246-273 (1972); III. "Proof of the existence conjectures", JCTA 18 (1975) | VENUE corrected: Ann. Mat. Pura Appl. (seed) -> J. Combin. Theory Ser. A; the THREE-PART unit recorded with part titles pinned (ScienceDirect records + the designtheory.org encyclopedia); part III volume/pages not independently pinned (1975 via the ScienceDirect pii) |
| L5 | Ray-Chaudhuri-Wilson, "On t-designs", Osaka J. Math. 12(3) (1975), ProjectEuclid ojm/1200758175, MR 0392624; open PDF at the Osaka-U repository | YEAR corrected 1971 -> 1975; CONFIRMED DUPLICATE of I3 (the seed's own verify-vs-I3 instruction executed) - corpus distinct count 126 -> 125, flagged for synthesis |
| L6 | Rodl, "On a packing and covering problem", European J. Combin. 6 (1985), ScienceDirect S0195669885800238 | Title/venue CONFIRMED as seeded; pages not pinned (standard citations 69-78; companion Frankl-Rodl 6: 317-326 pinned via citing papers); the Erdos-Hanani source pinned (Publ. Math. Debrecen 10 (1963) 10-13) |

### Pattern census (sub-chunk 12b)

| P-ID | Fires in | Notes |
|------|----------|-------|
| P41 double-counting & divisibility | L4 (genuine: the existence conjecture itself) | the continuation: Wilson's theorem makes divisibility the WHOLE story asymptotically - for a fixed block-size set K, the necessary congruence conditions are sufficient for all large v; the birth-certificate pattern (L2 nonexistence, L3 fixed-family sufficiency) grows into an asymptotic COMPLETENESS theorem |
| P11 explicit construction | L4 (flagship) | Wilson's fundamental construction + ingredient designs + morphisms between PBD-closed sets - the composition machinery is design theory's constructive backbone; expected and confirmed |
| P12 random construction | L6 (flagship: the nibble's origin) | the semi-random nibble born here - a packing built in small random greedy steps with quasi-uniformity tracked across steps; the Erdos-Hanani conjecture proved asymptotically |
| P10 averaging / expectation | L6 (partial) | the second-moment/equidistribution estimates that keep each nibble near-uniform - the averaging engine does the maintenance work inside the P12 flagship |
| CAND-A2 semi-random nibble + parameter tracking (candidate) | L6 (ORIGIN firing) | third batch: A6/A8, B4, now L6 - the candidate's name descends literally from this paper's method; the nibble is the strongest P43+ candidate evidence to date with a NAMED origin |

### Honest hypothesis-test results (sub-chunk 12b's yield)

- L4 P24 MISSED (expected): the seed's shadow expectation was direction-wrong - Wilson's existence theory contains no Kruskal-Katona pricing; the backbone is P41 divisibility with P11 constructions.
- L4 P11 CONFIRMED (expected); P41 CONTINUATION CONFIRMED (per the 12a lineage plan - the sufficiency direction generalizes L3 from fixed families to all PBD-closed K).
- L4 P4: partial only - the recursive machinery is inherited from Hanani (L3) and lives inside the composition theorems; the headline proof's engine is elementary number theory (finite basis for PBD-closed sets), which matches NO Atlas pattern - recorded as a genuine coverage gap for synthesis.
- L5: no gather miss - a corpus fact: L5 == I3 (duplicate confirmed; seed year 1971 -> 1975). P19 credit stays at I3 (no double credit); the L-batch "P19 at RCW" expectation is satisfied by the same paper's I3 firing.
- L6 P12 CONFIRMED (expected); CAND-A2 origin firing CONFIRMED (the third-batch test passed); P10 partial (unplanned).

### Lineages recorded for teaching

- L3 -> L4 confirmed: Hanani's recursive machinery feeds Wilson's composition theorems (12a's plan, now landed).
- L4 -> L8 (planned, 12c): Wilson's deterministic-asymptotic existence vs Keevash's randomized algebraic construction - the modern counterpart arc.
- A6 -> L6 -> L9: the semi-random arc - Ajtai-Komlos-Szemeredi 1981 (independent sets in triangle-free graphs, the ancestor), Rodl 1985 (the nibble born), Pippenger-Spencer (the formalization, 12c). Spencer's branching-process alternative proof of Erdos-Hanani noted as an engine-contrast lineage.
- Erdos-Hanani 1963 -> L6: the 22-year conjecture-to-proof arc; the counting bound C(v,t)/C(k,t) is the "trivial optimum" the field spent two decades reaching.

### Verification levels statement (12b)

Metadata: web-verified (sources per paper: L4 ScienceDirect records for all three parts + the designtheory.org PBD encyclopedia; L5 ProjectEuclid + MathSciNet MR + the Osaka-U repository first-page PDF; L6 ScienceDirect + the Oxford nibble survey notes + citing papers arXiv math/9511224 and West's Illinois page). Moves: flagged-sketch summaries (L5's first page partly quoted). Zero full-text fetches. Page-range honesty: L4-III, L5, L6 page ranges NOT independently pinned and recorded as such (never guessed).

## Sub-chunk 12c (L7-L9) - gathered and mined 2026-10-13

All 3 papers metadata-verified; moves at flagged-sketch level from publisher/author/arXiv records and standard survey material; zero paywalled fetches. HEADLINES: the SEMI-RANDOM ARC IS COMPLETE (A6 -> L6 origin -> L9 formalization -> L8 application) - CAND-A2 is now the survey's strongest P43+ case; P41's continuation lands a second time at L8 (the Existence Conjecture: divisibility is the whole story for Steiner systems); TWO new WATCH items open at the L8 origin (absorption; randomized algebraic construction).

### Verification table

| ID | Verified citation | Corrections vs seed |
|----|------------------|---------------------|
| L7 | Teirlinck, "Non-trivial t-designs without repeated blocks exist for all t", Discrete Math. 65(3): 301-311 (1987), DOI 10.1016/0012-365X(87)90061-6 | TITLE pinned (adds "without repeated blocks"; hyphenation "Non-trivial"); venue CONFIRMED; DOI pinned |
| L8 | Keevash, "The existence of designs", arXiv:1401.3665 (v1 Jan 2014; v3 2024 on the arXiv record); Bourbaki text 1100 "DESIGNS EXIST!" (June 2015) | Journal version NOT PINNED - the seed's "J. Amer. Math. Soc." UNCONFIRMED, recorded honestly (the paper is widely cited as the arXiv, e.g. by the 2024 short-proof paper); arXiv ID and dates pinned |
| L9 | Pippenger-Spencer, "Asymptotic behavior of the chromatic index for hypergraphs", JCTA 51(1): 24-42 (1989), DOI 10.1016/0097-3165(89)90074-5 | VENUE corrected: Ser. B (seed) -> Ser. A; title confirmed ("behavior" spelling pinned); DOI pinned |

### Pattern census (sub-chunk 12c)

| P-ID | Fires in | Notes |
|------|----------|-------|
| P11 explicit construction | L7 (flagship) | Teirlinck's explicit recursive scheme builds non-trivial SIMPLE t-designs for every t - pure build-the-object work, zero asymptotic counting; the all-t existence question settled constructively a generation before Keevash's Steiner-system theorem |
| P4 recurrence + induction | L7 (partial) | the construction reduces t to t-1 recursively (large-set-style machinery), but the placement is explicit handwork - partial as at L1 |
| P41 double-counting & divisibility | L8 (genuine: the Existence Conjecture's statement) | the Keevash continuation: for fixed t,k the necessary divisibility conditions are sufficient for large n (Steiner systems, lambda=1, ALL t) - the exact lambda=1 analogue of Wilson's theorem; the 19th-century existence problem settled with divisibility as the whole story |
| P12 random construction | L8, L9 (flagships) | L9: the nibble FORMALIZED - the Pippenger-Spencer parameter-tracking framework is the canonical "nibble lemma" (near-regular small-codegree hypergraphs have chromatic index asymptotic to the degree). L8: the nibble as workhorse inside the randomized-algebraic designs proof |
| CAND-A2 semi-random nibble (candidate) | L9 (the formalization), L8 (the application) | FOURTH/FIFTH batches: A6/A8, B4, L6 (origin, 12b), now L9 (parameter tracking made explicit and general - the method itself) and L8 (the nibble inside the designs proof). The candidate's arc is complete in-corpus: origin -> formalization -> application |
| WATCH absorption (new) | L8 (ORIGIN firing) | the template absorbs the nibble's leftovers via pre-arranged local trades - single batch so far; external descendants confirm load-bearing status (Glock-Kuhn-Lo-Osthus iterative absorption, Mem. AMS 284 (2023); the 2024 short proof) |
| WATCH randomized algebraic construction (new) | L8 (ORIGIN firing) | choose the random object from an algebraically structured family (random linear maps over finite fields) so the template carries guaranteed trade properties - the seed's own expected candidate at L8, executed honestly; single batch so far |

### Honest hypothesis-test results (sub-chunk 12c's yield)

- L7 P11 CONFIRMED (expected); P4 partial confirmed; and an honest NEGATIVE: P41 does NOT fire at L7 - Teirlinck's lambda is free, so the divisibility story is bypassed, not violated; the P41 arc runs Wilson (L4) -> Keevash (L8), with Teirlinck on a different axis (all t, unbounded lambda).
- L8 P30 MISSED (expected by seed; direction-wrong): no regularity partition is load-bearing; the counting is handled by template + nibble + absorption. P41 CONTINUATION CONFIRMED (the Existence Conjecture's statement); P12 CONFIRMED; CAND-A2 application firing; TWO new WATCH items opened (absorption; randomized algebraic construction) - the seed's own "candidate: randomized algebraic construction" expectation executed honestly. P22 NOT credited (finite-field linear algebra, not the polynomial method - recorded under the WATCH item).
- L9 P12 CONFIRMED (expected); CAND-A2's FORMALIZATION test PASSED (fourth batch); venue correction Ser. B -> Ser. A logged.

### Lineages recorded for teaching

- The SEMI-RANDOM ARC, complete: Ajtai-Komlos-Szemeredi 1981 (A6, the ancestor) -> Rodl 1985 (L6, the nibble born) -> Pippenger-Spencer 1989 (L9, formalized) -> Keevash 2014 (L8, the application to designs). Three sub-chunks of one batch close the method's origin story - the survey's cleanest engine lineage.
- The EXISTENCE-SPECTRUM arc: Hanani L3 (small t, exact) -> Wilson L4 (fixed K, t=2, large v) -> Teirlinck L7 (all t, unbounded lambda) -> Keevash L8 (Steiner systems, all admissible large v). The 19th-century problem (per the AMS memoir's framing) ends with divisibility as the whole story.
- Frankl-Rodl 1985 (the 12b companion record) -> L9: the single almost-perfect packing generalized to chromatic index.
- L4 -> L8 engine contrast INSIDE the batch: Wilson's deterministic-asymptotic number theory vs Keevash's randomized-algebraic + nibble + absorption; and the Glock-Kuhn-Lo-Osthus memoir (Mem. AMS 284 (2023)) gives the pure-absorption alternative proof - an engine-contrast pair inside one theorem.

### Verification levels statement (12c)

Metadata: web-verified (sources per paper: L7 ScienceDirect + dblp; L8 arXiv abstract page + the author's Oxford page + the Bourbaki text 1100 + the Aperiodical Proof News post; L9 ScienceDirect + NYU Scholars + the Harvey Mudd scholarship record). Moves: flagged-sketch summaries. Zero full-text fetches. Honesty record: L8's journal version unpinned (recorded, never guessed); L7/L9 fully pinned with DOIs.

(Sub-chunk 12d extends this file at its own close.)
