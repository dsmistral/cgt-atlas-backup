# Batch E - Coloring, list coloring and flows (gathered and mined)

Session chunk 5, 2026-10-13. All 11 papers metadata-verified; move descriptions at flagged-sketch level from publisher pages, located open copies, and general knowledge; zero paywalled fetches (scope rule unused).

## Verification table

| ID | Verified citation | Corrections vs seed |
|----|------------------|---------------------|
| E1 | Brooks, Proc. Cambridge Philos. Soc. 37: 194-197 (1941) | none |
| E2 | Hadwiger, Vierteljschr. Naturforsch. Ges. Zurich 88: 133-143 (1943) | page range per standard citation, flagged; title/venue/year confirmed |
| E3 | Vizing, Diskret. Analiz 3: 25-30 (1964), MR 0180505 | none; Gupta independent discovery noted; Vizing's 1976 list-coloring note recorded |
| E4 | Tutte, Canad. J. Math. 6: 80-91 (1954), DOI 10.4153/CJM-1954-010-9 | none |
| E5 | Jaeger, JCTB 26: 205-216 (1979) | TITLE corrected ("Flows and generalized coloring theorems in graphs"); pages flagged; Kilpatrick independent discovery noted |
| E6 | Seymour, JCTB 30: 130-135 (1981) | TITLE corrected ("Nowhere zero 6 flows"); VENUE corrected Quart. J. Math. Oxford -> JCTB |
| E7 | Erdos-Rubin-Taylor, Congr. Numer. 26: 125-157 (1979) | pages flagged; Vizing shared attribution noted |
| E8 | Hajnal-Szemeredi, in: Combinatorial Theory and its Applications (Bolyai 4), North-Holland: 601-623 (1970) | VENUE corrected (not Canad. J. Math.); pages flagged |
| E9 | Thomassen, JCTB 62: 180-181 (1994), DOI 10.1006/jctb.1994.1062 | none |
| E10 | Voigt, Discrete Math. 120: 215-219 (1993) | VENUE corrected (not JCTB) |
| E11 | Galvin, JCTB 63: 153-158 (1995) | none; open PDF located |

## Pattern census (Atlas P-IDs firing in this batch)

| P-ID | Fires in | Notes |
|------|----------|-------|
| P34 minor chasing | E2 (flagship: the origin paper), E6 (contraction lemma) | FIRST GENUINE USAGE EVIDENCE for silent forward-registry P34 |
| P37 duality | E4 (flagship: plane dual exchanges coloring with flows) | FIRST GENUINE USAGE EVIDENCE for silent forward-registry P37; E5/E6 recorded as flow-framework lineage |
| P15 induction on vertices/edges | E1, E3, E7, E8, E9 | E9 carries the strengthened-hypothesis meta-move |
| P8 longest-path / extremal | E1, E3, E7, E11 (secondary) | |
| P25 reduction / encoding | E4 (Tait), E5/E6 (group products), E7 (hypergraph correspondence), E11 (kernels) | E7's bipartite-hypergraph correspondence is two-way |
| P5 generating function | E4 | chromatic/flow polynomials as carriers |
| P11 explicit construction | E7 (separating examples), E10 (counterexample) | E10: the build-the-object pattern in its adversarial role |
| P16 alternating paths / augmentation | E8 (migration chains) | a new face: alternating chains for color classes, not matchings |
| P18 algorithmic proof | E3 (constructive), E8 (lineage: Kierstead-Kostochka algorithms) | |
| P20 weight shifting | E8 adjacent only | weak/adjacent; the real P20 test is Katona (Batch K) |

## New-pattern candidates and gate status after five batches

1. No new full candidates. New WATCH-ITEM: Kempe-chain / fan recoloring - alternating-path recoloring as a coloring engine (E3 Vizing fans, E8 migration chains, E9 chain-flavored induction step). Same-batch recurrence, no dedicated Atlas P-ID; P16 is the closest pattern but its description is matching/flow-specific - the synthesis must judge whether this is a P16 face or a P43 candidate. Watch Batches F/G for further firings.
2. Silent-registry ledger GROWS BY TWO: P34 (E2 flagship + E6) and P37 (E4 flagship) get their first genuine usage evidence. Full ledger: P28 (B1/B2), P29 (B4), P40 (C5), P34 (E2/E6), P37 (E4).
3. Honest structural note: NO paper in Batch E fires P36 (discharging) - Thomassen's 5-choosability proof is famously discharging-free; the planar-coloring discharging tradition (Appel-Haken and successors) is not in this corpus, consistent with the corpus's focus on coloring/flows theorems rather than 4CT-style case analysis.
4. CAND-A4 (entropy compression): did not fire here (expected); keep watching M. Gate status otherwise unchanged: CAND-A1/A2/A3 crossed; CAND-B5/CAND-C1 synthesis calls.
5. The strengthened induction hypothesis (E9, also present in spirit in D4/D6's phase arguments) is recorded as a meta-move under P15/P4, not a pattern.

## Verification levels statement

Metadata: web-verified (sources per paper; page ranges for E2/E5/E7/E8 recorded per standard citation with flags). Moves: flagged-sketch summaries. Zero full-text fetches. Open full texts located: E11 (Kostochka's course page PDF); E6 fully documented by the open new-proof paper (arXiv 1512.06214); E8 by the open Kierstead-Kostochka short proof.
