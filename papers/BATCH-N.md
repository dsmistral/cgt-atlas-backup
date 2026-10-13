# Batch N - youth-authored accepted papers: patterns accessible at pre-doctoral levels (gathered and mined; work style v2)

Chunk 14 under work style v2: three sub-chunks (14a N1-N3; 14b N4-N6; 14c N7-N8), each pushed as its own commit. Seeded from SOURCES.md section 4 (user-directed, 2026-10-13): ACCEPTED papers only (never proposals or mere surveys), authors at undergraduate level and below (high school, middle school, amateur). The batch's research question: which Atlas patterns are accessible enough - and mostly used - at pre-doctoral levels to reach research-grade results.

| Sub-chunk | Papers | Status |
|-----------|--------|--------|
| 14a | N1 Jackson-Johnson; N2 Sah-Sawhney-Stoner-Zhao; N3 Jain-Sah-Sawhney | DONE (section below) |
| 14b | N4 PRIMES STEP chip-firing; N5 stable marriage and Sudoku; N6 sequences of stable matching | DONE (section below) |
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

## Sub-chunk 14b (N4-N6) - gathered and mined 2026-10-13

All 3 papers metadata-verified against journal/arXiv records; two open full texts fetched under the scope rule (N4's journal PDF and N6's published JIS PDF - the P5/P3 pattern decisions needed the interiors); N5 verified from the open arXiv HTML, the CMJ page itself Cloudflare-blocked; zero paywalled fetches. HEADLINES: **P3 inclusion-exclusion fires for the FIRST TIME in the corpus - at the middle-school level** (N6's exact-soulmate counts, Lemma 4 / Theorems 6 and 9): the never-fired Atlas pattern's first genuine usage evidence arrives from a PRIMES STEP team in grades 6-9. The middle-school trio's engines are the freshman canon's core: P4 recurrence + induction (N4 flagship - the chip-firing paper's spine), the P25 encoding (N5 flagship - the SMP <-> Sudoku translation, the whole-paper move), and the elementary counting faces (P9 pigeonhole at N5's key function; P1 bijection at N6's joint-profiles count; P2/P41/P7 partials). Honest misses: P5 at BOTH N4 and N6 (the seed shorthand conflated sequence generation with generating functions - no GF in either paper), P16 at N5 (no augmentation engine - the accessibility datum), P23 at N6.

### Verification table

| ID | Verified citation | Corrections vs seed |
|----|------------------|---------------------|
| N4 | Agrawal, Ge, Greene, Kim, Mandal, Parida, Pulugurtha, Redwine, Samanta, Xu, and Khovanova, "Chip-Firing on Infinite k-ary Trees", Enumer. Comb. Appl. 6:1 (2026), Article #S2R7, DOI 10.54550/ECA2026V6S1R7 (received May 22 2025, accepted Nov 6 2025, published Jan 2 2026); arXiv:2501.06675 | CONFIRMED as seeded; dates + DOI pinned; the PDF URL's S2A7 filename vs the printed #S2R7 article number noted; the mentor Khovanova on the author list (honest note) |
| N5 | Borodin, Chen, Duncan, Litchev, Liu, Moroz, Qian, Raghavan, Rastogi, Voigt, and Khovanova, "The Stable Marriage Problem and Sudoku", College Mathematics Journal 55(4) (2024), DOI 10.1080/07468342.2023.2261183 (a PRIMES STEP 2021 project) | Published title confirmed via the T&F record; the arXiv preprint is titled "The Stable Matching Problem and Sudoku" - the preprint/publication title difference noted; the CMJ page range NOT pinned (T&F Cloudflare-blocked - honest, as at N1) |
| N6 | Borodin, Duncan, Litchev, Liu, Moroz, Qian, Raghavan, Rastogi, Voigt, and Khovanova, "Sequences of the Stable Matching Problem", Journal of Integer Sequences 27 (2024), Article 24.2.2 (received Jan 10 2022, published Jan 16 2024); arXiv:2201.00645 | Volume/article PINNED at gather as the seed directed; AUTHOR-LIST CORRECTION: Eric Chen on the arXiv preprint, ABSENT from the published JIS author list - recorded honestly |

### Pattern census (sub-chunk 14b)

| P-ID | Fires in | Notes |
|------|----------|-------|
| P3 inclusion-exclusion | N6 (genuine - FIRST census firing) | the alternating sums counting profiles with exactly k soulmate pairs (Lemma 4 / Theorem 6, repeated in the Latin-square interior of Theorem 9) - the never-fired Atlas pattern's first genuine in-corpus firing, from a middle-school team |
| P4 recurrence + induction | N4 (genuine - the paper's spine), N5 (genuine) | N4: induction on n for the stable configurations (Prop 3.1), backward induction for fire counts (Thm 4.1), the d0 recurrence + double induction (Prop 4.1 / Thm 4.2), the recursive root-fire formula (Cor 4.3). N5: Prop 1 - the forced soulmate pair removed, recurse |
| P25 reduction / encoding | N5 (flagship), N4 (partial) | N5: the bidirectional SMP <-> Sudoku translation is the whole paper (profiles in grids; mutually Latin / joint / disjoint profiles; the new joint-groups Sudoku). N4: the base-k digit encoding of the stable configuration (Prop 3.2) |
| P9 pigeonhole | N5 (genuine) | Prop 2: ranked j at least 2n times forces a man ranked j twice - the key function is a bijection |
| P1 bijection | N6 (genuine), N5 (partial) | N6: joint profiles = Latin squares x key functions (A002860(n) x n!) - count by 1-1 correspondence. N5: the key-function bijective structure (Theorem 3); the counting content lands at N6 |
| P2 double counting | N4 (partial), N6 (partial) | N4: the chip-flow accounting identity (Lemma 4.1 - chips sent to children counted both ways) and the total-fires double-sum re-indexing (Thm 5.1). N6: the staged product decompositions + the (n^2)! encoding bound (Prop 3) |
| P41 divisibility | N6 (partial) | Prop 3: the disjoint-profiles count divisible by (n!)^2 via the relabeling symmetry - double counting's arithmetic face continuing outside design theory |
| P7 parity & handshaking | N4 (partial) | Prop 5.4: the total fires at the odd special indices divisible by 2(k+1) - a divisibility end-of-argument; the chip-conservation identity credited under P2 (no double credit) |
| P18 algorithmic proof | N6 (partial) | the Gale-Shapley round traces (Props 1, 2, 7): the trace IS the proof, with the honest caveat that the algorithm is the object of study |

### Honest hypothesis-test results (sub-chunk 14b)

- N4 P5 MISSED (expected by seed as the fire-count sequences): NO generating function appears in the paper - closed forms come from direct summation, recurrences, and the k-adic-valuation digit analysis; the seed's shorthand conflated sequence generation with P5 (recorded, never silently).
- N6 P5 MISSED and P23 MISSED (both expected by seed): no generating function; no compression/shifting - the counting engine is inclusion-exclusion + staged products + algorithm traces; P3 fires instead (UNPLANNED - the corpus's first P3 firing).
- N5 P16 MISSED (expected by seed as P16?): no alternating-path/augmentation move anywhere; the matching structure runs on blocking pairs + the Gale-Shapley proposing procedure - the accessibility datum: the SMP canon at the middle-school level does NOT use augmentation.
- N4 P7 PARTIAL (expected by seed as chip-firing invariants and parity): the parity content is one divisibility proposition (Prop 5.4); the chip-conservation identity is recorded under P2 - no double credit.
- Coverage-gap observation for the synthesis: N4's k-adic-valuation digit engine (Thm 4.2: d0(m,k) = nu_k((k-1)m+1)+1; the fractal difference sequences; the schizophrenic-numbers decimal phenomenon) matches NO Atlas P-ID - a digit-arithmetic engine joining the L4/L12/M8/M1-M2 coverage-gap list.
- Author-level honesty notes: all three papers include the mentor Khovanova (MIT); the students are PRIMES STEP (grades 6-9) - the batch's youth claims carry these caveats, never silent.

### Lineages (sub-chunk 14b)

- The chip-firing arc: Engel 1975 (probabilistic abacus) -> Spencer 1986 (one-dimensional) -> Bjorner-Lovasz-Shor 1991 (graphs) -> Musiker-Nguyen (binary trees) -> Inagaki-Khovanova-Luo (binary trees, the immediate predecessor; arXiv-only, EXCLUDED from this corpus by the accepted-papers rule - noted in SOURCES.md) -> N4 2026 (k-ary trees: the middle-school team generalizing the published binary-tree results).
- The stable-matching pair: Gale-Shapley 1962 -> N5 (CMJ 2024, the SMP <-> Sudoku translation) and N6 (JIS 2024, the profile-counting sequences) - one PRIMES STEP circle, two journals; the mutually-Latin thread (N5) counted at N6 (Theorems 8-9), with the OEIS as the shared backbone (30 new sequences).
- The P3 accessibility datum for the synthesis: the never-fired Atlas pattern's first in-corpus firing arrives from pre-doctoral authors - the freshman canon's inclusion-exclusion carries publishable research at the middle-school level.

### Verification-levels statement

All three papers metadata-verified against journal/arXiv records (sources described in the per-paper files); N4 and N6 proof interiors verified against the fetched open PDFs (the journal versions); N5 verified against the open arXiv HTML (the CMJ full-text page Cloudflare-blocked - the published version's interior not fetched, honestly). Moves at flagged-sketch level per the standing convention; zero paywalled fetches.
