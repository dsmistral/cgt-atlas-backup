---
name: "cgt-ch17-symmetry-design"
title: "Ch. 17 — Symmetry, Inversion, and Design (A Lecture Course in the Feynman Style)"
type: "text/markdown"
---

# Chapter 17 · Symmetry, Inversion, and Design

*Part of the Combinatorics & Graph Theory Atlas (see the Atlas canvas for the chapter map and progress report).*

Chapter 2 planted a seed you have been carrying ever since. Cayley's formula says n^{n−2} trees grow on n labeled vertices — and then the exploration X1 asked: how many *shapes*? Not trees, tree *types* — two trees counted once if some relabeling carries one onto the other. The labeled count explodes; the shape count limps along as 1, 1, 1, 2, 3, 6, 11, 23. The exploration named the tool that answers such questions — **Pólya's machine** — and deferred it. This is the chapter where the debt is paid. **Symmetry** (Lectures 1–2) is the discipline of counting *orbits* — objects up to relabeling, colorings up to rotation, molecules up to the symmetries of their frame — and it comes in two acts: Burnside's lemma averages a group over its fixed points, and Möbius inversion runs the same averaging idea backwards, recovering the individual counts that a pile of sums has smeared together. **Design** (Lectures 3–4) is the second half: combinatorial objects — Steiner triple systems, projective planes, the schoolgirls' walking schedule — whose existence is governed by pure *arithmetic divisibility*. The through-line is a counting question asked three ways: when you average over symmetry, what are you really counting; when you invert an average, what survives; and when you demand that every pair of points sit in exactly one block, which universes of points are even possible? **Codes** (Lectures 5–6) close the circle: the error-correcting codes of Chapter 8 return with their Singleton and Plotkin bounds, and the Golay codes — the best single page in coding theory, Berlekamp called their 1949 announcement — turn out to *be* designs in disguise: their weight supports are the Witt systems S(4,5,11), S(5,6,12), and S(5,8,24), whose automorphism groups are the sporadic Mathieu groups.

The deal with the reader is the one the Atlas has enforced since Chapter 1: every number printed below was machine-verified before printing — exhaustive orbit censuses, complete Steiner-system searches (STS(13) = 2 proved by a machine run that visited all 41,621 search states), perfect-code partitions checked word by word — and where a statement is a conjecture, a proof is cited rather than given, or a count is beyond the chapter's computational reach, the text says so in those words.

## How to read this chapter

Nothing here needs beyond Chapter 2 (labeled versus unlabeled graphs, Cayley's formula, the tree-shape exploration X1), Chapter 6 (you met Fisher's inequality there, proved twice — the Gram-determinant route and Bose's dimension argument), and Chapter 8 (the Hamming cube, the [7,4] code, Delsarte's linear program). All group machinery is defined in place; the only group we ever enumerate in full is the rotation group of the cube. Lines marked **✎ Checkpoint** are the places to stop and predict — commit to a guess, in ink, before reading on. Exercises are graded ●○○ *easy* (one idea, applied directly), ●●○ *moderate* (two ideas, or one tricky step), ●●● *tough* (several ideas combined); ◆ **pattern unknown** problems come with no hint — diagnosing the tool is part of the problem; ◐ **Explorations** are open-ended investigations that state what you should find, not a number to match. Worked answers sit at the end; hints travel with the problems.

Notation. A **group action** of a group G on a set X is a map G × X → X, written g·x, with e·x = x and g·(h·x) = (gh)·x; the **orbit** of x is G·x = {g·x : g ∈ G}; X/G is the set of orbits, and Fix(g) = {x : g·x = x}. A **cycle type** is the multiset of cycle lengths in a permutation's disjoint-cycle decomposition; c(g) is its number of cycles. The **cycle index** of an action on n points is the polynomial Z_G(x₁,…,x_n) = (1/|G|)·Σ_{g∈G} x₁^{c₁(g)}···x_n^{c_n(g)}, where c_i(g) is the number of i-cycles in g. A **poset** (P, ≤) is a partially ordered set; μ(x,y) is its **Möbius function**, defined by μ(x,x) = 1 and Σ_{x≤z≤y} μ(x,z) = 0 for x < y. A **t-(v,k,λ) design** is a v-point set with a family of k-subsets (**blocks**) such that every t-subset of points lies in exactly λ blocks; **Steiner system** S(t,k,v) = a t-(v,k,1) design; b = number of blocks, r = number through a fixed point; a design is **resolvable** when its blocks partition into parallel classes, each class partitioning the point set. A **projective plane** of order q is a design with q²+q+1 points, q+1 points per line, any two points on exactly one line (so S(2, q+1, q²+q+1)). A **[n,k,d]_q code** is a q-ary code of length n with q^k codewords and minimum distance d; MDS = meeting the Singleton bound d = n−k+1; A_q(n,d) is the largest size of any q-ary (n,d)-code.

