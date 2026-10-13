# Batch L - Designs, packing and codes (gathered and mined; work style v2)

Chunk 12 under work style v2: four sub-chunks of three papers, each pushed as its own commit. This file is created at sub-chunk 12a and extended at every sub-chunk close. Designed home of the silent P41 (divisibility) and P42 (words-as-designs).

| Sub-chunk | Papers | Status |
|-----------|--------|--------|
| 12a | L1 Witt; L2 Bruck-Ryser; L3 Hanani | DONE (sections below) |
| 12b | L4 Wilson; L5 Ray-Chaudhuri-Wilson; L6 Rodl | DONE (sections below) |
| 12c | L7 Teirlinck; L8 Keevash; L9 Pippenger-Spencer | PENDING |
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

(Sub-chunks 12c-12d extend this file at their own closes.)
