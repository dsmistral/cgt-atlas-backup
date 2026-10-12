## Lecture 2 · Möbius Inversion: Running the Sieve Backwards

### 2.1 The averaging problem, inverted

Burnside computes one aggregate (the orbit count) from many local counts (the fixed points). Averaging has a mirror problem, and number theory lived in it for a century: every positive integer n carries the divisor sum

Σ_{d|n} 1 = τ(n), the number of divisors of n.

Fine — but suppose you know τ and want something *behind* it. The classic behind-the-scenes function is the Möbius function μ(n), the number-theoretic bellows: μ(n) = (−1)^k if n is a product of k distinct primes, μ(n) = 0 if any prime divides n twice, μ(1) = 1. Its whole job is the inversion formula:

if g(n) = Σ_{d|n} f(d) for all n, then f(n) = Σ_{d|n} μ(d)·g(n/d).

Read it as recovering the individual from the pile of sums. Why does μ do this? Because Σ_{d|n} μ(d) = 0 unless n = 1, when it is 1 — the Möbius function sums to an *identity* over the divisors of any n > 1, which is exactly what an inverse needs. The proof of the inversion formula is a change of order of summation plus that identity; it takes four lines and is Exercise 4's warm-up half.

The identity Σ_{d|n} μ(d) = [n = 1] and the sibling identities Σ_{d|n} φ(d) = n and Σ_{d|n} d·μ(n/d) = φ(n) are all machine-verified in this chapter's lab over every n ≤ 10,000 — zero mismatches; spot values: τ(60) = 12, φ(60) = 16, φ(100) = 40.

### 2.2 Rota's move: the poset is the thing

In 1964 Gian-Carlo Rota asked the question that turned a number-theory trick into a combinatorial theory: *where does μ really live?* Answer: on the divisor lattice — the poset of divisors of n ordered by divisibility, where d ≤ e means d | e. Number-theoretic μ(d) is a value attached to the *pair* (1, n) of that poset, filtered through the pairs (d, e) with n/d squarefree. And the definition that generalizes is this:

**Poset Möbius function.** On a finite poset P, define μ(x, y) for x ≤ y by μ(x, x) = 1 and, for x < y,

μ(x, y) = −Σ_{x ≤ z < y} μ(x, z).

