# Batch A - The probabilistic method and random graphs (gathered and mined)

Session chunk 1, 2026-10-13. All 9 papers metadata-verified against web sources; proof-move descriptions are honest summaries at flagged-sketch level (general knowledge plus publisher abstracts where open); no paywalled full texts were fetched - the scope rule fired zero times because every candidate pattern already has abundant open documentation.

## Verification table

| ID | Verified citation | Corrections vs seed |
|----|------------------|---------------------|
| A1 | Erdos, Bull. Amer. Math. Soc. 53(4): 292-294 (1947) | none |
| A2 | Erdos-Renyi, Publ. Math. Debrecen 6(3-4): 290-297 (1959), DOI 10.5486/PMD.1959.6.3-4.12 | Gilbert G(n,p) provenance note added |
| A3 | Erdos-Renyi, Magyar Tud. Akad. Mat. Kut. Int. Kozl. 5: 17-61 (1960); free PDF at renyi.hu | none |
| A4 | Erdos, Canad. J. Math. 11: 34-38 (1959), DOI 10.4153/CJM-1959-003-9 | YEAR corrected 1961 to 1959; 1961 sequel noted |
| A5 | Erdos-Lovasz, in Infinite and Finite Sets, Colloq. Math. Soc. Janos Bolyai 10, 609-627 (1975) | none |
| A6 | Ajtai-Komlos-Szemeredi, J. Combin. Theory Ser. A 29(3): 354-360 (1980), DOI 10.1016/0097-3165(80)90030-8 | VENUE corrected JCTB-1981 to JCT-A 1980 |
| A7 | Shearer, Discrete Mathematics 46: 83-87 (1983), DOI 10.1016/0012-365X(83)90273-X | VENUE corrected JCTB to Discrete Math. 46; 1991 sequel noted |
| A8 | Kim, Random Structures and Algorithms 7(3): 173-207 (1995); Fulkerson Prize 1997 | VENUE corrected JAMS to RSA |
| A9 | Moser-Tardos, J. ACM 57(2), Art. 11 (2010); arXiv:0903.0544 | none |

## Pattern census (Atlas P-IDs firing in this batch)

| P-ID | Fires in | Notes |
|------|----------|-------|
| P12 random construction | A1, A2, A3, A4, A6, A8 | the batch's dominant move, as hypothesized |
| P13 union bound | A1 | and the degenerate special case of the LLL (A5, A9) |
| P10 averaging/expectation | A2, A3, A4, A6, A7, A8 | |
| P14 alteration | A4, A6, A8 | A4 is the alteration's canonical debut - confirmed |
| P4 recurrence + induction | A5, A7, A8 (process bookkeeping) | |
| P18 algorithmic proof | A9 | the resampling proof IS the algorithm |
| P11 explicit construction | A8 (dense triangle-free graph with small alpha) | |
| P9 pigeonhole | A1 (the framing being departed from) | |

Hypothesis scorecard: the seed's expected-patterns column was confirmed for all 9 papers; no expected tag was overturned. The atlas P-index holds up completely on its home turf.

## New-pattern candidates (each needs fire-across-2-batches evidence to enter ANALYSIS.md)

1. CAND-A1 - THE LOVASZ LOCAL LEMMA. Shape: many bad events, each rare and near-independent of most others; Move: 4pd <= 1 (or asymmetric x-certificates) implies positive probability that none occur; a strict strengthening of P13 in the sparse-dependency regime. Evidence: A5 (debut), A7 (Shearer lineage = the optimal threshold), A9 (algorithmization; Godel Prize 2020). HEADLINE FINDING of this batch: no P-ID in P1-P42 names this move - P13 covers only the union bound. Cross-batch test: B9 (Johansson occupancy), B7/B8 (containers vs LLL), L batch (nibble LLL usage). This is the survey's leading P43 candidate so far.
2. CAND-A2 - SEMI-RANDOM/NIBBLE CONSTRUCTION WITH PARAMETER TRACKING. Shape: build the object by a controlled adaptive random process, tracking densities by potential functions/differential equations, then alter. Evidence: A8 (Kim; ancestor A6). Distinct from P12 because the process is adaptive. Cross-batch test: L6 (Rodl nibble), L9 (Pippenger-Spencer).
3. CAND-A3 - THRESHOLD/WINDOW PHENOMENON. Shape: a property's probability flips in a narrow window; the window is the theorem. Evidence: A2, A3 (early instances). Cross-batch test: B3 (Friedgut-Kalai sharp thresholds), B5/B6 (Kahn-Kalai, Park-Pham).
4. CAND-A4 - ENTROPY COMPRESSION. Shape: long executions of an algorithm would compress randomness below entropy, contradiction. Evidence: A9 only. Demotion candidate unless Batches D/M surface it.

## Verification levels statement

Metadata: web-verified (sources recorded per paper). Proof moves: flagged-sketch-level summaries from general knowledge and open abstracts; no claim here reaches executed-lab or complete-proof level. Open full texts located but not fetched: A1 (ams.org), A3 (renyi.hu), A8 (course copy), A9 (arXiv). Scope rule usage: zero fetches needed.
