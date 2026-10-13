# Pattern index (through chunk 18 - Batch P, extension corpus)

Status wording is abbreviated here; the per-pattern files are authoritative. 'Census batches' = batches whose pattern census records a firing (partials included).

| P-ID | Pattern | Family | Census batches |
|------|---------|--------|----------------|
| P1 | Bijection | 01-counting | C, N |
| P2 | Double counting | 01-counting | H, L, N |
| P3 | Inclusion-exclusion | 01-counting | N (first firing) |
| P4 | Recurrence + induction | 02-induction-extremal | A, C, D, F, G, H, I, L, M, N |
| P5 | Generating function | 04-analytic-information | C, E |
| P6 | Complement / reflection | 01-counting | - |
| P7 | Parity & handshaking | 01-counting | D, N |
| P8 | Longest-path / extremal | 02-induction-extremal | D, E, F, H, I |
| P9 | Pigeonhole | 01-counting | A, F, G, H, I, K, N |
| P10 | Averaging / expectation | 03-probability | A, B, D, G, H, I, K, L, N, P |
| P11 | Explicit construction | 05-construction-algorithms | A, E, G, I, J, L |
| P12 | Random construction | 03-probability | A, B, D, F, H, L, O |
| P13 | Union bound | 03-probability | A, N |
| P14 | Alteration | 03-probability | A |
| P15 | Induction on vertices/edges | 02-induction-extremal | E, H, I, J |
| P16 | Alternating paths / augmentation | 06-duality-optimization | D, E |
| P17 | Duality (min-max) | 06-duality-optimization | D |
| P18 | Algorithmic proof | 05-construction-algorithms | A, D, E, G, M, N, O |
| P19 | Rank / linear algebra | 07-linear-algebra-polynomial | C, F, I, J, L, M |
| P20 | Weight shifting / symmetrization | 08-canonicalization | E |
| P21 | Spectral / Rayleigh | 07-linear-algebra-polynomial | J |
| P22 | Polynomial method | 07-linear-algebra-polynomial | I |
| P23 | Compression / shifting | 08-canonicalization | I, K |
| P24 | Shadow pricing (Kruskal-Katona) | 08-canonicalization | K |
| P25 | Reduction / encoding | 05-construction-algorithms | B, D, E, F, G, H, L, M, N, O, P |
| P26 | Compactness (finite vs infinite) | 02-induction-extremal | F |
| P27 | Correlation | 03-probability | O (first touch, partial - dependency-graph face; the FKG face test moves to Batch U) |
| P28 | Concentration | 03-probability | B, N |
| P29 | Entropy counting | 04-analytic-information | B |
| P30 | Regularity partitioning | 09-density-structure | F, G, M |
| P31 | Counting-removal | 09-density-structure | G |
| P32 | Stability | 08-canonicalization | G |
| P33 | Density increment | 09-density-structure | F |
| P34 | Minor chasing | 10-graph-structure | E, H |
| P35 | Dynamic programming on structure | 10-graph-structure | M (partial touch) |
| P36 | Discharging | 10-graph-structure | - |
| P37 | Duality | 06-duality-optimization | E, H, I, J, M |
| P38 | Replication | 10-graph-structure | H |
| P39 | Symmetry averaging | 11-symmetry-designs-codes | C |
| P40 | Mobius inversion | 11-symmetry-designs-codes | C |
| P41 | Double-counting & divisibility | 11-symmetry-designs-codes | L |
| P42 | Words-as-designs | 11-symmetry-designs-codes | L |

## Candidates and watch-items