The recursion runs upward: to know μ(x, y) you need μ on the interval strictly below y. (Two traps for the implementer, both caught by the lab's own consistency checks: the sum excludes z = y — including it makes the recursion self-referential and silently wrong; and the recursion accumulates from x *upward*, not from y downward.) The inversion theorem is then pure algebra:

**Theorem (Möbius inversion on posets).** If g(x) = Σ_{x ≤ z ≤ y} f(z) for all x ≤ y (sums over the interval), then f(y) = Σ_{x ≤ z ≤ y} μ(z, y)·g(z).

The proof is one line of algebra once you observe that the functions ζ(x, y) = [x ≤ y] and μ(x, y) are mutual inverses under **convolution** — the incidence algebra of P, where (α ∗ β)(x, y) = Σ_{x ≤ z ≤ y} α(x, z)·β(z, y). ζ is the algebra's identity-shaped zeta function; μ is its inverse, exactly as the Riemann zeta and the classical μ are inverse under Dirichlet convolution. Rota's 1964 paper ("On the foundations of combinatorial theory I. Theory of Möbius functions") made this the founding observation of modern enumerative combinatorics: choose the poset, get a μ, get an inversion.

**✎ Checkpoint.** Before computing: on the Boolean lattice B_k of subsets of a k-set (ordered by inclusion), predict μ(∅, S). Hint: what does inclusion-exclusion look like from inside the incidence algebra?

### 2.3 Three posets, three μ's

- **The divisor lattice** of n. μ(1, n) is the classical Möbius μ(n); μ(d, e) = μ(e/d) filtered as above. The whole of elementary number-theory sieving is one poset.
- **The Boolean lattice B_k.** Every proper extension of the empty set flips sign: μ(∅, S) = (−1)^{|S|}, machine-verified for k ≤ 6 in the lab (all 64 intervals of B_6 checked against the recursion). Inclusion-exclusion — the oldest trick in the counting book — is Möbius inversion on B_k; the pattern map's averaging entry and this lecture are the two faces of one coin.
- **The partition lattice Π_n** (set partitions ordered by refinement; the whole set is the bottom, singletons-only is the top). This one is genuinely nontrivial: |Π_n| = 1, 2, 5, 15, 52 for n = 1..5, and the machine census of μ(0̂, 1̂) — the Möbius value of the whole lattice, bottom to top — is **1, −1, 2, −6, 24**: that is, μ(0̂, 1̂) = (−1)^{n−1}(n−1)!, proved by a bijection of the intervals onto permutations (the classic result, reproducible from the lab's recursion).

### 2.4 What to learn

Averaging hides individuals; inversion buys them back. The structure that makes inversion possible is a poset with a μ attached — and once the incidence algebra is in hand, inclusion-exclusion, the divisor identities, and the partition-lattice sign pattern all become one theorem read off three lattices. The "recover what was averaged" pattern is the proposed registry entry; Burnside and Möbius, Lectures 1 and 2, are the two directions of the same coin.

---

## Lecture 3 · Designs I: Steiner's Question, Fisher's Inequality, and the Planes That Cannot Exist

### 3.1 The schoolgirl's diary and Steiner's question

In 1844 Woolhouse posed, in the Lady's and Gentleman's Diary, the problem of arranging triples so that no pair repeats; Kirkman solved the existence question for triples in 1846 (the paper sits in the journal's 1847 volume — cite Kirkman 1846/47), and in 1850 posed his famous walking problem: fifteen schoolgirls, seven days, rows of three, every pair together exactly once *per week*. Steiner asked the abstract version for k-subsets in 1853, unaware of Kirkman, and the objects carry Steiner's name. Definitions:

A **t-(v, k, λ) design** is a v-point set X and a family B of k-subsets (blocks) such that every t-subset of X lies in exactly λ blocks. λ = 1 gives a **Steiner system S(t, k, v)**. For t = 2, k = 3: a **Steiner triple system STS(v)**. Counting constants: a t-design with v points, b blocks, r blocks through a fixed point, satisfies λ·C(v, t) = b·C(k, t) and r·C(v−1, t−1) = λ·C(k−1, t−1) — double counting the (block, t-subset) pairs two ways. For an STS: b = v(v−1)/6 and r = (v−1)/2.

**✎ Checkpoint.** Before reading on: v(v−1)/6 and (v−1)/2 must be integers. Which v survive? Predict the congruence class before checking the next paragraph.

### 3.2 The arithmetic gate: v ≡ 1, 3 (mod 6), and the exhibit that cannot exist

Integrality of b and r forces v ≡ 1 or 3 (mod 6). The gate has two leaves, both machine-walked in the lab: r = (v−1)/2 integer says v is odd, leaving v ≡ 1, 3, 5 (mod 6); then b = v(v−1)/6 needs 3 | v(v−1), which fails exactly when v ≡ 2 (mod 3) — that is, at v ≡ 5 (mod 6) — leaving **v ≡ 1 or 3 (mod 6)**. The remarkable theorem (Kirkman's constructions, completed by Bose 1939 and Skolem 1958): **STS(v) exists if and only if v ≡ 1 or 3 (mod 6)** — the arithmetic gate is the *whole* story.

And here is the chapter's worked non-existence exhibit, the one the scope sheet nearly fumbled: **S(2,3,6) does not exist.** The formula gives r = (6−1)/2 = 5/2 — not an integer, so no system. The lab makes this a *machine proof*, not an algebra shrug: over all C(20, 5) = 15,504 candidate 5-block families from the 20 triples on 6 points, exactly **zero** exact covers exist. Divisibility is not a technicality; it is the admission fee, and v = 6 cannot pay.

### 3.3 Fisher's inequality: b ≥ v

For 2-designs, block count can never duck below point count:

**Theorem (Fisher 1940).** In a 2-(v, k, λ) design with k < v, b ≥ v.

Chapter 6 proved this two ways — the Gram determinant of the block incidence vectors (a square v × v Gram matrix whenever b = v, with det = (r−λ)^{v−1}·(r+(v−1)λ); the Fano-plane instance prints (3−1)^6·9 = 576 = 24²) and Bose's linear-algebra argument. What this chapter adds is the *census view*: Fisher is tight at the bottom and slack immediately above. The Fano plane STS(7): b = v = 7, tight. STS(9) — the machine census finds exactly 840 labeled systems, all isomorphic (one orbit; the affine plane AG(2,3)): b = 12 > 9. The projective plane of order 3 (next section): b = v = 13, tight again — and this is no accident: **the equality case of Fisher is precisely the symmetric designs**, where any two blocks also meet in exactly λ points, duality everywhere.

### 3.4 Projective planes, and the orders that cannot exist

A **projective plane of order q** is a design with v = q²+q+1 points, blocks (lines) of size q+1, every pair of points on exactly one line — that is, S(2, q+1, q²+q+1). Finite field arithmetic builds one for every prime power q: points = 1-dimensional subspaces of F_q³, lines = 2-dimensional ones. The machine instance this chapter carries everywhere is **PG(2,3)**: 13 points, 13 lines of 4 points, every pair on exactly one line (all 78 pairs machine-checked) — an S(2,4,13), Fisher-tight with b = v = 13. The affine plane AG(2, q) — STS(9) at q = 3 — is the projective plane minus a line and its points.

Do planes exist at every order? Here the story becomes one of combinatorics' great campaigns. The order-2 plane (the Fano plane, v = 7) is unique; order 3 unique; and then:

**Theorem (Bruck–Ryser 1949; Chowla–Ryser 1950).** If a projective plane of order q ≡ 1 or 2 (mod 4) exists, then q is a sum of two squares.

The lab runs the census: q = 6 and q = 14 are 2 (mod 4) and not sums of two squares — **no plane of order 6, none of order 14**. q = 10 is 2 (mod 4) but 10 = 1² + 3², so Bruck–Ryser is silent; the true obstruction took until 1989, when Lam, Swiercz and Thiel closed order 10 by coding theory plus one of the largest computer searches of its era. And q = 12 — 0 (mod 4), outside Bruck–Ryser entirely — is **the smallest open order today**. The chapter says this in those words: nobody knows whether a plane of order 12 exists.

### 3.5 How many systems? The census ladder

Uniqueness at 7 and 9, then a fork: the lab's orderly-generation search — branching on the lowest uncovered pair, canonicalizing candidates under the stabilizer of the partial system, and discarding nothing — visits **41,621 search states and 560 leaves, all valid**, collapses them to isomorphism classes, and returns **STS(13) = 2**: one system with 8 Pasch configurations (four triples on six points, the "quadrilateral" {a,b,c},{a,d,e},{f,b,d},{f,c,e} up to labels), one with 13 — automorphism groups of order 6 and 39, labeled counts 1,037,836,800 + 159,667,200 = 1,197,504,000 = 13!·(2 systems)/(|Aut| sums, as it must). The Fano plane has 7 Pasches, STS(9) has 0; the two STS(13)s split the difference, and the lab's leaves sort cleanly into buckets 468 (8-Pasch) + 92 (13-Pasch). Beyond reach of this chapter's machines and honest to say so: STS(15) = 80 systems; STS(19) = 11,084,874,829 (the Kaski–Östergård classification of 2004).

### 3.6 What to learn

Designs live or die by double counting. The two counting constants (b, r) are forced by λ·C(v, t) = b·C(k, t) before any construction begins; divisibility is the gate; Fisher's b ≥ v is the global shadow of linear independence; and the equality cases — Fano, PG(2,3) — are exactly the symmetric, self-dual worlds where the design looks the same from the block side. The census ladder (1, 1, 2, 80, eleven billion) shows how fast "count the objects" outruns "prove the theorems."
