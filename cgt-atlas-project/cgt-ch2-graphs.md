---
name: "cgt-ch2-graphs"
title: "Ch. 2 — Graph Theory Core: A Lecture Course in the Feynman Style"
type: "text/markdown"
---

# Chapter 2 · Graph Theory Core

*A lecture course in the spirit of Chapter 1: the idea before the formula, the story before the proof, and the proof as a conversation. Every method of the reference canon is preserved inside the narrative; the problem families run from handshaking to the subject's crown jewels — Dirac's theorem, its degree-sequence refinements (Pósa and Chvátal), and the Gallai–Milgram path-cover theorem — and the computational lab verifies Dirac, Pósa, Chvátal's closure lemma, and Gallai–Milgram by exhaustion.*

## How to read this chapter

Read it slowly, with a pencil. Chapter 1 taught you to count *collections*; this chapter is about *structure* — what the wiring of things forces, regardless of what the things are. A **graph** is just dots and lines: cities and roads, people and friendships, letters and envelopes' addresses. Because the dots have no meaning, whatever we prove is true of every wiring in the world — that is the whole secret of the subject's power.

**Notation.** G = (V, E), n = |V| vertices, m = |E| edges, d(v) = degree of v, δ and Δ = min and max degree, N(v) = neighbors of v. Graphs are finite, undirected, and simple unless a lecture says otherwise — multigraphs enter with Königsberg.

**The exercises are graded:** ●○○ *easy* (a direct application of one lecture idea), ●●○ *moderate* (two ideas, or one tricky step), ●●● *tough* (several chapter ideas combined). Hints travel with the problems; worked answers sit at the very end of the chapter. Try honestly before reading a hint — the struggle is the part of learning that cannot be outsourced. Beyond the graded set, ◆ **pattern-unknown** problems name no method and carry no hint: diagnosing which tool fits is part of the problem. And ◐ **Explorations** at the end are open-ended investigations with no single right answer — research training, not test preparation.

---

## Lecture 1 · What Degrees Force

Here is a puzzle that looks like a parlor trick: *at any party, an even number of people have shaken hands an odd number of times.* Prove it — and, more importantly, find the machine behind it.

### 1.1 Count the ends of the handshakes

Don't track people; track *ends of handshakes*. A handshake has two ends — that sounds too obvious to be useful, and it is the whole proof. Make a table: rows are the n people, columns are the m handshakes, and put a ✓ wherever a person participated in a handshake. Now count the check marks two ways.

**By rows:** person v has one ✓ per handshake they were in — that is exactly d(v), the number of hands v shook. Row-total: Σ_v d(v).
**By columns:** every handshake column has exactly two ✓'s. Column-total: 2m.

One table, two totals — and the totals must agree, because they count the *same marks*:

**Σ_{v∈V} d(v) = 2m** — the Handshaking Lemma. (Pattern **P2**: count one world two ways.)

Check it on something small before trusting it. Take the triangle {A,B,C} with a pendant D hanging off C: degrees are 2, 2, 3, 1; the sum is 8; and indeed m = 4, so 2m = 8. ✓

### 1.2 Parity falls out for free

Now the party puzzle. Σd(v) = 2m is *even*. Split the sum into even and odd summands: the even ones contribute an even amount, so the odd ones must too — and a sum of odd numbers is even exactly when there is an *even number of them*. Done: an even number of people are odd handshakers. (Pattern **P7**.)

Notice the strange power of this argument: we could not tell you *which* people are odd, or how many — only that the count is even. Parity arguments are the bargain basement of mathematics: almost no information in, one bit of unbreakable truth out. For instance, *no graph can have exactly one odd-degree vertex* — not because of anything about graphs, but because of arithmetic.

### 1.3 Build the graph one edge at a time (a second engine)

Here is the same theorem, explained by *history* instead of *structure*. Start from no edges (Σd = 0 ✓) and add edges one at a time. Each new edge raises two degrees by one each: the sum grows by 2, so it stays twice the edge count — the identity again. And look at the odd vertices: a new edge flips the parity of exactly two of them, so the *number* of odd vertices changes by −2, 0, or +2 — it stays even forever. The parity fact again, from the construction this time. (Pattern **P4**.)

Two explanations of one fact, one static (the table) and one dynamic (the build) — when something is true, hunt both. Each explanation generalizes in a different direction, and you will meet both again: the table becomes double counting, the build becomes induction.

### 1.4 Two people with the same degree (the pigeonhole with one box removed)

One more degree fact, and it hides a lesson about *rescuing* failed proofs. Claim: in any graph on n ≥ 2 vertices, two vertices have the same degree. (In any group of n people, two have the same number of friends in the group.)

Try pigeonhole naively: degrees live in {0, 1, …, n−1} — that is n boxes for n vertices. Not enough! Pigeonhole needs more objects than boxes, and we are exactly one short. Most people quit here. Instead, inspect the failure: the proof would work if one *box* were unavailable. Is it? Boxes 0 (an isolated vertex) and n−1 (a vertex adjacent to *everyone*) cannot both be occupied — a universal vertex shakes everyone's hand, so nobody is isolated. So the n vertices really live in at most n−1 usable boxes, and two share one. ∎ (Pattern **P9**, refined form.)

**The lesson, stated so you'll reuse it:** when a pigeonhole count fails by exactly one, look for two categories that cannot be simultaneously occupied. A proof that fails by a hair is not a failure — it is a map, with an X marking the extra fact you need.

**What you now own:** the ends-table (P2/P7), the static-and-dynamic double explanation, the missing-box pigeonhole.

---

## Lecture 2 · The Walk That Cannot End

Now the first structural theorem. Suppose every vertex of a graph has degree at least 2 — every room in the house has at least two doors. Must the graph contain a cycle?

Feel it as a story first. You walk through the house by the rule: *never turn around* — enter a room by one door, leave by another. Since every room has two doors, you can always leave. So the walk never gets stuck; but the house is finite; so the only possible ending is that you walk into a room you have seen before. And the moment that happens, you have found a closed loop: a **cycle**. Two ways to make this honest:

### 2.1 Corner the endpoint (the longest-path method)

Take a **longest path** in the graph, P = v₀v₁…v_k. "Longest" is not a description — it is a weapon. Look at the endpoint v₀: every neighbor of v₀ lies *on P*, because a neighbor outside P would let us extend the path, contradicting longest-ness. The endpoint is cornered. But d(v₀) ≥ 2, so v₀ has some neighbor v_j with j ≥ 2 (its other neighbor is v₁, the path itself). Then v₀v₁…v_jv₀ is a cycle. ∎ (Pattern **P8** — *the extremal object is so rigid that its border has nowhere to hide.*)

The same moment, drawn — the cornered endpoint, its trapped neighbors, and the chord that closes the cycle:

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 880 330" font-family="system-ui, -apple-system, 'Segoe UI', sans-serif">
  <rect x="0" y="0" width="880" height="330" fill="#ffffff"/>
  <text x="40" y="34" font-size="17" font-weight="700" fill="#193e5c">Figure 1 &#183; The cornered endpoint &#8212; the chord closes the cycle (&#167;2.1)</text>
  <g stroke="#94a3b8" stroke-width="3">
    <line x1="512" y1="235" x2="656" y2="235"/>
    <line x1="656" y1="235" x2="800" y2="235"/>
  </g>
  <g stroke="#2563eb" stroke-width="4">
    <line x1="80" y1="235" x2="224" y2="235"/>
    <line x1="224" y1="235" x2="368" y2="235"/>
    <line x1="368" y1="235" x2="512" y2="235"/>
  </g>
  <path d="M 80 220 Q 296 70 512 220" fill="none" stroke="#dc2626" stroke-width="3.5"/>
  <g fill="#ffffff" stroke="#2563eb" stroke-width="3">
    <circle cx="80" cy="235" r="13"/><circle cx="224" cy="235" r="13"/><circle cx="368" cy="235" r="13"/>
    <circle cx="512" cy="235" r="13"/><circle cx="656" cy="235" r="13"/><circle cx="800" cy="235" r="13"/>
  </g>
  <circle cx="80" cy="235" r="13" fill="none" stroke="#dc2626" stroke-width="3"/>
  <g font-size="14" font-weight="600" fill="#172333" text-anchor="middle">
    <text x="80" y="272">v&#8320;</text><text x="224" y="272">v&#8321;</text><text x="368" y="272">v&#8322;</text>
    <text x="512" y="272">v&#8323;</text><text x="656" y="272">v&#8324;</text><text x="800" y="272">v&#8325;</text>
  </g>
  <text x="296" y="100" font-size="12.5" fill="#dc2626" font-style="italic" text-anchor="middle">the second neighbor v&#8323; &#8212; the chord</text>
  <text x="104" y="196" font-size="12.5" fill="#2563eb">the cycle v&#8320;v&#8321;v&#8322;v&#8323;</text>
  <text x="584" y="216" font-size="12.5" fill="#64748b">rest of the longest path</text>
  <text x="40" y="314" font-size="12" fill="#64748b">d(v&#8320;) &#8805; 2 and every neighbor on P, so some neighbor v_j has j &#8805; 2 &#8212; and the chord v&#8320;v_j closes a cycle.</text>
</svg>
```

### 2.2 Just walk (the first-repeat method)

Or run the story literally. Start anywhere and walk: at each step from v_i, step to any neighbor *other than* v_{i−1} — always possible, since every vertex has ≥ 2 neighbors. The walk is infinite, the vertex set is finite, so some vertex repeats. Take the **first** repeat: v_j = v_i with i < j and v₀, …, v_{j−1} all distinct. Then v_i v_{i+1} … v_j is a closed walk with no repeated vertices inside — a cycle. ∎ (Pattern **P18**: the procedure *is* the proof, with a pigeonhole hiding inside.)

**Why you should care about the method and not just the fact.** "Take a longest path; the endpoint is trapped" is one of the top three moves in all of graph theory. Watch it return: it finds leaves in trees (Lecture 3), it underlies Prüfer's analysis (Lecture 4), and it proves Dirac's theorem (Lecture 6). When you need to prove something *exists* in every graph, your first reflex should be: *grab the most extreme object available and interrogate its boundary.*

**What you now own:** cornered endpoints (P8); first-repeat walks (P18+P9); the extremal reflex.

---

## Lecture 3 · Trees: Just Enough Roads

A new country, n cities, and a minister of roads who must connect every city to every other — directly or through intermediates — while building not one unnecessary road. The result of her economy is called a **tree**: a graph that is **connected** (every city reaches every other) and **acyclic** (no closed loops of roads). The question this lecture answers: *how many roads does such a country have, and why is that number inevitable?* The answer, n − 1, is almost boring. The *reason* is a set of ideas you will use for the rest of the book.

### 3.1 Leaves are forced (the extremal reflex again)

Take a longest path in the tree, v₀…v_k. Claim: d(v₀) = 1 — v₀ is a **leaf**. If v₀ had a second neighbor u ≠ v₁, then u is not on the path (else extending is impossible... wait — if u *were* on the path, v₀…v_j = u would close a cycle; if u were *off* the path, the path wasn't longest. Either way, contradiction). So the endpoint's only neighbor is v₁, and the tree has a leaf. ∎ (P8, second appearance. Notice how the two failure modes of an extra neighbor — "on the path" and "off the path" — split into *cycle* and *longer path*; that is acyclicity and connectedness doing their jobs one at a time.)

### 3.2 The three-way door

For a graph G on n vertices, these are equivalent — and each equivalence is a tool you'll hold for life:

**(a)** G is connected and acyclic. **(b)** G is connected with exactly n − 1 edges. **(c)** Every two vertices of G are joined by a *unique* path.

**(a) ⇒ (b): peel the leaf.** Induct on n. A tree with n ≥ 2 has a leaf v (§3.1). Delete v and its edge: what's left is still connected (v was a dead end, no through-traffic used it) and still acyclic — a tree on n − 1 vertices, which by induction has n − 2 edges. Put v back with its one edge: n − 1 edges. ∎ (P4: leaf-peeling — the tree's own structure powers the induction.)

**(b) ⇒ (a): count the surplus.** First a sub-fact, worth having on its own: *every connected graph has at least n − 1 edges.* Proof: from any connected G, delete an edge lying on a cycle, if one exists; connectivity is untouched (the edge's endpoints remain connected the long way around). Repeat until no cycles remain: you reach a connected acyclic subgraph — a **spanning tree** — which by (a)⇒(b) has exactly n − 1 edges. Since we only deleted, G itself had ≥ n − 1 edges. Now suppose G is connected with n − 1 edges *and* has a cycle: deleting any cycle edge leaves it connected with n − 2 edges — below the floor just established. Contradiction. ∎

**(a) ⇒ (c): two paths would weld into a cycle.** Suppose vertices u ≠ v have two different paths P and Q. They agree for a while; let x be the *last* vertex where they still agree. After x the paths split, and they must rejoin somewhere (they meet again at v at the latest); let y be the *first* rejoining point. The segment of P from x to y and the segment of Q from x to y share only their endpoints — so together they close a cycle. But trees have none. ∎

**(c) ⇒ (a): unique paths mean connected and no cycles.** Unique *paths between every pair* includes existence, which is connectedness. And if a cycle existed, any two adjacent vertices x, y on it would have two x–y routes: the edge, and the rest of the cycle. So acyclic. ∎

### 3.3 The consequences you should know cold

- A **forest** (acyclic, possibly disconnected) on n vertices with k components has exactly n − k edges — peel a leaf from any component repeatedly (each peel removes one vertex and one edge, components unchanged) until every component is a single vertex.
- In a tree, *every* edge is a bridge (delete it and the tree splits into two parts — Lecture 4 uses this constantly) and *every* non-edge, when added, creates exactly one cycle (the two endpoints have a unique path already).
- **Spanning trees exist in every connected graph** (the deletion procedure of (b)⇒(a) constructs one — pattern P18: the proof is the procedure).

**What you now own:** leaf-peeling induction (P4), the three-way door and its proofs, cycle-deletion for spanning trees (P18), and the extremal reflex in its third job.

---

## Lecture 4 · Naming All the Trees: Prüfer and Cayley

Here is a shock. The number of trees one can build on n *labeled* vertices {1, …, n} — plain n^{n−2}, a pure exponent — is **Cayley's formula** (Cayley, 1889). For n = 4 it says there are 16 trees; the lab below counted them all, and there are exactly 16. Now, how could anyone *find* such a formula? Not by listing trees. You find it by hoping for a miracle and then checking that the miracle is real: *if only trees were secretly sequences* — say, sequences of length n − 2 over an n-letter alphabet — the answer would be obvious, n^{n−2}. Prüfer (1918) proved the miracle true: there is a perfect way to **name** every tree by a sequence.

### 4.1 The code

To encode a labeled tree: repeat n − 2 times — *find the smallest leaf; write down the label of its neighbor; delete the leaf (and its edge)*. The string of written labels is the **Prüfer code**.

Work both tiny examples by hand — this is not optional. The star on {1,2,3,4} centered at 4: smallest leaf 1, write 4, delete; smallest leaf 2, write 4, delete; code **(4,4)**. The path 1–2–3–4: leaves are 1 and 4; smallest is 1, write its neighbor 2, delete 1; now the path 2–3–4 has leaves 2 and 4; smallest is 2, write 3, delete. Code **(2,3)**. Two different trees, two different names.

The star's encoding, run step by step — smallest leaf deleted each time, its neighbor written down:

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 880 350" font-family="system-ui, -apple-system, 'Segoe UI', sans-serif">
  <rect x="0" y="0" width="880" height="350" fill="#ffffff"/>
  <text x="40" y="34" font-size="17" font-weight="700" fill="#193e5c">Figure 2 &#183; Pr&#252;fer encoding of the star on {1, 2, 3, 4} (&#167;4.1)</text>
  <!-- Panel A : the full star -->
  <text x="40" y="72" font-size="13" fill="#172333" font-weight="600">start: the star, center 4</text>
  <g stroke="#94a3b8" stroke-width="3">
    <line x1="150" y1="215" x2="70" y2="125"/><line x1="150" y1="215" x2="230" y2="125"/><line x1="150" y1="215" x2="150" y2="305"/>
  </g>
  <g fill="#ffffff" stroke="#2563eb" stroke-width="3">
    <circle cx="70" cy="125" r="15"/><circle cx="230" cy="125" r="15"/><circle cx="150" cy="305" r="15"/>
  </g>
  <circle cx="150" cy="215" r="17" fill="#14766d" stroke="#ffffff" stroke-width="3"/>
  <g font-size="14" font-weight="700" text-anchor="middle">
    <text x="70" y="130" fill="#172333">1</text><text x="230" y="130" fill="#172333">2</text>
    <text x="150" y="310" fill="#172333">3</text><text x="150" y="220" fill="#ffffff">4</text>
  </g>
  <text x="40" y="338" font-size="12" fill="#dc2626">smallest leaf 1 &#8594; write 4, delete 1</text>
  <!-- Panel B : after deleting 1 -->
  <text x="335" y="72" font-size="13" fill="#172333" font-weight="600">after deleting 1 (wrote 4)</text>
  <g stroke="#94a3b8" stroke-width="3">
    <line x1="445" y1="215" x2="365" y2="125"/><line x1="445" y1="215" x2="445" y2="305"/>
  </g>
  <g fill="#ffffff" stroke="#2563eb" stroke-width="3">
    <circle cx="365" cy="125" r="15"/><circle cx="445" cy="305" r="15"/>
  </g>
  <circle cx="445" cy="215" r="17" fill="#14766d" stroke="#ffffff" stroke-width="3"/>
  <g font-size="14" font-weight="700" text-anchor="middle">
    <text x="365" y="130" fill="#172333">2</text><text x="445" y="310" fill="#172333">3</text><text x="445" y="220" fill="#ffffff">4</text>
  </g>
  <text x="335" y="338" font-size="12" fill="#dc2626">smallest leaf 2 &#8594; write 4, delete 2</text>
  <!-- Panel C : the run ends -->
  <text x="630" y="72" font-size="13" fill="#172333" font-weight="600">run over: n &#8722; 2 = 2 deletions</text>
  <line x1="680" y1="215" x2="800" y2="215" stroke="#94a3b8" stroke-width="3"/>
  <circle cx="680" cy="215" r="15" fill="#ffffff" stroke="#2563eb" stroke-width="3"/>
  <circle cx="800" cy="215" r="17" fill="#14766d" stroke="#ffffff" stroke-width="3"/>
  <g font-size="14" font-weight="700" text-anchor="middle">
    <text x="680" y="220" fill="#172333">3</text><text x="800" y="220" fill="#ffffff">4</text>
  </g>
  <rect x="630" y="260" width="220" height="42" rx="8" fill="#f3f7fb" stroke="#bcd6f0"/>
  <text x="740" y="287" font-size="14" font-weight="700" fill="#193e5c" text-anchor="middle">code = (4, 4)</text>
</svg>
```

### 4.2 The dictionary — why the code is a perfect name

Why does this lose no information? Because the code keeps an exact tally book of the tree:

**Fact 1 (occurrences = degree − 1).** Label v is written into the code exactly d(v) − 1 times. *Proof.* v is written once each time a neighbor of v is deleted while v is still alive. Now run the algorithm to the end: every vertex except the final two survivors is eventually deleted (as a leaf — with exactly one living neighbor at that moment). If v is deleted, its living neighbors at that moment number exactly 1, so the neighbors deleted *before* v number d(v) − 1 — those are precisely v's entries in the code. If v survives to the final edge, its single co-survivor neighbor is never deleted, and the other d(v) − 1 neighbors die while v watches: again d(v) − 1 writes. ∎

**Fact 2 (leaves = missing labels).** At any moment of the run, the leaves of the current tree are exactly the labels *absent from the code still to be written*. *Proof, both directions.* (⇐) Suppose v is absent from the remaining code but has d′ ≥ 2 living neighbors. To ever be deleted, v must first shrink to one neighbor — which requires a neighbor's death, and any death of a living neighbor of v writes v into the code. Even if v plans to survive to the end, the final edge leaves v with exactly one living neighbor, so again a neighbor must die first, writing v. Either way v's absence is contradicted. So d′ = 1: v is a leaf. (⇒) Suppose v is a leaf with neighbor u. If v dies first, its deletion writes *u* (not v), and v, being dead, is never written again: absent. If u dies first, then u died as a leaf, meaning u's only living neighbor was v — so the current tree was already just the edge uv, i.e., the run is over, the remaining code is empty, and v is absent. ∎

### 4.3 Decoding, and why it inverts (complete)

To decode (a₁, …, a_{n−2}): track a *pool* of labels not appearing in the remaining code; repeatedly take the **smallest** pool label ℓ, join ℓ to the front a_i of the remaining code, delete ℓ from the pool and a_i from the code; when a label's count in the remaining code hits zero, add it back to the pool; at the end, join the last two surviving labels.

*Why this reconstructs the tree.* Induct on the code. By Fact 2, the leaves of the full tree are exactly the labels absent from the whole code — so the smallest absent label ℓ₁ *is* the smallest leaf, which is precisely the vertex the encoder deleted first, writing its neighbor = a₁. So edge (ℓ₁, a₁) is correct, and the encoder then continued on the tree minus ℓ₁, producing exactly the tail (a₂, …): the same problem, one smaller. Induct. The final two survivors are the labels that were never any ℓᵢ: join them. Conversely, re-encoding the reconstruction re-runs the encoder's own steps, so it returns the original code. Two procedures, mutual inverses — a genuine **bijection** (P1). ∎

Check it on Lecture 4.1's examples: decode (4,4): pool {1,2,3} → join 1–4, then 2–4, then 3–4: the star. Decode (2,3): pool {1,4}: join 1–2 (2's count drops to 0, 2 enters the pool); join 2–3 (3 enters the pool); end pool {3,4}: join 3–4: the path. ✓