| Item | Gate status | Batches |
|------|-------------|---------|
| CAND-A1 Lovasz Local Lemma | CROSSED; external arc gathered and COMPLETE (chunk 17) - recommendation strengthened | A, B, O |
| CAND-A2 semi-random nibble | CROSSED + origin L6 + formalization L9 + application L8 (12c) - strongest P43+ case | A, B, L |
| CAND-A3 threshold/window | CROSSED | A, B |
| CAND-A4 entropy compression | NOT crossed in-corpus (final verdict); ORIGIN FIRING found in the extension corpus (O4 Moser 2009, the debut) | A, O (origin) (+ B9/Molloy-2019 lineage) |
| CAND-B5 hypergraph containers | CROSSED in the extension corpus (chunk 18: the P1 origin + P2 bridge + P3/P4 flagships; batches B + P) - promotion to the user-approved Atlas session | B, P |
| CAND-C1 analytic combinatorics | synthesis call | C |
| CAND-G1 transference/dense-model | synthesis call | G |
| WATCH Boolean influence | no firing in M; synthesis call on B3 alone | B |
| WATCH spread induction | no firing in M; synthesis call on B6 alone | B |
| WATCH sign-reversing involution | synthesis call | C |
| WATCH Kempe-chain recoloring | likely dies at synthesis | E |
| WATCH monovariant/potential | synthesis call | D, G |
| WATCH slice rank | synthesis call (face of P19/P22) | I |
| WATCH absorption | WATCH - L8 origin (12c), needs 2nd batch | L |
| WATCH randomized algebraic construction | WATCH - L8 origin (12c), needs 2nd batch | L |
| WATCH flag algebras | WATCH - M3 origin + M4 second firing, both within batch M; cross-batch test impossible in-corpus - synthesis call (mirrors CAND-B5 precedent) | M |
| WATCH Luks-framework group recursion | WATCH - M1 origin + M2 second firing (13a); NO Atlas P-ID (coverage-gap engine) | M |

Ledger note (RECONCILED at chunk 15, 2026-10-13): P39 exited the silent registry at batch C (C1/C7); the STATE.md ledger omission was migration-era bookkeeping - see the P39 dossier and papers/ANALYSIS.md section 3.

12a note (2026-10-13): P41 exited the silent registry (L2 flagship origin / L3 sufficiency converse / L1 partial). P42's designed-home expectation L1 MISSED (the words-as-designs engine is retrospective for Witt; real home L10, pending). See the dossiers and BATCH-L.md.

12b note (2026-10-13): CAND-A2 origin paper landed - L6 Rodl (the nibble born; third batch A/B/L). P41 continuation at L4 (the existence conjecture: divisibility is the whole story asymptotically); P11 flagship at L4; P12 flagship at L6 with a P10 partial. L5 CONFIRMED DUPLICATE of I3 (year corrected 1971 -> 1975; corpus distinct count 126 -> 125 - synthesis flag). L4 P24 MISSED (seed direction-wrong). See the dossiers and BATCH-L.md.

