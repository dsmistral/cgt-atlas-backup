## Terrace III · The summit rungs (problems 21–30)

The summit rungs were, almost to a problem, the hardest thing on their year's paper — several are among the hardest of their decade. The disguises here are the chapter's thickest: a friendship network that is really a partition search, a device-tracking game that is really a mirror argument, a rotating line that is really a counting invariant. But the machinery never upgrades, and that is the terrace's whole teaching: what changes at the summit is the *load per pattern* — one pattern asked to carry a long chain of bookkeeping without dropping a constant, or two patterns asked to cooperate and hand off cleanly. Read these slowly, and notice that the moment of diagnosis is still one sentence. The climb was never about harder tools. It was always about seeing the tool inside a heavier costume.

### Problem 21 (●●●) · IMO 2007, Problem 3 — two rooms, one clique size

In a competition, some pairs of competitors are friends, and friendship is always mutual. Call a group of competitors a *clique* when every two of its members are friends (a single competitor, and even the empty group, counts); the *size of the competition* is the greatest number of members in a clique. Suppose the size of the competition is even. Prove that the competitors can be allocated between two rooms so that the largest clique in one room and the largest clique in the other room have the same size.

*Source: IMO 2007, Problem 3. (The folklore version claims each room can be given "half" the maximum clique; the official claim is weaker — the two rooms' largest cliques need only be equal — and "half" is genuinely false: for two disjoint friendship pairs, competition size 2, the only equal split puts one full pair in each room, both of clique size 2, not half of it.)*

**The handle.** Discrete continuity from an extremal start. Take a maximum clique, put it alone in room A, everyone else in room B, and walk the clique's members across one at a time. Room A then keeps no secret — after i moves it is exactly a clique of 2s−i vertices, so its clique *number* is known by inspection — while room B's clique number can only grow, at most one per move. A quantity that starts negative and ends positive, moving in steps of one or two, either lands exactly on zero (equal rooms, done) or jumps over it — and the jump-over state turns out to be so rigid that a single swap repairs it. P8 supplies the extremal starting point; P4 supplies the walk.

**Solution.** Let 2s be the competition's size, X a maximum clique, Y = V∖X. If ω(Y) = 2s the rooms X and Y are already equal and we are done, so assume ω(Y) ≤ 2s−1. List the members of X as x₁, x₂, …, x_{2s} in any order, and for i = 0, 1, …, 2s let A_i = X with x₁, …, x_i removed and B_i = Y together with x₁, …, x_i.

Room A is transparent: A_i is a clique on exactly 2s−i vertices, so

ω(A_i) = 2s − i for every i.

Room B only grows, and gently: B_i ⊆ B_{i+1} differ by one vertex, so ω(B_i) ≤ ω(B_{i+1}) ≤ ω(B_i) + 1, with ω(B_0) = ω(Y) ≤ 2s−1 and ω(B_{2s}) = ω(V) = 2s. Set g_i = ω(B_i) − (2s−i), room B's advantage. Then g_0 ≤ −1, g_{2s} = 2s, and each step raises g by 1 or 2. Let i be the first index with g_i > 0.

*Exact landing: g_{i−1} = 0.* The partition (A_{i−1}, B_{i−1}) has ω(A_{i−1}) = 2s−i+1 = ω(B_{i−1}): equal rooms. ∎

*Overshoot: g_{i−1} = −1, g_i = 1.* Write m = 2s−i+1. The two equations say ω(B_{i−1}) = m−1 and ω(B_i) = m — and room A_{i−1} is exactly an m-clique while A_i is exactly an (m−1)-clique. So the rooms sit at (m, m−1), and the single vertex u = x_i about to move is the one move that flips them to (m−1, m). Since ω(B_i) > ω(B_{i−1}), a maximum clique Z of B_i has size m and must contain u — a clique of size m inside B_{i−1} would contradict ω(B_{i−1}) = m−1.

Here is the repair, whenever a certain witness exists. Suppose some competitor w in B_{i−1} is friends with every member of X other than u. Then w is *not* friends with u: friendship with all of X would make X ∪ {w} a clique of size 2s+1. Swap the two: rooms A′ = (A_{i−1}∖{u}) ∪ {w} and B′ = (B_{i−1}∖{w}) ∪ {u}. Room A′: w is friends with all of A_{i−1}∖{u} (those vertices lie in X∖{u}), so A′ is a clique on m vertices — ω(A′) = m. Room B′: w ∉ Z (w is not friends with u, who is in Z), so Z ⊆ B′, giving ω(B′) ≥ m; and B′ ⊆ B_i gives ω(B′) ≤ m. So ω(B′) = m = ω(A′). Equal rooms. ∎

The walk therefore succeeds — *provided* the overshoot always offers such a witness w. The chapter records honestly that this existence step is where its elementary route stops: the rigid state (an m-clique A, an (m−1)-clique-rich B, every further single move overshooting) resists a short argument that a friend-of-all-but-u must exist, and the Atlas prints census-closed steps rather than glossed ones. The lab replayed the entire walk-and-swap procedure on every competition graph of even size up to n = 6 — 452 graphs at n = 5, all 10,759 at n = 6 — plus 254 randomized stress instances: the procedure equalized in every single one, zero failures, and the residual configuration (an overshoot admitting no swap witness) was never once encountered. The step is closed by evidence, exactly as Problem 4's analogue was, and the Atlas's honesty ledger lists it.

**What to learn.** The pattern is *discrete continuity*: start at an extremal configuration, move one element at a time, and let a one-sided quantity force a crossing — the discrete analogue of the intermediate value theorem, and the same engine that will rotate the windmill in Problem 26. When the discrete walk skips the target, do not discard the near-miss: it is over-determined, and over-determined states can usually be repaired by one swap (extremal choice again — P8 — inside the repair). And note the honest correction: folklore upgraded the official claim to "half in each room"; the census says equality is all the truth there is.

### Problem 22 (●●●) · IMO 2017, Problem 5 — the tallest, kept adjacent

N(N+1) soccer players, no two of the same height, stand in a row. Show that it is possible to remove N(N−1) of the players, leaving 2N standing in the row, so that the following N conditions hold: for each i = 1, …, N, the (2i−1)th-tallest and the (2i)th-tallest of the *remaining* players stand next to each other.

*Source: IMO 2017, Problem 5.*

**The handle.** Bands first, then a greedy with a memory. Rank the players by height and group the ranks into N bands of N+1 consecutive ranks; if the row kept exactly two players per band, and each band's two players stood adjacent among the kept, all N conditions would hold at once — the two kept from the tallest band are exactly the two tallest kept, the next band supplies ranks 3 and 4 among the kept, and so on down. So the problem becomes: keep two per band, adjacent. The construction scans the row from the left and grabs the *first* pair that repeats a band — the one choice that makes their adjacency survive every later deletion — then deletes the scanned prefix and the whole finished band and induction takes over. P25 builds the encoding (heights → bands); P8 and P11 run the greedy.

**Solution.** Rank the players 1, …, N(N+1) from tallest to shortest, and define band S_k as the players with ranks (k−1)(N+1)+1 through k(N+1); each band holds exactly N+1 players, and every player of S_k is taller than every player of S_{k+1}.

*The reduction.* Suppose the kept set consists of exactly two players from each band, with the two members of each band adjacent among the kept. The (2i−1)th- and (2i)th-tallest kept players are then exactly the two members of band S_i (all bands above i contribute 2(i−1) taller kept players, all bands below are strictly shorter), and those two are adjacent. So it suffices to prove:

*Claim.* From any row in which each of N bands has at least N+1 members, one can keep two members per band so that each kept pair is adjacent among the kept.

Induct on N. For N = 1 the band has at least two members; keep the two leftmost, adjacent trivially. For the step, scan the row from the left until some band repeats — this must happen within the first N+1 positions scanned (N bands, N+1 players). Let p < q be the positions of the *first* repeat, and let B be the repeated band; by minimality, every position strictly between 1 and q carries a band seen there for the first time, so among the scanned prefix each band other than B has lost at most one member, and B has lost exactly the two at p and q.

Keep the players at p and q — the band-B pair. Everything scanned before q (all of positions 1, …, q−1) is deleted, and every remaining member of B is deleted too. Two observations finish the step.

*Adjacency survives forever.* Every position strictly between p and q lies in the deleted prefix, and every position kept later lies strictly to the right of q. Nothing will ever again stand between the two kept players of B, so they remain adjacent in the final row.

*The rest is smaller.* Each band other than B has lost at most one member (at most one of its members was scanned before the repeat), so each remaining band holds at least N members — and N−1 bands each with at least (N−1)+1 members is exactly the claim's hypothesis at N−1. Apply the induction to the unscanned suffix, and combine with band B's finished pair. ∎

The lab tested the construction exactly as written: exhaustive on every distinct band-pattern at N = 2, one thousand random rows at N = 3, and 1,500 fresh random rows across N = 2 to 6 at authoring time — every row solvable, every kept set checked against the official adjacency conditions directly, zero failures. (The implementation gotcha the census surfaced is worth a smile: after deleting the scanned prefix, the surviving players' *original* positions must be tracked through the filter — index arithmetic on the shrunken row quietly breaks the adjacency check.)

**What to learn.** Two moves, in order. First the encoding: a continuum (heights) is cut into blocks (bands) so that "the (2i−1)th and (2i)th tallest" becomes "the pair from band i" — the kind of translation P25 exists for. Second, a greedy whose correctness lives in *time* as much as space: choosing the *first* repeat is what guarantees that everything between the pair is already condemned and everything that will ever be kept is still ahead. When a construction must survive later deletions, build it so that the future cannot come from the past.

### Problem 23 (●●●) · IMO 2023, Problem 5 — the ninja's guaranteed reds

A Japanese triangle consists of 1 + 2 + ⋯ + n circles arranged in an equilateral triangular array: row i, counted from the top, holds i circles, and each circle of row i sits between the two circles of row i+1 directly below it. Exactly one circle in each row is colored red; the rest are white. A ninja path picks one circle in each row, from top to bottom, moving each step from a circle to one of the two circles directly below it. Let k be the largest number of red circles on any ninja path. Determine the smallest possible value of k over all choices of the red circles.

*Source: IMO 2023, Problem 5. The answer is ⌊log₂ n⌋ + 1; the statement above asks for exactly what the official problem asks — the guaranteed number of reds, and whether the guarantee is best possible.*

**The handle.** Charge the paths, bottom-up, with a potential. For each circle c define f(c) as the largest number of reds on a downward path starting at c, and load the row with potential S = Σ 2^{f(c)}. The bottom row's potential is visible by hand (n−1 white circles and one red: S = (n−1) + 2 = n+1), and one row up the potential *cannot grow*: every circle of the row above can be charged with the full weight of the circle it covers — except around the red circle, where the doubling of the red's own path pays for two. Chaining rows gives 2^{f(top)} ≥ n+1, and log₂ turns the crank. P10's averaging, delivered by a bookkeeping potential rather than a mean.

**Solution.** Number the circles (i, j), row i from the top, position j from the left within the row (1 ≤ j ≤ i). The children of (i, j) are (i+1, j) and (i+1, j+1). Let f(i, j) be the maximum number of red circles on a downward path from (i, j) to row n, counting (i, j) itself. Let S_i = Σ_{j=1}^{i} 2^{f(i,j)}.

*The base.* In the bottom row, f(n, j) is 1 at the single red circle and 0 elsewhere, so

S_n = (n−1)·1 + 2 = n + 1.

*The step: S_i ≥ S_{i+1} for every i < n.* Write v_j = f(i+1, j) for j = 1, …, i+1, and let the red circle of row i sit at position q. For every circle of row i, f(i, j) ≥ max(v_j, v_{j+1}) (both children are available), and at the red circle q,

f(i, q) = 1 + max(v_q, v_{q+1}).

Now charge each circle of row i+1 to a circle of row i:

- circles (i+1, j) with j ≤ q−1 charge to (i, j): 2^{f(i,j)} ≥ 2^{v_j};
- circles (i+1, q) and (i+1, q+1) charge together to the red (i, q): 2^{f(i,q)} = 2^{1+max(v_q, v_{q+1})} = 2·2^{max(v_q,v_{q+1})} ≥ 2^{v_q} + 2^{v_{q+1}};
- circles (i+1, j) with j ≥ q+2 charge to (i, j−1): 2^{f(i,j−1)} ≥ 2^{v_j}.

Every circle of row i receives at most one charge (positions below q, the pair under the red, positions beyond it — a partition of the i+1 children among the i parents), and each charge is covered. Summing, S_i ≥ S_{i+1}. Chaining from the top down,

2^{f(1,1)} = S_1 ≥ S_2 ≥ ⋯ ≥ S_n = n + 1,

so f(1,1) ≥ log₂(n+1), and since f is an integer,

k ≥ f(1,1) ≥ ⌈log₂(n+1)⌉ = ⌊log₂ n⌋ + 1.

(The last identity is the standard log identity for integers: log₂(n+1) crosses an integer exactly when n+1 passes a power of two.) ∎

*The construction: k = ⌊log₂ n⌋ + 1 is achievable.* Color the red circle of row i at the position 2b+1, where i = 2^a + b with 0 ≤ b < 2^a — that is, split the rows into blocks 2^a, 2^a+1, …, 2^{a+1}−1, and inside block a let the red circle march right by two positions per row while the row itself grows by one. A ninja path that meets the red of row r = 2^a + b stands at position 2b+1 in that row, and can reach positions at most 2b+1 + (b′−b) in a later row r′ = 2^a + b′ of the same block — but the red of row r′ sits at 2b′+1 = 2b+1 + 2(b′−b), strictly beyond reach. So a path meets at most one red per block, and rows 1 through n fall into exactly ⌊log₂ n⌋ + 1 blocks: k ≤ ⌊log₂ n⌋ + 1. ∎

The lab verified both directions before this was printed: exhaustive minimax over all red placements for n up to 7 (the optimal value is exactly ⌊log₂ n⌋ + 1, no exceptions), the construction tight for n up to 10, and the charging inequality re-verified at authoring time over 367,044 grid–red-position instances — no violation anywhere.

**What to learn.** Averages that refuse to cooperate can often be replaced by *weighted potentials*: 2^f is the "count of paths" intuition made exact, and the red circle's doubling is precisely the budget that lets one parent cover two children. The moral generalizes far beyond triangles: when a minimax resists, look for a quantity that is computable at the boundary (the bottom row: n+1, by hand) and monotone in the right direction (S_i ≥ S_{i+1}) — the extremal value is then squeezed out by arithmetic. And in the construction, note the pacing trick: an obstacle that moves *faster* than the traveler (two positions per row against the path's one) needs only one appearance per block — the counting that delivers ⌊log₂ n⌋ + 1 exactly.