**And the punchline:** n − 2 slots, n choices each, one tree per sequence, one sequence per tree — the count is n · n · … · n = **n^{n−2}**. ∎

### 4.4 The dictionary pays rent: degree sequences

Fact 1 says a tree with degrees (d₁, …, d_n) corresponds to a code containing label i exactly dᵢ − 1 times. So the number of labeled trees with a *given* degree sequence is just the number of words with prescribed letter counts — a multinomial:

**# trees with degrees (d₁,…,d_n) = (n−2)! / Πᵢ (dᵢ − 1)!**  (when Σdᵢ = 2n − 2, all dᵢ ≥ 1).

Verify on n = 4 before trusting it: the all-degrees-sum is 2n − 2 = 6. Sequences: stars (degrees 1,1,1,3 up to which vertex is the center): (3−2)!... compute: (4−2)!/(2!)·… per center it is 2!/2! = 1, four centers → 4 stars. Paths (degrees 1,1,2,2): choose the two internal vertices (6 ways), each with 2!/(1!·1!) = 2 codes → 12. Total 4 + 12 = **16** ✓ — exactly Cayley's count, recovered from the dictionary without ever listing trees.

### 4.5 Joyal's other door (complete)

Cayley's formula has a second famous proof, Joyal's (1981), with a different soul — and a different moral: *count something bigger, and count it somewhere easier.* Prüfer names trees by sequences; Joyal packs a whole doubly-rooted tree into a single function, and Cayley falls out the other side without a word of the code dictionary.

**The two worlds, counted first.** A **doubly-rooted tree** is a labeled tree T with two distinguished vertices a and b (possibly equal). Whatever the tree count turns out to be, each tree carries exactly n² doubly-rooted versions — n choices for a times n for b — so the map "forget the roots", (T, a, b) ↦ T, is exactly n²-to-1, by definition and nothing deeper (that is the non-circularity: no step of this proof leans on Cayley). In the other world, a **function** f : {1,…,n} → {1,…,n} is a list of n values with n choices each: n^n functions, no graph theory involved. Joyal's claim: **doubly-rooted trees and functions are in bijection.** Comparing counts, n² · (#trees) = n^n, so #trees = n^{n−2} — Cayley, proved a second time.

**Step 1 — read a function as a picture.** Draw the *functional digraph* of f: an arrow z → f(z) out of every vertex. Follow the arrows from any start: you never get stuck (every vertex has an outgoing arrow), and there are only n vertices — so you walk until a vertex repeats, and the repeat closes a **cycle** (a one-vertex loop f(z) = z counts). Every function therefore looks the same: some disjoint cycles, with trees hanging off them, every branch arrowing inward toward its cycle. The cycle vertices are the spine-to-be.

**Step 2 — G: function → doubly-rooted tree.** Take the cycles of f. Order them by **decreasing smallest label**; rotate each to start at its smallest label; concatenate them all, in that order, into one sequence x₁, x₂, …, x_k — the **spine**. Set a = x₁ and b = x_k. Now build T: join consecutive spine vertices by edges (the spine becomes a path from a to b), and for every vertex z *not* on a cycle, add the edge {z, f(z)} — its old arrow, kept as an undirected rope pulling it toward the spine.

Why the result is a tree: every old cycle has been opened and its vertices reused along one path, so no cycles survive; every off-cycle chain still leads to the spine, so everything is connected. Count the edges while you are at it: the k spine vertices contribute k − 1 edges, the n − k others one rope each — n − 1 total, connected, acyclic: a tree, by the three-way door of §3.2. This is **G**: f ↦ (T, a, b).

**Worked example (n = 5).** f(1) = 5, f(2) = 2, f(3) = 1, f(4) = 2, f(5) = 1. Cycles: (2) — it stands still — and (1, 5), since 1 → 5 → 1; off the cycles, 3 → 1 and 4 → 2. Decreasing minima: (2) has smallest label 2, (1, 5) has 1 — so (2) goes first. Spine: [2, 1, 5]; a = 2, b = 5. Tree: the path 2–1–5, plus the ropes 3–1 and 4–2 — the tree 4–2–1–5 with a 3 hanging off the 1. Two sanity checks to carry in your pocket: the star K_{1,3} centered at 4 with a = b = 4 has spine [4] and every leaf roped to the center — the constant function f ≡ 4. And the path 1–2–3–4 rooted at a = 4, b = 1 has spine [4, 3, 2, 1] — and gives back the identity function.

**Step 3 — F: doubly-rooted tree → function.** Given (T, a, b): the spine is the unique a-to-b path, x₁ = a, …, x_k = b (§3.2, door (c)). Cut the spine into **blocks** that begin exactly at the **strict left-to-right records** of the label sequence — a record being a label smaller than every label to its left. Inside one block x_i, x_{i+1}, …, x_j (from a record up to just before the next): set f(x_m) = x_{m+1} for m < j — walk forward — and f(x_j) = x_i: the block closes into a cycle at its smallest label. For a vertex z off the spine: f(z) = the neighbor of z on its path toward the spine. This is **F**: (T, a, b) ↦ f.

**Step 4 — why the round trip closes, both ways.** After G, the spine is the concatenation of cycles in decreasing order of minima, each written min-first. So each cycle's minimum is a strict record — it is smaller than the minima of all earlier cycles, hence smaller than *every* earlier spine label — and no other spine label is a record, since it exceeds its own cycle's minimum, which sits to its left. So F's record rule cuts the spine back into exactly the original cycles, in exactly the original order, and reads each one correctly; and off the spine, G roped z to f(z), so "neighbor toward the spine" hands f(z) right back. That is F(G(f)) = f. Conversely, after F the cycles *are* the blocks — and records strictly decrease, so the blocks arrive already sorted by decreasing minima, min-first — while the spine path and the off-spine chains rebuild T edge for edge, and a, b are the spine's ends. That is G(F(T, a, b)) = (T, a, b). Two procedures, mutual inverses: a bijection (P1 at full power — the named objects are no longer sequences but whole wired structures). ∎

Before installation this was machine-verified in both directions (appendix): every one of the 4⁴ = 256 functions on {1,…,4} and all 5⁵ = 3125 on {1,…,5} survives f → G → F → f; every doubly-rooted tree (all 256 on 4 labels, all 3125 on 5) survives (T, a, b) → F → G → (T, a, b); zero failures either way.

**What you now own:** structure-as-sequence bijections (P1), Joyal's pack-the-whole-structure bijection — Cayley's second proof, independent of Prüfer — the two dictionary facts and their proofs, degree-sequence counting for free.

---

## Lecture 5 · Königsberg: the Seven Bridges

The city of Königsberg sat on a river with an island, joined by seven bridges. The citizens asked, on Sunday walks: *can one cross every bridge exactly once and come home?* Euler answered in 1736 — no — and in answering invented the subject: he declared that only the *wiring* matters (four land masses, seven connections) and nothing else. Land masses become vertices, bridges become edges (several allowed between the same pair — a *multigraph*).

**Theorem.** A connected multigraph has a closed walk using every edge exactly once (an *Euler tour*) **iff every vertex has even degree**. (For a walk that need not close — an *Euler trail* — the condition is: at most two odd vertices, and the walk runs between them.)

### 5.1 Why even degrees are necessary

On a closed walk, each visit to a vertex consumes its edges in *pairs*: one edge in, one edge out. Enter three times and you must leave three times. So every degree touched by the walk is even; if the walk covers *all* edges, all degrees are even. ∎ (P7 — parity again, now as a necessary condition.)

And Königsberg dies by Lecture 1: the degrees are 5 (the island Kneiphof) and 3, 3, 3 — four odd vertices; check the total against the handshaking lemma: 5+3+3+3 = 14 = 2·7 ✓. Impossible.

### 5.2 Why even degrees are enough — Hierholzer's splicing (complete)

Now the converse, and the proof is a machine you can run. Walk greedily from any vertex, never reusing an edge. When can you get stuck? Only at a vertex with no fresh edge left. If you get stuck at some vertex w ≠ start, then w was *entered* once more than it was *left* — one of its edges used without replacement, contradicting d(w) even. So the walk can only die at the **starting vertex**, and it dies holding a closed trail C. If C misses some edge, then (the graph being connected) some vertex w on C touches an unused edge; the unused edges at every vertex still number even (we removed a closed trail, which used each visited vertex's edges in pairs — pairs again!); so from w we can greedily walk a second closed trail C′ through unused edges, and **splice** C′ into C at w. Each splice strictly enlarges one closed trail; edges are finite; the machine halts with a single closed trail covering every edge. ∎ (P18: the proof *is* an O(m) algorithm — this is why Euler's theorem is not just true but *usable*: your route-finder can actually run it.)

The splice, drawn — two closed trails sharing the vertex w, welded into one closed trail through it:

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 880 350" font-family="system-ui, -apple-system, 'Segoe UI', sans-serif">
  <defs>
    <marker id="arrB" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto-start-reverse">
      <path d="M 0 0 L 10 5 L 0 10 z" fill="#2563eb"/>
    </marker>
    <marker id="arrA" viewBox="0 0 10 10" refX="9" refY="5" markerWidth="7" markerHeight="7" orient="auto-start-reverse">
      <path d="M 0 0 L 10 5 L 0 10 z" fill="#d97706"/>
    </marker>
  </defs>
  <rect x="0" y="0" width="880" height="350" fill="#ffffff"/>
  <text x="40" y="34" font-size="17" font-weight="700" fill="#193e5c">Figure 3 &#183; Hierholzer&#8217;s splice at the shared vertex w (&#167;5.2)</text>
  <!-- Panel A : two closed trails -->
  <text x="40" y="72" font-size="13" fill="#172333" font-weight="600">before: two closed trails C and C&#8242; through w</text>
  <g fill="none" stroke="#2563eb" stroke-width="3.5" marker-end="url(#arrB)">
    <line x1="285" y1="175" x2="200" y2="120"/>
    <line x1="195" y1="112" x2="195" y2="248"/>
    <line x1="200" y1="260" x2="285" y2="205"/>
  </g>
  <g fill="none" stroke="#d97706" stroke-width="3.5" marker-end="url(#arrA)">
    <line x1="315" y1="175" x2="400" y2="120"/>
    <line x1="405" y1="112" x2="405" y2="248"/>
    <line x1="400" y1="260" x2="315" y2="205"/>
  </g>
  <g fill="#ffffff" stroke="#94a3b8" stroke-width="2.5">
    <circle cx="192" cy="108" r="11"/><circle cx="192" cy="252" r="11"/>
    <circle cx="408" cy="108" r="11"/><circle cx="408" cy="252" r="11"/>
  </g>
  <circle cx="300" cy="190" r="15" fill="#14766d" stroke="#ffffff" stroke-width="3"/>
  <text x="300" y="195" font-size="12" font-weight="700" fill="#ffffff" text-anchor="middle">w</text>
  <text x="120" y="300" font-size="12.5" fill="#2563eb" font-weight="600">C</text>
  <text x="425" y="300" font-size="12.5" fill="#d97706" font-weight="600">C&#8242;</text>
  <!-- Panel B : the spliced tour -->
  <text x="480" y="72" font-size="13" fill="#172333" font-weight="600">after: one closed trail, spliced at w</text>
  <g fill="none" stroke-width="3.5">
    <line x1="725" y1="175" x2="640" y2="120" stroke="#2563eb" marker-end="url(#arrB)"/>
    <line x1="635" y1="112" x2="635" y2="248" stroke="#2563eb" marker-end="url(#arrB)"/>
    <line x1="640" y1="260" x2="725" y2="205" stroke="#2563eb" marker-end="url(#arrB)"/>
    <line x1="755" y1="175" x2="840" y2="120" stroke="#d97706" marker-end="url(#arrA)"/>
    <line x1="845" y1="112" x2="845" y2="248" stroke="#d97706" marker-end="url(#arrA)"/>
    <line x1="840" y1="260" x2="755" y2="205" stroke="#d97706" marker-end="url(#arrA)"/>
  </g>
  <g fill="#ffffff" stroke="#94a3b8" stroke-width="2.5">
    <circle cx="632" cy="108" r="11"/><circle cx="632" cy="252" r="11"/>
    <circle cx="848" cy="108" r="11"/><circle cx="848" cy="252" r="11"/>
  </g>
  <circle cx="740" cy="190" r="15" fill="#14766d" stroke="#ffffff" stroke-width="3"/>
  <text x="740" y="195" font-size="12" font-weight="700" fill="#ffffff" text-anchor="middle">w</text>
  <text x="480" y="300" font-size="12.5" fill="#172333">walk C until it returns to w &#8212; then keep going straight into C&#8242;</text>
  <text x="480" y="322" font-size="12" fill="#64748b">each splice strictly enlarges one closed trail; the machine halts with a single Euler tour</text>
