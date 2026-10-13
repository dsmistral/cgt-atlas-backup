# Batch N - youth-authored accepted papers: patterns accessible at pre-doctoral levels (gathered and mined; work style v2)

Chunk 14 under work style v2: three sub-chunks (14a N1-N3; 14b N4-N6; 14c N7-N8), each pushed as its own commit. Seeded from SOURCES.md section 4 (user-directed, 2026-10-13): ACCEPTED papers only (never proposals or mere surveys), authors at undergraduate level and below (high school, middle school, amateur). The batch's research question: which Atlas patterns are accessible enough - and mostly used - at pre-doctoral levels to reach research-grade results.

| Sub-chunk | Papers | Status |
|-----------|--------|--------|
| 14a | N1 Jackson-Johnson; N2 Sah-Sawhney-Stoner-Zhao; N3 Jain-Sah-Sawhney | DONE (section below) |
| 14b | N4 PRIMES STEP chip-firing; N5 stable marriage and Sudoku; N6 sequences of stable matching | PENDING |
| 14c | N7 Kuszmaul; N8 reverse Sidorenko | PENDING |

## Sub-chunk 14a (N1-N3) - gathered and mined 2026-10-13

All 3 papers metadata-verified; moves at flagged-sketch level (two OPEN full texts fetched under the scope rule - N2's proof structure and N3's proof interior needed verification for pattern decisions; zero paywalled fetches). HEADLINES: the accessibility datum lands both ways - an undergraduate(+mentor) team settles a 31-year-open conjecture with an ACCESSIBLE SKELETON (the independent-set recursion + Zhao's swapping trick) plus one heavy technical verification (the layered Holder inequality; Kahn's entropy engine honestly replaced), while the high-school pair (N1) reach the Monthly's lead article with ZERO Atlas patterns (the designed domain-outlier datum). P28 fires in its SECOND census batch at N3, with the interior union bound confirming the seed's P13 (also its second batch).

### Verification table

| ID | Verified citation | Corrections vs seed |
|----|------------------|---------------------|
| N1 | Jackson and Johnson, "Five or Ten New Proofs of the Pythagorean Theorem", Amer. Math. Monthly 131(9): 739 (2024), DOI 10.1080/00029890.2024.2370240 (lead article, November 2024) | CONFIRMED as seeded; end page not pinned (the T&F full-text page is Cloudflare-blocked - recorded honestly); the March 2023 AMS sectional presentation noted |
| N2 | Sah, Sawhney, Stoner, Zhao, "The number of independent sets in an irregular graph", J. Combin. Theory Ser. B 138: 172-195 (2019); arXiv:1805.04021 | CONFIRMED as seeded (MIT DSpace citation); author-level note: three undergraduates + the faculty mentor (Zhao) - recorded honestly |
| N3 | Jain, Sah, Sawhney, "Anticoncentration versus the Number of Subset Sums", Advances in Combinatorics 2021:6, 10 pp., DOI 10.19086/aic.24872 (received 19 Jan 2021, published 28 Jun 2021); arXiv:2101.07726 | CONFIRMED as seeded; DOI/dates/length pinned; author-level note: Sah/Sawhney undergraduates, Jain a graduate student - recorded honestly |

### Pattern census (sub-chunk 14a)

| P-ID | Fires in | Notes |
|------|----------|-------|
| P25 reduction / encoding | N2 (genuine) | Zhao's bipartite-swapping reduction (the double cover G x K2) is the settlement's step 1 - the seed's expectation confirmed |
| P4 recurrence + induction | N2 (genuine, unplanned) | induction on the vertex count via the independent-set recursion i(G) = i(G-w) + i(G-w-N(w)) at a maximum-degree vertex - the freshman-level recursion is the proof's skeleton |
| P10 averaging / expectation | N3 (genuine), N2 (partial) | N3: the density-transfer move (the uniform measure on B dominated by the Bin(k) product measure; then averaging over x) is the paper's own novelty vs Nederlof et al. N2: the Holder/convexity face in the local-inequality verification |
| P28 concentration | N3 (genuine - SECOND census batch) | the sharp binomial small-ball comparison (Lemma 2.3: entropy-form Chernoff-Hoeffding + Gaussian sign-coupling + Jensen + MGF) - the Littlewood-Offord lineage's modern face; the K1 engine was the P9 antichain face (the honest same-lineage engine contrast) |
| P13 union bound | N3 (genuine - SECOND census batch) | the sup over A inside the comparison lemma tamed by P[sup >= e^{tn}] <= |A| * sup - the interior step, confirmed against the fetched open PDF |
| P2 double counting | N3 (partial, unplanned) | the injective sumset identity A x (kB) -> A + kB (Lemma 2.2, inherited from Nederlof et al.) - the counting identity that launches the proof |

### Honest hypothesis-test results (sub-chunk 14a)

- N1: the seed's domain-outlier hypothesis CONFIRMED - NO Atlas P-ID fires (the engine is Pythagoras-free trigonometric manipulation; the accessibility path at the high-school level was contest culture + domain fluency, not pattern deployment).
- N2 P29 MISSED as the in-proof engine (expected flagship by seed): the settling proof AVOIDS Kahn's entropy argument (Shearer's inequality not applicable losslessly in the irregular case); the Holder + computation step is recorded as a P10 convexity face with the Lubetzky-Zhao reinterpretation note (Holder reinterprets Kahn's entropy proof for the regular case). The lineage stands: Kahn 2001 (the B4 P29 flagship) -> Zhao 2009/2010 (swapping) -> N2 2019.
- N2 P9 MISSED (expected by seed): the double-cover counting content is the injection recorded under P25.
- N3 P28-family CONFIRMED (expected); N3 P10 CONFIRMED (expected); N3 P13 CONFIRMED in the interior (expected - the open full text was fetched for this decision per the scope rule).
- Author-level honesty notes: N2 includes the faculty mentor; N3 includes a graduate student - the batch's youth claims are recorded with these caveats, never silently.

### Lineages (sub-chunk 14a)

- The independent-sets arc: Granville 1988 (the Banff conjecture) -> Alon 1991 -> Kahn 2001 (entropy, bipartite regular; the B4 P29 flagship) -> Zhao 2009/2010 (bipartite swapping, all regular) -> Galvin-Zhao (computer-assisted, maximum degree <= 5) -> N2 2019 (all graphs without isolated vertices; the colorings/homomorphisms analogue settled by the authors in follow-up work). The open expository reproduction: Chheda-Goel-Qiao, arXiv:2405.18815 (2024).
- The anticoncentration arc: K1 Erdos 1945 (the Sperner antichain - the P9 face) -> K6 Kleitman diametric -> B1/B2 concentration (Janson, Talagrand - the P28 home batch) -> Tao-Vu inverse Littlewood-Offord -> Nederlof-Pawlewicz-Swennenhuis-Wegrzycki (bin packing) -> N3 (the O(sqrt(epsilon)) bound; the linear dependence conjectured). External descendants: the Renyi-entropy comparison line improving N3's bound - a synthesis note.

### Verification-levels statement

All three papers metadata-verified against journal/author/press records (sources described in the per-paper files); N2's proof structure verified against its open PDF and the Chheda-Goel-Qiao expository reproduction; N3's proof interior verified against its open arXiv PDF; N1 at flagged sketch from the open T&F snippets plus press records (the full-text page Cloudflare-blocked). Moves at flagged-sketch level per the standing convention; zero paywalled fetches.
