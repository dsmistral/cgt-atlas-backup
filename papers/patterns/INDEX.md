# Pattern index (through chunk 13c)

Status wording is abbreviated here; the per-pattern files are authoritative. 'Census batches' = batches whose pattern census records a firing (partials included).

| P-ID | Pattern | Family | Census batches |
|------|---------|--------|----------------|
| P1 | Bijection | 01-counting | C |
| P2 | Double counting | 01-counting | H, L |
| P3 | Inclusion-exclusion | 01-counting | - |
| P4 | Recurrence + induction | 02-induction-extremal | A, C, D, F, G, H, I, L, M |
| P5 | Generating function | 04-analytic-information | C, E |
| P6 | Complement / reflection | 01-counting | - |
| P7 | Parity & handshaking | 01-counting | D |
| P8 | Longest-path / extremal | 02-induction-extremal | D, E, F, H, I |
| P9 | Pigeonhole | 01-counting | A, F, G, H, I, K |
| P10 | Averaging / expectation | 03-probability | A, B, D, G, H, I, K, L |
| P11 | Explicit construction | 05-construction-algorithms | A, E, G, I, J, L |
| P12 | Random construction | 03-probability | A, B, D, F, H, L |
| P13 | Union bound | 03-probability | A |
| P14 | Alteration | 03-probability | A |
| P15 | Induction on vertices/edges | 02-induction-extremal | E, H, I, J |
| P16 | Alternating paths / augmentation | 06-duality-optimization | D, E |
| P17 | Duality (min-max) | 06-duality-optimization | D |
| P18 | Algorithmic proof | 05-construction-algorithms | A, D, E, G, M |
| P19 | Rank / linear algebra | 07-linear-algebra-polynomial | C, F, I, J, L, M |
| P20 | Weight shifting / symmetrization | 08-canonicalization | E |
| P21 | Spectral / Rayleigh | 07-linear-algebra-polynomial | J |
| P22 | Polynomial method | 07-linear-algebra-polynomial | I |
| P23 | Compression / shifting | 08-canonicalization | I, K |
| P24 | Shadow pricing (Kruskal-Katona) | 08-canonicalization | K |
| P25 | Reduction / encoding | 05-construction-algorithms | B, D, E, F, G, H, L, M |
| P26 | Compactness (finite vs infinite) | 02-induction-extremal | F |
| P27 | Correlation | 03-probability | - |
| P28 | Concentration | 03-probability | B |
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
| CAND-A1 Lovasz Local Lemma | CROSSED | A, B |
| CAND-A2 semi-random nibble | CROSSED + origin L6 + formalization L9 + application L8 (12c) - strongest P43+ case | A, B, L |
| CAND-A3 threshold/window | CROSSED | A, B |
| CAND-A4 entropy compression | NOT crossed - NO firing in M (13a-13c scanned); final in-corpus verdict; synthesis decides on the B9 external lineage | A (+ B9 lineage) |
| CAND-B5 hypergraph containers | synthesis call | B |
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

Ledger note: P39 carries a FLAGGED LEDGER DISCREPANCY (batch-C census fires it at C1/C7; the running STATE.md silent-registry ledger never recorded its exit) - reconcile at synthesis.

12a note (2026-10-13): P41 exited the silent registry (L2 flagship origin / L3 sufficiency converse / L1 partial). P42's designed-home expectation L1 MISSED (the words-as-designs engine is retrospective for Witt; real home L10, pending). See the dossiers and BATCH-L.md.

12b note (2026-10-13): CAND-A2 origin paper landed - L6 Rodl (the nibble born; third batch A/B/L). P41 continuation at L4 (the existence conjecture: divisibility is the whole story asymptotically); P11 flagship at L4; P12 flagship at L6 with a P10 partial. L5 CONFIRMED DUPLICATE of I3 (year corrected 1971 -> 1975; corpus distinct count 126 -> 125 - synthesis flag). L4 P24 MISSED (seed direction-wrong). See the dossiers and BATCH-L.md.

