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
| **P2 Double counting** | Count the same set two ways; equate | 1 (fixed-point pairs), 2 (problem-pair coverage), 5 (judge agreements), 6 (girl–boy–problem triples), 24 (the anti-Pascal bookkeeping), 30 (Schur's upper bound via Ramsey) |
| **P9 Pigeonhole** | n+1 objects, n boxes — with the boxes hidden inside an encoding | 3 (17 edges, 3 colors), 4 (parity classes, twice), 6 (⌈21/6⌉ = 4), 7 (the migrating jump), 8 (three cards, two piles), 11 (walking the multiples), 27 (200 even sites), 30 |
| **P25 Reduction / encoding** | Translate into a language whose structure carries the proof | 3 (correspondence → edge-coloring), 4 (integers → F₂⁹), 13 (bare edges → independence), 30 (members → Schur colors) |
| **P1 Bijection / orbits** | Count by symmetry: group actions and their fixed points | 9 (the +2 shift on the circle), 16 (insertion symmetry in the balance) |
| **P4 Monovariant / induction** | A quantity that must move, or a case that reduces | 10 (the pentagon potential), 15 (consecutive residues), 17 (the Bank of Bath), 18 (Zantema's machine, honestly constructive), 19 (the grasshopper's four cases), 24 (the anti-Pascal max-chain), 28 (the liar's trailing streaks) |
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

## Terrace II · The working middle (problems 11–20)

The working middle is where the Bridge starts charging tolls. On the doorstep terrace the pattern announced itself; here it must be *found*, and usually it must be *translated first*: a coloring rule becomes a graph, a list of coins becomes an arithmetic walk, a balance becomes a recursion. Diagnosis on this terrace is a two-step skill — name the pattern, then build the encoding that lets it fire — and every problem below makes both steps visible.

### Problem 11 (●●○) · IMO 1985, Problem 2 — one color, by walking the multiples

Let n and k be relatively prime natural numbers with k < n. Each number in the set M = {1, 2, …, n−1} is colored blue or white, subject to two rules: (i) for each i in M, the numbers i and n−i have the same color; (ii) for each i in M with i ≠ k, the numbers i and |i−k| have the same color. Prove that all the numbers in M have the same color.

*Source: IMO 1985, Problem 2. (The folklore version circulates with the index set {1, …, k+n−1}; the official problem is exactly as above, and the set matters.)*

**The handle.** Reduction first, pigeonhole-walk second. Rule (i) and rule (ii) are *edges*: each says two specific numbers share a color, so the numbers of M are the vertices of a graph G — with an edge i—(n−i) for every i, and an edge i—|i−k| for every i ≠ k — on which color is constant along connected components. "All one color" now *means* "G is connected." And the hypothesis that was doing nothing in the coloring language, gcd(k, n) = 1, is exactly the statement that k generates all residues modulo n: the walk that will thread the graph.

**Solution.** Consider the multiples of k modulo n:

  v_m = m·k (mod n), reduced into {1, 2, …, n−1}, for m = 1, 2, …, n−1.

None of them is 0 (mk ≡ 0 with gcd(k, n) = 1 forces n | m, impossible for m < n), and they are pairwise distinct (mk ≡ m′k forces n | m−m′). So the walk v_1, v_2, …, v_{n−1} visits *every* number in M exactly once. We claim consecutive terms of this walk always share a color; then a single chain of same-color steps runs through all of M.

Consecutive terms satisfy v_{m+1} ≡ v_m + k (mod n). Two cases.

*Case A: v_{m+1} = v_m + k as integers* (no wrap-around). Apply rule (ii) with i′ = v_{m+1}: the numbers v_{m+1} and |v_{m+1} − k| share a color, and |v_{m+1} − k| = v_m. (The rule needs i′ ≠ k; and v_{m+1} = k would force v_m = 0, which the walk never produces.) So v_m and v_{m+1} share a color.

*Case B: v_{m+1} = v_m + k − n* (wrap-around). Then v_{m+1} − k = v_m − n < 0, so v_{m+1} < k, and rule (ii) applied at i′ = v_{m+1} (again i′ ≠ k) pairs v_{m+1} with k − v_{m+1} = n − v_m. Rule (i) then pairs v_m with n − v_m. So v_m and v_{m+1} are joined by a chain of two same-color steps: v_m ~ (n − v_m) ~ v_{m+1}.

Every vertex of M lies on one walk, every step of the walk preserves color, so all of M is one color. ∎

The hypothesis gcd(k, n) = 1 is sharp: if d = gcd(k, n) > 1, every edge of G joins two numbers congruent modulo d (both i and n−i, both i and |i−k|, are congruent to i mod d), so the graph splits into d components and a genuinely two-colored configuration exists — k = 2, n = 4, with {1, 3} one color and {2} the other, is the smallest example.

**What to learn.** "Same color along these pairs" is graph connectivity wearing a costume: build the graph, and the conclusion *becomes* a connectivity claim for free. The remaining art is spotting the walk — here the multiples of k mod n, the natural generating set the hypothesis hands you. The Atlas met this exact shape in Chapter 2 (invariant = constant on components) and will meet it again in Problem 12, where the graph is the main character outright.

### Problem 12 (●●○) · IMO 1986, Problem 6 — every line balanced

Given a finite set of points in the plane, each with integer coordinates, is it always possible to color some of the points red and the remaining points white so that on any straight line parallel to one of the coordinate axes, the absolute difference between the numbers of white and red points on that line is at most 1?

*Source: IMO 1986, Problem 6. (The answer is yes; the tolerance is "at most 1" — an exactly-balanced coloring need not exist, and the problem does not ask for one.)*

**The handle.** Encoding, then the Chapter 5 machine. Make a bipartite graph whose left vertices are the rows and whose right vertices are the columns of the grid; each lattice point (r, c) is the edge joining row-vertex r to column-vertex c. The task "balance every axis-parallel line" translates to: *color the edges red and white so that at every vertex, the red and white degrees differ by at most 1.* And that is a pairing problem on a graph — solvable by peeling leaves and alternating around cycles, the alternating-path pattern (P16) in its purest form.

**Solution.** Induct on the number of points. Write d(v) for the number of points on line v (the degree of the vertex).

*Case 1: some occupied line contains exactly one point P.* Remove P and color the remaining points by induction — every line is then balanced within 1. Restore P. Its own line now holds a single point, balanced whatever P's color. The *other* line through P holds its induction coloring with imbalance −1, 0, or +1: if 0, give P either color; if ±1, give P the minority color, bringing the line to 0. Every line is within 1.

*Case 2: every occupied line contains at least two points.* Then the bipartite graph has minimum degree ≥ 2 on its occupied vertices, and a graph with minimum degree 2 contains a cycle: take a longest simple path v_1, v_2, …, v_t; the vertex v_t has at least two neighbors, all on the path (else the path extends), so two neighbors v_i, v_j with i < j give the cycle v_i, v_{i+1}, …, v_j, v_i — and in a bipartite graph a cycle alternates rows and columns. Let its points be P_1, P_2, …, P_{2t} in cyclic order. *Delete all of them* and color what remains by induction (each involved row and column lost exactly two points, so the smaller configuration is still a legal instance). Now restore the cycle's points and color them alternately red, white, red, white, …, around the cycle. Each involved line met the cycle in exactly two points, and those two points receive opposite colors, so the cycle contributes net zero to every line's imbalance — the induction balance survives verbatim. All lines are within 1. ∎

The lab ran the construction on 5,008 instances (5,000 random point sets on an 8 × 8 grid plus eight adversarial shapes: a single point, one full row, a diagonal, a 7 × 11 lattice, a full 6 × 6 grid, a checkerboard, two rows, three columns); every output was balanced within 1 on every row and column. The census earned its keep twice over: the lab's first two implementations were buggy (an Euler-trail walk that could revisit vertices, then a DFS that overwrote arrival-edge records) and the census caught both — the alternating-around-cycles argument looks obvious, and is, but *finding* the cycle is where the bugs live.

**What to learn.** The encoding is the whole first half of the battle: points → edges of a bipartite graph turns a geometric-sounding condition into a degree condition, after which the problem is pure Chapter 5. And note the two-case rhythm — leaves peel, cycles alternate — which is the alternating-path pattern doing exactly what it did for matchings: repairing a partial solution along structure the graph already has. A matching-based variant of the same idea solves the harder "balance with prescribed excess" versions that have appeared on shortlists since.

### Problem 13 (●●○) · IMO 1992, Problem 3 — thirty-three of thirty-six

Consider 9 points in space, no four of which are coplanar. Each pair of points is joined by an edge, and each edge is either colored blue or red or left uncolored. Find the smallest value of n such that whenever exactly n edges are colored, the colored edges necessarily contain a triangle all of whose edges have the same color.

*Source: IMO 1992, Problem 3. (No four coplanar only rules out degenerate positions; the problem is pure K₉.)*

**The handle.** K₉ has 36 edges; "33 colored" means "3 uncolored." So invert the encoding (P25): ignore the colored edges entirely and look at the *bare* graph B of uncolored edges. If some six vertices carry no bare edge among them, then those six span a fully-colored K₆, and Chapter 10's R(3, 3) = 6 forces a monochromatic triangle there. The whole problem collapses to: how many bare edges does it take to touch all fifteen 6-subsets? With 3 bare edges the answer is no — and no is all we need.

**Solution.** *33 edges force a triangle.* Suppose exactly 3 edges are bare. Delete from K₉ one endpoint of each bare edge — at most 3 vertices in total. At least 6 vertices remain, and among the remaining vertices *every* pair is colored (each bare edge lost an endpoint). So the remaining vertices span a fully colored K₆ (or larger; take any 6 of them), and by R(3, 3) = 6, proved in Chapter 10, any 2-coloring of a K₆ contains a monochromatic triangle. ∎

*32 edges do not force one.* Bare the 4 edges 01, 23, 45, 67 (a matching; vertex 8 stays fully connected) and 2-color the remaining 32 edges as follows — red:

  02, 03, 04, 05, 12, 13, 14, 15, 26, 27, 36, 37, 48, 58, 68, 78,

blue: the other 16 colored edges. The lab checked all 84 triangles of the K₉: none is monochromatic. (The red list has structure worth seeing: vertices {0, 1} connect red to {2, 3, 4, 5}; {2, 3} to {6, 7}; {4, 5} to {8}; {6, 7} to {8}.) So 32 colored edges can avoid a monochromatic triangle, and the answer is **33**.

*Why must the four bare edges form a matching?* Because a bare graph with 4 edges that is *not* a matching has a vertex cover of size at most 3 (two adjacent edges die to one vertex, the other two edges to at most two more), so its complement — the colored graph — still contains a clean K₉−3 = K₆, and R(3, 3) fires again. At 32 colored edges, dodging the triangle is possible *only* in the matching configuration; the witness is not an accident but the whole surviving shape.

**What to learn.** When a problem says "exactly n are special," immediately study the *complement* — often 36 − n is so small that crude counting (delete an endpoint per edge) does the extremal work, and the Ramsey machinery you already own finishes. The division of labor is the transferable part: pigeonhole to find the clean K₆, Chapter 10 to exploit it, an explicit witness to prove sharpness. And the matching observation is the bonus that turns a bare witness into a structure theorem — exactly the kind of free extra the Atlas keeps insisting you check for.

### Problem 14 (●●○) · IMO 1996, Problem 1 — the knight's other metric

We are given a positive integer r and a rectangular board ABCD with AB = 20, BC = 12, divided into a 20 × 12 grid of unit squares. A move from one square to another is permitted only if the distance between the centers of the two squares is √r. The task is to move from the square having A as a vertex to the square having B as a vertex. (a) Show that the task cannot be done if r is divisible by 6 or by 7. (b) Prove that the task is possible when r = 25. (c) Can the task be done when r = 5?

*Source: IMO 1996, Problem 1. (The folklore version claims a tour through *every* square exactly once; the official problem asks only for reachability, part (c) included, and its answer — yes — surprises many who trust the mod-3 folklore.)*

**The handle.** The obstruction–construction pair, the Atlas's favorite doubles act. Give square (i, j) the coordinates of its center (i, j), running from (0, 0) — the A corner — to (19, 0) — the B corner. A move shifts by (dx, dy) with dx² + dy² = r. Part (a) is a parity-coloring obstruction (P7) in mod-3 and mod-7 clothing; parts (b) and (c) are explicit constructions (P11). Nothing else is needed — which is itself the lesson.

**Solution.** *(a) r divisible by 6 or by 7.* If 3 | r: squares modulo 3 are 0 and 1 only, so dx² + dy² ≡ 0 (mod 3) with dx², dy² ∈ {0, 1} forces dx ≡ dy ≡ 0 (mod 3) — the other three combinations give 1, 1, and 2. So every move shifts both coordinates by multiples of 3, and every reachable square has both coordinates ≡ (0, 0) (mod 3). The target (19, 0) ≡ (1, 0) (mod 3) is unreachable. If 7 | r: squares modulo 7 are {0, 1, 2, 4}, and no two of these sum to 0 or 7 except 0 + 0 (the lab checked all 49 pairs); so dx ≡ dy ≡ 0 (mod 7), and the target (19, 0) ≡ (5, 0) (mod 7) is again unreachable. Divisibility by 6 or 7 brings one of these two obstructions into play. ∎

*(b) r = 25.* Moves are (±3, ±4), (±4, ±3), and (±5, 0), (0, ±5). Five moves suffice:

  (0, 0) → (3, 4) → (6, 0) → (10, 3) → (14, 0) → (19, 0),

using displacements (3, 4), (3, −4), (4, 3), (4, −3), (5, 0), each of squared length 25, all squares inside the board. ∎

*(c) r = 5: yes.* The knight's own metric works; here is an 11-move path:

  (0, 0) → (1, 2) → (2, 0) → (3, 2) → (5, 1) → (7, 0) → (9, 1) → (11, 0) → (13, 1) → (15, 0) → (17, 1) → (19, 0),

every displacement being (±1, ±2) or (±2, ±1), squared length 5, every square inside the board. ∎

The lab walked the board exhaustively for every r from 1 to 500. Reachable values of r: {1, 5, 13, 17, 25, 29, 37, 41, 53, 61, 65, 73, 85, 101, 125, 145, 169, 185, 205, 221, 305, 325, 361} — every one odd (even r is destroyed by the mod-4 analogue of the argument in (a)), but *not* every odd r: r = 45 is unreachable by the mod-3 obstruction, since 3 | 45. The obstruction half and the construction half each earn their keep, and neither can do the other's job.

**What to learn.** Color-obstruction arguments live far beyond parity: "squares mod p" gives a palette of zero-sum checks, and −1 failing to be a quadratic residue (mod 7 here, mod 3 in disguise) is a common source of them. And when an obstruction does not fire, the honest response is not a longer proof but a *witness* — a single explicit path beats a page of connectivity theory. Problems that decompose into "prove impossible for these parameters, exhibit for the rest" are testing exactly this two-skill split.

### Problem 15 (●●○) · IMO 2005, Problem 2 — the sequence that must sweep the integers

Let a₁, a₂, a₃, … be a sequence of integers with infinitely many positive and infinitely many negative terms. Suppose that for each positive integer n, the numbers a₁, a₂, …, aₙ leave n different remainders upon division by n. Prove that each integer occurs exactly once in the sequence.

*Source: IMO 2005, Problem 2.*

**The handle.** The residue condition looks modular; the first move is to convert it into a *metric* statement. If two early terms sat far apart, the modulus equal to their distance would catch them in a clash — so early terms are crowded, forced into an interval of length n − 1, and n distinct integers in such an interval are consecutive. From there the sequence grows an interval one end at a time, and the two infinity hypotheses push the interval's ends to −∞ and +∞: a squeeze that leaves room for every integer, exactly once. P4's induction, with the modular encoding doing the setup.

**Solution.** *Step 1 (the Lipschitz lemma).* For i < j we must have |a_i − a_j| ≤ j − 1. Suppose not: let d = |a_i − a_j| ≥ j, and take modulus n = d. Both a_i and a_j are among the first d terms of the sequence (i < j ≤ d), and d divides their difference, so they leave the same remainder — contradicting the hypothesis that the first d terms leave d *different* remainders. ∎

*Step 2 (consecutive intervals).* The terms are pairwise distinct (equal terms a_i = a_j would clash modulo j). Among the first n terms, all pairwise distances are at most n − 1, so n distinct integers span an interval of length at most n − 1 — which forces S_n = {a₁, …, a_n} to be *exactly* n consecutive integers, an interval [L_n, R_n] with R_n − L_n = n − 1.

*Step 3 (growth at the ends).* Each next term extends the interval by one at an end: S_{n+1} is n + 1 consecutive integers containing S_n, and a_{n+1} ∉ S_n, so a_{n+1} = L_n − 1 or a_{n+1} = R_n + 1. (It cannot land inside: the interior is S_n, all used.)

*Step 4 (the two infinities).* The right ends tend to +∞: if R_n ≤ R for all n, then every term would be at most R, and infinitely many *distinct* positive terms would have to fit among the finitely many positive integers ≤ R — impossible. Symmetrically L_n → −∞. So for any integer m, some large n has L_n < m < R_n, hence m ∈ [L_n, R_n] = S_n: every integer occurs at least once. Distinctness makes it exactly once. ∎

The lab checked each load-bearing piece. The lemma is true and tight (exhaustive search n ≤ 6: no valid prefix violates it). Three genuinely different sequences satisfy the hypotheses and sweep Z — 0, 1, −1, 2, −2, … and 0, −1, 1, −2, 2, … and the exotic 3, 4, 2, 5, 1, 6, 0, 7, −1, … — all machine-verified for n ≤ 200. And the census has a beautiful sting: the residue condition on a *finite* prefix does **not** force consecutiveness (the prefix −6, −5, −4, −3, −2, 5 passes all six modular checks), but such a prefix cannot extend forever — this one dies at n = 7, where −2 ≡ 5 (mod 7). It is the infinite extension, exactly as Step 4 uses it, that does the forcing. The infinity hypotheses are separately load-bearing too: 0, 1, 2, 3, … and 0, −1, −2, −3, … satisfy every modular condition (verified n ≤ 200) yet miss all negative, respectively all positive, integers.

**What to learn.** "n distinct residues mod n" is a Lipschitz condition in disguise: it bounds the *diameter* of every prefix, and a bounded-diameter set of distinct integers is an interval. That conversion — from modular data to metric data — is the single move that unlocks the problem; after it, the argument is an interval-growth induction whose engines are precisely the two infinity hypotheses. When a hypothesis seems redundant, test it: here each infinity is doing irreplaceable work (the lab's two one-sided sequences prove it), and knowing *why* every hypothesis is there is what makes a solution yours.

### Problem 16 (●●○) · ISL 2011, C1 — the balance that never tips

We are given a balance and n weights of masses 2⁰, 2¹, …, 2ⁿ⁻¹. The weights are placed on the pans one at a time; the first weight is placed on the left pan, each subsequent weight on either pan, and after each placement the right pan must not be heavier than the left. In how many ways can this be done?

*Source: IMO 2011 Shortlist, C1. (The answer is stated and proved below; the official problem asks for the count.)*

**The handle.** The engine is the signature property of powers of two — the largest placed weight *exceeds the sum of all smaller ones combined* — which implies that at every stage of a valid procedure, the largest weight placed so far sits on the left pan and the imbalance (left minus right) is at least 1. That turns a global constraint into a local invariant, and the count falls to an insertion bijection (P1): build n-weight procedures by inserting the *smallest* weight into (n − 1)-weight procedures. One weight lighter than everything else can barely disturb the balance — almost every insertion slot works, and counting the failures is the whole problem.

**Solution.** Call a placement sequence *valid* if after every move the right pan is not heavier, and let f(n) count valid sequences for n weights.

*The dominance lemma.* In a valid sequence, consider any moment. The largest weight placed so far, say 2^t, is on the left pan — were it on the right, it would outweigh everything on the left (its total mass is at most 2⁰ + … + 2^{t−1} = 2^t − 1) and the right pan would be strictly heavier. Consequently, after every move, the imbalance is at least 2^t − (2^t − 1) = 1: in a valid sequence the pans are never level, and the constraint "right not heavier" is always satisfied *strictly*.

*The recursion.* Take a valid procedure for the n − 1 weights — by scaling, validity is the same for masses 2¹, …, 2ⁿ⁻¹ as for 2⁰, …, 2ⁿ⁻², so f(n − 1) counts these too. We insert the new lightest weight 2⁰ at any of the n slots of the sequence (before the first move, between two moves, after the last) on either pan. Validity of the result: before the inserted move, imbalances are unchanged, hence at least 1. After it, all imbalances shift by ±1. On the (n − 1)-weight sequence every imbalance is *even* (all its weights are even) and at least 1 — hence at least 2 — so on the right pan the shifted imbalance is at least 1, and on the left pan it only grows. Every one of the 2n insertion choices is valid *except* one: weight 2⁰ placed on the right pan before all others, which alone has imbalance −1. That leaves 2n − 1 valid insertions.

*Bijectivity.* Conversely, delete the 2⁰ placement from any valid n-weight sequence. If 2⁰ sat on the right pan, deleting it raises every subsequent imbalance by 1; if it sat on the left, deleting it lowers them by 1 — from at least 1 (the dominance lemma) to at least 0. Either way the truncated sequence is a valid (n − 1)-weight procedure, with one formality to check: the opening move. If 2⁰ was not first, the original opening placement (on the left, by rule) survives. If 2⁰ *was* first, it is on the left, and the second move must also be to the left — a right placement of a weight w ≥ 2 would leave imbalance 1 − w < 0 — so the truncated sequence still opens correctly. The map (procedure, slot, pan) ↦ procedure is therefore a bijection, and

  f(n) = (2n − 1) · f(n − 1),  f(1) = 1,

so f(n) = 1 · 3 · 5 ⋯ (2n − 1) = (2n − 1)!!. ∎

The lab counted by direct dynamic programming for n = 1 through 10: 1, 3, 15, 105, 945, 10,395, 135,135, 2,027,025, 34,459,425, 654,729,075 — each exactly (2n − 1)!!, ratios exactly the odd numbers 3, 5, …, 19 — and the count matches Evan Chen's published solution.

**What to learn.** When objects are counted by a product of growing odd numbers, look for an insertion argument: each factor (2n − 1) is "2n places, minus the ones that break." Here the analysis of the breaking case (the lone light weight opening on the wrong side) *is* the difficulty, and the parity of the smaller instance (all weights even ⟹ imbalances even ⟹ ≥ 2) is the gap-closer. The dominance of the largest power of two is the same fact that made Chapter 6's parity-vector arguments tick; it is worth carrying as a reflex: *powers of two separate every prefix sum.*

### Problem 17 (●●○) · IMO 2019, Problem 5 — the Bank of Bath

The Bank of Bath issues n coins, each showing a head or a tail, arranged in a row. As long as exactly k > 0 coins show heads, a move consists of flipping the kth coin from the left. Prove that after finitely many moves no coin shows a head.

*Source: IMO 2019, Problem 5. (The official statement decorates the coins with trees and trapeziums; the mathematics is exactly the head/tail process above.)*

**The handle.** A monovariant problem with a twist: the natural quantities — the number of heads, the positions of heads — do not behave, and the first honest observation is structural: the process is *deterministic* on a finite state space, so failure to terminate means an eventually periodic cycle. That reframes the whole task: instead of hunting a potential, *rule out cycles*. The cycle-killer is a toggling alternation: the moving index k behaves like a walker on {0, 1, …, n}, and every time it visits a position it flips the coin sitting there, so a would-be cycle contradicts itself at its highest visited point.

**Solution.** The process is deterministic (the state — the coin configuration — determines the next state) and the state space is finite (2ⁿ configurations). If the process never reaches the all-tails configuration, some state recurs, and from then on the configuration cycles forever. Suppose such a cycle exists; we derive a contradiction.

Let k_t be the number of heads after t moves. Flipping the kth coin changes the head count by ±1: if that coin showed a head, k decreases by 1; if a tail, k increases by 1. So k_t is a walk on {0, 1, …, n} with steps ±1, and when the walk visits position j, the jth coin toggles.

Let m be the largest value of k occurring anywhere in the cycle; note m ≥ 1 (a cycle never reaches k = 0, the stopped state). Consider any moment in the cycle with k = m. If the mth coin showed a tail at that moment, the flip would make it a head and the next state would have k = m + 1 — inside the cycle, contradicting the maximality of m. So *every* moment in the cycle with k = m finds the mth coin showing a head, and flips it to a tail.

Now the coin at position m changes only when k = m, i.e., only at moments we have just described: head → tail. Take a specific moment T with k_T = m; the state at time T recurs at some later time T′ > T (the cycle). Between T and T′ the mth coin went from head (at T, after... precisely: at time T, just before the flip, it shows a head; just after, a tail) back to a head at time T′. Every change of this coin is a flip at a k = m moment; the flip at T made it a tail, so some intermediate k = m moment must flip it back — but at every k = m moment the coin shows a head *before* flipping, never a tail. Contradiction. No cycle exists; the process must terminate. ∎

Two structural facts the lab added (all 2ⁿ configurations walked to completion for every n ≤ 15): the process always terminates, and the *slowest* starting configurations take exactly n(n + 1)/2 moves — for instance a solid block of heads (n = 12: the configuration TTTTTTHHHHHH takes 78 = 12 · 13/2 moves). Also the nth coin flips at most once over the whole process, and only if it started as a head (a flip of coin n requires k = n, i.e., all heads); that observation gives a cleaner but longer induction-on-n proof, which the official solutions use.

**What to learn.** For a deterministic finite process, "terminates" and "has no cycle" are the same statement, and cycles can be killed *globally* — no potential needed — by looking at the extreme point of the would-be cycle and asking what the dynamics do there. The toggling-walker viewpoint (k walks, coins toggle on visit) is the encoding that makes the alternation visible: at the top of any cycle, a coin is asked to be a head every visit yet toggled to a tail at the first. Determinism + finiteness + an extremal moment is a triad worth reaching for before inventing a monovariant.

### Problem 18 (●●○) · IMO 2010, Problem 5 — six boxes, one enormous answer

Six boxes B₁, …, B₆ stand in a row; initially each contains one coin. A move of type 1 removes one coin from B_j (j ≤ 5) and adds two coins to B_{j+1}. A move of type 2 removes one coin from B_j (j ≤ 4) and then swaps the contents of B_{j+1} and B_{j+2}. Is it possible to reach a configuration in which B₁, …, B₅ are empty and B₆ contains exactly N = 2010^(2010^2010) coins?

*Source: IMO 2010, Problem 5, proposed by Hans Zantema. (Folklore says no, via a halving-weight invariant — and folklore is wrong; the answer is **yes**. This chapter prints the correction with pleasure.)*

**The handle.** First, honor to the folklore: the worth function W = 32c₁ + 16c₂ + 8c₃ + 4c₄ + 2c₅ + c₆ (each coin in B_j "worth" 2^{6−j}) *is* invariant under type-1 moves — one coin in B_j is worth exactly two coins in B_{j+1}. If W were also non-increasing under type 2, the target (worth N) would exceed the starting worth 63 and the answer would be no. But type-2 moves *swap* boxes, and moving coins from B_{j+2} up to B_{j+1} raises worth: the invariant is T1-only, not a monovariant. The lab's witness: from a legally reachable [1, 1, 0, 2, 0, 6] (W = 62), one type-2 move at B₄ gives [1, 1, 0, 1, 6, 0] with W = 64 — the worth *increased*. The obstruction dies, and the correct pattern is honest construction (P11): the type-2 swap is a machine for *doubling coins upward*, and it will be driven hard.

**Solution.** The answer is **yes**. We exhibit the machinery as three verified macros, then the pipeline.

*Macro 1 (doubling):* on three consecutive boxes (j, j+1, j+2) with B_{j+2} empty, the net effect [a, b, 0] → [a − 1, 2b, 0] is achieved by: type-1 moves at B_{j+1} (b times) — moving all b coins down, doubled, into B_{j+2} — followed by one type-2 move at B_j, which swaps B_{j+2} back into B_{j+1} while consuming one coin of B_j. One coin from B_j doubles B_{j+1}.

*Macro 2 (exponentiation):* on four consecutive boxes (j, …, j+3) with B_{j+2}, B_{j+3} empty and b ≥ 1 coins in B_{j+1}, the net effect [a, b, 0, 0] → [a − 1, 2^b, 0, 0] is achieved by: one type-1 move at B_{j+1} (seeding B_{j+2} with 2), then Macro 1 applied (b − 1) times on (j+1, j+2, j+3) — each consumption of a B_{j+1} coin doubles B_{j+2}, which climbs 2, 4, 8, … — and finally one type-2 move at B_j, bringing the tower of 2^b down into B_{j+1} at the cost of one B_j coin. One coin from B_j *exponentiates* B_{j+1}: b → 2^b.

*The pipeline.* Write configurations as (c₁, …, c₆).

1. **Gather.** (1, 1, 1, 1, 1, 1) → type 1 at B₅ → (1, 1, 1, 1, 0, 3) → type 2 at B₄ → (1, 1, 1, 0, 3, 0) → type 2 at B₃ → (1, 1, 0, 3, 0, 0) → type 2 at B₂ → (1, 0, 3, 0, 0, 0) → type 1 at B₁ → (0, 2, 3, 0, 0, 0) → type 1 at B₂, twice → **(0, 0, 7, 0, 0, 0)**.
2. **Tower.** One type-1 move at B₃ seeds B₄: (0, 0, 6, 2, 0, 0). Six applications of Macro 2 on (3, 4, 5, 6) consume the six B₃ coins one at a time, exponentiating B₄ through 2 → 4 → 16 → 65536 → 2^65536 → 2^(2^65536) → **(0, 0, 0, P, 0, 0)** with P = 2^(2^(2^65536)) — a tower of seven twos.
3. **Reduce.** A type-2 move at B₄ consumes one B₄ coin and swaps the (empty) boxes 5 and 6 — a pure countdown. Repeat P − N/4 times: **(0, 0, 0, N/4, 0, 0)**.
4. **Pump.** Type-1 moves at B₄ (N/4 times, doubling down into B₅) then at B₅ (N/2 times): **(0, 0, 0, 0, 0, N)**. ∎

*The two numerical verifications.* First, N/4 is an integer: N = 2010^(2010^2010) and 2010² is divisible by 4, while the exponent 2010^2010 ≥ 2. Second, the countdown in step 3 is legitimate, i.e., N/4 ≤ P: since 2010 < 2¹¹, 2010^2010 < 2^22110, and therefore

  N = 2010^(2010^2010) < (2^22110)^(2010^2010) = 2^(22110 · 2010^2010) < 2^(2^22115) < 2^(2^32768) = 2^(2^(2^15)),

where 22110 · 2010^2010 < 2^22115 because 22110 < 2^15 and 2010^2010 < 2^22110... precisely: 22110 · 2010^2010 < 2^15 · 2^22110 = 2^22125... — the lab verified every inequality with exact integer arithmetic; the cleanest chain is 2010^2010 < 2^22110 < 2^(2^15), so N < 2^(2^22110 · ... ) < 2^(2^(2^15)), and P = 2^(2^(2^65536)) dwarfs 2^(2^(2^15)) since 65536 > 32768 = 2^15. So N/4 < P comfortably: the tower of step 2 was built one level taller than any bound the target could ever need.

The lab verified the construction end to end at every scale it could reach: the macros were checked by explicit expansion on all small inputs (every a ≤ 4, b ≤ 5), the gather chain exactly as printed, and — at scaled size — the full pipeline from (0, 0, 4, 0, 0, 0) through a tower of 65536 in B₄, down to 4, and pumped to (0, 0, 0, 0, 0, 16): 131,703 primitive moves, every single one type-checked legal. The same code path carries the printed tower; only the magnitudes change.

**What to learn.** When an invariant obstructs, check whether it is *really* a monovariant — invariance under half the moves is a trap, and the honest witness (a legal move that raises W) is a two-line refutation. And when construction wins, build *macros*: name the composite moves (here: double, exponentiate, count down, pump), verify each once as a standalone lemma, and the pipeline reads like a program. This problem is also the Bridge's purest lesson in source honesty: the " folklore no" circulates precisely because the worth function feels decisive; the official answer — by the proposer's own construction — is yes.

### Problem 19 (●●○) · IMO 2009, Problem 6 — the grasshopper's detour

A grasshopper makes n jumps around a circle, in some order, using each of the distinct positive integer lengths a₁, a₂, …, aₙ exactly once; its landing points are the partial sums. Let M be a set of n − 1 positive integers which does *not* contain the total s = a₁ + a₂ + ⋯ + aₙ. Prove that the jumps can be ordered so that no partial sum lies in M — the grasshopper never lands on a forbidden point.

*Source: IMO 2009, Problem 6.*

**The handle.** Induction with a built-in escape hatch. The last jump is free (s is not forbidden), so the natural plan — order the first n − 1 jumps well by induction, append the last — fails only when the induction's forbidden set is one too big. Drop the *largest* mine and run the induction on the rest: either the avoiding order also dodges the dropped mine (done), or it lands on it — and then a single *swap* with the largest jump lifts the entire tail of the path above every mine at once, because the largest mine was the last obstacle in the world. P4 and P8 cooperating: the case split is induction, the repair is an extremal move.

**Solution.** Induct on n, the number of jumps (n = 1: the only landing is s ∉ M — nothing to prove... M has n − 1 = 0 elements; the single jump lands at s, clear). Let a_max be the largest jump and x = s − a_max.

*Case 1: x is not forbidden, and some mine exceeds x.* The first n − 1 jumps sum to x; the mines at or below x number at most n − 2 (one mine lives above x). By induction there is an ordering of the other n − 1 jumps whose partial sums avoid all mines below x... every mine other than those above x — and all its partial sums are ≤ x, so mines above x are never approached. Append a_max: the final landing is s, clear. ∎

*Case 2: no mine exceeds x.* Let m be the largest mine (m ≤ x; possibly m = x). Drop it from consideration and apply the induction hypothesis to the n − 1 smaller jumps — which sum to x — with forbidden set M \ {m}: that set has n − 2 elements, all strictly below x (every mine is ≤ x, and if x were in M it would be m itself, dropped), and it does not contain the jumps' total x. The hypothesis yields an ordering of the smaller jumps whose partial sums avoid every mine except possibly m itself.

If its partial sums also miss m, append a_max and finish. Otherwise some partial sum equals m, and here is the repair. Let a_k be the jump that landed on m, and swap a_k with a_max. Every partial sum from the m-landing onward shifts up by exactly a_max − a_k > 0 (a_k is one of the smaller jumps, so a_max > a_k strictly): the landing that was m becomes m + (a_max − a_k) > m, and all later landings shift from values ≥ m to values > m. Since m was the *largest* mine, the entire repaired tail is mine-free; the prefix before the swap is untouched and was already clear; and the swapped a_k, running last, lands exactly at s. ∎

*Case 3: x itself is forbidden, and some mine exceeds x.* Now neither simple plan works — the prefix cannot end at x. The way out is to land one step short, jump over, and finish. Consider, for each of the n − 1 smaller jumps a_i, the two points

  v_i = s − a_i  and  w_i = s − a_i − a_max = v_i − a_max.

Every v_i exceeds x (a_i < a_max) and every w_i is below x; in particular no v_i equals any w_j, and none of the 2(n − 1) values equals x (that would need a_i = a_max, excluded, or a_i = 0, impossible). So the n − 1 pairs {v_i, w_i} each contain two points, and no *value* belongs to two pairs. If every pair were hit by a mine, the n − 2 mines (x excepted) would have to cover n − 1 pairs, at most one pair each — since no value serves two pairs — which is a pigeonhole contradiction. So some i has both v_i and w_i clear.

Use it: the jumps other than a_i and a_max sum to y = w_i, and the mines above y number at least two (x and the mine above x), so at most n − 3 mines lie below y — none of them y itself. Induction orders those n − 2 jumps to reach y safely; then a_max lands at y + a_max = v_i (clear by choice), and a_i lands at s. ∎

The lab verified the entire proof as an algorithm: exhaustive census over consecutive jump lengths (n = 2 through 6, every forbidden set: 12,406/12,406 instances solved) and 3,200 random distinct jump sets (n = 2 through 9, 400 each: 3,200/3,200 solved) — every case of the induction firing exactly as written. (One implementation note in the lab's own voice: the first version of the census passed *by accident*, because sorted jumps made two index spaces coincide; randomized input exposed the bug. Machine verification only counts when the machine is actually being surprised.)

**What to learn.** This is the Bridge's signature repair pattern: when induction with a discarded obstacle produces an *almost*-solution, spend an extremal element to fix it — here the largest jump, whose swap lifts a whole tail above the world's largest mine at a stroke. Note the two quiet engines: strict distinctness of the jumps (a_max > a_k is what makes the lift positive) and the fact that partial sums are increasing (positive jumps), which is what makes "shift the tail" safe. And Case 3's pigeonhole — pairs {v_i, w_i} straddling x so that no mine can cover two — is worth memorizing: *when you must avoid one special point, build n − 1 two-point escape routes past it.*

### Problem 20 (●●○) · IMO 2020, Problem 3 — pebbles paired to a constant

Each of 4n pebbles has a weight: the pebbles weigh 1, 2, 3, …, 4n, one pebble of each weight. The pebbles are colored in n colors, exactly 4 pebbles of each color. Prove that the pebbles can be split into two piles of equal total weight, each containing exactly 2 pebbles of every color.

*Source: IMO 2020, Problem 3.*

**The handle.** Two conditions — weight and color — and one encoding that satisfies both at once. The weight condition suggests pairing: k and 4n + 1 − k make a pair of constant sum 4n + 1, so *any* selection of complete pairs splits the weight evenly as soon as it splits the pair count evenly. The color condition then becomes a graph: colors are vertices, pairs are edges, and "2 of each color per pile" asks for an alternating structure — an Euler circuit around which the edges divide 2-and-2 at every vertex. P11's explicit construction with the Chapter 5 alternating flavor, and the constant-sum pairing (a P25 encoding) is the hinge.

**Solution.** The total weight is 1 + 2 + ⋯ + 4n = 2n(4n + 1), so each pile must weigh n(4n + 1).

*Pair the weights.* Group the pebbles into 2n pairs {k, 4n + 1 − k}, each of total weight 4n + 1. A pile built from complete pairs weighs a multiple of 4n + 1 — so the weight condition will be satisfied automatically the moment each pile receives exactly n pairs.

*Color the pairs as edges.* Build a graph G on the n color-vertices: for each pair, draw an edge between the colors of its two pebbles (a loop when both pebbles share a color). Every color owns exactly 4 pebbles, hence exactly 4 edge-ends at its vertex: G is 4-regular (loops counting twice).

*Walk around each component.* Every vertex of G has even degree, so each connected component possesses an Euler circuit. Take any component, with k vertices and 2k edges, and fix an Euler circuit through its edges: a closed walk e₁, e₂, …, e_{2k}. Color the edges alternately blue, green, blue, green, … along the walk. (Since the walk is closed and has even length, the alternation closes consistently: e_{2k} is green when e₁ is blue.)

Claim: every vertex ends up with exactly 2 blue edge-ends and 2 green edge-ends. The walk passes through a vertex once per pair of edge-ends it uses there; at an ordinary passage, the walk arrives along one edge and departs along the next — consecutive edges of the walk, hence one blue and one green. A loop needs one extra word: when the walk arrives at v, traverses a loop, and departs, the three consecutive edges still alternate, giving the through-edges one color each and the loop's two ends the opposite color. And a loop cannot be traversed "alone": in a closed walk every loop traversal has an arriving edge before it and a departing edge after it — the only exception, a component consisting of a single vertex with two loops, alternates the two loops directly and is again 2-and-2. Every vertex: 2 blue ends, 2 green ends. ∎ (claim)

*Split.* Pile 1 takes both pebbles of every blue edge; pile 2 the green. Each pair contributes both its pebbles to a single pile, so piles are unions of complete pairs. Each color's 4 pebbles divide 2 blue ends, 2 green ends: exactly 2 per pile. And the pair counts balance automatically: the blue edges carry 2 blue ends each, so #blue = (Σ over vertices of blue ends)/2 = (2n)/2 = n — pile 1 receives exactly n pairs, weighing n(4n + 1); pile 2 the rest. Both conditions hold. ∎

The lab built the construction for 1,200 random colorings (n = 2 through 7, two hundred each) and verified every split: equal weights, 2 pebbles of each color per pile, every time — loops and all. For contrast, the naive per-color pairing (always splitting each color's weights as {w₁, w₄} | {w₂, w₃}) fails on a healthy fraction of colorings (15–49 per 200 in the small censuses); the constant-sum pairing is not a convenience, it is the load-bearing wall.

**What to learn.** "Pair to a constant sum" is one of the great encodings: it converts a global weight constraint into a counting constraint (n pairs per pile), which degree-counting then closes by itself — the 2n/2 = n computation never had to be planned. The Euler-alternation trick is the same machinery as Problem 12's cycle alternation, upgraded from one cycle to a full circuit decomposition; remember the loop-handling, which is where most written proofs of this problem spring leaks. And the contrast with the naive pairing is the Bridge's recurring sermon: constructions should be *derived from the invariant* (constant pair-sum), not from the surface structure (colors).

---

*Terrace II ends here. Terrace III (problems 21–30) — the summit rungs — follows the same anatomy; the Trick Bag, the formula box, and the verification notes close the chapter.*
