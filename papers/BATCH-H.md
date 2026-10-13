# Batch H - Extremal graph theory and structure (gathered and mined)

Session chunk 8, 2026-10-13. All 13 papers metadata-verified; move descriptions at flagged-sketch level from publisher pages, located open copies, and general knowledge; zero paywalled fetches (scope rule unused).

## Verification table

| ID | Verified citation | Corrections vs seed |
|----|------------------|---------------------|
| H1 | Turan, Matematikai es Fizikai Lapok 48: 436-452 (1941) | none; pages pinned |
| H2 | Erdos-Gallai, Acta Math. Acad. Sci. Hungar. 10: 337-356 (1959) | none; OPEN renyi.hu PDF located |
| H3 | Kovari-Sos-Turan, Colloq. Math. 3(1): 50-57 (1954), DOI 10.4064/cm-3-1-50-57 | none |
| H4 | Corradi-Hajnal, Acta Math. Acad. Sci. Hungar. 14: 423-439 (1963) | none; pages pinned |
| H5 | Erdos, Magyar Tud. Akad. Mat. Kutato Int. Kozl. 7: 459-464 (1962) | pages pinned 459-464 (MathSciNet + author list); a 459-474 variant in two Springer secondary sources recorded as citation error |
| H6 | Thomason, Math. Proc. Camb. Phil. Soc. 95(2): 261-265 (1984), DOI 10.1017/S0305004100061521 | YEAR corrected 2001 -> 1984; seed's year belongs to the companion "The extremal function for complete minors", JCTB 81(2) (2001): 318-327 - recorded; OPEN Cambridge PDF located |
| H7 | Kostochka, Combinatorica 4(4): 307-316 (1984), DOI 10.1007/BF02579141 | title verified (seed asked); OPEN author PDF located |
| H8 | Robertson-Seymour, JCTB 41(1): 92-114 (1986), DOI 10.1016/0095-8956(86)90030-4, MR854606 | none; volume/pages pinned |
| H9 | Chudnovsky-Robertson-Seymour-Thomas, Ann. of Math. (2) 164(1): 51-229 (2006), DOI 10.4007/annals.2006.164.51 | none; OPEN Annals PDF located |
| H10 | Lovasz, Discrete Math. 2: 253-267 (1972) | none; companion "A characterization of perfect graphs" JCT 13: 95-98 (1972) recorded |
| H11 | Reed, JCTB 76(2): 136-149 (1999), DOI 10.1006/jctb.1998.1891 | citation corrected: JCTB 1999, not 1998; the 1998 companion "omega, Delta, and chi" JGT 27(4): 177-212 (conjecture paper) recorded |
| H12 | Szemeredi-Trotter, Combinatorica 3: 381-392 (1983), DOI 10.1007/BF02579194 | none |
| H13 | Ajtai-Chvatal-Newborn-Szemeredi, in: Theory and Practice of Combinatorics (Kotzig volume), NH Math. Studies 60 / Ann. Discrete Math. 12, North-Holland: 9-12 (1982) | venue details pinned; Leighton 1982 independent discovery recorded |

## Pattern census (Atlas P-IDs firing in this batch)

| P-ID | Fires in | Notes |
|------|----------|-------|
| P34 minor chasing | H6, H7, H8 | three genuine firings - the scheduled minor-chasing batch; expected at H9 too but MISSED there (honest) |
| P38 replication | H10 (via the same-year companion "A characterization of perfect graphs") | FIRST GENUINE USAGE EVIDENCE for silent P38 |
| P37 duality | H10 | second batch firing (E4 first): the family widens from planar duality to Konig-type minimax duality |
| P8 extremal/optimization | H1, H2, H4, H9, H11 | the batch's backbone pattern - maximal-example/minimal-counterexample analysis |
| P10 averaging / expectation | H5 (supersaturation), H13 (crossing averaging), H6 (density bookkeeping) | H1's slick averaging proof is retrospective exposition - not credited |
| P4 recurrence / induction | H1, H2, H5, H13 (+ H8 through the decomposition) | |
| P2 double counting | H3 (the star-counting engine), H12 (cell counting), H1 partial | H3's P2+P10 engine reappears inside H12 |
| P25 reduction / encoding | H2 (block decomposition), H8 (tree decomposition), H9 (basic classes + 2-joins), H10 (hypergraph formulation), H12 (cell decomposition) | |
| P15 coloring | H11 | topical hit; Kempe content unverified, not credited |
| P12 probabilistic | H6 | random dense subsets inside a structural proof; engine contrast with H7's deterministic construction |
| P9 pigeonhole | H3, H12, H13 | |

## New-pattern candidates and gate status after eight batches

1. No new candidates this batch. Gate status unchanged: CAND-A1/A2/A3 crossed; CAND-A4 unfired in-corpus (watch M); CAND-B5/C1/G1 synthesis calls.
2. Silent-registry ledger grows by one: P38 (H10, via the same-year companion Lovasz characterization paper; credited with the companion note). P37 gains a second batch firing (E4 + H10). Full ledger: P28 (B1/B2), P29 (B4), P33 (F5/F6/F7), P34 (E2/E6; now also H6/H7/H8), P37 (E4; now also H10), P40 (C5), P30 (G1 flagship), P31 (G5/G8/G9/G10/G11), P32 (G4), P38 (H10 via companion).
3. Honest hypothesis-test results (the batch is rich in misses - the index-testing yield): H1 P2 partial (the paper's own engine is induction); H3 P19 MISSED (engine is P2 double counting + P10 convexity); H9 P34 MISSED (SPGT is induced-subgraph decomposition, not minor structure) and P38 deferred to H10; H10 P19 MISSED (P37 + P38 fire instead); H12 P30 AND P33 BOTH MISSED (the incidence engine is partition-and-double-count); H13 P10 confirmed. Confirmed expectations: H2 P8, H4 P8, H5 P10, H6/H7/H8 P34, H11 P15.
4. Engine-contrast observations for the Atlas: (a) H6 vs H7 - same theorem, probabilistic vs deterministic engine; (b) H5's supersaturation is the conceptual ancestor of P31 counting-removal; (c) H12/H13 - cell decomposition plus double counting vs crossing-lemma averaging, unified by Szekeley's 1997 proof of Szemeredi-Trotter from the crossing lemma.
5. Watch-items: Kempe-chain/fan recoloring NOT credited in H (H11's proof unverified at flagged sketch; paywalled) - watch I (algebraic methods, Alon-Tarsi); monovariant/potential silent in H; Boolean influence, spread induction, sign-reversing involution silent.

## Verification levels statement

Metadata: web-verified (sources per paper; the Kotzig volume and the 1941/1962 Hungarian journals are print - citations pinned from multiple independent reference lists, MathSciNet, and the authors' own lists). Moves: flagged-sketch summaries. Zero full-text fetches. Open full texts located: H2 (renyi.hu), H6 (Cambridge Core), H7 (author Illinois page), H9 (Annals).
