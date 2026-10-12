## Session 54 machine runs — batch 4 (Chunk 54c-IV: STS(13) = 2 — the full machine proof) — 2026-10-12

### B4a — star-normalized orderly generation (provably complete)
- **Normalization:** point 0's six blocks fixed to the canonical star {0,1,2},{0,3,4},{0,5,6},{0,7,8},{0,9,10},{0,11,12} (every STS(13) is relabelable into this form: any point x's star is a perfect matching on the other 12 points; 13·6!·2⁶ relabelings hit the canonical form).
- **Search:** branch on the LOWEST uncovered pair (a,b) — this makes each labeled completion reachable at most once (no reordering duplicates); candidate third points c (both cross-pairs uncovered) are branch-reduced to orbit representatives under **H = Stab(partial) ∩ setwise-stabilizer of {a,b}** — the PROVABLY COMPLETE form: for any system T ⊇ partial with T's block {a,b,c} and any g ∈ H with g(c) = c_r, the relabeled g(T) ⊇ partial + {a,b,c_r}, so every isomorphism class represented at a node stays represented at some child; by induction every class has ≥ 1 leaf.
- **Stabilizer encoding:** the initial Stab(star) = S₂≀S₆, order 46,080, encoded as codes (pairPerm 0..719)·64 + flip 0..63, σ computed on demand (never materialized — the 16 MiB lesson); the child group G' = {σ ∈ G : σ(B_new) ∈ partial'} filtered incrementally down each DFS path.
- **Results (byte-exact):** **41,621 nodes, 560 leaves**; every leaf asserted valid on the spot: exactly 26 blocks, every point degree exactly 6, all 78 pairs covered exactly once (exact cover by construction + asserted).
- NOTE: the pre-compaction session's numbers (41,621 / 560) are reproduced exactly by this independently-written, provably-complete implementation.

### B4b — Pasch counter (definition + fast method, cross-validated)
- **Definition:** a Pasch = 4 blocks whose 6 pairwise intersections are exactly 1 point each and whose union is 6 points (e.g. {a,b,c},{a,d,e},{b,d,f},{c,e,f} up to the two pairings; pairs af/be/cd are covered by OTHER blocks — no STS contradiction, since the 6 points appear in r = 6 blocks each).
- **Fast method:** per ordered pair of blocks sharing exactly point a, with B1 = {a,x,y}, B2 = {a,u,w}: a fire in pairing 1 iff third(x,u) = third(y,w) = f with f ∉ B1∪B2; pairing 2 iff third(x,w) = third(y,u) = f' ∉ B1∪B2. **Each Pasch fires exactly 12× over ordered block pairs.**
- **Validation (definitional 4-subset enumeration = fast fires/12, ALL OK):** Fano plane 7 = 84/12 ✓; AG(2,3) = STS(9) 0 = 0/12 ✓ (anti-Pasch, known); cyclic Netto STS(13) 13 = 156/12 ✓; per-point profile Netto: 6 Pasches through every point (72 fires / 12), definitional = fast ✓.

### B4c — isomorphism dedup: exactly 2 classes
- **Iso test:** propagation-based (assign point images; any block of A with two assigned points forces the third through B's pair→third map; contradictions backtrack with an UNDO TRAIL), budget-limited, self-tested.
- **Pasch buckets (fires/12):** 8 Pasches → 468 leaves; 13 Pasches → 92 leaves; exactly 2 distinct totals.
- **Per-point Pasch profiles (fires/12, sorted):** bucket 8: 3,3,3,3,4,4,4,4,4,4,4,4,4 — profile-equal across all 468; bucket 13: 6×13 — profile-equal across all 92.
- **Iso-vs-fixed-representative:** all 467 members of bucket 8 iso to its rep (max 1,352 steps); all 91 members of bucket 13 iso to its rep (max 169 steps) → each bucket = ONE isomorphism class → **exactly 2 classes among the 560 leaves**.
- **Completeness ⇒ STS(13) = 2 non-isomorphic systems** (every class has ≥ 1 leaf by B4a's lemma; all leaves valid).

### B4d — class identification + automorphism orders
- **Cyclic Netto system** (base blocks {0,1,4},{0,2,7} developed mod 13; 26 blocks; exact cover machine-verified) is isomorphic to the 13-Pasch class rep ✓.
- **|Aut| (machine-counted self-isomorphisms):** 8-Pasch class → **6**; 13-Pasch (Netto) class → **39** (= Z₁₃ ⋊ Z₃, matching the multiplier-3 check).
- **Labeled-count consistency:** 13!/6 = 1,037,836,800 + 13!/39 = 159,667,200 = **1,197,504,000** total labeled STS(13) (13! = 6,227,020,800).

All numbers above are byte-exact outputs of these runs. Receipt for chunk 54c target (3), part 2 — STS(13) = 2. Scratch: 54c-sts13-leaves.txt (560 lines) kept for reproducibility; delete at session close.
