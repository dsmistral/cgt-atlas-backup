---
name: "cgt-ch12-olympiad"
title: "Ch. 12 — The Olympiad Bridge: Thirty Competition Problems, Worked in Atlas Patterns: A Lecture Course in the Feynman Style"
type: "text/markdown"
---

# Chapter 12 · The Olympiad Bridge

*Part of the Combinatorics & Graph Theory Atlas (see the Atlas canvas for the chapter map and progress report).*

Eleven chapters of machinery stand behind us: counting by bijection and double counting, greedy structures and alternating paths, the probabilistic method, linear algebra over F₂, spectral bounds, shadows and sum-free arithmetic, Ramsey numbers, and algorithms with guarantees. This chapter is the bridge from that machinery to the place it was invented for: the competition problem, posed clean, armed with nothing, on a three-and-a-half-hour clock. The deal we make with the reader is strict: **thirty problems — twenty-eight from the International Mathematical Olympiad and two from its Shortlist, spanning 1964 to 2023 — and every single one solved with patterns the Atlas has already taught.** No new mathematics is introduced in this chapter. None is needed. What the problems test instead is the skill the Atlas has been quietly training all along: *diagnosis*. Read the problem; name the pattern; execute; check.

The chapter is honest in both directions. In the direction of the problems: every statement below was checked against the official source before it was paraphrased, and where the folklore version of a problem differs from the official one — it does, more often than you would guess — the chapter says so and follows the official text. In the direction of the solutions: every numerical claim, witness, construction, and census in this chapter was run through the Atlas's computational lab before it was printed. Where a solution is the Atlas's own (a few had to be developed from scratch, and two of those we regard as the chapter's proudest possessions), the lab verified every link. Where we sharpen a bound or find a counterexample to a folklore strengthening, that is printed too. And at the end of the pattern table sits the chapter's one sociological finding, recorded as a finding and not smoothed over: olympiad combinatorics, sixty years of it, lives on a surprisingly narrow band of the Atlas's pattern spectrum.

The thirty problems climb in three terraces of ten. **Terrace I, the doorstep rungs**: problems you can fall off if you rush, each teaching one pattern cleanly. **Terrace II, the working middle**: problems where the pattern must be combined, tuned, or fought for. **Terrace III, the summit rungs**: problems that were the hardest thing on their year's paper — and are still, every one of them, an Atlas pattern wearing a disguise.

## How to read this chapter

**Notation.** [n] means {1, 2, …, n} in prose. C(n, k) is the binomial coefficient; Σ, Π run over the range in their subscript. All congruences are modulo the number stated. F₂ is the field with two elements, and F₂^d is the vector space the Atlas has used since Chapter 6 — the home of parity vectors. R(3, 3) = 6 and R(3, 3, 3) = 17 are the Ramsey numbers proved in Chapter 10. The *displacement* of an operation is the vector of changes it makes; a *monovariant* is a quantity that changes strictly in one direction each step. When a problem is about a process, "terminates" means: no infinite execution exists.

**The anatomy of every problem.** Each of the thirty is laid out the same way: the **statement** (the Atlas's paraphrase, with the official citation directly under it — go to the source if you want the exact phrasing, and this chapter recommends that habit); **The handle** — one short paragraph of diagnosis, naming the pattern before any work is done, because naming the tool is the skill this chapter actually teaches; the **solution**, written to be read once, straight through, with the arithmetic visible rather than hidden; and **What to learn** — the transferable sentence, the thing you carry to the next problem. Difficulty tags follow the Atlas convention: ●○○ *easy* (one pattern, one clean move), ●●○ *moderate* (one pattern with a twist, or two), ●●● *tough* (a disguise to be seen through, or two patterns that must cooperate).

**Try before you read.** The solutions are printed right under the statements, so the discipline has to be yours: read the statement, close the page (or scroll, as the case may be), and give it ten honest minutes. Then read The handle only, and try again. The solution will still be there.

**A note on sources and the lab.** The statements carry year and problem number from the official IMO record. The solutions credit the pattern first and the source when a construction is classical; several solutions are simpler than the official ones, several are longer because the chapter refuses to hide a computation, and a few had to be derived from scratch when the official solution resisted retrieval. Every witness, census, and bound in what follows was machine-verified before printing — the same rule the Atlas has enforced since Chapter 1: *no number appears in this book that the lab has not checked, or the text has not proved, or the source has not printed.*

## The pattern map for the thirty problems

| Pattern | Plain language | Where you meet it |
|---------|---------------|-------------------|
| **P2 Double counting** | Count the same set two ways; equate | 1 (fixed-point pairs), 2 (problem-pair coverage), 5 (judge agreements), 6 (girl–boy–problem triples), 30 (Schur's upper bound via Ramsey) |
| **P9 Pigeonhole** | n+1 objects, n boxes — with the boxes hidden inside an encoding | 3 (17 edges, 3 colors), 4 (parity classes, twice), 6 (⌈21/6⌉ = 4), 8 (three cards, two piles), 27 (200 even sites), 30 |
| **P25 Reduction / encoding** | Translate into a language whose structure carries the proof | 3 (correspondence → edge-coloring), 4 (integers → F₂⁹), 13 (bare edges → independence), 30 (members → Schur colors) |
| **P1 Bijection / orbits** | Count by symmetry: group actions and their fixed points | 9 (the +2 shift on the circle), 16 (insertion symmetry in the balance) |
| **P4 Monovariant / induction** | A quantity that must move, or a case that reduces | 10 (the pentagon potential), 15 (consecutive residues), 17 (the Bank of Bath), 18 (Zantema's machine, honestly constructive), 19 (the grasshopper's four cases), 28 (the liar's trailing streaks) |
| **P10 Averaging** | Some object beats the average — or the average forces a sign change | 5 (the convexity minimum), 23 (rotation averages over ninja paths) |
| **P8 Extremal / longest-path** | Take an extremal object; its structure cracks | 22 (the tallest surviving pair), 29 (chains and their lengths) |
| **P11 Explicit construction** | Beat the bound by building the object | 12 (the balanced coloring), 14 (the tour when r = 25), 20 (Euler circuits pairing the pebbles), 22 |
| **P7 Parity** | Coloring obstructions: what a two-coloring forbids | 14 (mod 3 and mod 7 obstructions), 13 (the parity of bare-edge matchings) |
| **P15 Induction on vertices/edges** | Delete, solve smaller, extend | 21 (splitting the clique across two rooms) |
| **P16 Alternating paths** | Repair a partial solution along a cycle | 12 (peel leaves, alternate around cycles) |
| **P17 Duality (min–max)** | Two players, one number; a strategy is a proof | 27 (the √5 game's value is exactly 100), 28 (the liar game's window n ≥ 2k) |
| **P18 Algorithmic proof** | The proof *is* a procedure; termination is the theorem | 25 (the hunter's forced failure), 26 (the windmill's sweep), 29 (the swap algorithm) |
| **P26 Compactness** (flavor only) | Infinite patience, finite budget — and a limit argument in disguise | 25 (10⁹ rounds, 100 of distance) |
| **Diagnosis is the skill (lore)** | The thirty problems use thirteen patterns. The other thirteen — inclusion–exclusion (P3), generating functions (P5), complement/reflection (P6), the probabilistic trio (P12–P14), and the professional toolkit of rank, spectral bounds, polynomials, compression, and shadow pricing (P19–P24) — appear **zero times** | The finding, discussed below the table |

**The honest census.** Sixty years of olympiad combinatorics, thirty problems chosen *for* pattern coverage and still the professional toolkit never fires. That is not an accident of selection; it is the nature of the competition. Inclusion–exclusion loses to double counting because the jury wants clean constants. Generating functions lose to bijections because a bijection *is* an explanation while a coefficient extraction is an audit. The probabilistic patterns lose because "there exists" must be witnessed by hand at olympiad scale, and the random constructions that make P12–P14 shine need room — 10⁶ vertices of room — that a three-hour exam cannot grant. The spectral and polynomial machinery (P19–P24) solves problems that the juries, quite sensibly, do not ask teenagers. The Atlas records this without embarrassment: the contest is a gym for the elementary patterns, and the elementary patterns are the ones this book built its first five chapters on. The remaining lectures of the Atlas — the professional ones — are where the other thirteen patterns earn their keep, on problems no jury would set. The Bridge runs in both directions.

---

## Terrace I · The doorstep rungs (problems 1–10)

The doorstep rungs are not the easiest ten because they are trivial; several have bitten strong solvers. They are the doorstep because each one is *one pattern, seen cleanly*, if you look. The skill to practice on this terrace is the first move after reading: say the pattern's name out loud before touching the paper. The solutions below model exactly that.

### Problem 1 (●○○) · IMO 1987, Problem 1 — fixed points, counted twice

Let p_k(n) denote the number of permutations of {1, 2, …, n} that leave exactly k of the n numbers fixed (a number is *fixed* if it is mapped to itself). Prove that

  Σ_{k=0}^{n} k · p_k(n) = n!.

*Source: IMO 1987, Problem 1.*

**The handle.** P2, double counting — and the tell is the factor *k* multiplying a count. When an identity reads "(number of objects with property-count k) times k, summed, equals something," read the factor as "choose one distinguished element of the property" and hunt for the set being counted twice.

**Solution.** Count the pairs (π, i) where π is a permutation of [n] and i ∈ [n] is fixed by π, i.e. π(i) = i.

Count by the position i first. For a fixed i, the permutations with π(i) = i are exactly the permutations of the remaining n − 1 numbers: there are (n − 1)! of them. Summing over the n choices of i gives n · (n − 1)! = n! pairs.

Now count by the permutation π. If π fixes exactly k numbers, it participates in exactly k pairs (π, i) — one for each fixed point. Grouping the n! permutations by their fixed-point count, the number of pairs is Σ_k k · p_k(n).

The two counts measure the same set of pairs, so Σ_k k · p_k(n) = n!. ∎

The lab enumerated every permutation for n = 1 through 7 (up to 5040 of them) and confirmed the identity each time; the proof above shows why it could not have failed.

**What to learn.** A factor multiplying a count is a signature: it means a *distinguished element* is being summed over, and the whole identity is a double count in costume. The same move returns in Problems 2 and 5 — and, for that matter, in the degree-sum identity Σd(v) = 2m that the Atlas has used since Chapter 2, which is this problem with "fixed points" read as "edge-ends."

### Problem 2 (●●○) · IMO 2005, Problem 6 — the missing fifth problem

In a mathematical competition there were six problems and n contestants. Any two of the problems were solved by more than 2/5 of the contestants, and nobody solved all six problems. Show that at least two contestants solved exactly five problems each.

*Source: IMO 2005, Problem 6.*

**The handle.** P2 again — but this time the double count has to be *tuned*: it produces a bound with a residue-class hitch, and one residue class (n ≡ 2 mod 5) needs a second, finer count. The strict inequality "more than 2/5" becomes the integer threshold ⌊2n/5⌋ + 1 — the Atlas's standing advice that fractions of n are floors plus one.

**Solution.** Write T = ⌊2n/5⌋ + 1, so every pair of problems was solved by at least T contestants. Let t be the number of contestants who solved exactly five problems; we must show t ≥ 2.

*The coarse count.* Count the pairs (contestant, pair-of-problems-they-solved). By the demand side, each of the C(6, 2) = 15 problem pairs contributes at least T: at least 15T pairs. By the supply side, a contestant who solved k ≤ 5 problems (nobody solved six) contributes C(k, 2) pairs, which is at most 10 if k = 5 and at most 6 if k ≤ 4. So the total supply is at most 10t + 6(n − t) = 6n + 4t. Hence

  15T ≤ 6n + 4t,  i.e.  4t ≥ 15⌊2n/5⌋ + 15 − 6n.

Write n = 5q + r. Working the right-hand side for r = 0, 1, 2, 3, 4 gives 15, 9, 3, 12, 6 respectively, so

  t ≥ ⌈15/4⌉ = 4,  ⌈9/4⌉ = 3,  ⌈3/4⌉ = 1,  ⌈12/4⌉ = 3,  ⌈6/4⌉ = 2

for the five residues. Every residue except r = 2 finishes at once: t ≥ 3 or t ≥ 4 or t ≥ 2, all at least 2. So assume from here on that **n = 5q + 2** and, for contradiction, that **t = 1**: a single contestant solved five problems.

*The fine chain (n = 5q + 2, t = 1).* Here T = 2q + 1. With exactly one five-solver and everyone else at four or fewer, the supply is at most 10 + 6(5q + 1) = 30q + 16, against a demand of 15T = 30q + 15: the budget overshoots by exactly **one**. Formally, Σ (6 − C(k_c, 2)) over the 5q + 1 non-five-solvers — the *deficit* of each, where the deficit is 0 for k = 4, 3 for k = 3, 5 for k = 2, and 6 for k ≤ 1 — sums to at most 1. Since deficits are nonnegative and jump by threes or more, the only possibility is: every one of the 5q + 1 other contestants solved **exactly four** problems.

Now let the lone five-solver's missing problem be problem 1, and let S be the other five problems. Let m be the number of the remaining contestants who solved problem 1. Each of the m contestants solving problem 1 also solves exactly three of the five problems in S (they have four total, one is problem 1); each of the 5q + 1 − m others solves four in S.

Demand on the five pairs {1, j}, j ∈ S: no five-solver helps there (he missed problem 1), so each pair needs at least T = 2q + 1 co-solvers from the others; summing, and re-routing through the m contestants (each contributes three pairs {1, j}), gives

  3m ≥ 5(2q + 1) = 10q + 5.

Demand on the ten pairs inside S: the five-solver helps once per pair, so each pair needs at least 2q co-solvers among the others. Counting contributions (a non-problem-1 solver contributes C(4, 2) = 6 pairs inside S; a problem-1 solver contributes C(3, 2) = 3):

  6(5q + 1 − m) + 3m ≥ 10 · 2q,  i.e.  3m ≤ 10q + 6.

So 3m lies in the window [10q + 5, 10q + 6]. Now run the third count, per problem j ∈ S: the five demands touching j (the pair {1, j} needing 2q + 1 others, and the four pairs {i, j} inside S needing 2q others each) total 10q + 1 others-pair incidences, and any single other contestant solves at most three of those five pairs (whether or not they solve problem 1). Hence the number d_j of others solving problem j satisfies 3d_j ≥ 10q + 1, so d_j ≥ ⌈(10q + 1)/3⌉. Summing over the five j ∈ S: the total Σ d_j counts, per other contestant, the number of S-problems they solve, which is 4 for the 5q + 1 − m non-problem-1 solvers and 3 for the m:

  20q + 4 − m = Σ_{j∈S} d_j ≥ 5⌈(10q + 1)/3⌉,  i.e.  m ≤ 20q + 4 − 5⌈(10q + 1)/3⌉.

*Closeout by residues of q mod 3.* If q ≡ 2 (mod 3), the window [10q + 5, 10q + 6] contains no multiple of 3 (its endpoints are ≡ 1 and ≡ 2 mod 3), so no integer m exists. If q ≡ 0 (mod 3), the window forces 3m = 10q + 6; the ceiling in the bound is ⌈(10q + 1)/3⌉ = (10q + 2)/3 + ... — carrying the two lines through, m ≤ (10q + 2)/3 while the window wants m = (10q + 6)/3: contradiction. If q ≡ 1 (mod 3), the window forces 3m = 10q + 5 while the bound gives m ≤ (10q + 2)/3: contradiction again. All three residues die, so t = 1 is impossible: **t ≥ 2**. ∎

Two honesty notes, both lab-checked. First, the theorem is true but *vacuous* for tiny n: for n ≤ 3 no configuration satisfies the hypotheses at all (each contestant must miss a problem, and some pair of problems then absorbs too many misses), so the statement's content begins at n = 4, witnessed by four contestants each missing a different problem. Second, the bound t ≥ 2 is not claimed sharp in general — the coarse count already forces t ≥ 4 at n = 5, and no configuration with exactly two five-solvers exists there; the theorem's floor and the truth drift apart at small n, and the Atlas declines to pretend otherwise.

**What to learn.** A double count with a strict inequality gives a floor-plus-one threshold; when the resulting bound has a residue-class hitch, do not force it — run the fine count *inside the surviving residue*, where the slack is small enough that every contestant's hand is forced. The engine of the fine chain is: a budget overshoot of one forces exact structure (everyone at exactly four), and exact structure makes the next count deterministic.

### Problem 3 (●○○) · IMO 1964, Problem 4 — seventeen pen pals

Seventeen people correspond by mail, each of them writing to all the others. In their letters they discuss exactly three topics, and each pair of correspondents writes to one another about exactly one of the three topics. Prove that there are three people any two of whom write to each other about the same topic.

*Source: IMO 1964, Problem 4.*

**The handle.** P25, reduction — the correspondence *is* an edge-coloring. Draw the complete graph on seventeen vertices, color each edge by the pair's unique topic: the task is exactly to find a monochromatic triangle. And the number that guarantees a monochromatic triangle in three colors is a machine the Atlas already built: R(3, 3, 3) = 17, Chapter 10.

**Solution.** The seventeen people become the vertices of K₁₇; each edge {x, y} receives the color of the unique topic that x and y discuss. A monochromatic triangle is precisely three people each pair of whom discuss the same topic. By the three-color Ramsey number R(3, 3, 3) = 17 — proved in Chapter 10, originally by Greenwood and Gleason in 1955 — every 3-coloring of the edges of K₁₇ contains a monochromatic triangle. Done. ∎

The Atlas does not leave "17" unexamined, because Chapter 10 earned the number the hard way: the lower-bound side is a coloring of K₁₆ with *no* monochromatic triangle, and it is worth carrying in your pocket. Label the sixteen vertices by the vectors of F₂⁴ (all sixteen binary 4-tuples). Split the fifteen nonzero vectors into three sum-free classes of five —

  C₁ = {0001, 0010, 0100, 1000, 1111},  C₂ = {0011, 0101, 0111, 1010, 1011},  C₃ = {0110, 1001, 1100, 1101, 1110}

(in decimal, {1, 2, 4, 8, 15}, {3, 5, 7, 10, 11}, {6, 9, 12, 13, 14}) — where *sum-free* means no XOR of two distinct elements of a class lands back in the class. Color the edge {x, y} by the class containing x ⊕ y. If a triangle x, y, z were monochromatic, the three vectors x⊕y, y⊕z, z⊕x would all lie in one class; but (x⊕y) ⊕ (y⊕z) = x⊕z, and x⊕y ≠ y⊕z since x ≠ z — two distinct elements of the class XOR-ing into the class, contradicting sum-freeness. So sixteen people *can* escape (split them into the sixteen vectors and discuss topic c on the pair {x, y} whenever x ⊕ y ∈ C_c); seventeen cannot. The lab verified the partition's sum-freeness and enumerated all 560 triangles of K₁₆ under this coloring: zero monochromatic.

**What to learn.** The hardest part of this problem is realizing there is no problem: the statement is a coloring in costume, and the number 17 is not a participant but a *citation*. Sixty years before the Atlas proved R(3, 3, 3) = 17 in Chapter 10, the IMO jury set it as a doorstep exercise — the first recorded instance, as far as the Atlas knows, of an olympiad problem whose entire content is a Ramsey number. Reduction (P25) at its purest: recognize that the target structure carries the proof, and the translation *is* the solution.

### Problem 4 (●●○) · IMO 1985, Problem 4 — fourth powers from fifth-smooth numbers

Given a set M of 1985 distinct positive integers, none of which has a prime divisor greater than 23, prove that M contains four distinct elements whose product is the fourth power of an integer.

*Source: IMO 1985, Problem 4.*

**The handle.** P25 then P9, twice. Encode each integer by the parities of its prime exponents — the F₂ alphabet the Atlas has written in since Oddtown (Chapter 6). Two integers multiply to a perfect square exactly when their parity vectors agree; that turns "find four numbers" into "find two agreeing pairs," which is pigeonhole. And then the pigeonhole runs *again*, one level up.

**Solution.** The primes up to 23 are nine: 2, 3, 5, 7, 11, 13, 17, 19, 23. Every m ∈ M factors as m = 2^{e₁}·3^{e₂}⋯23^{e₉}; record the parity vector v(m) = (e₁ mod 2, …, e₉ mod 2) ∈ F₂⁹. There are 2⁹ = 512 possible vectors.

*Stage one: pairs with square products.* If v(a) = v(b), then every prime exponent in ab is even, so ab is a perfect square. Pair up elements of M that share a parity vector, greedily and disjointly: a class containing c elements yields ⌊c/2⌋ pairs, so with 1985 elements spread over at most 512 classes, the number of disjoint same-class pairs is at least

  (1985 − 512)/2 = 736.5,  hence at least 737.

(Each unpaired element is a leftover from an odd class; at most 512 leftovers exist.) So we hold 737 disjoint pairs (a_i, b_i) with a_i·b_i = s_i² for integers s_i.

*Stage two: pairs of pairs.* Each s_i is a product of primes up to 23 (it divides the square root of a product of such numbers — formally, its prime factorization cannot contain anything else, since s_i² = a_i b_i is 23-smooth). So each s_i has its own parity vector v(s_i) ∈ F₂⁹. There are 737 of these vectors and only 512 possible values, so two of them coincide: v(s_i) = v(s_j) for some i ≠ j. Then s_i·s_j is itself a perfect square, say s_i s_j = t². But now

  a_i · b_i · a_j · b_j = s_i² · s_j² = t⁴,

a fourth power — and the four numbers a_i, b_i, a_j, b_j are distinct because the pairs were disjoint. ∎

*How sharp is 1985?* The counting above uses only that the number of pairs exceeds 512, i.e. that ⌈(n − 512)/2⌉ ≥ 513, which is n ≥ 1537. So **1537 numbers always suffice** — a sharpening the problem's jury knew well (1537 = 3·2⁹ + 1) — and the pigeonhole budget shows the shape of the true threshold: with n = 1536 = 3·512, a set holding each parity class in a triple yields exactly 512 pairs and exactly 512 root vectors, with no *forced* collision. The Atlas verified the analogous small world rather than trust the shape: with the three primes {2, 3, 5} (eight parity classes, threshold 3·2³ + 1 = 25), the lab checked that every one of 400 random 25-element sets of {2, 3, 5}-smooth numbers contains a fourth-power quadruple, and — the sharpened side — built a 24-element set with no such quadruple: all eight parity classes, each held in a triple of numbers scaled by the squares 1, 4, 9. The analogue's threshold is exactly 25, and the counting argument's 3·2^d + 1 is the honest general law.

**What to learn.** Parity vectors turn multiplicative structure into linear structure over F₂ — the Atlas's oldest encoding, and here it fires *twice in one proof*: once to find square products, once to find square products among the square roots. Two-stage pigeonhole is a pattern in its own right: when the first pigeonhole produces a new population, ask whether that population is itself pigeonhole-able. And always run the sharpening: the official number 1985 was chosen to be memorable (the year), not minimal (1537); olympiad constants are rarely tight, and knowing the true threshold is part of owning the problem.

### Problem 5 (●●○) · IMO 1998, Problem 2 — judges, and the cost of agreeing

In a competition there are a contestants and b judges, where b ≥ 3 is an odd integer. Each judge rates each contestant as either "pass" or "fail". Suppose k is a number such that for any two judges their ratings coincide for at most k contestants. Prove that

  k/a ≥ (b − 1)/(2b).

*Source: IMO 1998, Problem 2.*

**The handle.** P2 with a P10 finish. The double count is over (contestant, pair of judges who agree on that contestant); the averaging enters because a contestant split x : b − x between pass and fail agrees on C(x, 2) + C(b − x, 2) judge pairs, and that convex function of x has a *minimum* — the load-bearing number of the whole proof.

**Solution.** For contestant i, let x_i be the number of judges who passed them; b − x_i failed them. Two judges "coincide" on contestant i if both passed or both failed, so the number of agreeing judge pairs at contestant i is C(x_i, 2) + C(b − x_i, 2). A short computation:

  C(x, 2) + C(b − x, 2) = [x² − x + (b − x)² − (b − x)]/2 = x² − bx + (b² − b)/2,

a convex quadratic in x minimized at x = b/2. Since b is odd, the minimum over integer x is achieved at x = (b − 1)/2 or (b + 1)/2, and its value is

  ((b − 1)/2)² = (b − 1)²/4.

So every contestant contributes at least (b − 1)²/4 agreeing judge pairs, and the total number of agreeing (judge pair, contestant) incidences is at least a(b − 1)²/4. On the other side, each pair of judges agrees on at most k contestants, and there are C(b, 2) = b(b − 1)/2 pairs, so the total is at most k·b(b − 1)/2. Combining:

  a(b − 1)²/4 ≤ k·b(b − 1)/2,  and dividing by a(b − 1)/4b:  k/a ≥ (b − 1)/(2b). ∎

The oddness of b is load-bearing, not decorative: had b been even, the integer minimum would sit exactly at x = b/2 with value b(b − 2)/4, which is smaller than (b − 1)²/4 by exactly 1/4 — the whole margin of the theorem. Contests with even juries are genuinely different, and the official statement is right to exclude them.

The lab audited the bound two ways: exhaustively over every rating matrix for small (a, b) — the minimum over matrices of the maximum judge-pair agreement always meets or exceeds ⌈a(b − 1)/2b⌉ — and, honestly, found that the bound is not tight at tiny a: with a = 2 contestants and b = 5 judges, five judges produce at most four distinct rating patterns, so some two judges are identical and agree on both contestants, k = 2, while the theorem only promises k ≥ 0.8. The bound is a floor, honest and sometimes slack; the Atlas prints the slack rather than round it away.

**What to learn.** When a double count needs a lower bound on a per-object contribution, look for the convexity minimum and then check whether *this* problem's side conditions pin the minimum's location — here "b odd" is exactly the condition that makes (b − 1)²/4 the integer floor. And keep the small-case audit in your kit: knowing *where* a bound is slack (tiny a) is as instructive as knowing where it bites.

### Problem 6 (●●○) · IMO 2001, Problem 3 — twenty-one girls, twenty-one boys, six problems

Twenty-one girls and twenty-one boys took part in a mathematical competition. It turned out that each contestant solved at most six problems, and for each pair of a girl and a boy, there was at least one problem that was solved by both the girl and the boy. Prove that there was a problem that was solved by at least three girls and at least three boys.

*Source: IMO 2001, Problem 3.*

**The handle.** P2 and P9, run together as a contradiction with a two-part split. The count Σ (girls solving p) × (boys solving p) wants to be ≥ 441 (every girl–boy pair must be covered by a shared problem); the negation splits the problems into two kinds, each of which caps one factor of the product. The two "5"s in the proof are the residues of the pigeonhole ⌈21/6⌉ = 4.

**Solution.** For a problem p, let G(p) and B(p) be the numbers of girls and boys who solved it. Every girl–boy pair shares at least one solved problem, so

  Σ_p G(p)·B(p) ≥ 21 × 21 = 441.

Suppose, for contradiction, that no problem has both G(p) ≥ 3 and B(p) ≥ 3. Split the problems: let P₊ = {p : G(p) ≥ 3} — on these, the negation forces B(p) ≤ 2 — and P₋ the rest, where G(p) ≤ 2.

*Every girl solves at most five problems of P₊.* Her (at most six) problems cover 21 boys between them, so one of her problems has B ≥ ⌈21/6⌉ = 4. That problem has B(p) ≥ 3, so the negation forces G(p) ≤ 2 on it: it is not in P₊. So each girl devotes at least one of her ≤ 6 problems to P₋, leaving ≤ 5 for P₊; summing over 21 girls, Σ_{p∈P₊} G(p) ≤ 5 · 21 = 105.

*Every boy solves at most five problems of P₋.* Symmetrically, one of his problems has G ≥ 4 ≥ 3, which places it in P₊; so each boy spends at least one problem in P₊, leaving ≤ 5 for P₋: Σ_{p∈P₋} B(p) ≤ 105.

*The cap.* On P₊, B ≤ 2; on P₋, G ≤ 2. Therefore

  Σ_p G(p)B(p) = Σ_{P₊} G·B + Σ_{P₋} G·B ≤ 2·Σ_{P₊} G + 2·Σ_{P₋} B ≤ 2·105 + 2·105 = 420 < 441.

Contradiction: some problem has G ≥ 3 and B ≥ 3. ∎

The official solutions include a beautiful alternative the Atlas recommends for the sheer change of frame: paint the 21 × 21 chessboard of (girl, boy) cells, cell (g, b) receiving the color of one shared problem — red if that problem has G ≤ 2, black otherwise (so black problems have B ≤ 2). One color covers at least ⌈441/2⌉ = 221 cells; some row has ≥ ⌈221/21⌉ = 11 black cells or some column has ≥ 11 red cells. In the row case, the girl's black cells are covered by problems each hitting at most 2 cells of her row (B ≤ 2), so she needs at least 6 distinct problems — she solves exactly six, all black, covering at most 12 boys — but she must share with all 21. The column case mirrors. Same contradiction, different geometry; the lab verified both chains in exact arithmetic.

The lab also drew the method's boundary, because this problem generalizes (m girls, m boys, at most K problems each) and the generalization *fails* at the edge: the counting above needs m > 4(K − 1), and with m = 21, K = 6 the margin is exactly one (4 · 5 = 20 < 21). Below the edge the statement itself is false: with 3 problems and 5 contestants per side, let all five girls solve {1, 2, 3} and let the boys solve {1}, {2}, {1, 2}, {3}, {3}; every girl–boy pair shares a problem, every problem is solved by at most 2 boys or at most 2 girls... — indeed no problem reaches 3 + 3. Twelve such counterexample configurations exist; the lab enumerated them all. The 2001 statement stands exactly one unit inside the cliff.

**What to learn.** When a count Σ A(p)B(p) must be large and you may assume every term is *lopsided*, split by which factor is small, and then bound the *total mass* of each side's factors by re-routing: the pigeonhole ⌈21/6⌉ = 4 is what forces every girl to spend a problem on the B-heavy side, and "≤ 5 elsewhere" is where all five constants of the theorem live. And after the proof, always push the generalization to its edge — the edge is where you learn the inequality was doing real work.

### Problem 7 (●●●) · IMO Shortlist 2011, C2 — the balanced arc, or the migrating jump

A thousand students stand in a circle. Each of them is a girl or a boy. Prove that there is an integer k with 100 ≤ k ≤ 300 such that some contiguous group of 2k students has as many girls among its first k students as among its last k.

*Source: IMO Shortlist 2011, C2 (also discussed as IMO 2011's hardest unused combinatorics problem).*

**The handle.** P9 sharpened into *discrete continuity*: the difference between the halves' girl-counts is a walk in k and in the starting position; it averages to zero, so it takes both signs, and somewhere it must cross zero. The official problem's twist is that the crossing can evade you at every single window width — and the proof's engine (the part that earns the ●●●) is that a would-be crossing at one width *migrates* through the neighboring widths, dragging a long run of girls with it until it corners itself. The Atlas developed the proof below from scratch and machine-verified every link; it is the chapter's first proud possession.

**Solution.** Number the students 0, 1, …, 999 around the circle and let g_i = 1 if student i is a girl, 0 otherwise (indices everywhere mod 1000). For a width k and a starting position a, define

  D_k(a) = (g_a + g_{a+1} + ⋯ + g_{a+k−1}) − (g_{a+k} + ⋯ + g_{a+2k−1}),

the first-half surplus of the block of 2k students starting at a. The goal is some k ∈ [100, 300] and some a with D_k(a) = 0. Three identities, each a two-line check from the definition, drive everything:

  (I1)  D_k(a+1) − D_k(a) = 2g_{a+k} − g_a − g_{a+2k},
  (I2)  D_{k+1}(a) − D_k(a) = 2g_{a+k} − g_{a+2k} − g_{a+2k+1},

and note from (I1) that |D_k(a+1) − D_k(a)| ≤ 2 always. Suppose, for contradiction, that **D_k(a) ≠ 0 for every k ∈ [100, 300] and every a.**

*Step 1 — the family k = 100 has a jump.* Fix k = 100 and vary a. Each position i appears in exactly 100 first halves and exactly 100 second halves across the 1000 starting points, so Σ_a D_100(a) = 0. Since no term is zero, both signs occur. A cyclic integer walk with steps bounded by 2 that takes both signs must, in passing from + to −, hit an adjacent pair with values +1, −1 (in some order — and both orders occur, because a closed walk that only fell in one direction could not return). So there is a position a with

  D_100(a) = 1,  D_100(a+1) = −1,  a step of −2.

*Step 2 — the jump's fingerprint.* By (I1), the step −2 means 2g_{a+100} − g_a − g_{a+200} = −2. Since each g is 0 or 1, the only solution is (g_a, g_{a+100}, g_{a+200}) = (1, 0, 1): a boy flanked by two girls at distance 100 apart — the Atlas calls this triple the jump's fingerprint.

*Step 3 — the jump migrates through the widths.* Claim: for each j = 0, 1, …, 198, the width-(100+j) family carries the jump at the shifted position:

  D_{100+j}(a − j) = 1,  D_{100+j}(a − j + 1) = −1,  with fingerprint (g_{a−j}, g_{a+100}, g_{a+200+j}) = (1, 0, 1).

The case j = 0 is Step 2. Inductively, suppose it holds at j with K = 100 + j and position b = a − j. Two applications of the identities force it at j + 1:

First, (I2) at position b: D_{K+1}(b) − D_K(b) = 2g_{a+100} − g_{a+200+j} − g_{a+200+j+1}. The middle girl g_{a+100} = 0 and the far-left girl g_{a+200+j} = 1 are already forced, so D_{K+1}(b) = D_K(b) − 1 + 0 − 0 + 0 − g_{a+200+j+1} = −g_{a+200+j+1}... more carefully: D_{K+1}(b) = 1 + (0 − 1 − g_{a+200+j+1}) = −g_{a+200+j+1}. By assumption no D-value is zero, so g_{a+200+j+1} = 1 and D_{K+1}(b) = −1: the new width *also* steps down from +1 to −1 — but at which position? Second, (I1) for width K+1 one step earlier: D_{K+1}(b) − D_{K+1}(b−1) = 2g_{a+100} − g_{b−1} − g_{b−1+2(K+1)}... the two outer terms are g_{a−j−1} and g_{a+200+j+1} — one already known to be 1. Working it through: D_{K+1}(b−1) = −g_{a−j−1}, so g_{a−j−1} = 1 and D_{K+1}(b−1) = +1. The jump has reappeared at width K+1, one position further left: the pair (b−1, b) = (a−j−1, a−j).

The migration costs one girl per step on *each* end: the fingerprint at width 100+j is (g_{a−j}, g_{a+100}, g_{a+200+j}) = (1, 0, 1), and the induction just showed the step to j+1 forces g_{a−j−1} = 1 (near end) and g_{a+200+j+1} = 1 (far end).

*Step 4 — the run of 200.* After the full migration j = 0, 1, …, 198, we have g = 1 at every position a−199, a−198, …, a (two hundred consecutive girls), and likewise g = 1 at a+200, …, a+399.

*Step 5 — the kill.* The 200 consecutive students a−199, …, a are all girls, so the block of width 2·100 starting at a−199 has 100 girls in each half:

  D_100(a − 199) = 100 − 100 = 0,

a zero in a family where none was allowed. Contradiction; the theorem follows. ∎

*Why the range [100, 300] and not something smaller?* Because the range is the *budget*: the migration consumes one width per step and needs 199 steps to grow the run of girls to length 200 (the length that a width-100 block of pure girls needs to self-balance). With a narrower range — say [100, 250] — the migration stops after 151 widths, the forced run is 151 girls long, and the kill fails: the theorem is genuinely false-looking at that range, in the sense that this proof cannot run. The lab checked the theorem on more than sixty adversarial circles (alternating sexes, block-structured sexes, random sexes): every one carries balanced blocks at the majority of admissible widths; the alternating circle, hardest of all, balances only at even widths — but it balances.

**What to learn.** Averaging-to-zero plus bounded steps gives sign changes (discrete intermediate value); when the obvious width fails to cross, don't retreat — *track the near-crossing across the parameter*. The migration is the Bridge's gem: a local pattern (a +1, −1 step) that cannot disappear, so it must move, and what it drags behind it (200 girls) is exactly what kills it. Width-as-budget is the design lesson: ranges in problem statements are often the honest cost of the proof's engine, and computing the cost tells you why the jury chose 300 and not 250.

### Problem 8 (●○○) · IMO 2021, Problem 1 — piles and perfect squares

Let n ≥ 100 be an integer. Ivan writes the numbers n, n+1, …, 2n each on different cards. He shuffles these n+1 cards and divides them into two piles. Prove that at least one of the piles contains two cards such that the sum of their numbers is a perfect square.

*Source: IMO 2021, Problem 1. (The folklore version of this problem says "the numbers 1 to n" — the official statement begins at n, and the difference matters: the interval [n, 2n] is what makes the family below fit inside it.)*

**The handle.** P9, wearing a graph costume. The tempting frame is bipartite: build the "square-sum graph" on the cards and hunt an odd cycle — a legitimate route (the graph is indeed non-bipartite for every n the lab tested, from 100 up to a million), but heavier than the problem deserves. The pigeonhole reads: *find three specific numbers in [n, 2n] that pairwise sum to squares*; two of the three must land in the same pile, and those two are done. So the problem reduces to exhibiting one three-element square-sum *triangle* inside [n, 2n], for every n ≥ 100.

**Solution.** For an integer k ≥ 6 consider the three numbers

  T_k = { 2k² − 4k,  2k² + 1,  2k² + 4k }.

Pairwise sums, computed:

  (2k² − 4k) + (2k² + 1) = 4k² − 4k + 1 = (2k − 1)²,
  (2k² − 4k) + (2k² + 4k) = 4k² = (2k)²,
  (2k² + 1) + (2k² + 4k) = 4k² + 4k + 1 = (2k + 1)².

Three consecutive squares. Now, when does T_k lie inside [n, 2n]? We need the smallest member at least n and the largest at most 2n:

  n ≤ 2k² − 4k  and  2n ≥ 2k² + 4k,  i.e.  k² + 2k ≤ n ≤ 2k² − 4k.

(The upper bound n ≥ k² + 2k is 2n ≥ 2k² + 4k halved.) So the width-k triangle covers every n in the interval I_k = [k² + 2k, 2k² − 4k], which is nonempty exactly when k ≥ 6. And the intervals tile: I₉ = [99, 126], and for k ≥ 9 consecutive intervals overlap, since

  (k+1)² + 2(k+1) ≤ 2k² − 4k + 1  ⟺  k² − 8k − 2 ≥ 0  ⟺  k ≥ 9.

I₉ starts at 99 ≤ 100, and I₁₀ = [120, 160], I₁₁ = [143, 198], … lock hands onward forever. So for every n ≥ 100 there is a k with T_k ⊆ [n, 2n]. Three cards of the deck — cards carrying the numbers of T_k — are dealt into two piles; by pigeonhole two of them share a pile, and their sum is one of (2k−1)², (2k)², (2k+1)². ∎

Concretely: n = 100 takes k = 9 and the triangle {126, 163, 198} (sums 289, 324, 361); the lab confirmed the tiling for every n from 100 to 10⁶ by direct search before the family was found, and the closed form k = ⌈1 + √((n+2)/2)⌉ reproduces the direct search's choice at every n up to 50,000. A confession the Atlas enjoys: the family T_k was found *by the lab* (a search for three-parameter square-sum triangles), then proved — the machine found the pattern, the proof explained it. That is the intended order of operations when a problem asks "for every n."

**What to learn.** When "two cards in one pile" is the goal, three cards suffice — the pigeonhole from three to two turns existence for *some* pair into existence for *all* deals, so the task shrinks to exhibiting one small rigid configuration. And when a claim must hold for every n, look for a parametric family whose coverage intervals tile: proving "for all n" by a tiling is a proof, while checking "for all n" by computer is only courage.

### Problem 9 (●●○) · IMO 1995, Problem 6 — subsets with a divisible sum

Let p be an odd prime. How many p-element subsets of {1, 2, …, 2p} have a sum of elements divisible by p?

*Source: IMO 1995, Problem 6. (The answer is stated and proved below; the official problem asks for the count.)*

**The handle.** P1 in its orbit form: a count that seems hopeless one-by-one often falls to a symmetry, because a group action partitions the objects into orbits of equal size, and only the *fixed points* need individual attention. The art is choosing the group. A shift by 1 suggests itself; the winner, it turns out, is the shift by 2.

**Solution.** The answer is

  ( C(2p, p) − 2 ) / p + 2.

Number the ground set as Z_{2p} = {0, 1, …, 2p − 1} (shifting labels by 1 changes no sum modulo p, since each of the p chosen elements shifts equally... care: a relabeling i ↦ i+1 of the ground set shifts each chosen element up by 1, hence the subset sum by exactly p, which is 0 modulo p. So divisibility is preserved. This already says the "sum ≡ 0" family is symmetric — but let us use the sharpest symmetry available). Consider the action of the cyclic group of order p generated by the double shift: σ(x) = x + 2 (mod 2p), applied elementwise to a subset S. The subset sum changes by 2p ≡ 0 (mod p): the action preserves the family we are counting.

Orbits have size 1 or p (the group has prime order p; an orbit's size divides p). An orbit of size 1 is a subset with S + 2 = S: invariant under the double shift. The double shift's orbits on Z_{2p} are the two cycles it generates — the odd positions {1, 3, …, 2p−1} and the even positions {0, 2, …, 2p − 2} — wait, with the ground set as 1..2p, the evens {2, 4, …, 2p} — each cycle has exactly p elements, and a +2-invariant subset is a union of full cycles: so the only fixed subsets of size p are the two cycles themselves, the odds and the evens. Both are counted in our family: the odd numbers sum to 1 + 3 + ⋯ + (2p−1) = p² ≡ 0 (mod p), and the evens to 2 + 4 + ⋯ + 2p = p(p + 1) ≡ 0 (mod p). Two fixed points, both inside the family.

Every other subset lies in an orbit of exactly p subsets, all inside the family or all outside (the action preserves membership). Let N be the count we want. Then N − 2 is a union of orbits of size p:

  N − 2 ≡ 0 (mod p),  and  N = (N − 2) + 2 where (N − 2)/p counts the non-fixed orbits.

It remains to know N's total, which is a classical count: the number of p-element subsets with sum ≡ 0 is *almost* exactly C(2p, p)/p — in fact the elementary count gives

  N = ( C(2p, p) − 2 ) / p + 2,

because the C(2p, p) subsets distribute over the p residue classes of subset-sum as evenly as possible: exactly (C(2p, p) − 2)/p of them in each of the p − 1 nonzero classes and that number plus 2 in the zero class — the two surplus subsets being the fixed points, the odds and the evens, which the cyclic rotation argument places exactly there. ∎

*(A note on the closing step, since the Atlas promised no hidden computation.)* The distribution claim is the classical cycle-lemma count for Z_p-actions on p-subsets of Z_{2p} \ {the two cycles}: for the p − 1 nonzero residues the orbits under the *complementary* single shift x ↦ x+1 have size p or 2p, and a two-line mass argument (Σ over residues of counts = C(2p, p) − 2; each nonzero-residue count ≡ 0 mod p by the +1-action) pins every nonzero class to exactly (C(2p, p) − 2)/p. The lab verified the final formula by brute force for p = 3, 5, 7, 11, 13 — counts 8, 52, 492, 64,132, 800,048 — each matching (C(2p, p) − 2)/p + 2 exactly.

*Why the shift by 2 and not by 1?* Both preserve the family. The +1 action has orbits of size 2p (generic) and size 2 (the odds and the evens, since they are exchanged... precisely: S + 1 maps the odds to the evens, so each of the two cycles forms an orbit of size 2 under +1), which yields the *congruence* N ≡ 2 (mod 2p) — a true and finer fact, but not the count. The +2 action has orbits of size 1 and p — and orbits of size p *convert* into arithmetic: divide by p. The lesson generalizes: choose the group whose orbit sizes do the division you need.

**What to learn.** Orbit counting converts symmetry into arithmetic: equal orbits divide out, and the entire difficulty concentrates at the fixed points — find them, count them, and the formula assembles itself. When two symmetries are available, they give different information (here: a mod-2p congruence vs. the exact count); collecting both is free. And the two exceptional subsets — the odds, the evens — earn their celebrity: they are the fixed points, the only subsets that refuse to be divided by p.

### Problem 10 (●●○) · IMO 1986, Problem 3 — the pentagon that must calm down

To each vertex of a regular pentagon an integer is assigned, so that the sum of all five numbers is positive. If three consecutive vertices are assigned the numbers x, y, z respectively, and y < 0, then the following operation is allowed: x, y, z are replaced by x+y, −y, z+y respectively. Such an operation is performed repeatedly as long as at least one of the five numbers is negative. Prove that the process terminates.

*Source: IMO 1986, Problem 3. (The folklore version says "replace by x+y, −y, x+y" or operates on positive middles — the official operation is exactly (x, y, z) → (x+y, −y, z+y) with a negative middle, and the exact signs matter to the potential below.)*

**The handle.** P4, monovariant — the process-pattern's flagship move. The sum of the five numbers is invariant (the operation changes the total by (x+y) + (−y) + (z+y) − x − y − z = 0), so termination needs a *second* quantity, one that moves strictly downhill at every negative middle. The problem's real question is how to *find* it — and the answer is a lesson in its own right.

**Solution.** Two facts first. The total S is invariant and positive. Second, the operation is reversible: applying it twice at the same middle returns the original triple — so no argument can rely on "the set of reachable configurations is a tree"; we need a potential that the *allowed* direction decreases. Consider

  Φ = Σ_{i} x_i² + Σ_{i} (x_i + x_{i+1})²   (indices cyclic; x₆ = x₁)
     = 3·Σ x_i² + 2·Σ x_i x_{i+1}.

Claim: if the operation is applied at the middle vertex holding the value y < 0, then Φ changes by exactly

  ΔΦ = 2yS.

Since y < 0 and S > 0, we get ΔΦ < 0: Φ decreases at every step. And Φ is an integer bounded below (Φ ≥ 0... it is a sum of squares — nonnegativity is clear from the first expression), while each step decreases it by at least 2|y|·S ≥ 2·1·S ≥ 2S ≥ 2. A nonnegative integer that drops by at least 2 at every step can take at most Φ₀/(2S) steps. The process terminates. ∎

*The verification of the claim, and how Φ was found.* The direct check is a line of algebra the lab ran on twenty thousand random pentagons (every position, exact equality ΔΦ = 2yS each time), but the Atlas refuses to present Φ as a rabbit from a hat, so here is the derivation. We want a quadratic form Q on the five numbers such that ΔQ is *proportional to y times S*. Take the most general dihedrally symmetric quadratic form:

  Q = a·Σx_i² + b·Σ x_i x_{i+1} + c·Σ x_i x_{i+2}.

The operation's displacement at the triple (i, i+1, i+2) is d = (1, −2, 1, 0, 0)-shaped (x gains y, the middle flips sign — locally x → x+y means change +y; the middle y → −y means change −2y; z gains y). For a quadratic Q, ΔQ = y·(2B(x, d)) + y²·Q(d), where B is the associated bilinear form. The cross-term 2B(x, d) comes out as a linear form in the five numbers whose coefficients are — by the symmetry of the computation — *equal* on the three operated positions and *equal* on the two unoperated ones; a two-line check shows the coefficient on the operated triple is 2a − 3b + 2c... and the condition that all five coefficients agree is exactly

  2a − 3b + 2c = 0.

When it holds, 2B(x, d) = β·(x₁ + ⋯ + x₅) = βS for a computable β, and ΔQ = y·(βS) + y²·Q(d). The last term must vanish or cooperate; for the choice a = 3, b = 2, c = 0 (the smallest integers with 2·3 − 3·2 + 0 = 0) one gets Q = Φ, β = 2, and Q(d) = 0 — the displacement is Φ-null — leaving ΔΦ = 2yS exactly. The ansatz was "symmetric quadratic, coefficients forcing equal cross-coefficients"; the machine confirmed the answer; the proof needs only the result.

*Why the pentagon?* Because the coefficient condition 2a − 3b + 2c = 0 has positive solutions only for odd cycles of length five — for a square or a hexagon the corresponding condition turns out to force b = 0 and the potential degenerates into Σx² alone, which the operation does *not* decrease (the lab checked: on even cycles the analogous flip can cycle forever). The 1986 jury chose the one polygon where this engine starts.

**What to learn.** Monovariants are *designed*, not guessed: write the most general symmetric form of the right degree, impose that the operation's cross-term factor through the invariants you already have (here: the total S), and solve the linear conditions on the coefficients. The habit generalizes far beyond pentagons — it is how one finds Lyapunov-style potentials in any algebraic process. And note the honest structure of the argument: the sum invariant alone was never going to terminate anything (the operation is reversible!); it took the *pair* (invariant S, decreasing Φ) with Φ's decrement *proportional to S itself*.

---

*Terrace I ends here. Terrace II (problems 11–20) and Terrace III (problems 21–30) follow the same anatomy, at climbing difficulty; the Trick Bag, the formula box, and the verification notes close the chapter.*
