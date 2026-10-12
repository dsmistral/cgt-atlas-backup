---

## Lecture 6 · The Golay Bridge: Codes as Designs

### 6.1 The best single published page

Marcel Golay's 1949 note "Notes on Digital Coding" (Proceedings of the IRE, vol. 37, page 657 — half a column, one table) announced two codes: a binary [23,12,7] and a ternary [11,6,5]. Berlekamp's verdict is the standard quip: it is the best single published page in coding theory. (The ternary code had been printed even earlier — Virtakallio, 1947, in the Finnish football-pool magazine Veikkaaja; priority is recorded.) Both codes are **perfect**: their radius-t error balls tile their cubes exactly, the sphere-packing identity holding with equality — the [7,4,3] Hamming code of Chapter 8 has exactly two nontrivial siblings in the perfect family, and Golay's page contains both. Perfectness here is machine-verified in this chapter's lab, word by word: 729 ternary balls of radius 2 partition F₃¹¹ (729·243 = 177,147 = 3¹¹), and 4,096 binary balls of radius 3 partition F₂²³ (4,096·2,048 = 8,388,608 = 2²³).

### 6.2 The ternary Golay code and the Witt system S(4,5,11)

Take Φ₁₁ = 1 + x + x² + … + x¹⁰, the cyclotomic factor of x¹¹ − 1 over F₃. It splits into two monic quintics, and the lab factors it by machine:

Φ₁₁ = (x⁵ + x⁴ + 2x³ + x² + 2)·(x⁵ + 2x³ + x² + 2x + 2)

(verify the coefficient arithmetic mod 3 — the product is 1 + x + … + x¹⁰ with zero remainder, machine-checked). Either factor generates a cyclic code of length 11, dimension 6, and the machine census prints, for both: **729 codewords, minimum distance 5** — the [11,6,5]₃. The weight distribution (identical for both factors):

A₀ = 1, A₅ = 132, A₆ = 132, A₈ = 330, A₉ = 110, A₁₁ = 24.

Now the bridge: look only at the *supports* of the 132 weight-5 words. Two ternary words can share a support (a sign flip on a coordinate changes the word, not the support), and here the 132 words pair up onto **66 supports**, every 4-subset of the 11 coordinates lying in exactly one of them — the supports form the Steiner system **S(4,5,11)**, the small Witt design. Extend the code by an overall-parity coordinate to [12,6,6]₃ (machine-verified self-dual, weights A = 1, 264, 440, 24 at 0, 6, 9, 12): now the 132 weight-6 supports form **S(5,6,12)** — the large small-Witt design — with automorphism group M₁₂.

### 6.3 The binary Golay code and S(5,8,24)

The binary twin: over F₂, (x²³+1)/(x+1) factors into exactly two monic degree-11 polynomials (machine-found, not remembered):

g₀ = x¹¹ + x⁹ + x⁷ + x⁶ + x⁵ + x + 1, g₁ = x¹¹ + x¹⁰ + x⁶ + x⁵ + x⁴ + x² + 1.

Either generates the **[23,12,7]₂**: 4,096 words, minimum distance 7 — verified by the machine over all 8,386,560 codeword pairs, with the weight distribution

A₀ = 1, A₇ = 253, A₈ = 506, A₁₁ = 1288, A₁₂ = 1288, A₁₅ = 506, A₁₆ = 253.

Extend by parity to the **[24,12,8]₂** — self-dual, and the weight enumerator is the famous five-term line

A₀ = 1, A₈ = 759, A₁₂ = 2576, A₁₆ = 759, A₂₄ = 1.

The 759 weight-8 words — **octads** — are the blocks of S(5,8,24): the lab machine-verifies that each of the C(24,5) = 42,504 five-subsets of coordinates lies in **exactly one** octad. The octad arithmetic that makes the count inevitable is the exercise: every octad carries C(8,5) = 56 of the five-subsets, so 759·56 = 42,504 = C(24,5) — the design's defining property *is* the weight enumerator's arithmetic shadow.

### 6.4 Assmus–Mattson: how a code hands you a design

Why do the weight supports of these codes suddenly satisfy t-design conditions? The Assmus–Mattson theorem (1969) is the machine behind the bridge: for a linear code with few distinct weights and a dual with few weights, the words of any given weight carry a t-design on their supports. The theorem is stated (its proof — an incidence-counting argument via the dual code — is cited, and the chapter does not pretend otherwise); the Golay instances are the classic application, and Assmus–Mattson's own paper mined exactly these: the 5-designs on 12 and 24 points. The general pattern — **words-as-designs** — is the proposed registry entry: pick a code with rigid weight structure, read a design off its supports, and the code's automorphism group acts on the design's block set.