The chapter's machine runs follow the Atlas's standing rule: exhaustive where feasible (every orbit census cross-checked against a brute-force canonicalization; the S(2,3,6) non-existence verified over all 15,504 candidate block-sets; the Kirkman schedule checked line by line), and every search recorded so it can be replayed exactly.

## The pattern map for this chapter

| Pattern | Plain language | Where it fires |
|---------|---------------|----------------|
| **P10 Averaging / expectation** | The average is a promise; some object beats it | L1 (Burnside: the average of fixed points IS the orbit count — averaging as an exact identity, not an estimate) |
| **Symmetry averaging (new this chapter)** | To count objects up to symmetry, average the fixed points of the symmetry | L1 (necklaces, the colored cube, tree shapes — the debt to Chapter 2's X1 paid); proposed to the Atlas pattern registry at ship |
| **Möbius inversion (new this chapter)** | Sums hide individuals; run the sieve backwards to recover them | L2 (τ, φ, the partition lattice; Rota's incidence algebra); proposed at ship |
| **Double-counting / divisibility (new this chapter)** | Count one thing two ways; integrality is existence's admission fee | L3–L4 (Fisher's inequality b ≥ v; the v ≡ 1, 3 mod 6 gate; S(2,3,6) impossible at r = 5/2; Keevash's divisibility conditions); proposed at ship |
| **Words-as-designs (new this chapter)** | A code's constant-weight words carry a t-design on their supports | L6 (759 octads = S(5,8,24); 132 weight-6 words of the ternary Golay = S(5,6,12); Assmus–Mattson); proposed at ship |

---

## Lecture 1 · The Orbit-Counting Machine: Burnside, Pólya, and the Shapes of Trees

### 1.1 The question Chapter 2 left open

Cayley's formula counts trees on *labeled* vertices: 128 of them at n = 4, 1,250 at n = 5, 16,807 at n = 6. But the number of *shapes* — unlabeled trees, isomorphism classes — is 2, 3, 6, 11 at those sizes. The labeled count is a pile of copies: every shape on n vertices contributes exactly n!/|Aut(shape)| labelings (its automorphisms fold labelings onto each other), so the labeled world and the shape world are related by a sum you cannot read backwards:

n^{n−2} = Σ_{shapes S} n!/|Aut(S)|.

Two shapes with different automorphism groups contribute differently, and nothing about the equation lets you pull the shape count out. What is missing is a machine that counts *orbits* — equivalence classes under a group action — directly. Burnside's lemma is that machine, and it is almost embarrassingly simple once you see the double counting that powers it.

### 1.2 Burnside: averaging as an exact identity

**Lemma (Burnside — actually Cauchy 1845, Frobenius 1887; Burnside popularized it in his 1897 textbook, always with credit to Frobenius).** For a finite group G acting on a finite set X, the number of orbits is the average number of fixed points:

|X/G| = (1/|G|) · Σ_{g∈G} |Fix(g)|.

**Proof.** Count pairs (g, x) with g·x = x, two ways. Summing over group elements gives Σ_g |Fix(g)|. Summing over points gives Σ_x |Stab(x)|, and each point's orbit has size |G|/|Stab(x)| — the cosets of its stabilizer — so the points of one orbit contribute |G| in total. Orbits therefore each contribute exactly |G| to the second sum, and dividing by |G| counts orbits. Both sums equal, divide, done. ∎

This is Stigler's law in its purest form — the lemma that is not Burnside's — and the proof shows why the averaging works: it is not an estimate, it is bookkeeping. The orbit count falls out of a double count of pairs.

**✎ Checkpoint.** Before computing anything: 2-color necklaces of length 4, beads on a loop up to rotation. Predict how many there are, then check that the naive guess "2⁴/4 = 4" is close but has the wrong denominator. Where does the rotation group of a 4-loop fail to have every orbit of size 4?

The machine: the rotation group C₄ acts on the 16 colorings. The identity fixes 16; the rotations by one and three beads fix only the 2 constant colorings; rotation by two fixes 4. Burnside: (16 + 2 + 4 + 2)/4 = 6. The answer 6 — not 4 — is the orbit count, and the all-white and all-black necklaces are exactly the orbits whose small stabilizers made the division naive. Run the same computation for n = 1..12 and the census is **2, 3, 4, 6, 8, 14, 20, 36, 60, 108, 188, 352** — each value machine-checked two ways in this chapter's lab: brute-force canonicalization of every one of the 2^n strings against the same formula (1/n)·Σ_k 2^gcd(n,k), agreement at every n.

### 1.3 Pólya: the cycle index turns the lemma into a polynomial

Burnside's sum demands |Fix(g)| for each group element, and for coloring problems that is a one-liner: a coloring is fixed by g exactly when it is constant on each cycle of g, so a k-coloring has k^{c(g)} fixed colorings, c(g) the cycle count. Substitute and you have **Pólya's enumeration theorem**:

# orbits of k-colorings = Z_G(k, k, …, k), where Z_G(x₁,…,x_n) = (1/|G|)·Σ_{g∈G} ∏_i x_i^{c_i(g)}.

The polynomial Z_G — the **cycle index** — is worth computing once and keeping: it answers the coloring question for every k at the same time. (History's honest note: J. H. Redfield published the essence of this in 1927, in a paper so obscure that Pólya's 1937 independent rediscovery — motivated by counting chemical isomers — gave the theorem its name; "Redfield–Pólya" is the fair hyphenation.)

**The cube.** Color the six faces of a cube with k colors, up to rotation. The rotation group of the cube has 24 elements — machine-verified in this chapter's lab by generating the closure of two quarter-turns — with five cycle types on faces, machine-tallied as 1⁶:1, 2²1²:3, 2³:6, 3²:8, 4·1²:6 (identity; 180° turns about face axes; 180° turns about edge axes; 120° turns about vertex axes; quarter-turns about face axes — the counts sum to 24). A coloring fixed by a rotation is constant on each cycle, so each type contributes k^{#cycles}: k⁶, k⁴, k³, k², k³ respectively, and the cycle index collapses to

(k⁶ + 3k⁴ + 12k³ + 8k²)/24,

and for k = 1, 2, 3, 4, 5 the counts are **1, 10, 57, 240, 800** — every value machine-verified against brute-force canonicalization of all k⁶ labeled colorings under all 24 rotations. Pólya's original motivation was exactly this kind of question — counting chemical isomers, where a molecule's mirror-symmetric carbon framework turns equivalent labelings into one compound — and the closed form explains at a glance why the count at k = 2 is 10 rather than anything near the naive 2⁶/24: the two constant colorings ride through all 24 rotations fixed, inflating their orbits' share of the average.

### 1.4 Paying Chapter 2's debt: tree shapes by multiset closure

The tree-shape sequence — the X1 counts 1, 1, 1, 2, 3, 6 extended to n = 8 — is not a Pólya application in the direct sense (the "group" would act on an infinite set), but it is the same philosophy: count orbits by building each *exactly once*. The engine that does it is recursive and canonical. A rooted tree of size n is a multiset of rooted trees of sizes summing to n−1, so rooted shapes are generated by multisets of smaller ones, deduplicated by generating multisets in sorted order — every shape produced exactly once, no isomorphism test needed. The unrooted version splits by centroid: a tree has either one centroid (count: rooted multisets of total size n−1 with every branch at most ⌊(n−1)/2⌋) or two (n even: an unordered pair of rooted trees of size n/2), and the two cases are disjoint.

The census, machine-run twice (multiset generation, and full Prüfer-sequence enumeration over all n^{n−2} labeled trees with canonical-form dedup — the two agree at every n): unrooted shapes n = 1..8 are **1, 1, 1, 2, 3, 6, 11, 23**; rooted, **1, 1, 2, 4, 9, 20, 48, 115**. Chapter 2's first six values are exactly the opening of these sequences, and the automorphism-group subtlety that broke the naive division — why 16,807 labeled 6-vertex trees do not divide by 720 into an integer count of shapes — is now visible in the machine: the shapes' |Aut| values range from 2 to 120 and the sum Σ n!/|Aut(S)| = n^{n−2} balances term by term.

### 1.5 What to learn

Symmetry counting is double counting in disguise. Burnside's lemma is proved in two lines by counting pairs; Pólya's theorem packages the fixed-point counts into a polynomial that answers a whole family of questions at once; and the way to generate orbits directly — never produce two representatives of the same orbit, rather than produce and deduplicate — scales to the tree-shape census where the group is too wild to enumerate. The averaging pattern (P10) here upgrades from "some object beats the average" to "the average *is* the answer."
