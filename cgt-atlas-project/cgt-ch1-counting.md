---
name: "cgt-ch1-counting"
title: "Ch. 1 — Counting: A Lecture Course in the Feynman Style"
type: "text/markdown"
---

# Chapter 1 · Counting

*A lecture course, in the spirit of Feynman's physics lectures: the idea before the formula, the story before the proof, and the proof as a conversation. A compact reference card follows the lectures; graded exercises, a computational lab and worked answers close the chapter.*

## How to read this chapter

Read it slowly, with a pencil. Whenever a small number appears in front of you — *compute it yourself before reading on*. This chapter is a conversation, and you must do your half. Nothing here requires genius; it requires only the patience to count carefully, which is the entire secret of combinatorics. Lines marked **✎ Checkpoint** are the places to stop and predict: commit to a guess — in ink — before reading on. A checked guess teaches; a passively read reveal only feels like learning.

**The exercises are graded:** ●○○ *easy* (a direct application of one lecture idea), ●●○ *moderate* (two ideas, or one tricky step), ●●● *tough* (several chapter ideas combined). Hints travel with the problems; worked answers sit at the very end of the chapter. Try honestly before reading a hint — the struggle is the part of learning that cannot be outsourced. Beyond the graded set, ◐ **Explorations** at the end are open-ended investigations with no single right answer — research training, not test preparation.

---

## Lecture 1 · Ten Letters, Ten Wrong Envelopes

Here is a problem posed around 1708 by Pierre Rémond de Montmort, and it caused a surprising amount of trouble: *You have n letters and n addressed envelopes. In how many ways can you put every letter into a **wrong** envelope?*

A permutation with no fixed point is called a **derangement**, and the count is written D_n. Before we know anything, let us feel the numbers. Take n = 2: the only way to get both wrong is to swap them — D_2 = 1. For n = 3, try it: the two 3-cycles (2,3,1) and (3,1,2) — each list says where letters 1, 2, 3 go — put every letter in a wrong envelope, and everything else leaves at least one letter at home, so D_3 = 2. For n = 4 you can grind it out: D_4 = 9. From n = 2 the sequence runs 1, 2, 9, 44, 265, 1854, … and it grows almost as fast as the factorial. Already something is strange: "get everything wrong" turns out to be *far from rare — a sizeable fraction of all the arrangements there are*.

Now — how would you attack this? Let me show you three attacks, and I promise each one is something you could have invented.

### 1.1 First attack: count the complement — but carefully

There are n! arrangements in all. The ones we want are the complement of "at least one letter lands home." Fine: count the arrangements where letter 1 is home, letter 2 is home, and so on, and subtract. Let's do n = 4 by hand, because the danger shows up immediately.

"Letter i is home" happens in 3! ways for each fixed i — that's 4 × 6 = 24. Subtract from 24 total: 24 − 24 = 0?? Already nonsense — the answer is 9, not 0. **What went wrong?** A permutation with *two* letters home was counted twice, once for each letter. The events overlap, and overlapping events must not be counted with a plain subtraction.

So we repair it, and the repair is the whole method: *add back the double overlaps, subtract the triple overlaps, add back the quadruple…* For n = 4: (4 × 3!) − (C(4,2) × 2!) + (C(4,3) × 1!) − (1 × 0!) = 24 − 12 + 4 − 1 = 15 arrangements with at least one letter home. The complement: 24 − 15 = **9** ✓.

Do you see the mechanism? Add, subtract, add, subtract — **alternate**. Counting the complement of a union of overlapping events is a zigzag. Let us prove that this zigzag gives the exact count D_n for every n, not just n = 4. For each subset S ⊆ {1, …, n} of size k, the number of arrangements that place at least the letters of S into their own envelopes is (n−k)!, because the k letters in S are fixed and the remaining n−k letters may be arranged in any order. Since there are C(n,k) ways to choose the k-element subset S, the k-th level sum across all k-tuples of letters is C(n,k)·(n−k)!. Now follow any single arrangement π through the alternating sum

Σ_{k=0}^{n} (−1)^k · C(n,k) · (n−k)!.

Suppose π puts exactly m letters into their correct envelopes. At level k, the arrangement π is counted once for every k-element subset S chosen from its m fixed letters — that is, C(m,k) times for k ≤ m, and 0 times for k > m. The total net weight contributed by π to the alternating sum is therefore

Σ_{k=0}^{m} (−1)^k · C(m,k).

If m = 0 (so π is a derangement), this sum consists of the single term (−1)⁰·C(0,0) = 1, so every derangement is counted with weight 1. If m ≥ 1 (so π puts at least one letter home), the binomial theorem (1 + x)^m = Σ_{k=0}^{m} C(m,k)·x^k evaluated at x = −1 gives

Σ_{k=0}^{m} (−1)^k · C(m,k) = (1 − 1)^m = 0,

so every arrangement with one or more fixed letters cancels out completely. Finally, expanding C(n,k) = n!/(k!·(n−k)!) cancels the (n−k)! factors: C(n,k)·(n−k)! = n!/k!. We have proved:

**D_n = Σ_{k=0}^{n} (−1)^k · C(n,k) · (n−k)! = n! · Σ_{k=0}^{n} (−1)^k/k!**  — *inclusion–exclusion* (pattern **P3**).

**✎ Checkpoint.** Own the zigzag before moving on. Compute D₅ by hand: 120 − 5·24 + 10·6 − 10·2 + 5·1 − 1. Then compute the two fractions D₅/5! = 44/120 and D₄/4! = 9/24 — and notice how close together they already sit. Pocket that observation; §1.4 will explain it.

### 1.2 Second attack: explain the objects to themselves

The formula above is an *answer*. But a recurrence is an *explanation*, and explanations are worth more. Follow letter number 1. It must land in some envelope i ≠ 1: there are n − 1 choices.

**✎ Checkpoint.** Try the rest yourself before reading on: what can you say about where letter *i* goes? Find the two possible situations — one is a plain swap, and one hides a relabeling that is the entire trick.

Now there are exactly two situations:

1. **Envelope 1 gets letter i back** — a swap. The remaining n − 2 letters must all go wrong among themselves: D_{n−2} ways.
2. **Envelope 1 does not get letter i.** Then **remove letter 1 and envelope i** — both are spent — and **relabel envelope 1 as i**. Now letter i is forbidden the relabelled envelope i, and every other remaining letter is forbidden its own envelope: *exactly the derangement problem one size down*, D_{n−1} ways. (Check the bookkeeping on n = 3: letter 1 → envelope 3, and letter 3 avoids envelope 1. Remove letter 1 and envelope 3; relabel envelope 1 as "3". Now letters {2, 3} must derange on envelopes {2, 3*} — D₂ = 1 way ✓, namely letter 2 → envelope 1 and letter 3 → envelope 2.)

**D_n = (n−1)(D_{n−1} + D_{n−2})**. Check: D_4 = 3 × (2 + 1) = 9 ✓. (Two seeds power the machine: D₀ = 1 — the empty arrangement — and D₁ = 0 — a single letter cannot go wrong alone. The recurrence then produces D₂ = 1·(0 + 1) = 1, the swap, and the whole sequence is pinned.) This little machine *explains* why the numbers grow: each derangement is built from smaller derangements plus one honest choice. (Pattern **P4**: recurrence built by following a forced case analysis.)

### 1.3 Third attack: package the whole sequence into one object

Here is a thought that looks lazy and is secretly profound. Every permutation is: a **set** of letters left in their correct envelopes, glued to a derangement of the rest. Sets of letters are counted by 1 + x + x²/2! + … = e^x. All permutations are counted by 1/(1−x) = Σ n! xⁿ/n!. So if D(x) = Σ D_n xⁿ/n! is the derangement bookkeeping machine:

e^x · D(x) = 1/(1−x), that is, **D(x) = e^{−x}/(1−x)**.

One line — but *why* may we multiply? Because gluing two structures built on disjoint label sets obeys a clean law, and the law is double counting in disguise. If structure A can be built on k of the n labels — chosen in C(n,k) ways — and structure B on the remaining n−k, then the number of glued structures is Σ_k C(n,k)·a_k·b_{n−k}: the binomial coefficient's whole job is to **choose which labels belong to A**. And multiplying the bookkeeping machines performs exactly this sum, term by term:

**(Σ a_n xⁿ/n!) · (Σ b_n xⁿ/n!) = Σ_n [Σ_k C(n,k)·a_k·b_{n−k}] xⁿ/n!**.

So the sentence "every permutation is a set of fixed letters glued to a derangement of the rest" translates *mechanically* into e^x · D(x) = 1/(1−x), or D(x) = e^{−x} · 1/(1−x). When you know the product law, the algebra writes itself. Now unpack the coefficient of x^n on both sides by multiplying the two Taylor series

e^{−x} = Σ_k (−1)^k/k! · x^k and 1/(1−x) = Σ_m x^m.

A term of degree n in the product arises by pairing the x^k term of e^{−x} with the x^{n−k} term of 1/(1−x), for each k ∈ {0, 1, …, n}, and the coefficient of x^n in the product is therefore

D_n/n! = Σ_{k=0}^{n} (−1)^k/k! · 1 = Σ_{k=0}^{n} (−1)^k/k!.

Multiplying through by n! recovers D_n = n! · Σ_{k=0}^{n} (−1)^k/k! — the alternating formula of §1.1 falls out of the algebra *by itself*, without our having to track a single overlap by hand. When a bookkeeping machine reproduces an answer without being told the zigzag, that is a sign you have found the true structure. (Pattern **P5**: generating functions — a whole sequence treated as a single object.)

### 1.4 The punchline: nature leaves a fingerprint

**✎ Checkpoint.** Predict before the reveal: D₇/7! = 1854/5040 and D₈/8! = 14833/40320. Compute both as decimals, commit in ink to a guess about where the fractions are heading, and only then read on.

Divide by n!: D_n/n! = Σ_{k=0}^{n} (−1)^k/k! → **1/e ≈ 0.3679** as n grows. A random arrangement of a million letters has about a 36.8% chance of getting *every single one wrong* — essentially the same chance as for six letters (265/720 ≈ 36.8%). The number e, which you met in calculus as a limit of (1+1/n)ⁿ, shows up here as a *probability about universal mess-making*. Nature is economical with her ideas; she reuses them without telling you.

**What you now own:** count-the-complement with honest overlaps (P3); recurrence-as-explanation (P4); generating-function bookkeeping (P5); and the reflex — *when everything must avoid everything, count the complement, but respect the overlap.*

---

## Lecture 2 · The Mirror World: the Catalan Numbers

Now a problem that looks like a children's game and hides one of the deepest numbers in mathematics. A walker starts at the corner of a square city grid, at (0,0), and wants to reach the opposite corner (n,n), taking only steps East and North. Nothing special so far: C(2n,n) paths. But this walker is superstitious — she refuses ever to be *above* the diagonal line y = x. At every moment, "north so far" must not exceed "east so far." How many paths?

For n = 3: of the 20 total paths, exactly **5** survive. Five — the Catalan number **C₃**. (Mind your fingers: our sequence counts from C₀ = 1, so C₃ is the fourth *term*; "the fifth Catalan number" is exactly the off-by-one this course is training out of you. Compute n = 2 yourself; you should find 2. Do it — with a pencil — before reading on. This is not optional; the pencil is where the understanding happens.)

### 2.1 The mirror trick

Count the good paths directly? Hard. Count the **bad** paths — and this is the move to learn (pattern **P6**) — by finding a mirror image of them in a world we can count.