</svg>
```

### 5.3 The harder brother — and the lesson of the difference

Change one word in the problem — cross every *bridge* once becomes visit every *land mass* once — and you get Hamilton's problem (a *Hamilton cycle*). The two problems look like twins. They are not. Euler's condition is *local* (a parity check at each vertex) that composes globally — pieces weld, as in the splicing. Hamilton's is a *global booking constraint* — every vertex must be visited exactly once in one unbroken chain — and no local check certifies it; deciding Hamiltonicity is NP-hard (Chapter 11 makes this precise). **When two problems look like twins but only one has a good theory, the structural difference is the lesson.** Here it is: *additive, local conditions compose; global one-of-each constraints do not.*

But this raises a question worth a whole lecture: since no *exact* local characterization of Hamiltonicity exists, what is the strongest *sufficient* local condition? Answer: half the vertices. That is Lecture 6 — new in this edition.

**What you now own:** parity as necessity (P7), splicing as sufficiency (P18), the local-vs-global divide — and the right question to ask next.

---

## Lecture 6 · Dirac: When Half Is Enough

In 1952 a young graph theorist named Gabriel Dirac — who arrived at mathematics by a side door of a famous family: he was the stepson of the physicist Paul Dirac — proved the following: *if every vertex of a graph on n ≥ 3 vertices has degree at least n/2, then the graph has a Hamilton cycle.* Minimum degree halfway to "adjacent to everyone" already forces a perfect tour. Before the proof, feel why it's plausible: take any two vertices that are *strangers* — u ≁ v. Both neighborhoods then live inside the same n − 2 other vertices, and |N(u)| + |N(v)| ≥ 2·(n/2) = n > n − 2, so the two circles cannot miss each other: **N(u) ∩ N(v) ≠ ∅**. The graph is *tight everywhere* — no two strangers have disjoint acquaintance circles. (Adjacent pairs are exempt from this argument, and rightly so: in K_{3,3} two adjacent vertices from opposite sides have disjoint neighborhoods of size n/2 each. Strangers are what the engine consumes.) That tightness is the fuel; the proof's job is to route it into a single unbroken tour.

### 6.1 The proof — corner both ends at once

Take a longest path P = v₁v₂…v_k (the extremal reflex, P8, now with both ends working). Each endpoint is cornered: all neighbors of v₁ and of v_k lie on P (an outside neighbor would extend P). Define two sets of *positions along the path*:

**S = { i : 1 ≤ i ≤ k−1 and v₁ ~ v_{i+1} }**  (positions just before a neighbor of v₁)
**T = { i : 1 ≤ i ≤ k−1 and v_i ~ v_k }**  (positions just after a neighbor of v_k)

Count them: v₁'s neighbors all lie among v₂,…,v_k, and the rule i ↦ v_{i+1} matches them to positions one-to-one, so |S| = d(v₁) ≥ n/2; likewise |T| = d(v_k) ≥ n/2. Both S and T live in the same k−1 positions. If they never met, |S| + |T| ≤ k − 1 < n ≤ |S| + |T| — contradiction. So some **i ∈ S ∩ T**: the two chords v₁v_{i+1} and v_iv_k both exist. (This is pigeonhole, P9 — but note the upgrade: we are not matching pigeons to holes, we are detecting an *overlap of two majority subsets*, which is the same arithmetic wearing a better suit.)

Now read off the cycle: start at v₁, walk the path to v_i, jump the chord to v_k, walk the path *backwards* to v_{i+1}, jump the chord home to v₁:
**v₁ v₂ … v_i v_k v_{k−1} … v_{i+1} v₁** — a cycle through all k vertices of P.

The two chords and the cycle they close, drawn — i = 3 is the shared position:

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 880 380" font-family="system-ui, -apple-system, 'Segoe UI', sans-serif">
  <rect x="0" y="0" width="880" height="380" fill="#ffffff"/>
  <text x="40" y="34" font-size="17" font-weight="700" fill="#193e5c">Figure 4 &#183; Dirac&#8217;s proof &#8212; the two endpoint chords (&#167;6.1)</text>
  <!-- the path edges: cycle members emphasized -->
  <g stroke="#94a3b8" stroke-width="3">
    <line x1="368" y1="230" x2="512" y2="230"/>
  </g>
  <g stroke="#2563eb" stroke-width="4">
    <line x1="80" y1="230" x2="224" y2="230"/>
    <line x1="224" y1="230" x2="368" y2="230"/>
    <line x1="512" y1="230" x2="656" y2="230"/>
    <line x1="656" y1="230" x2="800" y2="230"/>
  </g>
  <!-- chord v1 - v4 (from S) -->
  <path d="M 80 215 Q 296 75 512 215" fill="none" stroke="#d97706" stroke-width="3.5"/>
  <!-- chord v3 - v6 (from T) -->
  <path d="M 368 245 Q 584 365 800 245" fill="none" stroke="#dc2626" stroke-width="3.5"/>
  <g fill="#ffffff" stroke="#2563eb" stroke-width="3">
    <circle cx="80" cy="230" r="13"/><circle cx="224" cy="230" r="13"/><circle cx="368" cy="230" r="13"/>
    <circle cx="512" cy="230" r="13"/><circle cx="656" cy="230" r="13"/><circle cx="800" cy="230" r="13"/>
  </g>
  <g font-size="14" font-weight="600" fill="#172333" text-anchor="middle">
    <text x="80" y="262">v&#8321;</text><text x="224" y="262">v&#8322;</text><text x="368" y="262">v&#8323;</text>
    <text x="512" y="262">v&#8324;</text><text x="656" y="262">v&#8325;</text><text x="800" y="262">v&#8326;</text>
  </g>
  <text x="296" y="98" font-size="12.5" fill="#d97706" font-style="italic" text-anchor="middle">chord v&#8321;v&#8324; &#8212; from S: v&#8321; ~ v_{i+1}</text>
  <text x="584" y="335" font-size="12.5" fill="#dc2626" font-style="italic" text-anchor="middle">chord v&#8323;v&#8326; &#8212; from T: v_i ~ v_k</text>
  <text x="440" y="200" font-size="12.5" fill="#193e5c" font-weight="700" text-anchor="middle">i = 3 &#8712; S &#8745; T</text>
  <text x="40" y="366" font-size="12" fill="#64748b">the cycle: v&#8321; v&#8322; v&#8323; v&#8326; v&#8325; v&#8324; v&#8321; &#8212; all k vertices of the longest path, ready for the &#8220;k = n?&#8221; check.</text>
</svg>
```

Is k = n? If some vertex x lies outside: first, G is connected — inline lemma: each component of a graph has at least δ+1 ≥ n/2 + 1 vertices (a vertex and all its neighbors live in its own component), and two components would then hold ≥ n+2 vertices, more than we have. So x has a neighbor v_j on the cycle, and breaking the cycle at v_j gives a path x v_j v_{j+1} … v_{j−1} with k+1 vertices — longer than the *longest* path. Contradiction. Hence k = n and the cycle is Hamiltonian. ∎

### 6.2 Method 2 — prove more, work less (Ore's theorem)

Look again at the engine: all it consumed was **d(v₁) + d(v_k) ≥ n**. Dirac supplies that via δ ≥ n/2. But Øystein Ore (1960) noticed that the endpoints of a longest path have a special status — and if they are *adjacent*, the path v₁…v_k already closes into a cycle covering all k vertices, and the connectivity-extension argument of §6.1 finishes it (k < n would yield a longer path — contradiction). So assume v₁ ≁ v_k: they form a **non-adjacent pair**, and Ore's hypothesis applies to exactly such pairs:

**Ore's theorem.** If d(u) + d(v) ≥ n for every *non-adjacent* pair u, v, then G is Hamiltonian.

The proof is now §6.1 with "δ ≥ n/2" replaced by "Ore's condition on the (non-adjacent) endpoints" — and one repair the substitution exposes: §6.1 bought connectivity from the component-size lemma, which leans on δ ≥ n/2, and Ore does not sell that. Restore it directly: if u, v lay in different components, of sizes a and b, they would be non-adjacent with d(u) + d(v) ≤ (a − 1) + (b − 1) = a + b − 2 ≤ n − 2 < n, contradicting Ore's condition before the path engine even starts. So G is connected, and the rest is §6.1 untouched. Dirac's theorem drops out as a corollary, since δ ≥ n/2 makes every pair's degree sum ≥ n. ∎

Here is the meta-lesson, one of the best in the book: **when an extremal argument stalls at "d(a) + d(b) ≥ n", do not demand it of every pair — demand it only where the proof actually looks, at the non-adjacent pairs. The theorem gets stronger and the proof does not get harder.** Call this the *Ore move*: *generalize the statement until the engine closes, and not one step further.* The strongest theorem provable by a given proof is usually the one worth stating.

### 6.3 The bound is honest

Can n/2 be relaxed to n/2 − 1? No — and here are the witnesses (constructions, P11 in reverse: not "build to beat a bound" but "build to show a bound cannot move"). For even n: two disjoint cliques K_{n/2} ⊔ K_{n/2} have δ = n/2 − 1 and, being disconnected, no Hamilton cycle. For odd n = 2k + 1: the complete bipartite graph K_{k,k+1} is connected, has δ = k = ⌊n/2⌋ — one below the line Dirac demands (δ ≥ n/2 means δ ≥ k + 1 here) — and still has no Hamilton cycle, its sides unequal by exactly one, so no alternating cycle can cover everyone. The lab below caught an even subtler witness on n = 6: the complete bipartite graph K_{2,4} has δ = 2 = n/2 − 1, *is* connected, and still has no Hamilton cycle — a bipartite graph's cycles must alternate sides, so with sides of unequal size (2 ≠ 4) no cycle can reach all vertices. And the famous Petersen graph (3-regular on 10 vertices, δ = 3 < 5) is connected, bridgeless, and stubbornly non-Hamiltonian — the lab confirmed all of this by brute force. Dirac's n/2 is exactly the frontier. Beyond it lies the degree-sequence landscape that §6.4 now enters — Pósa's theorem and Chvátal's closure — and far beyond that, the grail of a "good" characterization, which (Chapter 11) cannot exist unless P = NP.

### 6.4 Pósa: bill the poor vertices (Chvátal's closure)

Dirac prices *every* vertex at n/2 and Ore prices every *stranger pair* at n. Both are demanding landlords: one shabby vertex and the lease is off. But shabby vertices are often harmless. Take K_{n−1} and attach a new vertex p to just two clique vertices: p is as poor as a connected vertex can be (d(p) = 2), yet the tour writes itself — p, one neighbor, then everyone else in the clique, then the other neighbor, home. In 1962 a fifteen-year-old Budapest schoolboy named Lajos Pósa — Erdős loved to tell the story of finding him at his grandmother's kitchen table, already proving theorems — noticed that Hamiltonicity does not need every vertex rich. It needs the poor to be *few*, and it bills them exactly:

**Pósa's theorem (1962).** Let G have n ≥ 3 vertices, with degrees sorted d₁ ≤ d₂ ≤ … ≤ d_n. If

**d_k ≥ k + 1 for every integer k < n/2** — equivalently, *for every k < n/2, fewer than k vertices have degree at most k* — then G has a Hamilton cycle.

Check the equivalence before reading on: d_k ≥ k+1 says the k-th smallest degree already clears k, which says at most k−1 degrees are ≤ k. Then check the boundary before trusting the range — the condition must run all the way to k < n/2, not stop a step earlier. §6.3's own witness K_{3,4} (n = 7) has degrees 3,3,3,3,4,4,4: d₁ = 3 ≥ 2 ✓, d₂ = 3 ≥ 3 ✓ — but d₃ = 3 < 4 ✗, and K_{3,4} has no Hamilton cycle. The failure lands exactly at the last index the condition covers. The "+1" is just as honest: weaken d_k ≥ k+1 to d_k ≥ k and K_{3,4} slips through (d₃ = 3 ≥ 3); on six vertices the weakened condition is met by 21,218 graphs, of which 11,140 are tourless (the lab, Part 3). Pósa's line cannot move in either direction.

**The plan.** A direct assault on the longest path — Dirac's engine — consumes degree *sums*, and Pósa's condition does not sell them. Pósa's own 1962 proof instead rotated the longest path, counting the vertices his rotations could reach (Exercise 18 develops his rotation lemma — the engine that made his name). The cleanest complete route today is Chvátal's (1972), and it runs on two ideas, each worth owning for life.

**Idea 1 — the closure lemma (Bondy–Chvátal, 1976).** If u and v are non-adjacent and d(u) + d(v) ≥ n, then adding the edge uv cannot create or destroy Hamiltonicity: **G + uv is Hamiltonian if and only if G is.** The "only if" is trivial (a cycle of G is a cycle of G + uv); the "if" is §6.1's engine in miniature. Suppose G + uv has a Hamilton cycle using the new edge. Delete uv: what remains is a Hamilton *path* of G from u to v — write it u = w₁, w₂, …, w_n = v, every step an honest G-edge. Hunt a crossing pair of positions, exactly as §6.1 hunted S ∩ T:

**A = { i : 2 ≤ i ≤ n−1 and w_i ~ v }**  (positions of v's neighbors)
**B = { i : 1 ≤ i ≤ n−2 and w_{i+1} ~ u }**  (positions just before u's neighbors)

Because u and v are strangers in G, v's neighbors all sit at positions 2..n−1 — so |A| = d(v) — and u's likewise, so |B| = d(u). Both A and B live among the n − 1 positions {1, …, n−1}, yet |A| + |B| = d(u) + d(v) ≥ n > n − 1: some **i ∈ A ∩ B**. Read off the cycle — forward along the path to w_i, jump the chord w_i–v, backward along the path to w_{i+1}, jump the chord w_{i+1}–u home. That is Figure 4's picture verbatim, with (v₁, v_k) renamed (u, v), and every edge in it belongs to G. ∎ (P9, the overlap-of-majorities version — third appearance, now on a Hamilton path.)

Iterate the lemma: keep joining non-adjacent pairs with degree sum ≥ n until no pair qualifies. The result is the **closure** cl(G), and every addition was certified harmless, so **G is Hamiltonian if and only if cl(G) is.**

**Idea 2 — sorted degrees only climb.** Adding an edge raises two degrees by one each, and the sorted degree sequence never drops at any position. Compare the j smallest degrees before (a₁ ≤ … ≤ a_j) and after: the j smallest after are j of the old values, each either kept or raised by one. Match each to its base value: the bases are j *distinct* old degrees, so the largest base is at least a_j — and each of the j new values is at least its base. Hence the j-th smallest degree after is ≥ a_j. ∎ (P2 in yet another costume: match, then compare.)

**Chvátal's theorem (1972).** If for every k < n/2: **d_k ≥ k+1 or d_{n−k} ≥ n−k**, then G (n ≥ 3) is Hamiltonian.

*Proof.* First, the condition survives closure: by Idea 2 each d_k and each d_{n−k} only climbs under edge additions, so a satisfied disjunct stays satisfied. Now suppose, for contradiction, that the closure H = cl(G) is not complete. Choose H's non-adjacent pair u, v with the *largest* degree sum, named so that d(u) = k ≤ d(v). Because the closure is saturated, d(u) + d(v) ≤ n − 1 — a sum of n or more would have triggered one more addition. Two counts, at u and at v:

*At u:* every stranger of u has degree ≤ d(v) ≤ n−1−k (a stranger with larger degree would have formed a bigger-sum pair with u). Those strangers number n−1−k; together with u itself — degree k ≤ n−1−k, from 2k ≤ d(u) + d(v) ≤ n−1 — that is 1 + (n−1−k) = n−k vertices, every one of degree ≤ n−k−1. So **d_{n−k} ≤ n−k−1**: the second disjunct dies at index k.

*At v:* every stranger of v has degree ≤ d(u) = k, and v has n−1−d(v) ≥ k strangers (since d(v) ≤ n−1−k). So at least k vertices have degree ≤ k: **d_k ≤ k**. The first disjunct dies at the same index.

And k < n/2, since 2k ≤ n−1 < n. So H violates the condition at index k — impossible, because H is the closure of a graph that satisfied the condition, and the condition only strengthens under closure. (The degenerate case k = 0 — an isolated vertex in the closure — dies at index 1 instead: d₁ = 0, and d_{n−1} ≥ n−1 would need a vertex adjacent to everyone, the isolated u included.) The contradiction closes: cl(G) = K_n, which is plainly Hamiltonian, so G is. ∎

**Pósa's theorem is now a corollary:** Pósa's condition d_k ≥ k+1 holds on the entire range k < n/2, so it satisfies Chvátal's disjunction by its first arm everywhere — no second arm ever needed. Dirac falls out too: δ ≥ n/2 gives d_k ≥ ⌈n/2⌉ ≥ k+1. And the chain is strict: on six vertices the lab counts 1858 Dirac graphs inside 5218 Pósa graphs inside 5788 Chvátal graphs — 3360 graphs that Pósa certifies and Dirac cannot (all 1080 with degree sequence (2,3,3,3,3,4) among them, every single one Hamiltonian), and 570 more that only Chvátal reaches (all verified Hamiltonian; Exercise 13's table makes you run the diagnostics yourself).

One honest boundary. What Pósa does *not* claim: a graph failing the condition at some index is simply outside the theorem — some such graphs are Hamiltonian, some are not, and no degree-sequence test can separate them in general. Chvátal's test is the best possible *of its kind*: if the condition fails at even one index, some non-Hamiltonian graph has a degree sequence dominating yours pointwise (Chvátal's clique-stitching construction — not proved here; see his 1972 paper). And the true prize — a "good" characterization of Hamiltonicity itself — cannot exist unless P = NP (Chapter 11).

