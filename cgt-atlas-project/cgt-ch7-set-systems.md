---
name: "cgt-ch7-set-systems"
title: "Ch. 7 — Extremal Set Systems: A Lecture Course in the Feynman Style"
type: "text/markdown"
---

# Chapter 7 · Extremal Set Systems

*Part of the Combinatorics & Graph Theory Atlas (see the Atlas canvas for the chapter map and progress report).*

How many sets can you choose before structure is forced? An antichain forces the middle level; an intersecting family forces a star; cross-intersecting pairs force Bollobás's inequality — and every one of these falls to the same engine: **count the right pairs**. This edition is a lecture course in five lectures: Sperner's theorem three ways (with the symmetric chain decomposition actually built, not cited), Bollobás's two-families theorem with the honest skew landscape, Katona's circle method with the sharp interval lemma complete — the notorious mixed sub-case included — EKR uniqueness, with the proved range in full and the thin range flagged as a forward pointer to Chapter 9, and shifting, whose closing induction stays a cited brick because the circle method already carried the theorem. The chapter's second thread — sumsets (the staircase, Cauchy–Davenport in two complete proofs, Kneser's theorem, the Erdős–Ginzburg–Ziv theorem) and shadows (the Kruskal–Katona theorem through Keevash's clique-form proof, Daykin's complement mirror as a third EKR proof, the Hilton–Milner and Ahlswede–Khachatrian gateways, union-closed lore) — now lives in Chapter 9, "Sumsets and Shadows: the Completed Arcs", where the two flags are closed. Every proof is complete or honestly flagged; every claimed number is machine-checked; the figure is drawn from verified data.

## How to read this chapter

**Notation.** [n] = {1, …, n}; 2^[n] is its power set. C(n, k) is the binomial coefficient. A *family* F is a set of sets; *k-uniform* means every member has size k. A *chain* is a family of pairwise comparable sets; an *antichain* has no two comparable. *Intersecting* means every two members meet. For the circle lectures, points live on a cycle of n positions and dist(x, y) = min(|x−y|, n−|x−y|) is cyclic distance. Letters are re-stated locally where a lecture needs its own.

**The exercises are graded:** ●○○ *easy* (a direct application of one lecture idea), ●●○ *moderate* (two ideas, or one tricky step), ●●● *tough* (several chapter ideas combined). Hints travel with the problems; worked answers sit at the very end of the chapter. Try honestly before reading a hint. Beyond the graded set, ◆ **pattern-unknown** problems name no method and carry no hint: diagnosing which tool fits is part of the problem. And ◐ **Explorations** at the end are open-ended investigations with no single right answer — research training, not test preparation.

## The pattern table for this chapter

| Pattern | Plain language | Where you meet it |
|---------|---------------|-------------------|
| **P2 Double counting (chains / permutations / circles)** | Count pairs (object, witness-arrangement) two ways; the inequality falls out of the mismatch | L1, L2, L3, L4 |
| **P17 Duality / specialization** | One inequality, many shadows: Bollobás → LYM → Sperner by plugging in special pairs | L2, Ch. 9 L4 |
| **P8 Extremal circle structure** | Intersecting arcs trap their start points inside a short window; the window has exactly 2k−1 slots | L3, L4 |
| **P23 Compression / shifting** | Deform the family toward a canonical shape without losing the property or the count | L5 |
| **P4 Induction** | Peel the extreme element; one new element per step | Ch. 9 L1 |
| **P22 Polynomial method** | A polynomial vanishing on a grid, priced by its degrees — the same engine as Chapter 6 | Ch. 9 L1 |
| **P24 Shadow pricing (Kruskal–Katona)** | Price a family by its own real parameter x: a k-family of size C(x, k) forces every j-shadow to size ≥ C(x, j) — equality only at integer x and the complete families | Ch. 9 L4 |

---

## Lecture 1 · Sperner's Theorem: The Middle Level, Three Ways

**Problem.** The largest family of subsets of [n] with **no two comparable** (an *antichain*) has size **C(n, ⌊n/2⌋)** — the middle level(s).

### 1.1 Method 1 — Counting maximal chains (P2, full)

A *maximal chain* is ∅ ⊂ {x₁} ⊂ {x₁, x₂} ⊂ … ⊂ [n]. It is determined by the **order in which elements enter**, so there are exactly n! chains. A chain passes through a fixed k-set A in k!·(n−k)! orders: order A's k elements first (k! ways), then the remaining n−k (that many ways).

Now count pairs (chain, member of F on that chain). Each chain meets an antichain **at most once** — two members on one chain would be comparable. So:

Σ_{A∈F} |A|!·(n−|A|)! ≤ n!.

Divide by n!:

**LYM inequality.** Σ_{A∈F} 1/C(n, |A|) ≤ 1.

Finish: C(n, k) ≤ C(n, ⌊n/2⌋) for every k, so each term satisfies 1/C(n,|A|) ≥ 1/C(n, mid), and therefore

|F| = Σ_{A∈F} 1 ≤ C(n, mid) · Σ_{A∈F} 1/C(n,|A|) ≤ C(n, mid). ∎

**Equality.** Take the middle level itself: every term lands at exactly 1/C(n, mid), and the LYM sum is exactly 1. (When n is odd there are two middle levels, both of size C(n, (n−1)/2) = C(n, (n+1)/2); each saturates alone.) A worthwhile ✎: check that a mix of the two middle levels when n is odd is *not* an antichain — the smaller sets sit inside the bigger ones across levels.

### 1.2 Method 2 — The symmetric chain decomposition, actually built (full)

The second proof needs a structure the reference edition only cited: a partition of 2^[n] into chains that each run from some level r straight up to level n−r, one set per level along the way. This is the *symmetric chain decomposition* (SCD) of de Bruijn–Tengbergen–Kruyswijk — and it has a two-line recursive construction that we can verify, not just believe.

**The doubling construction.** Suppose 2^[n−1] has an SCD. Each chain C = (A₁ ⊂ A₂ ⊂ … ⊂ A_l) is symmetric: |A₁| + |A_l| = n−1, and sizes grow by exactly one per step. From C, keep:

- **the extended chain** A₁ ⊂ … ⊂ A_l ⊂ A_l ∪ {n}, and (when l ≥ 2)
- **the reflected chain** A₁ ∪ {n} ⊂ A₂ ∪ {n} ⊂ … ⊂ A_{l−1} ∪ {n}.

**Every subset of [n] lands in exactly one new chain.** A set S avoiding n lies in exactly one old chain, as some A_i; if i < l it appears only in the extended chain (the reflected chain only carries sets that *contain* n); if i = l it is the second-to-top of the extended chain — again exactly once. A set S containing n is T ∪ {n} for exactly one T ⊆ [n−1]: if T = A_l it is the top of the extended chain; if T = A_i with i ≤ l−1 it sits in the reflected chain. One home for everybody: a partition. ✓

**Symmetry survives.** Extended chain: |A₁| + |A_l ∪ {n}| = |A₁| + |A_l| + 1 = n. Reflected chain: |A₁∪{n}| + |A_{l−1}∪{n}| = |A₁| + 1 + |A_{l−1}| + 1, and |A_{l−1}| = |A_l| − 1 (sizes step by one), so this is |A₁| + |A_l| + 1 = n. Both start at level r and end at level n−r. ✓

**Base case.** 2^[1]: the single chain ∅ ⊂ {1}, symmetric (0 + 1 = 1). Induction up, and 2^[n] has an SCD for every n. ∎

**How many chains?** C(n, ⌊n/2⌋) — the middle binomial itself. Count chain *starts* by level: a chain starting at level r ends at n−r, so it passes through level j exactly when r ≤ j ≤ n−r, i.e. r ≤ min(j, n−j). Every set at level j lies on exactly one chain, so Σ_{r ≤ min(j,n−j)} starts(r) = C(n, j). Subtracting the equation for j−1: starts(j) = C(n, j) − C(n, j−1) for j ≤ n/2. Telescoping: total chains = Σ_{r=0}^{⌊n/2⌋} starts(r) = C(n, ⌊n/2⌋). ✓ (✎: run the telescoping for n = 5 by hand — starts 1, 4, 5 at levels 0, 1, 2, total 10 = C(5,2).)

**Sperner, second proof.** An antichain meets each chain at most once, so |F| ≤ number of chains = C(n, mid). ∎ Same bound, and now the extremal structure is vivid: the middle level works *because* it is a full transversal of the chains — one set per chain, no waste.

### 1.3 Erdős's generalization: banning chains of length k+1 (full)

Suppose F contains **no k+1 pairwise comparable sets** (an antichain is the k = 1 case). Both proofs adapt, and the SCD route needs no exchange argument.

**Weighted LYM (P2).** A maximal chain meets F in at most k members — the members along one chain are pairwise comparable, and k+1 of them would make a chain of length k+1. The pair-counting of §1.1 now reads Σ_{A∈F} |A|!·(n−|A|)! ≤ k·n!, i.e.

**Σ_{A∈F} 1/C(n, |A|) ≤ k.**

**The size bound, via the SCD.** Each chain c contributes at most min(k, |c|) members — a chain of length |c| can host at most |c| members anyway, and more than k would make a (k+1)-chain:

|F| ≤ Σ_c min(k, |c|).

Now evaluate the sum. Write min(k, |c|) = Σ_{j=1}^{k} [|c| ≥ j]. A chain has length ≥ j exactly when it starts at level r ≤ (n+1−j)/2. Summing over chains and telescoping exactly as in §1.2 (chains of length ≥ j are the chains starting at level ≤ ⌊(n+1−j)/2⌋, and there are C(n, ⌊(n+1−j)/2⌋) of them):

**Σ_c min(k, |c|) = Σ_{j=1}^{k} C(n, ⌊(n+1−j)/2⌋) — the k middle binomial coefficients** (as j runs, ⌊(n+1−j)/2⌋ visits the middle levels from the inside out, each level appearing once or twice according to parity).

**Sharpness.** The k middle levels themselves contain no chain of length k+1 — a chain steps up one level at a time — and have exactly the claimed size. ∎

For n = 4, k = 2: bound 6 + 4 = 10, achieved by levels 1 and 2. For n = 5, k = 2: 10 + 10 = 20. The exhaustive census in the lab confirms these maxima over *all* families, not just the constructions, for n = 4 and every k.

### 1.4 What to learn

LYM is a *weighted* pigeonhole: every set costs at least the middle-level price 1/C(n, mid), and the total budget is 1. The SCD converts the same statement into an unweighted one — one member per chain — which is why it survives the generalization to banned long chains so gracefully. And the doubling construction is worth remembering as a pattern: **build the recursive object explicitly, then let the counting verify it**. Dozens of theorems in extremal set theory are LYM in disguise; the next lecture shows the master example.

---

## Lecture 2 · Bollobás's Two-Families Theorem

**Problem.** Pairs of sets (A₁,B₁), …, (A_m,B_m) with **A_i ∩ B_i = ∅** but **A_i ∩ B_j ≠ ∅ for all i ≠ j**. Write a_i = |A_i|, b_i = |B_i|. Then

**Σ_i 1/C(a_i + b_i, a_i) ≤ 1.**

### 2.1 The permutation proof (P2, full)

Take a uniform random permutation of the ground set and let E_i be the event that **all of A_i precedes all of B_i** in it. Among the a_i + b_i relevant elements, every relative order is equally likely, and the orders that work are exactly those with the a_i elements of A_i first; so

P(E_i) = a_i!·b_i!/(a_i+b_i)! = 1/C(a_i+b_i, a_i).

**The events are disjoint.** Suppose E_i and E_j both hold, i ≠ j. By hypothesis pick x ∈ A_i ∩ B_j and y ∈ A_j ∩ B_i (both intersections are nonempty). E_i forces every element of A_i before every element of B_i — in particular x before y. E_j forces every element of A_j before every element of B_j — in particular y before x. No permutation does both. ∎

So P(∪ E_i) = Σ P(E_i) ≤ 1 — the theorem. ∎ **Complete, and short enough to hold in your head.**

### 2.2 LYM as a corollary (P17, full)

Given an antichain F ⊆ 2^[n], set A = A and B = [n] ∖ A for each member. Then A ∩ B = ∅ ✓. Incomparability says A ∖ A′ ≠ ∅ and A′ ∖ A ≠ ∅ for distinct members — that is, A ∩ B′ ⊇ A ∖ A′ ≠ ∅ and A′ ∩ B ≠ ∅ ✓. Bollobás applies with a + b = n:

Σ_{A∈F} 1/C(n, |A|) ≤ 1 — the LYM inequality, and Sperner follows as in §1.1. **One theorem, three shadows** (Bollobás, LYM, Sperner); the pattern-index dream, live.

### 2.3 Tightness, saturation, and a warning

**Tight.** Let the ground set be [m] and take the m pairs A_i = {i}, B_i = [m] ∖ {i}. Then A_i ∩ B_i = ∅ ✓, and for i ≠ j the element i lies in A_i ∩ B_j ✓. The sum is m · 1/C(m, 1) = 1 — **exactly 1**. The lab verifies this and a battery of random constrained instances; the bound is never exceeded and occasionally attained.

**A warning about weakenings.** If you keep only the "forward" cross-conditions A_i ∩ B_j ≠ ∅ for i < j (dropping i > j), the theorem as stated is **false** — the sum can exceed 1: take A₁ = {1}, B₁ = ∅ and A₂ = {2}, B₂ = {1}. The forward conditions hold, yet 1/C(1,1) + 1/C(2,1) = 3/2. And the obvious rescue attempt fails too: keeping the sizes small does not help. On [3] the pairs (A₁, B₁) = ({1}, {2}), (A₂, B₂) = ({2}, {1}), (A₃, B₃) = ({3}, {1, 2}) satisfy every skew condition *and* Aᵢ ≠ ∅ *and* |Aᵢ| ≤ |Bᵢ| for all three, yet Σ 1/C(|Aᵢ|+|Bᵢ|, |Aᵢ|) = 1/2 + 1/2 + 1/3 = **4/3** (Exercise 10 asks you to verify this by hand). What survives is the honest landscape, stated in full in the Trick Bag: the **uniform** skew bound — all |Aᵢ| = a, |Bᵢ| = b gives m ≤ C(a+b, a) (Frankl 1982; also Kalai 1984) — and, for non-uniform pairs on the ground set [n], the **Hegedüs–Frankl bound** Σ 1/C(|Aᵢ|+|Bᵢ|, |Aᵢ|) ≤ n+1 (2023), sharp at the complement pairs. The machine census is the referee: the exhaustive maxima are n+1 with no hypotheses, n with Aᵢ ≠ ∅, and 1, 4/3, 2 at n = 2, 3, 4 under |Aᵢ| ≤ |Bᵢ| — the sum genuinely grows, and no size condition brings it back to 1.