### 6.5 The Mathieu groups, and the chapter in one table

The automorphism group of S(5,8,24) is **M₂₄**, of order

24·23·22·21·20·48 = 244,823,040 = 2¹⁰·3³·5·7·11·23,

machine-multiplied and machine-factored; the point stabilizer is M₂₃ = 10,200,960 (= M₂₄/24), whose point stabilizer is M₂₂ = 443,520, and the octad stabilizer has order |M₂₄|/759 = 322,560 — the ladder the lab prints exactly. The S(5,6,12) system carries M₁₂ = 95,040 (its stabilizer arithmetic: |M₁₂|/132 hexads = 720), point stabilizer M₁₁ = 7,920. M₂₄ and M₁₂ are 5-transitive — M₁₂ sharply so — and by the classification of finite simple groups the Mathieu groups are the *only* 4-transitive permutation groups beyond the symmetric and alternating ones. They are the first five sporadic simple groups ever found (Mathieu, 1861 and 1873), and the honest historical arrow runs backwards: the *designs* were constructed first as abstract systems, and the *codes* — Golay 1949 — gave them their most usable incarnation.

**The consolidation table:**

| Object | The symmetry | The inversion | The design |
|--------|--------------|---------------|-----------|
| Necklaces / cube / trees (L1) | Burnside average over C_n, the 24 rotations, canonical generation | — | — |
| Divisors / subsets / partitions (L2) | — | μ recovers τ, φ, the (−1)^k and (−1)^{n−1}(n−1)! patterns | — |
| Fano / STS(9) / STS(13) (L3) | — | — | b = v(v−1)/6 forced by double counting; Fisher b ≥ v; census 1, 1, 2 |
| PG(2,3) (L3) | 13-point self-dual symmetric design | — | S(2,4,13), Bruck–Ryser's survivors |
| Schoolgirls (L4) | 7 parallel classes of PG(3,2) | — | resolvable STS(15); divisibility gate v ≡ 1,3 (mod 6) → S(3,4,n): n ≡ 2,4 (mod 6) |
| RS / simplex / greedy (L5) | Singleton by puncturing; Plotkin by averaging | — | — |
| Golay ↔ Witt (L6) | Aut groups M₂₄, M₁₂ | — | 66 supports = S(4,5,11); 759 octads = S(5,8,24) |

### 6.6 What to learn

