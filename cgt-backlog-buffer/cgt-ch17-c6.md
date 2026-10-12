## Computational Lab (verified)

Every run below was executed before a line of the chapter's prose was written; the printed numbers are byte-exact outputs of the recorded runs (receipts 54runs-1..11, kept in the session buffer). Where a code sketch is shown, it is the essence of the engine that produced the receipt — compacted to fit the page, faithful to the algorithm, with the receipt carrying the full record.

### Part 1 — Orbit censuses: necklaces, bracelets, the cube, the trees (Lecture 1)

```typescript
// Necklaces: brute force = canonicalize every 2^n string over all n rotations,
// collect lex-min representatives; Burnside = (1/n)·Σ_{k=0..n−1} 2^gcd(n,k).
// Bracelets: same + the n reflections of the dihedral group; Burnside side:
//   n odd:  reflections fix 2^((n+1)/2) each;  n even: (n/2)·2^(n/2+1) + (n/2)·2^(n/2).
// Cube: the rotation group = closure of the two quarter-turns (F L B R) and
// (U R D L); 24 elements machine-tallied by cycle type on faces:
//   1⁶:1, 2²1²:3, 2³:6, 3²:8, 4·1²:6; orbit count = Σ k^{cycles}/24 both ways.
// Trees: rooted = sorted-multiset closure; unrooted = centroid/bicentroid split;
// cross-check = full Prüfer enumeration n^{n−2} with canonical-form dedup.
```

**Verified output.** Necklaces n = 1..12, brute = Burnside at every n: **2, 3, 4, 6, 8, 14, 20, 36, 60, 108, 188, 352**. Bracelets n = 1..12, brute dihedral = Burnside over D_n at every n: **2, 3, 4, 6, 8, 13, 18, 30, 46, 78, 126, 224**; the necklace/bracelet contrast prints 14 vs 13 at n = 6 and 352 vs 224 at n = 12. Cube: |G| = 24 verified; k = 1..5 face-coloring orbits **1, 10, 57, 240, 800**, brute canonicalization = the closed form (k⁶+3k⁴+12k³+8k²)/24 at every k. Tree shapes n = 1..8: unrooted **1, 1, 1, 2, 3, 6, 11, 23**, rooted **1, 1, 2, 4, 9, 20, 48, 115**; the Prüfer cross-check agrees at every n. *(Receipt 54runs-1, extended by 54runs-9 K1.)*

### Part 2 — The Möbius battery (Lecture 2)

```typescript
// Divisor lattice, every n ≤ 10⁴: Σ_{d|n} 1 = τ(n); Σ_{d|n} μ(d) = [n=1];
// Σ_{d|n} d·μ(n/d) = φ(n); Σ_{d|n} φ(d) = n. Boolean B_k, k ≤ 6: μ(∅,S) = (−1)^{|S|}.
// Partition lattice Π_n, n ≤ 5: full element tally + μ(0̂,1̂) by the recursion
//   μ(x,y) = −Σ_{x≤z<y} μ(x,z)   // exclude z = y; accumulate from x upward
```

**Verified output.** All four divisor identities: **zero mismatches over every n ≤ 10,000** (spot values τ(60) = 12, φ(60) = 16, φ(100) = 40). Boolean: μ(∅, S) = (−1)^{|S|} on all intervals of B_6 (all 64 subsets walked). Partition lattices: **|Π_n| = 1, 2, 5, 15, 52** and **μ(0̂,1̂) = 1, −1, 2, −6, 24** = (−1)^{n−1}(n−1)! at every n. Implementation scars on the receipt: the recursion direction (μ(x,y) = −Σ_{x≤z<y} μ(x,z), accumulated upward from x — the first draft ran it downward and produced garbage the identity checks caught), the z = y self-inclusion trap, and the φ-sieve initialization (φ[m] = m before the sieve starts). *(Receipt 54runs-2.)*

### Part 3 — Steiner triple systems: the small census, the exhibit, the fork (Lectures 3–4)

```typescript
// STS(v) labeled census: exact cover of all C(v,2) pairs by triples, with
// propagation + undo; isomorphism by canonical relabeling.
// S(2,3,6): exhaustive over all C(20,5) = 15,504 candidate block families.
// STS(13): orderly generation — branch on the lowest uncovered pair; candidates
// canonicalized under Stab(partial) ∩ the pair-stabilizer; every leaf valid.
// Pasch counter: the four-triple quadrilateral, counted per system.
```