12c note (2026-10-13): the semi-random arc COMPLETE - CAND-A2 origin (L6) + formalization (L9 Pippenger-Spencer, venue corrected Ser. B -> Ser. A) + application (L8 Keevash); promotion to P43+ recommended at synthesis. P41 continuation at L8 (the Existence Conjecture); P11 flagship + P4 partial at L7 Teirlinck (title pinned; venue confirmed). TWO new WATCH items opened at the L8 origin: absorption; randomized algebraic construction (the seed's own candidate expectation executed). Honest misses: L8 P30 (no regularity partition load-bearing); honest negative: L7 P41 (lambda free). See the dossiers and BATCH-L.md.

12d note (2026-10-13) - BATCH L COMPLETE: P42 EXITS the silent registry at its designed home L10 (Assmus-Mattson - the origin paper: few dual weights => each weight class carries a t-design; the Golay code's weight classes recover the Witt designs; the 12a L1 miss vindicated). P19 fourth-batch firing at L11 MacWilliams (genuine), partials at L10/L12. Honest miss: L12 P40 (engine = classical invariant theory - a coverage gap for synthesis). Silent registry after Batch L: P27, P35, P36 (+ P20 under-used). See the dossiers and BATCH-L.md.

13a note (2026-10-13): the isomorphism column M1 -> M2 fires ONE engine twice (the Luks framework: permutation-group recursion on bounded simple sections) - opened as a WATCH item because it matches NO Atlas pattern (a coverage-gap engine with two in-corpus firings in one sub-chunk). THREE more honest seed misses logged: M1 P19 (group theory, not rank bounds) and M2 P8 AND P30 (the Design Lemma's split-or-Johnson dichotomy, not extremal analysis or regularity partitions). M3 opens the flag-algebras WATCH at its origin, with the M4 second-batch test pending (13b). P25 fires in all three papers; P18 twice; P4 (M1 partial, M2 genuine); P19/P37 partials at M3 (the Delsarte-LP lineage's density-era descendant). See the dossiers and BATCH-M.md.

13b note (2026-10-13): P30's designed watch-M firing LANDS - M5 Alon-Shapira (genuine) + M6 AFNS (flagship; the subtitle IS the pattern: "It's all about regularity"; SIAM J. Comput. 39(1): 143-167 (2009)). The flag-algebras WATCH fires a second time at M4 (Razborov's triangle-density theorem; venue corrected Algebra i Analiz -> CP&C 17(4): 603-618 (2008)) - both firings within batch M; the cross-batch test cannot be satisfied in-corpus (synthesis call mirrors CAND-B5). P18 fires twice more (the testers ARE the procedures); P25 three times (M4 genuine; M5/M6 partials); P19/P37 repeat their M3 partial faces at M4. CAND-A4 / Boolean influence / spread induction: not fired; final chance 13c. See the dossiers and BATCH-M.md.

13c note (2026-10-13) - BATCH M COMPLETE: P35 records its FIRST in-corpus touch (M9 Grohe, partial - DP over tree decompositions on the tractability side; standard-tool credit; the registry entry stays open). M7 Hopcroft-Tarjan (J. ACM 21(4):549-568 (1974)) fires P18 flagship + P25 partial (the DFS/path encoding); M8 Kruskal (PAMS 7(1):48-50 (1956); full title pinned) fires P18 genuine, with the greedy-exchange engine recorded as a coverage observation; M9 Grohe (title corrected: "seen from the other side" added; J. ACM 54(1) Art. 1 (2007)) fires P25 genuine. FINAL WATCH-M VERDICTS: CAND-A4 entropy compression NOT fired in M - the gate stays uncrossed (synthesis decides on the B9 lineage); Boolean influence and spread induction NOT fired in M - synthesis calls on B3/B6 alone. The batch's grand contrast recorded for synthesis: isomorphism by symmetry (M1/M2) vs homomorphism by structure (M9). See the dossiers and BATCH-M.md.
