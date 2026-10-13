# Chunk ledger - source of truth for progress

One chunk per session. Update this file in the same push_files commit as the batch it closes. Never leave a chunk IN PROGRESS without pushing a marker here.

| Chunk | Scope | Status | Session | Commit |
|-------|-------|--------|---------|--------|
| 0 | Bootstrap: charter, seed corpus, ledger | DONE | 2026-10-13 | 62ba5757 (chunk-0 commit) |
| 1 | Batch A - probabilistic method, random graphs (9) | DONE | 2026-10-13 | bd445028 (chunk-1 commit) |
| 2 | Batch B - thresholds, entropy, containers (9) | DONE | 2026-10-13 | 1bcb5614 (chunk-2 commit) |
| 3 | Batch C - enumerative counting (7) | DONE | 2026-10-13 | 39a651c (chunk-3 commit) |
| 4 | Batch D - matching, flows, greedy, algorithms (10) | DONE | 2026-10-13 | 7eb1215d (chunk-4 commit) |
| 5 | Batch E - coloring, list coloring, flows (11) | DONE | 2026-10-13 | 344bc49c (chunk-5 commit; ce99fa8f same-session touch-up) |
| 6 | Batch F - Ramsey theory (10) | DONE | 2026-10-13 | 26dd8b52 (chunk-6 commit) |
| 7 | Batch G - regularity, density, removal (12) | DONE | 2026-10-13 | this commit |
| 8 | Batch H - extremal graph theory (13) | PENDING | - | - |
| 9 | Batch I - algebraic and polynomial methods (12) | PENDING | - | - |
| 10 | Batch J - spectral methods (4) | PENDING | - | - |
| 11 | Batch K - shadows and compression (8) | PENDING | - | - |
| 12 | Batch L - designs, packing, codes (12) | PENDING | - | - |
| 13 | Batch M - modern structural/algorithmic (9) | PENDING | - | - |
| 14 | Synthesis: ANALYSIS.md, P43+ proposal, silent-P usage evidence | PENDING | - | - |

**How to run a gather chunk (per batch):** 1) verify each seed row against a web source, recording the URL; 2) gather abstract or faithful summary; 3) extract the decisive moves and tag Atlas P-IDs; 4) log candidate new patterns with the load-bearing test in mind; 5) fetch an open-access full text only if a new pattern needs it (scope rule); 6) push papers/BATCH.md + per-paper files + updated STATE.md in ONE push_files commit; 7) update the knowledge topic current-state paragraph.

**Candidate ledger (running, for the load-bearing test):** CAND-A1 Lovasz Local Lemma - GATE CROSSED (A: A5/A7/A9; B: B9 flagged presentation-level; resolve flag at synthesis). CAND-A2 semi-random nibble + parameter tracking - GATE CROSSED (A: A6/A8; B: B4 guided-random). CAND-A3 threshold/window - GATE CROSSED (A: A2/A3; B: B3/B5/B6). CAND-A4 entropy compression - A9 + Molloy-2019 lineage via B9; NOT crossed in-corpus; not fired in D/E/F/G (expected); watch M. CAND-B5 hypergraph containers - B7/B8 single batch, multi-domain within; synthesis call. CAND-C1 analytic combinatorics / singularity analysis - C2 + C6 with C3 lineage, ALL within Batch C; cross-batch in-corpus firing unlikely in H-M; synthesis call. CAND-G1 transference / dense-model principle - G11 flagship (Green-Tao) + G9 relative-removal lineage, single batch; synthesis call (P43+ candidate vs face of P30/P31). Watch-items: Boolean influence (B3), spread induction (B6), sign-reversing involution (C4), Kempe-chain/fan recoloring (E3, E8, E9; silent in F/G; watch H), monovariant/potential termination - NOW CROSS-BATCH (D: D4/D6; G: G1 index increment + G7 algorithmic index loop, G10 iterative purification adjacent; overlaps P4/P33 - synthesis call on distinctness). Silent-registry patterns with first genuine usage evidence: P28 (B1/B2), P29 (B4), P34 (E2/E6), P37 (E4), P40 (C5), P33 (F5/F6/F7), P30 (G1 named-lemma flagship, six faces in batch G; F6 was the birthplace - no double credit), P31 (G5 origin, G8 flagship, G9/G10/G11), P32 (G4 stability-method origin). Honest notes: no Batch E paper fires P36 (discharging); seed expectations P32@G2 and P32@G3 MISSED (limit-theorem papers); G8 proves P31 without full P30 and G10 proves density statements without the P33 loop - both recorded as teaching contrasts for the Atlas's P30/P31/P33 entries.
