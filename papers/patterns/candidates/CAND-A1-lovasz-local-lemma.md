# CAND-A1 - The Lovasz Local Lemma

- Family: candidates
- Shape: many bad events, each rare and near-independent of most others
- Move: a dependency graph with 4pd <= 1 (or asymmetric x-certificates) implies positive probability that no bad event occurs - a strict strengthening of P13 (union bound) in the sparse-dependency regime
- Evidence: A5 (debut, Erdos-Lovasz 1975), A7 (Shearer - the optimal-threshold lineage), A9 (Moser-Tardos algorithmization; Godel Prize 2020), B9 (Johansson - flagged PRESENTATION-LEVEL only; resolve the flag at synthesis)
- Gate status: CROSSED (batches A and B). The survey's leading P43 candidate.
- Synthesis tasks: resolve the B9 presentation-level flag (an open-exposition fetch is authorized under the scope rule if needed); confirm no existing P-ID names the move (P13 covers only the union bound).

## Synthesis call (chunk 15, 2026-10-13)

**Verdict: NOT PROMOTED in-corpus.** The B9 presentation-level flag is resolved AGAINST: the LLL step credited to Johansson lives in the Molloy-Reed expositions, not in Johansson's own DIMACS Technical Report 91-5 (itself never journal-published); by the letter of the load-bearing test the evidence is single-batch (A5/A7/A9). EXTERNAL-CANON RECOMMENDATION for the Atlas session: either name the Lovasz Local Lemma as its own Atlas entry or record it as P13's sparse-dependency strengthening. Full reasoning: papers/ANALYSIS.md section 1.

## Extension evidence - sub-chunk 17a (chunk 17, 2026-10-13)

Batch O (the LLL arc, NEXT100 seeds; quoted from papers/BATCH-O.md):
- Fires in: O1 (genuine), O2 (genuine), O3 (genuine)
- O1 Spencer 1977 - the LLL's first application flagship ("a probability theorem, due to Lovasz" derives the Ramsey lower bounds; the ASYMMETRIC x_i-certificate form credited to this paper at survey level, flagged honestly); O2 Beck 1991 - the FIRST algorithmization (existence proof -> explicit search procedure, under a stronger constant); O3 Erdos-Spencer 1991 - the LOPSIDED dependency-graph refinement + the n/4 Latin-transversal flagship.
- The chunk-15 external-canon recommendation gains its arc: three more load-bearing firings beyond A5/A7/A9, each a different adaptation (form, procedure, hypothesis).