**Verified output.** STS(7): **30 labeled systems**, one isomorphism class — the Fano plane unique (7 Pasches). STS(9): **840 labeled**, one orbit (0 Pasches — AG(2,3)). S(2,3,6): **0 of 15,504** — the non-existence machine proof (r = 5/2 the obstruction). STS(13): the orderly search visits **41,621 nodes and 560 leaves, all valid**; leaves sort into Pasch buckets **468 (8 Pasches) + 92 (13 Pasches)**; two isomorphism classes with **|Aut| = 6 and 39**; labeled counts **1,037,836,800 + 159,667,200 = 1,197,504,000**. Fisher on every found system: b ≥ v, tight at 7, slack at 9, 13. *(Receipts 54runs-3, 54runs-4.)*

### Part 4 — Quadruple systems and the schoolgirls (Lecture 4)

```typescript
// SQS(v) labeled census: exact cover of all C(v,3) triples by quadruples,
// propagation + undo; uniqueness = one orbit under the full symmetric group;
// |Aut| counted per representative (labeled total = v!/|Aut| when unique).
// PG(3,2): points = nonzero 4-bit vectors 1..15; lines {a,b,a XOR b}; spreads =
// 5 disjoint lines covering all 15 points (masks ≤ 15 bits — the 32-bit lesson:
// 35-bit line masks wrapped in the first draft and printed 52 spreads, an
// impossibility its own arithmetic exposed; fixed masks → 56).
// Parallelism: 7 spreads pairwise disjoint as line sets, covering all 35 lines.
```

**Verified output.** SQS(8): **30 labeled systems, one orbit — unique; |Aut| = 1,344 = AGL(3,2)** (30·1,344 = 8! exactly). SQS(10): **2,520 labeled, one orbit — Barrau's 1908 uniqueness machine-confirmed; |Aut| = 1,440 = PΓL(2,9)** (2,520·1,440 = 10! exactly; the remembered "15,120 labeled / |Aut| 240" was WRONG and the machine overruled it — recorded on the receipt). PG(3,2): 35 lines form STS(15) — all 105 pairs in exactly one line; **56 spreads**; the resolvable parallelism FOUND: 7 parallel classes × 5 disjoint triples, all 35 lines used once, every class a partition of the 15 points — the schoolgirl schedule:

- Mon: {1,2,3} {4,8,12} {5,10,15} {6,11,13} {7,9,14}
- Tue: {1,4,5} {2,8,10} {3,13,14} {6,9,15} {7,11,12}
- Wed: {1,6,7} {2,9,11} {3,12,15} {4,10,14} {5,8,13}
- Thu: {1,8,9} {2,12,14} {3,5,6} {4,11,15} {7,10,13}
- Fri: {1,10,11} {2,13,15} {3,4,7} {5,9,12} {6,8,14}
- Sat: {1,12,13} {2,4,6} {3,9,10} {5,11,14} {7,8,15}
- Sun: {1,14,15} {2,5,7} {3,8,11} {4,9,13} {6,10,12}

*(Receipts 54runs-5, 54runs-10.)*

### Part 5 — Code bounds: greedy, simplex, puncturing (Lecture 5)

```typescript
// GV greedy: start from any word, repeatedly add any word at distance ≥ d from
// all chosen; halt when the radius-(d−1) balls cover the cube.
// Plotkin witnesses: (6,4) = 4 and (7,4) = 8 — the simplex built as the dual of
// the Hamming code (all 7 nonzero codewords weight 4).
// Binary MDS census n ≤ 7: canonical subspace enumeration with RREF keys
// (post-elimination rows — a pre-elimination key bug was caught by a Gaussian
// cross-check on the recorded first version).
// RS over F₅: evaluate a+bx at 4 and at 5 field points; pairwise distances.
// Hamming [7,4,3]: parity-check columns = the 7 nonzero 3-bit vectors;
// syndrome s_j = XOR_i (w_i AND column_i[j]) — the first draft ANDed instead
// of XOR-accumulating and returned 64 bogus codewords (its own perfectness
// check, 64/128, exposed it).
```

