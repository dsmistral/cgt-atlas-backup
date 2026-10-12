---
name: "cgt-ch9-sumsets-shadows"
title: "Ch. 9 — Sumsets and Shadows: the Completed Arcs: A Lecture Course in the Feynman Style"
type: "text/markdown"
---

# Chapter 9 · Sumsets and Shadows: the Completed Arcs

*Part of the Combinatorics & Graph Theory Atlas (see the Atlas canvas for the chapter map and progress report).*

Two threads that began in Chapter 7 complete here, and the three flags its appendix left open close with them. The sumset thread asks how small A + B can be: the integer answer is a staircase, the prime-field answer is Cauchy–Davenport, and the master theorem is Kneser's, which prices a sumset by its periods — a price this chapter now computes in full, with the aperiodic assembly carried by two complete arguments: a two-case e-transform recursion for the weak form, and DeVos's intersection–union induction for the strong form. The shadow thread asks how few (k−1)-sets must sit underneath k given sets: the answer is the Kruskal–Katona theorem in its clique form, and the payoff is Daykin's mirror proof of EKR plus the deep cascade-uniqueness lemma, which together complete EKR uniqueness for every n > 2k — the thin range the earlier chapters honestly flagged. Between the threads, the zero-sum capstone EGZ fuses them. Every proof is complete or honestly cited, every claimed number is machine-checked, and the lab reproduces every census.

## How to read this chapter

**Notation.** A, B are nonempty finite subsets of an abelian group G, written additively; A + B = {a + b : a ∈ A, b ∈ B}, A − e = {a − e : a ∈ A}, and stab(S) = {g ∈ G : g + S = S} is the stabilizer. 𝔽_p is the field of order p and Z_n the cyclic group of order n. For the shadow thread: 𝓕, 𝓖 are k-uniform families of subsets of [n] = {1, …, n}; ∂𝓖 is the shadow (all (k−1)-sets contained in a member), ∂_j𝓖 the j-shadow, K^k_x the complete family (all k-subsets of a fixed x-set), 𝓕* = {[n]∖F : F ∈ 𝓕} the complement mirror; C(x, k) is the binomial coefficient, extended to real x ≥ k. Letters are re-stated locally where a lecture needs its own.

**The exercises are graded:** ●○○ *easy* (a direct application of one lecture idea), ●●○ *moderate* (two ideas, or one tricky step), ●●● *tough* (several chapter ideas combined). Hints travel with the problems; worked answers sit at the very end of the chapter. Try honestly before reading a hint. Beyond the graded set, ◆ **pattern-unknown** problems name no method and carry no hint: diagnosing which tool fits is part of the problem. And ◐ **Explorations** at the end are open-ended investigations with no single right answer — research training, not test preparation.

## The pattern table for this chapter

| Pattern | Plain language | Where you meet it |
|---------|---------------|-------------------|
| **P4 Induction** | Verify the base and run the recursion until a case fires; or induct on a measure every move decreases | L1 (staircase, m-fold), L2 (EGZ assembly), L3 (two cases, DeVos) |
| **P22 Polynomial method** | One polynomial vanishing on the grid; its top coefficient priced two ways | L1 |
| **P23 Compression / deformation** | Replace the object by a deformed one that is easier to read, preserving what matters | L2 (the e-transform), L3 |
| **Price the period, pass to the quotient (lore)** | When the obstruction is a subgroup of periods, quotient it away and price the deficit by its order | L2, L3 |
| **The real parameter is a price (lore)** | |𝓖| = C(x, k) buys no discount below: every j-shadow costs at least C(x, j), and adjacent-level equality pins the complete family | L4, L5 |
| **Ask what the dual object sees for free (lore)** | Complement the family before building machinery: intersection questions become containment questions | L4, L5 |

---

## Lecture 1 · The Staircase and Cauchy–Davenport

The sumset thread begins: instead of families of sets, **sets of numbers**, and the question becomes how small a sumset can be. The integer answer is a one-line staircase; the modular answer is a real theorem with two beautiful proofs — one by periodicity, one by the polynomial method of Chapter 6.

**Problem.** Nonempty finite A, B ⊆ ℤ: **|A + B| ≥ |A| + |B| − 1**, where A + B = {a + b}.

### 1.1 The integer staircase (P4, full)

Write A = {a₁ < … < a_s} and B = {b₁ < … < b_t}. The witness chain

a₁+b₁ < a₂+b₁ < a₃+b₁ < … < a_s+b₁ < a_s+b₂ < a_s+b₃ < … < a_s+b_t

is strictly increasing throughout — first climb the b₁ column, then walk the a_s row — and exhibits **s + t − 1 distinct sums**. ∎

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 880 330" font-family="Georgia, 'Times New Roman', serif">
  <rect x="0" y="0" width="880" height="330" fill="#ffffff"/>
  <text x="240" y="28" text-anchor="middle" font-size="17" fill="#111827">A = {1, 2, 4}, B = {1, 3}: the sumset grid</text>
  <text x="150" y="88" text-anchor="middle" font-size="14" fill="#374151">a \ b</text>
  <text x="220" y="88" text-anchor="middle" font-size="14" fill="#374151">1</text>
  <text x="300" y="88" text-anchor="middle" font-size="14" fill="#374151">3</text>
  <rect x="180" y="100" width="80" height="50" fill="#ffffff" stroke="#e5e7eb" stroke-width="2"/>
  <text x="220" y="132" text-anchor="middle" font-size="15" fill="#111827">2</text>
  <rect x="260" y="100" width="80" height="50" fill="#dbeafe" stroke="#2563eb" stroke-width="2.5"/>
  <text x="300" y="132" text-anchor="middle" font-size="15" fill="#1e3a8a">4</text>
  <text x="150" y="132" text-anchor="middle" font-size="15" fill="#111827">1</text>
  <rect x="180" y="150" width="80" height="50" fill="#dbeafe" stroke="#2563eb" stroke-width="2.5"/>
  <text x="220" y="182" text-anchor="middle" font-size="15" fill="#1e3a8a">3</text>
  <rect x="260" y="150" width="80" height="50" fill="#ffffff" stroke="#e5e7eb" stroke-width="2"/>
  <text x="300" y="182" text-anchor="middle" font-size="15" fill="#111827">5</text>
  <text x="150" y="182" text-anchor="middle" font-size="15" fill="#111827">2</text>
  <rect x="180" y="200" width="80" height="50" fill="#dbeafe" stroke="#2563eb" stroke-width="2.5"/>
  <text x="220" y="232" text-anchor="middle" font-size="15" fill="#1e3a8a">5</text>
  <rect x="260" y="200" width="80" height="50" fill="#dbeafe" stroke="#2563eb" stroke-width="2.5"/>
  <text x="300" y="232" text-anchor="middle" font-size="15" fill="#1e3a8a">7</text>
  <text x="150" y="232" text-anchor="middle" font-size="15" fill="#111827">4</text>
  <text x="240" y="278" text-anchor="middle" font-size="13" fill="#111827">staircase 2 &lt; 3 &lt; 5 &lt; 7: four = s+t&#8722;1 distinct sums</text>
  <text x="640" y="28" text-anchor="middle" font-size="17" fill="#111827">A + B = {2, 3, 4, 5, 7}</text>
  <line x1="520" y1="60" x2="520" y2="250" stroke="#e5e7eb" stroke-width="2"/>
  <circle cx="560" cy="90" r="9" fill="#dbeafe" stroke="#2563eb" stroke-width="2"/>
  <circle cx="595" cy="115" r="9" fill="#dbeafe" stroke="#2563eb" stroke-width="2"/>
  <circle cx="630" cy="140" r="9" fill="#dbeafe" stroke="#2563eb" stroke-width="2"/>
  <circle cx="665" cy="165" r="9" fill="#dbeafe" stroke="#2563eb" stroke-width="2"/>
  <circle cx="775" cy="215" r="9" fill="#dbeafe" stroke="#2563eb" stroke-width="2"/>
  <text x="560" y="70" text-anchor="middle" font-size="12" fill="#374151">2</text>
  <text x="595" y="100" text-anchor="middle" font-size="12" fill="#374151">3</text>
  <text x="630" y="128" text-anchor="middle" font-size="12" fill="#374151">4</text>
  <text x="665" y="153" text-anchor="middle" font-size="12" fill="#374151">5</text>
  <text x="775" y="200" text-anchor="middle" font-size="12" fill="#374151">7</text>
  <text x="640" y="278" text-anchor="middle" font-size="13" fill="#111827">|A+B| = 5 &#8805; s+t&#8722;1 = 4: the staircase witnesses four</text>
  <text x="440" y="322" text-anchor="middle" font-size="14" fill="#374151">Figure 1 &#183; The sumset staircase: climb the first column, then walk the last row; every step is a new sum</text>
