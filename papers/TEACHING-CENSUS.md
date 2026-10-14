# Teaching-aids track - the instructional pattern census (Track B)

Added 2026-10-14 (chunk 28, sub-chunk 28b). Charter (SOURCES.md section 5.1, Track B): mine course problem sets and solution notes for pattern usage at the instructional level, using the corpus census method (pattern ID + the decisive move + the honest miss), recorded here as a SEPARATE instructional census - never as paper firings. Census rows never touch the pattern dossiers, INDEX.md, CORPUS.md or NEXT100.md; the teaching track never edits the Atlas. Grading: GENUINE = the problem's designed solution engine is the pattern; PARTIAL = the pattern is a face of the engine or shares the load; CROSS-NOTE = a second pattern's view recorded without a firing; NO P-ID = the engine has no clean Atlas home (a coverage observation at the instructional level, the V9 precedent's teaching-side mirror).

## 1. T2 - MIT OCW 6.042J Mathematics for Computer Science (Spring 2015, Meyer) - census pass 1 (28b)

Source material (register-first, per SOURCES.md 5.1): the problem-set series MIT6_042JS15_ps1 through ps12 (the Lehman-Leighton-Meyer course), officially hosted on MIT's Open Learning Library (openlearninglibrary.mit.edu - MIT's own platform for the course; the sets carry the CC BY-NC-SA 3.0 license line). URLs verified 2026-10-14:

- ps1: https://openlearninglibrary.mit.edu/assets/courseware/v1/432a6320bb11c2bfba8ed2a47e68f86d/asset-v1:OCW+6.042J+2T2019+type@asset+block/MIT6_042JS15_ps1.pdf
- ps2: https://openlearninglibrary.mit.edu/assets/courseware/v1/a56c7e8c4c265baf3549ab786dc1fdc5/asset-v1:OCW+6.042J+2T2019+type@asset+block/MIT6_042JS15_ps2.pdf
- ps3: https://openlearninglibrary.mit.edu/assets/courseware/v1/004582165ee7e142a378192196660420/asset-v1:OCW+6.042J+2T2019+type@asset+block/MIT6_042JS15_ps3.pdf
- ps5: https://openlearninglibrary.mit.edu/assets/courseware/v1/f472b410ecb65c7a0ed180b2a8bbd5cb/asset-v1:OCW+6.042J+2T2019+type@asset+block/MIT6_042JS15_ps5.pdf

Availability honesty: ps4's official URL was NOT pinned at 28b (the search surfaced only third-party copies - excluded per policy); the ps4 census is deferred. The OCW course-calendar "session" PDFs (mit6_042js15_session1 through session8 fetched) were identified as TEXTBOOK-CHAPTER EXCERPTS (the readings: session 1 = Chapters 1.1-1.6, session 2 = 1.7-1.9, session 3 = 2.1-2.3, session 4 = 3.1-3.5, session 5 = 3.6, session 6 = 4.1-4.2, session 7 = 4.3-4.5, session 8 = 5.1-5.3) - reading material, not census material.

### Census rows (13 problems across four sets)

| Set | Problem | Topic (pinned from the set PDF) | Census | Decisive move / honest miss |
|-----|---------|--------------------------------|--------|-----------------------------|
| ps1 | 1 | Prove that log_4 6 is irrational | NO P-ID | proof by contradiction from 4^a = 6^b via unique factorization (2^(2a) = 2^b 3^b) - a number-theory drill, no Atlas home; the WOP-descent engine (the ps1-2 route) is not the designed path |
| ps1 | 2 | Use the Well Ordering Principle to prove n^3 <= 3^n for every nonnegative integer n (verify for n <= 4 by explicit calculation) | P4 PARTIAL | the minimal-counterexample descent - the induction step run in mirror form (the mcs teaches WOP, induction and strong induction as equivalent); the base-case check the honest boundary |
| ps1 | 3 | Validity, satisfiability, consistency of propositional formulas | NO P-ID | propositional-logic drill (truth table; the R-construction) - no Atlas home |
| ps1 | 4 | Parallel half-adders built from add1 modules (the carry-lookahead idea) | NO P-ID | propositional-formula construction - no Atlas home |
| ps2 | 1 | Set-theory predicate formulas (x in y) | NO P-ID | predicate-logic drill (extensionality; the Russell-flavored substrate) - no Atlas home |
| ps2 | 2 | De Morgan's law for set equality via a chain of IFFs | NO P-ID | proof-style drill - no Atlas home |
| ps2 | 3 | Binary words, languages, concatenation-definable (star-free) languages; concludes {00}* is not c-d | P4 PARTIAL | structural induction on the construction count (the problem's own footnote defines the count; 0-count base = finite languages) - the non-definability conclusion the payoff; the automata-theory substrate honestly a no-P-ID coverage observation |
| ps3 | 1 | The Fibonacci closed form F_n = (p^n - q^n)/sqrt(5) via strong induction | P4 GENUINE | the recurrence's characteristic roots (p, q the roots of x^2 = x + 1, in the hint) verified by strong induction - the recurrence+induction engine in its purest instructional form; NO P5 credit (no generating function used) |
| ps3 | 2 | The Block Stacking Game (score ab per split; find the maximizing strategy) | NO P-ID primary + P2 CROSS-NOTE | the potential-function/telescoping engine (p(S) = k(k-1)/2, potential loss ab per move; the mcs state-machine invariant method) - a coverage observation; the P2 pair-counting view recorded as a cross-note: each unordered box pair is separated in exactly one move, so the total score is n(n-1)/2 regardless of strategy |
| ps3 | 3 | Composition of functions: surjectivity/injectivity claims via arrows | NO P-ID | the arrows/definition drill - no Atlas home |
| ps5 | 1 | The binary pulverizer (gcd coefficients via division-by-2 and subtraction updates) | NO P-ID | invariant-preserving coefficient updates (the extended-Euclid invariant maintained across halving steps) - the same state-machine invariant class as ps3-2, a coverage observation |
| ps5 | 2 | Wilson's theorem: (p-1)! is congruent to -1 (mod p) | P1 GENUINE (involution/pairing face) | the hint IS the pattern: "think about pairing each term in (p-1)! with its multiplicative inverse"; part (a) is the fixed-point analysis (self-inverse iff k = 1 or k = p - 1) - the chunk-15 C4 verdict firing in freshman material |
| ps5 | 3 | Euler's phi is multiplicative, via the Chinese Remainder Theorem | P1 GENUINE | the CRT remainder map f: [0, ab) -> [0, a) x [0, b) proved a BIJECTION, restricted to the bijection Z*_ab -> Z*_a x Z*_b, the cardinality read off as phi(ab) = phi(a) phi(b) - count one set by matching 1-1 with a product set: the pass's cleanest firing |

### Pass-1 summary (28b)

Firings: P4 GENUINE 1 (ps3-1); P1 GENUINE 2 (ps5-2 at the pairing face; ps5-3); P4 PARTIAL 2 (ps1-2, ps2-3); P2 CROSS-NOTE 1 (ps3-2); NO P-ID 7. Headline: the freshman canon's combinatorial layer is exactly P1 and P4 - the Batch N accessibility datum's course-side mirror, now census-backed; the state-machine invariant engine (ps3-2, ps5-1) has no Atlas P-ID home - recorded as the teaching-side coverage observation (a synthesis-level question for a future Atlas session, NOT a WATCH). Honest scope: 13 problems from four of the twelve sets; ps4 deferred (official URL unpinned); ps6-ps12 at 28c or later; the 18.212 problem sets 1-3 also available for the next pass.