**Verified output.** GV greedy: (7,3): **16 ≥ ⌈128/29⌉ = 5**; (8,3): **16 ≥ 7**; (10,4): **32 ≥ ⌈1024/176⌉ = 6**; (12,4): **128 ≥ ⌈4096/299⌉ = 14**. Plotkin: **(6,4) = 4** and **(7,4) = 8** met exactly, the simplex saturating. Binary MDS census n ≤ 7: subspace counts = the Gaussian binomials **35, 155, 651, 1,395, 2,667, 11,811** (n = 2..7), maximum distance strictly below Singleton for every nontrivial dimension; only the three trivial families reach equality. RS over F₅: **[4,2,3]₅** — 25 words, machine minimum pairwise distance exactly 3 = Singleton; **[5,2,4]₅** — distance 4 = Singleton. Hamming [7,4,3]: **16 codewords, d = 3, A = [1, 0, 0, 7, 7, 0, 0, 1], perfect — 16 radius-1 balls of size 8 partition F₂⁷ (16·8 = 128 = 2⁷)**. Keevash arithmetic: S(3,4,10) admissible (30, 12, 4 all integers), S(3,4,12) fails at 55/3; census n = 4..60 matches n ≡ 2, 4 (mod 6) exactly. *(Receipts 54runs-6, 54runs-11.)*

### Part 6 — The Golay codes and their designs (Lecture 6)

```typescript
// Ternary: Φ₁₁ = 1+x+…+x¹⁰ over F₃ factors into two monic quintics
//   (x⁵+x⁴+2x³+x²+2)(x⁵+2x³+x²+2x+2) — machine-factored, not remembered;
// either generates [11,6,5]: 729 words, perfect (729 balls of radius 2,
// volume 1+2·11+4·55 = 243, partition F₃¹¹: 729·243 = 3¹¹).
// Extension: one overall-parity coordinate → [12,6,6], self-dual.
// Binary: (x²³+1)/(x+1) over F₂ factors into exactly two monic degree-11
// polynomials g₀, g₁ (machine-found); either generates [23,12,7]: 4,096 words,
// min pairwise distance 7 verified over all 8,386,560 pairs; perfect
// (4096·V(23,3) = 4096·2048 = 2²³). Extension → [24,12,8], self-dual.
// Design extraction: supports of constant-weight words; coverage test = every
// 5-subset of 24 coordinates in exactly one octad support.
```

**Verified output.** Ternary [11,6,5]₃ (both factors): **A = 1, 132, 132, 330, 110, 24** at weights 0, 5, 6, 8, 9, 11; **132 weight-5 words on 66 supports = S(4,5,11)** (every 4-subset in exactly one support); the [12,6,6]₃ extension: **A = 1, 264, 440, 24**, self-dual, **132 weight-6 supports = S(5,6,12)**. Binary [23,12,7]₂ (both factors g₀ = x¹¹+x⁹+x⁷+x⁶+x⁵+x+1, g₁ = x¹¹+x¹⁰+x⁶+x⁵+x⁴+x²+1): **A = 1, 253, 506, 1288, 1288, 506, 253** at weights 0, 7, 8, 11, 12, 15, 16, perfect; the [24,12,8]₂ extension: **A = 1, 759, 2576, 759, 1** at 0, 8, 12, 16, 24, self-dual; **759 octads, and each of the C(24,5) = 42,504 coordinate 5-subsets lies in exactly one octad = S(5,8,24)**. Mathieu arithmetic: **M₂₄ = 244,823,040 = 2¹⁰·3³·5·7·11·23**; M₂₃ = 10,200,960 = M₂₄/24; M₂₂ = 443,520 = M₂₃/23; M₁₂ = 95,040; M₁₁ = 7,920 = M₁₂/12; |M₂₄|/759 = 322,560; |M₁₂|/132 = 720. *(Receipts 54runs-7, 54runs-8, 54runs-11.)*

## Revision History & Verification Notes

**Machine-verification campaign (before a line of prose was installed).** Eleven recorded batches — receipts 54runs-1..11, kept in the session buffer — with every quantitative claim in this chapter traceable to one:

1. **Orbit censuses** (runs 1, 9): necklaces and bracelets n = 1..12 brute-versus-Burnside agreement at every n; the cube's 24 rotations, cycle-type census, and the k = 1..5 orbit counts 1, 10, 57, 240, 800; tree shapes 1, 1, 1, 2, 3, 6, 11, 23 with the Prüfer cross-check (rooted 115 at n = 8).
2. **Möbius battery** (run 2): the four divisor identities over all n ≤ 10⁴ (zero mismatches); Boolean μ on B_6; the partition lattices to Π₅ with μ(0̂,1̂) = 1, −1, 2, −6, 24.
3. **Small designs** (runs 3, 4): STS(7) 30/1, STS(9) 840/1; S(2,3,6) = 0 of 15,504 — the machine non-existence proof; STS(13) = 2 by orderly generation over 41,621 nodes / 560 leaves with the Pasch buckets 468 + 92, |Aut| 6 and 39, labeled total 1,197,504,000; Fisher on every system.
4. **Quadruple systems + schoolgirls** (runs 5, 10): SQS(8) 30 labeled / unique / |Aut| = 1,344; SQS(10) 2,520 / unique / |Aut| = 1,440; PG(3,2): 35 lines = STS(15), 56 spreads, the full 7-class resolvable parallelism verified class by class.
5. **Code bounds** (runs 6, 11): GV greedy witnesses at four parameter points; Plotkin tight at (6,4) = 4 and (7,4) = 8 simplex; the binary MDS census n ≤ 7 (Gaussian cross-checked); Reed–Solomon [4,2,3]₅ and [5,2,4]₅ Singleton-tight; Hamming [7,4,3] with distribution [1,0,0,7,7,0,0,1] and perfectness 128/128.
6. **The Golay bridge** (runs 7, 8, 11): both Φ₁₁ factors → [11,6,5]₃ perfect with A = 1, 132, 132, 330, 110, 24, 66 supports = S(4,5,11), extension [12,6,6]₃ self-dual with 132 supports = S(5,6,12); both degree-11 binary factors → [23,12,7]₂ perfect (A₇ = 253, A₈ = 506, A₁₁ = A₁₂ = 1288, A₁₅ = 506, A₁₆ = 253), extension [24,12,8]₂ self-dual with A = 1, 759, 2576, 759, 1, 759 octads = S(5,8,24) with all 42,504 five-subsets covered exactly once; the Mathieu order ladder.
7. **The BRC arithmetic** (run 9): PG(2,3) = S(2,4,13) with all 78 pairs machine-checked and b = v = 13; the sum-of-two-squares census q = 2..16.