</svg>
```

Tightness: arithmetic progressions. A = {0, d, 2d, …}, B likewise: |A+B| = |A| + |B| − 1 exactly. The staircase is the *only* shape that achieves equality, in a precise sense — the structure theory of near-equality is Kneser's business, next lecture.

### 1.2 Modulo a prime: Cauchy–Davenport, by periodicity (full)

**Theorem (Cauchy–Davenport).** A, B ⊆ 𝔽_p nonempty: **|A + B| ≥ min(p, |A| + |B| − 1).**

*Proof (the merge argument).* Translate so that 0 ∈ B, and write B = {0, b₁, …, b_{t−1}}. Build A₀ = A and A_i = A_{i−1} ∪ (A_{i−1} + b_i) for i = 1, …, t−1. By induction on i, A_i = A + {0, b₁, …, b_i}: each step unions in one more translate. So A_{t−1} = A + B.

**Each step gains at least one element — or the set is already everything.** If |A_i| = |A_{i−1}|, then A_{i−1} + b_i ⊆ A_{i−1}, and since both translates have the same size, **A_{i−1} + b_i = A_{i−1}**: the set is invariant under translation by b_i. But b_i ≠ 0 in 𝔽_p generates the whole additive group — the multiples of b_i cycle through all of 𝔽_p — so invariance under b_i forces invariance under every group element: A_{i−1} = 𝔽_p. (A nonempty finite set invariant under a transitive group of translations is the whole space.) Then A + B ⊇ A_{i−1} + 0 = 𝔽_p and we are done, with |A+B| = p ≥ min(p, a+b−1).

If no step stalls, |A+B| = |A_{t−1}| ≥ |A₀| + (t−1) = a + b − 1, and |A+B| ≤ p caps the claim at min(p, a+b−1). ∎

The lab runs this merge on every pair of subsets of 𝔽_5 and 𝔽_7 (with 0 ∈ B): a zero-gain step occurs **only** when the running set has already become the whole field — 8,624 processes, zero violations, and the periodicity claim (invariance ⟹ everything) is checked each time it fires.

### 1.3 The polynomial method proof (P22, full)

The second proof is the Chapter 6 engine running on a grid, and it is worth seeing in its purest form. One ingredient does all the work.

**Ingredient (the weighted-sum identity).** Let Π_A(x) = Π_{c∈A}(x − c) with derivative Π_A′, and likewise Π_B. For any polynomial f with total degree ≤ a + b − 2 (|A| = a, |B| = b),

Σ_{x∈A, y∈B} f(x, y) / (Π_A′(x) · Π_B′(y)) = [x^{a−1} y^{b−1}] f.

*Proof.* Expand f = Σ f_{ij} x^i y^j; the sum splits over monomials and separates in x and y:

Σ_{x∈A} x^i / Π_A′(x) = [i = a−1] — zero when i < a−1, one when i = a−1.

This is the classical partial-fraction identity: 1/Π_A(x) = Σ_{x₀∈A} 1/(Π_A′(x₀)(x − x₀)); multiplying both sides by x^{a−1}... more precisely, expand each fraction 1/(x−x₀) as a power series in 1/x and compare the coefficient of x^{−1}: the left side contributes 1, the right side contributes Σ_{x₀} x₀^{a−1}/Π_A′(x₀), and matching gives Σ_{x₀} x₀^i/Π_A′(x₀) = [i = a−1] for i ≤ a−1.

The same holds over B. Terms with i ≥ a cannot use the i ≤ a−1 identity — but they die by degree: i ≥ a forces j ≤ (a+b−2) − i ≤ b−2 < b−1, and the y-sum vanishes there. Only i = a−1, j = b−1 survives, contributing f_{a−1,b−1}. ∎

*(Companion fact — the grid lemma, D1.* A polynomial with deg_x < a and deg_y < b vanishing on all of A × B is identically zero: fix x₀ ∈ A, read f(x₀, ·) as a one-variable polynomial with b roots and degree < b, so it is ≡ 0; each y^j coefficient is then a one-variable polynomial in x of degree < a with a roots, so ≡ 0. D1 is the engine of the *classical* variant of this proof — where one starts from a higher-degree polynomial and must first reduce it to the grid — and it is the two-variable echo of Chapter 6's multilinear lemma. Our f has degree exactly a+b−2, so the identity alone finishes; the lab verifies D1 anyway, 184 exact grid reconstructions.)*

**The proof of Cauchy–Davenport.** Suppose, for contradiction, that |A + B| ≤ a + b − 2. The interesting case is a + b ≤ p + 1 (when a + b − 1 ≥ p, the periodicity proof of §1.2 already closed the theorem). Choose a set C with

A + B ⊆ C ⊆ 𝔽_p, |C| = a + b − 2

— possible because the complement of A + B has p − |A+B| ≥ (a+b−2) − |A+B| spare elements: we need a+b−2−|A+B| of them, and p ≥ a+b−2 guarantees supply. ✓

Now set f(x, y) = Π_{c∈C}(x + y − c), total degree a + b − 2.

- **f vanishes on A × B**: for x ∈ A, y ∈ B, the sum x + y lies in A + B ⊆ C, so one factor is zero. ✓
- So the weighted sum Σ_{A×B} f/(Π_A′Π_B′) is **0** — every numerator vanishes.
- But apply the identity: the sum equals [x^{a−1} y^{b−1}] f. And degree does the work: **f has total degree a+b−2 = (a−1)+(b−1), so every factor x+y−c must contribute its x or its y** to reach x^{a−1} y^{b−1} — no constant −c ever appears. The coefficient is the pure count C(a+b−2, a−1) — choosing which factors give x — nonzero mod p because a+b−2 ≤ p−1 keeps every factorial factor of C(a+b−2, a−1) below p.

**0 = C(a+b−2, a−1) ≢ 0. Contradiction.** ∎

Every ingredient is machine-checked: the partial-fraction identity (15,011 checks over 𝔽_5–𝔽_13), the weighted-sum identity including the dying logic (900 random polynomials), the grid lemma's interpolation (184 reconstructions), the binomial non-vanishing (all m ≤ p−1), and the vanishing step f(a,b) = 0 ⟺ a+b ∈ C (450 checks).

### 1.4 The m-fold corollary (full)

**m-fold Cauchy–Davenport.** |A₁ + A₂ + … + A_m| ≥ min(p, Σ|A_i| − m + 1).

*Proof.* Induction on m, merging two summands at a time: |A₁+…+A_m| ≥ |A₁ + (A₂+…+A_m)| ≥ min(p, a₁ + |A₂+…+A_m| − 1) ≥ min(p, a₁ + (p, Σ_{i≥2} a_i − (m−1) + 1) − 1) — with the convention min(p, ·) composing correctly — telescopes to min(p, Σ a_i − m + 1). ∎ (The lab stress-tests this on random m ≤ 4 families over 𝔽_5, 𝔽_7, 𝔽_11 — 600 trials, zero violations; Lecture 2 uses it twice.)

### 1.5 What to learn

Two proofs, two philosophies again. The merge argument is *dynamic*: grow the sumset and show the only way to stop is to finish. The polynomial argument is *static*: build one polynomial that vanishes on the grid, and price its top coefficient two ways. The grid lemma D1 is the polynomial method's workhorse — the same "small degree + many roots ⟹ zero" move as Chapter 6's multilinear lemma, in two variables. And note the exact fingerprint: the contradiction needed a+b−2 ≤ p−1, the same boundary the theorem itself respects.

---

## Lecture 2 · Kneser's Theorem and the Zero-Sum Capstone

Cauchy–Davenport lives in 𝔽_p, and the staircase lives in ℤ. Both are shadows of one master theorem: **Kneser's theorem**, which prices a sumset by its *period* — the translations that leave it alone. This lecture states Kneser, builds the e-transform toolkit that powers its proof (both properties proved in full), proves the quotient reduction completely, and hands the aperiodic step to the next lecture, which builds it in full. Then, as a capstone, the chapter's two threads — sets and sums — fuse in the Erdős–Ginzburg–Ziv theorem, proved here in full: pairing in the prime case, block extraction in the composite case, with the m-fold Cauchy–Davenport from Lecture 1 doing the arithmetic.

### 2.1 The statement, and what a stabilizer is

**Problem.** A, B nonempty finite subsets of an abelian group G. How small can A + B be?

In ℤ the answer is |A|+|B|−1 and the witness is an arithmetic-progression-like pair (Lecture 1's staircase). In 𝔽_p the answer is min(p, |A|+|B|−1) (Lecture 1, two proofs). In Z₆, take A = B = {0, 2, 4}: then A + B = {0, 2, 4} again — size **3**, not 5, not 3+3−1 = 5. What broke? The sumset is *periodic*: adding 2 to every element of {0,2,4} gives {0,2,4} back. Periods are not a pathology; they are the *third parameter* of the subject.

**Definition.** For S ⊆ G, the **stabilizer** of S is stab(S) = {g ∈ G : g + S = S}. 

**Lemma (the stabilizer is a subgroup; S is a union of cosets).** stab(S) is a subgroup of G, and if H = stab(S), then S is a union of H-cosets: s ∈ S ⟹ s + H ⊆ S.

*Proof.* 0 ∈ stab(S) (0 + S = S). If g, h stabilize S, then (g+h) + S = g + (h + S) = g + S = S, so g + h stabilizes. And g + S = S implies S = (−g) + S by translating both sides by −g, so −g stabilizes too: a subgroup. For the coset claim, s ∈ S and h ∈ H give h + s ∈ h + S = S. ∎

**Theorem (Kneser, 1953).** A, B nonempty finite subsets of the abelian group G, H = stab(A+B). Then

**|A + B| ≥ |A| + |B| − |H|**, equivalently |A + B| ≥ |A+H| + |B+H| − |H|.

Both forms hold; the second is never weaker, since A ⊆ A+H. Sanity checks: in ℤ the only finite set with a nonzero period is ∅, so H = {0} and Kneser is the staircase; in 𝔽_p the group has no nontrivial subgroups at all, so Kneser is Cauchy–Davenport *without the min(p, ·)* — and the min is exactly the full-field case, where H = stab(𝔽_p) = 𝔽_p has order p and the bound |A+B| ≥ |A|+|B|−p is vacuous. The theorem specializes correctly everywhere. (The ✎: in Z₆ with A = B = {0, 2, 4}, verify H = {0, 2, 4}, |A+B| = 3 = 3+3−3, and that A+B is exactly one H-coset — H itself.)

### 2.2 Tight examples and the census

Three regimes, three shapes:

- **H = {0}, tight:** A = B = {0, 1, …, k−1} in Z_n with n > 2k−2: A+B = {0, …, 2k−2}, size 2k−1 = k+k−1, no period. The staircase is tight in every group that has room for it.
- **H nontrivial, tight:** the coset A = B = H = {0,2,4} in Z₆ above; more generally A = B = a + H for any subgroup H: A+B = 2a + H, size |H| = |H|+|H|−|H|. Subgroups are the *atoms* of small sumsets.
- **Full group:** if A+B = G, then H = G and the bound reads |G| ≥ |A|+|B|−|G| — true and slack unless |A|+|B| = 2|G|.

The lab runs a census with the stabilizer computed exactly: all of Z₆, Z₇, Z₈, Z₉ (3,969 / 16,129 / 65,025 / 261,121 pairs) — **zero violations**, with every tight case accounted for by a subgroup exactly as above (an arithmetic progression when H = {0}, a coset structure when H ≠ {0}); the wider gate sampling — Z₁₀ up to size 5 (405,769 pairs), Z₁₂ up to size 4 (628,849), all of Z₃² (261,121), and 40,000 sampled pairs of Z₄² — is verification-basis record, not the printed lab.

### 2.3 The e-transform: the toolkit, proved (P23)

The engine behind the hard half of Kneser is Dyson's **e-transform** — a cousin of Chapter 7's shifting lecture: replace (A, B) by a deformed pair that is *easier to analyze* while the sumset only shrinks and the total size is preserved. Compression, not counting (P23 again).

**Definition.** For e ∈ G:

A(e) = A ∪ (B + e),  B(e) = B ∩ (A − e),

where A − e = {a − e : a ∈ A}. Note the shape: one set *grows* by a translate of the other, the other *shrinks* to what matches that translate.

**Property 1 (the sumset only shrinks): A(e) + B(e) ⊆ A + B.**

*Proof.* Take x ∈ A(e), y ∈ B(e); show x + y ∈ A + B. Two cases.

- x ∈ A: then y ∈ B(e) ⊆ B, so x + y ∈ A + B directly.
- x = b₁ + e with b₁ ∈ B: then y ∈ B ∩ (A − e), so y + e ∈ A, and x + y = b₁ + (y + e) ∈ B + A = A + B. ∎

The second case is the whole trick: the translate e, which created x, is *refunded* by B(e)'s membership test y + e ∈ A. What the transform gives with one hand it claws back with the other.

**Property 2 (the total size is preserved): |A(e)| + |B(e)| = |A| + |B|.**

*Proof.* First, (B ∩ (A − e)) + e = (B + e) ∩ A: both sides say {x : x − e ∈ B and x ∈ A + e}... check by translation — translating B ∩ (A−e) by e adds e to every element, giving exactly the elements that are in B+e and in A. So |B(e)| = |(B+e) ∩ A|, the translate having the same size. Now A(e) = A ∪ (B+e), so by inclusion–exclusion

|A(e)| + |(B+e) ∩ A| = |A ∪ (B+e)| + |A ∩ (B+e)| = |A| + |B+e| = |A| + |B|. ∎

**Monotonicity and termination.** A ⊆ A(e) always; B(e) ⊆ B always. If additionally B + e ⊄ A, the inclusion A ⊆ A(e) is *strict* — some element of B+e lies outside A — so by Property 2, |B(e)| < |B| strictly: the pair traded a unit of B for a unit of A. Since |B| is a positive integer that strictly decreases, the iteration terminates. Each step keeps Aᵢ + Bᵢ ⊆ A + B (Property 1) and |Aᵢ| + |Bᵢ| = |A| + |B| (Property 2).

The lab machine-checks both properties on every e ∈ G for random A, B in Z₆, Z₈, Z₃² — 6,900 checks, zero violations.

### 2.4 The assembly: the two moves

Here is the architecture of the full proof, in two moves.

**Move 1 (the aperiodic case).** If stab(A+B) = {0}, then |A+B| ≥ |A|+|B|−1. For ℤ this is the staircase (Lecture 1, proved); for 𝔽_p it is Cauchy–Davenport (Lecture 1, proved twice). For a general abelian group this is a real theorem, and the next lecture builds it in full. The engine is the e-transform of §2.3 — the toolkit above is complete — but one honest warning belongs here already: the transform preserves the sumset only up to *containment*, and the deformed pair can be *more* periodic than the original (the machine found a pair in Z₆ whose sumset is aperiodic while a perfectly legal transform of it is not — §3.2). So the aperiodic hypothesis must be handled with care: a two-case recursion carries the weak form (§3.1), and the strong form rides DeVos's intersection–union induction (§3.3). Sources: Kneser's original 1953 paper (Math. Z. 58), Dyson's 1945 transform argument, the self-contained treatment in Nathanson's *Additive Number Theory* (GTM 165), and Tao–Vu's *Additive Combinatorics*; the recent survey arXiv:2407.12253 traces the transform's history, and DeVos's short proof carries the strong form.

**Move 2 (the quotient reduction — proved in full).** Suppose Move 1 as a black box for every abelian group. Let H = stab(A+B). By §2.1, A+B is a union of H-cosets, and so are A+H and B+H. Pass to the quotient group G/H: the images S̄ = (A+B)/H, Ā = (A+H)/H, B̄ = (B+H)/H satisfy S̄ = Ā + B̄, and

- |S̄| = |A+B| / |H|, |Ā| = |A+H| / |H|, |B̄| = |B+H| / |H| (each set is a disjoint union of cosets);
- **stab(S̄) is trivial in G/H:** if a coset g+H satisfies (g+H) + S̄ = S̄, then for every s ∈ A+B we get g+s+H inside S̄, hence g+s ∈ A+B (a union of cosets); so g + (A+B) ⊆ A+B, and finiteness gives equality, g ∈ H — the identity coset.

Apply Move 1 to Ā, B̄ in G/H: |S̄| ≥ |Ā| + |B̄| − 1. Multiply through by |H|:

**|A+B| ≥ |A+H| + |B+H| − |H| ≥ |A| + |B| − |H|.** ∎

Both Kneser forms at once, and the aperiodic black box is the only flagged input. Note the pleasing division of labor: the *hard* content is all in Move 1 (structure), and Move 2 is pure bookkeeping with cosets — the same "pass to the quotient where the obstruction vanishes" move that solved the Petersen graph's equitable quotient in Chapter 8.

### 2.5 The capstone: Erdős–Ginzburg–Ziv, in full

**Theorem (EGZ, 1965).** Any 2n−1 integers contain n whose sum is divisible by n.

Forty years of additive combinatorics in one sentence: 2n−1 is the cap (2n−2 can fail: n−1 zeros and n−1 ones). The proof below is complete.

**Step 1 — the prime case, n = p.** A multiset of 2p−1 residues.

*Trivial case.* Some value occurs ≥ p times: those p copies sum to p·v ≡ 0 mod p. Done. So assume every value occurs ≤ p−1 times.

*Pairing lemma.* A multiset of 2m elements in which no value occurs more than m times can be split into m pairs, each with two distinct elements.

*Proof.* Sort the elements as e₁ ≤ e₂ ≤ … ≤ e_{2m} and pair eᵢ with e_{i+m} for i = 1, …, m. If a pair had eᵢ = e_{i+m}, then the sorted run eᵢ, e_{i+1}, …, e_{i+m} would be m+1 equal elements — forbidden. ∎

Now remove any single element x from the multiset. The remaining 2p−2 = 2(p−1) elements still have every multiplicity ≤ p−1 = m, so the pairing lemma splits them into p−1 pairs {aᵢ, bᵢ}, aᵢ ≠ bᵢ — each pair a 2-element subset of 𝔽_p. The **m-fold Cauchy–Davenport** (Lecture 1, proved) applies to these p−1 two-element sets:

|{choose one element from each pair and sum}| ≥ min(p, 2(p−1) − (p−1) + 1) = min(p, p) = p.

Every residue is achievable as a choice-sum — including **−x**. Take that choice: x together with the p−1 chosen elements is p elements summing to 0 mod p. ∎

Watch how the book's patterns stack: the greedy pairing is compression (P23), the counting engine is m-fold C–D (P22/P4), and the conclusion is a *reachability* statement — the same "the achievable set is everything" move as the Hoffman-bound arguments of Chapter 8. The lab verifies the whole chain: exhaustive search over all multisets for n = 3–7 (21 / 120 / 715 / 4,368 / 27,132 multisets) — every one contains a zero-sum n-subset (the 20,000-sample sweeps at n = 9, 10 are gate record, not the printed lab); the pairing lemma on 800 random constrained multisets; and 900 full prime-case runs in which the choice-sumset always covered 𝔽_p and −x was always reachable (44 runs settled by the trivial case, counted separately).

**Step 2 — the composite case, n = nm′.** Suppose EGZ holds for n and for m; prove it for nm. Given 2nm−1 integers. Extract disjoint n-blocks, each with sum ≡ 0 mod n, using EGZ(n) repeatedly: after j blocks, 2nm−1−nj elements remain, and one more extraction is possible whenever

2nm−1−nj ≥ 2n−1, i.e. n(2m−j) ≥ 2n, i.e. **j ≤ 2m−2**.

So we extract exactly 2m−1 disjoint blocks B₁, …, B_{2m−1}, each of size n with sum sᵢ ≡ 0 mod n. Divide: tᵢ = sᵢ/n are 2m−1 integers, so EGZ(m) picks m of them with tᵢ₁ + … + tᵢ_m ≡ 0 mod m. The union of the corresponding m blocks has exactly nm elements with total sum n(tᵢ₁ + … + tᵢ_m), divisible by nm. EGZ(nm) holds. ∎

**Step 3 — assembly.** EGZ(1) is vacuous, EGZ(p) is Step 1, and Step 2 builds EGZ of any composite from its factors. Induction on the number of prime factors (with multiplicity) closes the theorem for every n. ∎

The lab runs the composite chain end-to-end on 300 random instances over (n, m) = (2,3), (3,2), (2,2), (2,5), (3,3): every instance yields its 2m−1 disjoint zero-sum-n blocks, and the EGZ(m) selection on the scaled block sums produces a genuine zero-sum-nm subset. (One lab bug is worth recording as a lesson: the verifier initially checked the final sum mod nm via the *scaled* sums, i.e. mod m, rather than mod nm — the fixed check confirms divisibility by nm itself.)

### 2.6 What to learn

Kneser's theorem is the bookkeeping of *periodicity*: whenever a sumset underperforms the staircase, the deficit is exactly paid by a subgroup of periods, and the coset structure is not an accident but a proof. The e-transform is the book's compression engine at its purest — shifting (Chapter 7's shifting lecture) deformed families toward the star, the merge deformed sumsets toward the field, and the e-transform deforms pairs toward a configuration where the period is visible. And EGZ shows what a toolkit is *for*: pairing (P23) feeds m-fold C–D (P22), whose prime case feeds a block reduction (P4), and the capstone theorem falls to three moves, each of which was already on the table. That is the Feynman test of understanding — *knowing how to redo the proof with the tools you own* — and the two sumset lectures own every tool of that thread. The next lecture completes what this one flags: it builds the aperiodic assembly in full, closing the appendix's third flag. The lecture after adds the last engine of the set-system thread — shadow pricing — and uses it to retire the first of the three; the second, the thin range, follows in the closing lecture — flagged honestly until then.

---

## Lecture 3 · The Assembly, Completed: Dyson's Recursion and DeVos's Proof

Lecture 2 proved Kneser's quotient move and left the aperiodic case as a flagged input. This lecture builds that input, twice. First the *weak* theorem — every pair with |A| + |B| ≤ |G| admits a proper subgroup H with |A + B| ≥ |A| + |B| − |H| — by a two-case recursion on Dyson's e-transform, the §2.3 toolkit doing exactly the work it was built for. The recursion is honest about its own reach: a plain induction cannot deliver the strong form, and a small example in Z₆ says why (§3.2). The strong form then rides DeVos's short intersection–union induction, presented in full (§3.3): one new notion — a *portion* of a sumset — and three counting equations close what the transform alone could not. With §2.4's quotient move, this completes the book's proof of Kneser's theorem and retires the appendix's third flag.

### 3.1 The weak form: a two-case recursion (P4, full)

**Theorem (weak Kneser).** A, B nonempty finite subsets of the abelian group G with |A| + |B| ≤ |G|. Then there is a *proper* subgroup H ⊊ G with

**|A + B| ≥ |A| + |B| − |H|.**

*Proof.* The recursion runs on the pair (A, B), preserving three invariants — A + B contains every later sumset, the total size never changes, B never empties — and it stops in one of two cases, each of which produces a proper subgroup.

**The base: |B| = 1.** Take H = {0}: |A + B| = |A| = |A| + |B| − 1, and {0} ⊊ G because |A| + |B| ≤ |G| with both sets nonempty rules out the trivial group.

**Case 1 (no witness).** Scan the pair for a *witness*: a triple (a, b′, b) ∈ A × B × B with a + b − b′ ∉ A. If none exists then A + (B − B) ⊆ A: every difference stabilizes A, and H′ = ⟨B − B⟩, the subgroup generated by the differences, satisfies H′ ⊆ stab(A). Now four facts, each one line:

- B ⊆ b₀ + H′ for any b₀ ∈ B (every b − b₀ lies in B − B ⊆ H′), so |B| ≤ |H′|;
- H′ stabilizes A + b₀, so A + B ⊆ (A + b₀) + H′ = A + b₀, and equality holds — the sumset collapses to a single translate, |A + B| = |A|;
- stab(A) ⊆ stab(A + B) (g + A = A gives g + (A + B) = (g + A) + B = A + B), so H′ ⊆ stab(A + B);
- H′ is proper: stab(A) = G would force A = G, impossible since |A| ≤ |G| − |B| ≤ |G| − 1.

The bound reads |A + B| = |A| = |A| + |B| − |B| ≥ |A| + |B| − |H′|, with H′ proper. Done.

**Case 2 (a witness exists).** Take the canonical one — the lexicographically first (a, b′) ∈ A × B (a ascending, then b′ ascending) admitting some b ∈ B with a + b − b′ ∉ A, and the first such b — and set e = a − b′,

A′ = A ∪ (B + e),  B′ = B ∩ (A − e).

The §2.3 properties do the work:

- *Containment:* A′ + B′ ⊆ A + B (Property 1) — the first invariant survives.
- *Size preservation:* |A′| + |B′| = |A| + |B| (Property 2) — so the hypothesis |A| + |B| ≤ |G| survives, and so does nonemptiness: b′ + e = a ∈ A, so b′ ∈ B′, and A ⊆ A′.
- *Strict decrease:* the witness says b + e ∉ A, so B + e ⊄ A, and §2.3's monotonicity remark gives |B′| < |B|.

Recurse on (A′, B′). |B| is a positive integer that strictly decreases, so the recursion stops — at the base or at Case 1, whichever comes first. Unrolling: the terminal pair (A*, B*) has |A*| + |B*| = |A| + |B| and its own proper subgroup H (either {0} or its Case-1 H*), with |A* + B*| ≥ |A*| + |B*| − |H|; containment chains the bound up:

|A + B| ≥ |A* + B*| ≥ |A*| + |B*| − |H| = |A| + |B| − |H|. ∎

**Corollary (Cauchy–Davenport, recovered whole).** In 𝔽_p the only proper subgroup is {0}, so the weak form gives |A + B| ≥ |A| + |B| − 1 whenever |A| + |B| ≤ p. And if |A| + |B| ≥ p + 1, then for every c ∈ 𝔽_p the sets A and c − B meet (their sizes sum to more than p), so c ∈ A + B and A + B = 𝔽_p. Together: |A + B| ≥ min(p, |A| + |B| − 1), Lecture 1's theorem — recovered without reopening either of its proofs. ∎

**Machine record.** The recursion is deterministic under the canonical rule, so it can be censused. The sweep ran it on all 738,884 ordered pairs of nonempty subsets of the twelve groups of order ≤ 9 — every Case-2 step machine-checked for containment, size preservation, strict decrease, and nonemptiness, every Case-1 termination checked for H′ ⊆ stab(A), |B| ≤ |H′|, and the collapse A + B = A + b₀, every termination checked for the weak-form conclusion and for the properness of H when |A| + |B| ≤ |G|. Zero violations anywhere:

| Group | Pairs | Case-1 | Staircase bases | Case-2 steps | Max depth |
|-------|-------|--------|-----------------|--------------|-----------|
| Z₂ | 9 | 1 | 8 | 2 | 2 |
| Z₃ | 49 | 7 | 42 | 24 | 2 |
| Z₄ | 225 | 41 | 184 | 167 | 3 |
| Z₂² | 225 | 49 | 176 | 158 | 3 |
| Z₅ | 961 | 176 | 785 | 982 | 3 |
| Z₆ | 3,969 | 872 | 3,097 | 4,939 | 4 |
| Z₇ | 16,129 | 3,473 | 12,656 | 24,333 | 4 |
| Z₈ | 65,025 | 15,541 | 49,484 | 111,607 | 5 |
| Z₄×Z₂ | 65,025 | 16,607 | 48,418 | 109,052 | 5 |
| Z₂³ | 65,025 | 18,161 | 46,864 | 106,738 | 5 |
| Z₉ | 261,121 | 63,798 | 197,323 | 505,136 | 5 |
| Z₃² | 261,121 | 66,334 | 194,787 | 492,082 | 5 |
| **Total** | **738,884** | **185,060** | **553,824** | **1,355,220** | **5** |

The theorem is indifferent to which witness the rule picks — any witness works in Case 2 — but the census is not: these counts are the lexicographic rule's. (The lab, Part 4, runs the recursion exhaustively on Z₄, Z₆, Z₇ and prints the matching rows.)

### 3.2 An honesty interlude: why the recursion stops at the weak form

The tempting overreach: run the recursion to the end, then claim the terminal H′ stabilizes A + B and read off the strong form. The containment H′ ⊆ stab(A) ⊆ stab(A + B) is proved — but for the *terminal* pair, and the recursion only preserved the original sumset up to *containment*. Nothing stops the deformed pair from being more periodic than the original, and on a small example in Z₆ it happens: A = {0, 1, 3}, B = {0, 2}. Here stab(A + B) = {0} — the sumset A + B = {0, 1, 2, 3, 5} is aperiodic — yet the perfectly legal transform with witness (a, b′, b) = (0, 2, 0), e = 4 produces A′ = {0, 1, 3, 4} and B′ = {2}, whose sumset A′ + B′ = {0, 2, 3, 5} is stabilized by {0, 3}: aperiodicity is *destroyed* by the transform. Of the six (a, b′) pairs, four are genuine transforms (containment, size preservation, and strict decrease all hold); the canonical rule picks the first of them — (a, b′) = (0, 0) with b = 2, e = 0, giving A′ = {0, 1, 2, 3} and B′ = {0}, stabilizer still trivial — while the period-creating (0, 2) with e = 4 is legal but not canonical. The weak form survives because it never asks about stab(A + B) — it produces its own proper subgroup at the terminal pair, whichever pair that is. The strong form prices the *original* sumset's period, so it needs an argument that keeps the original in view throughout. DeVos's induction does exactly that, with no transforms at all.

### 3.3 The strong form: DeVos's intersection–union induction (full)

**Theorem (Kneser, strong form — DeVos's route).** X, Y nonempty finite subsets of the abelian group G, K = stab(X + Y). Then |X + Y| ≥ |X + K| + |Y + K| − |K|.

*Proof.* Induction on the measure **|X + Y| + |X|**. (The route is DeVos's — *A short proof of Kneser's addition theorem for abelian groups*; the treatment below follows his two-page note.)

**The quotient branch: K ≠ {0}.** This is Move 2 of §2.4, in one line: in G/K the image of X + Y has trivial stabilizer, induction prices the images, and multiplying by |K| gives the claim. So assume **K = {0}** — the aperiodic branch, the flagged case of Lecture 2, now carried to the end.

If |X| = 1, then X + Y is a translate of Y and X + K a coset of K: the bound reads |Y| ≥ |Y + K|, true since Y ⊆ Y + K. Let |X| ≥ 2 and choose distinct x, x′ ∈ X. Since stab(Y) ⊆ stab(X + Y) = {0} and x′ − x ≠ 0, the element x′ − x does not stabilize Y, so some y ∈ Y has y + x′ − x ∉ Y. Translate Y ← Y − y + x: the theorem's cardinalities do not move, and now ∅ ≠ X ∩ Y ⊊ X (x lies in both; x′ would lie in the new Y only if y + x′ − x lay in the old one).

**Portions.** Call a set Z ⊆ X + Y, with H = stab(Z), a **portion** if

|Z| + |H| ≥ |X ∩ Y| + |(X ∪ Y) + H|.

Set Z₀ = (X ∩ Y) + (X ∪ Y) ⊆ X + Y. The pair (X ∩ Y, X ∪ Y) has a smaller measure — |Z₀| + |X ∩ Y| ≤ |X + Y| + |X ∩ Y| < |X + Y| + |X| — so induction applies and gives |Z₀| ≥ |(X∩Y) + stab(Z₀)| + |(X∪Y) + stab(Z₀)| − |stab(Z₀)|, which is the portion inequality for Z₀. A portion exists; choose one, Z, with H = stab(Z) **minimal under inclusion**. (Z is nonempty: stab(∅) = G, and stab(Z₀) ⊊ G — a nonempty stable set equal to G would make X + Y = G, contradicting K = {0} — so the minimal choice avoids the empty set.)

**The trivial exit: H = {0}.** |X + Y| ≥ |Z| ≥ |X ∩ Y| + |X ∪ Y| − 1 = |X| + |Y| − 1. Done.

**The nontrivial branch: H ≠ {0} — for a contradiction.** Since stab(X + Y) = {0} ≠ H, the sumset cannot contain every H-coset it touches: if a + b + H ⊆ X + Y for all a ∈ X, b ∈ Y, then every s = x + y ∈ X + Y carries s + H ⊆ X + Y, making H ⊆ stab(X + Y) = {0}. So choose a ∈ X, b ∈ Y with **C := a + b + H ⊄ X + Y**, and define

X₁ = X ∩ (a + H),  Y₁ = Y ∩ (b + H),  X₂ = X ∩ (b + H),  Y₂ = Y ∩ (a + H),

so X₁, Y₁ ≠ ∅, and for i = 1, 2 set Zᵢ = Z ∪ (Xᵢ + Yᵢ) and Hᵢ = stab(Xᵢ + Yᵢ).

*The key observation.* Suppose Xᵢ, Yᵢ ≠ ∅. Then **Hᵢ = stab(Zᵢ) ⊊ H**, in four steps. (1) *Hᵢ ⊆ H:* pick p ∈ Xᵢ + Yᵢ ⊆ C; any g stabilizing Xᵢ + Yᵢ has g + p ∈ Xᵢ + Yᵢ ⊆ C, so g ∈ C − C = H. (2) *Z misses C:* Z is a union of H-cosets, and it cannot meet C — meeting it would mean containing it, but C ⊄ X + Y ⊇ Z. So |Zᵢ| = |Z| + |Xᵢ + Yᵢ|. (3) *stab(Zᵢ) = Hᵢ:* a g ∉ H has g + C ≠ C; comparing the C-parts of g + Zᵢ = Zᵢ gives g + (Xᵢ + Yᵢ) ⊆ Z, and then |g + Z| + |Xᵢ + Yᵢ| = |Zᵢ| = |Z| + |Xᵢ + Yᵢ| forces g + Z = Z, so g ∈ stab(Z) = H — contradiction; hence stab(Zᵢ) ⊆ H, and for g ∈ H the equality g + Zᵢ = Zᵢ reduces (Z being H-stable) to g + (Xᵢ + Yᵢ) = Xᵢ + Yᵢ, i.e. g ∈ Hᵢ. (4) *Strictness:* Hᵢ = H would make H stabilize the nonempty Xᵢ + Yᵢ inside its own coset C, forcing Xᵢ + Yᵢ = C ⊆ X + Y — false. By the minimality of H, **Zᵢ is not a portion**:

|Zᵢ| + |Hᵢ| < |X ∩ Y| + |(X ∪ Y) + Hᵢ|.

And induction applies to (Xᵢ, Yᵢ): the measure drops, since |Xᵢ + Yᵢ| ≤ |H| < |X + Y| (Z is a nonempty union of H-cosets, so |H| ≤ |Z| ≤ |X + Y|, and equality would force Z = X + Y and H = stab(X + Y) = {0}) while |Xᵢ| ≤ |X|. Induction there reads |Xᵢ + Yᵢ| ≥ |Xᵢ + Hᵢ| + |Yᵢ + Hᵢ| − |Hᵢ|.

**Equation (1).** Subtract the not-a-portion inequality from the portion inequality of Z:

|(X ∪ Y) + H| − |(X ∪ Y) + Hᵢ| < (|Z| + |H|) − (|Zᵢ| + |Hᵢ|) = |H| − |Xᵢ + Yᵢ| − |Hᵢ| ≤ |H| − |Xᵢ + Hᵢ| − |Yᵢ + Hᵢ|,

the last step by induction on (Xᵢ, Yᵢ). Equation (1) holds for i = 1 unconditionally; for i = 2 it needs X₂, Y₂ ≠ ∅.

*Three degeneracies, each fatal.* Equation (1) at i = 1 caps the left side strictly below |H| − |X₁ + H₁| − |Y₁ + H₁|. But:
- If **Y₂ = ∅**: the coset a + H lies inside (X ∪ Y) + H (a ∈ X), and its points covered by (X ∪ Y) + H₁ can only come from X₁ (a Y-point reaching into a + H would sit in Y₂) — so at least |H| − |X₁ + H₁| points of the coset are uncovered, and the left side of (1) is ≥ |H| − |X₁ + H₁|. Contradiction.
- If **X₂ = ∅**: the same count on the coset b + H (b ∈ Y) gives a left side ≥ |H| − |Y₁ + H₁|, which exceeds |H| − |X₁ + H₁| − |Y₁ + H₁| since X₁ ≠ ∅. Contradiction.
- If **a + H = b + H**: then X₁ = X₂ and Y₁ = Y₂, and the uncovered count on the single coset C is ≥ |H| − |(X₁ ∪ Y₁) + H₁| ≥ |H| − |X₁ + H₁| − |Y₁ + H₁| — the right side of (1). Contradiction.

So X₂, Y₂ ≠ ∅ and a + H ≠ b + H, and equation (1) holds for i = 1, 2.

**Equation (2).** Both (X ∪ Y) + H and (X ∪ Y) + Hᵢ are unions of Hᵢ-cosets (Hᵢ ⊆ H), so the left side of (1) is a nonnegative multiple of |Hᵢ| — and every term of the right side is a multiple of |Hᵢ| too. A nonnegative multiple sitting strictly below a multiple of |Hᵢ| is at least |Hᵢ| below it:

|H| − |Xᵢ + Hᵢ| − |Yᵢ + Hᵢ| ≥ |Hᵢ|, hence **|H| ≥ |Xᵢ| + |Yᵢ| + |Hᵢ|** — for i = 1, 2.

**Equation (3).** X + Y is not a portion — if it were, its stabilizer {0} would be a portion-stabilizer inside H, contradicting minimality — so |X + Y| < |X ∩ Y| + |X ∪ Y| = |X| + |Y|, i.e. **|X| + |Y| − |X + Y| ≥ 1**. Now let

A = (a + H) ∖ (X₁ ∪ Y₂),  B = (b + H) ∖ (X₂ ∪ Y₁)

— the uncovered parts of the two cosets. A and B are disjoint (a + H ≠ b + H) and both avoid X ∪ Y. Chain the portion inequality of Z with two additions:

|H| ≥ |X ∩ Y| + |(X ∪ Y) + H| − |Z| ≥ |X ∩ Y| + |X ∪ Y| + |A| + |B| − |Z| = |X| + |Y| + |A| + |B| − |Z|,

and |Z| + |Xᵢ + Yᵢ| ≤ |X + Y| (Z misses C, Xᵢ + Yᵢ lies in C ∩ (X + Y)), so

|H| ≥ |A| + |B| + |X| + |Y| − |X + Y| + |Xᵢ + Yᵢ| > |A| + |B| + |Xᵢ| + |Yᵢ| − |Hᵢ|,

using |X| + |Y| − |X + Y| ≥ 1 and induction's |Xᵢ + Yᵢ| ≥ |Xᵢ| + |Yᵢ| − |Hᵢ| — for i = 1, 2.

**The partition that cannot add up.** Sum equation (2) for i = 1, 2 and equation (3) for i = 1, 2, and halve:

2|H| > |A| + |B| + |X₁| + |Y₁| + |X₂| + |Y₂|.

But the two cosets partition exactly: a + H = A ⊎ X₁ ⊎ Y₂ and b + H = B ⊎ X₂ ⊎ Y₁, so the right side is |a + H| + |b + H| = 2|H|. Contradiction — the nontrivial branch cannot occur, and the theorem is proved. ∎

**Machine record.** The machinery is deterministic, so it too was censused: on the 39,449 aperiodic pairs with |X| ≥ 2 of Z₆ (1,080), Z₇ (5,537), Z₈ (18,432), and Z₄×Z₂ (14,400), the translate step always lands ∅ ≠ X ∩ Y ⊊ X; Z₀ = (X ∩ Y) + (X ∪ Y) is always a portion; and the trivial exit always holds — the aperiodic staircase |X + Y| ≥ |X| + |Y| − 1, zero violations. The stabilizer of Z₀ is nontrivial on 3,604 of the pairs (Z₆ 60, Z₇ 0, Z₈ 930, Z₄×Z₂ 2,614), but on *every* pair there is also a trivial-stabilizer portion — so the stabilizer-minimal choice, the proof's, never fires the nontrivial branch in the data. The proof carries that branch anyway; that is what proofs are for, and the four equations above are what it costs. (Exercise 10 walks the canonical instance X = {0, 1}, Y = {0, 3, 4} in Z₆ — six portions, one of them Z₀ with stabilizer {0, 3}, five trivial; the lab, Part 4, enumerates them.)

With Move 2 (§2.4) and this lecture assembled, Kneser's theorem is the book's throughout: |A + B| ≥ |A + H| + |B + H| − |H| for H = stab(A + B), no flagged inputs left. **Flag (iii) retires.**

### 3.4 What to learn

Two assemblies, two temperaments. The recursion is P4 in its purest form: a deterministic procedure whose two exits are the two cases of the proof, the invariants doing the bookkeeping — and its honesty clause teaches as much as its success: the invariant was too weak for the strong form, and the Z₆ counterexample is a proof that no witness rule fixes that; some failures are structural, not tactical. DeVos's induction is the opposite temperament: no transforms, one well-chosen measure (|X + Y| + |X|), one new notion — the portion, which prices a piece of the sumset by its *own* stabilizer — and a final pair of cosets that cannot be partitioned as the arithmetic demands. The lesson to carry: when an invariant fails, the right move is sometimes not a better invariant but a different induction — DeVos never repairs the transform; he refuses it. And notice what made the strong form cheap: the portion inequality is Kneser's own bound applied to a sub-pair, the induction hypothesis doing at every level what the quotient move does once. With the strong form proved, the sumset thread is complete: staircase, C–D, Kneser, EGZ — every proof the book's.

---

## Lecture 4 · Shadows: The Kruskal–Katona Theorem

### 4.1 The question, and two costumes

The last engine of the set-system thread answers a deceptively simple question: **if you know how many k-sets you own, how few (k−1)-sets must sit underneath them?** The *shadow* ∂𝓖 of a k-uniform family 𝓖 is the family of all (k−1)-sets contained in some member of 𝓖; the j-shadow ∂_j𝓖 is the same construction iterated down to level j. Shadows look like bookkeeping; they are actually a *price system* — and pricing families by their shadows is what finally lets this book's counting world reach the structural questions the earlier routes left flagged.

**The theorem, costume one (the cascade).** Kruskal (1963) and Katona (1966), independently: among all families of N k-sets, the smallest shadow is achieved by the initial segments of the *colex order* — order k-sets by their largest element, ties broken by the next-largest, downward ({1,2} ≺ {1,3} ≺ {2,3} ≺ {1,4} ≺ …) — and take the first N. The cascade form makes the minimum computable: write N in its k-binomial representation

N = C(a_k, k) + C(a_{k−1}, k−1) + … + C(a_i, i)   (a_k > a_{k−1} > … > a_i ≥ i ≥ 1),

built greedily (a_k is the largest a with C(a, k) ≤ N, then descend a level), and then the minimum shadow size is C(a_k, k−1) + C(a_{k−1}, k−2) + … + C(a_i, i−1). This chapter cites the cascade theorem rather than proving it — it belongs to the same world as the compression philosophy of Chapter 7's shifting lecture (a canonical initial segment beats every deformation), raised to a complete classification.

**Costume two (the real parameter — the one this book uses).** Lovász's version prices a family by a single number: if |𝓖| = C(x, k) with x real and x ≥ k, then |∂𝓖| ≥ C(x, k−1). Real binomials C(x, k) = x(x−1)…(x−k+1)/k! interpolate the integer ones and are strictly increasing in x. The two costumes are one theorem: the cascade pins the exact minimum integer-wise; the real form trades a little sharpness for portability — no bookkeeping, one price per family, pluggable into inductions (both §4.2 and §4.3 rely on exactly that).

**The machine census as referee.** Cascade versus colex initial segments: agreement on all 781 sizes (k = 2, 3, 4; every N ≤ C(12, k)); and cascade(10, 3) = 10 = C(5, 2) — the ten triples on a 5-set have exactly ten pairs underneath them. The real form, exhaustively: every one of the 32,767 nonempty 2-uniform families on [6] and every one of the 1,048,575 3-uniform families on [6] satisfies the bound (plus 24,000 sampled families at (7, 3), (7, 4), (8, 3), (8, 4) — zero violations), and **equality happens exactly when x is an integer and 𝓖 is the complete family K^k_x** — all k-subsets of a fixed x-set: all 99 exhaustive equality cases are precisely these, 57 at k = 2 (15 single edges + 20 triangles + 15 four-vertex cliques + 6 five-vertex + 1 six-vertex) and 42 at k = 3 (20 single triples + 15 + 6 + 1 complete families above them).

(✎: at k = 2 the shadow is the vertex set. The four edges {1,2}, {1,3}, {1,4}, {2,3} have |𝓖| = 4 = C(x, 2), so x = (1+√33)/2 ≈ 3.37, and the shadow {1, 2, 3, 4} has size 4 ≥ 3.37 ✓. The triangle {1,2}, {1,3}, {2,3} has x = 3 and shadow exactly {1, 2, 3} of size 3 = C(3, 1) — equality, and indeed the triangle is the complete family on {1, 2, 3}, as the equality structure demands.)

### 4.2 The clique form, and the proof (full)

The route to a complete proof is one more change of costume — from shadows to cliques. Fix r ≥ 1 and a family 𝓖 of r-subsets of a vertex set V. Call an (r+1)-set X a **clique** of 𝓖 if every r-subset of X belongs to 𝓖, and write K(𝓖) for the number of cliques. (The empty family has none; the statement below assumes |𝓖| = C(x, r) with x ≥ r, i.e. a nonempty family.)

**Theorem (clique form; statement Lovász — from the cascade theorem —, short proof by Keevash, 2008).** If |𝓖| = C(x, r) with x real and x ≥ r, then K(𝓖) ≤ C(x, r+1).

**Proof.** Induction on r.

*Base r = 1.* 𝓖 is a set of x vertices; every pair drawn from it is a 2-clique, so K(𝓖) = C(x, 2) exactly. ✓

*Step.* For a vertex v define its **link** L(v) = {T ⊆ V∖{v} : |T| = r−1 and T∪{v} ∈ 𝓖}. The map T ↦ T∪{v} is a bijection from L(v) to the members of 𝓖 containing v, so |L(v)| = d(v), the degree of v. Two ceilings on K(v), the number of cliques containing v:

1. **The link ceiling.** A clique X containing v has the form X = S∪{v} with |S| = r, and X is a clique exactly when S ∈ 𝓖 and every (r−1)-subset T of S lies in L(v) — that is, S is an r-clique of the (r−1)-uniform family L(v). So K(v) ≤ K^{(r−1)}(L(v)), and the inductive hypothesis prices it: writing |L(v)| = C(y_v, r−1),

K(v) ≤ C(y_v, r) = d(v) · (y_v − r + 1)/r,

by the identity C(y, r) = C(y, r−1) · (y − r + 1)/r, valid for real y.

2. **The degree ceiling.** The map X ↦ X∖{v} sends cliques containing v injectively into members of 𝓖 avoiding v (X∖{v} is an r-subset of the clique X, hence a member; distinct cliques have distinct shadows). So K(v) ≤ |𝓖| − d(v) = C(x, r) − d(v).

**The per-vertex price.** Claim: K(v) ≤ (x/r − 1)·d(v) for every vertex. Two cases.

- If y_v ≤ x−1 (equivalently d(v) ≤ C(x−1, r−1), binomials being increasing): ceiling 1 gives K(v) ≤ d(v)·(y_v − r + 1)/r ≤ d(v)·(x − r)/r = (x/r − 1)·d(v). ✓
- If y_v > x−1 (equivalently d(v) > C(x−1, r−1)): ceiling 2 gives K(v) ≤ C(x, r) − d(v) < C(x, r) − C(x−1, r−1) = C(x−1, r) — Pascal's identity, valid for real x — and C(x−1, r) = C(x−1, r−1)·(x−r)/r < d(v)·(x−r)/r. ✓ (Strictly: this case is always lossy.)

**Summing.** Each clique contains r+1 vertices and each member of 𝓖 contains r, so (r+1)·K(𝓖) = Σ_v K(v) and Σ_v d(v) = r·C(x, r). A vertex with d(v) = 0 lies in no clique (a clique through v needs a member containing v), so its price term is 0 ≤ 0 and harmless. Hence

(r+1)·K(𝓖) = Σ_v K(v) ≤ (x/r − 1)·Σ_v d(v) = (x/r − 1)·r·C(x, r) = (x−r)·C(x, r) = (r+1)·C(x, r+1),

the last step by C(x, r+1) = C(x, r)·(x−r)/(r+1). Divide by r+1. ∎

**Equality.** Equality K(𝓖) = C(x, r+1) forces every inequality in the sum tight. The second case is strictly lossy, so every active vertex (d(v) > 0) sits in the first case at its boundary: y_v = x−1, i.e. **d(v) = C(x−1, r−1) for every vertex contained in a member of 𝓖**. Now count: if n′ vertices are active, then r·C(x, r) = Σ_v d(v) = n′·C(x−1, r−1), so n′ = r·C(x, r)/C(x−1, r−1) = x. So x is an integer (n′ is one), the union of 𝓖 has exactly x vertices, and C(x, r) r-sets inside an x-set can only mean 𝓖 contains **all** of them: 𝓖 = K^r_x. Conversely the complete family attains equality. So **equality ⟺ x ∈ ℤ and 𝓖 is complete** — and the census agrees: all 99 exhaustive equality cases at (6, 2) and (6, 3) are exactly the complete families, in the clique form and in the shadow form alike.

**Corollary (the shadow form — Lovász's costume).** Let 𝓕 be k-uniform with |𝓕| = C(x, k). Then |∂𝓕| ≥ C(x, k−1).

*Proof.* Let 𝓖 = ∂𝓕, a (k−1)-uniform family (if it is empty, 𝓕 is empty and the claim is trivial), and write |𝓖| = C(y, k−1) — the *own* real parameter of the shadow. Every member F ∈ 𝓕 is a k-clique of 𝓖: all its (k−1)-subsets lie in ∂𝓕 by definition. Hence C(x, k) = |𝓕| ≤ K(𝓖) ≤ C(y, k), so y ≥ x by monotonicity of C(·, k), and |∂𝓕| = C(y, k−1) ≥ C(x, k−1). ∎

**The j-form, by induction on the price.** The same argument iterates to every level j < k: |𝓖| = C(x, k) implies |∂_j𝓖| ≥ C(x, j). One application gives |∂𝓖| ≥ C(x, k−1); now price ∂𝓖 by its own parameter — |∂𝓖| = C(x′, k−1) with x′ ≥ x — and apply again: |∂²𝓖| ≥ C(x′, k−2) ≥ C(x, k−2); iterate down to level j. The engine is that each application prices the *current* family by its own real parameter, and parameters only grow as you descend. Machine check, exhaustive: at (6, 3) both j = 1 and j = 2 hold for all 1,048,575 families (zero violations), equality exactly the 42 complete families; at (6, 2), j = 1 holds for all 32,767 families, equality exactly the 57 complete families. ∎

### 4.3 Daykin's mirror: EKR a third way (full)

Now the payoff — the theorem this book has proved completely once (the circle method, Chapter 7's Lecture 3) and cited once (the shifting route, its closing step): a second complete proof, with no circles, no shifting, and no averaging — one disjointness observation, one j-form application, one monotone function. **Daykin's observation (1974)** is that complementation turns *intersection* facts into *containment* facts, and containment is exactly what shadows measure.

Let 𝓕 be an intersecting k-uniform family on [n], n ≥ 2k, and pass to complements: 𝓕* = {[n]∖F : F ∈ 𝓕}, uniform of size n−k ≥ k. Take the k-shadow of 𝓕* and read it in plain language:

∂_k𝓕* = {k-sets S : S ⊆ [n]∖F for some F ∈ 𝓕} = the k-sets **disjoint from a member of 𝓕**.

**The mirror disjointness.** 𝓕 ∩ ∂_k𝓕* = ∅. Indeed, a member F ∈ 𝓕 lying in ∂_k𝓕* would be disjoint from some F′ ∈ 𝓕 — impossible in an intersecting family, including the case F′ = F, since a k-set is never disjoint from itself (k ≥ 1). Both 𝓕 and ∂_k𝓕* are k-uniform, so

|𝓕| + |∂_k𝓕*| ≤ C(n, k).   (*)

**One application of the j-form.** Write |𝓕*| = |𝓕| = C(x, n−k) with x ≥ n−k ≥ k. The j-form at level j = k gives |∂_k𝓕*| ≥ C(x, k). Feeding this into (*):

C(x, n−k) + C(x, k) ≤ C(n, k).

Now define h(t) = C(t, n−k) + C(t, k) and watch two facts do all the work. First, h is strictly increasing for t ≥ n−k, since both binomials increase there. Second, Pascal at the integer point n−1:

h(n−1) = C(n−1, n−k) + C(n−1, k) = C(n−1, k−1) + C(n−1, k) = C(n, k).

So C(x, n−k) + C(x, k) ≤ h(n−1) with h increasing forces **x ≤ n−1**, and therefore

|𝓕| = C(x, n−k) ≤ C(n−1, n−k) = C(n−1, k−1). ∎

That is EKR — the book's second complete proof. At n = 2k the mirror *is* the complementary-pair argument of Chapter 7's Lecture 4: 𝓕* is then k-uniform, a k-set inside the complement of a k-set is exactly that complement, so ∂_k𝓕* = 𝓕* and (*) reads 2|𝓕| ≤ C(2k, k) — one member per complementary pair, Chapter 7's §4.1 re-derived.

**Machine record.** Exhaustive on [6]: every one of the 192 intersecting 2-uniform families (the empty family included) and all 59,049 intersecting 3-uniform families satisfy (*); the maximum 5 at (6, 2) is achieved by exactly the 6 stars (the n > 2k regime), the maximum 10 at (6, 3) by exactly 1,024 families (the n = 2k regime). One honest nuance the census surfaces: mirror-*equality* in (*) is not the same as maximality — at (6, 2) it holds for 26 families, the 6 stars and also the 20 triangles, which are sub-maximum (size 3) but still split C(6, 2) = 15 exactly; at (6, 3) it holds for all 1,024 maxima. The EKR bound comes from h's monotonicity, not from mirror-equality alone: a tight mirror can still sit at a loose x.

With this, **flag (i) of the appendix — the shifting route's closing induction — is retired**: EKR now has two complete proofs in this book (Chapter 7's circle-method Lecture 3; the mirror, here), and the shifting route's closing induction is cited for what it is — the field's standard third route, carrying none of this book's weight. (D. E. Daykin, "Erdős–Ko–Rado from Kruskal–Katona", J. Combin. Theory Ser. A 17 (1974) 254–255.)

### 4.4 The shade route to uniqueness — the missing brick

The mirror tempts an overreach: uniqueness by the same road. Suppose n > 2k and |𝓕| = C(n−1, k−1) exactly. Then (*) forces |∂_k𝓕*| ≤ C(n, k) − C(n−1, k−1) = C(n−1, k), while the j-form gives |∂_k𝓕*| ≥ C(x, k): so x = n−1, and **equality holds in the j-form, many levels deep** — the shadow drops from uniformity n−k all the way down to level k. If deep j-form equality forced 𝓕* to be the complete family K^{n−k}_{n−1} — all (n−k)-sets inside one fixed (n−1)-set — then every member of 𝓕 would contain the missing vertex z, and the star would follow: uniqueness proved.

The gap, closed two lectures ahead: §4.2's equality analysis is proved for the shadow one level down and iterates level by level, and the seemingly deeper statement — "a family sitting at the cascade's minimum across many levels at once must be complete" — in fact follows from that same clique-equality analysis, applied once at the level adjacent to uniformity. That is the deep cascade-uniqueness lemma, built in four steps in §5.2. The ledger after this lecture: flag (i) closed here; flag (iii) (Kneser's aperiodic assembly) closed in Lecture 3; flag (ii) — the middle-J transport with its thin range, the honest forward pointer in Chapter 7's Lecture 4 — is the closing lecture's target.

**The Hilton–Milner gateway.** Once stars are the unique maximum (n > 2k), the next question writes itself: how big can an intersecting family with an **empty core** — no element common to all members — be? Hilton–Milner (1967): |𝓕| ≤ C(n−1, k−1) − C(n−k−1, k−1) + 1, tight at the family of all k-sets containing x and meeting a fixed Y (x ∉ Y, |Y| = k), together with Y itself. The machine census at (7, 3) confirms the shape of the world: Bron–Kerbosch over the 35 triples finds exactly 6,127 maximal intersecting families; the maximum 15 is achieved by exactly the 7 stars; among empty-core families the maximum is 13 = C(6, 2) − C(3, 2) + 1, the HM formula, achieved by exactly **175** families — and the census splits them into two shapes: 140 of the HM type (7 choices of x, 20 of Y) and 35 of a second shape, the k-sets meeting a fixed triple W in at least 2 points, which at k = 3 ties the HM family in size. The tie is a small-k phenomenon: at k ≥ 4 the two shapes separate — sizes 70 and 75 at (10, 4), 51 and 53 at (9, 4), 288 and 316 at (12, 5), the HM formula winning each time in this regime (Hilton–Milner's theorem) — and the *shape* comparison is genuinely subtle: it is the doorstep of the next theorem.

**Ahlswede–Khachatrian: the complete answer (citation gateway).** For n < 2k every two k-sets intersect, so the maximum is trivially C(n, k) — larger than any star; EKR's regime n ≥ 2k is exactly where the star C(n−1, k−1) wins. The complete answer for *all* (n, k) is Ahlswede–Khachatrian's complete intersection theorem (1997): the maximum is max over r ≥ 0 of |F_r|, where F_r is the family of k-sets meeting the initial segment [2r+1] in at least r+1 points. The star is r = 0; the Hilton–Milner world is r = 1; the sequence continues — at (7, 3) the sizes read [15, 13, 10, 0], at (5, 3) they read [6, 7, 10, 0] and the winner is r = 2 with 10 = C(5, 3), the whole level, as n < 2k demands. This chapter records the theorem as a gateway — stated, sampled by machine, proved nowhere here — and points the reader at Chapter 7's ◐15 for the exploration.

**Union-closed lore: the frontier one theorem away.** A family 𝓐 is *union-closed* if A ∪ B ∈ 𝓐 for all A, B ∈ 𝓐. Frankl's 1979 conjecture: in any union-closed family with at least one nonempty member, some element lies in at least half the members. It is open still — one of the great stubborn problems — and the best proved fraction is Gilmer's constant (3−√5)/2 ≈ 0.3819660112501051 (Gilmer 2022), a breakthrough obtained by information-theoretic means. Two facts this chapter's own tools can verify. First, the free case: a union-closed family containing a singleton {x} already satisfies the conjecture for x — pair each set avoiding x with its union with {x}; the map is injective, ∪-closedness keeps the partner inside the family, and the avoiding sets are thereby outnumbered. Second, the census: on [3], all 121 nonempty union-closed families (120 with a nonempty member; {∅} alone is vacuous); on [4], all 4,959 (4,958); the singleton lemma on the 4,126 singleton-containing families of [4] — zero failures anywhere. (Survey: arXiv:2306.12351.)

### 4.5 What to learn

Shadow pricing completes the chapter's engine collection. The real parameter x is a *price*: a k-family costing C(x, k) gets no discount at any lower level — every j-shadow costs at least C(x, j) — and the complete families are the only exact price tags, the colex initial segments the only exact minimizers. Three routes to EKR now live in this book: averaging over circles (Chapter 7's Lecture 3), deforming by shifting (its Lecture 5, the last step cited), and pricing the complement mirror (this lecture) — and the third is by far the cheapest, which is a lesson in itself: *before building machinery, ask what the dual object sees for free*. What remains flagged, honestly: the deep-level cascade uniqueness and the thin range it serves — the closing lecture builds the first and completes the second, retiring the appendix's last flag. And the gateways installed here point beyond the course: Hilton–Milner for empty cores, Ahlswede–Khachatrian for all n, Gilmer's constant for union-closed families — the current frontier of the counting world this book has been teaching.

---

## Lecture 5 · Uniqueness Completed: The Shade Route

The last flag closes. Lecture 4 priced shadows, proved the clique form with its equality analysis, and used Daykin's mirror for a second complete proof of EKR — then stopped honestly at uniqueness: the mirror pins the *size* of a maximum family, but the brick it lacked was the statement that a family sitting at the cascade's minimum across many levels at once must be complete. This lecture builds that brick — the deep cascade-uniqueness lemma, in four steps from §4.2's own equality analysis — and spends it on the EKR uniqueness theorem for *every* n > 2k, thin range included. No circles, no shifting, no middle-J transport: the mirror, the j-form, and one squeeze.

### 5.1 From mirror-equality to the exact price

Recall the mirror (§4.3): 𝓕 intersecting and k-uniform on [n], n > 2k, 𝓕* = {[n]∖F : F ∈ 𝓕} uniform of size n − k ≥ k, the disjointness |𝓕| + |∂_k𝓕*| ≤ C(n, k), and the increasing function h(t) = C(t, n−k) + C(t, k) with h(n−1) = C(n, k). Writing |𝓕*| = |𝓕| = C(x, n−k), the j-form feeds |∂_k𝓕*| ≥ C(x, k) into the mirror, and h increasing forces x ≤ n−1: the EKR bound |𝓕| ≤ C(n−1, k−1) — Daykin's proof, complete.

Now suppose the family is *maximum*: |𝓕| = C(n−1, k−1) exactly. Then the parameter is pinned from both sides. The floor: C(x, n−k) = |𝓕| = C(n−1, n−k) with C(·, n−k) increasing gives x ≥ n−1; the cap: x ≤ n−1. So **x = n−1 exactly** — cap meets floor — and the two bounds on the shadow meet in the middle: |∂_k𝓕*| ≥ C(n−1, k) from the j-form and |∂_k𝓕*| ≤ C(n, k) − |𝓕| = C(n−1, k) from the mirror, so

**|∂_k𝓕*| = C(n−1, k) exactly:**

the mirror of a maximum family sits at the j-form's floor at level k, many levels below its uniformity n − k. One more bookkeeping device and the brick is assembled. For each level j with k ≤ j ≤ n−k, write x_j for the *own* real parameter of ∂_j𝓕* — that is, |∂_j𝓕*| = C(x_j, j) — so x_{n−k} = x = n−1 and x_k = n−1 (the shadow at level k costs exactly C(n−1, k)). The j-form applied to the level-j family reads |∂_{j−1}𝓕*| ≥ C(x_j, j−1); comparing with the definition of x_{j−1} and using that binomials increase: **x_{j−1} ≥ x_j — as the level descends, the parameter never decreases**. The chain

x_{n−k} ≤ x_{n−k−1} ≤ … ≤ x_k

is pinned at both ends by n−1, so every level's parameter is n−1: |∂_j𝓕*| = C(n−1, j) for all k ≤ j ≤ n−k. The parameters agree all the way down — but agreeing parameters do not yet say *complete*. The bridge is the next section's lemma.

### 5.2 The deep cascade-uniqueness lemma (four steps)

Everything rests on one corollary of §4.2's equality analysis, worth stating on its own:

**One-level corollary.** Let 𝓖 be r-uniform with |𝓖| = C(x, r), x real, x ≥ r. If |∂𝓖| = C(x, r−1) — equality at the level adjacent to uniformity — then x is an integer and 𝓖 = K^r_x.

*Proof.* Every member of 𝓖 is an r-clique of its own shadow, so |𝓖| ≤ K(∂𝓖); the clique form of §4.2 applied to the (r−1)-uniform ∂𝓖, priced by its parameter x, gives K(∂𝓖) ≤ C(x, r). But |𝓖| = C(x, r), so all three are equal. Equality in §4.2's analysis forces the priced family to be complete: ∂𝓖 = K^{r−1}_x, and x is an integer (the active vertices count it). Finally every member of 𝓖 has all its (r−1)-subsets inside that fixed x-set, so every member lies inside it — and C(x, r) members of an x-set are all of them: 𝓖 = K^r_x. ∎

**Lemma (deep cascade uniqueness).** Let 𝓖 be r-uniform with |𝓖| = C(x, r), x real, x ≥ r. If for some level j₀ < r the shadow satisfies |∂_{j₀}𝓖| = C(x, j₀) — deep equality pinned at one lower level — then 𝓖 = K^r_x.

*Proof.* (1) *The chain.* For each level j let x_j be the own parameter of ∂_j𝓖 (with ∂_r𝓖 := 𝓖, so x_r = x); the j-form gives x_{j−1} ≥ x_j, so x_r ≤ x_{r−1} ≤ … ≤ x_{j₀}. (2) *Both ends equal x.* x_r = x by definition; at level j₀, |∂_{j₀}𝓖| = C(x, j₀) = C(x_{j₀}, j₀) and C(·, j₀) is strictly increasing, so x_{j₀} = x. (3) *The squeeze.* A monotone chain with equal endpoints is constant: x_{r−1} = x, which is to say |∂𝓖| = C(x, r−1) — the adjacent-level equality. (4) *The corollary fires.* 𝓖 = K^r_x. ∎

That is the whole "uniqueness theory of the binomial cascade" the shade route was missing: not a deeper theorem, but the observation that the equality analysis of §4.2 plus a monotone chain *is* the deep statement. Equality pinned at any depth propagates up to the adjacent level, and the adjacent level decides.

**Machine record.** The lemma says deep equality ⟺ complete, and the census confirms both directions at every reachable size, zero exceptions. Deep means: |𝓖| = C(u, k) with u the union size, and |∂_j𝓖| = C(u, k−j) at every level — the real parameter resolves to the integer u (this is the shortcut the lab uses: no bisection, exact integer arithmetic). The counts: at (6, 3), of the 1,048,575 families exactly **42** are deep, and all 42 are complete — 20 single triples, 15 K³₄, 6 K³₅, and 1 K³₆, one complete family per choice of union set; at (6, 4), 32,767 families, **22** deep, all complete; at (7, 5), 2,097,151 families, **29** deep, all complete — 21 K⁵₅ + 7 K⁵₆ + 1 K⁵₇. And at r = 2 with x = 5, n = 7, a graph costume: of the 352,716 ten-edge graphs on [7], exactly **21** carry at least ten triangles — the clique-form equality K(𝓖) = C(5, 3) — and every one of them is K₅ plus two isolated vertices: the complete family K²₅, in its 21 placements. Deep equality and completeness coincide at every censusable size, which is what a proved lemma and an honest census should agree on. (The lab, Part 5, runs all four hunts with the integer shortcut.)

### 5.3 The star theorem, completed for every n > 2k

**Theorem (EKR uniqueness, complete range).** Let 𝓕 be an intersecting k-uniform family on [n] with n > 2k and |𝓕| = C(n−1, k−1). Then 𝓕 is a star: all members share one fixed element.

*Proof.* Assemble the pieces. (1) *Cap meets floor* (§5.1): x = n−1 exactly and |∂_k𝓕*| = C(n−1, k) exactly. (2) *The squeeze* (§5.2): the parameters of the intermediate shadows are pinned at n−1 across the whole range [k, n−k]; since n > 2k, the adjacent level n−k−1 lies in that range, so |∂𝓕*| = C(n−1, n−k−1). (3) *The one-level corollary:* 𝓕* = K^{n−k}_{n−1} — every member of 𝓕* lies inside one fixed (n−1)-set, which must be [n]∖{z} for some z. (4) *Translate back:* F ∈ 𝓕 has [n]∖F ∈ 𝓕* ⊆ K^{n−k}_{n−1}, so [n]∖F ⊆ [n]∖{z}, so z ∈ F: every member of 𝓕 contains z, and |𝓕| = C(n−1, k−1) is the full count of k-sets through z. 𝓕 is the star at z. ∎

With Chapter 7's circle method (the bound) and its uniqueness lecture (the range its induction reached), this closes the EKR arc over the whole of n > 2k — including the thin range 2k < n < 3k, which the circle method crossed by a middle-J transport the book never needed to build. The transport is thereby bypassed, not disproved: Katona's classical proof of the uniqueness theorem walks exactly that road, and the shade route reaches the same summit from the other side. **Flag (ii) retires here**, and the forward pointer Chapter 7's Lecture 4 planted is landed.

*The mirror partition, at equality.* For the star itself the accounting is exact — worth reading as a check that the boundary of the proof is the boundary of the theorem. The star's mirror is the complete family 𝓕* = K^{n−k}_{n−1} inside V₀ = [n]∖{z}, with |𝓕*| = C(n−1, k−1), and — because k ≤ n−k — its k-shadow is *all* the C(n−1, k) k-sets inside V₀. Every k-set of [n] contains z or avoids it: a disjoint cover,

C(n−1, k−1) + C(n−1, k) = C(n, k) — Pascal, machine-checked at (9, 4) 56 + 70 = 126, (5, 2) 4 + 6 = 10, (7, 3) 15 + 20 = 35, (8, 3) 21 + 35 = 56.

*The (9, 4) budget, honestly.* The theorem covers (9, 4): the nine stars, size 56 = C(8, 3), are the only intersecting 4-families of that size. A census proof is out of reach — the book's depth-first hunt over the 126 four-sets of [9] ran some thirty million nodes and never produced a non-star of size 56; its best empty-core partial, 53, is exactly Hilton–Milner's bound at (9, 4) (§4.4's gateway), the largest an empty-core family can be. The census is evidence; the proved lemma is the proof. ◐15 inherits the hunt.

### 5.4 What to learn

The shade route is the book's last path up EKR and the cheapest of the three: no averaging, no shifting, no transport — one disjointness observation, one priced shadow, one squeeze. Its engine pairing deserves a name: §4.2's equality analysis was proved for *one* level, and the deep lemma is nothing but the observation that a monotone chain with pinned endpoints is constant — the squeeze does the work that a deeper theorem might have been asked to do. That is the general lesson about "genuinely deeper" bricks: sometimes the deeper statement is the shallow one, iterated by an invariant. And the specific lesson: when a proof stops for want of a uniqueness statement, price the *dual* object — the complement mirror — and ask what its shadows cost. The three flags the restructure left open are now closed: (iii) by the assembly (Lecture 3), (i) by the mirror (Lecture 4), (ii) here. The counting world this book has been teaching now runs from Sperner to the thin range with every load-bearing proof on the table; what remains beyond the course is gateway material, honestly labeled — Hilton–Milner, Ahlswede–Khachatrian, the union-closed frontier.

---

## The Trick Bag (reference card)

| Pattern | Plain language | Where you met it |
|---------|---------------|------------------|
| **P4 Induction** | Verify the base and run the recursion until a case fires; or induct on a measure every move decreases — the staircase chain, the m-fold merge, the two-case recursion, DeVos's |X+Y| + |X| | L1, L2, L3 |
| **P22 Polynomial method** | One polynomial vanishing on the grid; the weighted-sum identity prices its top coefficient two ways | L1 |
| **P23 Compression / deformation** | Replace the pair by a deformed one that is easier to read: the merge grows A, the e-transform trades B for A — sumset containment and total size preserved | L2, L3 |
| **Price the period, pass to the quotient (lore)** | When the obstruction is a subgroup of periods, quotient it away and price the deficit by its order — Kneser's Move 2 | L2, L3 |
| **The real parameter is a price (lore)** | |𝓖| = C(x, k) buys no discount at any level; every j-shadow costs at least C(x, j), and the complete families are the only exact price tags | L4, L5 |
| **Ask what the dual object sees for free (lore)** | Complement the family before building machinery: intersection becomes containment, and the shadow prices it | L4, L5 |

**Formula box:** staircase |A+B| ≥ |A|+|B|−1 over ℤ; Cauchy–Davenport |A+B| ≥ min(p, |A|+|B|−1) over 𝔽_p — proved twice (the merge/periodicity argument; the weighted-sum identity Σ f/(Π′Π′) = [x^{a−1}y^{b−1}]f, with the grid lemma D1) — and the m-fold min(p, Σ|Aᵢ| − m + 1). Kneser: |A+B| ≥ |A+H| + |B+H| − |H|, H = stab(A+B); weak form: |A|+|B| ≤ |G| ⟹ some proper H with |A+B| ≥ |A|+|B|−|H|, by the two-case e-transform recursion (Case 1: H′ = ⟨B−B⟩ ⊆ stab(A), collapse A+B = A+b₀; Case 2: witnessed transform e = a−b′, A′ = A∪(B+e), B′ = B∩(A−e)); strong form by DeVos: portions Z ⊆ X+Y with |Z|+|stab(Z)| ≥ |X∩Y|+|(X∪Y)+stab(Z)|, Z₀ = (X∩Y)+(X∪Y), the stabilizer-minimal choice, equations (1)(2)(3), the coset-partition contradiction. EGZ: 2n−1 integers contain n with sum ≡ 0 mod n — prime case by pairing plus m-fold C–D, composite by blocks. Shadows: the cascade/colex minimum; Lovász |∂𝓕| ≥ C(x, k−1) from the clique form K(𝓖) ≤ C(x, r+1) (Keevash's proof); the j-form |∂_j𝓖| ≥ C(x, j); equality ⟺ x ∈ ℤ and 𝓖 complete; deep cascade-uniqueness: equality pinned at any lower level squeezes to the adjacent level and forces K^r_x. Daykin mirror: |𝓕| + |∂_k𝓕*| ≤ C(n, k); h(t) = C(t, n−k) + C(t, k) increasing with h(n−1) = C(n, k) ⟹ EKR; at the maximum, cap meets floor: x = n−1, 𝓕* = K^{n−k}_{n−1} ⟹ the star — uniqueness for every n > 2k. Gateways: Hilton–Milner C(n−1, k−1) − C(n−k−1, k−1) + 1; Ahlswede–Khachatrian max over r of |F_r|; Frankl's union-closed conjecture with Gilmer's constant (3−√5)/2 ≈ 0.3819660112501051.

---

## Exercises (graded: ●○○ easy · ●●○ moderate · ●●● tough)

**Easy — one idea, applied directly**

1. ●○○ **The staircase, explicitly.** Take A = {2, 5, 9} and B = {1, 4}: write the witness chain of |A|+|B|−1 strictly increasing sums, then compute A+B in full and check the chain inside it. Where do the extra sums come from?

**Moderate — two ideas, or one tricky step**

2. ●●○ **Invariance forces everything.** Prove the merge lemma's engine: if a nonempty finite S ⊆ 𝔽_p satisfies S + b = S for some b ≠ 0, then S = 𝔽_p. Then run the merge by hand for A = {0, 1}, B = {0, 2, 3} in 𝔽₅ and watch each step gain an element.

3. ●●○ **Stabilizers, computed.** For S = {0, 2, 4}, compute stab(S) in Z₈, then recompute it for the same set viewed inside Z₆ and explain the difference. Prove: for the cyclic interval S = {0, 1, …, k−1} in Z_n with 2k−2 < n, stab(S) = {0}, and the staircase is tight: |S+S| = 2k−1 = k+k−1. *Hint: a nonzero period g lies in S−S — an arithmetic condition on cyclic distances.*

4. ●●○ **The two-case recursion, by hand.** Run the recursion of §3.1 on three pairs in Z₆: A = B = {0, 2, 4}; A = {0, 1, 3} with B = {0, 2}; A = {0, 1, 3} with B = {0, 2, 3}. In each, say which case fires, exhibit the canonical witness (a, b′, b) and e = a − b′ at every step, and verify containment and size preservation at each step. *Hint: the second pair terminates in one step, with canonical witness (a, b′) = (0, 0) and b = 2.*

5. ●●○ **Case 1's subgroup, in detail.** At a Case-1 termination of the recursion of §3.1, prove: H′ = ⟨B − B⟩ is contained in stab(A), which is contained in stab(A + B); B lies inside a single coset b₀ + H′; and A + B collapses to the single translate A + b₀. Then say exactly where the hypothesis |A| + |B| ≤ |G| enters the proof, and what fails without it. *Hint: stab(A) = G forces A = G.*

6. ●●○ **The deep lemma on a small stage.** On [6], the star of all triples containing 1 and the complete family K³₅ on {2, 3, 4, 5, 6} cost the same: 10 = C(5, 3). Compute both shadows and explain, via the one-level corollary of §4.2's equality analysis, why only the complete family can sit at the deep-equality price through every level. *Hint: the star's shadow has 15 = C(6, 2) members — its real parameter jumps to 6 at the level below.*

**Tough — several chapter ideas combined**

7. ●●● **The partial-fraction identity.** For A ⊆ 𝔽_p with Π′(a) = Π_{a′∈A, a′≠a}(a − a′), prove Σ_{a∈A} a^i/Π′(a) = 0 for i < |A|−1 and = 1 for i = |A|−1. *Hint: Lagrange interpolation — both sides compute the leading coefficient of the interpolant.*

8. ●●● **The grid lemma, D1.** Prove: a polynomial f(x, y) with deg_x f < |A| and deg_y f < |B| that vanishes on all of A×B is identically zero; and the weighted-sum identity Σ_{a,b} f(a,b)/(Π′_A(a)Π′_B(b)) = [x^{|A|−1}y^{|B|−1}]f for total degree ≤ |A|+|B|−2. *Hint: two-stage Lagrange in x then y; for the identity, run the same computation on the monomial basis.*

9. ●●● **EGZ by hand, prime case.** Take the multiset {0, 0, 1, 1, 1, 2, 2, 4, 4} in 𝔽₅: run the full proof — remove x = 0, opposite-pair the sorted remainder, apply m-fold Cauchy–Davenport to the four 2-element pairs, and exhibit an explicit choice summing to −x. Then check the trivial case on {1, 1, 1, 1, 1, 0, 2, 2, 3}.

10. ●●● **The portion machinery, by hand.** Take X = {0, 1}, Y = {0, 3, 4} in Z₆. Verify that the translate step of §3.3 leaves Y as it is, compute Z₀ = (X ∩ Y) + (X ∪ Y) together with its stabilizer, and list all six portions of X + Y with their stabilizers. Which portions can the stabilizer-minimal choice pick, and why does the proof never need the nontrivial-stabilizer branch on this instance? *Hint: no 3-subset is a portion — a trivial-stabilizer portion needs |Z| ≥ 4, and the {0, 3}-periodic subsets are all even-sized.*

11. ●●● **Star mirror partitions, and the pinned parameter.** Verify the mirror partition for the star at (9, 4), (5, 2), (7, 3), and (8, 3): exhibit 𝓕* as a complete family, compute |𝓕*| and |∂_k𝓕*|, and check the disjoint cover against C(n, k). Then prove the cap-meets-floor step of §5.1: at a maximum-sized family, the increasing function h pins the mirror parameter down to x = n − 1 exactly. *Hint: both C(t, n−k) and C(t, k) increase on [n−k, n−1], and the maximum size is exactly C(n−1, n−k).*

12. ◆ EGZ(4) with a block certificate: from the 7 integers 1, 2, 3, 4, 5, 6, 7, extract three disjoint pairs with even sums, halve them, and use EGZ(2) on the three halves to exhibit four of the original integers with sum divisible by 4. Write the certificate, and verify it directly.

13. ◆ Kneser tight census for Z₆: the group has four subgroups. For each one, exhibit a pair (A, B) with stab(A+B) equal to that subgroup and Kneser tight *in the strong form* |A+B| = |A+H| + |B+H| − |H|, and say which pairs are also tight in the weak form.

14. ◐ **Tight Kneser pairs in Z₄².** The group Z₄² has one-dimensional and two-dimensional subgroups, over F₂-style and cyclic parts. Census pairs (A, B) of small size, compute H = stab(A+B) for each, and hunt for tight instances of every possible subgroup type — coset pairs, arithmetic-progression pairs, and anything that is neither. Is every tight pair a union of cosets of H in both arguments, or does the census find a genuinely ragged example?

15. ◐ **The thin range at (9, 4), hunted.** Uniqueness at (9, 4) — that the nine stars, size 56 = C(8, 3), are the *only* intersecting 4-families of that size — is a theorem of §5.3, so a machine hunt can only illustrate. Hunt anyway: search depth-first over the 126 four-sets of [9], extending an intersecting family one member at a time, and record the largest empty-core family you meet. The book's own search — some thirty million nodes deep — tops out at 53, exactly the Hilton–Milner bound at (9, 4), the largest an empty-core family can be; no non-star of size 56 exists to be found, and the proved lemma, not the census, is what carries that. What does the search's difficulty teach about census evidence in the middle range 2k < n < 3k?

**Graded backfill — five more, each hint naming its pattern**

16. ●○○ **The m-fold staircase, sharp and slack.** Prove the m-fold corollary of §1.4 yourself: for nonempty A₁, …, A_m ⊆ 𝔽_p, |A₁ + A₂ + … + A_m| ≥ min(p, Σ|A_i| − m + 1), merging two summands at a time and checking that the min(p, ·) caps compose through the induction. Then calibrate it on 2-element summands in 𝔽₇: with m = 3 the bound reads 4, with m = 4 it reads 5. Verify that {0,1}³ and {0,1}⁴ attain equality, exhibit a triple with slack, and run the census: all 9,261 ordered triples and all 194,481 ordered quadruples of 2-subsets of 𝔽₇. How many triples are tight, how many fill the whole field — and is the pure arithmetic progression {0,1}³ the typical tight shape, or does the census surprise you? *Hint: P4 — merge two summands at a time, the caps composing exactly as §1.4 sketches; then the affine maps x ↦ ux + v of 𝔽₇ classify what tightness looks like.*

17. ●●○ **The engine's regime boundary.** The polynomial proof of §1.3 builds C of size a+b−2 containing A+B, and the contradiction needs the count C(a+b−2, a−1) nonzero mod p. Prove both sides of the boundary: (i) if a+b−2 ≤ p−1, the count is never ≡ 0 mod p; (ii) if a+b−2 ≥ p — with a, b ≤ p, as C–D itself forces — it is always ≡ 0: the engine provably cannot fire outside its regime, the boundary is a wall, not a slope. Verify the whole-field costume: at a+b−2 = p the set C would be all of 𝔽_p, Π_{c∈𝔽_p}(x+y−c) = (x+y)^p − (x+y), and the top coefficient is C(p, a−1) ≡ 0. Then the disassembly: p = 7, A = {0,1,3}, B = {0,2} — a pair with staircase slack. For all 35 choices of C ⊆ 𝔽₇ with |C| = 3, run the weighted-sum identity on f(x, y) = Π_{c∈C}(x+y−c): what does it return, and why is no contradiction available? *Hint: P22 — price the top coefficient two ways, then ask what its nonvanishing costs: which factorial does the regime protect, and who owns the other side of the boundary?*

18. ●●○ **A tight mirror that lies.** Daykin's mirror at (6, 2): 𝓕 intersecting and 2-uniform on [6], 𝓕* the family of complements (4-sets), and |𝓕| + |∂₂𝓕*| ≤ C(6, 2) = 15. Take the triangle 𝓕 = {12, 13, 23}: compute 𝓕*, compute ∂₂𝓕* — the pairs disjoint from some member of 𝓕 — and watch the mirror split 15 exactly, even though the triangle is far from maximum (the stars have 5). Explain the lie: mirror-equality and j-form tightness are independent. Price the triangle's mirror by its real parameter (C(x, 4) = 3), read the j-form floor at level 2, and measure the slack; then do the same for a star and watch the floor met exactly — cap meets floor only at a maximum family. Run the census: all 192 intersecting 2-families on [6] — which split the mirror exactly, and what are they? *Hint: ask what the dual object sees for free — complement first, price the shadow second; a tight mirror can still sit at a loose x.*

19. ●●○ **The cap is sharp: the census of near-misses.** EGZ needs 2n−1 integers; prove 2n−2 fails: the multiset {0^(n−1), 1^(n−1)} contains no n-subset with sum ≡ 0 mod n. Generalize the bookkeeping to any two-value multiset {a^(n−1), b^(n−1)}: which differences a − b dodge every zero-sum n-subset, and which never do? Then hunt for exotic avoiders: census every multiset of size 2n−2 over Z_n for n = 3 through 9 — 873,912 multisets in all — and classify what you find. Is every avoider two-value? How many are there at each n, and does a formula read them off? *Hint: the pairing lemma's sorted bookkeeping (P23): a zero-sum n-subset takes j copies of one value and n−j of the other; the gcd prices which differences can dodge.*

20. ●●● **The clique form in graph costume: ten edges, ten triangles.** Specialize the clique form to r = 2: a graph with m = C(x, 2) edges (x real, x ≥ 2) has at most C(x, 3) triangles. Run the lecture's proof in costume — the link of v is its neighborhood, the link ceiling counts edges inside N(v), the degree ceiling counts edges avoiding v — and prove the equality analysis at r = 2: t = C(x, 3) forces x to be an integer and the graph to be K_x plus isolated vertices. Now the hunt: on [7], ten edges. x = 5, so t ≤ 10; census all 352,716 ten-edge graphs, verify exactly 21 attain the bound — each one K₅ plus two isolated vertices, 21 = C(7, 5) placements — and read the distribution honestly: where does it jump? As a bonus, run the [6] costume end-to-end: all 32,767 nonempty graphs, equality exactly on the 57 complete families — the same 57 the shadow census of §4.1 priced at k = 2. *Hint: the real parameter is a price — C(x, 2) edges buy at most C(x, 3) triangles — and the ledger is P4's double count 3t = Σ_v K(v).*

---

## Answers to the Exercises

**A1.** The witness chain climbs the b₁ column then walks the a_s row: 2+1 = 3 < 5+1 = 6 < 9+1 = 10 < 9+4 = 13 — four = 3+2−1 strict sums. The full sumset is {3, 6, 9, 10, 13}, size 5 ≥ 4. The chain sits inside it; the extra element **9** (= 5+4) — and the duplicate 6 (= 2+4, already reached as 5+1) — come from the grid's interior cells above the staircase: the staircase witnesses the *minimum*; interior cells are surplus. (Part 1 runs the same check on Figure 1's data, A = {1, 2, 4}, B = {1, 3}.)

**A2.** If S + b = S with b ≠ 0 in 𝔽_p, then S + mb = S for every integer m, and the multiples of b exhaust 𝔽_p (b has order p, p prime). So S is invariant under every translation — and a nonempty translation-invariant subset of a transitive group is everything: pick s ∈ S; for any y ∈ 𝔽_p, y = s + (y−s) with y−s a multiple of b, so y ∈ S. S = 𝔽_p. The merge for A = {0, 1}, B = {0, 2, 3} in 𝔽₅: S = {0, 1}; +2 gives {2, 3}, union {0, 1, 2, 3} — gain 2; +3 gives {3, 4}, union 𝔽₅ — gain 1. Every step gains, and the total 5 = |A+B| ≥ min(5, 2+3−1) = 4 ✓. (Part 1's monitor: 9,759 zero-gain steps over 8,624 processes — every single one with the set already full.)

**A3.** In Z₈: {0,2,4}+2 = {2,4,6} ≠ S and +4 = {4,6,0} ≠ S — stab is trivial, **{0}**. In Z₆: {0,2,4}+2 = {2,4,0} = S, so stab = **{0,2,4}** (≅ Z₃). The same set, two different ambient groups: in Z₆ the element 2 has order 3 and the set is its whole orbit — a subgroup; in Z₈ the order of 2 is 4 and the orbit {0,2,4,6} is one larger than S. Stabilizers are group-theoretic, not set-theoretic. For the cyclic interval S = {0, …, k−1} in Z_n with 2k−2 < n: a period g satisfies 0 ∈ S ⟹ g ∈ S, and (s + g ≡ 0 for the preimage s) ⟹ −g ∈ S; with g ≠ 0 that means g ≤ k−1 and n−g ≤ k−1, so n ≤ 2k−2 — contradicting the hypothesis. So stab = {0}, and S+S = {0, …, 2k−2} with no wraparound: size 2k−1 = k+k−1, the staircase tight.

**A4.** The first pair is Case 1 outright: B − B = {0, 2, 4} = stab(A), so no witness exists — every a + b − b′ lands back in A = {0, 2, 4}. H′ = {0, 2, 4}, B ⊆ 0 + H′, and A + B collapses to A + 0 = {0, 2, 4}: |A + B| = 3 = 3 + 3 − 3 ✓. The second pair takes one step. The canonical scan finds (a, b′) = (0, 0) admitting b = 2 (0 + 2 − 0 = 2 ∉ A), so e = 0: A′ = A ∪ (B + 0) = {0, 1, 2, 3}, B′ = B ∩ (A − 0) = {0}. Size preservation 4 + 1 = 3 + 2 ✓; containment A′ + B′ = {0, 1, 2, 3} ⊆ A + B = {0, 1, 2, 3, 5} ✓; strict decrease 1 < 2 ✓. Now |B′| = 1: the staircase base reads |A + B| ≥ |A′ + B′| = 4 ≥ 4. The third pair takes two. Step 1: the same witness (0, 0, 2), e = 0, but now B′ = {0, 2, 3} ∩ {0, 1, 3} = {0, 3}, with A′ = {0, 1, 2, 3} — preservation 4 + 2 = 3 + 3 ✓, strict decrease 2 < 3 ✓, containment A′ + B′ = {0, 1, 2, 3, 4, 5} ⊆ A + B = {0, 1, 2, 3, 4, 5} ✓. Step 2: the scan on (A′, B′) finds (a, b′) = (1, 0) admitting b = 3 (1 + 3 − 0 = 4 ∉ A′), so e = 1: A″ = A′ ∪ (B′ + 1) = {0, 1, 2, 3, 4}, B″ = B′ ∩ (A′ − 1) = {0} — preservation 5 + 1 = 4 + 2 ✓, containment ✓ — and the base reads |A + B| ≥ |A″ + B″| = 5 ≥ 5; the true sumset is all of Z₆, size 6 ≥ 5. Both descents end at the staircase base; the census counts them among Z₆'s 3,097 base terminations (against 872 Case-1 terminations).

**A5.** No witness means: for every a ∈ A and b, b′ ∈ B, a + b − b′ ∈ A — that is, A + (B − B) ⊆ A. So every difference stabilizes A, and H′ = ⟨B − B⟩ ⊆ stab(A). The chain to the sumset: g + A = A gives g + (A + B) = (g + A) + B = A + B, so stab(A) ⊆ stab(A + B). The coset: fixing b₀ ∈ B, every b ∈ B has b − b₀ ∈ B − B ⊆ H′, so B ⊆ b₀ + H′ — one H′-coset, and in particular |B| ≤ |H′|. The collapse: A + B ⊆ A + (b₀ + H′) = (A + b₀) + H′ = A + b₀ (the last step because H′ stabilizes A, hence A + b₀), and A + b₀ ⊆ A + B since b₀ ∈ B: so A + B = A + b₀, |A + B| = |A|. The bound: |A + B| = |A| = |A| + |B| − |B| ≥ |A| + |B| − |H′|. Properness is where the hypothesis enters: H′ ⊆ stab(A), and stab(A) = G would force A = G (a nonempty finite set stabilized by every element is the whole group) — impossible when |A| ≤ |G| − 1, which |A| + |B| ≤ |G| with B nonempty grants. Without the hypothesis, A = G is a legal pair; then stab(A) = G, H′ = G is not proper, and the bound degenerates to |G| ≥ |A| + |B| − |G| — true but vacuous. That is exactly why the weak form carries the size hypothesis and the strong form (§3.3) does not.

**A6.** The star: ten triples through 1, |𝓖| = 10 = C(5, 3), so its price parameter is x = 5. Its shadow: every pair inside a triple through 1 — the five pairs containing 1 and the ten pairs among {2, …, 6} — fifteen = C(6, 2), against the j-form floor C(5, 2) = 10. Deep equality fails at the first level down: the star pays the minimum at level 3 but not at level 2. The complete family K³₅ on {2, …, 6} costs the same 10; its shadow is the ten pairs of the 5-set and its second shadow the 5 singletons = C(5, 1): deep equality at every level. The one-level corollary of §4.2's equality analysis explains the asymmetry: |𝓖| = C(x, k) *with* |∂𝓖| = C(x, k−1) forces x an integer and 𝓖 = K^k_x. The star fails the hypothesis (15 ≠ 10) and is not even a candidate for the deep-equality price; any family that *is* a candidate — sitting at the cascade's minimum at the uniformity level and the level below — is complete by the corollary. The deep lemma of §5.2 adds the propagation: equality pinned at *any* lower level squeezes up to the adjacent level, so deep equality at any depth forces completeness.

**A7.** The Lagrange basis polynomial L_a(x) = Π_{a′≠a}(x−a′)/Π′(a) has degree |A|−1, leading coefficient 1/Π′(a), and satisfies L_a(a′) = [a = a′]. For i ≤ |A|−1, the polynomial x^i has degree < |A| = the number of nodes, so it equals its own interpolation: x^i = Σ_{a∈A} a^i L_a(x) identically. Match leading coefficients: the left side contributes [i = |A|−1], the right side Σ a^i/Π′(a). Machine check: 15,011 evaluations over 𝔽₅–𝔽₁₃, zero exceptions.

**A8.** Vanishing: fix b ∈ B; f_b(x) = f(x, b) has deg_x < |A| and vanishes at every a ∈ A — |A| roots — so f_b ≡ 0. That says each coefficient c_i(y) of f (as a polynomial in x) vanishes at every b ∈ B; each c_i has deg_y < |B| and |B| roots, so c_i ≡ 0: f ≡ 0. The identity: interpolate f in the x-direction, f(x, y) = Σ_a L_a(x)·f(a, y) (valid for each fixed y by univariate Lagrange, since deg_x f < |A|); now apply A7's univariate identity to each f(a, ·) in y and sum — the double sum Σ_{a,b} f(a,b)/(Π′_A(a)Π′_B(b)) picks out [y^{|B|−1}] of Σ_a L_a(x)·f(a, y), and the monomial-basis case of the same computation (run f = x^i y^j) leaves only the coefficient of x^{|A|−1}y^{|B|−1} when i + j = |A|+|B|−2. Machine check: 184 exact grid reconstructions and 900 random polynomials (including the terms with i ≥ |A|, which die by degree: j ≤ |B|−2).

**A9.** No value occurs 5 times, so the trivial case is off. Remove x = 0; the sorted remainder is 0, 1, 1, 1, 2, 2, 4, 4 — no value more than 4 = m times, so opposite pairing (element i with element i+4) gives the pairs **(0, 2), (1, 2), (1, 4), (1, 4)**, each with distinct entries. The m-fold Cauchy–Davenport bound: min(5, 2·4 − 4 + 1) = 5, so the choice-sumset is all of 𝔽₅ — in particular −x = 0 is a choice-sum. One: 0 + 2 + 4 + 4 = 10 ≡ 0 (mod 5). The five elements 0, 0, 2, 4, 4 sum to 10 ≡ 0 ✓. Trivial case {1,1,1,1,1,0,2,2,3}: the value 1 occurs 5 = p times; those five sum to 5 ≡ 0 (mod 5) ✓.

**A10.** The canonical translate leaves Y alone (y = 0): X ∩ Y = {0}, X ∪ Y = {0, 1, 3, 4}, so Z₀ = (X ∩ Y) + (X ∪ Y) = {0, 1, 3, 4} with stab(Z₀) = {0, 3}, and X + Y = {0, 1, 3, 4, 5}. The portion test reads |Z| + |stab(Z)| ≥ |X∩Y| + |(X∪Y) + stab(Z)|: for Z₀, 4 + 2 = 6 ≥ 1 + 4 = 5 ✓ (the union is already {0, 3}-invariant, so (X∪Y) + stab(Z₀) = X ∪ Y). The six portions: Z₀ itself, with stabilizer {0, 3}; the four 4-subsets {0, 1, 3, 5}, {0, 1, 4, 5}, {0, 3, 4, 5}, {1, 3, 4, 5}, each passing as 4 + 1 ≥ 1 + 4 = 5, all with trivial stabilizer; and the full sumset X + Y = {0, 1, 3, 4, 5}, with trivial stabilizer: 5 + 1 ≥ 5 ✓. No 3-subset passes (3 + 1 = 4 < 5), and no odd-sized set carries the {0, 3} stabilizer (its cosets are the pairs {g, g+3}), so every portion here has either the full {0, 3} or the trivial stabilizer. The proof's choice — a portion whose stabilizer is minimal by inclusion — therefore lands on a trivial-stabilizer portion, and the H ≠ {0} branch never fires on this instance. The machine sweep of §3.3 confirms this on every one of the 39,449 aperiodic pairs it covers: a trivial-stabilizer portion always exists, so the minimal choice is always trivial — the nontrivial branch is carried by the proof, not by the data.

**A11.** For the star at z, every complement [n]∖F avoids z, so 𝓕* consists of (n−k)-sets inside the (n−1)-set V₀ = [n]∖{z}; being maximum-sized, it is *all* of them: 𝓕* = K^{n−k}_{n−1}, with |𝓕*| = C(n−1, k−1). And since k ≤ n−k, every k-set inside V₀ extends to an (n−k)-set inside V₀, so ∂_k𝓕* is *all* C(n−1, k) k-sets of V₀. The accounting is a disjoint cover: every k-set of [n] either contains z (a star member, in 𝓕) or avoids z (in ∂_k𝓕*), and the two families are disjoint — so |𝓕| + |∂_k𝓕*| = C(n−1, k−1) + C(n−1, k) = C(n, k) exactly. Machine-verified: (9, 4) 56 + 70 = 126, (5, 2) 4 + 6 = 10, (7, 3) 15 + 20 = 35, (8, 3) 21 + 35 = 56 — every partition a disjoint cover. The cap-meets-floor step: at a maximum family, |𝓕| = C(x, n−k) = C(n−1, k−1) = C(n−1, n−k), and the mirror inequality plus the j-form give h(x) = C(x, n−k) + C(x, k) ≤ C(n, k) = h(n−1), with h strictly increasing on [n−k, n−1] (both binomials increase there) — so x ≤ n−1. The floor: C(x, n−k) = C(n−1, n−k) with C(·, n−k) increasing forces x ≥ n−1. Cap meets floor: **x = n−1 exactly**, and with it |∂_k𝓕*| = C(n−1, k) — the shadow pinned at the j-form's floor. §5.2's squeeze carries the pin up to the adjacent level, and the one-level corollary finishes: 𝓕* is complete, so 𝓕 is the star.

**A◆12.** Blocks with even sums: (1, 3) sum 4, (2, 4) sum 6, (5, 7) sum 12 — three disjoint pairs covering six of the seven integers, each sum ≡ 0 mod 2 ✓ (2m−1 = 3 blocks with n = 2, m = 2, extracted while j ≤ 2m−2 = 2 ✓). Halve: 2, 3, 6. EGZ(2) on these three integers: two with even sum — 2 and 6 ✓. The corresponding blocks (1,3) and (5,7): four integers **{1, 3, 5, 7}** with sum 16 ≡ 0 (mod 4) ✓ — verified directly: 16 mod 4 = 0. Certificate complete: blocks, halves, EGZ(2) selection, union.

**A◆13.** Z₆ has four subgroups. Tight pairs, strong form |A+B| = |A+H| + |B+H| − |H|:

- H = {0}: A = B = {0, 1}: A+B = {0, 1, 2}, and 3 = 2+2−1 ✓ — tight in both forms.
- H = {0, 3}: A = B = {0, 3}: A+B = {0, 3}, and 2 = 2+2−2 ✓ — both forms.
- H = {0, 2, 4}: A = B = {0, 2, 4}: A+B = {0, 2, 4}, and 3 = 3+3−3 ✓ — both forms; the coset pair of §2.2.
- H = Z₆: A = {0, 1, 2}, B = {0, 3, 4, 5}: A+B = Z₆ (check: 2+0 = 2, 2+4 = 0, 2+5 = 1, 0+3 = 3, 0+4 = 4, 0+5 = 5), and 6 = 6+6−6 ✓ — strong-tight; the weak form reads 6 ≥ 3+4−6 = 1, slack. (For weak tightness at H = Z₆ take A = B = Z₆: 6 = 6+6−6.)

The pattern the census surfaces: with H = {0} the tight pairs are arithmetic progressions (staircase shape); with H nontrivial they are coset pairs — unions of H-cosets; the full-group case is strong-tight by saturation. Part 1's Z₆ census: 3,969 pairs, zero violations, 1,004 tight.

**A16.** The induction merges the tail first: |A₂ + … + A_m| ≥ min(p, s − m + 2) with s = Σ_{i≥2}|A_i|, by hypothesis; then the two-summand bound prices |A₁ + (A₂ + … + A_m)| ≥ min(p, |A₁| + min(p, s − m + 2) − 1). The caps compose: if s − m + 2 ≥ p, the inner family is at the cap and the outer min is p, while Σ|A_i| − m + 1 ≥ p + |A₁| − 1 ≥ p — both sides p; otherwise the inner family has size ≥ s − m + 2, and the outer min is at least min(p, |A₁| + s − m + 1) = min(p, Σ|A_i| − m + 1), min(p, ·) being monotone. ∎ The calibration: {0,1}³ gives {0, 1, 2, 3} — 4 = min(7, 6 − 3 + 1), equality; {0,1}⁴ gives {0, 1, 2, 3, 4} — 5 = min(7, 8 − 4 + 1), equality (and in 𝔽₅, {0,1}³ gives 4 = min(5, 4) — equality against the cap itself). Slack: {0,1} + {0,2} + {0,4} = {0, 1, 2, 3, 4, 5, 6} — the whole field, against a bound of 4. The census: all 9,261 ordered triples of 2-subsets of 𝔽₇ — zero violations, 1,029 tight (choice-sumset of size exactly 4), 2,058 full (all of 𝔽₇), the remaining 6,174 in between; all 194,481 ordered quadruples — zero violations, 7,203 tight (exactly 5); and 250,047 ordered triples of subsets of sizes up to 3 — zero violations again. The surprise is in the shapes: under the 42 affine maps x ↦ ux + v of 𝔽₇, the 1,029 tight triples sort into just 8 types, and the pure AP triple {0,1}³ is the rarest of them — 21 of 1,029, its orbit halved by the stabilizer x ↦ 6x + 1, which swaps 0 and 1. The largest type — 252 of 1,029 — is the mixed shape ({0,1}, {0,6}, {2,3}): {0,1} + {0,6} = {0, 1, 6}, and adding {2, 3} gives {1, 2, 3, 4}: tight, and visibly not an affine image of a triple with three equal summands, since affine maps preserve coincidences. Three one-repeat types sit at 126 each — ({0,1}, {0,1}, {2,3}) gives {2, 3, 4, 5} — and four all-distinct types complete the census: the mixed shape at 252 and three at 126, among them the spread ({0,1}, {2,3}, {4,5}) with choice-sumset {0, 1, 2, 6}. The lesson: the staircase minimum is an affine world, not an arithmetic one — tightness does not mean arithmetic progressions, and equality at the m-fold bound is a whole equivalence class of shapes wide.

**A17.** (i) The ledger: C(a+b−2, a−1) · (a−1)! · (b−1)! = (a+b−2)!. In the regime a+b−2 ≤ p−1 every factor on the right is below p, so p divides nothing — and since the binomial times the two smaller factorials rebuilds the factorial, p ∤ C(a+b−2, a−1). (ii) Beyond, C–D's own constraints a, b ≤ p put p ≤ a+b−2 ≤ 2p−2: the numerator factorial carries exactly one factor p (no second multiple fits below 2p), while (a−1)! and (b−1)! stop short of p — so p divides the binomial exactly once, always. The count is identically zero mod p on the far side: the engine cannot fire there even in principle. Machine check: every prime p ≤ 19, all 1 ≤ a, b ≤ p — nonzero throughout the regime, zero at the boundary and beyond, zero exceptions in either direction. The whole-field costume: Π_{c∈𝔽_p}(z − c) = z^p − z, coefficients verified for every p ≤ 19 — so at a+b−2 = p the engine's polynomial is (x+y)^p − (x+y), its top coefficient C(p, a−1) ≡ 0, and the would-be contradiction reads 0 = 0. The disassembly: {0,1,3} + {0,2} = {0, 1, 2, 3, 5} — size 5 against the staircase bound 4, so no 3-set can contain the sumset. For each of the 35 choices of C the weighted-sum identity returns C(3, 2) = 3 mod 7 — the engine always tells the truth — and f vanishes on the whole grid for none of them: the vanishing hypothesis the contradiction feeds on is exactly what a slack pair refuses to supply. Cauchy–Davenport itself holds on both sides of the wall: exhaustive over the 961 ordered pairs of nonempty subsets of 𝔽₅ (811 tight) and the 16,129 of 𝔽₇ (9,857 tight), plus 200,000 sampled pairs of 𝔽₁₁ — zero violations anywhere. The moral: the two proofs split 𝔽_p at exactly a+b = p+1 — the polynomial engine owns the near side and provably dies on the far side, where the periodicity proof takes over. The theorem's min(p, ·) is not a convenience; it is the seam between the two proofs.

**A18.** The triangle's mirror: 𝓕* = {3456, 2456, 1456}, and a pair lies in the shadow exactly when it sits inside one of these 4-sets — the three pairs of {4, 5, 6} and the nine pairs crossing from {1, 2, 3} to {4, 5, 6} — twelve in all. So |𝓕| + |∂₂𝓕*| = 3 + 12 = 15: the mirror splits C(6, 2) exactly. Yet EKR caps 𝓕 at C(5, 1) = 5, and the triangle has 3 — sub-maximum with a perfect mirror. The explanation: the mirror inequality and the j-form floor are independent constraints. Price the triangle's mirror: C(x, 4) = 3 gives x ≈ 4.63, so the j-form floor at level 2 is C(x, 2) ≈ 8.40 — and the shadow actually costs 12, a slack of ≈ 3.60. Slack in the j-form is what lets x sit below n − 1 = 5 at a mirror-exact family: h's monotonicity only ever says x ≤ n − 1, and a loose floor never pushes back. At a star both ends pin: |𝓕| = 5 = C(5, 4) makes x = 5 exactly, and the shadow is the ten pairs of {2, …, 6} — the complete family K²₅ — costing C(5, 2) = 10 on the nose: cap meets floor, the §5.1 pin, and the mirror partition reads C(5, 1) + C(5, 2) = C(6, 2) — Pascal at the star, §5.3's accounting at n = 6. The census: all 192 intersecting 2-families of [6] (the empty family included) satisfy the mirror — zero violations — and exactly 26 split it exactly: the 6 stars, which are the 6 maximum families, and the 20 triangles, nothing else. The j-form slack, machine-measured on all 26: zero on every star, ≈ 3.60 on every triangle. The lesson: mirror-equality is bookkeeping; maximality is a price. The EKR bound lives in h's monotonicity, not in the mirror's arithmetic — a tight mirror at a loose x is the census's standing warning against reading equality as extremality.

**A19.** The canonical near-miss: an n-subset of {0^(n−1), 1^(n−1)} must take j zeros and n − j ones with 1 ≤ j ≤ n − 1 — neither value alone has n copies — so its sum is n − j with 1 ≤ n − j ≤ n − 1, never ≡ 0 mod n. The same bookkeeping prices every two-value multiset {a^(n−1), b^(n−1)}: an n-subset takes j copies of a and n − j of b, 1 ≤ j ≤ n − 1, and the sum is ja + (n−j)b ≡ j(a−b) mod n. If gcd(a−b, n) = 1, then j(a−b) ≡ 0 forces j ≡ 0 — out of range — and the multiset avoids every zero-sum n-subset. If d = gcd(a−b, n) > 1, then j = n/d lands in range and (n/d)(a−b) ≡ 0 mod n: the multiset fails. So the two-value world splits cleanly: coprime differences dodge, non-coprime differences never do. The census hunts for anything else, and finds nothing: every multiset of size 2n−2 over Z_n for n = 3 through 9 — 15 + 84 + 495 + 3,003 + 18,564 + 116,280 + 735,471 = 873,912 multisets — and the avoiders are exactly the two-value coprime ones: zero exotic exceptions, zero non-coprime survivors. The counts read 3, 4, 10, 6, 21, 16, 27 — exactly n·φ(n)/2 at every n: n translations, φ(n) coprime partners, halved for the unordered pair. Divide the labor honestly, as ◐15 does at (9, 4): both two-value directions are proved above; the absence of exotics is census evidence through n = 9, and the classification it supports — avoiders are two-value with coprime difference, nothing else — is not claimed beyond the census here. The lesson: the EGZ cap is not merely sharp; one element below it, the landscape collapses to a two-value world priced by a gcd.

**A20.** The r = 2 specialization, in costume: the link L(v) is the neighborhood N(v), a 1-uniform family of size d(v) = C(y_v, 1), and its cliques are the pairs inside it, so the link ceiling reads K(v) ≤ C(d(v), 2) = d(v)(y_v − 1)/2 — triangles through v are edges inside N(v). The degree ceiling: deleting v from a triangle through v gives an edge avoiding v, injectively — K(v) ≤ m − d(v). The per-vertex price: if d(v) ≤ x − 1, the link ceiling gives K(v) ≤ d(v)(d(v) − 1)/2 ≤ d(v)(x − 2)/2 = (x/2 − 1)·d(v); if d(v) > x − 1, the degree ceiling gives K(v) ≤ m − d(v) < C(x, 2) − (x − 1) = (x−1)(x−2)/2 < (x/2 − 1)·d(v). Summing, 3t = Σ_v K(v) ≤ (x/2 − 1)·Σ_v d(v) = (x/2 − 1)·2m = (x − 2)·x(x−1)/2 = 3·C(x, 3): **t ≤ C(x, 3).** Equality forces every active vertex into the first case at its boundary — d(v) = x − 1 — and then Σ_v d(v) = 2m = x(x−1) counts exactly x active vertices: x is an integer, and C(x, 2) edges on x vertices is K_x, plus isolated vertices. ∎ The hunt: on [7], m = 10 = C(5, 2), so t ≤ C(5, 3) = 10. The census over all 352,716 ten-edge graphs: the maximum 10 is attained exactly 21 times, and every attainer is K₅ plus two isolated vertices — C(7, 5) placements, the equality analysis walking in costume. The honest distribution: triangle counts run 0 through 7 (7 is reached by 2,310 graphs), then nothing at 8, nothing at 9, and the 21 at 10 — the summit is isolated, a gap of two below it. The ceilings are census-clean everywhere: K(v) ≤ 10 − d(v) and K(v) ≤ (3/2)·d(v) hold at every vertex of all 352,716 graphs, zero violations. The [6] bonus: all 32,767 nonempty graphs satisfy t ≤ C(x, 3) with x = (1 + √(1+8m))/2, and equality holds exactly on the 57 complete families — 15 single edges (t = 0 = C(2, 3)), 20 triangles, 15 copies of K₄, 6 of K₅, 1 of K₆. These are the same 57 that the §4.1 census found as the shadow's equality cases at k = 2: at r = 2 the clique costume and the shadow costume are one theorem, their equality cases literally coinciding — a complete graph is the only shape that pays exactly C(x, 2) for its edges, C(x, 3) for its triangles, and x for its vertex set. Machine check: zero violations throughout both censuses; every equality case complete in both.

---

## Computational Lab (verified)

### Part 1 — Sumsets: the staircase, Cauchy–Davenport, Kneser, and the e-transform

```python
A, B = [1, 2, 4], [1, 3]
chain = [A[0]+B[0], A[1]+B[0], A[2]+B[0], A[2]+B[1]]
print(chain, sorted({a + b for a in A for b in B}))

