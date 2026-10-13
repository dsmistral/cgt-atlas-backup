# Batch I - Algebraic, polynomial and set-system methods (gathered and mined)

Session chunk 9, 2026-10-13. All 12 papers metadata-verified; move descriptions at flagged-sketch level from publisher pages, located open copies, and general knowledge; zero paywalled fetches (scope rule unused).

## Verification table

| ID | Verified citation | Corrections vs seed |
|----|------------------|---------------------|
| I1 | Sperner, Math. Z. 27: 544-548 (1928), DOI 10.1007/BF01171114 | none; OPEN EUDML copy located |
| I2 | Erdos-Ko-Rado, "Intersection theorems for systems of finite sets", Quart. J. Math. Oxford 12(1): 313-320 (1961), DOI 10.1093/qmath/12.1.313 | TITLE corrected (seed: "An intersection theorem for finite sets"); YEAR corrected 1938 -> 1961 (essentially completed 1938, published 1961; story verified via the historical survey arXiv:0808.0774); OPEN renyi.hu PDF located |
| I3 | Ray-Chaudhuri-Wilson, "On t-designs", Osaka J. Math. 12(3): 737-744 (1975), MR0392624 | none; seed "verify" flags resolved (venue and title confirmed); Project Euclid page located |
| I4 | Frankl-Wilson, "Intersection theorems with geometric consequences", Combinatorica 1(4): 357-368 (1981), DOI 10.1007/BF02579457 | none; seed title confirmed on the SpringerLink page |
| I5 | Frankl-Rodl, "Forbidden intersections", Trans. Amer. Math. Soc. 300(1): 259-286 (1987), MR0871675 | none; seed venue "verify" flag resolved; OPEN AMS PDF located |
| I6 | Alon-Tarsi, "Colorings and orientations of graphs", Combinatorica 12(2): 125-134 (1992), DOI 10.1007/BF01204715 | none; OPEN Springer PDF located |
| I7 | Alon, "Combinatorial Nullstellensatz", Combin. Probab. Comput. 8(1-2): 7-29 (1999) | none; Cambridge Core article page verified |
| I8 | Dvir, "On the size of Kakeya sets in finite fields", J. Amer. Math. Soc. 22(4): 1093-1097 (2009), DOI 10.1090/S0894-0347-08-00607-3, arXiv:0803.2336 | YEAR corrected 2008 -> 2009 (electronic publication June 2008, print issue 2009; arXiv posted March 2008); OPEN AMS PDF located |
| I9 | Croot-Lev-Pach, "Progression-free sets in Z_4^n are small", Ann. of Math. (2) 185(1): 331-337 (2017), DOI 10.4007/annals.2017.185.1.7, arXiv:1605.01506 | none; seed arXiv-2016 note resolved (posted May 2016); OPEN Annals PDF located |
| I10 | Ellenberg-Gijswijt, "On large subsets of F_q^n with no three-term arithmetic progression", Ann. of Math. (2) 185(1): 339-343 (2017), DOI 10.4007/annals.2017.185.1.8, arXiv:1605.09223 | none; OPEN Annals PDF located |
| I11 | Delsarte, "An algebraic approach to the association schemes of coding theory", Philips Research Reports Supplement no. 10 (1973) | none; OPEN scanned copy located (pearl-hifi Philips archive) |
| I12 | Marcus-Tardos, "Excluded permutation matrices and the Stanley-Wilf conjecture", J. Combin. Theory Ser. A 107(1): 153-160 (2004), DOI 10.1016/j.jcta.2004.04.002 | none; OPEN author PDF (Marcus page) + UMN seminar scan located |

## Pattern census (Atlas P-IDs firing in this batch)