**What you now own (Lecture 6, complete):** the cornered-both-ends method (P8 + P9 fused), connectivity-from-minimum-degree, the Ore move, the **closure move** — *add what cannot change the answer, then argue about the saturated object* — and honest tightness witnesses at every boundary.

---

## Lecture 7 · One From Each Path: Gallai–Milgram

The last lecture opens the door to *directed* graphs — a lecture says otherwise, and this one does. A **digraph** is dots with one-way arrows between them (no loops needed here); a **directed path** is a walk that follows the arrows; and two vertices are adjacent if some arrow runs between them, either way — that is adjacency in the *underlying* graph, and α(D) will always mean the independence number of that underlying graph.

Here is the seed, already in your pocket. Exercise 20 (Rédei's theorem) says: in any *tournament* — every pair joined by exactly one arrow — the players can always be ranked in a chain p₁ → p₂ → … → p_n, a directed Hamilton path. In 1960 Tibor Gallai and Arthur Milgram published a paper whose title, translated, reads "A generalization of a graph-theoretic theorem of Rédei." Generalization how? A tournament is the most *hostile* geometry imaginable for independence: every two vertices adjacent, so α = 1. Rédei says one directed path then covers everything. Gallai and Milgram asked what happens in an arbitrary digraph, where long directed paths can be impossible outright (two vertices with no arrow either way admit no path through both). The answer: the vertices can always be split into few disjoint directed paths — and the price is exactly α.

**Theorem (Gallai–Milgram 1960).** Every digraph D has a **path cover** — vertex-disjoint directed paths covering every vertex exactly once — consisting of at most α(D) paths.

We will prove something stronger, a form you can *see* with. Call a set S a **cross-cut** of a cover P if S contains exactly one vertex from each path of P. 

**Theorem (cross-cut form).** Every digraph has a path cover P and an independent cross-cut S of P.

The cross-cut form hands over the theorem as a corollary: |P| = |S| ≤ α. But it is more than a repackaging — it names a *witness* (the independent set) matched path-for-path, which is exactly what the proof constructs. (Try the tiny example of the digraph with arcs w→x and v→x: the minimum covers {(w,x),(v)} and {(v,x),(w)} each admit the independent cross-cut {w, v} — but note it is *not* the set of endpoints: v→x joins the ends of the first cover. The witness lives in the proof, not in the ends.)

### 7.1 End-minimal covers

A cover's **end-set** is the set of last vertices of its paths — k paths, k distinct ends. Call a cover **end-minimal** if no cover of D has an end-set that is a *proper subset* of its end-set. Two facts make this notion golden:

*Every minimum-size cover is end-minimal.* A proper sub-end-set has smaller size, so it would belong to a cover with fewer paths — contradiction.

*End-minimality is what survives deletion.* If we delete a vertex, a cover of the smaller digraph may stop being minimum-size — but with a nested notion, the induction can compare end-sets directly. This is the "prove more, work less" move again: strengthen the induction hypothesis until deletion can't break it. (The Ore move's cousin — generalizing the *statement* until the proof closes.)

### 7.2 The proof (induction on the number of vertices, P15)

**Claim.** Every end-minimal path cover of every digraph admits an independent cross-cut.

*Base.* The empty digraph: the empty cover, cross-cut ∅. Induction step: let D have n vertices, P = {p₁, …, p_k} an end-minimal cover, ends v₁, …, v_k. If the end-set {v₁, …, v_k} is independent, it is itself a cross-cut — done. Otherwise some arrow joins two ends; relabel so it runs **v₂ → v₁** (call it the **blue arrow**).

First, p₁ cannot be the single vertex v₁. If it were, splicing v₂ → v₁ onto p₂'s end and deleting p₁ would leave a cover whose end-set is the old one minus v₂ — a proper subset, forbidden by end-minimality. So p₁ has at least two vertices; let **v** be its second-to-last vertex, joined to v₁ by the path's own last step (the **red arrow** v → v₁).

Now delete v₁. The digraph D′ = D − v₁ inherits the cover P′ = {p₁′, p₂, …, p_k}, where p₁′ is p₁ shortened by one (its end is now v). The end-sets: Ends(P′) = {v, v₂, …, v_k}. The two arrows that used to touch v₁:

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 880 350" font-family="system-ui, -apple-system, 'Segoe UI', sans-serif">
  <rect x="0" y="0" width="880" height="350" fill="#ffffff"/>
  <text x="40" y="34" font-size="17" font-weight="700" fill="#193e5c">Figure 5 &#183; Gallai&#8211;Milgram &#8212; the two arrows at the deleted end v&#8321; (L7)</text>
  <g stroke="#94a3b8" stroke-width="3">
    <line x1="80" y1="110" x2="200" y2="110"/>
    <line x1="200" y1="110" x2="320" y2="110"/>
    <line x1="320" y1="110" x2="440" y2="110"/>
    <line x1="80" y1="250" x2="200" y2="250"/>
    <line x1="200" y1="250" x2="320" y2="250"/>
    <line x1="320" y1="250" x2="440" y2="250"/>
  </g>
  <line x1="440" y1="110" x2="580" y2="110" stroke="#dc2626" stroke-width="3.5"/>
  <path d="M 440 250 Q 530 220 574 122" fill="none" stroke="#2563eb" stroke-width="3.5"/>
  <g fill="#ffffff" stroke="#94a3b8" stroke-width="3">
    <circle cx="80" cy="110" r="11"/><circle cx="200" cy="110" r="11"/><circle cx="320" cy="110" r="11"/>
    <circle cx="80" cy="250" r="11"/><circle cx="200" cy="250" r="11"/><circle cx="320" cy="250" r="11"/>
  </g>
  <circle cx="440" cy="110" r="13" fill="#ffffff" stroke="#dc2626" stroke-width="3"/>
  <circle cx="580" cy="110" r="13" fill="#ffffff" stroke="#dc2626" stroke-width="3.5"/>
  <circle cx="440" cy="250" r="13" fill="#ffffff" stroke="#d97706" stroke-width="3"/>
  <polygon points="580,110 568,104 568,116" fill="#dc2626"/>
  <polygon points="576,124 579,109 564,117" fill="#2563eb"/>
  <g font-size="14" font-weight="600" fill="#172333" text-anchor="middle">
    <text x="440" y="145">v</text>
    <text x="580" y="80">v&#8321; (deleted)</text>
    <text x="440" y="285">v&#8322;</text>
  </g>
  <g font-size="13" fill="#64748b" text-anchor="middle">
    <text x="80" y="82">p&#8321;: &#8230;</text>
    <text x="80" y="222">p&#8322;: &#8230;</text>
  </g>
  <text x="640" y="180" font-size="12.5" fill="#dc2626" font-style="italic">red arrow: p&#8321;&#8217;s own last step</text>
  <text x="640" y="200" font-size="12.5" fill="#2563eb" font-style="italic">blue arrow: the end-to-end splice</text>
  <text x="40" y="330" font-size="12" fill="#64748b">After deleting v&#8321;, any cover of D&#8242; that shrinks the end-set must re-enter along the red arrow (its path ends at v), the blue arrow (ends at v&#8322;), or as a singleton &#8212; and every route shrinks the end-set again.</text>
</svg>
```

**P′ is end-minimal in D′.** Suppose not: some cover Q′ of D′ has Ends(Q′) ⊊ Ends(P′) = {v, v₂, …, v_k}. Reinsert v₁ — there are three routes, and each one contradicts P's end-minimality in D:

- **Red route:** if v is an end of Q′, extend that path by the red arrow v → v₁. The new cover of D has end-set (Ends(Q′) ∖ {v}) ∪ {v₁} — v is missing from it, but v belongs to Ends(P): a proper subset. ✗
- **Blue route:** else if v₂ is an end of Q′, extend that path by the blue arrow v₂ → v₁. Now v₂ is missing: a proper subset again. ✗
- **Singleton route:** else neither v nor v₂ ends a path of Q′, so Ends(Q′) misses at least two of {v, v₂, …, v_k} — it has at most k − 2 elements. Add the one-vertex path {v₁}: even after gaining v₁ the end-set has at most k − 1 elements and still misses v₂: a proper subset. ✗

Every route shrinks the end-set, and end-minimality forbids all three. So P′ is end-minimal in D′, and the induction hypothesis applies: P′ has an independent cross-cut S′. But S′ avoids v₁, so no arrow of D among S′'s vertices was deleted — S′ is independent in D itself. And its choices still hit p₁′ ⊆ p₁ and every other p_i: it is an independent cross-cut of the original P. ∎

Sit back and see the shape: an extremal cover, an arc that tempts a merge, a deletion, and a three-way case check that the *nested* minimality absorbs. No counting, no degree sums — pure structure. That is why Gallai–Milgram generalizes so far.

### 7.3 What the theorem buys

**(a) The partition form.** |cover| = |cross-cut| ≤ α: every digraph splits into at most α directed paths. **(b) Rédei.** A tournament has α = 1, so one directed path covers everyone — Exercise 20's insertion argument finds it constructively; Gallai–Milgram explains *why it must exist*. **(c) A length bound for free.** If the longest directed path of D has ℓ vertices, then n ≤ ℓ·α, so some directed path has at least **n/α** vertices — every digraph with small independence number is forced to contain a long directed path (pigeonhole over the ≤ α covering paths). **(d) Undirected graphs too.** Replace each edge by arrows both ways: undirected paths are directed paths of the biorientation, so every *undirected* graph also covers by ≤ α paths and contains a path on ≥ n/α vertices.

And the family resemblance goes deeper. Take a partially ordered set, view it as a digraph (arrow from smaller to larger), and make it transitive: directed paths are *chains*, independent sets are *antichains* — and Gallai–Milgram becomes **Dilworth's theorem** (Chapter 5, Lecture 5): a poset of width w splits into w chains. Gallai–Milgram is Dilworth with the transitivity sanded off — the proof above never used it.

**The bound is honest.** Take n/2 disjoint arrows (n even) and nothing else: a directed path cannot leave its own arrow, so a cover needs at least n/2 paths — and the n/2 arrows are exactly such a cover. Meanwhile picking one endpoint from each arrow gives an independent set of size n/2, so α = n/2: cover and independence meet exactly at α. (The empty digraph is the other equality: n paths, α = n.)

**What you now own:** end-minimality — extremality by inclusion, minimal not by size but by a nested quantity (P8's spirit, P15's mechanics) — the cross-cut way of seeing transversal witnesses, and a theorem that quietly unifies Rédei and Dilworth.

---

## The Trick Bag (reference card)

| Pattern | Plain language | Where you met it |
|---------|---------------|-----------------|
| **P2 Double counting** | One table, two totals; the disagreement is the theorem | L1.1 |
| **P7 Parity / handshaking** | Σd = 2m; evenness falls out for free | L1.2, L5.1 |
| **P9 Pigeonhole (refined)** | More objects than boxes — after deleting the impossible boxes; overlap-of-majorities version in Dirac | L1.4, L6.1 |
| **P8 Longest path / extremal** | Corner the endpoint(s); the border has nowhere to hide | L2.1, L3.1, L6.1 |
| **P4 Leaf induction** | Peel the leaf; the structure powers the induction | L1.3, L3.2 |
| **P1 Bijection** | Name every object by a sequence (Prüfer); count sequences instead | L4 |
| **P18 Algorithmic proof** | The procedure is the proof; termination = theorem | L2.2, L3.3, L5.2 |
| **P15 Induction on vertices** | Delete a vertex; extend the solution back through the boundary | L7 |
| **The Ore move (lore)** | Generalize the statement until the proof-engine closes, and no further | L6.2 |
| **The closure move (lore)** | Add what cannot change the answer; argue about the saturated object | L6.4 |
| **End-minimality (lore)** | Extremality by inclusion, not size — the nested quantity survives deletion | L7 |

**Formula box:** Σ_v d(v) = 2m; even number of odd-degree vertices. δ ≥ 2 ⇒ a cycle. Trees: connected+acyclic ⇔ connected with n−1 edges ⇔ unique paths; forest with k parts: n − k edges. Cayley: n^{n−2} labeled trees; with degrees (dᵢ): (n−2)!/Π(dᵢ−1)!. Euler tour ⇔ connected + all degrees even (trail: ≤ 2 odd). Dirac: n ≥ 3, δ ≥ n/2 ⇒ Hamiltonian. Ore: d(u)+d(v) ≥ n on all non-adjacent pairs ⇒ Hamiltonian. Closure: non-adjacent u, v with d(u)+d(v) ≥ n — adding uv keeps Hamiltonicity intact. Chvátal: d_k ≥ k+1 or d_{n−k} ≥ n−k for all k < n/2 ⇒ Hamiltonian. Pósa: d_k ≥ k+1 for all k < n/2 ⇒ Hamiltonian. Gallai–Milgram: every digraph covers by ≤ α vertex-disjoint directed paths (end-minimal cover + independent cross-cut); some directed path has ≥ n/α vertices.

---

## Exercises (graded: ●○○ easy · ●●○ moderate · ●●● tough)

*Hints are here; worked answers are at the end of the chapter. Try first.*

**Easy — one idea, applied directly**

1. (●○○) **The hypercube.** Q_n is the graph whose vertices are the 2ⁿ bitstrings of length n, two vertices adjacent when their strings differ in exactly one bit. Compute its number of edges with Lecture 1's machine — no listing allowed. Then decide for which n the hypercube has an Euler tour. *Hint: P2 — first find every vertex's degree; then Lecture 5's theorem does the rest.*
2. (●○○) **Euler tours in the two famous families.** For which n does K_n have an Euler tour? For which m, n does K_{m,n}? *Hint: Lecture 5's theorem turns both questions into pure parity bookkeeping (P7).*
3. (●○○) **Prüfer, by hand.** (a) Encode the star on {1, 2, 3, 4, 5} centered at 5. (b) Decode (2, 1, 4) and draw the tree. (c) Re-encode your answer to (b) — you must recover (2, 1, 4). *Hint: Lecture 4.1's algorithm, run with a pencil; the round trip is the point.*
4. (●○○) A forest has 12 vertices and 9 edges. How many components does it have? And can a graph on 10 vertices with 8 edges be connected? *Hint: Lecture 3.3's n − k for the first; the n − 1 floor of Lecture 3.2 for the second.*

**Moderate — two ideas, or one tricky step**

5. (●●○) Every graph with m ≥ n edges contains a cycle — *hint: P4/P8 — a spanning forest has at most n−1 edges (L3.2); the surplus edge has both ends in one tree component, and in a tree two vertices have a unique path... which plus that edge closes a cycle*.
6. (●●○) **Counting leaves.** Prove that in any tree, the number of leaves is **2 + Σ (d(v) − 2)**, the sum over vertices of degree ≥ 3. Check it on the star, the path, and the full binary trees. *Hint: P2 — Lecture 1's degree-sum bookkeeping, run on Lecture 3's n − 1 edges.*
7. (●●○) How many labeled trees on {1,…,n} have a given degree sequence (d₁,…,d_n)? Then: how many labeled trees on {1,…,6} are *paths*? How many are *stars*? Verify the two answers add up sensibly against Cayley's 6⁴ = 1296. *Hint: P1, the Prüfer dictionary (L4.4); for the paths, choose the two leaves first.*
8. (●●○) A graph is bipartite iff it contains no odd cycle — *hint: P18 (attempt to 2-color by distance-parity from a root) + P8 (an odd closed walk contains an odd cycle — chase the first repeat as in L2.2)*.
9. (●●○) A directed graph in which in-degree = out-degree at every vertex decomposes into edge-disjoint directed cycles — *hint: P18 walk-and-splice exactly as in L5.2 (follow edges greedily; parity of in/out degrees means you can only get stuck where you started)*.
10. (●●○) Prove δ ≥ n/2 forces connectivity; then show the bound is honest — *hint: P9 for the lemma (each component ≥ δ+1 vertices); P11 for tightness (two cliques K_{n/2})*.
11. (●●○) Show Ore's n is honest: a graph with d(u) + d(v) ≥ n − 1 for all non-adjacent pairs need not be Hamiltonian — *hint: P11 (a clique K_{n−1} plus one pendant vertex hanging off it)*.
12. (●●○) **Pósa versus Dirac.** (a) Show that Dirac's hypothesis implies Pósa's condition. (b) Exhibit a graph on six vertices that satisfies Pósa's condition but not Dirac's — any realization of the degree sequence (2,3,3,3,3,4) will do; find one by hand and check its degrees. *Hint: for (a), sort and compare (§6.4's translation: δ ≥ n/2 makes d_k ≥ ⌈n/2⌉); for (b), P11 — six vertices, nine edges, one poor vertex of degree 2.*
13. (●●○) **Degree-sequence diagnostics.** For each of the three graphs — K_{3,4}; the Petersen graph; your witness from Exercise 12 — decide: Dirac? Pósa? Chvátal? Hamiltonian? (The Petersen graph's refusal of a Hamilton cycle is the lab's verified fact; you may quote it.) *Hint: sort the degrees and walk §6.4's two conditions index by index; watch where each dies.*
14. (●●○) **Gallai–Milgram workout.** From the cross-cut form, deduce: (a) the partition form (at most α paths); (b) Rédei's theorem; (c) every digraph on n vertices with independence number α contains a directed path on at least n/α vertices; (d) the bound is honest — n/2 disjoint arrows (n even) force cover = α exactly. *Hint: a cross-cut holds one vertex per path (P9 for (c)); for (d), show each path is trapped inside its own arrow.*

**Tough — several chapter ideas combined**

15. (●●●) **The two extremes of a tree.** Among all trees on n vertices, prove that the **star minimizes** and the **path maximizes** the total of all pairwise distances. *Hint: P2 — double-count by edges: every edge of a tree splits it into pieces of sizes s and n − s, and a pair's path uses that edge exactly when the pair straddles the split. For the maximum, P4 — peel a leaf, and bound how far the surviving vertices sit from its neighbor.*
16. (●●●) **The centroid.** Prove that every tree has a *centroid*: a vertex whose removal leaves pieces of at most n/2 vertices each. *Hint: P8/P18 — start anywhere; if some piece of T − v outweighs half the tree, walk into it and watch the heaviest piece shrink. Then ask: how many centroids can a tree have, and where do they sit?*
17. (●●●) **The hypercube has a Hamilton tour.** Prove that Q_n (Exercise 1's graph) has a Hamilton cycle for every n ≥ 2. *Hint: P4 — split Q_n into two copies of Q_{n−1} joined by a perfect matching; break an edge of the smaller cube's Hamilton cycle and re-thread both copies. Your construction will hand you a **Gray code** — a cyclic listing of all n-bit strings in which consecutive strings differ in exactly one bit.*
18. (●●●) **Pósa's rotation lemma.** Let P be a longest path of a graph G. A *Pósa rotation* of a path (x₁, x₂, …, x_m) is the path (x_{j−1}, x_{j−2}, …, x₁, x_j, x_{j+1}, …, x_m) built on a chord x₁–x_j (j ≥ 2) — same vertices, new endpoint. Let R be the set of all endpoints obtainable from P by any sequence of rotations, performed at either end. Prove: **(a)** every x ∈ R has all its neighbors on P; **(b)** every x ∈ R has degree at most |R|. (These two facts are the engine of Pósa's own 1962 proof — with the degree condition's counting, they already force more than n/2 reachable endpoints.) *Hint: for (a), extend the witnessing path; for (b), P9 — the map sending each neighbor to its predecessor on the witnessing path is injective and lands inside R.*

**Pattern unknown — you choose the tool** *The graded set above tells you which lecture idea to reach for — research and exams do not. No hints here, and no difficulty rating either: diagnosing the problem is part of the problem. Worked answers still wait at the end.*

19. (◆) How many labeled trees on {1, …, n} have vertex 1 as a leaf?
20. (◆) In a *tournament* — n players, every pair plays once, every game has a winner — show the results can always be listed so that each player beat the next: a directed Hamilton path.
21. (◆) Prove that every graph on n ≥ 3 vertices with at least **C(n−1, 2) + 2** edges is Hamiltonian. Is the bound honest?
22. (◆) **Orientations and colorings.** Let χ(G) be the *chromatic number* — the least number of colors needed to color the vertices so that adjacent vertices get different colors (Chapter 3 studies it; here only the definition is needed). Prove the **Gallai–Hasse–Roy–Vitaver theorem**: χ(G) equals the minimum, over all ways of orienting the edges of G, of the number of vertices on the longest directed path. (No hint — finding which of this chapter's ideas fits is the assignment.)

**Graded backfill — five more, each hint naming its pattern**

23. (●○○) **Regularity, checked by parity.** (a) Why can no 7-vertex graph have every vertex of degree exactly 3? (b) Build a 6-vertex graph that does it. (c) Prove the general law: a k-regular graph on n vertices exists **iff nk is even and k < n**, by building one whenever the two conditions hold. *Hint: (a) is P7 — Lecture 1's degree-sum machine; (c) is P11 — place the vertices on a cycle and connect each to its k/2 nearest neighbors on each side, handling odd k by the across-the-circle antipodal pairing (which forces n even — exactly the parity you already owe).*
24. (●●○) **Forcing leaves through Prüfer.** Fix a set S of s vertices. How many labeled trees on {1,…,n} have *every vertex of S* as a leaf (the others unrestricted)? *Hint: P1 — Lecture 4.4's dictionary again: a vertex is a leaf exactly when its Prüfer count is zero, so the codes you must count are those drawn from a shrunken alphabet.*
25. (●●○) **The center of a tree.** The *eccentricity* of a vertex is its largest distance to any other vertex; the *center* is the set of vertices of minimum eccentricity. Prove that every tree's center is either a single vertex or two adjacent vertices. *Hint: P8/P18 — take a longest path (its endpoints are the tree's extreme points, Lecture 2.1's reflex); watch what the eccentricities do along it, then peel the outermost vertices away and watch the center refuse to move.*
26. (●●●) **Hamilton paths at half minus one.** Prove that every graph on n vertices with minimum degree δ ≥ (n−1)/2 contains a Hamilton *path* — strictly less than Dirac asks, and strictly more than Dirac returns. Then show the bound is honest. *Hint: P15 fused with Lecture 6 — pad the graph with one universal vertex and bill Dirac for the new graph; remove the guest and a Hamilton cycle becomes a Hamilton path. For honesty, P11 in reverse: two disjoint cliques.*
27. (●●●) **The exact leaf set.** Exercise 24 counted trees in which S's vertices are all leaves — but the *other* vertices were allowed to be leaves too. Count the labeled trees on {1,…,n} whose leaf set is **exactly** a fixed set L of size k ≥ 2. *Hint: P1 then P3 — Prüfer codes over the alphabet {1,…,n} ∖ L in which **every** letter is used at least once; the zigzag of inclusion–exclusion handles the "at least once."*

**Explorations — ◐ research-style training** *No single right answer — what you should find is described in each. These train the habit research actually runs on: changing the problem.*

X1. (◐) **How many trees are there, really?** Cayley's n^{n−2} counts trees on *labeled* vertices. Strip the labels: how many different *shapes* of tree are there on n vertices? Enumerate all labeled trees by Prüfer and deduplicate under relabeling (n = 8 has 262,144 labeled trees; a Raspberry Pi chews through it easily). You should find the shape-counts begin 1, 1, 1, 2, 3, 6 — and fall further and further behind n^{n−2} as n grows. Meditate on why: the Prüfer bijection is *powered* by labels — which vertex a code word names — and symmetry is exactly what a bijection cannot digest. Counting unlabeled objects in general is where a famous later machine (Pólya's) begins; this exploration is its seed.

X2. (◐) **How far apart is a random pair of vertices?** Exercise 15 brackets every tree between the star's compactness and the path's sprawl. Now generate *random* trees — a random Prüfer code is a uniformly random labeled tree — and measure the average total pairwise distance for n = 4, 5, 6, 7, 8. You should find the average sitting far above the star's floor yet clearly below the path's ceiling — and you should measure how it grows with n before suspecting its growth rate: it is a famous one, and no lecture of this chapter proves it. (That is the discovery cycle's sixth stage running: generalize, and meet the first question this chapter honestly cannot answer.)

---

## Computational Lab (verified)

### Part 1 — The Prüfer bijection, round-tripped (verified 2026-10-09)

```python
from collections import Counter