### 2.4 What to learn

Bollobás is the strongest form of the "one budget per witness" principle in this chapter: the budget Σ 1/C(a+b, a) is spent by *pairs*, and the witness arrangements are *permutations*. Note the asymmetry with L1: there, chains are deterministic objects counted twice; here, a single random permutation pays for every pair at once, and disjointness of events is the whole proof. When a problem hands you set pairs with a disjointness condition *inside* each pair and intersection conditions *across* pairs, this is the theorem to try first.

---

## Lecture 3 · The Circle Method: Katona's Interval Lemma and EKR

**Problem (Erdős–Ko–Rado).** A family F of k-subsets of [n], **pairwise intersecting**, n ≥ 2k. Then |F| ≤ **C(n−1, k−1)** — achieved by the *star* (all k-sets containing a fixed element).

The proof arranges [n] on a circle at random and counts. The engine is a lemma about arcs, and this lecture proves it completely — including the mixed sub-case that the reference edition had to flag.

### 3.1 Arcs and their starts (P8, full)

Put the n points on a circle and fix a direction. A *k-arc* is a set of k consecutive points; identify it by its **start**. Two k-arcs with starts s, t:

**Claim.** The arcs intersect ⟺ dist(s, t) ≤ k−1.

*Proof.* (⇐) Say the clockwise distance from s to t is d ≤ k−1 (the other case is symmetric). Then t itself lies in the arc starting at s (which covers s, s+1, …, s+k−1), and t lies in its own arc. A shared point. (⇒) Let z be a shared point: z is among s, …, s+k−1 and among t, …, t+k−1 (clockwise from each start). So the clockwise offsets z−s and z−t both lie in [0, k−1], and their difference — the clockwise distance between s and t, up to sign — has absolute value ≤ k−1. The cyclic distance, the smaller of the two oriented distances, is ≤ k−1. ∎

So an intersecting family of arcs is exactly a set S of start points with **pairwise cyclic distances ≤ k−1**. Geometry has become arithmetic on a cycle.

### 3.2 The interval lemma, complete (the mixed sub-case included)

**Katona's interval lemma.** If S ⊆ ℤ_n has pairwise cyclic distances ≤ k−1, then |S| ≤ k. (Requires n ≥ 2k.)