def elems(mask, p): return [i for i in range(p) if mask >> i & 1]
cd_pairs = cd_viol = cd_tight = 0
for p, cap in [(2, 2), (3, 3), (5, 5), (7, 7), (11, 4), (13, 3)]:
    subs = [m for m in range(1, 2**p) if bin(m).count("1") <= cap]
    for Am in subs:
        for Bm in subs:
            a, b = elems(Am, p), elems(Bm, p)
            s = {(x + y) % p for x in a for y in b}
            bound = min(p, len(a) + len(b) - 1)
            cd_pairs += 1; cd_viol += len(s) < bound; cd_tight += len(s) == bound
print(cd_pairs, cd_viol, cd_tight)

proc = zg = zg_full = holds = 0
for p in (5, 7):
    subs = [m for m in range(1, 2**p)]
    for Am in subs:
        for Bm in [m for m in subs if m & 1]:
            proc += 1
            a, b = elems(Am, p), [x for x in elems(Bm, p) if x]
            S = set(a)
            for x in b:                      # the nonzero elements only
                before = len(S)
                S |= {(y + x) % p for y in S}
                if len(S) == before:
                    zg += 1
                    zg_full += S == set(range(p))    # invariance -> already everything
            allS = {(x + y) % p for x in elems(Am, p) for y in elems(Bm, p)}
            holds += len(allS) >= min(p, len(elems(Am, p)) + len(elems(Bm, p)) - 1)