def prufer_encode(edges, n):
    adj = {v: set() for v in range(1, n + 1)}
    for u, v in edges: adj[u].add(v); adj[v].add(u)
    alive, seq = set(range(1, n + 1)), []
    for _ in range(n - 2):
        leaf = min(v for v in alive if len(adj[v] & alive) == 1)
        nb = (adj[leaf] & alive).pop()
        seq.append(nb); alive.remove(leaf)
    return seq

def prufer_decode(seq, n):
    cnt = Counter(seq)
    pool = [v for v in range(1, n + 1) if cnt[v] == 0]
    edges = []
    for a in seq:
        leaf = min(pool); pool.remove(leaf)
        edges.append((leaf, a))
        cnt[a] -= 1
        if cnt[a] == 0: pool.append(a)
    pool.sort()
    edges.append((pool[0], pool[1]))
    return edges
```

**Verified output (2026-10-09):** 40/40 random Prüfer sequences (n = 6) survive the round trip sequence → tree → sequence; decoding all 16 length-2 sequences over {1,2,3,4} yields **16 distinct edge sets** — Cayley's formula n^{n−2} = 4² = 16, confirmed by total enumeration.

### Part 2 — Dirac's theorem verified by exhaustion (verified 2026-10-10)

No randomness needed: for n = 6 there are only 2^15 = 32768 graphs, and we can check *every single one*. Dirac's hypothesis is δ ≥ n/2 = 3; the claim is that all such graphs are Hamiltonian.

```python
def has_hamilton_cycle(adj, n):
    visited = [False] * n
    found = False
    def dfs(v, count):
        nonlocal found
        if found: return
        if count == n:
            if adj[v][0]: found = True
            return
        for u in range(n):
            if adj[v][u] and not visited[u]:
                visited[u] = True; dfs(u, count + 1); visited[u] = False
    visited[0] = True; dfs(0, 1)
    return found

n = 6
pairs = [(a, b) for a in range(n) for b in range(a + 1, n)]
dirac_total = dirac_ham = tight_witnesses = 0
for mask in range(1 << len(pairs)):        # all 32768 graphs
    adj = [[False]*n for _ in range(n)]
    deg = [0]*n
    for i, (a, b) in enumerate(pairs):
        if mask >> i & 1:
            adj[a][b] = adj[b][a] = True; deg[a] += 1; deg[b] += 1
    d = min(deg)
    if d < 2: continue
    ham = has_hamilton_cycle(adj, n)
    if d >= 3:
        dirac_total += 1; dirac_ham += ham   # Dirac's territory
    elif not ham:
        tight_witnesses += 1                  # delta = n/2 - 1 and NO Hamilton cycle

# Tightness witnesses: two disjoint triangles, and the Petersen graph
tri = [[False]*6 for _ in range(6)]
for a, b in [(0,1),(0,2),(1,2),(3,4),(3,5),(4,5)]:
    tri[a][b] = tri[b][a] = True            # delta = 2 = n/2 - 1, disconnected
P = [[False]*10 for _ in range(10)]
def add(g, a, b): g[a][b] = g[b][a] = True
for i in range(5): add(P, i, (i+1) % 5); add(P, i, i + 5)
for a, b in [(5,7),(7,9),(9,6),(6,8),(8,5)]: add(P, a, b)  # Petersen, 3-regular
print(dirac_total, dirac_ham, tight_witnesses,
      has_hamilton_cycle(tri, 6), has_hamilton_cycle(P, 10))
