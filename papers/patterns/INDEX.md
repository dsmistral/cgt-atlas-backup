# Pattern index (through chunk 12c)

Status wording is abbreviated here; the per-pattern files are authoritative. 'Census batches' = batches whose pattern census records a firing (partials included).

| P-ID | Pattern | Family | Census batches |
|------|---------|--------|----------------|
| P1 | Bijection | 01-counting | C |
| P2 | Double counting | 01-counting | H, L |
| P3 | Inclusion-exclusion | 01-counting | - |
| P4 | Recurrence + induction | 02-induction-extremal | A, C, D, F, G, H, I, L |
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
| P18 | Algorithmic proof | 05-construction-algorithms | A, D, E, G |
| P19 | Rank / linear algebra | 07-linear-algebra-polynomial | C, F, I, J, L |
| P20 | Weight shifting / symmetrization | 08-canonicalization | E |
| P21 | Spectral / Rayleigh | 07-linear-algebra-polynomial | J |
| P22 | Polynomial method | 07-linear-algebra-polynomial | I |
| P23 | Compression / shifting | 08-canonicalization | I, K |
| P24 | Shadow pricing (Kruskal-Katona) | 08-canonicalization | K |
| P25 | Reduction / encoding | 05-construction-algorithms | B, D, E, F, G, H, L |
| P26 | Compactness (finite vs infinite) | 02-induction-extremal | F |
| P27 | Correlation | 03-probability | - |
| P28 | Concentration | 03-probability | B |
| P29 | Entropy counting | 04-analytic-information | B |
| P30 | Regularity partitioning | 09-density-structure | F, G |
| P31 | Counting-removal | 09-density-structure | G |
| P32 | Stability | 08-canonicalization | G |
| P33 | Density increment | 09-density-structure | F |
| P34 | Minor chasing | 10-graph-structure | E, H |
| P35 | Dynamic programming on structure | 10-graph-structure | - |
| P36 | Discharging | 10-graph-structure | - |
| P37 | Duality | 06-duality-optimization | E, H, I, J |
| P38 | Replication | 10-graph-structure | H |
| P39 | Symmetry averaging | 11-symmetry-designs-codes | C |
| P40 | Mobius inversion | 11-symmetry-designs-codes | C |
| P41 | Double-counting & divisibility | 11-symmetry-designs-codes | L |
| P42 | Words-as-designs | 11-symmetry-designs-codes | - |

## Candidates and watch-items

| Item | Gate status | Batches |
|------|-------------|---------|
| CAND-A1 Lovasz Local Lemma | CROSSED | A, B |
| CAND-A2 semi-random nibble | CROSSED + origin L6 + formalization L9 + application L8 (12c) - strongest P43+ case | A, B, L |
| CAND-A3 threshold/window | CROSSED | A, B |
| CAND-A4 entropy compression | NOT crossed - watch M | A (+ B9 lineage) |
| CAND-B5 hypergraph containers | synthesis call | B |
| CAND-C1 analytic combinatorics | synthesis call | C |
| CAND-G1 transference/dense-model | synthesis call | G |
| WATCH Boolean influence | watch M | B |
| WATCH spread induction | watch M | B |
| WATCH sign-reversing involution | synthesis call | C |
| WATCH Kempe-chain recoloring | likely dies at synthesis | E |
| WATCH monovariant/potential | synthesis call | D, G |
| WATCH slice rank | synthesis call (face of P19/P22) | I |
| WATCH absorption | WATCH - L8 origin (12c), needs 2nd batch | L |
| WATCH randomized algebraic construction | WATCH - L8 origin (12c), needs 2nd batch | L |

Ledger note: P39 carries a FLAGGED LEDGER DISCREPANCY (batch-C census fires it at C1/C7; the running STATE.md silent-registry ledger never recorded its exit) - reconcile at synthesis.

12a note (2026-10-13): P41 exited the silent registry (L2 flagship origin / L3 sufficiency converse / L1 partial). P42's designed-home expectation L1 MISSED (the words-as-designs engine is retrospective for Witt; real home L10, pending). See the dossiers and BATCH-L.md.

12b note (2026-10-13): CAND-A2 origin paper landed - L6 Rodl (the nibble born; third batch A/B/L). P41 continuation at L4 (the existence conjecture: divisibility is the whole story asymptotically); P11 flagship at L4; P12 flagship at L6 with a P10 partial. L5 CONFIRMED DUPLICATE of I3 (year corrected 1971 -> 1975; corpus distinct count 126 -> 125 - synthesis flag). L4 P24 MISSED (seed direction-wrong). See the dossiers and BATCH-L.md.

12c note (2026-10-13): the semi-random arc COMPLETE - CAND-A2 origin (L6) + formalization (L9 Pippenger-Spencer, venue corrected Ser. B -> Ser. A) + application (L8 Keevash); promotion to P43+ recommended at synthesis. P41 continuation at L8 (the Existence Conjecture); P11 flagship + P4 partial at L7 Teirlinck (title pinned; venue confirmed). TWO new WATCH items opened at the L8 origin: absorption; randomized algebraic construction (the seed's own candidate expectation executed). Honest misses: L8 P30 (no regularity partition load-bearing); honest negative: L7 P41 (lambda free). See the dossiers and BATCH-L.md.
