---

## Lecture 4 · Designs II: The Existence Theorems — Wilson, Keevash, and the Schoolgirls

### 4.1 Resolvability: Kirkman's problem, solved on the smallest stage

Kirkman's walking problem asks for more than an STS(15): the 35 triples must partition into **7 parallel classes of 5 disjoint triples each**, every class a partition of the 15 girls, so no two girls walk together twice across the week. A design with such a class structure is **resolvable**. The lab constructs the answer on the smallest geometric stage — PG(3,2), the projective 3-space over F₂: its 15 points are the nonzero 4-bit vectors, its lines the triples {a, b, a XOR b}, and its **35 lines are precisely an STS(15)** (every one of the 105 pairs lies in exactly one line — machine-checked). A **spread** is a set of 5 lines partitioning the points; the space has exactly **56 spreads** (machine census). The parallelism the schoolgirls need is a set of 7 spreads sharing no line; the search finds it, and the schedule is printed in the lab verbatim — Monday through Sunday, every class a clean partition, all 35 lines used exactly once. The full record: STS(15) has 80 isomorphism classes and exactly how many resolvable ones was settled only in the computer era; the lab's resolvable witness is the classical one and its verification is line-by-line.

(Sylvester's harder question — extend the walk to 13 *weeks* so every pair of girls walks together exactly once per week and every triple... the full statement of his 13-week problem — was settled by Denniston in 1974, seven hours of Elliott 4130 time; uniqueness of his solution is still open. The chapter cites and moves on.)

### 4.2 Wilson: existence up to finitely many exceptions

For a fixed k, does a 2-(v, k, 1) design (a pairwise balanced design, PBD) exist for all large admissible v? Wilson's theorem chain of the early 1970s ("An existence theory for pairwise balanced designs" I–III) answers **yes**: for each k, all but finitely many v satisfying the divisibility conditions actually carry a design. The proof engine — pairwise balanced designs with one block size at a time, glued via Wilson's fundamental construction — is beyond this chapter's scope to prove; what the chapter keeps is the *shape* of the answer: divisibility is a finite check, non-existence is confined to a finite exceptional set, and the exceptional set is computable in principle for every fixed k.

### 4.3 Keevash: divisibility is the only obstruction, at last

The finishing theorem is recent and is one of the great results of modern combinatorics:

**Theorem (Keevash 2014, "The existence of designs," arXiv 1401.3665).** For every t and k, there is n₀ such that for all n ≥ n₀ satisfying the divisibility conditions — C(n−i, k−i)/C(t−i, k−i) ∈ ℤ for every 0 ≤ i < t — a Steiner system S(t, k, n) exists.

Steiner's 1853 question, open for 160 years, closes: for large systems, the arithmetic gate that blocked S(2,3,6) at a glance is the *only* obstruction. The proof is non-constructive (randomized algebra — a subtle blend of the probabilistic method of Chapter 4 with algebraic structure), and it further settled the existence of nontrivial Steiner systems for t ≥ 6 and infinitely many t = 4, 5.

The lab runs the divisibility check where the chapter can hold it in its hands, on quadruple systems S(3,4,n): the conditions are C(n,3)/4, C(n−1,2)/3, and (n−2)/2 all integral. n = 10: 30, 12, 4 — SQS(10) exists (the lab builds it: 2,520 labeled systems, one orbit, uniqueness — Barrau's 1908 theorem machine-confirmed; |Aut| = 1,440). n = 12: fails at C(11,2)/3 = 55/3 — no SQS(12), arithmetic gate closed before any search. And the census over n = 4..60: divisibility holds exactly when n ≡ 2 or 4 (mod 6) — Hanani's iff theorem (1960/1963), with the machine checking the arithmetic half.

### 4.4 The small-quadruple ladder, honestly

S(3,4,8): the lab finds 30 labeled systems, one orbit — unique, with |Aut| = 1,344 = AGL(3,2) (the 30 labeled copies each with 1,344 automorphisms exactly partition 8! = 30·1,344). S(3,4,10): unique as above. SQS(16): **1,054,163** systems (cited; the honest lab note says why: at v = 16 even a single system's labeled orbit census is an industrial computation, and the count belongs to the classification literature, not to this chapter's machines). S(4,5,v): unique at v = 11 (the Witt small system — Lecture 6's ternary Golay will *be* it), nonexistent at 15 and 17, known at 23, 35, 47, 71, …, and the smallest open order is **21**. The ladder's shape: after the first two rungs, counting collapses from "uniqueness" to "census by industrial machine," and by the third rung into open problems — the design universe thickens as fast as the existence theory thins.

### 4.5 What to learn

Existence at scale is the divisibility conditions *plus* one theorem. Kirkman's resolvable STS(15) shows constructions can be pure geometry (PG(3,2)); Wilson confines exceptions to finite sets; Keevash erases them entirely for large v. The pattern entry proposed: **double-counting/divisibility** — integrality as the admission fee, existence as the theorem that the fee is sufficient.

---

## Lecture 5 · Coding Beyond the Sphere: Singleton, Plotkin, and Gilbert–Varshamov

### 5.1 Where Chapter 8 left the cube

Chapter 8 built the Hamming theory: the [7,4,3] code — 16 words, minimum distance 3, the weight distribution A = [1, 0, 0, 7, 7, 0, 0, 1] (one zero word, seven of weight 3, seven of weight 4, one all-ones) — and Delsarte's linear program on the cube. This lecture takes the three bounds that shape every code family: Singleton from the outside, Plotkin from the outside when distances are dense, Gilbert–Varshamov from the inside. The lab re-derives the Hamming [7,4,3] from the parity-check view (columns = the seven nonzero 3-bit vectors) and machine-verifies its **perfectness**: 16 radius-1 balls of size 8 tile F₂⁷, 16·8 = 128 = 2⁷ — every word within distance 1 of exactly one codeword, the sphere-packing identity made literal.

### 5.2 Singleton and MDS

**Theorem (Singleton bound; standard citation Singleton 1964 — though proven earlier by Joshi in 1958 and Komamiya in 1953, a priority the chapter records honestly).** Any q-ary code of length n, size M, minimum distance d satisfies M ≤ q^{n−d+1}. *Proof in one move:* puncture d−1 coordinates; surviving words remain distinct, and there are only q^{n−d+1} of them. ∎

Codes meeting the bound with equality — [n, k, n−k+1]_q — are **MDS** (maximum distance separable). The binary census is a desert: the lab enumerates every binary code up to n = 7 by canonical subspace enumeration (Gaussian cross-checks on the row-reduced keys) and finds *no* nontrivial binary MDS — the only [n, k, n−k+1]₂ codes are the trivial three families (whole space k = n, repetition k = 1, and parity k = n−1). Over larger alphabets the desert blooms: **Reed–Solomon codes** take the messages (a, b) ∈ F_q² and evaluate a + bx at n distinct field points. The lab's witnesses over F₅: evaluations at 4 points give **[4,2,3]₅** (25 words, all distinct, machine minimum pairwise distance exactly 3 = Singleton) and at all 5 points **[5,2,4]₅** (distance 4 = Singleton). A degree-1 polynomial has at most 1 root, so two messages differ in at least n−1 positions — Singleton tight for every n ≤ q+1, and the whole family rides one polynomial fact.

How far can MDS go? The **MDS conjecture** (posed as a question by Segre in 1955): a nontrivial [n,k]_q MDS code has n ≤ q+1, except when q is even with k = 3 or k = q−1, where n ≤ q+2. The prime-field case is now a theorem — **Ball 2012**, with Ball–De Beule 2012 giving k ≤ 2p−2 for q = p^h — and the general case is **open**. Another honest frontier entry.

### 5.3 Plotkin: dense distance caps size

**Theorem (Plotkin 1960).** A binary code of length n and minimum distance d with 2d > n has at most 2·⌊d/(2d−n)⌋ codewords; in the boundary case A(2d, d) ≤ 4d.

*Proof shape (the chapter's full proof is by averaging — the pattern map's P10 in its purest code-theoretic use):* sum the pairwise distances two ways. On one hand, every pair is ≥ d apart, contributing d·C(M,2). On the other, column by column: if a column has z zeros and M−z ones it contributes z(M−z) ≤ M²/4, so the total is ≤ M²n/4. Comparing: d·M(M−1)/2 ≤ M²n/4, which rearranges (M ≥ 2) to M ≤ 2d/(2d−n). ∎ (Chapter 8 already owns the Delsarte-certificate form of Plotkin — the certificate F = 1 + K₁/(2d−n) — the two routes agree and the cross-reference stands.)

The bound is tight in the dense corner where Singleton is slack: the lab exhibits **A(6,4) = 4** (Plotkin bound 2·⌊4/2⌋ = 4, met by a machine-constructed code of 4 words) and **A(7,4) = 8** (bound 2·⌊4/(8−7)⌋ = 8, met by the **[7,3,4] simplex code** — the dual of the Hamming code: all seven nonzero codewords have weight exactly 4, so every pair sits at distance 4, machine-verified). Simplex structure saturates Plotkin exactly as polynomial structure saturates Singleton: **the extremal witness teaches the bound**.

### 5.4 Gilbert–Varshamov: existence from greed

**Theorem (Gilbert 1952; the linear-code version Varshamov 1957).** A_q(n, d) ≥ q^n / Σ_{j=0}^{d−1} C(n,j)(q−1)^j.

*Proof:* greed. Throw balls of radius d−1 around a maximal code; maximality says they cover the whole cube, so M·(ball volume) ≥ q^n. ∎ The lab runs the greedy construction itself and prints honest witnesses at four points — (7,3): 16 ≥ ⌈128/29⌉ = 5; (8,3): 16 ≥ 7; (10,4): 32 ≥ 6; (12,4): 128 ≥ 14 — each a machine-constructed code and a count that clears the bound with room, because the ball-volume denominator over-counts overlaps near the covering boundary.

### 5.5 What to learn

The three bounds are three geometries of the Hamming cube: Singleton slices coordinates away (algebra), Plotkin averages distances (geometry), Gilbert–Varshamov covers (volume). MDS codes live where algebra is richest (polynomials over fields); Plotkin-tight codes where combinatorial designs are (the simplex); and the GV bound is the guarantee that good codes are *easy to find* — greed suffices. The frontier ledger: binary MDS trivial (census), general MDS bounded by a conjecture with the prime case proved, Plotkin's corner exactly charted by simplex witnesses.