12c note (2026-10-13): the semi-random arc COMPLETE - CAND-A2 origin (L6) + formalization (L9 Pippenger-Spencer, venue corrected Ser. B -> Ser. A) + application (L8 Keevash); promotion to P43+ recommended at synthesis. P41 continuation at L8 (the Existence Conjecture); P11 flagship + P4 partial at L7 Teirlinck (title pinned; venue confirmed). TWO new WATCH items opened at the L8 origin: absorption; randomized algebraic construction (the seed's own candidate expectation executed). Honest misses: L8 P30 (no regularity partition load-bearing); honest negative: L7 P41 (lambda free). See the dossiers and BATCH-L.md.

12d note (2026-10-13) - BATCH L COMPLETE: P42 EXITS the silent registry at its designed home L10 (Assmus-Mattson - the origin paper: few dual weights => each weight class carries a t-design; the Golay code's weight classes recover the Witt designs; the 12a L1 miss vindicated). P19 fourth-batch firing at L11 MacWilliams (genuine), partials at L10/L12. Honest miss: L12 P40 (engine = classical invariant theory - a coverage gap for synthesis). Silent registry after Batch L: P27, P35, P36 (+ P20 under-used). See the dossiers and BATCH-L.md.

13a note (2026-10-13): the isomorphism column M1 -> M2 fires ONE engine twice (the Luks framework: permutation-group recursion on bounded simple sections) - opened as a WATCH item because it matches NO Atlas pattern (a coverage-gap engine with two in-corpus firings in one sub-chunk). THREE more honest seed misses logged: M1 P19 (group theory, not rank bounds) and M2 P8 AND P30 (the Design Lemma's split-or-Johnson dichotomy, not extremal analysis or regularity partitions). M3 opens the flag-algebras WATCH at its origin, with the M4 second-batch test pending (13b). P25 fires in all three papers; P18 twice; P4 (M1 partial, M2 genuine); P19/P37 partials at M3 (the Delsarte-LP lineage's density-era descendant). See the dossiers and BATCH-M.md.

13b note (2026-10-13): P30's designed watch-M firing LANDS - M5 Alon-Shapira (genuine) + M6 AFNS (flagship; the subtitle IS the pattern: "It's all about regularity"; SIAM J. Comput. 39(1): 143-167 (2009)). The flag-algebras WATCH fires a second time at M4 (Razborov's triangle-density theorem; venue corrected Algebra i Analiz -> CP&C 17(4): 603-618 (2008)) - both firings within batch M; the cross-batch test cannot be satisfied in-corpus (synthesis call mirrors CAND-B5). P18 fires twice more (the testers ARE the procedures); P25 three times (M4 genuine; M5/M6 partials); P19/P37 repeat their M3 partial faces at M4. CAND-A4 / Boolean influence / spread induction: not fired; final chance 13c. See the dossiers and BATCH-M.md.

13c note (2026-10-13) - BATCH M COMPLETE: P35 records its FIRST in-corpus touch (M9 Grohe, partial - DP over tree decompositions on the tractability side; standard-tool credit; the registry entry stays open). M7 Hopcroft-Tarjan (J. ACM 21(4):549-568 (1974)) fires P18 flagship + P25 partial (the DFS/path encoding); M8 Kruskal (PAMS 7(1):48-50 (1956); full title pinned) fires P18 genuine, with the greedy-exchange engine recorded as a coverage observation; M9 Grohe (title corrected: "seen from the other side" added; J. ACM 54(1) Art. 1 (2007)) fires P25 genuine. FINAL WATCH-M VERDICTS: CAND-A4 entropy compression NOT fired in M - the gate stays uncrossed (synthesis decides on the B9 lineage); Boolean influence and spread induction NOT fired in M - synthesis calls on B3/B6 alone. The batch's grand contrast recorded for synthesis: isomorphism by symmetry (M1/M2) vs homomorphism by structure (M9). See the dossiers and BATCH-M.md.

14a note (2026-10-13): Batch N opens (youth-authored ACCEPTED papers; SOURCES.md section 4). P28 fires in its SECOND census batch (N3 Jain-Sah-Sawhney - the sharp binomial small-ball comparison, the Littlewood-Offord lineage's modern face; the K1 engine was the P9 antichain face), and P13 fires in its second batch too (the interior union bound at the sup over A, confirmed against the fetched open PDF). N2 Sah-Sawhney-Stoner-Zhao settles Kahn's conjecture with an accessible skeleton: P25 genuine (Zhao's swapping), P4 genuine unplanned (the freshman-level independent-set recursion at a maximum-degree vertex), P10 partial (the layered Holder verification); HONEST MISS P29 (the proof AVOIDS Kahn's entropy - the convexity face credited under P10 with the Lubetzky-Zhao note) and P9. N1 Jackson-Johnson (the HIGH-SCHOOL pair; the Monthly's lead article) fires NO Atlas P-ID - the designed domain-outlier datum for the accessibility question. Author-level honesty notes: N2 includes the faculty mentor; N3 includes a graduate student. See the dossiers and BATCH-N.md.

14b note (2026-10-13): Batch N's middle-school trio: **P3 fires for the FIRST time in the corpus (N6 - the exact-soulmate inclusion-exclusion, from a PRIMES STEP team in grades 6-9)**; P4 genuine at N4 (the chip-firing paper's spine) and N5 (the soulmate-removal induction); P25 flagship at N5 (the SMP <-> Sudoku translation) and partial at N4 (the base-k digit encoding); P9 genuine at N5 (the key-function pigeonhole); P1 genuine at N6 + partial at N5; P2/P7/P41/P18 partials (N4/N6). Honest misses: P5 at BOTH N4 and N6 (no generating function in either paper - the seed shorthand conflated sequences with GFs), P16 at N5 (no augmentation - the accessibility datum), P23 at N6. Coverage-gap observation for the synthesis: N4's k-adic-valuation digit engine (fractal difference sequences, schizophrenic numbers) matches no Atlas P-ID. See the dossiers and BATCH-N.md.

14c note (2026-10-13) - BATCH N COMPLETE (8/8): N7 Kuszmaul (HIGH SCHOOL, solo; EJC 20(4) Article #P10 (2013) pinned) fires P1 genuine + P4 genuine (unplanned - the class-count recurrences) + P25 partial (the Klein-four orbit reduction; the avoidance connection); honest misses P5 (zero generating functions - the third consecutive youth-paper P5 miss) and P23 (no compression - invariants + recurrences + bijections). N8 reverse Sidorenko (Inventiones 221(2): 665-711 (2020); the same team as N2) fires P25 genuine (the homomorphism encoding), P10 genuine (the graphical Brascamp-Lieb machinery - the Holder lineage as the whole engine; a coverage note: P10's functional-analysis face), P4 genuine (unplanned - the strengthened list-coloring induction); honest misses P30 AND P31 (the Sidorenko problem space without the regularity/removal engine). The batch's accessibility answer for the synthesis: the pre-doctoral canon = P25/P4/P1/P9/P10; P3's debut at grades 6-9; the honest boundary - P5, P16 (augmentation), P23, and P30/P31 never fired in Batch N. See the dossiers and BATCH-N.md.

## Note 15 (chunk 15 - synthesis, 2026-10-13)

THE SYNTHESIS IS DONE: papers/ANALYSIS.md is the survey's final analysis document. PROPOSED P43 = CAND-A2 semi-random nibble with parameter tracking (five batches: A6/A8 ancestors, B4, L6 origin, L9 formalization, L8 application - the strongest load-bearing case). PROPOSED P44 = CAND-A3 threshold/window (A2/A3, B3, B5, B6 - "the window is the theorem"; a phenomenon-pattern in the P26 manner). NOT promoted: CAND-A1 (the B9 flag resolved against - the LLL step lives in the Molloy-Reed expositions; external-canon recommendation), CAND-B5 and CAND-C1 (single-batch; external-evidence recommendations), WATCH flag algebras (RECOMMENDED on external evidence - both firings within batch M; the descendants decide), WATCH absorption and WATCH randomized algebraic construction (external-evidence recommendations). DIES in-corpus: CAND-A4 entropy compression, WATCH Boolean influence, WATCH spread induction, WATCH Kempe chains. FACES, not separate patterns: transference -> P30/P31; slice rank -> P19/P22; sign-reversing involution -> P1; monovariant -> P4. The Luks framework = a coverage-gap engine. Silent ledger FINAL: P27/P36 fully silent (P36 = corpus-sampling gap), P35 partial-touch only (entry open), P20 genuinely under-used, P6 ZERO firings, P39 RECONCILED (exited at batch C). Workhorses: P4 (10 batches), P25 (9), P10 (9), P9 (7). The gate-status table above records the PRE-synthesis state; this note's verdicts are final. Full reasoning and the Atlas recommendations (all pending a user-approved Atlas session): papers/ANALYSIS.md.
## Note 18 (chunk 18 - Batch P, 2026-10-13)

CAND-B5 hypergraph containers CROSSES the two-batch load-bearing gate in the extension corpus: the arc gathered complete - P1 Kleitman-Winston 1982 (the IMPLICIT ORIGIN, survey-level attribution; venue corrected to Discrete Math. 41(2): 167-172) -> B7/B8 (the 2015 general theorems, batch B) -> P2 Samotij 2015 (the expository bridge; EJC 48: 5-18) -> P3 Morris-Saxton 2016 (the even-cycle flagship: Erdos's conjecture confirmed; title/venue corrected to "The number of C_{2l}-free graphs", Adv. Math. 298: 534-580) -> P4 Balogh-Liu-Sharifzadeh-Treglown 2018 (the arithmetic flagship: the Cameron-Erdos maximal question closed sharply; "Sharp bound on the number of maximal sum-free subsets of integers", JEMS 20(8): 1885-1911; Green's container lemma - the ARITHMETIC face, with the companion's Lemma 2.1 derivable from B7/B8). The chunk-15 external-evidence-only recommendation is superseded by the in-survey crossing; the promotion decision belongs to the user-approved Atlas session. Census: P10 genuine at P3 (the balanced supersaturation theorem - the H5 supersaturation face modernized); P25 partials at P1/P2 (the certificate/profile encoding). See papers/BATCH-P.md.