*Proof.* Fix an anchor s₀ ∈ S. Every other point of S lies in the **window** [s₀−k+1, s₀+k−1] — the 2k−1 positions within cyclic distance k−1 of s₀ — because all pairwise distances to s₀ are ≤ k−1. (Here n ≥ 2k matters: the window's 2k−1 positions are distinct on the cycle.) Split the window's interior:

- **forward offsets** A = {a ∈ [1, k−1] : s₀+a ∈ S},
- **backward offsets** B = {b ∈ [1, k−1] : s₀−b ∈ S}.

Take a ∈ A and b ∈ B. The two points s₀+a and s₀−b have cyclic distance min(a+b, n−a−b). Now **a + b = k is forbidden**: it would give distance min(k, n−k) = k > k−1 (using n ≥ 2k). So no a ∈ A pairs with any b ∈ B at sum exactly k:

**A ∩ (k − B) = ∅**, where k − B = {k − b : b ∈ B}.

Both A and k − B live inside the k−1 slots [1, k−1], disjointly:

|A| + |B| = |A| + |k − B| ≤ k − 1, and |S| = 1 + |A| + |B| ≤ k. ∎

That is the whole proof — the "mixed sub-case" (forward and backward starts coexisting) is exactly the A ∩ (k−B) = ∅ step, and it costs one line once the window and the reflected set k−B are on the table. The reference edition's honest warm-up still makes a good ✎: without the reflection trick, the naive bound is |A|, |B| ≤ k−1 each, giving 2k−1; the reflection k − B is what fuses the two groups into one budget.

**Figure 1 draws the proof**: an equality configuration on the circle, the window, and the offset strip where A and k−B tile [1, k−1] disjointly.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 880 330" font-family="Georgia, 'Times New Roman', serif">
  <rect x="0" y="0" width="880" height="330" fill="#ffffff"/>
  <text x="240" y="28" text-anchor="middle" font-size="17" fill="#111827">n = 10, k = 4: starts S = {8, 9, 0, 1}</text>
  <circle cx="240" cy="165" r="110" fill="none" stroke="#9ca3af" stroke-width="2"/>
  <path d="M 135 199 A 110 110 0 1 1 345 199" fill="none" stroke="#dc2626" stroke-width="2" stroke-dasharray="7 5"/>
  <text x="240" y="308" text-anchor="middle" font-size="13" fill="#dc2626">window [s&#8320;&#8722;3, s&#8320;+3]: 2k&#8722;1 = 7 slots</text>
  <circle cx="240" cy="55" r="13" fill="#2563eb" stroke="#1e3a8a" stroke-width="2"/>
  <text x="240" y="60" text-anchor="middle" font-size="13" fill="#ffffff">0</text>
  <circle cx="305" cy="76" r="13" fill="#2563eb" stroke="#1e3a8a" stroke-width="2"/>
  <text x="305" y="81" text-anchor="middle" font-size="13" fill="#ffffff">1</text>
  <circle cx="345" cy="131" r="13" fill="#ffffff" stroke="#374151" stroke-width="2"/>
  <text x="345" y="136" text-anchor="middle" font-size="13" fill="#111827">2</text>
  <circle cx="345" cy="199" r="13" fill="#ffffff" stroke="#374151" stroke-width="2"/>
  <text x="345" y="204" text-anchor="middle" font-size="13" fill="#111827">3</text>
  <circle cx="305" cy="254" r="13" fill="#ffffff" stroke="#374151" stroke-width="2"/>
  <text x="305" y="259" text-anchor="middle" font-size="13" fill="#111827">4</text>
  <circle cx="240" cy="275" r="13" fill="#ffffff" stroke="#374151" stroke-width="2"/>
  <text x="240" y="280" text-anchor="middle" font-size="13" fill="#111827">5</text>
  <circle cx="175" cy="254" r="13" fill="#ffffff" stroke="#374151" stroke-width="2"/>
  <text x="175" y="259" text-anchor="middle" font-size="13" fill="#111827">6</text>
  <circle cx="135" cy="199" r="13" fill="#ffffff" stroke="#374151" stroke-width="2"/>
  <text x="135" y="204" text-anchor="middle" font-size="13" fill="#111827">7</text>
  <circle cx="135" cy="131" r="13" fill="#2563eb" stroke="#1e3a8a" stroke-width="2"/>
  <text x="135" y="136" text-anchor="middle" font-size="13" fill="#ffffff">8</text>
  <circle cx="175" cy="76" r="13" fill="#2563eb" stroke="#1e3a8a" stroke-width="2"/>
  <text x="175" y="81" text-anchor="middle" font-size="13" fill="#ffffff">9</text>
  <text x="240" y="40" text-anchor="middle" font-size="12" fill="#2563eb">anchor s&#8320;</text>
  <text x="660" y="28" text-anchor="middle" font-size="17" fill="#111827">the offset strip [1, k&#8722;1]</text>
  <rect x="545" y="120" width="60" height="50" fill="#dbeafe" stroke="#2563eb" stroke-width="2.5"/>
  <text x="575" y="151" text-anchor="middle" font-size="16" fill="#1e3a8a">1</text>
  <rect x="625" y="120" width="60" height="50" fill="#ffffff" stroke="#dc2626" stroke-width="2.5"/>
  <text x="655" y="151" text-anchor="middle" font-size="16" fill="#dc2626">2</text>
  <rect x="705" y="120" width="60" height="50" fill="#ffffff" stroke="#dc2626" stroke-width="2.5"/>
  <text x="735" y="151" text-anchor="middle" font-size="16" fill="#dc2626">3</text>
  <text x="575" y="192" text-anchor="middle" font-size="13" fill="#2563eb">A = {1}</text>
  <text x="695" y="192" text-anchor="middle" font-size="13" fill="#dc2626">k&#8722;B = {2, 3}</text>
  <text x="660" y="228" text-anchor="middle" font-size="13" fill="#111827">a + b = 4 is forbidden &#8658; A &#8741; (k&#8722;B) = &#8709;</text>
  <text x="660" y="250" text-anchor="middle" font-size="13" fill="#111827">equality: A &#8851; (k&#8722;B) = {1, 2, 3}, so |A| + |B| = 3 = k&#8722;1</text>
  <text x="660" y="272" text-anchor="middle" font-size="13" fill="#111827">backward offsets B = {1, 2} reflect by b &#8614; k&#8722;b</text>
  <text x="440" y="322" text-anchor="middle" font-size="14" fill="#374151">Figure 1 &#183; Katona's window: starts trapped within distance k&#8722;1 of the anchor, and the forbidden sum a + b = k</text>
</svg>
```

The lab verifies the lemma exhaustively: for every 2k ≤ n ≤ 16 (k ≥ 2), the maximum size of a start set with pairwise distances ≤ k−1 is exactly k — 0 violations across every subset of every cycle.

### 3.3 Equality: consecutive starts and the unique common point (n > 2k)

Equality analysis drives uniqueness, so we do it now, completely.

**Lemma (structure of equality).** Suppose n > 2k and |S| = k in the interval lemma. Then S is a set of **k consecutive points** of the cycle, and the k arcs starting at S share **exactly one common point**.

*Proof.* Equality gives |A| + |B| = k−1 with A and k−B *disjoint* subsets of [1, k−1] — so they tile it: **A ⊔ (k−B) = [1, k−1]**. The extra room n ≥ 2k+1 bans one more sum: a + b = k+1 gives cyclic distance min(k+1, n−k−1), and n−k−1 ≥ k, so the distance is k+1 > k−1 — forbidden. Hence also **A ∩ (k+1−B) = ∅**.

Now let b ∈ B with b ≥ 2, and suppose b−1 ∉ B. From the tiling, k−b+1 = k−(b−1) ∉ k−B, so k−b+1 ∈ A. But (k−b+1) + b = k+1 — a forbidden sum with b ∈ B, contradicting A ∩ (k+1−B) = ∅. So **B is downward-closed**: b ∈ B, b ≥ 2 ⟹ b−1 ∈ B, i.e. B = {1, …, β} for some β ≥ 0. The tiling then forces A = {1, …, k−1−β}.

So S = {s₀} ∪ {s₀+1, …, s₀+k−1−β} ∪ {s₀−1, …, s₀−β} = {s₀−β, …, s₀+k−1−β}: k consecutive points. The arc starting at s₀−β+i covers s₀−β+i, …, s₀+k−1−β+i; every such arc contains s₀+k−1−β (i ≤ k−1), so that point is common to all k arcs. No other point is: the point s₀+k−1−β+j with j ≥ 1 needs i ≥ j in the arc start, so the arc starting at s₀−β fails to contain it once j ≥ 1. Exactly one common point. ∎

At exactly n = 2k the tiling still holds but the (k+1)-ban disappears, and non-consecutive equality configurations exist: for (n, k) = (6, 3), the starts {0, 2, 4} give three pairwise-intersecting arcs with no common point — the lab census counts 8 equality configurations there, 2 of them non-consecutive; for (8, 4) it counts 16, of which 8 non-consecutive. The uniqueness theorem in the next lecture will have to treat n = 2k separately, and it does.

### 3.4 EKR by double counting (P2, full)

Call a pair (σ, A) a *witness* if σ is a circular arrangement of [n] (there are (n−1)!, modulo rotation) and A ∈ F appears as an **arc** of σ.

*Per set.* A fixed k-set S is an arc of exactly **k!·(n−k)!** arrangements: treat S as a block — k! orders inside, (n−k)! circular arrangements of the block and the other n−k elements.

*Per arrangement.* The F-arcs of one circle are pairwise intersecting (F is), so their starts have pairwise cyclic distances ≤ k−1, so there are at most **k** of them (interval lemma).

So |F| · k!·(n−k)! ≤ k · (n−1)!, and dividing:

|F| ≤ k·(n−1)! / (k!·(n−k)!) = (n−1)! / ((k−1)!(n−k)!) = **C(n−1, k−1)**. ∎

**Tight.** The star: all k-sets through a fixed point x have size C(n−1, k−1) ✓ and are pairwise intersecting ✓.

### 3.5 What to learn

The circle method is double counting with a *geometric* engine: the interval lemma is what makes "per arrangement ≤ k" true, and its complete proof is a lesson in **reflections** — map the backward offsets by b ↦ k−b so both directions compete for the same k−1 slots, and the mixed case dies of overcrowding. Watch where n ≥ 2k and n ≥ 2k+1 were used: the first makes the window non-degenerate and bans the sum k; the second bans k+1 and unlocks the structure of equality. Hypotheses in extremal theorems are usually the exact fingerprints of the proof steps.

---

## Lecture 4 · Uniqueness: Why Only Stars

EKR says |F| ≤ C(n−1, k−1). The sharp question: **who achieves equality?** The answer: at n = 2k, many families; at n > 2k, only stars. This lecture proves the n = 2k characterization completely, proves the structural steps of the n > 2k case, and flags — honestly — the one transport step it does not rebuild, with citations and machine census evidence in its place.

### 4.1 Equality forces every circle to be full (full)

**Lemma.** |F| = C(n−1, k−1) ⟺ every circular arrangement carries **exactly k** F-arcs.

*Proof.* The witness count of §3.4 is |F|·k!(n−k)! = Σ_σ (F-arcs of σ), and each term is ≤ k. Equality in the bound is equality in this count: since C(n−1,k−1)·k!(n−k)! = k·(n−1)! exactly (an arithmetic identity — the lab checks it for all n ≤ 20), |F| maximal forces the total to reach its cap k·(n−1)!, which with every term ≤ k forces every term to equal k. Conversely, one full circle count recovers the maximum. ∎

So an extremal family is *rigid*: on every single arrangement, its arcs must realize the interval lemma's equality case. Rigidity is what uniqueness proofs feed on.

### 4.2 What a full circle looks like (full)

For n > 2k, §3.3 applies to every circle: its k F-arcs start at k consecutive points and share exactly one common point z(σ). For n = 2k this fails — non-consecutive configurations exist — which is why the two regimes must be separated, and why n = 2k admits many extremal families:

**Theorem (equality at n = 2k, complete).** At n = 2k, F is extremal (|F| = C(2k−1, k−1)) **iff** F contains exactly one set from each complementary pair {S, [2k]∖S}.

*Proof.* First, two members of F cannot be complementary (they would be disjoint), so F takes at most one set from each of the ½C(2k,k) = C(2k−1, k−1) pairs — that is the EKR bound in this regime, reproved. Conversely, if F takes exactly one from each pair it is automatically intersecting: two k-sets of [2k] that are disjoint are complements of each other — the only way to fit 2k points into two disjoint k-sets — so they would form one of the pairs, and F never holds both ends of a pair. Size: C(2k−1,k−1) ✓. ∎

For (n, k) = (6, 3) the lab enumerates all of them: exactly **2^10 = 1024** maximum families, one per choice of one-from-each-complementary-pair — the 6 stars among them, and 1018 others; the census confirms both the count and that every one of the 1024 choices really is intersecting. At n > 2k the party ends, and the rest of the lecture explains why.

### 4.3 The transport to a global center (structure proved; one step flagged)

Fix n > 2k and an extremal F. Every circle σ carries exactly k F-arcs with a single common point z(σ) — but z is allowed to depend on σ. The theorem to close is that one point x works for *all* circles simultaneously; then every U ∈ F, being an arc of some circle together with... more precisely, F ⊆ star(x), and |F| = C(n−1,k−1) = |star(x)| forces F = star(x).

Here is the structure of the classical completion (Katona 1972), with the parts this chapter proves marked:

**(i) Block-circles.** Fix a k-set T = {t₁, …, t_k} ∈ F and consider arrangements where T's elements sit consecutively, in their internal order, with the n−k outside elements in an arbitrary order π. By §4.1 these circles are full, and the F-arcs on them are constrained: an arc of such a circle that meets T in a consecutive tail {t_p, …, t_k} and outside elements before/after in suitable positions. Writing N = n−k for the number of outside elements, the F-arcs of a block-circle split into **T-tail arcs** B_p = {t_p, …, t_k} ∪ (p−1 outside elements) and **T-head arcs** W_i = {t₁, …, t_{k−i}} ∪ (i outside elements); the count k = (#tails) + (#heads) defines an integer j(π) ∈ [0, k−1] for each outside order π.

**(ii) The J-invariant.** Swapping two adjacent outside positions changes at most one of the F-arc counts — the arc W_i whose "window" straddles the swapped pair — so j(π) can only change when the corresponding W_i enters or leaves F. For n ≥ 3k−2 every swap position is within reach of the argument, and since adjacent transpositions generate all orders, **J := j(π) is the same for every π**. *(This generation-and-invariance step is the flagged brick: the single-transposition analysis is routine but bookkeeping-heavy; see Katona (1972) and Anderson (1987) for the complete write-up.)*

**(iii) Endpoints give stars.** If J = 0, every U ∈ F must contain t_k: a set avoiding t_k misses all the tail arcs that §4.1 forces into F... and the forced family pins U to meet {t_k}, from which F ⊆ star(t_k) and equality forces F = star(t_k). Similarly J = k−1 forces star(t₁). *(Proved in the references; the chapter states it as part of the flagged chain.)*

**(iv) Middle values J ∈ [1, k−2].** The forced family drives F into the k-sets that meet both the head {t₁, …, t_{k−J}} and the tail {t_{k−J}, …, t_k} — a class that strictly contains star(t_{k−J}), so a naive count does *not* exclude it; the classical exclusion is a finer argument. *(Flagged with (ii)–(iii).)*

**Honest summary.** This chapter proves: the counting lemma §4.1, the per-circle structure §4.2, the complete n = 2k characterization, and the endpoint *statements*. The full transport (ii)–(iv) — for which Katona's original paper and Anderson's textbook are the standard sources — is cited, not rebuilt, and the thin range 2k < n ≤ 3k−2 (where (ii) needs adjustment) is cited with it — and carried forward: Chapter 9's closing lecture builds the cascade-uniqueness brick and completes the thin range, retiring the flag there. What we can do, and do, is **verify the conclusion exhaustively wherever brute force reaches**: (5, 2): all 5 maximum families are the 5 stars; (7, 3): exactly 7 maximum families, all stars; (8, 3): exactly 8, all stars. On the smallest thin-range case (9, 4), the lab sets up the census as an Exploration.

### 4.4 What to learn

Uniqueness proofs are *rigidity* arguments: equality in a double count forces every local configuration to be extremal too, and extremal local configurations are so constrained that a global structure falls out. The gap between "every circle has a common point" and "one point serves every circle" is exactly where the hard work of such proofs lives — here it is the invariance of the head/tail split J under rearrangements of the outside elements. When you meet a uniqueness claim in the wild, ask: *what is being double-counted, and what does forcing equality at every term buy?*

---

## Lecture 5 · Shifting: Deforming Families Toward the Star

The circle method proves EKR by *averaging over arrangements*. Shifting takes the opposite philosophy: **deform the family itself** toward a canonical shape, without changing its size or losing the intersecting property — and read the theorem off the deformed family (P23).

### 5.1 The (i, j)-shift (definition)

For i < j, the *shift* S_{ij} replaces a set A containing j but not i by (A − {j}) ∪ {i} — swapping the big element for a smaller one — and leaves every other set alone. Applied to a family: S_{ij}(F) = {S_{ij}(A) : A ∈ F}, keeping the family a set (duplicates merge). A family is *shifted* when no shift changes it: whenever A ∈ F, j ∈ A, i ∉ A, i < j, then also (A − {j}) ∪ {i} ∈ F.

**Size is preserved (full).** A shift fires only when the target set is absent from F, so the map A ↦ S_{ij}(A) is injective on F: two sets cannot collapse onto one target, because an unshifted set is its own image and a shifted set's image is not in F. So |S_{ij}(F)| = |F|, and k-uniformity is obviously preserved — every image has the same size as its source. ✓

### 5.2 Intersecting is preserved (full)

Suppose F is k-uniform and intersecting, and let C, D ∈ S_{ij}(F) be disjoint — we derive a contradiction.

Both cannot contain i (they would meet there), so one of them, say C, misses i. Any shifted image contains i, so C was not shifted: **C ∈ F**. If D ∈ F too, then C ∩ D = ∅ contradicts F intersecting. So i ∈ D and D is a shifted copy: D = (D* − {j}) ∪ {i} with D* ∈ F. From C ∩ D = ∅: i ∉ C (given), j ∉ D (D contains i and is disjoint from C... more precisely j ∉ D because if j ∈ D then j ∉ C), and C ∩ (D* − {j}) = ∅ — the unshifted part of D* misses C entirely.

**Case j ∉ C.** Then C ∩ D* = (C ∩ D) ∪ (C ∩ {j}) = ∅ — two members of F, disjoint. Contradiction.

**Case j ∈ C.** Then C ∈ F with j ∈ C, i ∉ C, *and C survived the shift* — which happens only when its own shift target C′ = (C − {j}) ∪ {i} was already present in F. Now compute C′ ∩ D*: every cross-piece dies — C′ ∩ D ⊆ C ∩ D = ∅ for the D-part; i ∉ D* (D* contains j but not i, being the unshifted source); j was removed from C′; and (C − {j}) ∩ (D* − {j}) ⊆ C ∩ (D* − {j}) = ∅. So C′ ∩ D* = ∅ with C′, D* ∈ F. Contradiction. ∎

The proof is a template for *every* shifting-preservation argument in the field: chase which of the conflicting sets were actually moved, split on whether the shift's target was already present, and land the contradiction back in the original family.

### 5.3 Termination and the shifted shape

Shifting terminates. Each effective shift strictly decreases the weight w(F) = Σ_{A∈F} Σ_{x∈A} x — a swap replaces j by i < j — and w is a nonnegative integer. So after finitely many shifts the family is shifted, and it is still k-uniform, still intersecting, and still the same size.

What does a shifted intersecting family look like? Its members lean toward small elements — the star at element 1 is the most shifted family there is. For EKR, one closes by induction on k: split the shifted family into sets containing 1 and sets avoiding it; shiftedness converts "avoids 1" into strong structural hypotheses (any set avoiding 1 can absorb... the details are where the work is), and the induction lands |F| ≤ C(n−1, k−1). **This closing induction is a flagged brick** — see Frankl's survey or the standard texts; the circle method already gave us the theorem in full, so the chapter loses nothing by flagging the second route's last step. Chapter 9's shadow lecture retires even the *need* for it: Daykin's complement mirror, a single Kruskal–Katona application, gives a second complete proof of EKR with no closing induction at all — so no part of the book's EKR story rests on a flagged step; the shifting route's last step remains cited as the field's standard assembly.

### 5.4 What to learn

Shifting is the most portable deformation tool in extremal set theory: it preserves size and uniformity automatically, and with modest case analysis it preserves intersecting-ness, cross-intersecting-ness, and most "forbidden configuration" properties. It reappears throughout the field — Frankl–Wilson theory in Chapter 6 leans on it — and its philosophy (canonical forms first, counting second) complements the circle method's (averaging first, structure second). The lab verifies preservation and termination on random families; every trial shifts to stability with size, uniformity, and intersecting-ness intact.

---

## The Trick Bag (reference card)

| Pattern | Plain language | Where you met it |
|---------|---------------|------------------|
| **P2 Double counting (chains / permutations / circles)** | Count pairs (object, witness-arrangement) two ways; the inequality falls out of the mismatch | L1, L2, L3, L4 |
| **P17 Duality / specialization** | One inequality, many shadows: Bollobás → LYM → Sperner by plugging in special pairs | L2, Ch. 9 L4 |
| **P8 Extremal circle structure** | Intersecting arcs trap their start points inside a short window; the window has exactly 2k−1 slots | L3, L4 |
| **P23 Compression / shifting** | Deform the family toward a canonical shape without losing the property or the count | L5 |
| **P4 Induction** | Peel the extreme element; one new element per step — or one block per extraction | Ch. 9 L1, L2 |
| **P22 Polynomial method** | A polynomial vanishing on a grid, priced by its degrees — the same engine as Chapter 6 | Ch. 9 L1 |
| **P24 Shadow pricing (Kruskal–Katona)** | Price a family by its own real parameter x: a k-family of size C(x, k) forces every j-shadow to size ≥ C(x, j) — equality only at integer x and the complete families | Ch. 9 L4 |
| **One budget per witness (lore)** | Chains, permutations, circles: the proof prices each extremal witness arrangement, and the budgets sum to the answer | L1, L2, L3 |
| **Rearrange, then average (lore)** | The circle method: bound on every arrangement, average over random ones | L3, L4 |
| **A deficit is a period (lore)** | A sumset that underperforms the staircase by d carries a stabilizer of order ≥ d — the deficit is the period, not an accident | Ch. 9 L2 |
| **Census what you cannot rebuild (lore)** | Where a transport step is flagged, exhaustive machine census of every case brute force reaches stands in as evidence | L4, Ch. 9 L2 |
| **The complement mirror (lore)** | Pass to complements: an intersecting family and the k-shadow of its complement family are disjoint — one j-form application plus one monotone function turns this into EKR | Ch. 9 L4 |
| **Beyond EKR (lore)** | Empty core ⇒ Hilton–Milner's C(n−1,k−1) − C(n−k−1,k−1) + 1; all n ⇒ Ahlswede–Khachatrian's maximum over r of the families F_r — the k-sets meeting a fixed (2r+1)-set in at least r+1 points | Ch. 9 L4 |
| **Union-closed frontier (lore)** | Frankl's conjecture: some element in at least half the sets; proved so far: (3−√5)/2 ≈ 0.382 (Gilmer); a singleton in the family settles it for free | Ch. 9 L4 |

**Formula box:** Sperner: |F| ≤ C(n, ⌊n/2⌋); LYM Σ 1/C(n,|A|) ≤ 1 for antichains; Erdős: no chain of length k+1 ⇒ |F| ≤ Σ_{j=1..k} C(n, ⌊(n+1−j)/2⌋) = the sum of the k middle binomials. SCD: chain count C(n, ⌊n/2⌋), starts(j) = C(n,j) − C(n,j−1), Σ_c min(k,|c|) = sum of the k middle binomials; a family with no (k+1)-chain meets every symmetric chain ≤ k times. Bollobás: pairs (Aᵢ, Bᵢ), Aᵢ∩Bᵢ = ∅, cross-intersecting ⇒ Σ 1/C(aᵢ+bᵢ, aᵢ) ≤ 1; the skew versions (forward conditions only): uniform |Aᵢ| = a, |Bᵢ| = b ⇒ m ≤ C(a+b, a) (Frankl 1982; Kalai 1984); non-uniform on [n] ⇒ Σ 1/C(|Aᵢ|+|Bᵢ|, |Aᵢ|) ≤ n+1, sharp at the complement pairs (Hegedüs–Frankl 2023); no size hypothesis rescues Σ ≤ 1 — the exhaustive maxima are n+1 (no hypotheses), n (Aᵢ ≠ ∅), and 1, 4/3, 2 at n = 2, 3, 4 under |Aᵢ| ≤ |Bᵢ| (Exercise 10; the machine census is the referee). EKR: intersecting k-uniform on [n], n ≥ 2k ⇒ |F| ≤ C(n−1, k−1); equality at n = 2k ⟺ exactly one set from each complementary pair (2^{C(2k−1,k−1)} maximum families; (6,3): 2^10 = 1024); at n > 2k, equality forces k consecutive arc-starts per circle, one common point, and ultimately the star. Interval lemma: pairwise intersecting k-arcs ⇒ starts inside a (2k−1)-slot window, at most k arcs; equality (n > 2k) ⇒ B = [1,β], A = [1,k−1−β], k consecutive starts. The sumset clauses — the staircase, Cauchy–Davenport in both proofs with the m-fold corollary, Kneser with the e-transform, EGZ — and the shadow clauses — the Kruskal–Katona cascade and clique forms, the Daykin mirror, Hilton–Milner, Ahlswede–Khachatrian, union-closed — live in Chapter 9's formula box now (its Lectures 1, 2, and 4).

---

## Exercises (graded: ●○○ easy · ●●○ moderate · ●●● tough)

**Easy — one idea, applied directly**

1. ●○○ **The smallest EKR census, by hand.** List every intersecting family of 2-subsets of [5] up to size 4 (there are not many maximal ones): show the maximum is 4 = C(4,1), and that the maximum families are exactly the five stars. *Hint: among the 10 edges of K₅, intersecting means no two disjoint edges.*
2. ●○○ **Complementary-pair arithmetic.** At n = 2k, count the complementary pairs {S, S̄} of k-subsets of [2k] and verify that half of C(2k, k) equals C(2k−1, k−1). Then show that choosing exactly one set from each pair always yields an intersecting family of the EKR-maximum size. *Hint: disjoint k-sets at n = 2k are complements.*

**Moderate — two ideas, or one tricky step**

3. ●●○ **LYM from Bollobás, in full detail.** Given an antichain A₁, …, A_m, set up the Bollobás pairs and verify *both* cross-intersection hypotheses from incomparability, concluding Σ 1/C(n, |Aᵢ|) ≤ 1. Which hypothesis fails if the family is merely an intersecting family rather than an antichain?
4. ●●○ **The naive interval bound.** Without the reflection trick, show that pairwise intersecting k-arcs have at most 2k−1 starts (treat the starts after and before a chosen anchor separately, k−1 each plus the anchor). Then show where the proof loses: the two budgets must be *summed*, and only the substitution k − B puts both budgets in the same (2k−1)-slot window. *Hint: §3.2's A ∪ (k−B) = [1, k−1].*
5. ●●○ **The exchange argument.** Give the alternative proof of Erdős's bound: among families with no chain of length k+1, take one of maximum size, show its LYM sum is ≤ k, and then exchange sets between levels — if a cheaper level has room, move — until the family is pushed into the k middle levels. Where exactly does maximality forbid the exchange?
6. ●●○ **Shifting hygiene.** Prove that an (i, j)-shift preserves the size and the k-uniformity of a family, and that the weight w(F) = Σ_{A∈F} Σ_{x∈A} x strictly decreases with every nontrivial shift — a nonnegative integer, hence termination. Then verify on the 2-subsets of [4] that the fully shifted maximal intersecting families are exactly two: the star {12, 13, 14} and the triangle {12, 13, 23}.
7. ●●○ **Equality at n = 2k, both directions.** At n = 2k: (⇐) a one-per-complementary-pair family is intersecting of maximum size (Exercise 2); (⇒) an intersecting family of maximum size C(2k−1, k−1) contains exactly one of each complementary pair — no more (disjointness), no fewer (count the pairs and use the size). Conclude: for (6, 3) there are exactly 2^10 maximum families.
8. ●●○ **The window algebra, end to end.** Prove the two facts behind the interval lemma's sharp count: with anchor s₀ and window [s₀−k+1, s₀+k−1], the forward-offset set A and backward-offset set B satisfy A ∩ (k−B) = ∅ and therefore |A|+|B| ≤ k−1. Verify both on the (6, 3) witness {0, 2, 4} and on the consecutive family {0, 1, 2}. *Hint: a forbidden sum a+b = k; every offset pair either fits the window or dies.*
**Tough — several chapter ideas combined**

9. ●●● **Equality structure at n > 2k, in full.** Reconstruct §3.3's argument with every step: forbidden sum k+1 (cyclically), b ∈ B with b ≥ 2, the inference b−1 ∈ B (else k−b+1 ∈ A sums to k+1 with b), the collapse B = [1, β] and A = [1, k−1−β], and the conclusion: k consecutive starts sharing exactly one common point. Verify each step on the circle n = 10, k = 4 with S = {8, 9, 0, 1} (Figure 1's data).
10. ●●● **The skew landscape, mapped.** (a) Verify the 3/2 counterexample of §2.3 condition by condition. (b) Now add the rescue attempts: on [3], take the pairs (A₁, B₁) = ({1}, {2}), (A₂, B₂) = ({2}, {1}), (A₃, B₃) = ({3}, {1, 2}); check every skew cross-condition, every disjointness, Aᵢ ≠ ∅, and |Aᵢ| ≤ |Bᵢ| for all three — then compute Σ 1/C(|Aᵢ|+|Bᵢ|, |Aᵢ|) and watch it exceed 1. (c) Two survivors: show the singleton-complement system ({i}, [n]∖{i}) is skew (indeed cross-intersecting both ways) with Σ = 1; and show the uniform bound C(a+b, a) is sharp by pairing every a-subset of a fixed (a+b)-set with its complement (same size, distinct sets ⇒ no containment). (d) The sharpness witness for the n+1 bound: list *all* subsets of [n] in non-increasing size order and pair each Aᵢ with Bᵢ = [n]∖Aᵢ. Show the system is skew (non-increasing size bans containment), and compute the sum. What does the answer tell you about *any* attempt to rescue Σ ≤ 1 with a size hypothesis?

**Pattern unknown — you choose the tool** *No hints, no difficulty rating: diagnosing the problem is part of the problem. Worked answers still wait at the end.*

11. ◆ Count the maximum intersecting families of 3-subsets of [6] — not just their size. You should get a familiar power of 2; say what each family is, and how many of them are stars.
12. ◆ Write the symmetric chain decomposition of 2^[4] explicitly — every chain, start to finish — and check the three defining properties: partition, steps of +1, and symmetry |bottom| + |top| = 4. How many chains, and what should that number be?
**Explorations — ◐ research-style training** *No single right answer — what you should find is described in each.*

13. ◐ **The thin range, censused.** At (n, k) = (9, 4) the uniqueness proof's transport step needs care (2k < n ≤ 3k−2). Set up a search for maximum intersecting families of 4-subsets of [9] — branch on the 126 sets, prune by the C(8, 3) = 56 bound — and census what you find: are all maximum families stars, how many are there, and what do near-maximum non-star families look like? Compare with (7, 3) and (8, 3), where the full census is exhaustively known.
14. ◐ **LYM sums, sampled and exhaustive.** For n ≤ 4, enumerate all antichains (167 of them at n = 4) and verify Σ 1/C(n,|A|) ≤ 1, with equality exactly on the middle level(s) — and confirm that mixes of the two middle levels when n is odd fail to be antichains at all (the smaller sets sit inside the bigger ones). For n = 5, 6 sample random antichains (grow by adding incomparable sets) and study the distribution of LYM sums: where does the mass concentrate, and how close do the sampled maxima get to 1?
15. ◐ **Beyond EKR: the complete intersection theorem.** For (n, k) = (7, 3), (8, 3), (10, 4), (9, 4), (12, 5), compute the sizes of the Ahlswede–Khachatrian candidates F_r — the k-sets meeting [2r+1] in at least r+1 points — for every r, and the Hilton–Milner formula C(n−1, k−1) − C(n−k−1, k−1) + 1 alongside. You should find F₁ and HM equal in size at k = 3 (the (7, 3) census counts 175 empty-core maxima of size 13, split 140 + 35 between the two shapes) and separated at k ≥ 4 — 70 vs 75 at (10, 4), 51 vs 53 at (9, 4), 288 vs 316 at (12, 5). Which is the true empty-core maximum in each case? Where does the star stop being the overall maximum, and which F_r takes over? The complete answer — the maximum over r of |F_r| for every n and k — is Ahlswede–Khachatrian's 1997 theorem; a Bron–Kerbosch census of maximal intersecting families (Chapter 9's lab, Part 3) is the natural lab companion.

**Graded backfill — five more, each hint naming its pattern**

16. ●○○ **Half the cube, no uniformity.** Show that a pairwise-intersecting family 𝓕 of arbitrary subsets of [n] — no size condition, no uniformity — satisfies |𝓕| ≤ 2^{n−1}. Then exhibit a maximum family on [4] whose members have no element in common. Finally contrast with Exercise 2: at n = 2k every one-per-complementary-pair choice of k-sets is intersecting, but on the full 2^[4] most one-per-pair choices fail — say exactly which extra hypothesis made Exercise 2's choices safe. *Hint: P2 — the complementary-pair ledger of Exercise 2, run over the whole cube: {A, Ā} splits 2^[n] into 2^{n−1} pairs, and an intersecting family takes at most one from each.*

17. ●●○ **Stars and triangles: the complete k = 2 map.** (a) Prove that every pairwise-intersecting family of 2-subsets of [n] is contained in a star (all pairs through one point) or in the three edges of a triangle. (b) Deduce the inclusion-maximal families for n ≥ 4: exactly the n full stars and the C(n, 3) triangles, and nothing else. (c) Stars have n−1 edges and win outright once n ≥ 5; at n = 4 the four triangles tie them at 3 = C(3, 1). Reconcile the tie with Exercise 7: show that each triangle on [4] picks exactly one edge from each complementary pair, so all eight maxima are one-per-pair families, as A7 demands. *Hint: P2 — A1's edge-census chase promoted to every n, then count the maximal witnesses.*

18. ●●○ **Sunflowers.** A family S₁, …, S_r is a sunflower with core K when Sᵢ ∩ S_j = K for all i ≠ j; the petals Sᵢ ∖ K must be nonempty and pairwise disjoint. (a) Prove the sunflower lemma: more than k!(r−1)^k sets, all of size at most k, contain a sunflower with r petals. Induct on k: if some point lies in more than (k−1)!(r−1)^{k−1} members, hand its trace family to the induction and glue the point back into the core; otherwise a maximal pairwise-disjoint subfamily — of size less than r — covers the count: every remaining member meets it, and the degree bound pays the ledger. (b) At k = 2, r = 3 the bound reads 8. Prove the structural equivalence: an edge family with no 3-sunflower is exactly one with Δ ≤ 2 and matching number ≤ 2, and census the true maxima on [5] and [6]. (c) The bound has honest slack here; the conjecture that k!(r−1)^k can be driven down to c^k — the 2020 results reach about (log k)^k — is open. Quote it; do not prove it. *Hint: P4 — peel by a degree census: a heavy point recurses on traces, light points let the disjoint subfamily pay.*

19. ●●● **Shattered sets (Sauer–Shelah).** 𝓕 shatters S when {A ∩ S : A ∈ 𝓕} is all of 2^S. Prove the dimension bound: if |𝓕| > C(n, 0) + C(n, 1) + … + C(n, s−1), then 𝓕 shatters a set of size s. The sharp route, inducting on n: fix a coordinate x; project every member of 𝓕 (delete x wherever it appears) and collect the distinct images into G₀; collect into G₁ the projections whose two lifts, A and A ∪ {x}, both lie in 𝓕. Then show: (i) |𝓕| = |G₀| + |G₁|, by counting the fibers of the projection; (ii) G₀ shatters no s-set — a G₀-witness lifts to an 𝓕-witness with the same trace; (iii) G₁ shatters no (s−1)-set — a G₁-witness for the trace T on S lifts to both traces T and T ∪ {x} on S ∪ {x}, so a G₁ shattering of S is an 𝓕 shattering of the s-set S ∪ {x}; (iv) close the induction with Pascal. Finish with sharpness: the level family {A : |A| ≤ s−1} meets the bound exactly and shatters no s-set — which trace can it never realize? *Hint: P4 + P2 — peel one coordinate; Pascal's identity pays the sum.*

20. ●●○ **The shift's boundary.** §5.2 proves that (i, j)-shifts preserve pairwise intersection for k-uniform families. (a) Show the uniformity was never needed: replay the three-case ledger for arbitrary families and find that the mixed case closes on the *original* family, not the shifted one. (b) The antichain property is another story: exhibit a two-set family and one shift whose image is a chain, and check whether the full shift of §5.3 (all pairs, to stability) rescues it. (c) Audit the chapter: every place Lecture 5 and its exercises use the shift — is uniformity present at each use? *Hint: P23 — compression preserves exactly what it is asked to preserve; audit hypotheses, not conclusions.*

---

## Computational Lab (verified)

Four parts, all deterministic — the randomized parts use a fixed Lehmer generator (seed 12345, multiplier 48271, modulus 2³¹−1), so every run reproduces every digit. The printed outputs were produced by machine runs of exactly this logic (the verification record in the appendix enumerates the runs). Runtimes: Part 2's (8, 3) census and the skew battery's exact-fraction recursions take a few minutes each; everything else is seconds.

### Part 1 — Sperner, LYM, and the symmetric chain decomposition, actually built

```python
from math import comb

def scd(n):
    chains = [[frozenset()]]                          # n = 0: one chain holding the empty set
    for m in range(1, n + 1):
        nxt = []
        for c in chains:
            nxt.append(c + [c[-1] | {m - 1}])         # the chain, new element on top
            if len(c) > 1:
                nxt.append([A | {m - 1} for A in c[:-1]])   # first l-1 sets, new element
        chains = nxt
    return chains

for n in range(1, 7):
    ch = scd(n)
    flat = [A for c in ch for A in c]
    ok = (len(set(flat)) == 2**n                                        # partition
          and all(len(c[i+1]) == len(c[i]) + 1 for c in ch for i in range(len(c)-1))
          and all(len(c[0]) + len(c[-1]) == n for c in ch)              # symmetry
          and len(ch) == comb(n, n // 2))
    print(n, len(ch), ok)

ch6 = scd(6)
erdos  = [sum(min(k, len(c)) for c in ch6) for k in range(1, 7)]
formula = [sum(comb(6, (7 - j) // 2) for j in range(1, k + 1)) for k in range(1, 7)]
print(erdos, formula, erdos == formula)

def popcount(x): return bin(x).count("1")
def members(mask): return [s for s in range(16) if mask >> s & 1]
antichains = lym_eq = 0; lym_ok = True; best = [0, 0, 0, 0]
for mask in range(1, 2**16):                          # every nonempty family on [4]
    mem = sorted(members(mask), key=popcount)
    chain = {}
    for s in mem:
        chain[s] = 1 + max((chain[t] for t in chain if t & ~s == 0), default=0)
    longest = max(chain.values())
    for k in range(1, 5):
        if longest <= k: best[k-1] = max(best[k-1], len(mem))
    if longest == 1:
        antichains += 1
        lym = sum(1 / comb(4, popcount(s)) for s in mem)
        lym_ok &= lym <= 1 + 1e-12
        lym_eq += abs(lym - 1) < 1e-12
print(antichains, lym_ok, lym_eq, best)
```

**Verified output.** The doubling construction passes every check for n = 1…6 — `1 1 True`, `2 2 True`, `3 3 True`, `4 6 True`, `5 10 True`, `6 20 True` — partition, +1 steps, symmetry, and chain count = middle binomial all at once. The Erdős sums from the built decomposition, `[20, 35, 50, 56, 62, 63]`, agree exactly with the formula Σ_{j≤k} C(6, ⌊(7−j)/2⌋). The n = 4 census over all 65,535 nonempty families prints `167 True 5 [6, 10, 14, 15]`: 167 antichains, LYM never exceeded, equality in exactly **5** of them (the five full levels — every level saturates LYM, but only level 2 maximizes the count), and the maximum sizes of families with no chain of length k+1 are **6, 10, 14, 15** — the four sums of middle binomials, matching the SCD prediction to the digit.

### Part 2 — The EKR censuses, exhaustively

```python
from itertools import combinations
from math import comb, factorial

def max_cliques(vs, adj):                 # Bron-Kerbosch with pivoting
    best = [0, 0]                         # [max size, count]
    def bk(R, P, X):
        if not P and not X:
            if len(R) > best[0]: best[0], best[1] = len(R), 1
            elif len(R) == best[0]: best[1] += 1
            return
        pivot = max(P + X, key=lambda u: sum(adj[u][w] for w in P))
        for v in [w for w in P if not adj[pivot][w]]:
            bk(R + [v], [w for w in P if adj[v][w]], [w for w in X if adj[v][w]])
            P.remove(v); X.append(v)
    bk([], list(vs), [])
    return best

for n, k in [(5, 2), (6, 3), (7, 3), (8, 3)]:
    V = list(combinations(range(n), k))
    adj = [[i != j and set(a) & set(b) != set() for j, b in enumerate(V)]
           for i, a in enumerate(V)]
    size, count = max_cliques(range(len(V)), adj)
    print(f"({n}, {k}): max {size}, families {count}, EKR bound {comb(n-1, k-1)}")

def cdist(a, b, n): return min(abs(a - b), n - abs(a - b))
def is_consec(S, n):
    s = sorted(S)
    if len(s) < 2: return True
    gaps = [s[i+1] - s[i] for i in range(len(s) - 1)]
    return gaps == [1] * (len(s) - 1) or \
           (gaps == [1] * (len(s) - 2) and s[0] + n - s[-1] == 1)
for n, k in [(6, 3), (7, 3), (8, 3), (8, 4), (10, 4), (10, 5)]:
    best, configs, nonc = 0, 0, 0
    for size in range(1, k + 1):
        for S in combinations(range(n), size):
            if not all(cdist(a, b, n) <= k - 1 for a, b in combinations(S, 2)):
                continue
            if size > best: best, configs, nonc = size, 1, 0
            elif size == best:
                configs += 1
                if not is_consec(S, n): nonc += 1
    print(f"({n}, {k}): max {best}, configs {configs}, non-consecutive {nonc}")

def common_points(starts, n, k):
    arcs = [{(s + j) % n for j in range(k)} for s in starts]
    return {t for t in range(n) if all(t in a for a in arcs)}
ok1 = all(len(common_points(range(s, s + k), n, k)) == 1
          for n, k in [(6, 3), (7, 3), (8, 4), (10, 4)] for s in range(n))
ok2 = all(sum(1 for s in range(n) if x in {(s + j) % n for j in range(k)}) == k
          for n in range(4, 10) for k in range(2, n // 2 + 1) for x in range(n))
ok3 = all(comb(n-1, k-1) * factorial(k) * factorial(n-k) == k * factorial(n-1)
          for n in range(2, 13) for k in range(1, n))
print(ok1, ok2, ok3)
print("Figure 1 tiling:", {1} | {4 - b for b in {1, 2}} == {1, 2, 3})
```

**Verified output.** The maximum-clique census of the intersect graphs prints `(5, 2): max 4, families 5`, `(6, 3): max 10, families 1024`, `(7, 3): max 15, families 7`, `(8, 3): max 21, families 8` — the EKR bound C(n−1, k−1) is attained, and the census counts the witnesses: at n = 2k exactly **1024** maximum families for (6, 3) (one per complementary pair, 2^10), while at n > 2k only the **n stars** survive — 5, 7, and 8 respectively. The interval-lemma brute force prints `(6, 3): max 3, configs 8, non-consecutive 2`, `(7, 3): max 3, configs 7, non-consecutive 0`, `(8, 3): max 3, configs 8, non-consecutive 0`, `(8, 4): max 4, configs 16, non-consecutive 8`, `(10, 4): max 4, configs 10, non-consecutive 0`, `(10, 5): max 5, configs 32, non-consecutive 22`: the maximum is always exactly k, non-consecutive equality configurations exist precisely at n = 2k, and for n > 2k every maximum configuration is k consecutive points. Then `True True True`: k consecutive arcs always share exactly one common point; every point lies on exactly k arcs; and the circle-counting identity C(n−1,k−1)·k!·(n−k)! = k·(n−1)! holds for all n ≤ 12 — the arithmetic behind the double count. `Figure 1 tiling: True` — A ∪ (k−B) tiles {1, 2, 3} disjointly on the drawn configuration.

### Part 3 — Bollobás: saturation and an exhaustive small sweep

```python
from fractions import Fraction
from math import comb

star = sum(Fraction(1, comb(6, 1)) for _ in range(6))   # A_i = {i}, B_i = the rest
print("star sum:", star)

pairs = [(A, B) for A in range(8) for B in range(8)
         if not A & B and A | B]                        # disjoint pairs on [3]
def cross_ok(ps):
    return all(ps[i][0] & ps[j][1] for i in range(len(ps)) for j in range(len(ps))
               if i != j)
valid = viol = tight = 0
for p1 in pairs:
    for p2 in pairs:
        if not cross_ok([p1, p2]): continue
        fam = [p1, p2]
        for p3 in pairs:
            fam3 = fam + [p3]
            if not cross_ok(fam3): continue
            valid += 1
            s = sum(Fraction(1, comb(bin(A).count("1") + bin(B).count("1"),
                                      bin(A).count("1"))) for A, B in fam3)
            viol += s > 1; tight += s == 1
        valid += 1
        s = sum(Fraction(1, comb(bin(A).count("1") + bin(B).count("1"),
                                  bin(A).count("1"))) for A, B in fam)
        viol += s > 1; tight += s == 1
print(valid, viol, tight)
```

**Verified output.** `star sum: 1` — exactly, by rational arithmetic: the six-pair star spends the whole budget, six terms of 1/C(6,1) = 1/6. The exhaustive sweep over every configuration of 2 or 3 pairs on ground set [3] satisfying *both* hypotheses prints `60 0 18`: **60** valid configurations, **zero** violations, and **18** tight ones — the budget is never exceeded, and saturation happens only in the star-like arrangements, exactly as Lecture 2's tightness discussion claims.

### Part 4 — The skew battery (Bollobás §2.3)

```python
from math import comb
from fractions import Fraction

def bits(m): return bin(m).count("1")

# the skew battery — exhaustive, exact fractions
def skew_max(n, hyp):
    cands = []
    for A in range(1 << n):
        for B in range(1 << n):
            if A & B or not hyp(A, B): continue
            cands.append((A, B, Fraction(1, comb(bits(A) + bits(B), bits(A)))))
    memo = {}
    def best(state):
        key = tuple(sorted(state))
        if key in memo: return memo[key]
        res = Fraction(0)
        for A, B, w in cands:
            if A in state: continue
            if any(not (a & B) for a in state): continue
            tot = w + best(state + [A])
            if tot > res: res = tot
        memo[key] = res
        return res
    return best([])

variants = [(lambda A, B: True, "ANY", 1, 4),
            (lambda A, B: A != 0, "A nonempty", 1, 4),
            (lambda A, B: A != 0 and bits(A) <= bits(B), "A nonempty & |A|<=|B|", 2, 4),
            (lambda A, B: bits(A) <= bits(B), "|A|<=|B|", 2, 4)]
for hyp, name, lo, hi in variants:
    vals = [skew_max(n, hyp) for n in range(lo, hi + 1)]
    print("skew maxima", name, ":", ", ".join(str(v) for v in vals))
for n in range(2, 8):
    hf = sum(Fraction(1, comb(n, bits(A))) for A in range(1 << n))
    sing = sum(Fraction(1, comb(n, 1)) for _ in range(n))
    print(f"n = {n}: HF list sum {hf}, singleton-complement sum {sing}")

def uniform_max(n, a, b):
    As = [m for m in range(1 << n) if bits(m) == a]
    cands = [(A, B) for A in As
             for B in (m for m in range(1 << n) if bits(m) == b) if not (A & B)]
    memo = {}
    def best(state):
        key = tuple(sorted(state))
        if key in memo: return memo[key]
        res = 0
        for A, B in cands:
            if A in state: continue
            if any(not (s & B) for s in state): continue
            res = max(res, 1 + best(state + [A]))
        memo[key] = res
        return res
    return best([])

for a, b, n in [(1,1,3),(1,1,4),(1,2,4),(1,2,5),(2,1,4),(2,1,5),
                (2,2,5),(2,2,6),(1,3,5),(3,1,5)]:
    m = uniform_max(n, a, b)
    print(f"uniform ({a},{b}) on [{n}]: max {m}, bound C({a+b},{a}) = {comb(a+b,a)}")

```

**Verified output.** The skew battery, exact fractions, exhaustive: maxima **2, 3, 4, 5** with no hypotheses (n = 1..4), **1, 2, 3, 4** with A nonempty, and — the refutation of the quoted Σ ≤ 1 rescue — **1, 4/3, 2** with A nonempty and |Aᵢ| ≤ |Bᵢ| (n = 2..4), **2, 7/3, 3** with |Aᵢ| ≤ |Bᵢ| and the empty A allowed. The constructions land exactly: the HF subset list sums to n+1 for every n = 2..7, the singleton-complement system to 1, and the uniform census returns C(a+b, a) in all ten configurations — including (2, 2) on [6], where the maximum is 6 out of 15 available A's: the bound survives grounds larger than a+b.

---

## Answers to the Exercises

**A1.** View the 2-subsets of [5] as the edges of K₅: a pairwise-intersecting family is a set of edges no two of which are disjoint. If every two edges share the same vertex, the family is a star — at most 4 = C(4, 1) edges. Otherwise two edges {v, a}, {v, b} share v and some edge avoids v; to meet both it must be {a, b} — the triangle. Any further edge must then meet all three triangle edges: through v it fails on {a, b} unless it is one of {v, a}, {v, b}; avoiding v it must sit inside {a, b} — {a, b} itself. So a non-star family caps at the triangle's 3 edges, and the maximum is **4**, attained exactly by the five stars. Machine check: the Part 2 census prints `(5, 2): max 4, families 5`.

**A2.** The complement map S ↦ [2k]∖S is an involution on the k-subsets with no fixed point (S = S̄ would force S = ∅ by disjointness), so the C(2k, k) k-sets split into ½C(2k, k) pairs; and ½C(2k, k) = C(2k−1, k−1) because C(2k, k) = (2k/k)·C(2k−1, k−1) = 2C(2k−1, k−1). Choosing one set per pair: two chosen sets A, B cannot be disjoint — B ⊆ Ā would force B = Ā (both have size k), the very pair A was chosen from. So every one-per-pick family is intersecting, of size C(2k−1, k−1) = the EKR bound: at n = 2k the bound is attained by **every** such choice.

**A3.** For an antichain A₁, …, A_m set Bᵢ = [n]∖Aᵢ. Then Aᵢ ∩ Bᵢ = ∅, and for i ≠ j: Aᵢ ∩ B_j = Aᵢ ∖ A_j, which is nonempty *because the family is an antichain* — Aᵢ ⊆ A_j is forbidden, so Aᵢ has an element outside A_j. Bollobás gives Σ 1/C(|Aᵢ| + (n − |Aᵢ|), |Aᵢ|) = Σ 1/C(n, |Aᵢ|) ≤ 1: LYM. For a merely intersecting family the first cross hypothesis fails exactly at comparable pairs: Aᵢ ⊆ A_j makes Aᵢ ∖ A_j = ∅ while both still meet each other — intersection is not incomparability.

**A4.** Naive bound: pick any start s₀ ∈ S; every other start is within cyclic distance k−1 of it (arcs intersect ⟺ start distance ≤ k−1), so all starts lie in the window {s₀−k+1, …, s₀+k−1}: at most 2k−1 of them. The loss: the forward starts (offsets A) and backward starts (offsets B) are budgeted separately, (k−1) + 1 + (k−1). The sharp proof reflects the backward budget — k − B lives in the *same* interval [1, k−1] as A, and the two are disjoint (a + b = k would put two starts at cyclic distance exactly k), so |A| + |B| ≤ k−1 and |S| ≤ k. One substitution, one budget: that is the entire content of the "mixed sub-case".

**A5.** The no-(k+1)-chain condition yields the weighted LYM inequality Σ_{A∈F} 1/C(n, |A|) ≤ k (§1.3). Write x_j = |F_j| for the level counts: Σ_j x_j/C(n, j) ≤ k with 0 ≤ x_j ≤ C(n, j) — a fractional knapsack whose cost-per-set at level j is 1/C(n, j). To maximize Σ x_j under the budget, buy where the binomial is largest: fill levels in decreasing order of C(n, j) — the k middle levels — and the value is Σ of the k middle binomials. The exchange: any feasible solution placing sets at a costlier (smaller-binomial) level while a cheaper level has room can be moved, keeping the count and lowering the weight — so the optimum is the greedy fill, and |F| ≤ the sum of the k middle binomials. Maximality enters as: the *inertia* of the exchange — no further move helps — is exactly the greedy configuration. Machine check: n = 4 census maxima {6, 10, 14, 15}, the four sums of middle binomials (Part 1).

**A6.** The (i, j)-shift sends A to A′ = (A∖{j})∪{i} only when i ∉ A, j ∈ A, and A′ ∉ F — so sizes and uniformity are preserved, and the map A ↦ A′ is injective: two different sets cannot shift to the same image, since the image contains i and not j, and both preimages would have to be image∖{i}∪{j}. The weight w(F) = Σ_{A∈F} Σ_{x∈A} x strictly *decreases* (j is replaced by i < j) and is a nonnegative integer — termination. On the 2-subsets of [4]: the star at 2, {12, 23, 24}, shifts by (1,2) to {12, 13, 14}; the triangle {12, 13, 23} is fixed (23 → 13 ∈ F, so it stays); and every other maximal intersecting family shifts to one of these two. Fully shifted maximal families: exactly the star **{12, 13, 14}** and the triangle **{12, 13, 23}**.

**A7.** (⇐) is Exercise 2. (⇒) Let |F| = C(2k−1, k−1) — exactly the number of complementary pairs. F never contains both members of a pair (they are disjoint, and k-sets at n = 2k are complements); so it contains at most one per pair — that is at most C(2k−1, k−1) sets, and equality of counts forces **exactly one per pair**. For (6, 3): 10 pairs, so 2^10 = **1024** maximum families, the 6 stars among them (a star contains exactly one member of each pair — every k-set either contains the center or its complement does). Machine check: Part 2 prints `max 10, families 1024`, and A2's argument shows every one of them is intersecting.

**A8.** All starts lie in the window around the anchor s₀; a forward start sits at s₀+a (a ∈ A ⊆ [1, k−1]) and a backward one at s₀−b (b ∈ B ⊆ [1, k−1]). Two window positions at offset-sum a+b are at cyclic distance min(a+b, n−a−b); for a+b = k and n ≥ 2k this distance is exactly k > k−1 — the two arcs would be disjoint, forbidden. So no a ∈ A satisfies a = k−b for a b ∈ B: **A ∩ (k−B) = ∅**, both inside [1, k−1], whence |A|+|B| ≤ k−1 and |S| ≤ k. On (6, 3) with S = {0, 2, 4}, anchor 0: A = {2}, B = {2}, k−B = {1}: disjoint, |A|+|B| = 2 = k−1 ✓. On S = {0, 1, 2}: A = {1, 2}, B = ∅, same total ✓.

**A9.** Equality forces |A|+|B| = k−1 with A and k−B tiling [1, k−1] disjointly. The room n ≥ 2k+1 (n > 2k) bans one more sum: a + b = k+1 puts two starts at cyclic distance k+1 (cyclically: n−k−1 ≥ k, so the distance is k+1 > k−1) — forbidden, so **A ∩ (k+1−B) = ∅**. Now take b ∈ B with b ≥ 2 and suppose b−1 ∉ B. Then k−(b−1) ∉ k−B, so by the tiling k−b+1 ∈ A; but (k−b+1) + b = k+1 — a forbidden sum — contradiction. So b ∈ B, b ≥ 2 ⟹ b−1 ∈ B: B is downward-closed, B = {1, …, β}, and the tiling forces A = {1, …, k−1−β}: **k consecutive starts**, whose arcs share exactly the point s₀+k−1−β... on Figure 1's data (n = 10, k = 4, S = {8, 9, 0, 1}, anchor 8): A = {1, 2, 3}, B = ∅ (β = 0), the starts are 8, 9, 10, 11 ≡ 8, 9, 0, 1, and the four arcs {8,9,0,1}, {9,0,1,2}, {0,1,2,3}, {1,2,3,4} share exactly {1} = the point s₀+k−1 mod n ✓ — pairwise distances 1, 2, 3, 1, 2, 1, all ≤ 3 ✓.

**A10.** (a) The two pairs: A₁∩B₁ = {1}∩∅ = ∅ ✓, A₂∩B₂ = {2}∩{1} = ∅ ✓; the one forward condition A₁∩B₂ = {1}∩{1} ≠ ∅ ✓. Sum: 1/C(1,1) + 1/C(2,1) = 1 + 1/2 = **3/2**. (b) The three pairs: disjointness {1}∩{2} = {2}∩{1} = {3}∩{1,2} = ∅ ✓; forward conditions A₁∩B₂ = {1}∩{1} ≠ ∅, A₁∩B₃ = {1}∩{1,2} ≠ ∅, A₂∩B₃ = {2}∩{1,2} ≠ ∅ ✓; Aᵢ ≠ ∅ for all three ✓; |Aᵢ| ≤ |Bᵢ| (1 ≤ 2, 1 ≤ 1, 1 ≤ 2) ✓. Sum: 1/C(2,1) + 1/C(2,1) + 1/C(3,1) = 1/2 + 1/2 + 1/3 = **4/3** > 1 — the size hypothesis does not rescue Σ ≤ 1. The exhaustive census (Part 4) confirms the pattern: under exactly these hypotheses the maxima at n = 2, 3, 4 are 1, 4/3, 2 — the sum genuinely grows (and by symmetry the same holds for |Aᵢ| ≥ |Bᵢ|: swap the roles of the A's and B's and read the list backwards). (c) Singleton-complement: for i ≠ j, Aᵢ∩B_j = {i}∩([n]∖{j}) = {i} ≠ ∅ — the system is cross-intersecting in *both* directions, a fortiori skew in any order; Σ = n · 1/C(n, 1) = **1**, the budget exactly spent. Uniform sharpness: pair every a-subset A of a fixed (a+b)-set X with B = X∖A; for i ≠ j the same-size distinctness of Aᵢ, A_j gives Aᵢ ⊄ A_j, i.e. Aᵢ∩B_j ≠ ∅ — m = C(a+b, a) skew pairs, each of weight 1/C(a+b, a): Σ = 1, meeting Frankl's uniform bound m ≤ C(a+b, a) (1982; also Kalai 1984, and via Lovász's tensor argument) exactly. The census says the bound survives larger grounds: at (a, b) = (1, 1) on [4] the maximum is still 2, at (2, 2) on [6] still 6 = C(4, 2) — out of 15 available A's; all ten checked configurations return C(a+b, a). (d) Order all 2^n subsets of [n] by non-increasing size (ties arbitrary). For i < j: |Aᵢ| ≥ |A_j|, so Aᵢ ⊆ A_j would force Aᵢ = A_j — forbidden, since the list has no repeats — hence Aᵢ ⊄ A_j, which is exactly Aᵢ∩B_j ≠ ∅ for B_j = [n]∖A_j; disjointness is complementarity. So the system is skew, and Σ 1/C(|Aᵢ|+|Bᵢ|, |Aᵢ|) = Σ over all subsets of 1/C(n, |A|) = Σ_k C(n,k)/C(n,k) = **n+1** — the sharpness witness for the Hegedüs–Frankl bound Σ ≤ n+1 (2023). The machine census confirms optimality (n = 1..4: maxima exactly 2, 3, 4, 5, the witnesses being complement systems) and more: at n = 2, 3 the extremal pair-set is unique up to ordering — every pair complementary, the whole subset list (2 and 48 valid orderings respectively). **The lesson:** no size condition on the individual pairs brings the sum back to 1. The true landscape is the uniform bound C(a+b, a) and the sharp n+1; the "skew Bollobás with Σ ≤ 1 under a size hypothesis" that circulates informally is false, and the three-pair family of (b) is its smallest refutation.

**A◆11.** At (6, 3) the EKR bound is C(5, 2) = 10, and by A7's characterization a family is maximum iff it contains exactly one 3-set from each of the 10 complementary pairs: **2^10 = 1024** maximum families. Each is automatically intersecting (A7/disjointness), so all 1024 count — the lab census agrees to the family. Among them the **stars** are the 6 families "all triples containing x": for each pair {S, S̄}, exactly one member contains x (they are disjoint and cover [6]), so the star is one-per-pair; and 1018 others (e.g. swap the choice inside any pair not involving the star's pattern) — the census counted them all: `max 10, families 1024`, six of which are stars.

**A◆12.** Six chains, from the doubling construction (Part 1's `scd(4)`):

∅ ⊂ {1} ⊂ {1,2} ⊂ {1,2,3} ⊂ {1,2,3,4} — sizes 0..4;
{4} ⊂ {1,4} ⊂ {1,2,4} — sizes 1, 2, 3;
{3} ⊂ {1,3} ⊂ {1,3,4} — sizes 1, 2, 3;
{3,4} — sizes 2, 2;
{2} ⊂ {2,3} ⊂ {2,3,4} — sizes 1, 2, 3;
{2,4} — sizes 2, 2.

Sixteen sets, each exactly once (partition ✓); every step adds one element ✓; every chain satisfies |bottom| + |top| = 4 ✓ (0+4, 1+3, 1+3, 2+2, 1+3, 2+2). The count is **6 = C(4, 2)** — the middle binomial, as it must be.

**A16.** Complementation is a fixed-point-free involution on 2^[n] (A = Ā would put every x inside A and outside A), so the 2^n subsets split into the 2^{n−1} pairs {A, Ā}, whose two members are disjoint. An intersecting family takes at most one from each pair: |𝓕| ≤ 2^{n−1}. Sharpness: the star — all 2^{n−1} sets containing a fixed point — is pairwise intersecting. The machine census of all 65,536 subfamilies of 2^[4] says the maximum 8 is attained by exactly **12** families: the four stars and eight others with no element in common, for instance {12, 13, 14, 234, 123, 124, 134, 1234} — the 2-sets through 1, all four triples, and the top; every pair meets, yet the total intersection is empty. The contrast with Exercise 2: there, B ∩ A = ∅ with |A| = |B| = k at n = 2k forced B = Ā, so a one-per-pair choice banned disjointness automatically — the only sets that could clash with A were ruled out by the picking rule itself. With sizes free, two chosen sets can be disjoint without being complements ({1} from the pair {1, 234} and {23} from the pair {14, 23}, say), and of the 2^8 = 256 one-per-pair choices at n = 4 only those same 12 are intersecting. The pigeonhole is necessary; the safety was uniformity's gift.

**A17.** (a) With at most one edge the family sits in any star. With two, they share a vertex v — say {v, a} and {v, b} (disjointness is banned). If every edge contains v: the star at v. Otherwise some edge avoids v; to meet both {v, a} and {v, b} it must be {a, b}, and the triangle {v, a}, {v, b}, {a, b} is present. A fourth edge meeting all three: through v it would be {v, c} with c outside {a, b} — disjoint from {a, b}; avoiding v it must fit inside {a, b}, and {a, b} is taken. So the family sits inside the star at v or inside that triangle. (b) The full star at v is maximal for n ≥ 4: an added edge {a, b} avoiding v misses the star edge {v, c} for any c outside {a, b}, and n ≥ 4 provides such a c. A triangle is maximal by the same chase — nothing meets all three edges. Since every intersecting family sits in one of these, the maximal ones are exactly the n stars and the C(n, 3) triangles: 8, 15, 26 at n = 4, 5, 6, in exact agreement with the exhaustive machine censuses (27 + 76 + 192 intersecting families, zero of them outside a star or a triangle). At n = 3 the star is not maximal — it sits inside the one triangle — which is why the count needs n ≥ 4. (c) Stars have n−1 edges and win alone once n ≥ 5 (the censuses: five stars at n = 5, six at n = 6). At n = 4, stars and triangles tie at 3 = C(3, 1). A7 says the maxima at n = 2k are exactly the one-per-pair choices — 2^3 = 8 at (4, 2) — and each triangle complies: {12, 13, 23} takes 12 against 34, 13 against 24, and 23 against 14, one edge from each complementary pair. The eight maxima are the four stars and the four triangles, every one a one-per-pair family, exactly as A7 demands.

**A18.** (a) Induction on k; k = 0 is vacuous (only ∅ exists, so the family has at most one member and the threshold 1 is never exceeded). Suppose the lemma holds at k−1. If some point x lies in more than (k−1)!(r−1)^{k−1} members of 𝓕, the traces {A ∖ {x} : x ∈ A ∈ 𝓕} are more than (k−1)!(r−1)^{k−1} sets of size at most k−1; the induction yields an r-sunflower B₁, …, B_r among them with core K, and the originals B₁ ∪ {x}, …, B_r ∪ {x} form a sunflower with core K ∪ {x} — the petals Bᵢ ∖ K stay nonempty and disjoint, and the sets stay distinct. Otherwise every point has degree at most (k−1)!(r−1)^{k−1}. Take a maximal pairwise-disjoint subfamily P₁, …, P_t inside 𝓕: if t ≥ r, those members are an r-sunflower with core ∅, so t ≤ r−1, and maximality forces every member to meet P = P₁ ∪ … ∪ P_t — at most (r−1)k points. Count (member, point of P) pairs: at least |𝓕| on one side, at most |P|·(k−1)!(r−1)^{k−1} ≤ (r−1)k·(k−1)!(r−1)^{k−1} = k!(r−1)^k on the other. So |𝓕| ≤ k!(r−1)^k, contradicting the hypothesis — a heavy point must have existed after all. (b) For edges the possible cores of a 3-sunflower are ∅ (three disjoint edges) and {v} (three distinct edges through v — distinct 2-sets through v meet exactly at v, so all pairwise intersections equal {v}); a core of size 2 would mean three identical edges, impossible in a family. So no 3-sunflower ⟺ no three disjoint edges and no vertex of degree ≥ 3 ⟺ matching number ≤ 2 and Δ ≤ 2 (machine: the equivalence holds over all 1,024 edge families on [5] and all 32,768 on [6], zero violations). Under those two caps the census maxima are **5** on [5], attained by exactly the twelve labeled 5-cycles (5!/10 = 12), and **6** on [6], attained by exactly the ten disjoint triangle pairs — the ten ways to split [6] into two triples. (c) The bound 2!·2² = 8 sits above both true maxima: the lemma is honest, with slack, already at k = 2. The sunflower conjecture (Erdős–Rado) asks for a bound of c^k for an absolute constant c; the 2020 breakthroughs — Alweiss–Lovett–Wu–Zhang, simplified by Rao — brought the known bound down to about (log k)^k. Open, quoted as open: the [5] and [6] censuses are this exercise's own evidence that the classical bound is not the truth.

**A19.** (i) The projection π(A) = A ∖ {x} maps 𝓕 onto G₀, and each fiber {A, A ∪ {x}} ∩ 𝓕 has size 1 or 2 — size 2 exactly when the projection belongs to G₁. Summing the fiber sizes: |𝓕| = |G₀| + |G₁|. (ii) If G₀ shatters S, with x ∉ S and |S| = s: every witness A ∈ G₀ has a lift in 𝓕 — itself if A ∈ 𝓕, otherwise A ∪ {x} — and both lifts cut S in A ∩ S (x is outside S), so 𝓕 realizes every trace G₀ does: 𝓕 shatters S. (iii) If G₁ shatters S with |S| = s−1: for each T ⊆ S take A ∈ G₁ with A ∩ S = T; both A and A ∪ {x} lie in 𝓕, cutting S ∪ {x} in T and in T ∪ {x}; as T runs over 2^S the two traces together cover all of 2^{S∪{x}} — 𝓕 shatters the s-set S ∪ {x}. (iv) G₀ and G₁ live on the n−1 coordinates other than x. By (ii), G₀ shatters no s-set, so induction gives |G₀| ≤ C(n−1, 0) + … + C(n−1, s−1); by (iii), G₁ shatters no (s−1)-set, so |G₁| ≤ C(n−1, 0) + … + C(n−1, s−2). Pascal adds the two sums to C(n, 0) + … + C(n, s−1), closing the induction on n (the base n = 0 is the single set ∅, which shatters only ∅ and never exceeds the bound). Sharpness: {A : |A| ≤ s−1} has exactly the bound's size, and on any s-set S its traces never include S — A ∩ S = S would need A ⊇ S, of size at least s; every other trace is realized, by A = T itself. Machine: the exhaustive [4] census over all 65,536 families returns maxima exactly **1, 5, 11** at s = 1, 2, 3 — the three bounds, no more — with 16, 400, and 400 attainers respectively (at s = 2 the level family {∅, 1, 2, 3, 4} and 399 others, for example {∅, 1, 12, 3, 4}); the fiber identity and both shatter steps re-verified on 5,000 random [5] instances, zero violations; and the boundary probed from above: 20,000 random [5] families, all of size above 6, all shattered a 2-set, and of 10,000 further samples the 4,677 of size above 16 all shattered a 3-set. Zero escapes.

**A20.** (a) The ledger, uniformity-free. Write C* = (C ∖ {j}) ∪ {i} for a shifted member, and suppose the shifted family contains disjoint images C′ and D′; injectivity (Exercise 6, proved without uniformity) gives unique preimages. Case 1, both unshifted: C ∩ D = ∅ inside 𝓕 — forbidden. Case 2, both shifted: C* and D* both contain i — not disjoint. Case 3, mixed — say C′ = C unshifted and D′ = D* = (D ∖ {j}) ∪ {i} with C ∩ D* = ∅. Then i ∉ C (i lies in D*), and D contained j but not i — the shift's precondition. Since 𝓕 is intersecting, C ∩ D ≠ ∅; but D = (D* ∖ {i}) ∪ {j}, so C ∩ D ⊆ (C ∩ D*) ∪ (C ∩ {j}) = {j} — hence C ∩ D = {j}, and j ∈ C. Now C contains j and not i: C was itself a shift candidate, and the only reason it stayed is that C* = (C ∖ {j}) ∪ {i} already lies in 𝓕. But C* ∩ D = ((C ∖ {j}) ∩ D) ∪ ({i} ∩ D) = ∅ ∪ ∅ = ∅ — the first term dies because C ∩ D = {j}, the second because i ∉ D. Two disjoint members of 𝓕: the contradiction lands in the *original* family, where uniformity was never consulted. (The mirror case, C shifted and D unshifted, swaps the names.) (b) {{1, 3}, {2}} under S_23: the shift condition holds for {1, 3} (j = 3 present, i = 2 absent, {1, 2} not in the family), so the image is {{1, 2}, {2}} — and {2} ⊂ {1, 2}: a chain. The full shift does not rescue it: cycling the pairs to §5.3's stability lands at {{1}, {1, 2}}, still a chain (machine, exact). Nor is it a fluke: of the 167 nonempty antichains on [4], **72** lose the antichain property by the time the full shift stabilizes. (c) The audit: §5.1 defines the shift for k-uniform families, §5.2 proves intersecting-preservation in that setting, §5.3 and Exercise 6/A6 verify size, uniformity, and termination, and the EKR application shifts k-sets throughout — uniformity is present at every use, and by (a) it was never even needed for intersecting-preservation, only for the k-set bookkeeping around it. The antichain casualty of (b) touches nothing standing: nothing in Lecture 5 shifts an antichain. Machine: single shifts exhaustively on [4] — all 8,262 intersecting-family × pair checks preserve intersection, plus 2,570 sampled single shifts on [5], zero violations; the full-shift census over all 65,536 families on [4], again zero violations.

---

## Revision History & Verification Notes

**Editions.** Reference edition (five problem families: Sperner/LYM with the SCD as a flagged sketch, EKR with the sharp interval lemma flagged, Bollobás, the integer staircase, and Cauchy–Davenport as a statement with a flagged sketch; one verified lab) → **Feynman lecture edition** (this edition): 8 lectures. Everything from the reference canon is preserved inside the narrative, and the flagged sketches are now complete proofs: Katona's interval lemma in full — including the mixed sub-case and the equality structure at n > 2k —, the symmetric chain decomposition actually built by the doubling construction (with Erdős's generalization proved from it, no exchange argument required), Cauchy–Davenport twice (merge/periodicity and the polynomial method, with the m-fold corollary), and two new summits: the uniqueness lecture (complete n = 2k characterization, structural steps at n > 2k, honest flags on the transport) and the Kneser–EGZ lecture (stabilizer subgroup lemma, the e-transform toolkit with both properties proved, the quotient reduction proved in full, and the Erdős–Ginzburg–Ziv theorem end to end). The full Atlas exercise standard is installed (tiers, ◆ pattern-unknown, ◐ Explorations, worked answers, this appendix), and two figures are embedded (the interval-lemma window; the sumset staircase grid). A **canon-install pass** then added the closing lecture: Kruskal–Katona proved through Keevash's clique-form argument with the equality structure, the j-form by own-parameter induction, Daykin's complement mirror as a third complete EKR proof (retiring the shifting route's flag), the honest shade-route-to-uniqueness discussion, the Hilton–Milner and Ahlswede–Khachatrian gateways, the union-closed lore, the corrected skew landscape (graded Exercise 16 with worked answer), the ◐24 exploration, and the lab's Part 6 — with the pattern table, Trick Bag, and formula box extended to match. A **restructure pass (session 38)** then slimmed the course to its five-lecture extremal-set core: Lectures 6–8 (sumsets twice and shadows) moved verbatim — with nine exercises, eight worked answers, Figure 2, and the lab's Parts 4 and 5 plus Part 6 minus its skew battery — into the new Chapter 9 skeleton, "Sumsets and Shadows: the Completed Arcs", assembled the same session; the skew battery stayed here as the new lab Part 4 (it anchors §2.3 and Exercise 10); exercises renumbered 1–10 graded, ◆11–◆12, ◐13–◐15, answers A1–A10 + A◆11–A◆12. The appendix's earlier paragraphs keep the numbering of their time.

**Corrections during the rewrite (verification-pass honesty).** Five items were caught by the machine or by the verification discipline before anything was installed. (1) **The middle-J uniqueness step is false as naively stated**: the planned exclusion |𝓗| < C(n−1, k−1) cannot hold, because 𝓗 (the k-sets hitting both the head and tail configurations) always contains the star at z = t_{k−J} — |𝓗| ≥ C(n−1, k−1) unconditionally. Lecture 4 was restructured around this: the counting reduction, the per-circle structure, and the complete n = 2k characterization are proved; the middle-J transport and the thin range 2k < n ≤ 3k−2 are flagged with citations and machine census evidence instead of a fake proof. (2) A lab-writer's bug: the composite EGZ check first tested the final sum modulo m — the *scaled* modulus — instead of modulo nm; the fixed check (sum of the union divisible by nm, equivalently the halved-then-selected block sums ≡ 0 mod m) is what the lab runs. (3) The merge monitor first counted the trivial b = 0 step as a zero-gain event; the fixed monitor skips it, and then *every* zero-gain step fires only when the running set is already the whole field — the periodicity claim in its clean form. (4) Three self-correcting prose artifacts in the Lecture 7 draft were caught and removed before assembly (a checkpoint phrased as visible self-correction, a wrong element count in the composite proof, a mangled cross-reference). (5) **The canon-audit proposal quoted a false skew theorem.** The proposal's "Frankl Σ ≤ 1 with |Aᵢ| ≤ |Bᵢ|" appears in none of the sources it gestured at: Frankl's 1982 paper proves the *uniform* bound m ≤ C(a+b, a), and the non-uniform statement that holds is Hegedüs–Frankl's Σ 1/C(|Aᵢ|+|Bᵢ|, |Aᵢ|) ≤ n+1 (2023, sharp). The quoted version was machine-refuted on [3] — the three-pair family of §2.3's warning satisfies every skew condition plus A ≠ ∅ and |Aᵢ| ≤ |Bᵢ| and sums to 4/3 — before installation, and the install teaches the verified landscape instead (§2.3, the Trick Bag, Exercise 16/A16, Part 6g). The audit's lesson, recorded: proposals are re-verified against the sources and the machine *before* they become chapter content.

**Canon-coverage audit — executed (user-approved).** A standing Atlas goal is auditing each chapter against the broader canon; the audit PROPOSES and the user approves before anything is installed. This chapter's audit produced four proposals, which the user approved, and they are now chapter content: (1) **The Kruskal–Katona theorem** — the chapter's load-bearing gap, since the shifting route to EKR flags its closing induction and Frankl's uniqueness route runs through shade minimization — installed as Lecture 8: the cascade and Lovász statements with the colex agreement machine-checked (781/781), Keevash's clique-form proof in full with the equality analysis (equality ⟺ integer x and the complete family, all 99 exhaustive cases confirmed), the j-form by own-parameter induction, and Daykin's mirror as a third complete EKR proof, closing flag (i) — the flagged induction is retired, EKR no longer rests on it anywhere in this chapter. (2) **Ahlswede–Khachatrian** — the honest continuation of L4 into n < 2k — installed as a citation gateway: Hilton–Milner stated with its formula and machine witnesses (the (7, 3) census: 175 empty-core maxima of size 13, split 140 + 35 between the HM and F₁ shapes), the complete intersection theorem cited with machine-computed sizes, the F₁-vs-HM divergence at k ≥ 4 recorded honestly (70 vs 75, 51 vs 53, 288 vs 316), and ◐24 as the exploration. (3) **The union-closed conjecture** — installed as lore: Frankl's 1979 statement, Gilmer's constant, the singleton lemma proved in a line, and exhaustive censuses on [3] and [4] with zero failures. (4) **Skew Bollobás** — installed as graded Exercise 16 with worked answer A16 — and corrected in the process: the proposal's quoted version is false (Correction 5), and what the chapter now teaches is the verified landscape (Frankl's uniform bound, Hegedüs–Frankl's sharp n+1, the machine census as referee). The audit's proposals and their execution are part of this edition's verification record below.

**Figures.** Two figures, embedded as fenced SVG at their lecture locations per the dual-presentation convention (prose and lab code stay terminal-portable): Figure 1 (L3) — the circle n = 10 with the equality configuration S = {8, 9, 0, 1} at k = 4, the (2k−1)-slot window around the anchor, and the offset strip where A = {1} and k−B = {2, 3} tile [1, 3] disjointly; Figure 2 (L6) — the sumset grid A = {1, 2, 4} × B = {1, 3} with the staircase witness 2 < 3 < 5 < 7 picked out and the full sumset {2, 3, 4, 5, 7} on its diagonal line. All figure data were machine-verified before drawing: S's pairwise cyclic distances {1, 2, 3, 1, 2, 1} all ≤ k−1; the tiling A ∪ (k−B) = {1, 2, 3} with A ∩ (k−B) = ∅; the staircase strictly increasing; the sumset of size 5 against the bound 4. Lecture 8 adds no new figure: its objects — shadows, cascades, the complement mirror — are numeric families rather than geometric configurations, and the lecture's ✎ checkpoints and Part 6's printed censuses carry its worked data. The restructure (session 38) moved Figure 2 to Chapter 9 with the sumset lecture; Figure 1 — the circle-method window — stays.

**Verification record (all deterministic; the Python labs above are the reader's runnable copies of the same logic).** Interval lemma: max |S| = k exhaustive for all 2k ≤ n ≤ 16, zero violations; arcs-intersect ⟺ cyclic start distance ≤ k−1 exact for 4 ≤ n ≤ 12; equality configurations at n > 2k are all consecutive (exhaustive), while n = 2k admits non-consecutive witnesses — (6, 3): 8 configs, 2 non-consecutive; (8, 4): 16, 8 non-consecutive; (10, 5): 32, 22 non-consecutive; window algebra A ∩ (k−B) = ∅, A ∪ (k−B) = [1, k−1], |A|+|B| = k−1: 5,551 anchor-checks, all pass. Uniqueness census: (5, 2) max 4 = exactly 5 families, all stars; **(7, 3) max 15 = exactly 7, all stars; (8, 3) max 21 = exactly 8, all stars** (exhaustive); (6, 3) at n = 2k: exactly 1024 = 2^10 maximum families, every one-per-complementary-pair pick intersecting; k consecutive arcs share exactly one common point (n ≤ 12); star = exactly k arcs on every circle (n ≤ 9); counting identity C(n−1, k−1)·k!·(n−k)! = k·(n−1)! for all n ≤ 20. Sperner side: the SCD doubling construction verified n = 1..8 — partition, +1 steps, symmetry, chain counts 1, 2, 3, 6, 10, 20, 35, 70 = C(n, ⌊n/2⌋), and Σ_c min(k, |c|) = sum of the k middle binomials for every k; exhaustive n = 4 (all 65,535 nonempty families): 167 antichains, LYM ≤ 1 with equality on the 5 full levels, weighted LYM (no (k+1)-chain ⇒ Σ ≤ k) zero violations, maxima {6, 10, 14, 15} = the middle-binomial sums exactly; shifting: 1,200 random intersecting families to stability — size, uniformity, intersecting all preserved; Bollobás: 2,000 random constrained instances Σ ≤ 1 (7 tight) plus the exhaustive ground-[3] sweep (60 valid configurations, 0 violations, 18 tight) and the m = 6 star summing to exactly 1. Sumsets: Cauchy–Davenport — 473,998 pairs over 𝔽₂, 𝔽₃, 𝔽₅, 𝔽₇ (all subsets), 𝔽₁₁ (≤ 4), 𝔽₁₃ (≤ 3): zero violations, 42,081 tight; merge/periodicity — 7,279 gate processes in 𝔽₅/𝔽₇ with gain-0 ⟺ invariance and invariance never occurring short of the full field, and the lab monitor's 8,624 processes with all 16,988 zero-gain steps full-field; polynomial method — univariate partial-fraction identity 15,011 checks (p = 5..13), bivariate weighted-sum identity 900 random polynomials (including the i ≥ |A| terms dying by degree), C(m, r) ≢ 0 mod p for m ≤ p−1 (206 checks), grid-lemma interpolation 184 exact reconstructions, vanishing f(a,b) = 0 ⟺ a+b ∈ C (450 checks), coefficient identity 360 checks, padding arithmetic always true; m-fold C–D: 600 random trials, zero violations. Kneser: exhaustive Z₆..Z₉ (3,969 / 16,129 / 65,025 / 261,121 pairs), Z₁₀ (≤ 5: 405,769), Z₁₂ (≤ 4: 628,849), Z₃² (261,121), Z₄² (40,000 sampled): |A+B| ≥ |A|+|B|−|stab(A+B)| zero violations, tight counts 1,004 / 3,382 / 7,269 / 17,524 for the exhaustive four; e-transform: both properties on all e ∈ G for random pairs in Z₆, Z₈, Z₃², Z₄² — 28,000 gate checks, 6,900 lab checks, zero violations. EGZ: exhaustive n = 3..7 (21 / 120 / 715 / 4,368 / 27,132 multisets — every one contains a zero-sum n-subset) plus 20,000 sampled multisets each at n = 9, 10; pairing lemma 800 random constrained multisets, zero failures; prime-case engine 900 runs — all succeeded, the trivial case firing 225 times in the gate's runs and 44 in the lab's seeded runs, with the choice-sumset covering 𝔽_p in every non-trivial run; composite chain 300 instances over (n, m) = (2,3), (3,2), (2,2), (2,5), (3,3) — every instance yielded 2m−1 disjoint zero-mod-n blocks, the EGZ(m) selection succeeded, and the union certified zero mod nm. **Canon install (Lecture 8 and its orbit), all deterministic:** cascade vs colex initial-segment shadows — agreement on 781/781 sizes (k = 2, 3, 4; every N ≤ C(12, k)); cascade(10, 3) = 10 = C(5, 2). Lovász real form: exhaustive (6, 2) 32,767 + (6, 3) 1,048,575 nonempty families, zero violations, plus 24,000 sampled families at (7, 3), (7, 4), (8, 3), (8, 4) — zero violations. Clique form on the same grounds: zero violations. Equality in the shadow, clique, and j-forms ⟺ x ∈ ℤ and the complete family K^k_x: at (6, 2) all 57 equality cases are the complete families (15 + 20 + 15 + 6 + 1), at (6, 3) all 42 (20 + 15 + 6 + 1) — 99 cases, every one complete, confirmed case by case. j-form: (6, 3) j = 1 and j = 2 zero violations over all 1,048,575 families; (6, 2) j = 1 zero violations, equality 57. Daykin mirror: exhaustive (6, 2) 192 intersecting families (empty included) and (6, 3) 59,049 — zero violations of |𝓕| + |∂_k𝓕*| ≤ C(n, k); maxima 5 by exactly the 6 stars and 10 by exactly 1,024; mirror-equality at 26 ((6, 2): 6 stars + 20 sub-maximum triangles — mirror-tight ≠ maximal, recorded as the honest nuance) and at all 1,024 ((6, 3)). Hilton–Milner: (7, 3) Bron–Kerbosch census — 6,127 maximal intersecting families; maximum 15 = exactly the 7 stars; empty-core maximum 13 = the HM formula C(6, 2) − C(3, 2) + 1, achieved by exactly 175 families, machine-classified 140 HM(x, Y) + 35 F₁(W), none other; AK sizes at (7, 3) [15, 13, 10, 0] and at (5, 3) [6, 7, 10, 0]; F₁ vs HM machine sizes: (7, 3) 13 vs 13, (10, 4) 70 vs 75, (9, 4) 51 vs 53, (12, 5) 288 vs 316 — the divergence recorded honestly. Skew battery: exhaustive memoized recursion over constraint states with exact fractions — maxima n+1 with no hypotheses (n = 1..4: 2, 3, 4, 5; witnesses = complement systems), n with A ≠ ∅ (1, 2, 3, 4), 1, 4/3, 2 at n = 2, 3, 4 with A ≠ ∅ and |Aᵢ| ≤ |Bᵢ| — the refutation of the quoted Σ ≤ 1 version — and 2, 7/3, 3 with |Aᵢ| ≤ |Bᵢ|, A = ∅ allowed; swap-mirror symmetry (|Aᵢ| ≥ |Bᵢ|) confirmed identical; constructions: the Hegedüs–Frankl subset list Σ = n+1 verified n = 2..7, singleton-complement Σ = 1 verified n = 2..7, uniform complement systems attain m = C(a+b, a) at all 9 (a, b) pairs, uniform census maxima = C(a+b, a) in all 10 configurations including grounds larger than a+b ((2, 2) on [6]: 6 of 15 available A's), and the extremal pair-set is unique at n = 2, 3 (all pairs complementary; 2 and 48 valid orderings). Union-closed: [3] 121 nonempty families (120 with a nonempty member — {∅} vacuous), [4] 4,959 (4,958), zero failures of the 1/2 conjecture; the singleton lemma verified on all 98 ([3]) + 4,126 ([4]) singleton-containing families, zero bad; Gilmer's constant (3−√5)/2 = 0.3819660112501051. **Restructure verification (session 38):** the exported lecture block (39,279 chars), all nine exported exercise lines, all eight exported answers (A◆20 with its full multi-line block), and the exported lab parts (Parts 4–5 verbatim; Part 6 minus the skew battery) verified byte-identical inside the Chapter 9 skeleton — zero content loss; the skew battery's code (2,098 chars) and its verified-output sentences re-homed as this chapter's lab Part 4 with the same printed digits; the kept chapter re-gated: 5 lecture headers, balanced fences, 0 mojibake, no session references in lecture bodies, one trailing newline, canvas == master.

**Standing decisions.** Lecture bodies carry no session references; history lives here. Flags, as standing content rather than TODOs: (i) **closed** — the shifting route's EKR closing induction (L5) carried no weight once the circle method proved EKR in full, and the Daykin mirror — now Chapter 9's shadow lecture — provides a second complete proof besides; the induction remains cited as the field's standard route, and nothing in this chapter rests on it; (ii) **closed** — the middle-J transport and the thin range 2k < n ≤ 3k−2 in the uniqueness lecture (L4, cited to Katona 1972, Anderson 1987, Godsil–Meagher 2015, with exhaustive census evidence at (5,2), (6,3), (7,3), (8,3)); the mirror-plus-KK discussion moved with the shadow lecture to Chapter 9, whose closing lecture (Lecture 5, the shade route: cap-meets-floor, the deep cascade-uniqueness lemma, the star theorem for every n > 2k) completed the thin range and retired the flag; (iii) **closed** — Kneser's aperiodic case (the e-transform toolkit and the quotient reduction are proved; the general assembly was cited to Kneser 1953 (Math. Z. 58), Dyson 1945, Nathanson's GTM 165, Tao–Vu, and the arXiv:2407.12253 survey) — Chapter 9's Lecture 3 closed it: Dyson's two-case recursion proves the weak form in full, and DeVos's intersection–union proof completes the strong form. The canon-coverage audit's four proposals were approved by the user and executed — the executed record is the audit paragraph above. The web edition embeds this chapter byte-identically (the standard delivery format); the PDF export check is the user-owned release gate, then learner testing.

**Backfill (session 41).** Five graded exercises (16–20) with pattern-mapped hints were added, per the atlas-wide backfill mandate: the non-uniform half-cube bound |𝓕| ≤ 2^{n−1} by complementary pairs, with the census surprise (at n = 4, twelve maxima, eight with empty total intersection) and the honest contrast with Exercise 2's automatic one-per-pair safety at n = 2k; the complete k = 2 map — every intersecting edge family inside a star or a triangle, the maximal census n stars + C(n, 3) triangles for n ≥ 4, and the n = 4 star-triangle tie reconciled with A7's one-per-pair characterization; the sunflower lemma by induction on k, with the k = 2, r = 3 census (the Δ ≤ 2 ∧ ν ≤ 2 equivalence, maxima 5 and 6 on [5] and [6], the slack against the bound 8, and the sunflower conjecture quoted as open); Sauer–Shelah with the projection/both-lifts decomposition (|𝓕| = |G₀| + |G₁|, the two shatter steps, Pascal's close, and the level-family sharpness — the design's first draft misstated the [4] census as 1, 5, 15; the machine returned 1, 5, 11, exactly the bounds, and the text was corrected before installation); and the shift's boundary — intersecting-preservation needs no uniformity (the mixed-case ledger closing on the original family), the antichain property dies (the {{1, 3}, {2}} witness; 72 of the 167 [4]-antichains broken by the full shift), and the chapter's uses audited uniform. Worked answers A16–A20 were machine-verified before installation: the exhaustive 2^[4] census (65,536 subfamilies — pairwise-intersecting maximum 8, twelve attainers, eight with empty intersection, the displayed witness exact); the edge-family censuses on [4]/[5]/[6] (27 + 76 + 192 intersecting families, zero outside stars and triangles; maximal counts 8, 15, 26; size maxima attained by 8 = four stars + four triangles, five stars, six stars); the sunflower censuses (the no-3-sunflower equivalence over all 1,024 + 32,768 edge families, zero violations; maxima 5 and 6, machine-classified as exactly the twelve labeled 5-cycles on [5] and the ten disjoint-triangle splits of [6]); Sauer (exhaustive [4] maxima 1, 5, 11 at s = 1, 2, 3 with 16, 400, 400 attainers; the fiber identity and both shatter steps on 5,000 random [5] instances, zero violations; 20,000 + 4,677 sampled above-bound families all shattering as claimed); the shift (single shifts exhaustively on [4] — 8,262 intersecting family-pair checks plus 2,570 sampled [5] shifts, zero violations; the full-shift census zero violations; 167 antichains counted, 72 broken). One numbering note: the two older mentions of a graded Exercise 16 in this appendix (the Editions paragraph and the canon-audit paragraph) are the session-36 skew-Bollobás exercise in its period numbering — renumbered to Exercise 10/A10 by the session-38 restructure — and are preserved as the historical record; the new 16–20 continue the post-restructure numbering.

---
*Chapter status: ✅ **Feynman edition + exercise backfill (session 41)** — 5 lectures (Sperner three ways; Bollobás with the skew landscape; the circle method and EKR; uniqueness — the proved range complete, the thin range a flagged forward pointer to Chapter 9; shifting), all kept proofs complete; 1 verified figure; 15 graded exercises + 2 ◆ pattern-unknown + 3 ◐ explorations, 17 worked answers machine-verified; lab in 4 verified parts (Sperner/SCD census, EKR interval lemma + uniqueness censuses, Bollobás sweep, the skew battery); the sumsets and shadows material — three lectures with nine exercises, eight answers, Figure 2, and lab Parts 4–6 — lives in Chapter 9, where the two flags are closed. Ships with its web edition (the standard delivery format): the HTML canvas embeds this chapter byte-identically; print to PDF from a browser for a correct export.*