The three threads of the chapter knit into one object: the Golay codes are perfect by *volume* (sphere-packing — Lecture 5's cube geometry), their supports are designs by *counting* (Assmus–Mattson — Lecture 3–4's double counting), and their automorphism groups are symmetry groups (Lecture 1's orbit machines, run at full size). The words-as-designs bridge is the proposed pattern entry, and the Mathieu groups are the proof that the bridge can carry traffic: five sporadic simple groups live at the far end of it.

---

## The Trick Bag (reference card)

| Tool | Statement | Where proved / cited |
|------|-----------|---------------------|
| **Burnside's lemma** | # orbits = (1/\|G\|)·Σ_g \|Fix(g)\| | L1 (proved in full; Cauchy 1845/Frobenius 1887 priority) |
| **Pólya's theorem** | k-coloring orbits = Z_G(k,…,k); Z_G the cycle index | L1 (proved from the fixed-point form; Redfield 1927 priority noted) |
| **Cube cycle index** | (k⁶+3k⁴+12k³+8k²)/24; k = 1..5: 1, 10, 57, 240, 800 | L1 (machine census 1⁶:1, 2²1²:3, 2³:6, 3²:8, 4·1²:6) |
| **Shape generation** | Rooted = multiset closure; unrooted = centroid split; 1,1,1,2,3,6,11,23 | L1 (Prüfer cross-check) |
| **Möbius inversion (classical)** | g = Σ_{d\|n} f(d) ⟹ f(n) = Σ_{d\|n} μ(d)·g(n/d); Σ_{d\|n} μ(d) = [n=1] | L2 (proved) |
| **Poset μ + incidence algebra** | μ ζ = identity under convolution; μ(0̂,1̂) on Π_n = (−1)^{n−1}(n−1)! | L2 (proved; Rota 1964) |
| **Design counting constants** | λ·C(v,t) = b·C(k,t); r = λ(v−1)/(k−1) | L3 (double counting) |
| **STS gate** | STS(v) exists iff v ≡ 1, 3 (mod 6); S(2,3,6) impossible at r = 5/2 | L3 (cited; machine exhibit) |
| **Fisher's inequality** | 2-(v,k,λ) with k < v ⟹ b ≥ v; equality ⟺ symmetric designs | L3 (Ch. 6 proofs cited; census view here) |
| **Bruck–Ryser–Chowla** | q ≡ 1,2 (mod 4) plane ⟹ q a sum of two squares; orders 6, 14 out; 10 out by Lam et al. 1989; 12 open | L3 (cited; arithmetic census) |
| **STS census ladder** | 1 (v=7), 1 (v=9), 2 (v=13, machine-proved), 80 (v=15), 11,084,874,829 (v=19) | L3 (first three machine; the rest cited) |
| **Wilson / Keevash** | PBDs: all but finitely many admissible v; designs for all large admissible n — divisibility the only obstruction | L4 (cited) |
| **Kirkman resolvability** | PG(3,2): 35 lines = STS(15), 56 spreads, 7 disjoint = the schoolgirl schedule | L4 (machine-verified) |
| **SQS ladder** | SQS iff v ≡ 2, 4 (mod 6) (Hanani); unique at 8 (Aut 1344) and 10 (Aut 1440 = PΓL(2,9)); 1,054,163 at 16; S(4,5,v) unique at 11, smallest open 21 | L4 (8/10 machine; rest cited) |
| **Singleton / MDS** | M ≤ q^{n−d+1}; binary MDS trivial; RS over F₅: [4,2,3]₅, [5,2,4]₅; MDS conjecture (Segre 1955), prime case Ball 2012 | L5 (bound proved; census + witnesses machine) |
| **Plotkin bound** | 2d > n ⟹ M ≤ 2⌊d/(2d−n)⌋; tight at (6,4) = 4, (7,4) = 8 simplex | L5 (proved by averaging; witnesses machine) |
| **Gilbert–Varshamov** | A_q(n,d) ≥ q^n/Σ_{j<d} C(n,j)(q−1)^j | L5 (proved; greedy witnesses machine) |
| **Perfect codes** | Hamming [7,4,3]: A = [1,0,0,7,7,0,0,1], 16·8 = 128; ternary [11,6,5]: 729·243 = 3¹¹; binary [23,12,7]: 4096·2048 = 2²³ | L5–L6 (machine; Ch. 8 cross-ref) |
| **Golay ↔ Witt** | 132 w₅ words → 66 supports = S(4,5,11); [12,6,6] → 132 = S(5,6,12); 759 octads = S(5,8,24), each 5-subset in exactly one; Assmus–Mattson 1969 the bridge | L6 (machine) |
| **Mathieu ladder** | M₂₄ = 244,823,040 = 2¹⁰·3³·5·7·11·23; M₂₃ = 10,200,960; M₂₂ = 443,520; M₁₂ = 95,040; M₁₁ = 7,920; 5-transitive M₂₄, M₁₂ | L6 (machine arithmetic; transitivity cited) |

**Formula box:** Burnside |X/G| = (1/|G|)Σ_g |Fix(g)|; Pólya Z_G(x) = (1/|G|)Σ_g ∏_i x_i^{c_i(g)}, cube (k⁶+3k⁴+12k³+8k²)/24, 2-color necklace (1/n)Σ_{k=0}^{n−1} 2^gcd(n,k). Möbius: Σ_{d|n} μ(d) = [n=1]; inversion f(n) = Σ_{d|n} μ(d)g(n/d); poset μ(x,y) = −Σ_{x≤z<y} μ(x,z); Boolean μ(∅,S) = (−1)^{|S|}; partition μ(0̂,1̂) = (−1)^{n−1}(n−1)!. Designs: λC(v,t) = bC(k,t), r = λ(v−1)/(k−1); STS: b = v(v−1)/6, r = (v−1)/2, exists iff v ≡ 1,3 (mod 6); Fisher b ≥ v; projective plane S(2,q+1,q²+q+1), affine S(2,q,q²); BRC: q ≡ 1,2 (mod 4) ⟹ q = a²+b². Codes: Singleton A_q(n,d) ≤ q^{n−d+1}; Plotkin 2d > n ⟹ A_2(n,d) ≤ 2⌊d/(2d−n)⌋, A_2(2d,d) ≤ 4d; GV A_q(n,d) ≥ q^n/Σ_{j=0}^{d−1}C(n,j)(q−1)^j; Hamming ball V(n,t) = Σ_{j≤t} C(n,j); perfect: M·V(n,t) = q^n. Golay: ternary [11,6,5] A = 1,132,132,330,110,24; binary [24,12,8] A = 1,759,2576,759,1; octad arithmetic 759·56 = 42,504 = C(24,5); |M₂₄| = 244,823,040.

---