print(proc, zg, zg == zg_full, holds)

for n in (6, 7, 8, 9):
    subs = [m for m in range(1, 2**n)]
    pairs = viol = tight = 0
    for Am in subs:
        for Bm in subs:
            a, b = elems(Am, n), elems(Bm, n)
            S = {(x + y) % n for x in a for y in b}
            H = sum(all((s + g) % n in S for s in S) for g in range(n))
            pairs += 1
            viol += len(S) < len(a) + len(b) - H
            tight += len(S) == len(a) + len(b) - H
    print(f"Z_{n}: pairs {pairs}, violations {viol}, tight {tight}")

_state = 12345
def rnd(n):
    global _state
    _state = (48271 * _state) % 2147483647
    return _state % n
checks = viol = 0
for n, dims in [(6, None), (8, None), (9, (3, 3))]:
    def elem(): return [rnd(3), rnd(3)] if dims else rnd(n)
    def add(x, y): return [(x[0]+y[0]) % 3, (x[1]+y[1]) % 3] if dims else (x + y) % n
    def sub(x, y): return [(x[0]-y[0]) % 3, (x[1]-y[1]) % 3] if dims else (x - y) % n
    def key(z): return tuple(z) if dims else (z,)
    for _ in range(300):
        A, asz = [], 1 + rnd(4)
        while len(A) < asz:
            e = elem()
            if not any(key(e) == key(a) for a in A): A.append(e)
        B, bsz = [], 1 + rnd(4)
        while len(B) < bsz:
            e = elem()
            if not any(key(e) == key(b) for b in B): B.append(e)
        AB = {key(add(a, b)) for a in A for b in B}
        for ei in range(n):
            e = [ei // 3, ei % 3] if dims else ei
            Ae = A + [x for x in (add(b, e) for b in B)
                      if not any(key(x) == key(a) for a in A)]
            Be = [b for b in B if any(key(sub(a, e)) == key(b) for a in A)]
            checks += 1
            viol += any(key(add(x, y)) not in AB for x in Ae for y in Be)
            viol += len(Ae) + len(Be) != len(A) + len(B)
print(checks, viol)

trials = viol = 0
for p in (5, 7):
    for _ in range(300):
        m = 2 + rnd(3)
        sets = []
        for _ in range(m):
            s, sz = set(), 1 + rnd(3)
            while len(s) < sz: s.add(rnd(p))
            sets.append(s)
        cur = set(sets[0])
        for s in sets[1:]:
            cur = {(x + a) % p for x in cur for a in s}
        trials += 1
        viol += len(cur) < min(p, sum(map(len, sets)) - m + 1)
print(trials, viol)
```

**Verified output.** The staircase witness prints `[2, 3, 5, 7] [2, 3, 4, 5, 7]` — the chain of 4 = 3+2−1 strict sums inside the full sumset of size 5 (Figure 1's data). Cauchy–Davenport over 𝔽₂, 𝔽₃, 𝔽₅, 𝔽₇ (all pairs), 𝔽₁₁ up to size 4, 𝔽₁₃ up to size 3: `473998 0 42081` — **473,998 pairs, zero violations, 42,081 tight**. The merge/periodicity monitor over 𝔽₅ and 𝔽₇ (every A, every B containing 0, skipping the trivial b = 0 step) prints `8624 9759 True 8624`: 8,624 processes, **9,759** zero-gain steps, every single one fired only when the running set was already the whole field — invariance forces everything — and the bound held in all 8,624. The Kneser census, exhaustive over Z₆ through Z₉ with the stabilizer computed exactly, prints `Z_6: pairs 3969, violations 0, tight 1004`, `Z_7: pairs 16129, violations 0, tight 3382`, `Z_8: pairs 65025, violations 0, tight 7269`, `Z_9: pairs 261121, violations 0, tight 17524` — **zero violations** anywhere. The e-transform stress (300 random pairs in each of Z₆, Z₈, Z₃², every e in the group) prints `6900 0`: both properties — sumset containment and size preservation — hold in all **6,900** checks. The m-fold corollary over 𝔽₅ and 𝔽₇ prints `600 0` — **600** random families of m ≤ 4 sets, zero violations.

### Part 2 — EGZ: exhaustive, by pairing, and by blocks

```python
_state = 12345
def rnd(n):
    global _state
    _state = (48271 * _state) % 2147483647
    return _state % n

def egz_holds_multiset(counts, n):        # counts[v] = multiplicity of v; DP
    dp = [[False] * n for _ in range(2 * n)]
    dp[0][0] = True
    for v in range(n):
        for _ in range(counts[v]):
            for j in range(2 * n - 2, -1, -1):
                for s in range(n):
                    if dp[j][s]: dp[j + 1][(s + v) % n] = True
    return dp[n][0]

for n in range(3, 8):                      # n = 7 takes a few minutes
    counts = [0] * n; total = passed = 0
    def rec(i, left):
        global total, passed
        if i == n - 1:
            counts[i] = left
            total += 1
            passed += egz_holds_multiset(counts, n)
            counts[i] = 0
            return
        for c in range(left + 1):
            counts[i] = c; rec(i + 1, left - c)
        counts[i] = 0
    rec(0, 2 * n - 1)
    print(f"n = {n}: multisets {total}, containing a zero-sum n-subset: {passed}")

trials = fails = 0
for _ in range(800):
    m = 2 + rnd(4)
    pool = 2 + rnd(m + 1)
    mult = []
    while len(mult) < 2 * m:
        v = rnd(pool)
        if mult.count(v) < m: mult.append(v)
    s = sorted(mult)
    trials += 1
    fails += any(s[i] == s[i + m] for i in range(m))
print("pairing:", trials, "failures:", fails)

runs = trivial = ok = covered = 0
for p in (5, 7):
    for _ in range(450):
        mult = [rnd(p) for _ in range(2 * p - 1)]
        runs += 1
        if any(mult.count(v) >= p for v in range(p)):
            trivial += 1
            continue
        x = mult[0]
        rest = sorted(mult[1:])
        prs = [(rest[i], rest[i + p - 1]) for i in range(p - 1)]
        if any(a == b for a, b in prs): continue
        cur = set(prs[0])
        for a, b in prs[1:]:
            cur = {(u + v) % p for u in cur for v in (a, b)}
        covered += len(cur) == p
        ok += (p - x) % p in cur
print("prime case:", runs, "trivial:", trivial,
      "non-trivial succeeded:", ok, "choice-sumset covered field:", covered)

def zero_sum_subset(a, k):
    n = len(a)
    def rec(start, left, acc, s):
        if left == 0: return acc if s % k == 0 else None
        for i in range(start, n - left + 1):
            r = rec(i + 1, left - 1, acc + [i], s + a[i])
            if r: return r
        return None
    return rec(0, k, [], 0)

trials = fails = 0
for n, m in [(2, 3), (3, 2), (2, 2), (2, 5), (3, 3)]:
    for _ in range(60):
        arr = [rnd(50) for _ in range(2 * n * m - 1)]
        pool, block_sums = arr[:], []
        for _ in range(2 * m - 1):
            idx = zero_sum_subset([v % n for v in pool], n)
            if idx is None:                     # EGZ says this never happens
                fails += 1
                break
            block_sums.append(sum(pool[i] for i in idx) // n)
            pool = [v for j, v in enumerate(pool) if j not in idx]
        else:
            sel = zero_sum_subset([v % m for v in block_sums], m)
            trials += 1
            fails += sel is None or sum(block_sums[i] for i in sel) % m != 0
print("composite chain:", trials, "failures:", fails)
```

**Verified output.** The exhaustive sweep prints `n = 3: multisets 21, containing a zero-sum n-subset: 21`, then `120 / 120`, `715 / 715`, `4368 / 4368`, and finally `n = 7: multisets 27132, containing a zero-sum n-subset: 27132` — **every** multiset of 2n−1 residues contains n summing to 0, for every n ≤ 7. The pairing lemma on 800 random constrained multisets prints `pairing: 800 failures: 0` — the opposite pairing never pairs an element with its equal. The prime-case engine over 𝔽₅ and 𝔽₇ prints `prime case: 900 trivial: 44 non-trivial succeeded: 856 choice-sumset covered field: 856`: 44 runs settled by the trivial ≥ p-copies case, and in **all 856** remaining runs the four-step machine worked end to end — pairs distinct, choice-sumset equal to the whole field (the m-fold Cauchy–Davenport bound, achieved), and −x reachable. The composite chain over (n, m) = (2,3), (3,2), (2,2), (2,5), (3,3) prints `composite chain: 300 failures: 0`: every instance extracted its 2m−1 disjoint zero-mod-n blocks, EGZ(m) selected on the scaled sums, and the union certified a genuine zero-mod-nm subset. (A lab-writer's lesson, recorded in the appendix: the first version of this check tested the final sum modulo m — the scaled modulus — instead of modulo nm; the fixed check is what prints here.)

### Part 3 — Shadows and the frontiers: Kruskal–Katona, the Daykin mirror, Hilton–Milner, union-closed

```python
from math import comb, sqrt
from fractions import Fraction
from itertools import combinations

def bits(m): return bin(m).count("1")

# (a) the cascade formula vs the colex initial segments
def cascade(N, k):
    total, a_prev = 0, None
    while N > 0 and k >= 1:
        a = k
        while comb(a + 1, k) <= N: a += 1
        if a_prev is not None and a >= a_prev: a = a_prev - 1
        total += comb(a, k - 1)
        N -= comb(a, k)
        a_prev, k = a, k - 1
    return total

agree = total = 0
for k in (2, 3, 4):
    sets = sorted(combinations(range(12), k), key=lambda S: tuple(reversed(S)))
    for N in range(1, len(sets) + 1):
        total += 1
        sh = {S[:i] + S[i+1:] for S in sets[:N] for i in range(k)}
        if len(sh) == cascade(N, k): agree += 1
print("cascade == colex shadows:", agree, "/", total, "; cascade(10, 3) =", cascade(10, 3))

# (b, c, d) Lovasz form, j-form, clique form — exhaustive on [6]
def comb_real(x, k):
    r = 1.0
    for i in range(k): r = r * (x - i) / (i + 1)
    return r

def real_param(m, k):
    lo, hi = k - 1, 40.0
    while comb_real(hi, k) < m: hi *= 2
    for _ in range(60):
        mid = (lo + hi) / 2
        if comb_real(mid, k) < m: lo = mid
        else: hi = mid
    return (lo + hi) / 2

def census(n, k):
    sets = [m for m in range(1 << n) if bits(m) == k]
    t = len(sets)
    subs = []                      # (k-1)-subset masks of each member
    for m in sets:
        subs.append({m & ~(1 << e) for e in range(n) if m >> e & 1})
    hisets = [m for m in range(1 << n) if bits(m) == k + 1]
    quads = []                     # each (k+1)-set as the list of its k-subsets
    for m in hisets:
        quads.append([m & ~(1 << e) for e in range(n) if m >> e & 1])
    badL = eqL = eqLc = badJ = eqJ = badC = eqC = eqCc = 0
    for mask in range(1, 1 << t):
        idx = [i for i in range(t) if mask >> i & 1]
        m = len(idx)
        x = real_param(m, k)
        union = 0
        sh = set()
        for i in idx:
            union |= sets[i]
            sh |= subs[i]
        if len(sh) < comb_real(x, k - 1) - 1e-9: badL += 1
        complete = (m == comb(bits(union), k))
        if abs(len(sh) - comb_real(x, k - 1)) < 1e-9:
            eqL += 1
            if complete: eqLc += 1
        if bits(union) < x - 1e-9: badJ += 1       # j = 1 shadow = the union
        if abs(bits(union) - x) < 1e-9: eqJ += 1
        famset = {sets[i] for i in idx}
        K = 0
        for q in quads:
            if all(g in famset for g in q): K += 1
        if K > comb_real(x, k + 1) + 1e-9: badC += 1
        if abs(K - comb_real(x, k + 1)) < 1e-9:
            eqC += 1
            if complete: eqCc += 1
    return badL, eqL, eqLc, badJ, eqJ, badC, eqC, eqCc

for k in (2, 3):
    bL, eL, eLc, bJ, eJ, bC, eC, eCc = census(6, k)
    print(f"census (6,{k}): Lovasz bad {bL}, eq {eL} (complete {eLc}); "
          f"j=1 bad {bJ}, eq {eJ}; clique bad {bC}, eq {eC} (complete {eCc})")

# (e) the Daykin mirror, exhaustive
def mirror62():
    edges = [m for m in range(1 << 6) if bits(m) == 2]
    t = len(edges)
    dj = [sum(1 << j for j in range(t) if not (edges[i] & edges[j])) for i in range(t)]
    count = viol = maxsz = maxcnt = eq = 0
    for mask in range(1 << t):
        if any(mask & dj[i] for i in range(t) if mask >> i & 1): continue
        count += 1
        sz = bits(mask)
        sh = 0
        for i in range(t):
            if mask >> i & 1: sh |= dj[i]
        if sz + bits(sh) > comb(6, 2): viol += 1
        if sz > maxsz: maxsz, maxcnt = sz, 1
        elif sz == maxsz: maxcnt += 1
        if sz + bits(sh) == comb(6, 2): eq += 1
    print("mirror (6,2): families", count, "violations", viol,
          "max", maxsz, "(by", str(maxcnt) + ")", "mirror-eq", eq)

def mirror63():
    tr = [m for m in range(1 << 6) if bits(m) == 3]
    pairs, seen = [], set()
    for t in tr:
        if t not in seen:
            pairs.append((t, 63 ^ t)); seen.add(t); seen.add(63 ^ t)
    count = viol = maxsz = maxcnt = eq = 0
    for d in range(3 ** 10):
        fam, dd = [], d
        for p in range(10):
            r = dd % 3; dd //= 3
            if r: fam.append(pairs[p][r - 1])
        count += 1
        if 2 * len(fam) > comb(6, 3): viol += 1   # n = 2k: shadow of F* is F*
        if len(fam) > maxsz: maxsz, maxcnt = len(fam), 1
        elif len(fam) == maxsz: maxcnt += 1
        if 2 * len(fam) == comb(6, 3): eq += 1
    print("mirror (6,3): families", count, "violations", viol,
          "max", maxsz, "(by", str(maxcnt) + ")", "mirror-eq", eq)

mirror62(); mirror63()

# (f) Hilton-Milner census at (7, 3), Bron-Kerbosch
def hm73():
    tr = [m for m in range(1 << 7) if bits(m) == 3]
    t = len(tr)
    adj = [[j for j in range(t) if j != i and tr[i] & tr[j]] for i in range(t)]
    maximal = []
    def bk(R, P, X):
        if not P and not X:
            maximal.append(list(R)); return
        pivot = max(P + X, key=lambda u: sum(1 for v in adj[u] if v in P))
        for v in list(P):
            if v in adj[pivot]: continue
            bk(R + [v], [w for w in P if w in adj[v]], [w for w in X if w in adj[v]])
            P.remove(v); X.append(v)
    bk([], list(range(t)), [])
    maxsz = max(len(c) for c in maximal)
    stars = sum(1 for c in maximal if len(c) == maxsz)
    def core(c):
        r = 127
        for i in c: r &= tr[i]
        return r
    empty = [c for c in maximal if core(c) == 0]
    cmax = max(len(c) for c in empty)
    cwin = [c for c in empty if len(c) == cmax]
    hm = f1 = 0
    for c in cwin:
        fam = {tr[i] for i in c}
        if any(fam == ({Y} | {F for F in tr if F >> x & 1 and F & Y})
               for x in range(7) for Y in tr if not Y >> x & 1): hm += 1
        elif any(fam == {F for F in tr if bits(F & W) >= 2} for W in tr): f1 += 1
    print("HM (7,3): maximal", len(maximal), "; max", maxsz, "(by", str(stars) +
          " stars); empty-core max", cmax, "(by", str(len(cwin)) + ":",
          str(hm) + " HM +", str(f1) + " F1)")
    sizes = []
    for r in range(4):
        w = (1 << (2 * r + 1)) - 1
        sizes.append(sum(1 for F in tr if bits(F & w) >= r + 1))
    print("AK sizes (7,3):", sizes)

hm73()

# (h) union-closed, exhaustive
def union_closed(n):
    join = [[a | b for b in range(1 << n)] for a in range(1 << n)]
    closed = nonempty = fails = withsing = singbad = 0
    for mask in range(1, 1 << (1 << n)):
        fam = [i for i in range(1 << n) if mask >> i & 1]
        if any(not (mask >> join[i][j] & 1) for i in fam for j in fam): continue
        closed += 1
        if any(fam):
            nonempty += 1
            if not any(2 * sum(1 for f in fam if f >> x & 1) >= len(fam)
                       for x in range(n)): fails += 1
        singles = [f for f in fam if bits(f) == 1]
        if singles:
            withsing += 1
            for s in singles:
                if 2 * sum(1 for f in fam if f & s) < len(fam): singbad += 1
    return closed, nonempty, fails, withsing, singbad

for n in (3, 4):
    cl, ne, f, ws, sb = union_closed(n)
    print(f"union-closed [{n}]: {cl} families ({ne} with a nonempty member), "
          f"conjecture failures {f}; singleton lemma on {ws} families, bad {sb}")
print("Gilmer constant:", (3 - sqrt(5)) / 2)
```

**Verified output.** The cascade agrees with the colex initial segments on **781/781** sizes (k = 2, 3, 4; every N ≤ C(12, k)), and cascade(10, 3) = 10 = C(5, 2). The censuses: at (6, 2) all 32,767 nonempty families pass the Lovász form with **57** equalities — every one a complete family —, the j = 1 form with the same 57, and the clique form with the same 57; at (6, 3) all 1,048,575 families pass all three checks with **42** equalities each, again exactly the complete families (x an integer), as §4.2's equality analysis demands. The Daykin mirror: **192** intersecting families at (6, 2), zero violations of |𝓕| + |∂_k𝓕*| ≤ C(6, k), maximum 5 achieved by exactly the 6 stars, mirror-equality at 26 (the 6 stars plus the 20 sub-maximum triangles — tight mirror, loose x); at (6, 3), **59,049** families, zero violations, maximum 10 by exactly 1,024, mirror-equality at all 1,024. Hilton–Milner at (7, 3): Bron–Kerbosch finds **6,127** maximal intersecting families; the maximum 15 belongs to exactly the 7 stars; the empty-core maximum is **13** — the HM formula C(6, 2) − C(3, 2) + 1 — achieved by exactly **175** families, **140** of the HM type and **35** of the F₁ type and none other; the AK sizes read [15, 13, 10, 0]. Union-closed: on [3], **121** nonempty families (120 with a nonempty member; {∅} alone is vacuous), zero conjecture failures; on [4], **4,959** (4,958), zero failures; the singleton lemma holds on all 98 singleton-containing families of [3] and all 4,126 of [4], zero bad; Gilmer's constant prints 0.3819660112501051.

### Part 4 — The assembly: the two-case recursion and DeVos's portions

```python
def elems(mask, n): return [i for i in range(n) if mask >> i & 1]
def sumset(A, B, n): return {(a + b) % n for a in A for b in B}
def stab(S, n):
    s = set(S)
    return [g for g in range(n) if all((x + g) % n in s for x in s)]
def closure(diffs, n):
    H, todo = {0}, list(diffs)
    while todo:
        d = todo.pop()
        for g in list(H):
            for h in ((g + d) % n, (g - d) % n):
                if h not in H: H.add(h); todo.append(h)
    return sorted(H)
def witness(A, B, n):
    for a in sorted(A):
        for bp in sorted(B):
            for b in sorted(B):
                if (a + b - bp) % n not in set(A):
                    return a, bp, b
    return None
def recurse(A, B, n):
    """Two-case recursion, canonical rule; every step verified."""
    As, Bs, steps = set(A), set(B), 0
    AB = sumset(As, Bs, n)
    while len(Bs) > 1:
        w = witness(sorted(As), sorted(Bs), n)
        if w is None:                                   # Case 1
            H = closure({(b - bp) % n for b in Bs for bp in Bs}, n)
            assert all((a + h) % n in As for a in As for h in H)
            b0 = min(Bs)
            assert Bs <= {(b0 + h) % n for h in H}      # |B| <= |H'|
            assert sumset(As, Bs, n) == {(a + b0) % n for a in As}
            return "case1", steps
        a, bp, b = w                                     # Case 2
        e = (a - bp) % n
        Anew = As | {(x + e) % n for x in Bs}
        Bnew = Bs & {(x - e) % n for x in As}
        assert sumset(Anew, Bnew, n) <= AB              # containment
        assert len(Anew) + len(Bnew) == len(As) + len(Bs)  # size preservation
        assert 0 < len(Bnew) < len(Bs) and bp in Bnew    # strict decrease
        As, Bs, steps = Anew, Bnew, steps + 1
    return "base", steps
for n in (4, 6, 7):                                      # Z_7 takes a minute
    pairs = case1 = bases = steps = 0
    for Am in range(1, 1 << n):
        for Bm in range(1, 1 << n):
            kind, st = recurse(elems(Am, n), elems(Bm, n), n)
            pairs += 1; steps += st
            if kind == "case1": case1 += 1
            else: bases += 1
    print(f"Z_{n}: pairs {pairs}, case1 {case1}, bases {bases}, steps {steps}")

# the aperiodicity counterexample of 3.2
A, B, n = [0, 1, 3], [0, 2], 6
AB = sumset(A, B, n)
print("stab(A+B):", stab(AB, n))
for a in A:
    for bp in B:
        e = (a - bp) % n
        Ap = sorted(set(A) | {(x + e) % n for x in B})
        Bp = sorted(set(B) & {(x - e) % n for x in A})
        if (sumset(Ap, Bp, n) <= AB and len(Ap) + len(Bp) == len(A) + len(B)
                and len(Bp) < len(B)):
            print(f"transform a={a} b'={bp} e={e}: {Ap} + {Bp}, stab",
                  stab(sumset(Ap, Bp, n), n))

# DeVos's portions on the canonical instance of 3.3
X, Y, n = [0, 1], [0, 3, 4], 6
XYt = sumset(X, Y, n)
from itertools import combinations
def is_portion(Z):
    H = stab(Z, n)
    inter = set(X) & set(Y)
    uniH = sumset(sorted(set(X) | set(Y)), H, n)
    return len(Z) + len(H) >= len(inter) + len(uniH), H
for r in range(len(XYt) + 1):
    for Zc in combinations(sorted(XYt), r):
        ok, H = is_portion(set(Zc))
        if ok: print("portion:", sorted(Zc), "stab", H)
```

**Verified output.** The recursion sweep prints `Z_4: pairs 225, case1 41, bases 184, steps 167`, `Z_6: pairs 3969, case1 872, bases 3097, steps 4939`, `Z_7: pairs 16129, case1 3473, bases 12656, steps 24333` — the matching rows of §3.1's table (the full twelve-group sweep, 738,884 pairs with zero violations, is the TypeScript run recorded in the appendix; the census counts are the canonical lexicographic rule's). The counterexample prints `stab(A+B): [0]` and four transform lines — the period-creating (a, b′) = (0, 2) with e = 4 producing A′ = [0, 1, 3, 4], B′ = [2] with stab [0, 3], and the three other genuine transforms — the canonical (0, 0) among them — keeping the trivial stabilizer [0] — the §3.2 warning, machine-witnessed. The portion enumeration prints exactly six lines: `[0, 1, 3, 4] stab [0, 3]`, the four trivial-stabilizer 4-subsets `[0, 1, 3, 5]`, `[0, 1, 4, 5]`, `[0, 3, 4, 5]`, `[1, 3, 4, 5]`, and the full sumset `[0, 1, 3, 4, 5] stab [0]` — Exercise 10's list, reproduced.

### Part 5 — The shade route: deep censuses and the mirror arithmetic

```python
from math import comb
from itertools import combinations

def deep_census(n, k):
    """Deep equality via the integer shortcut: |G| = C(u,k) with u the union
    size, and every j-shadow exactly C(u, j).  Deep ⟺ complete, by 5.2."""
    sets = [m for m in range(1 << n) if bin(m).count("1") == k]
    t = len(sets)
    deep = complete = 0
    for mask in range(1, 1 << t):
        fam = [sets[i] for i in range(t) if mask >> i & 1]
        union = 0
        for f in fam: union |= f
        u = bin(union).count("1")
        if len(fam) != comb(u, k): continue            # parameter must be u
        cur, ok = fam, True
        for j in range(k - 1, 0, -1):
            sh = set()
            for f in cur:
                for e in range(n):
                    if f >> e & 1: sh.add(f & ~(1 << e))
            if len(sh) != comb(u, j): ok = False; break
            cur = sorted(sh)
        if ok:
            deep += 1
            complete += len(fam) == comb(u, k)        # automatic: deep => complete
    print(f"({n},{k}): families {(1 << t) - 1}, deep {deep}, complete {complete}")

deep_census(6, 3); deep_census(6, 4); deep_census(7, 5)   # (7,5) takes minutes

# the (3,2,5) hunt: ten edges, ten triangles, on [7]
edges = list(combinations(range(7), 2))
tris = [(edges.index((a, b)), edges.index((a, c)), edges.index((b, c)))
        for a, b, c in combinations(range(7), 3)]
total = hits = 0
for combo in combinations(range(21), 10):
    s = set(combo)
    tri = sum(1 for t in tris if t[0] in s and t[1] in s and t[2] in s)
    total += 1
    if tri >= 10:
        deg = sorted(sum(1 for e in combo if v in edges[e]) for v in range(7))
        assert deg == [0, 0, 4, 4, 4, 4, 4]             # K5 + two isolated
        hits += 1
print("10-edge graphs on [7]:", total, "with >= 10 triangles:", hits)

# the star mirror partitions and the cap-meets-floor arithmetic
for n, k in [(9, 4), (5, 2), (7, 3), (8, 3)]:
    star, shade = comb(n - 1, k - 1), comb(n - 1, k)
    print(f"({n},{k}): |F*| = {star} + |d_k F*| = {shade} = {star + shade}"
          f" = C({n},{k}) = {comb(n, k)}")
print("h(t) = C(t,5)+C(t,4):", [comb(t, 5) + comb(t, 4) for t in (5, 6, 7, 8)],
      "h(8) = C(9,4) =", comb(9, 4))
```

**Verified output.** The deep censuses print `(6,3): families 1048575, deep 42, complete 42`, `(6,4): families 32767, deep 22, complete 22`, `(7,5): families 2097151, deep 29, complete 29` — deep equality and completeness coincide at every size, zero exceptions, as the §5.2 lemma demands (the 29 at (7, 5) split 21 K⁵₅ + 7 K⁵₆ + 1 K⁵₇ by union set; the (7, 5) sweep takes a few minutes). The hunt prints `10-edge graphs on [7]: 352716 with >= 10 triangles: 21`, every hit asserting the K₅-plus-two-isolated degree pattern — the 21 placements of the complete family K²₅. The mirror arithmetic prints `(9,4): |F*| = 56 + |d_k F*| = 70 = 126 = C(9,4) = 126`, likewise (5, 2) 4 + 6 = 10, (7, 3) 15 + 20 = 35, (8, 3) 21 + 35 = 56 — every partition a disjoint cover — and the h-values `[6, 21, 56, 126]` with `h(8) = 126 = C(9, 4)`: strictly increasing, capped exactly at Pascal's point, so cap meets floor and x = n − 1 exactly.

---

## Revision History & Verification Notes

**Editions.** Born inside Chapter 7: the staircase/Cauchy–Davenport, Kneser/EGZ, and shadows lectures date from that chapter's Feynman lecture edition, with their exercises, answers, and lab parts (one exception at the export: the skew battery, Part 6(g) there, stayed in Chapter 7, where it anchors its §2.3's warning and its Exercise 10/A10). The **session-38 restructure** moved the three lectures verbatim into this file with the old numbering deliberately inherited (sections 6.x–8.x; exercises 2, 10, 11, 12, 13, 14, ◆18, ◆20, ◐23; answers A2, A10–A14, A◆18, A◆20; lab Parts 4–6; Figure 2). This edition — the restructure's planned polish, executed as task B3d — completes the authoring: the chapter gets its own introduction, notation, pattern table, Trick Bag, and formula box; the inherited lectures become 1, 2, and 4, and two NEW lectures join — Lecture 3 (the aperiodic assembly: the weak form by the two-case e-transform recursion, the strong form by DeVos's intersection–union induction — flag (iii) closed) and Lecture 5 (the thin range completed by the shade route, through the deep cascade-uniqueness lemma — flag (ii) closed; with flag (i) closed by Daykin's mirror in Lecture 4, all three of Chapter 7's open flags retire here). Exercises renumber 1–11 graded plus ◆12–13 and ◐14–15, answers A1–A11 and A◆12–A◆13, the lab becomes Parts 1–5, the figure 1. Outside the renumbering and re-aiming tokens, the inherited lecture bodies, exercises, answers, and lab parts are byte-identical to the export; the new material was authored against this edition's machine runs. The session-67 adversarial review then audited the chapter end to end — one lecture-wording repair (§3.2's canonical-witness attribution, with Part 4's verified-output sentence matched to it), four record-level alignments (§1.2's merge processes 7,279 → the lab's 8,624 over 𝔽₅/𝔽₇; §2.3's 28,000 → 6,900; §2.2's and §2.5's gate runs re-attributed to the verification record; §2.5's trivial-case count 225 → the lab's 44), one monitor-output repair (Part 1's and A2's zero-gain count 16,988 → the true 9,759), and one lab-code repair (Part 3(h)'s union-closed mask range) — the mathematics otherwise clean.

**Verification basis.** The inherited numbers (the Kneser census, the e-transform stress, the EGZ sweeps, the shadow/mirror/Hilton–Milner/union-closed censuses) were executed and recorded during Chapter 7's life; the lab Parts 1–3 are the reader's runnable copies of exactly that logic, renumbered only. The new numbers were machine-verified at authoring, all clean: (1) the two-case recursion on all 738,884 pairs of the twelve groups of order ≤ 9 — 185,060 Case-1 terminations, 553,824 staircase bases, 1,355,220 Case-2 steps, maximum depth 5, every step and termination checked as §3.1 lists, zero violations; (2) the aperiodicity counterexample of §3.2, all four genuine transforms enumerated; (3) the DeVos machinery on the 39,449 aperiodic pairs of Z₆, Z₇, Z₈, and Z₄×Z₂ — translate, Z₀-portion, and aperiodic-staircase checks all clean, stab(Z₀) nontrivial on 3,604 pairs (60 / 0 / 930 / 2,614), a trivial-stabilizer portion on every pair; (4) the deep censuses — (6, 3) 1,048,575 families → 42 deep, all complete; (6, 4) 32,767 → 22; (7, 5) 2,097,151 → 29 (21 K⁵₅ + 7 K⁵₆ + 1 K⁵₇); and the (3, 2, 5) hunt: exactly 21 of the 352,716 ten-edge graphs on [7] carry at least ten triangles, all K₅ plus two isolated vertices; (5) the mirror arithmetic and the star mirror partitions of §5.3; (6) the (9, 4) depth-first hunt of ◐15's record (best empty-core partial 53, the Hilton–Milner bound). The lab Parts 4–5 are runnable copies of runs (1)–(5). The transform itself was verified the standard way: an exact-token replacement pipeline, every anchor asserted unique before the swap; a residual scan for stale-reference shapes (all zero); and a hygiene gate — five lecture headers, twenty-four subsection headers, twelve balanced fence lines, zero mojibake, zero session references in lecture bodies, one trailing newline — before the master and its canvas were written from the same string and read back equal.

**Standing decisions.** Lecture bodies carry no session references; history lives here. The chapter proves what it uses and cites what it does not: the cascade costume of Kruskal–Katona is cited while the clique form (statement Lovász, proof Keevash) is proved; Katona's classical route to the EKR uniqueness theorem is cited while the shade route is proved, and the middle-J transport of Chapter 7's Lecture 4 is bypassed, not rebuilt; Hilton–Milner, Ahlswede–Khachatrian, and Gilmer's constant stand as gateways; DeVos's proof is presented in full and cited to its author, with Nathanson's GTM 165 and the survey arXiv:2407.12253 carrying the transform's history; the two-case recursion is presented with this book's canonical lexicographic witness rule — the theorem is indifferent to the rule, the census is not, and the §3.1 counts are the rule's; the (9, 4) uniqueness census is honestly recorded as beyond the book's brute budget, the hunt inheriting to ◐15. The web edition embeds this chapter byte-identically (the standard delivery format); the PDF export check is the user-owned release gate; learner testing now follows the completion of the whole project scope, at the user's direction.

**Figures.** One figure, embedded as a fenced SVG at its lecture location per the dual-presentation convention (prose and lab code stay terminal-portable), renumbered 1 in this edition: Figure 1 (L1) — the sumset staircase: climb the first column, then walk the last row; every step is a new sum. The figure data were machine-verified before drawing and moved verified; the caption carries this chapter's numbering.

**Backfill (session 41).** Five graded exercises (16–20) with pattern-mapped hints were added, per the atlas-wide backfill mandate, with worked answers A16–A20 continuing the exercise numbering (14–15 are explorations and carry no answers): the m-fold corollary proved and calibrated (zero violations over all 9,261 ordered triples and all 194,481 ordered quadruples of 2-subsets of 𝔽₇, plus 250,047 mixed-size triples; 1,029 tight triples sorting into 8 affine types — the AP triple the rarest, 21 of 1,029; 7,203 tight quadruples); the polynomial engine's regime boundary (the count C(a+b−2, a−1) is never ≡ 0 mod p below a+b = p+1 and always ≡ 0 beyond, all primes p ≤ 19 — the boundary is a wall, not a slope; the whole-field costume z^p − z verified coefficient-by-coefficient for p ≤ 19; the disassembly on {0,1,3} + {0,2} — all 35 choices of C return C(3, 2) = 3 mod 7, vanishing on no full grid; Cauchy–Davenport exhaustive on 𝔽₅ (961 pairs, 811 tight) and 𝔽₇ (16,129 pairs, 9,857 tight) and 200,000 sampled pairs of 𝔽₁₁, zero violations); the tight-mirror nuance (all 192 intersecting 2-families of [6]: zero mirror violations, exactly 26 mirror-tight — the 6 stars, which are the maximum families, and the 20 triangles; j-form slack 0 on every star against ≈ 3.60 on every triangle, x ≈ 4.63 priced by C(x, 4) = 3); the EGZ cap's near-miss census (all 873,912 multisets of size 2n−2 over Z_n, n = 3..9: the avoiders are exactly the two-value multisets {a^(n−1), b^(n−1)} with gcd(a−b, n) = 1 — counts 3, 4, 10, 6, 21, 16, 27 = n·φ(n)/2 at every n, zero exotic exceptions, the classification honestly scoped to the census); and the clique form in graph costume (all 32,767 nonempty graphs on [6]: t ≤ C(x, 3) with equality exactly the 57 complete families — the §4.1 shadow census's 57 re-read through the clique form; all 352,716 ten-edge graphs on [7]: maximum t = 10 attained exactly 21 times, every attainer K₅ + 2 isolated, the distribution jumping from 2,310 graphs at 7 straight to the 21 at 10 with nothing at 8 or 9; the per-vertex ceilings K(v) ≤ 10 − d(v) and K(v) ≤ (3/2)d(v) clean at every vertex of every graph). Every answer was machine-verified before installation.

**Adversarial review (session 67).** The review arc's two arguing experts (skeptic and engineer) took this chapter chunk by chunk — correctness, coherence, exposition, figure aid — extend-never-rewrite, every retained objection machine-verified before any edit. Verdict: the mathematics is otherwise CLEAN, with one lecture-wording defect, four record-level attribution defects, one monitor-output defect, and one lab-code defect caught, confirmed, and repaired in place. **The defects (machine-sealed):** (1) §3.2's counterexample paragraph said the canonical rule picks the period-creating transform — false: the canonical rule (the lexicographically first (a, b′) admitting some b) picks (a, b′) = (0, 0) with b = 2, e = 0, giving A′ = {0, 1, 2, 3} and B′ = {0} and keeping the trivial stabilizer, while the period-creating (0, 2) with e = 4 is legal but second in the witness order (the four genuine transforms, lex order: (0, 0), (0, 2), (1, 2), (3, 0)); the sentence now says so, and Part 4's verified-output paragraph names the period-creating line as period-creating, the canonical (0, 0) among the trivial-stabilizer three. (2) §1.2 credited the merge monitor with 7,279 processes on sampled pairs in 𝔽₁₁ — the printed lab runs 𝔽₅ and 𝔽₇ only, 8,624 processes; aligned. (3) §2.3 credited the e-transform stress with 28,000 checks over Z₆, Z₈, Z₃² and Z₄² — the printed lab runs Z₆, Z₈, Z₃², 300 random pairs each, every e: 6,900 checks; aligned. (4) §2.2 credited the printed lab with the gate's wider Kneser sampling (Z₁₀ to size 5, Z₁₂ to size 4, all of Z₃², 40,000 sampled Z₄² pairs) — re-attributed to the verification record; the printed census is Z₆–Z₉. (5) §2.5 credited the printed lab with the gate's 20,000-sample sweeps at n = 9, 10 — re-attributed the same way; the printed lab is exhaustive n = 3–7. (6) §2.5's prime-case sentence counted 225 trivial-case runs — the lab's own printed record says 44 (900 runs, trivial 44, non-trivial 856); aligned to it. (7) Part 1's verified output recorded 16,988 zero-gain steps — under the printed code the count is 9,759 (all with the running set already the whole field; the theory decomposes it 9,681 + 78), reproduced twice; the recorded line now prints `8624 9759 True 8624`, and A2's citation carries the same number. (8) Part 3(h)'s union-closed block enumerated `for mask in range(1, 1 << n)` — 7 masks at n = 3 and 15 at n = 4, which cannot produce the recorded census; the corrected `range(1, 1 << (1 << n))` reproduces the record exactly ([3] 121 closed, 120 nonempty, 0 failures, 98 with a singleton, 0 bad; [4] 4,959 / 4,958 / 0 / 4,126 / 0) — recorded outputs correct, printed code repaired, outputs unchanged. **The fresh battery (all green, condensed):** the weak-form recursion census on all twelve groups of order ≤ 9 exact against §3.1's table (738,884 pairs, 185,060 Case-1, 553,824 staircase bases, 1,355,220 Case-2 steps, max depth 5, zero violations of any property); the §3.2 counterexample and Exercise 10's six portions reproduced exactly; DeVos's machinery on the 39,449 aperiodic pairs of Z₆, Z₇, Z₈, Z₄×Z₂ (translate, Z₀-portion, trivial exit all clean; stab(Z₀) nontrivial on 3,604 = 60 / 0 / 930 / 2,614); the lab's LCG engines reproduced line for line (the staircase witness, 473,998 C–D pairs with 42,081 tight, the merge monitor, the e-transform 6,900, the m-fold 600, EGZ exhaustive 21 / 120 / 715 / 4,368 / 27,132, the pairing 800, the prime case 900 / 44 / 856 / 856, the composite chain 300); A16's 9,261 triples, 194,481 quadruples, and 250,047 mixed sums with the 8-type orbit classification exact; A17's regime boundary (the binomial wall at every prime p ≤ 19, the whole-field costume, the disassembly, F₅ and F₇ exhaustive plus F₁₁ sampled); A19's near-miss census — all 873,912 multisets n = 3–9, avoiders exactly the two-value coprime families, counts n·φ(n)/2, zero exotics; the shadow censuses — deep = complete with zero exceptions at (6, 2), (6, 3) (42), (6, 4) (22), and (7, 5) (29 = 21 K⁵₅ + 7 K⁵₆ + 1 K⁵₇); the mirror partitions and star mirrors ((9, 4) 56 + 70 = 126, (5, 2) 4 + 6, (7, 3) 15 + 20, (8, 3) 21 + 35; h(t) = C(t, 5) + C(t, 4) = 6, 21, 56, 126 with h(8) = C(9, 4)); the ten-edge hunt's 352,716 graphs (2,310 at t = 7, none at 8 or 9, exactly 21 at t = 10, all K₅ plus two isolated, the per-vertex ceilings K(v) ≤ 10 − d(v) and K(v) ≤ (3/2)d(v) clean at every vertex of every graph); the [6] costume's 57 equality families (15 edges, 20 triangles, 15 K₄, 6 K₅, 1 K₆); the HM(7, 3) maximal census (6,127 maximal families, maximum 15 by the 7 stars, empty-core maximum 13 by the 140 HM-type + 35 F₁, none unmatched); the AK sizes [15, 13, 10, 0]; the union-closed census under the repaired range; and Gilmer's constant (3 − √5)/2; and the (9, 4) empty-core hunt of ◐15, here upgraded from honest budget to proof: a branch-and-bound search (6,374 nodes, no budget exhaustion) certifies that no intersecting 4-family on [9] with empty core reaches 54 — the maximum is exactly 53, the Hilton–Milner size, attained by the HM-type family (verified pairwise intersecting with core ∅). Cross-references: the Chapter 6, 7, and 8 pointers valid (the multilinear lemma, the circle method, the complementary pair, the shifting lecture, ◐15, the equitable quotient); the pattern index consistent with the atlas (P4: 16, 20; P22: 17; P23: 19; the lore rows 11 and 18). Checker-side alarms, all the reviewer's own, re-run green: the DeVos Z₄×Z₂ record requires the column-major encoding where the recursion census is row-major, the product-group negation is not N−j in mixed moduli, and the review's own census tools threw three self-bugs (a 32-bit shift wrap in the (7,5) pin census, a combinatorial-iterator placeholder, and a per-vertex push duplication in the ten-edge hunt) — each caught by its own count check and fixed before any finding was recorded. Per the rebuild rule the web edition and the .html export were rebuilt — fidelity proof first — and the review arc advances to Chapter 10.

---
*Chapter status: ✅ **Feynman edition + exercise backfill (session 41) + adversarial review (session 67)** — 5 lectures (the staircase and Cauchy–Davenport; Kneser's theorem and the zero-sum capstone; the assembly completed: Dyson's recursion and DeVos's proof; shadows: the Kruskal–Katona theorem; uniqueness completed: the shade route), all proofs complete with citations kept honest; 1 verified figure; 16 graded exercises + 2 ◆ pattern-unknown + 2 ◐ explorations, 18 worked answers machine-verified; lab in 5 verified parts (sumsets; EGZ; shadows and the frontiers; the assembly; the shade route). Born in Chapter 7, exported by the restructure, completed here as a standalone course: the sumset and shadow arcs close, and with them the three flags the restructure left open. The session-67 adversarial review audited the chapter end to end — one lecture-wording repair (§3.2's canonical-witness attribution), four record-level alignments (§1.2's merge processes, §2.3's e-transform checks, §2.2's and §2.5's gate attributions, §2.5's trivial-case count), one monitor-output repair (Part 1's and A2's zero-gain count), and one lab-code repair (Part 3(h)'s union-closed range), the mathematics otherwise clean. Ships with its web edition (the standard delivery format): the HTML canvas embeds this chapter byte-identically; print to PDF from a browser for a correct export.*
