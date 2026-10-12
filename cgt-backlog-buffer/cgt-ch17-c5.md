## Exercises (graded: ●○○ easy · ●●○ moderate · ●●● tough)

**1. (●●○) The twelfth necklace.** Compute the number of 2-color necklaces of length 12 by Burnside, then explain in one sentence why the answer is *not* 2¹²/12. *(Hint: gcd is doing the work — tabulate 2^gcd(12, k) for k = 0..11 before averaging.)*

**2. (●●○) The three-color cube.** Using the cycle-type census 1⁶:1, 2²1²:3, 2³:6, 3²:8, 4·1²:6, compute the number of rotationally distinct 3-colorings of the cube's faces, and verify your answer against the closed form (k⁶+3k⁴+12k³+8k²)/24.

**3. (●○○) Bracelets vs necklaces, at six beads.** A bracelet may be picked up and flipped; a necklace may only be spun. Compute both counts for 2 colors at n = 6 and explain the difference of exactly one orbit: which coloring class merges under the flip?

**4. (●○○) The divisor battery.** Compute τ(60) and φ(60); then prove the identity φ(n) = Σ_{d|n} d·μ(n/d) by Möbius inversion from Σ_{d|n} φ(d) = n. *(All three values are machine-verified in the lab.)*

**5. (●○○) The exhibit that cannot exist.** Show that S(2,3,6) cannot exist by integrality of r; then state the exact congruence gate for STS(v) and where v = 6 fails it. *(The lab's machine proof searched all 15,504 candidate block families and found zero — your job is the two-line reason.)*

**6. (●●○) Fisher at nine.** The lab's census finds exactly 840 labeled STS(9)s, all isomorphic. Compute b and r for STS(9), verify Fisher's inequality b ≥ v with the actual slack, and explain what the slack measures geometrically (the affine plane AG(2,3) has a distinguished line at infinity that the Fano plane does not).

**7. (●●○) A symmetric design.** For PG(2,3): verify from the construction (points = 1-dim subspaces of F₃³) that b = v = 13, and prove that in any projective plane any two *lines* meet in exactly one point — so the design is symmetric: the block-versus-point incidence matrix is square and the dual design is another plane of the same order.

**8. (●●○) Quadruple witnesses.** The lab finds SQS(8) and SQS(10) each unique (one orbit; 30 and 2,520 labeled systems). Compute the pair-multiplicity λ₂ for S(3,4,v) at v = 8 and v = 10 from the counting constants alone, and check your values against the lab's witnesses.

**9. (●●●) The schoolgirls' schedule, verified.** The lab prints a resolvable STS(15): 7 parallel classes of 5 disjoint triples. Prove from the parameters alone that any resolvable STS(15) must have exactly 7 classes of exactly 5 triples each (count block-slots two ways), then verify the lab's printed schedule satisfies: every class partitions all 15 girls; the 35 triples are distinct and each is a line of PG(3,2).

**10. (●●○) Reed–Solomon is MDS.** Prove that the code of evaluations of a + bx at n distinct points of F_q has minimum distance exactly n−1 (hence [n,2,n−1]_q, Singleton-tight), and exhibit the lab's witnesses [4,2,3]₅ and [5,2,4]₅.

**11. (●●○) Two bounds, two witnesses.** Run the Plotkin arithmetic at (7,4): the bound gives 2⌊4/(8−7)⌋ = 8, met by the [7,3,4] simplex (all seven nonzero words weight 4). Then run the Gilbert–Varshamov arithmetic at (10,4): the bound gives 32 ≥ ⌈1024/176⌉ = 6. Verify both denominators (the ball volume 1+10+... at d−1 = 3; the Plotkin floor) and explain why one bound is met *exactly* and the other with a factor of 5 to spare.

**12. (●●○) Octad arithmetic.** The extended binary Golay code has 759 weight-8 words. Show that if their supports form an S(5,8,24), then the count 759 is forced by pure arithmetic: C(24,5)/C(8,5). Compute the number, and verify it equals the weight enumerator's A₈.

### ◆ Pattern-unknown problems (no hints; the diagnosis is the point)

**◆ Problem 1.** Chapter 2's exploration X1 counted 1, 1, 1, 2, 3, 6 tree shapes at n = 6 and deferred the machine. Extend the census to n = 8 — by any method that never produces the same shape twice — and also report the *rooted* count at n = 8.

**◆ Problem 2.** On the partition lattice Π₅ (52 elements), compute μ(0̂, 1̂) directly from the recursion — no formula assumed. Then guess the general pattern for Π_n and check it against Π₄.

**◆ Problem 3.** Chapter 8's [7,4,3] Hamming code has 16 words. Verify the weight distribution [1,0,0,7,7,0,0,1] and prove the perfectness identity 16·8 = 128 = 2⁷ from the distribution — counting, not construction, is the tool the problem wants.

### ◐ Explorations (what you should find, not a number to match)

**◐ Exploration 1 (Bruck–Ryser table).** For each order q = 2..16, classify: ruled out by Bruck–Ryser–Chowla (and why, via the sum-of-two-squares test), silent to it, or (where the answer is known) resolved by other means. You should find exactly two ruled-out orders in this range, one famously silent-then-killed order (q = 10), and the smallest open order.

**◐ Exploration 2 (Keevash's gate, by hand).** Write the three divisibility conditions for S(3,4,n) explicitly as three fractions in n. Evaluate them at n = 10 and n = 12; determine which condition is the binding one at each, and run the census: for which residues mod 6 do all three hold? (The lab's machine census over n = 4..60 confirms the pattern; your job is the hand derivation plus the machine agreement.)

**◐ Exploration 3 (The Mathieu ladder).** Verify by machine arithmetic: M₂₄ = 24·23·22·21·20·48 and its prime factorization; the stabilizer ladder M₂₃ = M₂₄/24, M₂₂ = M₂₃/23, M₁₂ = 12·11·10·9·8, M₁₁ = M₁₂/12; and the block-stabilizer arithmetic |M₂₄|/759 (octads) and |M₁₂|/132 (hexads). Explain why each quotient is an integer, using the design whose blocks are being stabilized.

## Answers to the Exercises

**1.** Burnside over C₁₂: tabulate gcd(12, k) for k = 0..11 — 12, 1, 2, 3, 4, 1, 6, 1, 4, 3, 2, 1 — so the fixed-coloring counts are 4096, 2, 4, 8, 16, 2, 64, 2, 16, 8, 4, 2, summing to 4224, and 4224/12 = **352**. And it is *not* 2¹²/12 = 341.33 because orbits are not the same size: the two constant colorings ride all 12 rotations fixed, and every orbit of size s contributes |G|/s to the sum Σ|Fix| — Burnside's average repairs exactly what naive division breaks. *(Receipt 54runs-1: brute-force canonicalization of all 4096 strings agrees at n = 12, and at every n = 1..12.)*

**2.** k = 3: (729 + 3·81 + 12·27 + 8·9)/24 = (729 + 243 + 324 + 72)/24 = 1368/24 = **57** ✓, matching the machine's brute-force canonicalization (54runs-1).

**3.** Necklaces: Burnside over C₆, rotations k = 0..5 fix 2^gcd(6,k) = 64, 2, 4, 8, 4, 2 — sum 84, and 84/6 = **14**. Bracelets: add the 6 reflections of the dihedral group; n even splits them — 3 axes through opposite bead-pairs (2 fixed beads + 2 swapped pairs = 4 cycles → 16 fixed colorings each) and 3 axes through opposite gaps (3 swapped pairs = 3 cycles → 8 each), reflection total 3·16 + 3·8 = 72; (84 + 72)/12 = **13** ✓ (54runs-9). The merged orbit: the two mirror-image necklaces with no rotational symmetry — e.g. 001011 and its reversal — become a single bracelet under the flip.

**4.** 60 = 2²·3·5 → τ(60) = 3·2·2 = **12**; φ(60) = 60·(1/2)(2/3)(4/5) = **16**. Proof of the identity: from Σ_{d|n} φ(d) = n (both sides count pairs (d, m) with m ≤ d... the standard double count: fractions k/n in lowest terms grouped by denominator d | n), apply Möbius inversion to g(n) = n = Σ_{d|n} f(d) with f = φ: φ(n) = Σ_{d|n} μ(d)·(n/d) = Σ_{d|n} (n/d)·μ(d), equivalently Σ_{d|n} d·μ(n/d) ✓ (all identities machine-verified n ≤ 10⁴, zero mismatches; receipt 54runs-2).

**5.** r = (v−1)/(k−1) = 5/2 — not an integer, so no S(2,3,6) exists. The gate is v ≡ 1 or 3 (mod 6), and v = 6 fails at exactly one leaf: b = 6·5/6 = 5 is an integer, so it is r = 5/2 that kills it — which is precisely why the exhibit is instructive: checking *one* counting constant is not enough to certify existence, but one non-integer is enough to certify non-existence. The lab's exhaustive search over all 15,504 candidate block families returns zero systems — the machine echo of the two-line reason. *(Receipt 54runs-3.)*

**6.** STS(9): b = 9·8/6 = **12** > v = 9 (Fisher slack 3); r = 8/2 = 4. The geometric reading: STS(9) is the affine plane AG(2,3) — PG(2,3) with a line at infinity deleted — so 13 − 1 = 12 lines remain on 13 − 4 = 9 points. Fisher's tight case b = v needed the full symmetric plane; deleting the line at infinity destroys the symmetry and leaves the inequality strict. (The machine census: 840 labeled systems, one isomorphism orbit — receipt 54runs-3.)

**7.** Any two 1-dim subspaces of F₃³ span a unique 2-dim subspace (their sum), so any two points lie on exactly one line; dually, any two 2-dim subspaces intersect in a 1-dim subspace (dimension formula: 2+2−3 = 1), so any two lines meet in exactly one point. The incidence matrix is square (13 = 13) and N^T is the incidence matrix of another S(2,4,13) — the dual plane. Fisher is tight exactly because the blocks, like the points, are pairwise "incident-constant" (any two blocks meet in λ' = 1 points). *(Receipt 54runs-9: all 78 pairs in exactly one of the 13 lines, machine-verified.)*

**8.** Fix a pair P in S(3,4,v). Every triple P ∪ {x} lies in a unique block, whose fourth point is a partner y(x); the partner map x ↦ y is a fixed-point-free involution on the remaining v − 2 points (y(y(x)) = x, since P ∪ {y} ∪ {x} is the same block), so the points pair up and the blocks through P number (v−2)/2: **λ₂ = 3 at v = 8** (three pairs from six points) and **λ₂ = 4 at v = 10** — both confirmed on the lab's witnesses, where every pair lies in exactly 3 (resp. 4) blocks. The same count is the i = 2 case of the design constant λ_i = λ·C(v−i, t−i)/C(k−i, t−i): C(6,1)/C(2,1) = 3 and C(8,1)/C(2,1) = 4. *(Receipts 54runs-5.)*

**9.** Any resolvable STS(15): 35 blocks total (15·14/6); each parallel class partitions 15 points into 15/3 = 5 triples; so the number of classes is 35/5 = **7** — both counts forced, no freedom anywhere. The lab's schedule verifies: each class's 5 triples are pairwise disjoint and cover {1..15}; the 35 triples are distinct; each is {a, b, a XOR b} in the bitmask labeling, i.e., a line of PG(3,2). *(Receipt 54runs-10; the schedule prints Monday..Sunday verbatim.)*

**10.** Two distinct messages (a,b) ≠ (a′,b′) give a nonzero linear polynomial c₀ + c₁x with at most one root among the n evaluation points, so the evaluations agree in at most one position and differ in at least n−1: d ≥ n−1; Singleton gives d ≤ n−1; equality. Witnesses: [4,2,3]₅ (25 words, machine min distance 3) and [5,2,4]₅ (min distance 4) — receipt 54runs-11.

**11.** Plotkin at (7,4): 2d > n (8 > 7) so M ≤ 2⌊d/(2d−n)⌋ = 2·4 = 8; the simplex meets it (7 nonzero words of weight 4; distance between any two = 4 by linearity). GV at (10,4): ball volume Σ_{j=0}^{3} C(10,j) = 1+10+45+120 = 176; A ≥ 1024/176 → 32 ≥ 5.82, so ≥ 6; the greedy construction actually finds 32 words. Why the difference in tightness: Plotkin's averaging argument is *exact* for its witnesses (the simplex saturates the double count), while GV's greedy leaves slack because balls near the packing boundary overlap less than the volume bound pretends. *(Receipts 54runs-6, 54runs-11.)*

**12.** If the 759 octads form S(5,8,24), each octad contains C(8,5) = 56 five-subsets and each of the C(24,5) = 42,504 five-subsets lies in exactly one octad, so 759·56 = 42,504 — and 42,504/56 = **759** ✓ = A₈, the machine's weight-enumerator entry. The arithmetic is airtight in both directions: the design property forces the weight enumerator's A₈, and the lab verifies the design property independently (each of the 42,504 five-subsets in exactly one octad, machine-checked; receipt 54runs-8).

### Answers to the ◆ problems (receipt-backed)

**◆ 1.** Unrooted shapes at n = 8: **23** (multiset closure via the centroid split; independent Prüfer-sequence enumeration of all 8⁶ = 262,144 labeled trees with canonical-form dedup agrees exactly). Rooted shapes at n = 8: **115**. The diagnosis: this is orbit counting where the "group" is all relabelings — Burnside in spirit, canonical-generation in practice. *(Receipt 54runs-1; the machine cross-check is the whole point: two independent engines, one answer.)*

**◆ 2.** μ(0̂, 1̂) on Π₅ = **+24**, computed from the recursion alone — the lab walks the 52-element lattice (|Π₅| = 52, machine-tallied) and the alternating accumulation returns +24. The general pattern it suggests: μ(0̂,1̂) on Π_n = (−1)^{n−1}(n−1)!, and the machine agrees — n = 3: +2, n = 4: −6, n = 5: +24. The diagnosis: Möbius inversion on a genuinely non-numeric poset — the pattern is the incidence algebra, not the numbers. *(Receipt 54runs-2.)*

**◆ 3.** Weight distribution [1,0,0,7,7,0,0,1]: 16 words, weights 0,3,4,7. Perfectness from the distribution: count pairs (c, x) with x within distance 1 of codeword c — equivalently Σ_c (1 + 7) = 16·8 = 128 = 2⁷; a perfect code must satisfy M·(1+n) = 2^n at radius 1, and the [7,4,3] does, exactly. The diagnosis: sphere-packing as a *counting* identity on the weight enumerator — Chapter 8's Delsarte machinery in miniature. *(Receipt 54runs-11.)*

### Findings for the ◐ explorations (receipt-backed)

**◐ 1.** Ruled out by BRC in 2..16: q = 6 and q = 14 (both ≡ 2 mod 4, neither a sum of two squares: 6 = a²+b² has no solution; 14's prime factor 7 ≡ 3 mod 4 appears to an odd power). The silent-then-killed: q = 10 ≡ 2 mod 4 but 10 = 1²+3², so BRC says nothing — non-existence is Lam–Swiercz–Thiel 1989 (coding theory + search). Smallest open: **q = 12** (≡ 0 mod 4, outside BRC entirely). The silent orders that exist: 2, 5, 9, 13 pass BRC (each a sum of two squares); 3, 7, 11, 15 (≡ 3 mod 4) and 4, 8, 16 (≡ 0 mod 4) are silent to BRC. *(Receipt 54runs-9.)*

**◐ 2.** S(3,4,n) conditions: C(n,3)/4, C(n−1,2)/3, (n−2)/2. At n = 10: 120/4 = 30 ✓, 36/3 = 12 ✓, 8/2 = 4 ✓ — admissible (SQS(10) exists and is unique). At n = 12: 220/4 = 55 ✓, but 55/3 ∉ ℤ — inadmissible; the binding condition is the second (pairs through a point). Census n = 4..60: all three hold iff n ≡ 2 or 4 (mod 6) — zero mismatches with Hanani's iff theorem. *(Receipt 54runs-11.)*

**◐ 3.** M₂₄ = 244,823,040 = 2¹⁰·3³·5·7·11·23 (product and factorization both machine-verified); M₂₃ = M₂₄/24 = 10,200,960; M₂₂ = M₂₃/23 = 443,520; M₁₂ = 95,040; M₁₁ = M₁₂/12 = 7,920; |M₂₄|/759 = 322,560; |M₁₂|/132 = 720. Integrality: each quotient counts a stabilizer (point stabilizers by transitivity; octad/hexad stabilizers because the group acts on the block set of the Witt design — 759 octads, 132 hexads — transitively by design automorphism). *(Receipt 54runs-11.)*

---