```

**Verified output (2026-10-10):** all 32768 graphs on 6 vertices enumerated. **1858** of them satisfy Dirac's hypothesis δ ≥ 3, and **all 1858 are Hamiltonian — zero violations** (a check, not a proof: Dirac's proof is Lecture 6). With δ = 2 = n/2 − 1 there are **1990 non-Hamiltonian witnesses**, starting with K_{2,4} — connected yet still tourless (L6.3). The two disjoint triangles: degrees (2,2,2,2,2,2), no Hamilton cycle ✓. The Petersen graph: 3-regular as expected, **no Hamilton cycle** ✓.

**The count-it-twice bonus.** The number 1858 was itself double-checked the Chapter 1 way: δ(G) ≥ 3 on 6 vertices holds exactly when the *complement* has maximum degree ≤ 2, i.e., is a disjoint union of paths and cycles. A careful hand count of those (partitions of 6 into path/cycle blocks: 420 + 432 + 225 + 225 + 160 + 240 + 80 + 15 + 45 + 15 + 1) gives exactly **1858** ✓. Confession, because it is instructive: the first hand count gave 1903 — a disagreement of 45 — and the audit found the slip (graphs of type "two disjoint edges plus two isolated vertices" come in 45 splits, not 90: choose the two singletons first, C(6,2) = 15 ways, then split the remaining four into pairs, 3 ways). *When two honest counts disagree, the disagreement itself is the finding: it tells you exactly where one of your bookkeepings lies.* That is Lecture 3 of Chapter 1, running live in a new costume.

**What to explore:** re-run with n = 7 (2^21 ≈ 2M graphs — a Raspberry Pi handles this in minutes) and confirm Dirac's territory is again 100% Hamiltonian; count non-Hamiltonian graphs with δ = 2 for larger n; verify Exercise 10's tightness examples.

### Part 3 — Pósa, Chvátal, and the closure, verified by exhaustion (verified 2026-10-10)

Three conditions on the sorted degrees d₁ ≤ … ≤ d_n (k < n/2 throughout): **Pósa** d_k ≥ k+1; **Chvátal** d_k ≥ k+1 or d_{n−k} ≥ n−k; and the *weak* condition d_k ≥ k that §6.4 warns about. Plus the closure lemma: adding an edge between non-adjacent u, v with d(u) + d(v) ≥ n must never change Hamiltonicity — in either direction.

```python
def census(n):                      # has_hamilton_cycle is Part 2's
    pairs = [(a, b) for a in range(n) for b in range(a + 1, n)]
    counts = {'posa': 0, 'posa_nh': 0, 'chv': 0, 'chv_nh': 0,
              'weak': 0, 'weak_nh': 0}
    for mask in range(1 << len(pairs)):
        adj = [[False] * n for _ in range(n)]
        deg = [0] * n
        for i, (a, b) in enumerate(pairs):
            if mask >> i & 1:
                adj[a][b] = adj[b][a] = True; deg[a] += 1; deg[b] += 1
        s = sorted(deg); rng = range(1, (n + 1) // 2)   # k < n/2
        p = all(s[k - 1] >= k + 1 for k in rng)
        c = all(s[k - 1] >= k + 1 or s[n - k - 1] >= n - k for k in rng)
        w = all(s[k - 1] >= k for k in rng)
        ham = has_hamilton_cycle(adj, n)
        for ok, tag in ((p, 'posa'), (c, 'chv'), (w, 'weak')):
            if ok:
                counts[tag] += 1
                if not ham: counts[tag + '_nh'] += 1
    return counts

def closure_check(n):               # Ham(G) must equal Ham(G+uv), both ways
    pairs = [(a, b) for a in range(n) for b in range(a + 1, n)]
    checked = disagreed = 0
    for mask in range(1 << len(pairs)):
        adj = [[False] * n for _ in range(n)]
        deg = [0] * n
        for i, (a, b) in enumerate(pairs):
            if mask >> i & 1:
                adj[a][b] = adj[b][a] = True; deg[a] += 1; deg[b] += 1
        for i, (u, v) in enumerate(pairs):
            if not (mask >> i & 1) and deg[u] + deg[v] >= n:
                checked += 1
                adj[u][v] = adj[v][u] = True
                flip = has_hamilton_cycle(adj, n)
                adj[u][v] = adj[v][u] = False
                if flip != has_hamilton_cycle(adj, n): disagreed += 1
    return checked, disagreed

print([census(n) for n in (4, 5, 6)], closure_check(6))
```

**Verified output (2026-10-10):** n = 4, 5, 6 censuses — Pósa survivors 10, 86, 5218, **zero non-Hamiltonian in all three**; Chvátal survivors 10, 146, 5788, **zero non-Hamiltonian**; the weak condition's survivors 41, 513, 21,218 — of which **31, 295, 11,140 are tourless** (K_{3,4} is the n = 7 emissary of this army: it fails Pósa and Chvátal exactly at k = 3 and refuses the tour). Closure lemma at n = 6: **35,520 qualifying (G, u, v) triples, zero disagreements** — the added edge never created and never destroyed a Hamilton cycle. **At n = 7 the census ran over all 2,097,152 graphs: Pósa survivors 197,726 and Chvátal survivors 354,806 — still zero violations.** The strictness chain is populated: on six vertices, 1858 Dirac graphs ⊂ 5218 Pósa graphs ⊂ 5788 Chvátal graphs — 3360 certified by Pósa but not Dirac, 570 more reached only by Chvátal (all 570 verified Hamiltonian, e.g. the degree sequence (2,2,2,4,4,4)); and all **1080** realizations of (2,3,3,3,3,4) — a Pósa-not-Dirac sequence — are Hamiltonian. (Checks, not proofs: the proofs are §6.4.)

**What to explore:** raise the census to n = 7 (2^21 graphs — minutes on a Raspberry Pi) and watch all three counts grow with zero violations; find the smallest graph satisfying Chvátal but *no* lecture theorem — then explain why none can exist.

### Part 4 — Gallai–Milgram, verified by exhaustion (verified 2026-10-10)

Every loopless digraph on n vertices is a bitmask over its n(n−1) possible arcs. `min_path_cover` is exact (a subset DP: which vertex sets can be arranged into one directed path, then how few such paths cover everything); `alpha_underlying` is exact too (independence in the graph that forgets arrow directions).

```python
def min_path_cover(out_adj, n):
    full = (1 << n) - 1
    hstart = [0] * (full + 1)      # hstart[S] = possible starting vertices of a directed path spanning S
    for S in range(1, full + 1):
        for u in range(n):
            if S >> u & 1:
                if S == 1 << u:
                    hstart[S] |= 1 << u
                elif hstart[S ^ (1 << u)] & out_adj[u]:
                    hstart[S] |= 1 << u
    dp = [n + 1] * (full + 1); dp[0] = 0
    for S in range(1, full + 1):
        T = S
        while T:                    # all submasks of S
            if hstart[T] and dp[S ^ T] + 1 < dp[S]:
                dp[S] = dp[S ^ T] + 1
            T = (T - 1) & S
    return dp[full]

def alpha_underlying(out_adj, n):
    und = [0] * n
    for a in range(n):
        for b in range(n):
            if out_adj[a] >> b & 1:
                und[a] |= 1 << b; und[b] |= 1 << a
    best = 0
    for S in range(1, 1 << n):
        if all(not (und[v] & S) for v in range(n) if S >> v & 1):
            best = max(best, bin(S).count("1"))
    return best

for n in (4, 5):                    # 4096 and 1,048,576 digraphs
    arcs = [(a, b) for a in range(n) for b in range(n) if a != b]
    violations = 0
    for amask in range(1 << len(arcs)):
        out_adj = [0] * n
        for i, (a, b) in enumerate(arcs):
            if amask >> i & 1:
                out_adj[a] |= 1 << b
        if min_path_cover(out_adj, n) > alpha_underlying(out_adj, n):
            violations += 1
    print(n, "vertices:", 1 << len(arcs), "digraphs,", violations, "violations")

print(min_path_cover([0b0010, 0, 0b1000, 0], 4))    # two disjoint arrows: 0 -> 1 and 2 -> 3, cover 2 = alpha
```

**Verified output (2026-10-10):** n = 4 — all **4096** digraphs enumerated, min cover ≤ α with **zero violations**; n = 5 — all **1,048,576** digraphs, **zero violations**. The proof's own claim was tested too: at n = 4, all **77,824** path covers of all digraphs were enumerated, the **15,325** end-minimal covers among them isolated, and **every single one admits an independent cross-cut — zero failures** (as Lecture 7's induction promises). The witnesses of sharpness: two disjoint arrows on 4 vertices have cover 2 = α, and three disjoint arrows on 6 vertices have cover 3 = α (the printed check) — equality, not just ≤. And the Rédei connection held exactly: all **64** tournaments on 4 vertices and all **1024** on 5 vertices are covered by a single directed path. (Checks, not proofs: the proof is Lecture 7.)

**What to explore:** push to n = 6 for tournaments (2^15 orientations of K_6 — cover 1 every time, Rédei again); modify `min_path_cover` to return the cover itself and *watch* the cross-cut appear; find a digraph where the minimum cover is *forced* to have its endpoints adjacent — then verify that its cross-cut still exists, just as the three-vertex example in Lecture 7 promises.

---

## Answers to the Exercises

*Attempt everything first — the value is in the attempt; these pages will still be here when you return.*

**A1.** Every vertex of Q_n has exactly n neighbors — flip any one of the n bits. So Σd = n · 2ⁿ, and Lecture 1 equates that to 2m: **m = n·2ⁿ⁻¹** (P2). Check n = 3: 3·4 = 12 edges. For the Euler tour: Q_n is connected (flip bits one at a time to walk any string down to 00…0), and *every* degree equals n — so by Lecture 5 the tour exists **iff n is even**. Machine check: edge counts 1, 4, 12, 32, 80 for n = 1..5, all regular of degree n; Hierholzer's algorithm finds tours on Q_2 and Q_4, and correctly refuses Q_3 and Q_5 (odd degrees).

**A2.** K_n: every degree is n − 1, so the tour exists **iff n is odd** (n ≥ 3). K_{m,n}: the m side vertices have degree n, the n side vertices degree m — all even **iff m and n are both even**. Watch the trap: K_{3,3} is regular and lovely, but degree 3 is odd — no tour. Machine check: tours on K_3, K_5, K_{2,2}, K_{2,4}, K_{4,4}; none on K_4, K_6, K_{2,3}, K_{3,3}, K_{3,4}.

**A3.** (a) The star centered at 5: leaves 1, 2, 3, 4. Smallest leaf 1 → write 5, delete; then 2 → 5; then 3 → 5. Code **(5, 5, 5)**. (b) Decoding (2, 1, 4): the labels *absent* from the code are {3, 5} — those are the leaves-to-be. Take the smallest, 3: join 3–2 (2's remaining count drops to zero, so 2 joins the pool). Take 2: join 2–1 (1 joins the pool). Take 1: join 1–4 (4 joins). Survivors {4, 5}: join them. The tree is 3–2, 2–1, 1–4, 4–5 — **the path 5–4–1–2–3**, with 1 in the middle. (c) Re-encode: leaves 3 and 5; smallest 3, write its neighbor 2, delete; leaves 2 and 5; smallest 2, write 1, delete; leaves 1 and 5; smallest 1, write 4; code **(2, 1, 4)** ✓ — the round trip closes, as a bijection must (Lecture 4.3).

**A4.** Forests obey m = n − k (Lecture 3.3): 9 = 12 − k gives **k = 3** components. And a connected graph contains a spanning tree, so m ≥ n − 1: 8 < 9, so **no** — 10 vertices and 8 edges cannot be connected. Machine check: the identity m = n − k holds on all 291 labeled forests on 5 vertices (every one of the 1024 five-vertex graphs was classified).

**A5.** Suppose G were acyclic: then it is a forest, and forests have m = n − k ≤ n − 1 (Lecture 3.3) — but m ≥ n. Contradiction: **every graph with m ≥ n edges has a cycle**. (The localized version, from the hint: a spanning forest uses at most n − 1 of the m edges, so some edge e lies inside one tree component; its endpoints have a unique path between them in the tree, and that path plus e closes the cycle — you even know *where* the cycle lives.) Machine check: on 5 vertices, all 291 acyclic graphs have m ≤ 4, and all 638 graphs with m ≥ 5 contain a cycle.

**A6.** Bookkeeping (P2): in a tree, Σd = 2m = 2(n − 1). Split the vertices into leaves (L of them), degree-2 vertices (n₂), and the rest, and write Σd = L + 2n₂ + Σ_{d≥3} d(v). Since n = L + n₂ + n₃₊: 2(L + n₂ + n₃₊) − 2 = L + 2n₂ + Σ_{d≥3} d(v), so Σ_{d≥3} d(v) = L + 2n₃₊ − 2, i.e. **L = 2 + Σ_{d≥3} (d(v) − 2)**. Checks: the path — the sum is empty, L = 2 ✓; the star — 2 + (n − 1 − 2) = n − 1 leaves ✓; the full *unrooted* binary tree — every non-leaf vertex has degree 3, contributing exactly 1 each, so L = 2 + (number of internal vertices) — mind the rooted reading: a rooted full binary tree has a degree-2 root, and there L = I + 1 instead. Machine check: zero violations across all 16 + 125 + 1296 + 16807 labeled trees on 4, 5, 6, 7 vertices.

**A7.** The Prüfer dictionary (Fact 1): label i is written exactly d(i) − 1 times. So trees with degree sequence (d₁, …, d_n) ↔ code words in which letter i appears dᵢ − 1 times — a multinomial: **(n − 2)! / Πᵢ (dᵢ − 1)!**. Paths on {1, …, 6}: pick the two leaves, C(6,2) = 15 ways; all other degrees are 2, so each choice contributes 4!/(1!)⁴ = 24 codes: **15 × 24 = 360 = 6!/2** (as it must be: order the 6 labels, divide by the two directions — two bookkeepings agreeing again). Stars: pick the center, 6 ways, each with 4!/4! = 1 code: **6**. Machine check: enumerating all 1296 codes for n = 6 confirms exactly 360 path trees, 6 stars, and exactly 24 trees in which 1 and 2 are the two leaves; at n = 5 the census is 5 stars + 60 paths + 60 of the remaining type = 125 = Cayley ✓.

**A8.** (⇐) Fix a component, root it anywhere at r, and color v by d(r, v) mod 2. Claim: every edge joins opposite colors. If an edge xy joined same-colored vertices, then d(r,x) + 1 + d(r,y) is odd — a closed walk of odd length. **Lemma (odd closed walks breed odd cycles):** in a closed walk v₀…v_m with m odd, chase the first repeat exactly as in Lecture 2.2; the walk splits at it into two closed walks whose lengths sum to m — one of them is odd and strictly shorter. Induct: a shortest odd closed walk repeats nothing but its endpoints, which makes it an *odd cycle*. That contradicts the hypothesis, so the coloring is proper: **bipartite**. (⇒) Walk around an odd cycle: each edge demands a color flip, and an odd number of flips cannot return you to your starting color — no 2-coloring exists. Machine check: on all 1024 graphs on 5 vertices, BFS-bipartiteness agrees with brute-force odd-cycle search on every single graph (376 bipartite, 648 carrying an odd cycle — agreement 1024/1024).

**A9.** Walk greedily: from the start s, keep following unused edges. Where can you get stuck? Only where no unused *out*-edge remains. Every pass through a vertex w ≠ s consumes one in-edge and one out-edge of w; being stuck at w means the walk entered w once more than it left, i.e. used in-edges ≥ used out-edges + 1, i.e. d⁻(w) ≥ d⁺(w) + 1 — impossible when in = out. **So the walk closes at s**: you get a closed directed walk. Now Lecture 2.2's chase (directed version) extracts a directed *cycle* from it; delete that cycle — it removed exactly one in-edge and one out-edge at each of its vertices, so in = out survives everywhere; repeat on the rest. Edges are finite; the machine halts with everything partitioned into directed cycles (P18: procedure = proof). One honest wrinkle, seen live in the machine run: the greedy walk [0, 1, 2, **0**, 3, 4, **0**] on the test digraph *returned to its start and kept going* — closed walks may splice several cycles together; the chase, not the walk, produces the cycle. The full 9-edge example (three cycles sharing vertices) decomposed into 0→1→2→0, 0→3→4→0, 1→5→3→1, edge-disjoint, covering all 9 edges exactly once ✓.

**A10.** Any component of G contains a vertex and all its neighbors: |C| ≥ 1 + δ ≥ 1 + n/2. Two components would then hold at least 2(1 + n/2) = n + 2 > n vertices — so **one component**: connected (P9, the same lemma that served Dirac). Tightness: two disjoint cliques K_{n/2} ⊔ K_{n/2} have δ = n/2 − 1 and no tour of anything — the bound n/2 cannot fall to n/2 − 1. Machine check: all 1858 graphs on 6 vertices with δ ≥ 3 are connected (the same 1858 as the lab's Dirac territory — of course: Dirac graphs are a subclass), and K₃ ⊔ K₃ (δ = 2) is the disconnected witness.

**A11.** Take a clique K_{n−1} and hang one pendant vertex p off one of its vertices. The non-adjacent pairs are exactly (p, x) with x a clique vertex other than p's neighbor: d(p) + d(x) = 1 + (n − 2) = **n − 1** for every such pair — the weakened hypothesis holds. But p is a leaf, and a Hamilton cycle hands every vertex two cycle-edges — a leaf can hold only one. **Not Hamiltonian**; Ore's n is honest. Machine check: n = 5 witness has degrees (4, 3, 3, 3, 1), all non-adjacent pairs summing to exactly 4 = n − 1, and a Hamiltonian search confirms no tour; likewise the n = 6 witness (m = 11, sums 5 = n − 1, no tour).

**A12.** (a) Sort the degrees: every sorted degree d_k ≥ δ, and δ ≥ n/2. For n even and any k < n/2 we have k + 1 ≤ n/2 ≤ d_k; for n odd, δ ≥ n/2 forces δ ≥ ⌈n/2⌉ = (n+1)/2 ≥ k + 1 for every k < n/2. Either way **d_k ≥ k+1 holds on the whole range** — Dirac's hypothesis hands Pósa's condition over at full price (§6.4's translation: δ ≥ n/2 makes d_k ≥ ⌈n/2⌉ ≥ k+1). (b) The witness, on vertices {1, …, 6}, nine edges: 1–3, 1–4, 1–5, 1–6, 2–4, 2–5, 2–6, 3–4, 3–5. Degrees: d(6) = 2 (its neighbors are 1 and 2), d(2) = d(3) = d(4) = d(5) = 3, d(1) = 4 — sorted **(2, 3, 3, 3, 3, 4)**. Dirac refuses it (δ = 2 < 3 = n/2); Pósa bills it exactly: d₁ = 2 ≥ 2 ✓, d₂ = 3 ≥ 3 ✓ — the range ends at k = 2 when n = 6. And the tour is real: **6–1–4–3–5–2–6** (check every edge — 6–1, 1–4, 4–3, 3–5, 5–2, 2–6, all present). Machine check: all **1080** realizations of (2,3,3,3,3,4) on six vertices are Hamiltonian (lab, Part 3) — Pósa keeps his promise on every one of them; Dirac keeps his on none.

**A13.** The diagnostics, run by hand (the lab, Part 3, ran them by machine to n = 7 — zero surprises):

| Graph | sorted degrees | Dirac? | Pósa? | Chvátal? | Hamiltonian? |
|-------|----------------|--------|-------|----------|---------------|
| K_{3,4} | 3,3,3,3,4,4,4 (n = 7) | ✗ (δ = 3 < 3.5) | ✗ dies at k = 3 | ✗ dies at k = 3 | ✗ |
| Petersen | ten 3s (n = 10) | ✗ (δ = 3 < 5) | ✗ dies at k = 3 | ✗ dies at k = 3 | ✗ (lab, Part 2) |
| Exercise 12's witness | 2,3,3,3,3,4 (n = 6) | ✗ (δ = 2 < 3) | ✓ | ✓ (first arm everywhere) | ✓ (A12's cycle) |

K_{3,4}: d₁ = 3 ≥ 2 ✓ and d₂ = 3 ≥ 3 ✓, but at k = 3 the condition demands d₃ ≥ 4 and gets 3 — dead; Chvátal's second arm asks d₄ ≥ 4 and also gets 3 — both die at the same index. Non-Hamiltonian: bipartite with unequal sides, and a bipartite cycle must alternate sides. The Petersen graph: at k = 3 Pósa needs d₃ ≥ 4 (has 3) and Chvátal's fallback needs d₇ ≥ 7 (has 3) — both dead at k = 3 again. And the witness sails through. *The moral is the point of the table: each refusal dies exactly at an index the theorem's range honestly covers — K_{3,4} at k = 3 = ⌊n/2⌋, the last covered index (shrink the range and it slips through, §6.4), the Petersen graph at k = 3 (drop the +1 and it slips through). The theorems refuse precisely where their hypotheses say they may.*

**A14.** (a) The cross-cut form supplies a cover P and an independent cross-cut S — one vertex per path. So |P| = |S|, and S independent means |S| ≤ α: **|P| ≤ α**, the partition form (and the minimum cover is smaller still). (b) A tournament has α = 1 — every pair adjacent in the underlying graph — so one directed path covers all n vertices: **Rédei**, now with a reason *why* (Exercise 20's insertion finds it; Gallai–Milgram guarantees it exists). (c) Cover by at most α paths, n vertices total: if every path held fewer than n/α vertices, the total would fall short of α·(n/α) = n — so some directed path has **at least n/α** vertices (P9, ordinary pigeonhole over the cover). (d) n/2 disjoint arrows (n even): the underlying graph is a perfect matching, so α = n/2 (one endpoint per arrow, never two from the same arrow). And every directed path is trapped inside its own arrow — between two arrows there is no arc to travel — so covering n vertices takes at least n/2 paths; the arrows themselves are exactly such a cover. **Cover = α = n/2 exactly** — the bound is honest. Machine check: min cover ≤ α held on all 4096 digraphs on 4 vertices and all 1,048,576 on 5 vertices, zero violations; the disjoint arrows give cover = α = 2 at n = 4 and 3 at n = 6; and the tournaments returned cover 1 on all 64 + 1024 of them (lab, Part 4).

**A15.** The engine (P2): every edge e of a tree is a bridge, deleting it splits the tree into sides of sizes s_e and n − s_e, and the unique path between u and v uses e *exactly when u and v straddle the split*. So the total distance W(T) = Σ_{pairs} d(u,v) = **Σ_e s_e (n − s_e)** — one sum over the n − 1 edges.
*The star is the floor:* for 1 ≤ s ≤ n − 1 the product s(n − s) is minimized at the ends: s(n − s) ≥ 1·(n − 1). So W(T) ≥ (n − 1)(n − 1) = **(n − 1)²**, with equality iff every edge has s_e ∈ {1, n − 1} — every edge touches a leaf — which forces all edges to share one center: the star.
*The path is the ceiling:* peel a leaf ℓ with neighbor p; distances among survivors are untouched, so W(T) = W(T′) + Σ_{u ∈ T′} (d(u, p) + 1), where T′ is the tree on n − 1 = N vertices. Sub-lemma: for any tree on N vertices and any vertex p, Σ_u d(u, p) ≤ C(N, 2). *Proof:* Σ_u d(u,p) = Σ_{k≥1} #{u : d(u,p) ≥ k}, and the ball of radius k around p holds at least k + 1 vertices (walk toward any farthest vertex; its geodesic supplies k + 1 distinct vertices within distance k) — so #{u : d(u,p) ≥ k} ≤ N − k, and the sum telescopes to N(N−1)/2. Now induct (P4): W(T) ≤ (N³ − N)/6 + N(N−1)/2 + N = ((N+1)³ − (N+1))/6 = **(n³ − n)/6** — the sub-lemma bounds the survivors' distance sum over T′'s N vertices by N(N−1)/2, and the peeled leaf pays its +1 to each of the N survivors — with equality forcing T′ to be a path with p at its end and ℓ hanging off that end — a path again.
Machine check: over *all* labeled trees on n = 4, 5, 6, 7 vertices, the minimum is exactly (n − 1)² (9, 16, 25, 36) attained only by the stars, the maximum exactly (n³ − n)/6 (10, 20, 35, 56) attained only by the paths, and every other tree strictly between. (For n = 5: 5 stars at 16, 60 paths at 20, and the other 60 trees in between.)

**A16.** Start anywhere, at v. If every piece of T − v has ≤ n/2 vertices, v is a centroid. Otherwise some piece H has more than half the tree; let u be v's neighbor inside H, and *walk to u*. Now the pieces of T − u are: the piece holding v, of size n − |H| < n/2 < |H|; and the pieces inside H − u, each of size ≤ |H| − 1. So the heaviest piece shrank from |H| to strictly below |H| — the heaviest-piece size is a positive integer that strictly decreases with every step, so the walk must terminate, and it terminates exactly at a **centroid** (P8/P18: an extremal quantity corners the object). And the census: the centroids are either a single vertex or two adjacent ones (if v and its neighbor u are both centroids, the edge between them splits the tree into exact halves — and a third centroid is impossible). Two centroids force n even — but even n does **not** force two: the 4-vertex star has exactly one (delete its center and three singletons remain, each ≤ n/2 = 2), while the 4-vertex path has two (its middle edge cuts 2 + 2). The exact rule: two centroids occur **iff some edge splits the tree into two halves of n/2 vertices each**. Machine check: all labeled trees on n = 4..7 have 1 or 2 centroids, adjacent whenever two; on odd n (5, 7) every tree has exactly one; on even n both cases occur (n = 4: 4 trees with one, 12 with two; n = 6: 486 with one, 810 with two); and across all 18,244 trees, two centroids ⇔ a halving edge — never otherwise.

**A17.** Induction on n (P4). Base: Q_2 is the 4-cycle itself. Step: Q_n is two copies of Q_{n−1} — last bit 0 and last bit 1 — joined by the perfect matching x ↔ x′. By induction the 0-copy has a Hamilton cycle C; break any one edge x–y of C, leaving a Hamilton *path* from y to x through all of the 0-copy. Now cross the matching x → x′, walk the same cycle backwards through the entire 1-copy from x′ to y′, and cross home y′ → y. The result is a single cycle visiting every vertex of Q_n exactly once: **a Hamilton cycle** (copy-internal moves are honest cube edges; the two matching moves flip exactly the last bit). Unrolled, the cycle lists all 2ⁿ bitstrings with consecutive strings one bit apart — a **Gray code**, the same object that keeps shaft encoders from miscounting and Karnaugh maps from scrambling. Machine check: the construction runs and verifies for n = 2, 3, 4, 5 — lengths 4, 8, 16, 32, all vertices distinct, every consecutive pair (including the closing pair) differing in exactly one bit.

**A18.** First, the invariant: every rotation rebuilds a path on the *same* m vertices of P — no rotation adds or drops a vertex — so every witnessing path is itself a longest path. **(a)** Let x ∈ R, witnessed by a path Q on P's vertices with x as an endpoint, and suppose x had a neighbor y outside P. Then appending y to Q at x's end is a path on m + 1 vertices — longer than the *longest* path. Contradiction: **every neighbor of every x ∈ R lies on P**. **(b)** Let x ∈ R, and read its witnessing path with x first: Q = (x = y₁, y₂, …, y_m) (a right-end witness is read backwards — reversal changes nothing). By (a) every neighbor of x sits on Q, at some position j ≥ 2. For each such neighbor y_j, rotate Q on the chord x–y_j: the rotated path (y_{j−1}, y_{j−2}, …, y₁, y_j, y_{j+1}, …, y_m) is legitimate — its joins are the given edge y₁–y_j and honest path edges otherwise — and its new endpoint is **y_{j−1}**. So the map *neighbor ↦ predecessor* sends every neighbor of x into R (for j = 2 the "rotation" is trivial and returns y₁ = x ∈ R). The map is injective — distinct positions, distinct predecessors — so d(x) = |N(x)| ≤ |R|: **every reachable endpoint has degree at most |R|** (P9, the injection version). And here is Pósa's engine turning over: if G satisfied his condition yet |R| = r < n/2, the r vertices of R would all have degree ≤ r — but the condition at k = r permits at most r − 1 vertices of degree ≤ r (§6.4's equivalence). Contradiction: **the rotations must reach at least n/2 endpoints** — Pósa's own 1962 starting count, the road §6.4 did not take (we took Chvátal's). Machine check: all 1990 non-Hamiltonian δ ≥ 2 graphs on six vertices were run through rotation exhaustively — (a) and (b) hold with **zero violations** (|R| minimum 3, mean 4.10); K_{2,4} reaches exactly 3 endpoints, each of degree 2 ≤ 3; the Petersen graph reaches all 10 vertices as endpoints, each of degree 3 ≤ 10, its longest path spanning all 10 vertices.

**A19.** The diagnosis is the whole problem — and the tool is the Prüfer dictionary (L4, Fact 1): vertex 1 is a leaf exactly when its degree is 1, exactly when label 1 is written **0 times**, exactly when the code avoids the letter 1 entirely. Codes of length n − 2 over the alphabet {2, …, n}: **(n − 1)^{n−2}**. Checks: n = 3 gives 2 — and indeed exactly two of the three labeled trees on 3 vertices have 1 as a leaf (in the third, 1 is the middle of the path); n = 4 gives 9, n = 5 gives 64. Machine check: enumerating all labeled trees confirms 9, 64, 625, 7776 trees with vertex 1 as a leaf for n = 4, 5, 6, 7 — exactly (n−1)^{n−2} each time. (Notice what the ◆ hid: a one-line fact about degrees wearing a counting costume.)

**A20.** This is Rédei's theorem. Build the listing by **insertion**: process the players one at a time, always maintaining a directed Hamilton path of those processed. To insert a new player x: if x beat the first vertex, prepend x; if the last vertex beat x, append x. Otherwise walk down the current path and let i be the *last* position whose player beat x — then x beat every player after position i (every pair played, so "did not lose to" means "beat"), in particular the one at i + 1. Splice x between positions i and i + 1: still a directed path, one vertex longer. Induction finishes: **every tournament has a directed Hamilton path**. Machine check: all 2⁶ = 64 tournaments on 4 players and all 2¹⁰ = 1024 on 5 players were enumerated and every single one contains a directed Hamilton path — zero failures (a detector, not a proof; the insertion argument is the proof). Note the contrast with Lecture 5.3: Hamilton *cycles* are brutally hard; Hamilton *paths* in tournaments are free — the tournament's completeness is exactly the lubricant the insertion needs.

**A21.** Two tools fused: count the missing edges (P2), then invoke Ore (L6.2). For any *non-adjacent* pair u, v: the edges live among the other n − 2 vertices (at most C(n−2, 2) of them), at u (exactly d(u)), and at v (exactly d(v)) — and none between u and v. So m ≤ C(n−2, 2) + d(u) + d(v), which rearranges to d(u) + d(v) ≥ m − C(n−2, 2) ≥ [C(n−1, 2) + 2] − C(n−2, 2) = (n − 2) + 2 = **n**. Every non-adjacent pair satisfies Ore's condition — Ore's theorem hands over the Hamilton cycle. And the bound is honest: K_{n−1} with one pendant vertex carries C(n−1, 2) + 1 edges and no Hamilton cycle (the leaf again, A11). Machine check: on 5 vertices all 56 graphs with m ≥ 8 are Hamiltonian; on 6 vertices all 576 graphs with m ≥ 12 are Hamiltonian, while at m = 11 exactly 30 graphs (the pendant-clique witness among them) still refuse a tour — the "+2" is exactly one edge more than the last failure.

**A22.** Both inequalities are constructive — the theorem is a *good* characterization in miniature. **(χ is at most the minimum.)** Fix any orientation D of G, and let ℓ(D) be the number of vertices on its longest directed path. The tempting proof fails, and it is worth watching it fail before repairing it. Color each vertex v by f(v) = the number of vertices on the longest directed path of D ending at v, and hope that an arc u → v forces f(v) ≥ f(u) + 1. On the directed triangle a → b → c → a this collapses: every vertex ends a directed path through all three vertices, so f(a) = f(b) = f(c) = 3 — adjacent vertices share a color, not a proper coloring at all. The flaw: in an orientation with directed cycles, the longest path ending at u may already pass through v, so extending it by u → v repeats a vertex. Cycles must be handled, not ignored. Throw arcs away until they cannot hurt: let H be an inclusion-maximal spanning acyclic subdigraph of D — keep every vertex, offer the arcs of D one at a time, and skip an arc whenever it would close a directed cycle in what has been built so far. (H is genuinely maximal: an arc skipped at its turn already had its blocking cycle among the arcs present then, and H only grows.) Now color each vertex v by f(v) = the number of vertices on the longest directed path **of H** ending at v, and audit every arc u → v of D — two cases, both strict. **If u → v belongs to H:** a longest H-path ending at u cannot visit v — if it did, its v → ⋯ → u segment followed by the arc u → v would close a directed walk, and every closed directed walk hides a directed cycle, which H cannot have. So appending u → v repeats nothing: f(v) ≥ f(u) + 1 > f(u). **If u → v does not belong to H:** maximality means H already holds a directed path P from v to u — otherwise adding the arc could not have closed a cycle when it was skipped. A longest H-path Q ending at v meets P only at v: any other shared vertex w would splice Q's w → ⋯ → v segment into P's v → ⋯ → w segment, closing a directed walk — a cycle in H, impossible again. So Q followed by P is a genuine directed path ending at u, and it is longer than Q: f(u) > f(v). Either way f(u) ≠ f(v), and every edge of G carries an arc of D one way or the other, so adjacent vertices always get different colors: f is a proper coloring, with values from 1 up to the longest H-path — a path of D — so at most ℓ(D) colors are used. Hence **χ(G) ≤ ℓ(D)** for *every* orientation, so χ(G) is at most the minimum. (On the directed triangle, H keeps two of the three arcs and the colors come out 1, 2, 3 — proper, using exactly ℓ(D) = 3 colors.) **(The minimum is at most χ.)** Take a proper coloring with χ color classes, numbered 1, …, χ, and orient every edge from its lower class to its higher. Along any directed path the class numbers strictly increase, so the path visits at most one vertex per class: at most χ vertices, i.e. ℓ ≤ χ for this orientation — the minimum over orientations is ≤ χ. The two inequalities meet: **χ(G) equals the minimum, over all orientations of G, of the number of vertices on the longest directed path** (Gallai–Hasse–Roy–Vitaver). Notice the family resemblance to Lecture 7: the coloring orientation certifies "some orientation has no long path" exactly the way a cross-cut certifies "few paths suffice" — both directions build the witness, which is what makes the characterization good. Machine check: on all 64 graphs on 4 vertices and all 1024 on 5 vertices, χ equals the orientation-minimized longest directed path — **zero disagreements**; and the repaired coloring itself was audited on every digraph — all 4096 on 4 vertices (proper at every arc, both case directions strict, never more than ℓ(D) colors) and all 1,048,576 on 5 vertices (proper, strict, zero violations).

**A23.** (a) P7 in one line: the degree sum would be 7 · 3 = 21, but every handshake counts twice, so the sum must be even — 21 is not. (b) K_{3,3}: six vertices, every degree 3, nk = 18 even ✓. (c) Necessity is P7 again (nk = 2m even) plus the trivial k < n. Sufficiency is a construction (P11): place 0, 1, …, n−1 on a circle. If k is even, connect each vertex to the k/2 nearest neighbors on each side. If k is odd, first do k−1 that way (even), then connect each vertex to the one diametrically opposite — a *perfect matching* on the circle, which is exactly why k odd forces n even; and that is the same parity debt as nk even: k odd and nk even already forced n even. Every vertex gains exactly k neighbors, and the two constructions never duplicate an edge. Machine check: the circulant recipe was built and audited for every n ≤ 10 and every k < n with nk even — every one regular, every nk-odd case refused ✓ (and 7·3 = 21 odd is case (a) again).

**A24.** Lecture 4.4's dictionary: a vertex is a leaf exactly when it appears *zero* times in the Prüfer code. So "every vertex of S is a leaf" means the code is a sequence of n−2 draws from the alphabet {1,…,n} with the s letters of S *forbidden* — and the count is **(n−s)^{n−2}**, the dictionary's answer with a shrunken alphabet (P1). Sanity rungs: s = 1 recovers the ◆19 exercise's (n−1)^{n−2} (all trees with vertex 1 a leaf — a star of rungs under the dictionary); s = n−1 gives 1^{n−2} = 1, the single star centered at the one survivor; s = n gives 0 — a one-vertex "tree" on n ≥ 3 vertices is a rumor. Machine check: for n = 4, 5, 6 and every s, the brute Prüfer census over all n^{n−2} labeled trees matches (n−s)^{n−2} exactly ✓.

**A25.** Take a longest path v₀v₁…v_d (P8 — Lecture 2.1's reflex; its length d is the tree's diameter). Every vertex's eccentricity is at least ⌈d/2⌉ — from any vertex, one of the two path endpoints is at least half the path away, and outside vertices only make distances longer. And the middle vertex (d even) or middle pair (d odd) achieves eccentricity exactly ⌈d/2⌉: its farthest vertex lies on the path (if some off-path branch went farther, the branch could be spliced into the path to make it *longer*, contradicting maximality — the extremal reflex again). So the center is the path's middle: one vertex if d is even, the adjacent pair v_{d/2 − 1}v_{d/2} if d is odd. The peeling view (P18): repeatedly remove all current leaves; eccentricities all drop by 1 together, so the minimum chases inward at the same rate from both ends — the walk stops at the path's middle and cannot pass it. Machine check: over all 18,248 labeled trees on n = 2..7 vertices, every center has size 1 or 2 and every two-center pair is adjacent — zero exceptions ✓ (8,833 of the trees had two centers).

**A26.** Pad, bill Dirac, remove the guest (P15 in its "change the object" costume). Add a new vertex x adjacent to everything: the padded graph has n+1 vertices, and every old vertex now has degree ≥ δ+1 ≥ (n−1)/2 + 1 = (n+1)/2, while d(x) = n ≥ (n+1)/2. So Dirac applies on the (n+1)-vertex graph and hands over a Hamilton *cycle*; delete x from that cycle and its two neighbors become the ends of a Hamilton *path* through all n original vertices. ∎ For odd n this is genuinely more than Dirac: δ = (n−1)/2 is half a notch below his threshold (integer arithmetic: for n = 7, δ = 3 < 3.5), and the machine census agrees — of the 2,126 graphs on n ≤ 6 with δ ≥ (n−1)/2, 230 sit below Dirac's threshold and every one still has a Hamilton path ✓. The bound is honest (P11 in reverse): for n = 7 take K₄ ∪ K₃ (δ = 2 = (n−3)/2, no Hamilton path — disconnected), and for n = 6 take K₃ ∪ K₃ (δ = 2, refused again ✓).

**A27.** The dictionary first (P1): the leaf set is exactly L when the Prüfer code uses *only* the letters outside L *and* every letter outside L appears — every vertex outside L must have degree ≥ 2, i.e. Prüfer count ≥ 1; every vertex of L must have count 0. So: codes of length n−2 over an alphabet of n−k letters, **surjective** onto that alphabet. The zigzag (P3) counts the surjective ones: **Σ_{j=0}^{n−k} (−1)^j · C(n−k, j) · (n−k−j)^{n−2}**. Sanity rungs: k = n−1 gives the single star centered at the one non-leaf — and the formula returns (1)^{n−2} − 0 = 1 ✓; k = 1 gives Σ (−1)^j C(n−1,j)(n−1−j)^{n−2}, the number of surjections from n−2 objects onto n−1 boxes — zero, as it must be: a tree has at least two leaves ✓ (the formula knows Theorem before you do). Machine check: for n = 4..7 and every k, C(n,k) times the formula equals the brute-census count of trees with a size-k leaf set — all 18 (n,k) pairs agree exactly ✓. Exercise 24 is the k-free version of this story; together they are the dictionary's two hardest shifts, and both were repairable with tools you already owned.

---

## Revision History & Verification Notes

**Editions.** Reference edition → Feynman lecture edition (6 lectures, Dirac and Ore added, two verified labs) → exercise retrofit: the seven original exercises preserved and graded, seven new exercises added, and the full Atlas standard installed — ●○○/●●○/●●● tiers with hints, worked answers, ◆ pattern-unknown problems, ◐ Explorations, and this appendix in place of inline history → session-23 pass (Joyal's bijection completed in §4.5; four vector figures installed) → backlog pass (session 24, this edition): Lecture 7 (Gallai–Milgram) and §6.4 (Pósa, Chvátal, the closure) added with complete proofs, five exercises added (12–14, 18, 22), the set renumbered 1–22, and lab Parts 3–4 installed → second-review audit (session 25, this edition): the A22 proof repaired and the Lab Part 4 example corrected — error fixes only, the freeze holds → graded backfill (session 41, this edition): exercises 23–27 (regularity-by-parity, forced Prüfer leaves, the tree center, Hamilton paths at δ ≥ (n−1)/2, the exact leaf set) + answers A23–A27, every number machine-verified before installation — a user-directed exception, recorded here and in the Standing decisions.

**Corrections during the retrofit.** The original tree-distance exercise stated that the star *maximizes* the total pairwise distance. Machine enumeration showed the reverse — over all 125 trees on 5 vertices the star's total (16) is the *minimum* and the path's (20) the maximum — and the exercise now states both extremes correctly. The other six original exercises are preserved with their content intact, regilded with tiers and renumbered.

**First external review (audited session 22; every claim machine-verified before acting).** Four genuine fixes: (1) **A16's centroid census overstated** — "two centroids happen exactly when n is even" is false (even n is necessary, not sufficient; the star K_{1,3} on 4 vertices has a unique centroid while n is even). Replaced with the exact rule: two centroids iff some edge halves the tree at n/2 + n/2 — verified across all 18,244 labeled trees on n = 4..7 (even-n breakdown: 4/12 on n = 4, 486/810 on n = 6). (2) **A15's ceiling induction had wrong terms** — the closing line used (N−1)(N−2)/2 + (N−1), which never equals the claimed (n³−n)/6 (at N = 4 it gives 16, not 20); corrected to N(N−1)/2 + N (the sub-lemma over T′'s N vertices plus the leaf's +1 to each survivor). The theorem and its full census were already machine-verified and unchanged. (3) **Ore's proof borrowed §6.1's connectivity**, which leans on δ ≥ n/2 — Ore does not imply it. Repaired with the component-size contradiction: non-adjacent u, v in components of sizes a, b give d(u) + d(v) ≤ a + b − 2 ≤ n − 2 < n. Brute-force confirmation: on all 32768 six-vertex graphs, 1978 satisfy Ore's condition, all 1978 are Hamiltonian, and none of the 6064 disconnected graphs satisfies it. (4) **The Lecture-6 introduction claimed neighborhood intersection for all pairs** — false for adjacent pairs (in K_{3,3}, two adjacent cross-side vertices have disjoint neighborhoods of size n/2 each, machine-checked); the argument now addresses strangers explicitly, with the n − 2 pigeonhole visible. Two clarifications: A6 now says *unrooted* full binary tree (a rooted one has a degree-2 root and gives L = I + 1, not I + 2); §6.3 gains the odd-n sharpness witness K_{k,k+1} (connected, δ = ⌊n/2⌋, no Hamilton cycle; k = 1, 2, 3 brute-forced, the alternation argument covers the rest), and the Notation line now states the finite/undirected/simple convention. **The reviewer's computational audit of the printed web-edition PDF matched every recorded count** (1858/1858, 576/576, 30 at m = 11, 1990 at δ = 2), and both labs passed the full extract-compile-run test from the printed PDF — the web edition's first reader-side certification. Pedagogy request (four vector diagrams: longest-path chord, Prüfer deletion, Hierholzer splice, Dirac endpoint chords) recorded as backlog, per the figures-at-rewrite-time convention.

**Second user-directed pass (session 23; both items machine-verified before installation).** (1) **Joyal's bijection completed** — §4.5, previously a flagged sketch, is now a full proof: the cycle-spine construction G (function → doubly-rooted tree), the record-block construction F (doubly-rooted tree → function), the worked n = 5 example, both round-trip arguments, and Cayley recovered as a corollary without Prüfer (the forgetful map (T,a,b) ↦ T is exactly n²-to-1 — the non-circularity). Machine verification, both directions exhaustive: all 4⁴ = 256 functions on {1,…,4} and all 5⁵ = 3125 on {1,…,5} survive f → G → F → f; all 256 (n = 4) and 3125 (n = 5) doubly-rooted trees survive (T,a,b) → F → G → (T,a,b); zero failures either way. Spot checks recorded: the star K_{1,3} with a = b = center maps to the constant function; the path with roots at opposite ends maps to the identity. (2) **The four reviewer-requested vector figures installed** — Figure 1 (longest-path chord, §2.1), Figure 2 (Prüfer deletion, §4.1), Figure 3 (Hierholzer splice, §5.2), Figure 4 (Dirac endpoint chords, §6.1) — a one-time user-directed figure pass, the recorded exception to the freeze (session-14 precedent). No lecture text other than §4.5 was altered; the web edition was rebuilt and re-verified byte-exact.

**Backlog pass (session 24; the recorded Ch. 2 backlog, closed on user instruction — session-23 precedent; every claim machine-verified before installation).** (1) **Pósa's theorem completed** — §6.4, by Chvátal's route: the Bondy–Chvátal closure lemma (§6.1's S∩T engine run on a Hamilton path), the sorted-degrees-climb lemma, **Chvátal's theorem in full** (the saturated closure, the maximum-degree-sum non-adjacent pair, both disjuncts dying at index k = d(u), the k = 0 case handled by the isolated-vertex observation), and Pósa's theorem as the first-arm corollary, with Dirac a further corollary. The condition is stated as **d_k ≥ k+1 for every k < n/2** — the range's boundary was checked against a tempting weaker form (k < (n−1)/2) and refused: K_{3,4} (n = 7) satisfies the weaker range and has no Hamilton cycle, dying exactly at k = 3 = ⌊n/2⌋; the honest form was confirmed against the literature and by machine. Machine verification before publication: Pósa census n = 4–7 — 10, 86, 5218, **197,726** survivors (all 2,097,152 graphs at n = 7), zero non-Hamiltonian; Chvátal census — 10, 146, 5788, **354,806**, zero non-Hamiltonian; the weak d_k ≥ k — 41, 513, 21,218 survivors of which 31, 295, 11,140 tourless; the closure lemma at n = 6 — 35,520 qualifying (G, u, v) triples, zero Hamiltonicity flips; the strictness chain 1858 ⊂ 5218 ⊂ 5788 with 3,360 Pósa-not-Dirac and 570 Chvátal-not-Pósa graphs (all 570 Hamiltonian; degree sequence (2,2,2,4,4,4) among the witnesses); all 1080 realizations of (2,3,3,3,3,4) Hamiltonian (A12's witness family). (2) **Gallai–Milgram completed** — Lecture 7, Diestel's end-minimal induction in full (end-minimal covers, deletion of the end v₁, the red/blue/singleton reinsertion audit — every route shrinks the end-set again), the cross-cut form, the partition form, the n/α length bound, Dilworth as the transitive special case, and Figure 5. Machine verification: all 4096 digraphs on 4 vertices and all 1,048,576 on 5 vertices — minimum path cover ≤ α, zero violations; all **77,824** path covers at n = 4 enumerated, the **15,325** end-minimal covers among them isolated, every one admitting an independent cross-cut — zero failures, exactly as the induction promises; the disjoint-arrows equality (cover = α = 2 at n = 4, = 3 at n = 6); Rédei: all 64 + 1024 tournaments covered by a single path. (3) **Five exercises added** — 12 (Pósa vs Dirac), 13 (degree-sequence diagnostics), 14 (Gallai–Milgram workout), 18 (Pósa's rotation lemma, ●●●), 22 (Gallai–Hasse–Roy–Vitaver, ◆) — and the set renumbered 1–22 (old 12–14 → 15–17, old 15–17 → 19–21; the answers move with their content, and the session-22 review references above follow: A16's, A15's). The rotation lemma was verified on all 1990 non-Hamiltonian δ ≥ 2 graphs on 6 vertices: (a) and (b) hold with zero violations, |R| minimum 3, mean 4.10 (K_{2,4}: 3 endpoints; Petersen: all 10, longest path spanning 10); GHRV was verified on all 64 + 1024 graphs with n ≤ 5, zero disagreements. (4) **Lab Parts 3–4 added** (the two censuses, portable Python, verified outputs recorded). Lecture text of Lectures 1–6 otherwise untouched; the web edition was rebuilt and re-verified byte-exact.

**Second external review (audited session 25; every claim machine-verified before acting).** The reviewer examined the post-backlog edition and confirmed all session-22 corrections in place; independently re-extracted and re-executed the embedded labs, matching every recorded count (Pósa 10, 86, 5218; Chvátal 10, 146, 5788; the weak condition 41, 513, 21,218); found no error in Joyal's bijection, the Pósa/Chvátal section, or Gallai–Milgram; and recommended no further mathematical expansion — the next value is learner testing, not more theorems. Two defects claimed; both verified genuine; both fixed. (1) **A22's first inequality had an invalid step.** The old proof colored v by the longest directed path of D ending at v and asserted that an arc u → v forces f(v) > f(u) — false on cyclic orientations: on the directed triangle every vertex ends a path through all three vertices, f ≡ 3, an improper coloring (machine-confirmed; the extension can repeat a vertex). The proof is replaced in A22: color by a longest path in an inclusion-maximal spanning acyclic subdigraph H, with the two strict cases (arc in H: appending repeats nothing, since the repeat would close a directed walk, hence a cycle; arc omitted by maximality: H's path from v to u splices onto any longest path ending at v, meeting it only at v — again a cycle would close). Exhaustive audit of the repaired coloring on every digraph: all 4096 on 4 vertices — proper at every arc, both case directions strict, never more than ℓ(D) colors — and all 1,048,576 on 5 vertices — proper, strict, zero violations. The theorem statement and its 64 + 1024-graph agreement census were already sound; only the proof was invalid. (2) **Lab Part 4's printed disjoint-arrows check used the wrong masks.** `[0b0010, 0b0001, 0, 0]` encodes 0 ⇄ 1 plus two isolated vertices — minimum cover 3, not 2 (machine-confirmed); the corrected input `[0b0010, 0, 0b1000, 0]` (arrows 0 → 1 and 2 → 3) gives cover 2 = α, now matching the prose it was printed to witness. And the DP table was mislabeled: it stores the *starting* vertices of spanning paths (for the single arc 0 → 1 the table records vertex 0), so `hpend` is renamed `hstart`; the n = 4 census re-ran under the renamed code unchanged — all 4096 digraphs, min cover ≤ α, zero violations. No other change to the chapter; the web edition was rebuilt and re-verified byte-exact. A follow-up fix caught by the user in the same session: **the A22 converse heading mislabeled the direction** — "The minimum is at least χ" restates the first direction's conclusion (χ ≤ min, already proved), while the argument below establishes the opposite, min ℓ(D) ≤ χ; corrected to "**The minimum is at most χ**" (the proof text was always right; only the heading was wrong). The direction was machine-checked directly: the coloring orientation's longest directed path has at most χ vertices on all 64 graphs on 4 vertices and all 1024 on 5, zero violations. The web edition was rebuilt and re-verified byte-exact again.

**Verification record.** The two computational labs stand as previously recorded: Prüfer round-trips (40/40 random sequences; all 16 codes on 4 vertices decode to distinct trees) and the Dirac exhaustion (all 32768 graphs on 6 vertices; 1858/1858 Dirac graphs Hamiltonian; 1990 non-Hamiltonian witnesses at δ = 2; Petersen and K_{2,4} confirmed). The retrofit's own answers were machine-verified before publication, all deterministically (exhaustive enumeration, no sampling): the leaf formula holds on all 18,244 labeled trees with n ≤ 7; centroids are 1 or 2 adjacent vertices on every tree with n = 4..7 (exactly one on odd n); the distance bracket (n−1)² ≤ W(T) ≤ (n³−n)/6 holds on every tree with n = 4..7, the floor attained only by stars and the ceiling only by paths; vertex-1-leaf counts equal (n−1)^{n−2} for n = 4..7 (9, 64, 625, 7776); degree-sequence counting confirms 360 paths, 6 stars, and 24 trees with leaves {1, 2} on 6 labels (and 5 + 60 + 60 = 125 on 5 labels); on all 1024 five-vertex graphs, bipartiteness agrees with odd-cycle-freeness, all 291 forests satisfy m = n − k, and all 638 graphs with m ≥ 5 contain a cycle; on all 32768 six-vertex graphs, every δ ≥ 3 graph is connected and every graph with m ≥ 12 is Hamiltonian (576/576), with 30 non-Hamiltonian stragglers at m = 11; Rédei holds on all 64 + 1024 tournaments with n ≤ 5; the hypercube checks ran to n = 5 (edge counts 1, 4, 12, 32, 80; Euler tours exactly when n even; inductive Gray-code Hamilton cycles verified at lengths 4, 8, 16, 32); the directed in = out decomposition was run live on a 9-edge digraph and split into three edge-disjoint directed cycles covering every edge once. The session-24 additions carry their own record (see the backlog-pass paragraph): the Pósa/Chvátal/closure censuses to n = 7, the Gallai–Milgram exhaustion to n = 5 with the 77,824-cover cross-cut audit, the rotation lemma's 1990-graph check, and the GHRV agreement on all 1136 graphs with n ≤ 5.

**Standing decisions.** The lecture text is unchanged by the retrofit; after the first external review (session 22), changes are error fixes only — the session-23 Joyal/figure pass and the session-24 backlog pass (Lecture 7, §6.4, exercises 12–14/18/22, lab Parts 3–4) are the recorded user-directed exceptions, not silent edits. New chapters inherit the full standard from the start. Backlog: **none** — Gallai–Milgram (Lecture 7) and Pósa's theorem (§6.4) are both complete and verified. (Joyal's bijection is complete, §4.5; the four requested vector figures are installed.) The session-25 reviewer's recommendation — no further mathematical expansion; learner testing next — is recorded in the Atlas as project direction, not a chapter change. **Session 41, at user direction, lifted the per-chapter freeze posture for the graded backfill (exercises 23–27 + A23–A27, the chapter's first post-review expansion); learner testing itself now runs at the end of the whole project scope.** The backfill's verification: the circulant construction was built and audited for all n ≤ 10, k < n with nk even (every case regular, every nk-odd case refused); (n−s)^{n−2} verified against the brute Prüfer census for n = 4..6, all s; the center census over all 18,248 labeled trees with n = 2..7 (every center of size 1 or 2, two-centers always adjacent — 8,833 two-center trees); the Hamilton-path census over all 2,126 graphs with n ≤ 6 and δ ≥ (n−1)/2 (all Hamiltonian-pathed, 230 of them below Dirac's threshold) with the honest witnesses K₄ ∪ K₃ and K₃ ∪ K₃; the exact-leaf-set formula verified against the brute census for all 18 (n,k) pairs with n = 4..7.

---
*Chapter status: ✅ **Feynman edition + full exercise standard + backlog closed + graded backfill (session 41)** — 7 lectures; Trick Bag of 8 patterns + 3 lore moves; verified lab, 4 parts; 23 graded exercises + 4 ◆ pattern-unknown + 2 ◐ explorations, 27 worked answers machine-verified; Pósa and Chvátal complete (§6.4, censuses verified to n = 7); Gallai–Milgram complete (Lecture 7, exhaustion verified to n = 5); Joyal's bijection complete (§4.5, both round trips machine-verified n = 4, 5); five vector figures. Two external reviews audited (sessions 22 and 25): six error fixes + two clarifications in all, every claim machine-verified first; both reviews' independent lab audits matched all recorded counts. **Lecture text frozen: error fixes only; the exercise set's session-41 backfill (23–27 + A23–A27) is the recorded user-directed exception.** Backlog: none.*
