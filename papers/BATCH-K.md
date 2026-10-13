# Batch K - Shadows, compression, Littlewood-Offord (gathered and mined)

Session chunk 11, 2026-10-13. All 8 papers metadata-verified; move descriptions at flagged-sketch level from publisher pages, located open copies, and general knowledge; zero paywalled fetches (scope rule unused). This is the designed home of the silent P24 (shadow pricing), the Atlas-named P23 (compression), and the silent P20 (weight shifting).

## Verification table

| ID | Verified citation | Corrections vs seed |
|----|------------------|---------------------|
| K1 | Erdos, Bull. Amer. Math. Soc. 51(12): 898-902 (1945), DOI 10.1090/S0002-9904-1945-08454-7 | none; OPEN AMS PDF located |
| K2 | Harper, "Optimal numberings and isoperimetric problems on graphs", J. Combin. Theory 1 (1966), DOI 10.1016/S0021-9800(66)80059-5 | TITLE corrected ("...on graphs", not "...on the cube"); VENUE corrected (JCT 1 (1966), not Discrete Math.) |
| K3 | Kruskal, "The number of simplices in a complex", in R. Bellman (ed.), Mathematical Optimization Techniques, Univ. of California Press (1963) | TITLE pinned; VENUE pinned (the seed's verify flags resolved) |
| K4 | Katona, "A theorem of finite sets", in Theory of Graphs (Proc. Colloq. Tihany, 1966), Academic Press (1968) | TITLE pinned; VENUE pinned (Tihany proceedings, published 1968) |
| K5 | Bollobas, "On generalized graphs", Acta Math. Acad. Sci. Hungar. 16: 447-452 (1965), DOI 10.1007/BF01904851 | none |
| K6 | Kleitman, "On a combinatorial conjecture of Erdos", J. Combin. Theory 1: 209-214 (1966) | TITLE pinned ("On a combinatorial conjecture of Erdos"); VENUE pinned |
| K7 | Katona, "Intersection theorems for systems of finite sets", Acta Math. Acad. Sci. Hungar. 15: 329-337 (1964), DOI 10.1007/BF01897141 | none; the shared-title coincidence with EKR 1961 (I2) recorded |
| K8 | Frankl-Furedi, "Forbidding just one intersection", J. Combin. Theory Ser. A 39: 160-176 (1985) | TITLE pinned; year 1985; OPEN PDF on Frankl's renyi.hu page |

## Pattern census (Atlas P-IDs firing in this batch)

| P-ID | Fires in | Notes |
|------|----------|-------|
| P24 shadow pricing (Kruskal-Katona) | K3, K4 | FIRST GENUINE FIRINGS - the silent pattern exits the registry in its named theorem's origin papers: Kruskal's cascade representation (price the family by its own real parameter x) and Katona's independent proof of the same bound. The theorem's FIVE independent discoveries (Schutzenberger 1959, Kruskal 1963, Harper 1966, Katona 1968, Clements-Lindstrom 1969, per the standard history) are the survey's strongest load-bearing evidence: the field needed this pattern five separate times |
| P23 compression / shifting | K2 (flagship), K8, K3 (partial), K6 (partial) | the Atlas-named pattern's first genuine classic-paper firings after the I1 partial: Harper's cube compressions toward the simplicial order (the founding large-scale deployment), Frankl-Furedi's shift-to-intersection-closed normalization; partials where the original engine is transformation/induction and the compression proof is retrospective (Clements-Lindstrom) |
| P9 pigeonhole / double counting | K1, K5 | Erdos's antichain map to Sperner (the L-O lemma); Bollobas's permutation double counting (disjoint events of probability 1/C(a+b,a)) |
| P10 averaging | K7 (partial) | the circle method debut: averaging over cyclic permutations does the symmetrization work |

## Honest hypothesis-test results (the batch's yield)

- K1 P10 AND P28 MISSED (both expected): the 1945 engine maps signed sums to subsets forming an ANTICHAIN and applies Sperner - P9 fires instead. The concentration-of-measure story (P28's batch-B home) is retrospective: the L-O lemma is its discrete ancestor. Lineage arc recorded: K1 -> K6 -> batch B concentration.
- K7 P20 MISSED (expected - THE designed-home test): the 2-intersecting bound's engine is the circle method (cyclic-permutation averaging, a P10 partial), not weight shifting. With the I2/E-batch misses, **P20 is now recorded as genuinely under-used by the field's classics - synthesis call on the Atlas P20 entry: the expected symmetrization work is performed by P23 shifting or P10 averaging.**
- K4 P23 MISSED (expected): Katona's shadow proof is the circle method, not compression - the honest same-batch engine contrast with K2/K3 and the retrospective Clements-Lindstrom compression proof.
- K6 P23 PARTIAL (expected): extremal families are Hamming balls, but the original engine is a coordinate-split induction.
- K2, K5, K8: seeds confirmed (P23, P9, P23 respectively, K8 at flagged sketch from the open PDF).

## New-pattern candidates and gate status after eleven batches

1. No new candidates this batch. Gate status unchanged: CAND-A1/A2/A3 crossed; CAND-A4 unfired in-corpus (watch M); CAND-B5/C1/G1 synthesis calls.
2. Silent-registry ledger: **P24 EXITS the registry** (first genuine evidence K3/K4). Remaining silent: P20 (missed now even in its designed home - genuinely under-used; synthesis call), plus the prior records. Full ledger after this batch: P28 (B1/B2), P29 (B4), P33 (F5/F6/F7), P34 (E2/E6; H6/H7/H8), P37 (E4; H10; I11; J2 secondary), P40 (C5), P30 (G1), P31 (G5/G8/G9/G10/G11), P32 (G4), P38 (H10 via companion), and now P24 (K3/K4).
3. Lineage notes recorded for teaching: the five independent KK discoveries; the circle-method arc (K7 1964 -> K4 1968 -> the one-page EKR proof 1972, the I2 retrospective engine); the K8 -> I5 engine dependency (Frankl-Rodl cites [FF1], [FF2]); the K1 -> K6 -> batch-B concentration arc.
4. Watch-items: Kempe-chain likely dies at synthesis (unchanged); slice-rank note stands (synthesis call).

## Verification levels statement

Metadata: web-verified (sources per paper; K2/K6 pinned via ScienceDirect plus a secondary reference list pinning JCT 1, 209-214; K3 via the standard citation record and the volume's table of contents; K4 via the Hungarian Academy repository record). Moves: flagged-sketch summaries. Zero full-text fetches. Open copies located: K1 (AMS PDF), K8 (renyi.hu PDF), K4 (mtak repository record), K7 (Springer/Akademiai Kiado records); K2, K5, K6 paywalled records with standard textbook treatments; K3 out of print with standard textbook treatments - scope rule unused throughout.