**The scars, kept on display.** The campaign's own oracles caught, before any number reached prose: the μ-recursion direction and the z = y self-inclusion (run 2's identity checks); the RREF key bug in the MDS census (a Gaussian cross-check on recorded subspaces); the ternary synthetic-division sign error — a negacyclic twin that passed the [11,6,5] test but whose extension failed self-duality, and the run refused to proceed past the failed check (run 7); the hand-transcribed binary factor that dropped its leading x¹¹ — the machine-found factorization was right and the transcription wrong (run 8); the SQS(10) remembered figures (15,120 labeled / 240) that the machine overruled with 2,520 / 1,440 (run 5) — receipts, not memory; the 32-bit bitwise mask trap, hit for the third time in the Atlas at the PG(3,2) spread census — 35-bit line masks wrapped at bit 32 and printed 52 spreads, and the tell was arithmetic, not visual: line-transitivity forces every line into equally many spreads, so 5·(#spreads) = 35·(per-line count) and the spread count must be a multiple of 7; 52 is not; fixed with short masks → 56 (run 10); the PG(2,3) collinearity test — the det≡0 shortcut and the affine-proportionality shortcut were both wrong (projective points live on representatives up to scaling; the rank-2 test is the correct one) (run 9); the Hamming syndrome AND-for-XOR wiring bug, exposed by its own perfectness counter (run 11); and the Mathieu M₂₃ product with a stray factor of 4, exposed by the M₂₄/24 cross-check line (run 11).

**Canon pins (verified before authoring).** Burnside's lemma: Cauchy 1845 / Frobenius 1887; Burnside's 1897 textbook (Stigler's law recorded). Pólya: Redfield 1927 (priority), Pólya 1937 ("Kombinatorische Anzahlbestimmungen für Gruppen, Graphen und chemische Verbindungen"). Rota, "On the foundations of combinatorial theory I. Theory of Möbius functions", *Z. Wahrscheinlichkeitstheorie verw. Gebiete* 2 (1964), 340–368. Kirkman 1846 (solving Woolhouse 1844; the journal volume is 1847 — cited "Kirkman 1846/47"); Steiner 1853; STS existence iff v ≡ 1, 3 (mod 6) (Bose 1939, Skolem 1958); Kirkman's schoolgirl problem 1850; Sylvester's extension — Denniston, *Discrete Math.* 9 (1974), 229–233. Fisher, "An examination of the different possible solutions of a problem in incomplete blocks", *Annals of Eugenics* 10 (1940), 52–87; Bose's alternative proof (Chapter 6's dual presentation). Bruck–Ryser 1949; Chowla–Ryser 1950; order 10: Lam–Swiercz–Thiel 1989; order 12 open. STS(19) = 11,084,874,829: Kaski–Östergård 2004 (Stinson–Ferch 1985 the forerunner). Wilson, "An existence theory for pairwise balanced designs" I–III (early 1970s); Keevash, "The existence of designs", arXiv:1401.3665 (2014). Hanani 1960 (*Canad. J. Math.* 12, 145–157) and 1963 (15, 702–722); Barrau 1908 (uniqueness of S(3,4,8) and S(3,4,10)); SQS(16) = 1,054,163; S(4,5,v) unique at 11, smallest open 21. Singleton 1964 (*IEEE Trans. Inf. Theory* 10(2), 116–118; earlier proofs Joshi 1958, Komamiya 1953 — priority recorded); MDS conjecture: Segre 1955; prime case Ball 2012 (*J. Eur. Math. Soc.* 14, 733–748); Ball–De Beule 2012 (*Des. Codes Cryptogr.* 65, 5–14). Plotkin 1960 (*IRE Trans. Inf. Theory* 6(4), 445–450; Chapter 8 owns the Delsarte-certificate form — cross-referenced, not re-proved). Gilbert 1952 (*Bell System Tech. J.* 31(3), 504–522); Varshamov 1957 (*Dokl. Akad. Nauk SSSR* 117, 739–741). Golay 1949 ("Notes on Digital Coding", *Proc. IRE* 37, 657); Virtakallio 1947 (the football-pool magazine Veikkaaja — priority recorded); Berlekamp's "best single published page" verdict. Assmus–Mattson, "New 5-designs", *J. Combin. Theory* 6 (1969), 122–151. Mathieu M₂₄/M₁₂ 5-transitivity and the CFSG uniqueness of the Mathieu groups among 4-transitive groups — cited. Cross-references: Chapter 2 (Cayley's formula, the X1 tree-shape exploration, "Pólya's machine" named there), Chapter 6 (Fisher's inequality two ways — the Gram determinant route and Bose's argument), Chapter 8 (the Hamming cube, the [7,4,3] distribution, Delsarte's program).

**The honest ledger.** Proved in the text: Burnside's lemma; Pólya's theorem (from the fixed-point form); the divisor Möbius inversion formula and the poset version via the incidence algebra; the design counting constants (double counting); the v ≡ 1, 3 (mod 6) necessity and the S(2,3,6) non-existence; the projective-plane duality argument (dimension formula); the resolvability parameter count (7 classes of 5); the Singleton bound (puncturing); the Plotkin bound (averaging, the boundary case stated); the Gilbert–Varshamov bound (greedy covering); the RS distance argument; the octad arithmetic (759·56 = 42,504). Stated with proof cited, not given: the STS existence theorem (Bose/Skolem); Fisher's inequality (Chapter 6); Bruck–Ryser–Chowla; the Lam–Swiercz–Thiel order-10 result; Wilson's and Keevash's theorems; Hanani's iff theorem; Barrau's uniqueness; the MDS conjecture and Ball's prime-case theorem; the Assmus–Mattson theorem; the CFSG 4-transitivity classification. Computed, not proved: every census, witness, factorization, and schedule in the lab — reproducible bit for bit from the receipts. The four proposed pattern-registry entries (Symmetry averaging, Möbius inversion, Double-counting/divisibility, Words-as-designs) are filed at ship.

---

**Status:** 🟩 Feynman edition — installed (session 54, chunks 54a–54f: session open, canon pins, verification campaign batches 1–11, design lock, authoring, assembly + install). The web edition `cgt-ch17-web` and the .html export follow at close. No claim in this chapter predates its receipt.
