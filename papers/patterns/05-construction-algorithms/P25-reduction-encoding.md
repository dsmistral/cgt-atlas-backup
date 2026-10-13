# P25 - Reduction / encoding

- Family: 05-construction-algorithms
- Atlas one-line: Translate one problem into another language; the target structure carries the proof or the hardness
- Home chapters (Atlas): 3, 10, 11
- Status (through chunk 13b): Atlas-named textbook-canon pattern; in-corpus firings recorded below. Batch M: the isomorphism column fires it twice (M1/M2 genuine), M3 the flagship encoding, M4 the second framework firing (genuine), M5/M6 the property-testing partials, and 13c M7 partial (DFS/path encoding) + M9 genuine (the CSP classification) - see the census rows
- Migration: this dossier was machine-migrated 2026-10-13 from the batch files (the gather record and source of truth); every census row and hypothesis-test note below is QUOTED, not rewritten.

## Census rows (quoted; source = papers/BATCH-*.md)

### Batch B (chunk 2)
- Fires in: B7
- Notes: classical theorems rephrased as hypergraph independence

### Batch D (chunk 4)
- Fires in: D1, D3, D5, D7, D8, D9, D10
- Notes: D7 is the whole-paper exemplar; D5 classifies optimizers by encoding; D9's lossless metric encoding

### Batch E (chunk 5)
- Fires in: E4 (Tait), E5/E6 (group products), E7 (hypergraph correspondence), E11 (kernels)
- Notes: E7's bipartite-hypergraph correspondence is two-way

### Batch F (chunk 6)
- Fires in: F4 (partition -> density), F7 (2D -> 1D), F8 (ergodic transference), F10 (structural/hereditary)
- Notes: 

### Batch G (chunk 7)
- Fires in: G1 (reduced graph), G3 (chromatic-number reduction), G12 (analytic recasting)
- Notes: 

### Batch H (chunk 8)
- Fires in: H2 (block decomposition), H8 (tree decomposition), H9 (basic classes + 2-joins), H10 (hypergraph formulation), H12 (cell decomposition)
- Notes: 

### Batch L, sub-chunk 12a (chunk 12)
- Fires in: L1 (partial)
- Notes: the Mathieu groups constructed as the design automorphism groups - combinatorics and group theory carried together; the successive transitive extensions mirror the design extensions.

### Batch M, sub-chunk 13a (chunk 13)
- Fires in: M1 (genuine), M2 (genuine), M3 (flagship)
- Notes: the isomorphism column carries the pattern twice - M1: GI encoded as the color-automorphism problem for permutation groups with bounded simple sections (the reduction IS the title move); M2: GI reduced to String Isomorphism / Coset Intersection under group action (the Luks-framework vehicle, quasipolynomial in the largest orbit); M3: asymptotic extremal questions encoded as elements of the flag algebra with positivity constraints - the model-theoretic translation is the whole framework.

### Batch M, sub-chunk 13b (chunk 13)
- Fires in: M4 (genuine), M5 (partial), M6 (partial)
- Notes: M4: the flag-algebra encoding again (the density problem translated into the algebra's positivity constraints - the framework's second in-corpus firing). M5 partial: a monotone property reduced to a finite set of forbidden colorings of reduced graphs. M6 partial: a property encoded by its regularity profile - the characterization is an encoding statement.

### Batch M, sub-chunk 13c (chunk 13)
- Fires in: M7 (partial), M9 (genuine)
- Notes: M7 partial (unplanned): the graph encoded into DFS/path structures - the path decomposition makes the iterative path-addition embedding tractable (the paper's own Auslander-Parter framing). M9 (expected by seed): homomorphism <-> CSP <-> conjunctive-query evaluation as one problem in three languages, with the complexity encoded as a structural invariant (bounded tree-width of cores) - the "other side" perspective is itself a translation.

## Hypothesis-test notes (quoted; source = papers/BATCH-*.md)

### Batch M, sub-chunk 13a (chunk 13)
- M1 P25 CONFIRMED (expected by seed); M3 P25 CONFIRMED (expected, flagship); M2 P25 confirmed UNPLANNED by seed (the M2 seed row expected P8/P30, both missed) - the reduction chain GI -> String Isomorphism -> Coset Intersection is the abstract's own framing.

### Batch M, sub-chunk 13b (chunk 13)
- M4 P25 CONFIRMED (expected by seed); M5/M6 P25 partials confirmed (unplanned - the seeds expected only P30).

### Batch M, sub-chunk 13c (chunk 13)
- M9 P25 CONFIRMED (expected by seed, genuine); M7 P25 partial confirmed (unplanned - the DFS/path encoding).

## Cross-links (interdependence)

(none recorded)
