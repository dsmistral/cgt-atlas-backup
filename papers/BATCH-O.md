# Batch O - the Lovasz Local Lemma arc (extension corpus; gathered and mined; work style v2)

Chunk 17 under work style v2: two sub-chunks (17a O1-O3; 17b O4-O6), each pushed as its own commit. Seeded from NEXT100.md (chunk 16 scouting, user-directed): the LLL arc that the chunk-15 synthesis recommended to the Atlas's external canon - the planned corpus holds the origin (A5), the Shearer refinement (A7) and the Moser-Tardos constructive proof (A9); this batch closes the arc's middle and its analytic flank. ACCEPTED papers only; the chunk-16 citation figures remain ESTIMATES (the 2026-10-13 API incident, SOURCES.md section 6) - this gather verifies METADATA against web sources, not citation counts.

| Sub-chunk | Papers | Status |
|-----------|--------|--------|
| 17a | O1 Spencer asymmetric; O2 Beck algorithmic; O3 Erdos-Spencer lopsided | DONE (section below) |
| 17b | O4 Moser constructive; O5 Kolipaka-Szegedy Shearer-threshold; O6 Suen correlation companion | pending (sub-chunk 17b) |

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
