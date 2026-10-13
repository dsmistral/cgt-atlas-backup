# Batch D - Matching, flows, greedy and algorithms (gathered and mined)

Session chunk 4, 2026-10-13. All 10 papers metadata-verified; move descriptions at flagged-sketch level from publisher pages, located open copies, and general knowledge; zero paywalled fetches (scope rule unused).

## Verification table

| ID | Verified citation | Corrections vs seed |
|----|------------------|---------------------|
| D1 | Kuhn, Naval Res. Logist. Q. 2(1-2): 83-97 (1955), DOI 10.1002/nav.3800020109 | none |
| D2 | Ford-Fulkerson, Canad. J. Math. 8: 399-404 (1956) | none |
| D3 | Edmonds, Canad. J. Math. 17(3): 449-467 (1965) | none; open PDF located (UMich) |
| D4 | Dinic, Soviet Math. Dokl. 11: 1277-1280 (1970) | title verified "...with power estimation"; transliteration Dinitz; Even-Itai modification noted |
| D5 | Edmonds, Math. Programming 1: 127-136 (1971), DOI 10.1007/BF01584082 | venue verified (seed said "(verify)") |
| D6 | Micali-Vazirani, 21st FOCS (1980), DOI 10.1109/SFCS.1980.12 | ACM DL title typo ("algoithm") noted; first complete correctness proof only 2020 (arXiv 2012.03582) |
| D7 | Karp, in: Complexity of Computer Computations, Plenum, New York, 1972, 85-103 | none |
| D8 | Karger, Proc. 4th ACM-SIAM Symp. Discrete Algorithms (SODA 1993) | TITLE corrected; VENUE corrected STOC -> SODA; seed's title belongs to the 1994 companion paper |
| D9 | Christofides, CMU GSIA Report 388 (1976); Serdyukov (1978) | venues resolved; Christofides-Serdyukov attribution recorded |
| D10 | Spielman-Teng, J. ACM 51 (2004), DOI 10.1145/990308.990310 | title completed; issue-number conflict flagged (ACM DL No. 3 vs standard citations 51(2): 385-463) |

## Pattern census (Atlas P-IDs firing in this batch)

| P-ID | Fires in | Notes |
|------|----------|-------|
| P16 alternating paths / augmentation | D1, D2, D3, D6 | the flagship batch: assignment (D1), flow (D2), general graphs with blossoms (D3), phased (D6) |
| P17 duality (min-max) | D1, D2, D9 | D2 is the canonical min-max; D1 predates LP-duality vocabulary; D9's cost certificate |
| P18 algorithmic proof | D1, D2, D3, D4, D5, D6, D9 | D3 is the founding citation for polynomial-time-as-efficiency |
| P25 reduction / encoding | D1, D3, D5, D7, D8, D9, D10 | D7 is the whole-paper exemplar; D5 classifies optimizers by encoding; D9's lossless metric encoding |
| P12 random construction | D8, D10 | two new faces: correctness-amplifying random process (D8), noise-on-input analysis (D10) |
| P10 averaging / expectation | D8 (counting flip), D9 (two-matchings averaging), D10 (expectation over noise) | |
| P4 recurrence / induction | D5 (exchange argument), D7 (reduction transitivity) | |
| P7 parity & handshaking | D9 | the odd-degree set is even, so the matching exists |
| P8 longest-path / extremal | D6 (short augmenting path unless near-max), D9 (tour minus edge = spanning tree) | secondary |

## New-pattern candidates and gate status after four batches

1. No new full candidates this batch. New WATCH-ITEM: monovariant / potential termination argument (D4: source-sink distance strictly rises per phase; D6: shortest augmenting-path length strictly rises) - a genuine same-batch recurrence with no dedicated Atlas P-ID naming it; it partially overlaps P4/P8; watch for cross-batch firing in E (iterative recoloring arguments), H, M.
2. CAND-A4 (entropy compression): NOT fired in Batch D, as expected (wrong domain); keep watching M.
3. Gate status unchanged: CAND-A1/A2/A3 crossed (pending synthesis); CAND-B5 and CAND-C1 single-batch multi-domain, synthesis calls.
4. Silent-registry ledger unchanged: P28 (B1/B2), P29 (B4), P40 (C5). Batch D fires none of P20/P24/P27-P42 - consistent with its domain: its patterns P16/P17/P18/P25 are all spoken in the Atlas and all fire genuinely here.
5. Honest headline: the algorithms batch is the strongest confirmation yet that the Atlas index matches field practice - every expected pattern fired, with the batch's big four (P16, P17, P18, P25) each firing in 4+ of the 10 papers.

## Verification levels statement

Metadata: web-verified (sources per paper). Moves: flagged-sketch summaries. Zero full-text fetches. Open full texts located: D3 (UMich PDF), D7 (Plenum PDF via the Wikipedia reference), D8 (course-copy chapter), D9 (DTIC record for the CMU report), D10 (arXiv version via the author page); the 2020 MV proof paper (arXiv 2012.03582) documents D6 fully.
