# Batch O - the Lovasz Local Lemma arc (extension corpus; gathered and mined; work style v2)

Chunk 17 under work style v2: two sub-chunks (17a O1-O3; 17b O4-O6), each pushed as its own commit. Seeded from NEXT100.md (chunk 16 scouting, user-directed): the LLL arc that the chunk-15 synthesis recommended to the Atlas's external canon - the planned corpus holds the origin (A5), the Shearer refinement (A7) and the Moser-Tardos constructive proof (A9); this batch closes the arc's middle and its analytic flank. ACCEPTED papers only; the chunk-16 citation figures remain ESTIMATES (the 2026-10-13 API incident, SOURCES.md section 6) - this gather verifies METADATA against web sources, not citation counts.

| Sub-chunk | Papers | Status |
|-----------|--------|--------|
| 17a | O1 Spencer asymmetric; O2 Beck algorithmic; O3 Erdos-Spencer lopsided | DONE (section below) |
| 17b | O4 Moser constructive; O5 Kolipaka-Szegedy Shearer-threshold; O6 Suen correlation companion | DONE (section below) |

## Sub-chunk 17a (O1-O3) - gathered and mined 2026-10-13

All 3 papers metadata-verified (sources recorded per paper); moves at flagged-sketch level; no full texts needed under the scope rule (the LLL literature is survey-rich - the Springer LLL survey's reference list pinned two citations); zero paywalled fetches. HEADLINES: the external CAND-A1 arc opens with its three structural papers - the asymmetric application (O1, 1977), the first algorithmization with its honest constant loss (O2, 1991), and the lopsided hypothesis refinement (O3, 1991); the P13 baseline-vs-LLL contrast (O1) mirrors the A5 datum, and O2's constant-loss datum sets up the 17b payoff.

### Verification table

| ID | Verified citation | Corrections vs seed |
|----|------------------|---------------------|
| O1 | Spencer, "Asymptotic lower bounds for Ramsey functions", Discrete Math. 20 (1977) 69-76 (ScienceDirect: abstract "A probability theorem, due to Lovasz, is used to derive lower bounds for various Ramsey functions"; NYU Scholars) | CONFIRMED; pages pinned 69-76; the asymmetric-form attribution recorded at survey level (Springer LLL survey; Alon-Spencer canon) - flagged honestly |
| O2 | Beck, "An algorithmic approach to the Lovasz local lemma. I", Random Structures & Algorithms 2(4) (1991) 343-365, DOI 10.1002/rsa.3240020402 (Wiley citation; Rutgers portal; Wikipedia algorithmic-LLL lineage) | PAGES CORRECTED (seed 343-358 -> 343-365) |
| O3 | Erdos-Spencer, "Lopsided Lovasz Local Lemma and Latin transversals", Discrete Appl. Math. 30(2-3) (1991) 151-154 (Springer LLL survey reference list; ScienceDirect abstract) | CONFIRMED; the seed's "(verify)" resolved |

### Pattern census (sub-chunk 17a)

| P-ID | Fires in | Notes |
|------|----------|-------|
| CAND-A1 | O1 (genuine), O2 (genuine), O3 (genuine) | the external arc's structural third: the asymmetric application (O1), the algorithmization with its constant loss (O2), the lopsided dependency refinement + the n/4 Latin-transversal flagship (O3); all three load-bearing in the abstracts'/surveys' own framing |
| P12 | O1 (genuine), O3 (partial) | O1: the random 2-colouring of K_N - the sampled object; O3: the random transversal sampled under the lopsided condition; the extension corpus's first P12 census rows |
| P18 | O2 (genuine) | the first algorithmization: the existence proof replaced by an explicit search procedure with a complexity analysis - the direct ancestor of A9's resampling |
| P13 | (none - honest miss note) | the union bound is only the degenerate d=0 case at O1 (the A5 datum mirrored); the arc's whole point is beating it |

### Engine contrast and lineage (sub-chunk 17a)

- The constant-loss arc: Beck's constructive version pays a stronger constant than the existential lemma (O2); the resampling revolution (O4, A9) erases the loss and reaches the exact boundary (O5) - recorded for the 17b payoff.
- O2's ". I" suffix: the promised Part II never appeared in print (honest note; the algorithmic arc continued via Moser-Tardos).

## Sub-chunk 17b (O4-O6) - gathered and mined 2026-10-13

All 3 papers metadata-verified; moves at flagged-sketch level; no full texts needed under the scope rule (the constructive-LLL content is carried by the arXiv:0903.0544 companion and A9's journal version; the Suen inequality by Janson's 1998 open citation); zero paywalled fetches. HEADLINES: the arc's constructive flank lands - the ENTROPY-COMPRESSION ORIGIN PAPER (O4, CAND-A4's debut: the compression contradiction IS the proof), the SHEARER-THRESHOLD COMPLETION (O5: constructive = existential at the abstract lemma's exact boundary; the hardcore-model phase-transition formulas as a P44 cross-note), and the analytic companion (O6: Suen's correlation inequality - P27's FIRST touch anywhere, partial, on the dependency-graph face; the FKG up-set face test moves to Batch U). BATCH O COMPLETE: CAND-A1's external arc spans 1977-2011 (five load-bearing firings + the analytic companion) - the chunk-15 external-canon recommendation is STRENGTHENED.

### Verification table

| ID | Verified citation | Corrections vs seed |
|----|------------------|---------------------|
| O4 | Moser, "A constructive proof of the Lovasz local lemma", STOC '09 (41st Annual ACM Symposium on Theory of Computing), pp. 343-350, DOI 10.1145/1536414.1536462; pages pinned via the Springer LLL survey's reference list; the arXiv:0903.0544 companion (the general version's preprint) noted honestly | CONFIRMED; seed's "verify pages" resolved |
| O5 | Kolipaka-Szegedy, "Moser and Tardos meet Lovasz", STOC '11 (San Jose, CA, June 6-8, 2011), pp. 235-244, DOI 10.1145/1993636.1993669 (ACM DL open PDF, snippet-level; Springer LLL survey reference list; Semantic Scholar) | CONFIRMED |
| O6 | Suen, "A correlation inequality and a Poisson limit theorem for nonoverlapping balanced subgraphs of a random graph", Random Structures & Algorithms 1(2) (1990) 231-242, DOI 10.1002/rsa.3240010210 (Wiley citation; Janson 1998 reference list) | TITLE AND VENUE CORRECTED (seed: "nonexchangeable events", J. Appl. Probab. 27 -> the canonical RSA paper; the seed conflated a same-author variant) |

### Pattern census (sub-chunk 17b)

| P-ID | Fires in | Notes |
|------|----------|-------|
| CAND-A1 | O4 (genuine), O5 (genuine); O6 (adjacent, NOT a firing) | O4: the solo constructive debut (resampling + witness trees); O5: the Shearer-threshold endpoint (the A7 <-> A9 <-> O5 line); O6: the analytic companion bounding the same quantity - recorded adjacent, not a firing |
| CAND-A4 | O4 (ORIGIN firing) | entropy compression's debut: the witness-tree counting contradiction IS the proof of O4 - the external lineage (Molloy 2019) now has its named origin |
| P18 | O4 (genuine), O5 (genuine) | O4: the resampling loop's termination analysis IS the theorem (A9's census line extends to the solo debut); O5: the efficiency analysis up to the abstract threshold |
| P25 | O4 (partial) | the witness-tree encoding: execution logs as labeled rooted trees, the counted object that makes the compression contradiction quantitative |
| P27 | O6 (first touch, partial) | the dependency-graph correlation face: joint non-occurrence bounded from pairwise dependency data - the silent registry's first recorded touch anywhere (14 in-corpus batches + extension); honest caveat: NOT the up-set/FKG face of the Atlas one-line; the FKG designed-home test moves to Batch U (U1, U2) |
| P44 (cross-note, no census row) | O5 | the hardcore lattice-gas phase-transition formulas - the threshold/window pattern's statistical-mechanics face (adopted into the Atlas at session 80; no survey dossier yet) |

### Engine contrast and lineage (sub-chunk 17b)

- The 1990 companion inequalities: B1 Janson (lower tail, in corpus) and O6 Suen (correlation, extension) born the same year; Janson's "New versions of Suen's correlation inequality" (RSA 13 (1998)) is the recorded refinement lineage.
- The constructive arc's payoff: O2's constant loss erased by O4/A9's resampling; O5 closes at Shearer's exact boundary.
- O6's Poisson limit theorem (nonoverlapping balanced subgraphs) claims NO Atlas P-ID (the B1-family Poisson-paradigm observation, recorded not tagged).

### BATCH O result (2026-10-13) - COMPLETE

6/6 papers metadata-verified (two seed corrections: O2 pages; O6 title + venue); moves at flagged-sketch level; zero paywalled fetches; no full texts needed under the scope rule (the LLL literature is survey-rich - the Springer LLL survey's reference list pinned three of the six citations). **CAND-A1's external arc COMPLETE (1977-2011): five load-bearing firings (O1 asymmetric application; O2 algorithmization; O3 lopsided refinement; O4 constructive debut; O5 Shearer-threshold completion) plus the analytic companion (O6) - the chunk-15 external-canon recommendation (name the LLL in the Atlas or record it as P13's sparse-dependency strengthening) is STRENGTHENED: the engine adapts at every level (form, procedure, hypothesis, threshold). CAND-A4's ORIGIN firing found (O4 - the entropy-compression debut itself; the in-corpus death verdict stands, the external line now has a named origin beyond the Molloy 2019 lineage). P27's FIRST touch (O6, partial, dependency-graph face; the FKG up-set face remains the open test at Batch U). P18's algorithmic-probability column grows by three (O2, O4, O5). P12 gains the extension corpus's first census rows (O1 genuine, O3 partial).** Honest notes: the asymmetric-form attribution (O1) is survey-level; O2's promised Part II never appeared; O6's Poisson limit claims no P-ID. The gather record: papers/O1-O6 per-paper files + this file; STATE.md rows 16 (pin fixed) and 17; the touched dossiers (P12, P18, P25, P27, CAND-A1, CAND-A4) + INDEX.md.
