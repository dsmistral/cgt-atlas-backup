# Batch G - Regularity, density and removal (gathered and mined)

Session chunk 7, 2026-10-13. All 12 papers metadata-verified; move descriptions at flagged-sketch level from publisher pages, located open copies, and general knowledge; zero paywalled fetches (scope rule unused).

## Verification table

| ID | Verified citation | Corrections vs seed |
|----|------------------|---------------------|
| G1 | Szemeredi, in: Problemes Combinatoires et Theorie des Graphes, Colloq. Int. CNRS 260, Orsay: 399-401 (1976) | none; pages pinned from two independent reference lists |
| G2 | Erdos-Stone, Bull. Amer. Math. Soc. 52(12): 1087-1091 (1946) | none; OPEN AMS PDF located; pages pinned |
| G3 | Erdos-Simonovits, Studia Sci. Math. Hungar. 1: 51-57 (1966) | none; OPEN renyi.hu PDF located |
| G4 | Simonovits, in: Theory of Graphs (Proc. Colloq., Tihany, 1966), Academic Press: 279-319 (1968) | TITLE corrected: full title ends "stability problems" (seed omitted the suffix) |
| G5 | Ruzsa-Szemeredi, in: Combinatorics Vol. II (Keszthely, 1976), Coll. Math. Soc. J. Bolyai 18, North-Holland: 939-945 (1978) | venue details + pages pinned; 1978 vs 1979 dating discrepancy recorded |
| G6 | Gowers, Geom. Funct. Anal. 7: 322-337 (1997), DOI 10.1007/PL00001621 | none; pages pinned; open short-proof companion noted (Caltech PDF) |
| G7 | Frieze-Kannan, Electron. J. Combin. 6(1): R17, 7 pp. (1999), DOI 10.37236/1449 | none; open-access journal |
| G8 | Fox, Ann. of Math. (2) 174(1): 561-579 (2011), DOI 10.4007/annals.2011.174.1.17 | YEAR corrected 2010 -> 2011 (seed's year was the arXiv posting); OPEN Annals + MIT PDFs located |
| G9 | Tao, J. Combin. Theory Ser. A 113(7): 1257-1280 (2006), arXiv math/0503572 | none; OPEN arXiv copy located |
| G10 | Gowers, Ann. of Math. (2) 166(3): 897-946 (2007), arXiv 0710.3032 | none; OPEN Annals PDF + author preprint located |
| G11 | Green-Tao, Ann. of Math. (2) 167(2): 481-547 (2008), arXiv math/0404188 | none; OPEN Annals PDF located |
| G12 | Lovasz-Szegedy, GAFA Geom. Funct. Anal. 17: 252-270 (2007), DOI 10.1007/s00039-007-0599-6 | none; pages pinned |

## Pattern census (Atlas P-IDs firing in this batch)

| P-ID | Fires in | Notes |
|------|----------|-------|
| P30 regularity | G1 (named-lemma flagship: the Orsay statement; F6 was the birthplace - no double credit), G5 (engine inside the (6,3) proof), G6 (limits face), G7 (algorithmic face), G10 (hypergraph flagship), G11 (host-verification layer), G12 (analyst face) | FIRST GENUINE USAGE EVIDENCE for silent P30 - the designed flagship batch: six faces of one pattern |
| P31 counting-removal | G5 (birthplace: triangle removal inside the (6,3) problem), G8 (flagship: new proof, tower of height 5h^4 log(1/epsilon) vs tower of height poly(1/epsilon)), G9 (hypergraph, self-contained), G10 (hypergraph regularity route), G11 (machinery layer) | FIRST GENUINE USAGE EVIDENCE for silent P31; G8 additionally proves P31 does NOT require full P30 |
| P32 stability | G4 (flagship: the stability-method origin paper) | FIRST GENUINE USAGE EVIDENCE for silent P32; the seed's P32@G2 and P32@G3 expectations MISSED (both are density/limit papers) |
| P10 averaging / expectation | G2 (common-neighborhood embedding), G3 (inherited), G4 (near-extremal forcing), G6 (partition bookkeeping) | the Erdos-Stone engine is an averaging engine at heart |
| P4 recurrence / induction | G1, G7 (refinement loops), G9 (uniformity induction), G10 (iterative purification) | |
| P25 reduction / encoding | G1 (reduced graph), G3 (chromatic-number reduction), G12 (analytic recasting) | |
| P18 algorithmic proof | G7, G12 | P30 meeting P18 at G7 |
| P11 explicit construction | G5 (Behrend-based (6,3) systems), G6 (recursive tower construction) | the batch's adversarial constructions |
| P9 pigeonhole | G2, G6 | secondary |

## New-pattern candidates and gate status after seven batches

1. NEW CANDIDATE: CAND-G1 transference / dense-model principle - flagship at G11 (Green-Tao), within-batch lineage at G9 (relative hypergraph removal). Single batch so far; the synthesis must judge P43+ candidate vs a face of P30/P31. Cross-batch in-corpus firing is unlikely in H-M (no further transference papers seeded); recorded as a synthesis call alongside CAND-B5 and CAND-C1.
2. Watch-item monovariant/potential termination CROSSES BATCHES: D (D4 phase-distance, D6 augmenting-path length) and G (G1 index increment - the energy argument terminating the regularity refinement; G7 the same loop algorithmically; G10's iterative purification in the same family, recorded adjacent). Overlaps P4 (induction/termination) and P33's increment face; the synthesis must decide whether a dedicated P-ID is warranted.
3. Silent-registry ledger GROWS BY THREE: P30 (G1 named-lemma flagship plus five more faces), P31 (G5 origin / G8 flagship / G9 / G10 / G11), P32 (G4 stability-method origin). Full ledger: P28 (B1/B2), P29 (B4), P33 (F5/F6/F7), P34 (E2/E6), P37 (E4), P40 (C5), P30 (G1 flagship), P31 (G5/G8/G9/G10/G11), P32 (G4). This is the largest single silent-registry harvest of the survey - the batch was designed for it and delivered.
4. Honest hypothesis-test results: P30@G1 confirmed (flagship as scheduled); P32@G2 and P32@G3 MISSED (the 1946 and 1966 papers are density/limit papers; stability is genuinely Simonovits 1968); P31@G5 confirmed (birthplace); P30@G11 confirmed at the verification layer only (pseudorandom host, not a regularity partition).
5. Teaching-contrast observations for the Atlas: G10 (hypergraph regularity route) proves density statements WITHOUT the P33 density-increment loop of F5/F6 - two different engines for the same theorems; and G8 shows P31 without full P30. Both contrasts belong in the P30/P31/P33 entries.
6. Kempe-chain watch-item did NOT fire in G (as expected - no coloring engine here); keep watching H. CAND-A4 (entropy compression) did not fire (expected); watch M. Gate status otherwise unchanged: CAND-A1/A2/A3 crossed; CAND-B5/C1/G1 synthesis calls.

## Verification levels statement

Metadata: web-verified (sources per paper; the CNRS 260, Tihany 1968, and Bolyai 18 volumes are print volumes - citations pinned from multiple independent reference lists). Moves: flagged-sketch summaries. Zero full-text fetches. Open full texts located: G2 (AMS), G3 (renyi.hu), G7 (EJC open access), G8 (Annals + MIT), G9 (arXiv), G10 (Annals + author preprint + arXiv), G11 (Annals + arXiv).