A bad path touches the line y = x + 1 at some first moment. Take the path up to that moment and reflect it across the line y = x + 1 — every East step becomes a North step and vice versa, and the path is reborn in the mirror world. Let me show you one, n = 2: the bad path **E, N, N, E** first touches the forbidden line at its third step. Reflect those three steps: E,N,N → N,E,E. The mirror path is N,E,E,E — a path that now ends at (3,1) instead of (2,2).

(What, geometrically, is this swap? Reflection across **any** line of slope +1 exchanges East and North steps; what the line's position decides is only *where the picture must be translated afterwards*. Two honest descriptions of one map. **Mirror in the boundary:** reflect the head across the forbidden line y = x + 1 — the touch point (t, t+1) stays where it is and the tail stays where it was, but the head now begins at (−1, 1), so the whole path is lifted by (1, −1) to start at the origin again. **Mirror in the main diagonal:** reflect the head across y = x — the origin stays fixed, but the touch point slides to (t+1, t), and now it is the *tail* that must shift by (1, −1) to rejoin it. Either way the very same path comes out, ending at (n+1, n−1). The step-swap is the primitive; the two mirrors are costumes for it — and when this chapter says "reflect across y = x + 1," it means the first description, translation included.)

Drawn, the pair looks like this (x runs right, y runs up; **⊗** marks the relevant first touch, ╱ the relevant line):

```
   The bad path  E N N E  (ends at (2,2)):

     y=2  ·    ⊗————●
             ╱ │          ╱ = the forbidden line y = x + 1
     y=1  ·    ●    ·     │ = the walker's steps
        ╱      │
     y=0  ●————●    ·
          0    1    2   (x)

   Its mirror  N E E E  (ends at (3,1)):

     y=2  ·    ·    ·    ·
                       ╱       ╱ = the line x = y + 1
     y=1  ●————●————⊗————●
          │       ╱
     y=0  ●    ·    ·    ·
          0    1    2    3   (x)
```

Read the left panel: East along the ground, North twice at x = 1, then East into (2,2) — the walker first sets foot on the line y = x+1 at ⊗. Swap the head up to ⊗ (E,N,N → N,E,E) and the path is reborn as the right panel, ending at (3,1) instead. To *return*, swap the right panel's head up to its own ⊗ — a first touch of **x = y + 1** — and E,N,N,E comes back. **The two ⊗'s lie on different lines.** That is the whole trap: hunt the wrong line and some partners (like E,E,E,N) offer no touch to find — the lab below rings exactly that alarm.

The same pair, drawn as **Figure 1** — labelled axes, the swapped head in amber and the kept tail in blue, both mirror lines dashed, and the two ⊗'s visibly on their different lines:

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 880 530" font-family="system-ui, -apple-system, 'Segoe UI', sans-serif">
  <rect x="0" y="0" width="880" height="530" fill="#ffffff"/>
  <!-- ================= FIGURE 1 · The reflection pair ================= -->
  <text x="40" y="34" font-size="17" font-weight="700" fill="#193e5c">Figure 1 &#183; The reflection pair &#8212; a bad path and its mirror</text>

  <!-- Panel A : bad path E N N E -->
  <text x="110" y="62" font-size="13" fill="#172333" font-weight="600">the bad path E N N E (ends at (2,2))</text>
  <g fill="#cbd5e1">
    <circle cx="110" cy="380" r="2.5"/><circle cx="160" cy="380" r="2.5"/><circle cx="210" cy="380" r="2.5"/><circle cx="260" cy="380" r="2.5"/>
    <circle cx="110" cy="330" r="2.5"/><circle cx="160" cy="330" r="2.5"/><circle cx="210" cy="330" r="2.5"/><circle cx="260" cy="330" r="2.5"/>
    <circle cx="110" cy="280" r="2.5"/><circle cx="160" cy="280" r="2.5"/><circle cx="210" cy="280" r="2.5"/><circle cx="260" cy="280" r="2.5"/>
    <circle cx="110" cy="230" r="2.5"/><circle cx="160" cy="230" r="2.5"/><circle cx="210" cy="230" r="2.5"/><circle cx="260" cy="230" r="2.5"/>
  </g>
  <line x1="110" y1="230" x2="110" y2="385" stroke="#94a3b8" stroke-width="1.2"/>
  <line x1="105" y1="380" x2="265" y2="380" stroke="#94a3b8" stroke-width="1.2"/>
  <g font-size="11" fill="#64748b" text-anchor="middle">
    <text x="110" y="398">0</text><text x="160" y="398">1</text><text x="210" y="398">2</text><text x="260" y="398">3</text>
    <text x="98" y="384">0</text><text x="98" y="334">1</text><text x="98" y="284">2</text><text x="98" y="234">3</text>
  </g>
  <!-- the forbidden line y = x + 1 -->
  <line x1="120" y1="320" x2="235" y2="205" stroke="#dc2626" stroke-width="2" stroke-dasharray="6,4"/>
  <text x="239" y="207" font-size="11.5" fill="#dc2626" font-style="italic">y = x + 1</text>
  <!-- path: head (amber) = steps 1-3, tail (blue) = step 4 -->
  <polyline points="110,380 160,380 160,330 160,280" fill="none" stroke="#d97706" stroke-width="4" stroke-linecap="round" stroke-linejoin="round"/>
  <polyline points="160,280 210,280" fill="none" stroke="#2563eb" stroke-width="4" stroke-linecap="round"/>
  <circle cx="210" cy="280" r="4" fill="#2563eb"/>
  <text x="220" y="272" font-size="11.5" fill="#2563eb">(2,2)</text>
  <!-- step labels -->
  <g font-size="11" font-weight="600">
    <text x="135" y="372" fill="#d97706" text-anchor="middle">1 E</text>
    <text x="172" y="356" fill="#d97706">2 N</text>
    <text x="172" y="303" fill="#d97706">3 N</text>
    <text x="185" y="272" fill="#2563eb" text-anchor="middle">4 E</text>
  </g>
  <!-- first-touch mark -->
  <circle cx="160" cy="280" r="8" fill="#ffffff" stroke="#dc2626" stroke-width="2.5"/>
  <line x1="154.5" y1="274.5" x2="165.5" y2="285.5" stroke="#dc2626" stroke-width="2"/>
  <line x1="165.5" y1="274.5" x2="154.5" y2="285.5" stroke="#dc2626" stroke-width="2"/>
  <g font-size="12" fill="#172333">
    <text x="110" y="428">swap the head up to &#8857;: E,N,N &#8594; N,E,E</text>
    <text x="110" y="448" font-size="11.5" fill="#64748b">the path is reborn in the mirror world</text>
  </g>

  <!-- Panel B : the mirror N E E E -->
  <text x="560" y="62" font-size="13" fill="#172333" font-weight="600">its mirror N E E E (ends at (3,1))</text>
  <g fill="#cbd5e1">
    <circle cx="560" cy="380" r="2.5"/><circle cx="610" cy="380" r="2.5"/><circle cx="660" cy="380" r="2.5"/><circle cx="710" cy="380" r="2.5"/>
    <circle cx="560" cy="330" r="2.5"/><circle cx="610" cy="330" r="2.5"/><circle cx="660" cy="330" r="2.5"/><circle cx="710" cy="330" r="2.5"/>
    <circle cx="560" cy="280" r="2.5"/><circle cx="610" cy="280" r="2.5"/><circle cx="660" cy="280" r="2.5"/><circle cx="710" cy="280" r="2.5"/>
    <circle cx="560" cy="230" r="2.5"/><circle cx="610" cy="230" r="2.5"/><circle cx="660" cy="230" r="2.5"/><circle cx="710" cy="230" r="2.5"/>
  </g>
  <line x1="560" y1="230" x2="560" y2="385" stroke="#94a3b8" stroke-width="1.2"/>
  <line x1="555" y1="380" x2="715" y2="380" stroke="#94a3b8" stroke-width="1.2"/>
  <g font-size="11" fill="#64748b" text-anchor="middle">
    <text x="560" y="398">0</text><text x="610" y="398">1</text><text x="660" y="398">2</text><text x="710" y="398">3</text>
    <text x="548" y="384">0</text><text x="548" y="334">1</text><text x="548" y="284">2</text><text x="548" y="234">3</text>
  </g>
  <!-- the line x = y + 1 -->
  <line x1="585" y1="405" x2="735" y2="255" stroke="#16a34a" stroke-width="2" stroke-dasharray="6,4"/>
  <text x="739" y="257" font-size="11.5" fill="#16a34a" font-style="italic">x = y + 1</text>
  <!-- path: head (amber) = steps 1-3, tail (blue) = step 4 -->
  <polyline points="560,380 560,330 610,330 660,330" fill="none" stroke="#d97706" stroke-width="4" stroke-linecap="round" stroke-linejoin="round"/>
  <polyline points="660,330 710,330" fill="none" stroke="#2563eb" stroke-width="4" stroke-linecap="round"/>
  <circle cx="710" cy="330" r="4" fill="#2563eb"/>
  <text x="720" y="322" font-size="11.5" fill="#2563eb">(3,1)</text>
  <!-- step labels -->
  <g font-size="11" font-weight="600">
    <text x="552" y="358" fill="#d97706" text-anchor="end">1 N</text>
    <text x="585" y="318" fill="#d97706" text-anchor="middle">2 E</text>
    <text x="635" y="318" fill="#d97706" text-anchor="middle">3 E</text>
    <text x="688" y="318" fill="#2563eb" text-anchor="middle">4 E</text>
  </g>
  <!-- first-touch mark -->
  <circle cx="660" cy="330" r="8" fill="#ffffff" stroke="#16a34a" stroke-width="2.5"/>
  <line x1="654.5" y1="324.5" x2="665.5" y2="335.5" stroke="#16a34a" stroke-width="2"/>
  <line x1="665.5" y1="324.5" x2="654.5" y2="335.5" stroke="#16a34a" stroke-width="2"/>
  <g font-size="12" fill="#172333">
    <text x="560" y="428">swap back up to &#8857;: N,E,E &#8594; E,N,N</text>
    <text x="560" y="448" font-size="11.5" fill="#64748b">the bad path returns &#8212; the bijection is two-way</text>
  </g>

  <!-- legend + note -->
  <g font-size="11.5">
    <line x1="40" y1="474" x2="70" y2="474" stroke="#d97706" stroke-width="4"/>
    <text x="78" y="478" fill="#172333">the head (what gets swapped)</text>
    <line x1="270" y1="474" x2="300" y2="474" stroke="#2563eb" stroke-width="4"/>
    <text x="308" y="478" fill="#172333">the tail (kept as it is)</text>
  </g>
  <text x="40" y="504" font-size="12" fill="#172333">The two &#8857; marks lie on different lines &#8212; y = x + 1 (left, red) and x = y + 1 (right, green). Hunt the wrong line and some partners offer no touch to find.</text>
</svg>
```

The miracle: this map is a **bijection** for every n ≥ 1 — and the way to *know* that is to verify both the endpoint step counts and the preservation of the first-touch index. Along any lattice path starting at (x₀, y₀) = (0,0), the quantity y_j − x_j starts at 0 and changes by ±1 at each step j. A path P from (0,0) to (n,n) is bad if and only if y_j − x_j ≥ 1 for some j, so by unit-step continuity there is a unique earliest step m = 2t + 1 at which y_m − x_m = 1 — namely, the first vertex (x_m, y_m) = (t, t+1) on the forbidden line y = x + 1, while y_j − x_j ≤ 0 for all 0 ≤ j < m. The prefix of P of length m has t East steps and t + 1 North steps, and the remaining suffix has n − t East steps and n − (t + 1) North steps. Define Φ(P) by swapping East and North in the prefix of length m. The reflected path Φ(P) has

(t + 1) + (n − t) = n + 1 East steps and t + (n − t − 1) = n − 1 North steps,

so it is an unrestricted lattice path from (0,0) to (n+1, n−1). Crucially, at every vertex (x′_j, y′_j) = (y_j, x_j) of the swapped prefix (0 ≤ j ≤ m), we have x′_j − y′_j = y_j − x_j. Therefore x′_j − y′_j ≤ 0 for all 0 ≤ j < m and x′_m − y′_m = 1, which means (x′_m, y′_m) = (t+1, t) is the **unique first vertex** of Φ(P) on the line x = y + 1.

Conversely, along any unrestricted path Q from (0,0) to (n+1, n−1), the difference x_j − y_j starts at 0, ends at (n+1) − (n−1) = 2 ≥ 1, and changes by ±1 per step, so Q has a unique first vertex (t+1, t) at step m = 2t + 1 where x_m − y_m = 1 (with x_j − y_j ≤ 0 for all 0 ≤ j < m). Defining Ψ(Q) by swapping East and North in the prefix up to step m produces a path to (n,n) whose vertices satisfy y″_j − x″_j = x_j − y_j ≤ 0 for 0 ≤ j < m and y″_m − x″_m = 1, so (t, t+1) at step m is its first touch of y = x + 1. Because Φ and Ψ reflect at the exact same first-touch index m in both directions and swapping East and North twice is the identity, Ψ(Φ(P)) = P and Φ(Ψ(Q)) = Q. (Careful: the inverse looks for the first touch of x = y + 1, *not* y = x + 1 — the path E, E, E, N to (3,1) never touches y = x + 1 at all. The lab below machine-tests this inverse in both directions.) Two worlds, perfectly translated, with the translation specified both ways.

Unrestricted paths of length 2n to (n+1, n−1) are easy to count: choose which n − 1 of the 2n steps are North, in C(2n, n−1) ways. Subtracting the bad paths from all C(2n,n) paths to (n,n) and simplifying the factorials gives:

**C_n = C(2n,n) − C(2n,n−1) = (2n)!/(n!·n!) − (2n)!/((n−1)!·(n+1)!) = (2n)!/(n!·n!) · (1 − n/(n+1)) = (1/(n+1)) · C(2n,n)**.

The ugly answer "5 out of 20" is now *explained*: exactly 1 in every 4 paths behaves. When a strange fraction becomes obvious, you have found the right idea.

### 2.2 The equation the paths obey

Look at any nonempty good path. It starts with an **East** step (a North step would put her above the diagonal immediately) and, at some point, first returns to the diagonal — closing the first "excursion." A good path is:

> **empty**, or **E** [a good path] **N** [a good path]

Read that aloud: a path is nothing, or a matched pair wrapping a smaller path and followed by another. That is *self-similarity* — the object is made of copies of itself. Here is a good path of size 3 cut at its first return (⊗ marks the first return to the diagonal):

```
   The path  E E N N E N:

     y=3  ·    ·    ·    ●
                         │
     y=2  ·    ·    ⊗————●
                    │
     y=1  ·    ·    ●    ·
                    │
     y=0  ●————●————●    ·
          0    1    2    3   (x)
```

Read the shape: the opening E starts the first excursion; the closing N of that excursion lands on ⊗. Inside the pair sat **A = E N** (a good path of size 1, translated); after it marches **B = E N** (another). The path is E [A] N [B] with |A| = 1, |B| = 1 — and summing over the splits 0+2, 1+1, 2+0 gives C₃ = 1·2 + 1·1 + 2·1 = 5 ✓.

The same cut, drawn as **Figure 2** — the wrapping pair E…N in purple, A in amber, B in blue, all six steps labelled and the split arithmetic at the foot:

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 548 880 350" font-family="system-ui, -apple-system, 'Segoe UI', sans-serif">
  <rect x="0" y="548" width="880" height="350" fill="#ffffff"/>
  <!-- ================= FIGURE 2 · The first-return cut ================= -->
  <text x="40" y="568" font-size="17" font-weight="700" fill="#193e5c">Figure 2 &#183; The first-return cut &#8212; E [A] N [B]</text>
  <text x="40" y="590" font-size="12.5" fill="#64748b">the good path E E N N E N of size 3, cut at its first return to the diagonal</text>

  <g fill="#cbd5e1">
    <circle cx="120" cy="780" r="2.5"/><circle cx="172" cy="780" r="2.5"/><circle cx="224" cy="780" r="2.5"/><circle cx="276" cy="780" r="2.5"/>
    <circle cx="120" cy="728" r="2.5"/><circle cx="172" cy="728" r="2.5"/><circle cx="224" cy="728" r="2.5"/><circle cx="276" cy="728" r="2.5"/>
    <circle cx="120" cy="676" r="2.5"/><circle cx="172" cy="676" r="2.5"/><circle cx="224" cy="676" r="2.5"/><circle cx="276" cy="676" r="2.5"/>
    <circle cx="120" cy="624" r="2.5"/><circle cx="172" cy="624" r="2.5"/><circle cx="224" cy="624" r="2.5"/><circle cx="276" cy="624" r="2.5"/>
  </g>
  <line x1="120" y1="624" x2="120" y2="785" stroke="#94a3b8" stroke-width="1.2"/>
  <line x1="115" y1="780" x2="281" y2="780" stroke="#94a3b8" stroke-width="1.2"/>
  <g font-size="11" fill="#64748b" text-anchor="middle">
    <text x="120" y="798">0</text><text x="172" y="798">1</text><text x="224" y="798">2</text><text x="276" y="798">3</text>
    <text x="108" y="784">0</text><text x="108" y="732">1</text><text x="108" y="680">2</text><text x="108" y="628">3</text>
  </g>
  <!-- the diagonal y = x -->
  <line x1="120" y1="780" x2="276" y2="624" stroke="#94a3b8" stroke-width="1.5" stroke-dasharray="4,4"/>
  <text x="282" y="612" font-size="11.5" fill="#64748b" font-style="italic">y = x</text>
  <!-- path segments -->
  <polyline points="120,780 172,780" fill="none" stroke="#7c3aed" stroke-width="4" stroke-linecap="round"/>
  <polyline points="172,780 224,780 224,728" fill="none" stroke="#d97706" stroke-width="4" stroke-linecap="round" stroke-linejoin="round"/>
  <polyline points="224,728 224,676" fill="none" stroke="#7c3aed" stroke-width="4" stroke-linecap="round"/>
  <polyline points="224,676 276,676 276,624" fill="none" stroke="#2563eb" stroke-width="4" stroke-linecap="round" stroke-linejoin="round"/>
  <circle cx="276" cy="624" r="4" fill="#2563eb"/>
  <text x="288" y="638" font-size="11.5" fill="#172333">(3,3)</text>
  <!-- step labels -->
  <g font-size="11" font-weight="600">
    <text x="146" y="772" fill="#7c3aed" text-anchor="middle">1 E</text>
    <text x="198" y="772" fill="#d97706" text-anchor="middle">2 E</text>
    <text x="232" y="756" fill="#d97706">3 N</text>
    <text x="216" y="704" fill="#7c3aed" text-anchor="end">4 N</text>
    <text x="252" y="668" fill="#2563eb" text-anchor="middle">5 E</text>
    <text x="284" y="652" fill="#2563eb">6 N</text>
  </g>
  <!-- first-return mark -->
  <circle cx="224" cy="676" r="8" fill="#ffffff" stroke="#dc2626" stroke-width="2.5"/>
  <line x1="218.5" y1="670.5" x2="229.5" y2="681.5" stroke="#dc2626" stroke-width="2"/>
  <line x1="229.5" y1="670.5" x2="218.5" y2="681.5" stroke="#dc2626" stroke-width="2"/>
  <!-- bracket reading -->
  <text x="120" y="838" font-size="15" font-weight="600"><tspan fill="#7c3aed">E</tspan><tspan fill="#172333"> [ </tspan><tspan fill="#d97706">A = E N</tspan><tspan fill="#172333"> ] </tspan><tspan fill="#7c3aed">N</tspan><tspan fill="#172333"> [ </tspan><tspan fill="#2563eb">B = E N</tspan><tspan fill="#172333"> ]</tspan></text>
  <text x="120" y="862" font-size="12.5" fill="#172333">|A| = 1, |B| = 1 &#8212; over the splits 0+2, 1+1, 2+0:  C&#8323; = 1&#183;2 + 1&#183;1 + 2&#183;1 = 5 &#10003;</text>
  <text x="120" y="886" font-size="11.5" fill="#64748b">&#8857; = the first return to the diagonal &#183; purple = the wrapping pair E &#8230; N &#183; amber = A (inside the pair) &#183; blue = B (the rest)</text>
</svg>
```

**✎ Checkpoint.** Now try the translation yourself before seeing it done. If C(x) is the bookkeeping machine for good paths, what should the sentence "a path is *empty*, or **E** [path] **N** [path]" say about C(x)? (Decide first what one wrapped pair E…N should *cost* — there is exactly one natural choice.)

Now the physicist's move. Define the bookkeeping machine **C(x) = Σ_{n≥0} C_n xⁿ** — the *ordinary* generating function: a path of size n contributes one unit of xⁿ. Notice what is *absent* here compared with Lecture 1.3, where D(x) = Σ D_n xⁿ/n! carried a factorial in every term. That factorial was load-bearing: derangements live on *labeled* letters, and gluing two labeled structures forces a choose-which-labels binomial — the 1/n! factors are exactly what tames it. A path carries no labels: its decomposition splits it by *position* — first excursion, then the rest — and the sizes of the pieces are read off the path itself, with nothing to choose. No binomial appears, so no factorial is needed. **Exponential bookkeeping for labeled worlds; ordinary bookkeeping for unlabeled ones** — a distinction that will earn its own lecture the next time it matters. The sentence above, translated into bookkeeping (one wrapped pair costs a factor x), is an *equation*:

**C(x) = 1 + x·C(x)²**.

That equation **is** the Catalan structure: x·C(x)² − C(x) + 1 = 0. Comparing coefficients of xⁿ directly in C(x) = 1 + x·C(x)² gives the convolution recurrence C_n = Σ_{k=0}^{n−1} C_k·C_{n−1−k} for n ≥ 1 with C₀ = 1 (check C_3 = 1·2 + 1·1 + 2·1 = 5 ✓). Better still, we can solve the quadratic for C(x) and extract the closed form without touching a mirror. For x ≠ 0, the quadratic formula gives

C(x) = (1 ± √(1−4x))/(2x).

Which sign does nature choose? Since C(x) = Σ C_n·xⁿ is continuous near x = 0 with C(0) = C₀ = 1, we must have lim_{x→0} C(x) = 1. Because √(1−4x) = 1 − 2x + O(x²) as x → 0, the plus branch diverges like 1/x, whereas the minus branch satisfies lim_{x→0} (1 − (1 − 2x + O(x²)))/(2x) = 1. Thus C(x) = (1 − (1−4x)^{1/2})/(2x) for |x| < 1/4. Now expand (1−4x)^{1/2} by Newton's generalized binomial theorem:

(1−4x)^{1/2} = 1 + Σ_{m=1}^{∞} C(1/2, m)·(−4)^m·x^m.

For m = 1, the term is C(1/2, 1)·(−4)·x = −2x = −(2/1)·C(0,0)·x. For every integer m ≥ 2, the numerator of C(1/2, m) has m factors — namely 1/2 followed by the m − 1 negative half-integers −1/2, −3/2, …, −(2m−3)/2:

C(1/2, m) = (1/2)(−1/2)(−3/2)···(−(2m−3)/2) / m! = ((−1)^{m−1})/(2^m·m!) · ∏_{j=1}^{m−1} (2j − 1).

Multiply numerator and denominator of this (m−1)-factor odd product by the (m−1)-factor even product ∏_{j=1}^{m−1} (2j) = 2^{m−1}·(m−1)! to complete the factorial (2m−2)!:

C(1/2, m)·(−4)^m = ((−1)^{m−1})/(2^m·m!) · (2m−2)!/(2^{m−1}·(m−1)!) · (−1)^m·2^{2m} = −(2/m)·(2m−2)!/((m−1)!·(m−1)!) = −(2/m)·C(2m−2, m−1).

Since −(2/m)·C(2m−2, m−1) also equals −2 at m = 1, the formula holds for all m ≥ 1. Substituting it into C(x) = (1 − (1−4x)^{1/2})/(2x) and shifting the summation index via n = m − 1 (so m = n + 1) yields

C(x) = (1/(2x)) · Σ_{m=1}^{∞} (2/m)·C(2m−2, m−1)·x^m = Σ_{n=0}^{∞} (1/(n+1))·C(2n,n)·xⁿ.

The coefficient of xⁿ on the right is C_n = (1/(n+1))·C(2n,n) for all n ≥ 0 — streaming out of pure algebra, and matching the mirror world of §2.1. Pattern **P4/P5** again: *decompose at the first return; write the self-similarity as an equation.*

### 2.3 One number, many costumes

**✎ Checkpoint.** Pause the book. You now own the sequence 1, 2, 5, 14, 42, 132. Write down every mathematical object you have *ever* seen counted by these numbers — guess boldly, in ink — then compare with the list below. Every hit you score is a costume you can hunt a bijection for.

Here is the part that would make you suspicious if you met it in fiction: the numbers 1, 2, 5, 14, 42… count *all* of these — good lattice paths to (n,n); balanced parenthesis strings with n pairs; triangulations of an (n+2)-gon; full binary trees with n+1 leaves; permutations of n things sortable by one stack. Five costumes, one number. Each pair of costumes is connected by an explicit **bijection** (pattern **P1**), and finding those translations is the best training I know: when the same numbers appear twice, do not shrug — *hunt the map between the two worlds.* The decomposition "E [path] N [path]" is the true content; every costume is the same creature wearing different clothes.

**What you now own:** count-the-bad by reflection (P6); decompose-at-first-return and write self-similarity as an equation (P4/P5); bijection-hunting (P1).

---

## Lecture 3 · Count It Twice

The single most productive trick in this entire book fits in one sentence: **count the same set two different ways and set the answers equal.**

### 3.1 The committee

From m women and n men, choose a committee of r. Obvious answer: C(m+n, r). But classify the same committees by composition — k women and r−k men: Σ_k C(m,k)·C(n, r−k). The two bookkeepings count one world, so:

**C(m+n, r) = Σ_k C(m,k)·C(n, r−k)** — Vandermonde.

Notice what happened: the identity was *not* algebra; it was an **observation about the world dressed in symbols**. Two ways to prove it anyway: (i) multiply (1+x)^m(1+x)^n = (1+x)^{m+n} and compare the coefficient of x^r — the bookkeeping machine again; (ii) lattice paths: paths from (0,0) to (m+n−r, r) take m+n steps, r of them North; classify them by k, the height at which a path crosses the boundary after step m — the first m steps place their k Norths in C(m,k) ways, the last n steps their r−k Norths in C(n, r−k) ways. Sum over k: same identity, third costume. *Multiple proofs are not decoration; each proof is a different door into the idea.*

### 3.2 The handshake among subsets

Now the deepest two-line argument in elementary combinatorics.

**✎ Checkpoint.** Warm the engine by hand first: list all 8 subsets of {1,2,3} and total their sizes — you should get 12. Now predict, in ink, the average size of a subset of {1,…,100} before reading the two bookkeepings.

For n ≥ 1, count pairs (x, S) where x is an element of the subset S of {1,…,n}:

- **Choose S first:** every k-element set contributes k pairs; total Σ_k k·C(n,k).
- **Choose x first:** each of the n elements sits in exactly half of all subsets — 2^{n−1} of them; total n·2^{n−1}.

So **Σ_k k·C(n,k) = n·2^{n−1}** for all n ≥ 1 (and trivially at n = 0, where both sides equal 0). And a third costume: differentiate (1+x)^n at x = 1. Three engines, one truth.

**The corollary to remember forever:** the *average* subset has n/2 elements. Averaging is the baby form of probability, and probability grows into an entire method — one that will later prove things *exist* without ever constructing them. Plant that seed now; Chapter 4 waters it.

---

## Lecture 4 · The Bit Machine: 2^n

Shortest lecture of the course. A subset of {1,…,n} is a row of n switches, each up or down. Switches: 2 × 2 × … × 2 = **2^n**.

**✎ Checkpoint.** Before classifying: what must Σ_k C(n,k) equal — and *why*, using nothing but the switch picture? Say the reason aloud, then check it against the n = 3 row of Pascal's triangle.

Classify by the number of "up" switches and you get Σ_k C(n,k) = 2^n — the same world counted by type and by total. The binomial theorem at x = 1 says the same thing in formal dress: this is the machine from Lecture 3 with both bookkeepings visible at once.

The switch picture is worth keeping for one reason: it converts statements about sets into statements about *strings*, where arithmetic is easy. Half the tricks in coding theory and combinatorics start by putting a string costume on a set.

---

## The Trick Bag (reference card)

| Pattern | Plain language | Where you met it |
|---------|---------------|-----------------|
| **P1 Bijection** | Two worlds, one map: translate the count. Its dynamic face, the **sign-reversing involution**: pair the unwanted objects with a sign-flipping swap and they cancel from an alternating sum (Gessel–Viennot) | Lecture 2.3, A18 |
| **P2 Double counting** | Count one world two ways; setting the answers equal is the theorem | Lecture 3 |
| **P3 Inclusion–exclusion** | Complement of overlapping events = zigzag add/subtract | Lecture 1.1 |
| **P4 Recurrence** | Follow a forced case; explain n by smaller n. Its termination face, the **monovariant**: a quantity that strictly improves at each step certifies the process bottoms out | Lecture 1.2, 2.2 |
| **P5 Generating function** | A whole sequence packaged as one object; algebra works for you | Lectures 1.3, 2.2 |
| **P6 Complement / reflection** | Can't count the good? Count the bad — maybe in a mirror world. Usage-evidence note: zero genuine firings in the survey's census of 133 papers across 14 batches — the only textbook-canon pattern with none; this card is textbook canon (a proof-shape every counter should own — Exercise 11 runs it), not field-visible practice | Lecture 2.1, A11 |

**Formula box:** For integers n, m, r ≥ 0 (with the convention C(a,b) = 0 whenever b > a): D_n = n!·Σ_{k=0}^{n}(−1)^k/k! (n ≥ 0); D_n = (n−1)(D_{n−1}+D_{n−2}) (n ≥ 2, with D₀ = 1, D₁ = 0); D(x) = e^{−x}/(1−x); D_n/n! → 1/e. C_n = (1/(n+1))·C(2n,n) (n ≥ 0); C(x) = 1 + xC(x)². Vandermonde: C(m+n,r) = Σ_{k=0}^{r} C(m,k)·C(n,r−k). Σ_{k=0}^{n} C(n,k) = 2^n; Σ k·C(n,k) = n·2^{n−1} (n ≥ 1).

---

## Exercises (graded: ●○○ easy · ●●○ moderate · ●●● tough)

*Hints travel with the graded tiers; worked answers are at the end of the chapter (numbered A1–A22 to match). Try first.*

**Easy — one idea, applied directly**

1. (●○○) Compute D₁₀ with the recurrence engine of Lecture 1.2 (no closed formulas allowed), then check D₁₀/10! against 1/e.
2. (●○○) Count the lattice paths from (0,0) to (5,5) staying weakly below the diagonal — *using the mirror trick of Lecture 2.1 by naming the reflected endpoint and inverse boundary explicitly, not plugging into the closed formula*.
3. (●○○) From 5 women and 4 men, count the 3-person committees directly; then classify by composition (k women, 3−k men) and check the bookkeepings agree. *(This is Lecture 3 in your hands.)*
4. (●○○) List all balanced parenthesis strings of length 6. Then prove why balanced parenthesis strings of length 2n are counted by C_n, and predict the count for length 8.
5. (●○○) How many length-4 strings over {a,b,c} contain at least one of each letter? — *inclusion–exclusion, and mind the overlaps.*
6. (●○○) **Anagrams.** How many distinct rearrangements does the word BANANA have? And MISSISSIPPI? *Hint: P1 — temporarily label the identical letters so everything is distinguishable, count, then ask how many labelings collapse onto one printed arrangement.*

**Moderate — two ideas, or one tricky step**

7. (●●○) Prove Σ_k C(n,k)² = C(2n,n). *Hint: P2 — choose n people from two rooms of n; or specialize Vandermonde.*
8. (●●○) Prove the derangements' second engine: **D_n = n·D_{n−1} + (−1)ⁿ**. *Hint: P5 — start from D(x) = e^{−x}/(1−x), multiply both sides by (1−x), and extract the coefficient of xⁿ.*
9. (●●○) Show that D_n is the nearest integer to n!/e for every n ≥ 1. *Hint: P3 — bound the discarded alternating tail strictly below 1/(n+1).*
10. (●●○) Count the arrangements of n ≥ 1 letters in which *exactly one* letter lands in its correct envelope. *Hint: choose the lucky letter — n ways — then derange the rest (P3/P4).*
11. (●●○) **The ballot problem.** Candidate A scores a votes, B scores b, with a > b ≥ 0. In how many orderings of the ballots is A strictly ahead after every single ballot? (Paths (0,0)→(a,b) touching the diagonal only at the start.) *Hint: P6 — first reduce to the weak version by deleting A's forced first ballot, then run Lecture 2.1's reflection through the line y = x+1.*
12. (●●○) **The couples' banquet.** From 7 married couples (14 people), count the 5-person delegations that contain no married couple. *Hint: P3 — the zigzag of Lecture 1, with "a couple both chosen" playing the role of "a letter home." Mind where the zigzag honestly stops: how many couples fit in a 5-person delegation at all?*
13. (●●○) **Compositions.** In how many ways can n be written as an *ordered* sum of positive integers? (For n = 4: 4, 3+1, 1+3, 2+2, 2+1+1, 1+2+1, 1+1+2, 1+1+1+1 — eight.) Prove your answer **two ways**: one bijection, one recurrence. *Hint: P1 on the n−1 gaps between n unit tokens — cut or glue; then P4, conditioning on the first summand.*
14. (●●○) **Committee, then subcommittee.** Prove that Σ_k C(n,k)·C(k,m) = C(n,m)·2^{n−m} for 0 ≤ m ≤ n. *Hint: P2 — count the pairs (committee S, subcommittee T) with T ⊆ S ⊆ {1,…,n} and |T| = m in two orders: choose S first, or choose T first and let S grow around it.*

**Tough — several chapter ideas combined**

15. (●●●) For n ≥ 1, count the paths from (0,0) to (n,n), on either side of the diagonal, that touch the diagonal **only at their two endpoints**. *Hint: once the side is chosen, the first and last steps are forced; strip them off, translate, and recognize what remains (Lecture 2.2's decomposition).*
16. (●●●) Prove Σ_k (k − n/2)²·C(n,k) = n·2ⁿ⁻². *In words: the average subset has n/2 elements (Lecture 3.2) — this says how far it typically strays. Hint: differentiate (1+x)ⁿ twice at x = 1, then combine with Lecture 3.2's identity.*
17. (●●●) 2n people sit at a round table. In how many ways can they split into n disjoint handshake pairs with **no two handshakes crossing**? *Hint: P1/P4 — fix person 1's partner; the handshake cuts the circle into two independent smaller circles; write the self-similarity (Lecture 2.2 style).*
18. (●●●) Find an explicit bijection between the triangulations of a convex (n+2)-gon and the balanced parenthesis strings of length 2n, and prove it is invertible. *Hint: P1 — distinguish one base edge of the polygon; the unique triangle sitting on that edge splits the polygon into two smaller polygons; recurse. Verify on the pentagon (n = 3) by listing all 5 triangulations and their 5 strings.*

19. (●●●) **Onto functions.** Count the functions from a 6-element set onto a 3-element set (every value must be hit at least once); then find the general formula for onto functions from an n-element set to a k-element set (n, k ≥ 1). *Hint: P3 again, but the bad events are now *misses* — a function avoiding a fixed set of j target values can land anywhere in the remaining k−j values. What is the derangement lesson's zigzag, transplanted?*

**Pattern unknown — you choose the tool** *The graded sets above tell you which lecture idea to reach for — research and exams do not. No hints here, and no difficulty rating either: diagnosing the problem is part of the problem. Worked answers still wait at the end.*

20. (◆) How many subsets of {1, …, n} contain no two consecutive integers?
21. (◆) Show that for n ≥ 1, the subsets of {1, …, n} of even size are exactly as many as those of odd size.
22. (◆) n straight lines are drawn in the plane, no two parallel and no three through a point. Into how many regions do they cut the plane?

**Explorations — ◐ research-style training** *No single right answer — what you should find is described in each. These train the habit research actually runs on: changing the problem.*

X1. (◐) **When letters may be correct.** Count the arrangements with *exactly r* letters home (choose the r lucky letters, derange the rest — these are the **rencontres numbers**). Then compute, for every n, the *expected* number of home letters in a random arrangement — count the pairs (letter, arrangement where it is home) two ways, Lecture 3's engine. You should find a strikingly clean answer independent of n; meditate on why. Then code it: for n = 5, 10, 20, tally the number of home letters over many random arrangements and watch the distribution settle — you should recognize Lecture 1.4's 1/e grown into a whole law (the count of home letters converges to a Poisson(1) distribution). Explain to yourself why the events "letter i is home" are rare, approximately independent events — each occurring with probability 1/n — and where the dependence hides.

X2. (◐) **Catalan paths in a band.** Restrict the walker to the band x − 2 ≤ y ≤ x (she may fall at most two behind): count paths to (n,n) for n = 1..6 by hand and by code, and find the recurrence they satisfy — it is unusually simple; find the *reason* for its simplicity. One boundary alone still surrenders to the mirror trick of Lecture 2.1; with two, the mirrored images overlap, and the honest repair is Lecture 1's zigzag (P3) applied to whole reflected worlds. No answer is provided here: hitting the edge of a method — and repairing it — is the exercise.

---

## Computational Lab (verified)

Both engines of Lecture 1 and Lecture 2 — with their boundary cases — cross-checked by execution (2026-10-09; re-run 2026-10-13; re-run 2026-10-23 as a line-for-line TypeScript port, all assertions and prints reproduced):

```python
from math import comb, e, factorial

def D_rec(n):                       # recurrence engine (Lecture 1.2)
    if n < 0:
        raise ValueError("n must be >= 0")
    if n == 0:
        return 1
    if n == 1:
        return 0
    D = [1, 0]
    for i in range(2, n + 1):
        D.append((i - 1) * (D[i-1] + D[i-2]))
    return D[n]

def D_one_step(n):                  # one-step engine (Exercise 8: D_n = n*D_{n-1} + (-1)**n)
    if n < 0:
        raise ValueError("n must be >= 0")
    d = 1
    for i in range(1, n + 1):
        d = i * d + (-1)**i
    return d

def D_ie(n):                        # inclusion-exclusion engine (Lecture 1.1)
    if n < 0:
        raise ValueError("n must be >= 0")
    return sum((-1)**k * comb(n, k) * factorial(n - k) for k in range(n + 1))

def C_rec(n):                       # Catalan first-return recurrence (Lecture 2.2)
    if n < 0:
        raise ValueError("n must be >= 0")
    C = [1]
    for i in range(1, n + 1):
        C.append(sum(C[k] * C[i-1-k] for k in range(i)))
    return C[n]

def C_mirror(n):                    # reflection-difference engine (Lecture 2.1)
    if n < 0:
        raise ValueError("n must be >= 0")
    bad = comb(2*n, n - 1) if n >= 1 else 0
    return comb(2*n, n) - bad

assert all(D_rec(n) == D_one_step(n) == D_ie(n) for n in range(11))
assert all(abs(D_rec(n) - factorial(n) / e) < 1 / (n + 1) for n in range(1, 11))
assert all(C_rec(n) == C_mirror(n) == comb(2*n, n) // (n + 1) for n in range(11))
assert all(sum(comb(m, k) * comb(n, r - k) for k in range(r + 1)) == comb(m + n, r)
           for m in range(6) for n in range(6) for r in range(m + n + 1))
assert all(sum(comb(n, k) for k in range(n + 1)) == 2**n for n in range(11))
assert all(sum(k * comb(n, k) for k in range(n + 1))
           == (n * 2**(n - 1) if n >= 1 else 0) for n in range(11))

print("D_n, n = 2..9:", [D_rec(n) for n in range(2, 10)])
print("D_9/9! =", round(D_rec(9) / factorial(9), 5))
print("Catalan, n = 0..10:", [C_rec(n) for n in range(11)])
```

**Verified output (printed by the block above; the assertions passed on the same runs — 2026-10-09, re-run 2026-10-13, TypeScript port 2026-10-23):** D_n for n = 2..9 = 1, 2, 9, 44, 265, 1854, 14833, 133496 — three engines agree everywhere (n = 0..10, boundary cases D₀ = 1 and D₁ = 0 included); D₉/9! = 0.36788 ≈ 1/e (Lecture 1.4, live). Catalan n = 0..10 = 1, 1, 2, 5, 14, 42, 132, 429, 1430, 4862, 16796 — recurrence, reflection difference, and closed form agree. The assertions certify more than the prints show: the nearest-integer bound |D_n − n!/e| < 1/(n+1) holds for n = 1..10 (Exercise 9's bound, live), and the Lecture 3/4 identities hold at every size tested — Vandermonde for all m, n ≤ 5 and r ≤ m+n, Σ C(n,k) = 2ⁿ and Σ k·C(n,k) = n·2ⁿ⁻¹ for n = 0..10, with the n = 0 case reading 0 = 0 as §3.2 records.

### Part 2 — the reflection bijection, machine-tested (verified 2026-10-10; re-run 2026-10-13; re-run 2026-10-23 as a TypeScript port, boundary sizes added)

A formula can lie about being a bijection — and, in fairness, so can code: a small-case test is an error *detector*, not a proof (the nearest-integer property of Exercise 9 (worked in A9) is settled by an argument, not by a tally, and no finite run of code replaces that). What code adds is a check the eye cannot fake. Lecture 2.1's map, together with its inverse (first touch of x = y+1), round-tripped over **all** small paths — the test that separates a bijection from a coincidence of totals:

```python
from itertools import combinations
from math import comb

def all_paths(a, b):
    if a < 0 or b < 0:
        return set()
    steps = a + b
    return {''.join('E' if i in east else 'N' for i in range(steps))
            for east in combinations(range(steps), a)}

def first_touch_index(p, target):   # earliest step k where (y - x) == target
    x = y = 0
    for k, s in enumerate(p):
        x += (s == 'E'); y += (s == 'N')
        if y - x == target:
            return k
    return None

def forward(p):    # bad path to (n,n): swap head at first touch of y - x = +1
    k = first_touch_index(p, +1)
    if k is None:
        return None                  # no touch: map undefined -- bug alarm
    return p[:k+1].translate(str.maketrans('EN','NE')) + p[k+1:]

def inverse(q):    # any path to (n+1, n-1): swap head at first touch of y - x = -1
    k = first_touch_index(q, -1)
    if k is None:
        return None
    return q[:k+1].translate(str.maketrans('EN','NE')) + q[k+1:]

for n in range(5):                   # includes the boundary sizes n = 0 and 1
    total = all_paths(n, n)
    bads = [p for p in total if forward(p) is not None]
    goods = [p for p in total if forward(p) is None]
    images = [forward(p) for p in bads]
    mirror = all_paths(n+1, n-1)
    assert len(bads) == len(set(images)) == len(mirror) == (comb(2*n, n-1) if n >= 1 else 0)
    assert len(goods) == comb(2*n, n) // (n + 1)           # the good count is C_n
    assert set(images) == mirror                          # bijection onto the mirror world
    assert all(inverse(forward(p)) == p for p in bads)    # round trip, bad side
    assert all(forward(inverse(q)) == q for q in mirror)  # round trip, mirror side
    assert all(first_touch_index(p, +1) == first_touch_index(forward(p), -1)
               for p in bads)                             # first-touch index preserved
    if n in (2, 3):
        print("n =", n, "|", len(bads), "bad of", len(total))
        print("      ", len(set(images)), "images,", len(mirror), "mirror paths")

assert forward('EEEN') is None   # the WRONG inverse hunts y = x+1 here: nothing to find
```

**Verified output (2026-10-10; the block prints the counts and asserts the rest; re-run 2026-10-23 as a TypeScript port, with the boundary sizes added):** n = 2 — 4 bad paths (of 6 total), 4 distinct images, all 4 paths to (3,1) covered, both round trips exact. n = 3 — 15 bad paths (of 20; 20 − C₃ = 20 − 5 = 15 ✓), 15 distinct images, all 15 paths to (4,2) covered, both round trips exact. At the boundary sizes the same assertions hold: n = 0 (one path, the empty one, trivially good — no bad paths, no mirror), n = 1 (two paths; the single bad path NE ↔ its mirror EE, and good = 1 = C₁), and at every size n = 0..4 the counts match the closed forms — bad = C(2n, n−1), good = C_n, mirror total = bad — with the **first-touch index m preserved under the map in both directions** (m for y = x+1 forward, m for x = y+1 back), the §2.1 proof's key invariant witnessed by machine. And `forward('EEEN')` returns **None**: a path to (3,1) never touches y = x+1 — the alarm that proves the inverse must search for **x = y+1**. *The lesson: when a chapter claims a bijection, the lab implements the map **and its inverse** and round-trips everything — matching totals certify a count, never a correspondence.*

**What to explore:** plot D_n·e/n! for n = 1..15 approaching 1 — and note that A9 proves the nearest-integer property *never* fails, so do not hunt a counterexample; instead watch the true rounding residual |D_n − n!/e| against its proven bound 1/(n+1) — the first omitted term of the alternating series — and measure how tightly it tracks the true error.

---

## Answers to the Exercises

*Attempt everything first — the value is in the attempt; these pages will still be here when you return.*

**A1.** D₁₀ = 9·(D₉ + D₈) = 9·(133496 + 14833) = **1,334,961**. Then D₁₀/10! = 1334961/3628800 ≈ **0.3678795** ≈ 1/e ✓ — Lecture 1.4, live at n = 10.

**A2.** Total paths to (5,5): C(10,5) = 252. A bad path first touches y = x+1; reflect its head through that line — a path ending at (6,4) instead, of which there are C(10,4) = 210. Good: 252 − 210 = **42** = C₅ ✓ (the map inverts honestly: a path to (6,4) has x − y travelling from 0 up to 2, so it touches x = y + 1 somewhere, and swapping the head at the *first* such touch returns the bad path — the same two-sided check as Lecture 2.1).

**A3.** Direct: C(9,3) = 84. By composition (k women from 5, 3−k men from 4): k=0: 1·4 = 4; k=1: 5·6 = 30; k=2: 10·4 = 40; k=3: 10·1 = 10. Sum 4+30+40+10 = **84** ✓. One world, two bookkeepings.

**A4.** Length 6: **()()(), ()(()), (())(), (()()), ((()))** — five strings = C₃ ✓. Why does C_n count balanced strings of length 2n in general? Replace every ( with an East step E and every ) with a North step N: a string is balanced if and only if it has n of each and every prefix contains at least as many ( as ) — which is x ≥ y at every step, step by step — so the substitution is a bijection onto the good Catalan paths of Lecture 2. For length 8, then: **C₄ = 14** (from the recurrence C₄ = C₀C₃ + C₁C₂ + C₂C₁ + C₃C₀ = 5+2+2+5, or the closed form).

**A5.** All strings: 3⁴ = 81. Missing a given letter: 2⁴ = 16 each (×3); missing two given letters: 1 each (×3); missing all three: 0. Inclusion–exclusion: 81 − 48 + 3 − 0 = **36**. (Note the overlap repair — plain subtraction would give nonsense, exactly as in Lecture 1.1.)

**A6.** Make the identical letters distinguishable, then divide the collapse away (P1). BANANA has six letters — one B, three A's, two N's — so the labeled word B A₁ N₁ A₂ N₂ A₃ has 6! = 720 labelings. Each printed arrangement comes from exactly 3! · 2! = 12 of them (relabel the A's, relabel the N's), so the count is 720/12 = **60**. MISSISSIPPI: 11!/(4!·4!·2!) = 39,916,800/1,152 = **34,650**. Second engine, as a check: choose the 4 positions holding S (C(11,4) = 330), then the 4 positions holding I among the rest (C(7,4) = 35), then the 2 positions holding P (C(3,2) = 3), and the M's fill what remains: 330·35·3 = 34,650 ✓. Two engines agreeing is Lecture 3's habit wearing a different coat. The general law: a word of n letters with multiplicities n₁,…,n_r has n!/(n₁!·…·n_r!) distinct arrangements.

**A7.** Choose n people from two rooms holding n each. Directly: C(2n,n) ways. By composition (k from room 1, n−k from room 2): Σ_k C(n,k)·C(n,n−k) = Σ_k C(n,k)². Equate. ∎ *(Third costume: lattice paths from (0,0) to (n,n), sorted by where they cross the antidiagonal x + y = n — at (k, n−k), in C(n,k)² ways.)*

**A8.** From D(x) = e^{−x}/(1−x), multiply both sides by (1−x): **(1−x)·D(x) = e^{−x}**. Now match the coefficients of the *plain power* xⁿ — and mind the bookkeeping, because with plain powers the factorial machinery stays visible. Left side: D(x) contributes D_n/n! (its xⁿ term), and x·D(x) contributes its own xⁿ term, which is the xⁿ⁻¹ term of D(x) shifted up one place: D_{n−1}/(n−1)! — the same number as n·D_{n−1}/n!. Right side: e^{−x} contributes (−1)ⁿ/n!. So **D_n/n! − D_{n−1}/(n−1)! = (−1)ⁿ/n!**, and multiplying through by n!: **D_n − n·D_{n−1} = (−1)ⁿ**. ∎ Check: D₅ = 44 = 5·9 − 1 ✓. (You can instead stay in the normalized EGF basis the whole way: there x·D(x) = Σ_n n·D_{n−1}·xⁿ/n! — the one-power shift costs exactly a factor n — and matching the coefficients of xⁿ/n! on both sides gives D_n − n·D_{n−1} = (−1)ⁿ directly, with no final multiplication. Both bookkeepings are honest and equivalent; the one error to avoid is writing one convention's numbers under the other convention's label.)

**A9.** D_n/n! = Σ_{k=0}^n (−1)^k/k!, so the difference is exactly **minus** the discarded tail: D_n/n! − 1/e = −Σ_{k=n+1}^∞ (−1)^k/k!. An alternating series with decreasing terms has a tail smaller in magnitude than its first omitted term: |D_n − n!/e| = n!·|tail| < n!/(n+1)! = 1/(n+1) ≤ 1/2. An integer within ½ of n!/e is unique, so D_n is it — the nearest-integer property *never* fails. ∎ (Check: D₄ = 9, 4!/e ≈ 8.83 ✓.)

**A10.** Choose which letter is fixed: n ways. The remaining n−1 letters must all go wrong: D_{n−1} ways. Total **n·D_{n−1}**. Check n=3: 3·D₂ = 3 = the three transpositions ✓.

**A11.** Fix the geometry first — this is where it is easy to slip. With p ≥ q, the endpoint (p,q) is *on or below* the diagonal, so the right weak version is: paths (0,0)→(p,q) staying **weakly below** (y ≤ x). Bad paths first touch y = x+1 — Lecture 2.1's own forbidden line. Swap the head up to that first touch: a prefix with a East-steps and a+1 North-steps becomes a+1 E's and a N's, re-aiming the whole path from (p,q) at **(p+1, q−1)**. Every path to (p+1, q−1) inverts this — its x − y climbs from 0 to p − q + 2 ≥ 2 in steps of ±1, so it first touches x = y+1, and swapping its head returns the bad path — a genuine two-way bijection, the bad side counted by C(p+q, q−1). So the weak count is C(p+q, q) − C(p+q, q−1) = **(p−q+1)/(p+1) · C(p+q, q)**. *Now the strict version:* A strictly ahead after every ballot ⇔ the first step is East, and after deleting it the translated path (0,0)→(a−1, b) is weakly below. Apply the weak formula with p = a−1, q = b: (a−b)/a · C(a+b−1, b) = (a−b)/a · a/(a+b) · C(a+b, b) = **(a−b)/(a+b) · C(a+b, b)**. ∎ Check a=2, b=1: 1/3 · 3 = 1 — and indeed AAB is the only ordering with A strictly ahead after every ballot (after 1: 1–0 ✓; after 2: 2–0 ✓; after 3: 2–1 ✓), while ABA ties at ballot 2 ✗ and BAA is behind at ballot 1 ✗. (Edge cases: at b = 0 the strict formula reads (a−0)/(a+0) · C(a, 0) = 1 — the all-A ordering, correct; and at q = 0 the weak count is 1 — the single all-East path — exactly as the weak formula says: (p−0+1)/(p+1) · C(p, 0) = 1.)

**A12.** Total delegations: C(14,5) = 2,002. Let E_c be the delegations containing couple c (both spouses). Zigzag (P3): |E_c| = C(12,3) = 220 (the couple is in, choose the other 3 from the remaining 12 people); any two couples fit together, so |E_c ∩ E_{c'}| = C(10,1) = 10 (4 people fixed, choose the fifth from the remaining 10); and *three* couples need 6 people, which a 5-person delegation cannot hold — the zigzag honestly stops at k = 2, which is exactly the point the hint nudges you to notice. So the answer is 2,002 − C(7,1)·220 + C(7,2)·10 = 2,002 − 1,540 + 210 = **672**. Machine check: enumerating all 2,002 five-person subsets, exactly 672 contain no married couple ✓ — the transplant of Lecture 1 is sound, and the early-stopping observation is what made the zigzag finite *and* obviously finite.

**A13.** Bijection (P1): write n as a row of n unit tokens with n − 1 gaps between them. Every composition is a choice of *which gaps to cut* — cut gaps split the row into blocks, the blocks are the summands, and gluing everywhere gives the one-summand composition n itself. There are 2^{n−1} subsets of gaps, so c_n = **2^{n−1}**. Recurrence (P4): condition on the first summand m (1 ≤ m ≤ n); what follows is a composition of n − m, so c_n = Σ_{m=1}^{n} c_{n−m} with c₀ = 1. The same equation read at n − 1 says c_{n−1} = Σ_{i=0}^{n−2} c_i, so c_n = c_{n−1} + Σ_{i=0}^{n−2} c_i = 2·c_{n−1} — and c₁ = 1 gives 2^{n−1} by induction. Machine check: n = 1..12 gives 1, 2, 4, 8, 16, 32, 64, 128, 256, 512, 1024, 2048, no exceptions ✓. The honest boundary: *order matters here* — 3+1 and 1+3 are different compositions. If you decide order *doesn't* matter (partitions), the count collapses (4 has 5 partitions, not 8) and no gap-bijection exists; that harder world is a different book's chapter.

**A14.** Count the pairs (S, T) with T ⊆ S ⊆ {1,…,n} and |T| = m. Way 1: pick the committee S first — if |S| = k, there are C(n,k) choices — then the subcommittee T ⊆ S: C(k,m) choices. Total: Σ_k C(n,k)·C(k,m). Way 2: pick the subcommittee T first (C(n,m) choices), then let the committee grow around it: every subset of the n − m outsiders may join S, 2^{n−m} choices. Total: C(n,m)·2^{n−m}. One set of pairs, two books (P2): **Σ_k C(n,k)·C(k,m) = C(n,m)·2^{n−m}**. ∎ Machine check: all n ≤ 12, all m — e.g. n = 8, m = 3 gives 1,792 both ways ✓. Notice the formula box's identities are the bottom rungs: m = 0 recovers Σ C(n,k) = 2^n, and m = 1 recovers Σ k·C(n,k) = n·2^{n−1}. The pattern generalizes: when an identity feels isolated, ask what two-order count produced it.

**A15.** Such a path stays strictly on one side of the diagonal in between (it cannot cross without touching). Take the above side: the first step must be N and the last must be E (any other first/last step lands on the wrong side or on the diagonal). Strip the forced pair: N [inner] E, where the inner path, translated down by one, runs (0,0)→(n−1, n−1) staying weakly above — count C_{n−1} by A10's weak formula (p = q = n−1 gives (1/n)·C(2n−2, n−1) = C_{n−1}). The below side gives another C_{n−1}. Total **2·C_{n−1}**. Check n=2: 2·C₁ = 2 ✓ (NNEE, EENN).

**A16.** Differentiating (1+x)ⁿ twice and evaluating at x=1: Σ k(k−1)C(n,k) = n(n−1)·2ⁿ⁻²; adding Lecture 3.2's Σ k·C(n,k) = n·2ⁿ⁻¹ gives Σ k²C(n,k) = n(n+1)·2ⁿ⁻². Then Σ(k − n/2)²C(n,k) = n(n+1)2ⁿ⁻² − n·(n·2ⁿ⁻¹) + (n²/4)·2ⁿ = 2ⁿ⁻²·(n² + n − 2n² + n²) = **n·2ⁿ⁻²**. ∎ Sanity: n=2: 1·1 + 0·2 + 1·1 = 2 = 2·2⁰ ✓.

**A17.** Let person 1 shake hands with person j. The chord 1–j splits the other 2n−2 people into two arcs of j−2 and 2n−j people; for no crossing, each arc must pair up internally, so **both numbers are even — j must be even**, j = 2i+2 (i = 0, …, n−1). Drawn for 8 people, with person 1 shaking person 4:

```
              8           1
            ·             ┃
          ·               ┃
        7                 ┃     2
        |                 ┃     |
        6                 ┃     3
          ·               ┃
            ·             ┃
              5           4
```

Clockwise from 1 to 4 the arc holds {2, 3} — 2 people, who must pair among themselves; clockwise from 4 back to 1 it holds {5, 6, 7, 8} — 4 people, pairing internally without crossing. And why must j be even? Try the chord 1–5 instead: the arcs become {2, 3, 4} and {6, 7, 8} — both *odd*, so someone would be forced to cross the chord.

The same table, drawn to scale as **Figure 3** — a true circle, the chord 1–4, and both arcs colour-coded with their counts and pairing counts:

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 925 880 372" font-family="system-ui, -apple-system, 'Segoe UI', sans-serif">
  <rect x="0" y="925" width="880" height="372" fill="#ffffff"/>
  <!-- ================= FIGURE 3 · The chord-split ================= -->
  <text x="40" y="950" font-size="17" font-weight="700" fill="#193e5c">Figure 3 &#183; The chord-split &#8212; handshakes around the table (exercise 13)</text>

  <circle cx="200" cy="1130" r="130" fill="none" stroke="#cbd5e1" stroke-width="1.5"/>
  <!-- arcs -->
  <path d="M 200,1000 A 130,130 0 0 1 292,1222" fill="none" stroke="#d97706" stroke-width="5"/>
  <path d="M 292,1222 A 130,130 0 1 1 200,1000" fill="none" stroke="#2563eb" stroke-width="5"/>
  <!-- chord 1-4 -->
  <line x1="200" y1="1000" x2="292" y2="1222" stroke="#dc2626" stroke-width="4"/>
  <text x="258" y="1108" font-size="11.5" fill="#dc2626">chord 1&#8211;4</text>
  <!-- people -->
  <g>
    <circle cx="200" cy="1000" r="7" fill="#ffffff" stroke="#172333" stroke-width="2"/><text x="200" y="982" font-size="13" font-weight="700" fill="#172333" text-anchor="middle">1</text>
    <circle cx="292" cy="1038" r="7" fill="#ffffff" stroke="#172333" stroke-width="2"/><text x="312" y="1034" font-size="13" font-weight="700" fill="#172333">2</text>
    <circle cx="330" cy="1130" r="7" fill="#ffffff" stroke="#172333" stroke-width="2"/><text x="348" y="1134" font-size="13" font-weight="700" fill="#172333">3</text>
    <circle cx="292" cy="1222" r="7" fill="#ffffff" stroke="#172333" stroke-width="2"/><text x="312" y="1240" font-size="13" font-weight="700" fill="#172333">4</text>
    <circle cx="200" cy="1260" r="7" fill="#ffffff" stroke="#172333" stroke-width="2"/><text x="200" y="1284" font-size="13" font-weight="700" fill="#172333" text-anchor="middle">5</text>
    <circle cx="108" cy="1222" r="7" fill="#ffffff" stroke="#172333" stroke-width="2"/><text x="88" y="1240" font-size="13" font-weight="700" fill="#172333" text-anchor="end">6</text>
    <circle cx="70" cy="1130" r="7" fill="#ffffff" stroke="#172333" stroke-width="2"/><text x="52" y="1134" font-size="13" font-weight="700" fill="#172333" text-anchor="end">7</text>
    <circle cx="108" cy="1038" r="7" fill="#ffffff" stroke="#172333" stroke-width="2"/><text x="88" y="1034" font-size="13" font-weight="700" fill="#172333" text-anchor="end">8</text>
  </g>
  <!-- annotations -->
  <g font-size="12.5" fill="#172333">
    <line x1="405" y1="1006" x2="435" y2="1006" stroke="#d97706" stroke-width="5"/>
    <text x="445" y="1010">arc {2, 3} &#8212; clockwise from 1 to 4</text>
    <text x="445" y="1032" fill="#64748b">2 people: they must pair among themselves &#8594; C&#8321; = 1 way</text>
    <line x1="405" y1="1066" x2="435" y2="1066" stroke="#2563eb" stroke-width="5"/>
    <text x="445" y="1070">arc {5, 6, 7, 8} &#8212; clockwise from 4 to 1</text>
    <text x="445" y="1092" fill="#64748b">4 people: pairing internally, no crossings &#8594; C&#8322; = 2 ways</text>
    <line x1="405" y1="1126" x2="435" y2="1126" stroke="#dc2626" stroke-width="5"/>
    <text x="445" y="1130">the chord 1&#8211;4 contributes a&#8321; &#183; a&#8322; = 1 &#215; 2 pairings</text>
    <text x="445" y="1170" fill="#64748b">j must be even: a chord 1&#8211;5 would strand the arcs</text>
    <text x="445" y="1190" fill="#64748b">{2, 3, 4} and {6, 7, 8} &#8212; both odd, forcing a crossing.</text>
  </g>
</svg>
```

The arcs then hold 2i and 2n−j = 2(n−1−i) people, pairable internally in a_i and a_{n−1−i} ways. So a_n = Σ_{i=0}^{n−1} a_i·a_{n−1−i} with a₀ = 1 — exactly the Catalan recurrence of Lecture 2.2, in the same "cut at the first return" costume. **a_n = C_n.** ∎ (Check 4 people: person 1 must pair with j = 2 or j = 4 — an odd j = 3 would strand one person on each side of the chord — giving (1,2)(3,4) and (1,4)(2,3): C₂ = 2 ✓.)

**A18.** Label the (n+2)-gon's vertices 0,…,n+1 and distinguish the edge (0, n+1). The triangulation's triangle sitting on this edge has third vertex k (1 ≤ k ≤ n) and splits the polygon into the (k+1)-gon on vertices 0..k and the (n−k+2)-gon on vertices k..n+1. Map: the triangle ↔ the outermost pair **( … )**, the left polygon ↔ what is inside the pair, the right polygon ↔ what follows it. Both sides then satisfy the same decomposition, so the counts agree by the same recurrence (Σ C_{k−1}C_{n−k} = C_n); or route everything through strings explicitly. Pentagon: 5 triangulations = C₃ ✓.

**A19.** The bad events are misses: E_j = "value j is never hit." A function avoiding a fixed set J of j values has (k−j)^n possibilities, so the zigzag (P3) over which values are missed gives the onto count: **Σ_{j=0}^{k} (−1)^j · C(k,j) · (k−j)^n**. For a 6-element set onto a 3-element set: 3⁶ − C(3,1)·2⁶ + C(3,2)·1⁶ = 729 − 192 + 3 = **540**. Machine check: of all 729 functions, exactly 540 hit every value ✓. Second engine, as a calibration: an onto function is a partition of the domain into k nonempty blocks (a Stirling number of the second kind, S(n,k)) followed by an assignment of blocks to values (k! ways) — k!·S(n,k) = 6·90 = 540 ✓. Sanity rungs: onto [5]→[5] gives 120 = 5! (when n = k the only onto functions are the bijections — the permutations of Lecture 1), and onto [n]→[1] gives 1. The derangement lesson transplanted: D_n comes from the same inclusion–exclusion, with the bad events "letter i lands home" — any j of them together leave (n−j)! arrangements, where the misses above leave (k−j)^n functions — and the rencontres numbers of X1 sit one step further along the same road.

**A20.** The graded exercises above hand you the pattern; here you must *find* it. So do what a researcher does: compute small cases. n = 0: 1 (the empty set). n = 1: 2. n = 2: 3 ({}, {1}, {2}). n = 3: 5. n = 4: 8. That sequence — 1, 2, 3, 5, 8 — is Fibonacci wearing a disguise, and now it must be *explained*, not just recognized. Let a_n count the subsets of {1,…,n} with no two consecutive. A subset either avoids n — a_{n−1} choices — or contains n, and then it cannot contain n−1, leaving a subset of {1,…,n−2}: a_{n−2} choices. So **a_n = a_{n−1} + a_{n−2}** with a₀ = 1, a₁ = 2 — the Fibonacci recurrence with shifted seeds, **a_n = F_{n+2}** (counting F₁ = F₂ = 1). ∎ Check n = 3 by listing: {}, {1}, {2}, {3}, {1,3} — 5 ✓. (The tool was P4, the recurrence — but the *diagnosis* was the exercise: experiment first, then the forced case analysis on element n.)

**A21.** The move is a **bijection** (P1), and it is one line: pair every subset S with the set obtained by toggling the membership of the element 1 (remove 1 if present, add it if absent). Toggling one element flips the parity of the size, so the pairing matches even-sized subsets with odd-sized ones; applying it twice returns S, so nothing is paired with itself — and neither side can outnumber the other. Both counts are **2ⁿ⁻¹**. ∎ Check n = 2: even {}, {1,2}; odd {1}, {2} ✓ — and watch the pairing do the work: {} ↔ {1} and {2} ↔ {1,2}. (Second costume: Σ_k (−1)^k C(n,k) = (1−1)ⁿ = 0 for n ≥ 1 — Lecture 1.1's zigzag collapsing to zero precisely because every even-sized subset (a +1 in the sum) has an odd-sized partner (a −1). One engine is a map; the other is a sum; the truth is the same.)

**A22.** No chapter formula covers this — which is the point. Experiment first: one line cuts the plane into 2 regions; two into 4; three into 7; four into 11. The *differences* are 2, 3, 4 — each new line adds one more region than the last one did. Now explain the pattern, because a conjecture without a reason is a rumor. The n-th line crosses each of the n − 1 earlier lines exactly once (no parallels, no triple crossings), so it is sliced into n pieces — and *each piece cuts one existing region into two*, adding one region per piece: **R_n = R_{n−1} + n**, with R₀ = 1. Telescoping: **R_n = 1 + (1 + 2 + … + n) = 1 + n(n+1)/2**. ∎ Check: n = 4 gives 11 ✓, n = 5 gives 16 — draw five lines and count. (The tool was again P4, but its *seed* was the experiment — the discovery cycle, running.)

---

## Revision History & Verification Notes

*The lectures above should read like a finished book; the development record lives here, so the body never interrupts itself with its own history.*

**Editions.** Reference edition → Feynman lecture edition → graded exercises with worked answers → three external reviews, each audited claim by claim before anything was changed. The reviews repaired, in order: a wrong reflection-bijection inverse (now machine-tested in both directions; the lesson, now an Atlas-wide lab rule, is that a lab must implement a claimed bijection's map *and* its inverse and round-trip everything), the Catalan decomposition's orientation, derangement-recurrence bookkeeping, ballot geometry, handshake indexing, and a lab contradiction (first review); the ordinary-vs-exponential generating-function distinction, the C₃ indexing, small-case-test honesty (second review); the two-mirror geometry of §2.1, the A16 worked-example classification, and the A8 tail sign (third review). The ✎ discovery checkpoints, ◐ Explorations, ◆ pattern-unknown exercises, and working diagrams were added along the way.

**Verification record.** The derangement engines agree (recurrence vs. inclusion–exclusion, n = 2..9; D₁₀ = 1,334,961) and the Catalan recurrence matches the closed form to n = 10. The reflection bijection and its inverse round-trip over all paths for n = 2 and n = 3, with the wrong-inverse alarm demonstrated (`forward('EEEN')` returns None). Both geometric readings of the reflection — the head mirrored in y = x + 1 with the whole path lifted by (1, −1), and the head mirrored in y = x with the tail shifted by (1, −1) — have been machine-checked to produce the identical image for all 76 bad paths with n ≤ 4. Every worked answer A1–A17 was re-derived independently (book closed) and then machine-verified: D₁₀ = 1,334,961 with D₁₀/10! = 0.3678795; good paths to (5,5) = 42 of 252 with bad = 210 = C(10,4); committee composition 4+30+40+10 = 84; the five length-6 strings exactly as listed and 14 at length 8; 36 of 81 strings contain all three letters; Σ C(n,k)² = C(2n,n) for n ≤ 12; D_n − n·D_{n−1} = (−1)ⁿ for n ≤ 14; D_n the nearest integer to n!/e with error < 1/(n+1) for n ≤ 12; exactly-one-fixed = n·D_{n−1} for n ≤ 7; ballot brute force = (a−b)/(a+b)·C(a+b,a) on six (a,b) pairs (1, 2, 2, 5, 5, 14) and weak counts = C(p+q,q) − C(p+q,q−1); touch-only-at-endpoints = 2·C_{n−1} for n = 2, 3, 4; Σ (k−n/2)²·C(n,k) = n·2ⁿ⁻² for n ≤ 10; non-crossing pairings = C_n with person 1's partner even in every single one; triangulations by diagonal-set exhaustion (pentagon 5, hexagon 14, heptagon 42); A15–A17 enumerated for n ≤ 10. Discrepancies across all passes: none — apart from the two the third review caught in the worked examples (the A16 classification, the A8 sign), which is precisely why independent eyes stay welcome.

**On the lab code and PDF rendering.** Both Python labs are stored with correct 4-space indentation and the recorded outputs come from real executions; the source has been audited at the byte level — every indentation character a plain 0x20 space (leading-space census exactly {0, 4, 8, 12, 15}), both blocks 100% ASCII. Nine external inspections have now reported the same damage in the exported PDF: the loop body of `D.append` rendering to the LEFT of its `for` header (measured: 73.35 pt vs 78.75 pt), the reflection block split across pages 9–10, and — in the latest inspections, machine-confirmed from the attached PDF itself — the deep indentation levels absent from the extracted text (census {0, 4} against the source's {0, 4, 8}), so the printed code does not even compile. The defect is the export pipeline's, not the source's; there is nothing left in the source to fix. The full remedy — the two-layer diagnosis (text layer vs rendering layer), the export fix (`white-space: pre`, `break-inside: avoid`), the two-stage post-export test (an HTML gate plus a PDF gate that reads the PDF itself), and standalone runnable copies of both labs, plus a reference web edition that embeds this chapter byte-identically and prints to a correctly indented PDF from any browser — now lives in the Atlas publishing toolkit, keeping this appendix to mathematics. Until the pipeline is repaired, the definitive test remains execution: both labs are plain Python and run in under a second on a Raspberry Pi, and the recorded outputs above are the reference to compare against.

**Figures.** Each of the three hard pictures appears twice, side by side: as ASCII (it renders identically in any editor or terminal, down to a Raspberry Pi console) and, immediately after, as an embedded vector figure — labelled axes, colour-coded steps, arc annotations — each drawn as one self-contained image that no page break can cut in half. The in-text embedding was added by direct user request after the freeze: the one non-error change since. (A companion canvas, "Chapter 1 — Figures", once carried the same three figures as a single combined vector sheet for export pipelines; at user direction it has since been removed, the in-text figures having made it redundant — nothing was redrawn, the embedded figures are byte-identical to the sheet it carried.)

**Independent verification.** The third review's author reports fresh exhaustive checks passing for the reflection map and its inverse (n = 1..7), for band-restricted Catalan paths (n = 1..8), and for the recurrences of A15 and A17.

**Revision pass (2026-10-13).** A full-text review in two roles — mathematical content, and publishing and code — with every worked answer A1–A22 re-derived and machine-checked and both labs re-run. No mathematical result changed. Repaired: the §1.4 comparison (three letters give 33.3%, not 36.8%; it now says six letters); the §1.2 seed statement (D₀ and D₁, as in the lab code); a stray fragment in Lecture 1; the exercise numbering (the five exercise lists now carry start attributes, so the printed numbers match A1–A22 and the cross-references); the statement and hint of exercise 11 (either side of the diagonal; the answer 2·C_{n−1} stands); the unclosed group in Figure 3's SVG (the only change to any of the three SVG figures); the column alignment of the vertical steps and the chord in the three ASCII figures; the labs (printed output added so the recorded numbers reproduce, and the Catalan assertion now covers n = 0..10); the stale counts and freeze status in the chapter status line and the preface; history references that had crept into Lab Part 2; and a few wording points (the §2.3 costume list, the slope of the reflecting lines, the P2 line of the reference card, the pattern tag on the ballot hint, the asides in A6, A16 and A22, and the reason given in A10 for the inverse's first touch, which held only when p = q).

**Standing decision.** The lecture text of this chapter was frozen from session 10 to session 40 — error repairs only. **The freeze was lifted at user direction (session 41), and the graded backfill (exercises 18–22 with answers A18–A22, every number machine-verified before installation: BANANA 60 / MISSISSIPPI 34,650 by two engines; the couples' banquet 672 by zigzag and by exhaustive census of all 2,002 subsets; compositions 2^{n−1} for n = 1..12 by direct enumeration; the committee–subcommittee identity for all n ≤ 12, all m; onto functions brute-counted against the zigzag for n ≤ 7 and cross-checked against k!·S(n,k)) is the first post-freeze addition, recorded here.** New chapters inherit the full standard from the start: graded exercises with worked answers, ✎ checkpoints, ◐ Explorations, ◆ pattern-unknown problems, working diagrams, machine-tested labs, and this appendix in place of inline history.

**Survey-adoption pass (session 80).** Two face notes from the paper-pattern survey's chunk-15 synthesis (papers/ANALYSIS.md, §2, in the cgt-atlas-backup repo) were installed in the Trick Bag, executing the survey's recommendation to name celebrated faces inside existing pattern entries rather than mint new IDs: the **sign-reversing involution** is now named as P1's dynamic face — pair the unwanted objects with a sign-flipping swap and they cancel from an alternating sum (Gessel–Viennot, the survey's firing) — and the **monovariant** is now named as P4's termination face — a quantity that strictly improves at each step certifies that the recursion bottoms out (the survey's firings: phase distance, augmenting-path length, regularity energy). No proof, exercise, or answer changed. The web edition's embedded payload and the .html export were rebuilt per the rebuild rule, fidelity-first.

**Usage-evidence note (session 83).** The paper-pattern survey's chunk-15 synthesis (papers/ANALYSIS.md, §3–§4, in the cgt-atlas-backup repo) records the honest negative for this chapter's reflection card: P6 fired in ZERO of the survey's 133 papers across 14 batches — the only textbook-canon pattern with none. The note installed in the Trick Bag's P6 row presents the pattern as what it is: textbook canon, a proof-shape every counter should own (Exercise 10's ballot problem runs it), not field-visible practice. No proof, exercise, or answer changed. The .html export is rebaked at this session's export pass.

**Expansion pass (2026-10-23, session 85).** The expansion campaign's pilot pass, built from a user-supplied updated draft compared line by line against this master. Adopted: the full zigzag weight-counting proof of §1.1 (follow one arrangement π through the alternating sum; binomial theorem at x = −1); the §1.3 coefficient-extraction walkthrough; the formal Φ/Ψ bijection proof of §2.1 (the first-touch index m = 2t+1 shown preserved in both directions — closing the gap where the chapter had asserted the inverse without proving the returned path's first touch); the §2.2 closed-form derivation (minus-branch selection, Newton's generalized binomial, the odd/even product completion); the n = 0 edge of §3.2; the exercise sets reorganized into strict tiers (6 easy, 8 moderate, 5 tough, 3 ◆ — the former graded-backfill block folded into the tiers, faithful to its own ● ratings) with strengthened hints (the explicit reflected endpoint and inverse boundary on the (5,5) walk; the proof demand on the parens exercise; the nearest-integer bound in place of a bare bound; the a > b ≥ 0 ballot range; the unit-token formulation of the compositions; the n, k ≥ 1 domain and the k−j landing values on the onto functions; the invertibility demand and pentagon check on the triangulations); the annotated formula box (seeds and domains stated, C(a,b) = 0 for b > a); and both labs expanded — a third derangement engine D_n = n·D_{n−1} + (−1)ⁿ (Exercise 8's, now machine-checked), the mirror difference C(2n,n) − C(2n,n−1) as a Catalan engine, boundary cases n = 0..10, Vandermonde and the two subset identities asserted (n = 0 included), and Part 2 extended to the boundary sizes n = 0 and 1 with the first-touch-index preservation asserted at every size. The worked answers were renumbered A1–A22 to match the new exercise numbers, reordered physically, and strengthened at A4 (the parens bijection proof supplied) and A11 (the b = 0 and q = 0 edge cases). Restored from the survey-adoption passes, which the draft had dropped: P1's sign-reversing involution face with its Gessel–Viennot attribution, P4's monovariant face, and P6's usage-evidence note (its ballot reference renumbered to Exercise 11); the dropped lab verification dates were re-established honestly — both labs ported line for line to TypeScript and re-executed on 2026-10-23, all assertions and prints reproduced, recorded as a TypeScript port. Rejected: the draft's export conventions (a MathJax CDN script with $-source TeX — this book ships pre-rendered, script-free HTML per the export rule), so its content was merged into the master and the export rebaked from the merged text; and its rewrites of A9, A12, A13 and the X1/X2 explorations, judged equivalent or weaker than the standing text. No pattern ID was misassigned anywhere in the draft — the mangling was the dropped face notes and the renumbering-sensitive cross-references, both repaired here (including two stale references to the nearest-integer property as Exercise 8/A8, now Exercise 9/A9, caught in the lab introduction and the exploration tail). The .html export is rebaked from this master at this session's export pass.

---
*Chapter status: ✅ **Feynman edition — mathematically ready.** 4 lectures with ✎ discovery checkpoints, two verified labs, 22 exercises with worked answers (19 graded in three tiers — 6 easy, 8 moderate, 5 tough — + 3 ◆ pattern-unknown, all independently re-derived & machine-verified), 2 ◐ Explorations, vector figures embedded in-text, and this Revision History appendix. Three external reviews audited claim by claim, nine external inspections of the exported PDF, the 2026-10-13 revision pass, and the 2026-10-23 expansion pass; the mathematical revision cycle is **closed** — the mathematics stands ready, and the one open issue (code indentation in the exported PDF) belongs to the publishing pipeline, tracked in the Atlas publishing toolkit. **Freeze**: lifted at user direction in session 41 (see *Standing decision*); the in-text figure embedding and the companion-canvas removal were the two earlier user-directed exceptions, recorded under *Figures*. Next in the Atlas queue: Chapter 6's Feynman rewrite.*