| P-ID | Fires in | Notes |
|------|----------|-------|
| P22 polynomial method | I4, I6, I7, I8, I9, I10 | the designed flagship: six firings spanning 1981-2017 - Frankl-Wilson multilinear polynomials, Alon-Tarsi graph-polynomial coefficient, the Nullstellensatz manifesto, Dvir's one-page Kakeya proof, CLP over Z_4, slice rank. The Nullstellensatz -> Kakeya -> CLP -> slice-rank lineage lives inside one batch (teaching arc). |
| P19 rank / linear algebra | I3, I4, I10, I11 | FIRST GENUINE IN-CORPUS FIRINGS of P19 (after the H3/H10 hypothesis misses): Ray-Chaudhuri-Wilson polynomial independence, Frankl-Wilson rank bound, Ellenberg-Gijswijt slice rank (tensor rank), Delsarte eigenvalue/LP algebra |
| P37 duality | I11 | third family firing: E4 (planar duality) -> H10 (Konig minimax) -> I11 (LP duality in the Delsarte bound); the family note widens from graph duality to general primal-dual arguments |
| P8 extremal/optimization | I2, I5 | the extremal-set-theory backbone: star maximality (I2), forbidden-intersection bound (I5) |
| P10 averaging | I5 | the honest engine of Frankl-Rodl: sphere-averaging/anticode argument over {+1,-1}^n encodings |
| P11 explicit construction | I4 | secondary: the Frankl-Wilson graphs deliver explicit Ramsey lower bounds (deterministic constructions from a counting bound) |
| P9 pigeonhole | I1 (partial) | Sperner's push-toward-the-middle replacement argument |
| P23 compression / shifting | I1 (partial) | the replacement step is shifting-flavored but credited partial only; expected at I2 and I12 too but MISSED there (honest) |
| P4 recurrence / induction | I2, I12 | I2's original induction/case engine; I12's critical-matrix induction (the whole proof, remarkably elementary) |
| P15 coloring | I6 | topical application: list coloring via orientation coefficients (the Alon-Tarsi number) |

## Honest hypothesis-test results (the batch's yield)

- I1 P23 PARTIAL (expected): the original engine is a replacement argument, not compression; the clean LYM proof is retrospective (Lubell-Yamamoto-Meshalkin) - mirror of the H1 Turan treatment.
- I2 P20 MISSED (expected): the original engine is induction + case analysis; shifting proofs and Katona's circle method are retrospective. P8 confirmed.
- I3 P24 MISSED (expected): no Kruskal-Katona shadow pricing despite the shadow-adjacent statement. P19 confirmed - the first genuine in-corpus firing.
- I5 P19 AND P30 BOTH MISSED (both expected): the richest miss of the batch - the natural linear-algebra engine (suggested by I3/I4) does NOT prove forbidden intersections; the original engine is sphere averaging + anticode bounds (P10), with later re-proofs via dependent random choice recorded in the survey literature.
- I11 P40 MISSED (expected): Delsarte's algebra is spectral/LP, not incidence-Mobius. P19 confirmed; P37 fires as a third family (LP duality).
- I12 P23 MISSED (expected): the Stanley-Wilf bound is pure structural induction; no compression appears. P4 confirmed.
- I4 P19 AND P22 BOTH CONFIRMED (both expected) - the flagship double hit; I10 P19 AND P22 both confirmed (slice rank = tensor rank + polynomial method).

## New-pattern candidates and gate status after nine batches

1. No new candidates this batch. Gate status unchanged: CAND-A1/A2/A3 crossed; CAND-A4 unfired in-corpus (watch M); CAND-B5/C1/G1 synthesis calls.
2. Silent-registry ledger: no NEW silent patterns gain first evidence this batch; P37 gains a third family firing (I11 LP duality). Full ledger: P28 (B1/B2), P29 (B4), P33 (F5/F6/F7), P34 (E2/E6; H6/H7/H8), P37 (E4; H10; I11), P40 (C5), P30 (G1), P31 (G5/G8/G9/G10/G11), P32 (G4), P38 (H10 via companion). P20 and P24 remain silent (I2, I3, I12 misses) - their designed home is Batch K; watch K.
3. New watch-note: slice rank (I9/I10) - a face of P19/P22 rather than a P43+ candidate; synthesis decides whether the Atlas P19/P22 entries should name it explicitly.
4. Kempe-chain/fan recoloring watch-item: still silent - the Alon-Tarsi engine (I6) is algebraic coefficient counting, not Kempe chains. Remaining coloring-paper supply in J-M is scarce; likely dies at synthesis (recorded).
5. Engine contrasts recorded for teaching: (a) I2 - one theorem, three engines (original induction/case analysis vs retrospective shifting vs Katona's circle method); (b) I3/I4 vs I5 - the rank/polynomial engine handles many-allowed-intersections theorems but NOT the single-forbidden-intersection theorem, where averaging takes over; (c) I7 -> I8 -> I9 -> I10 - the polynomial method's coming-of-age arc (Nullstellensatz manifesto -> one-page Kakeya -> ring-valued CLP -> slice rank) inside one batch; (d) I12 - an elementary critical-matrix induction cracks a conjecture that had resisted generating-function machinery.

## Verification levels statement

Metadata: web-verified (sources per paper; Delsarte 1973 is a print Philips supplement - citation pinned via the publisher-archive scan). Moves: flagged-sketch summaries. Zero full-text fetches. Open copies located: I1 (EUDML), I2 (renyi.hu), I5 (AMS), I6 (Springer), I8 (AMS), I9/I10 (Annals), I11 (pearl-hifi archive), I12 (author page + UMN scan).
