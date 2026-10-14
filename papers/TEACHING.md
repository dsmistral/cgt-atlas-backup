# Teaching aids track - source register and per-text records (SOURCES.md section 5.1)

Added 2026-10-14 (chunk 28, sub-chunk 28a). Purpose: free instructional texts and open courseware scoured for EXPLANATION AIDS that make existing Atlas patterns clearer to human learners - worked micro-proofs, intuition-first walkthroughs, visual scaffolds. The Atlas's Feynman-style presentation method is the standing method for any aid this track recommends; this survey RECOMMENDS aids and never edits the Atlas (adopting an aid is a future Atlas session requiring user approval, per the Atlas working protocol). Every text or course enters the SOURCES.md 5.1 register before use; entries are never removed silently.

Track A (this file): the per-text record - title, units used, availability, and the patterns exercised, honestly graded. Verification level "syllabus" = the unit list pinned from a web-verified index page and patterns mapped from unit titles only; "full-text" = the text read and mined (aids lifted with pinpoint citations). Track B (the instructional pattern census: course problem sets and solution notes) opens as a separate census file at a later sub-chunk - never as paper firings.

## 1. Source register (availability web-verified 2026-10-14; the register of record is SOURCES.md section 5.1)

| ID | Source | Availability (verified) | URL | Status |
|----|--------|------------------------|-----|--------|
| T1 | MIT OCW 18.212 Algebraic Combinatorics (Spring 2019; Alexander Postnikov; 39 lecture-note PDFs + problem sets) | OPEN (MIT OpenCourseWare) | https://ocw.mit.edu/courses/18-212-algebraic-combinatorics-spring-2019/ | REGISTERED + deep-gathered at 28a (syllabus level) |
| T2 | MIT OCW 6.042J Mathematics for Computer Science (Spring 2015; Albert R. Meyer; open textbook (Lehman-Leighton-Meyer) + lecture notes/videos) | OPEN (MIT OpenCourseWare) | https://ocw.mit.edu/courses/6-042j-mathematics-for-computer-science-spring-2015/ | REGISTERED; mining deferred |
| T3 | Flajolet and Sedgewick, "Analytic Combinatorics" (Cambridge University Press 2009) | OPEN author PDF | https://algo.inria.fr/flajolet/Publications/book.pdf | REGISTERED; mining deferred |
| T4 | Jukna, "Extremal Combinatorics: With Applications in Computer Science" (2nd ed., Springer 2011, EATCS series) | OPEN author-hosted PDF | https://web.vu.lt/mif/s.jukna/EC_Book/ | REGISTERED; mining deferred |
| T5 | Levin and Peres with Wilmer, "Markov Chains and Mixing Times" (2nd ed., AMS 2017) | OPEN author PDF | https://pages.uoregon.edu/dlevin/MARKOV/markovmixing.pdf | REGISTERED; mining deferred |
| T6 | Lovasz, "Combinatorial Problems and Exercises" (2nd ed., AMS Chelsea 2007, ISBN 978-0-8218-4262-1) | NO open edition from the publisher or author found (AMS record); third-party hosted copies sighted and excluded per policy | https://www.ams.org/publications/authors/books/postpub/chel-361 | REGISTER-ONLY (print edition) |
| T7 | van Lint and Wilson, "A Course in Combinatorics" (2nd ed., Cambridge University Press) | NO open edition found (publisher record; open front-matter PDF only); third-party hosted copies excluded per policy | https://www.cambridge.org/core/books/course-in-combinatorics/84B89574496561D5E3A960863B85E4B7 | REGISTER-ONLY (print edition) |

Register notes (2026-10-14): the SOURCES 5.1 candidate list named all seven; T1-T5 verified OPEN, T6-T7 honestly verified as NOT open - print-edition register entries, never open-fetch targets. T2's textbook authorship pinned from the OCW readings record ("notes ... courtesy of Eric Lehman, Tom Leighton, and Albert Meyer"). Verification records: the OCW course pages (T1's lecture-notes listing pinned; T2's open-textbook resource page), the author pages (T3 the Flajolet Publications book.pdf; T4 the author's EC_Book page; T5 the Levin MARKOV page), the AMS postpub record (T6), the Cambridge core record (T7).

## 2. Per-text records (Track A)

### T1 - MIT OCW 18.212 Algebraic Combinatorics (Spring 2019, Postnikov) - gathered at SYLLABUS level

Units used (39 lecture-note PDFs; titles pinned from the OCW lecture-notes page): Catalan numbers I-II; pattern avoidance in permutations; the Frobenius-Young identity; the hook-length formula via a random hook walk; hook walks; q-factorials and q-binomial coefficients; Grassmannians over finite fields; sets and multisets, statistics on permutations; Stirling numbers; Eulerian numbers, increasing binary trees, three Pascal-like triangles; three problem-set discussion pairs; posets and lattices (Boolean, partition, Young's); distributive lattices, Birkhoff's fundamental theorem; Sperner's property; Greene's theorem vs the Schensted correspondence; differential posets; unimodality of Gaussian coefficients; partition theory (Franklin's combinatorial proof of Euler's pentagonal number theorem; a combinatorial proof of Jacobi's triple product identity); two combinatorial proofs of Cayley's formula; the Matrix Tree Theorem (three lectures, incl. the Cauchy-Binet proof) and the directed version (by induction; via the Involution Principle); electrical networks; Eulerian cycles in digraphs, the B.E.S.T. theorem; parking functions and tree inversion polynomials; the Pascal triangle; the Lindstrom-Gessel-Viennot lemma (two lectures); the MacMahon proposition; plane partitions.

Patterns exercised (SYLLABUS LEVEL - mapped from the pinned unit titles; every mapping below is a candidate until the 28b full-text pass pins it against the dossiers):

- P1 (bijection): the course's flagship engine - Catalan numbers, pattern avoidance, Cayley's formula (TWO bijective proofs in one unit), parking functions, plane partitions, the Lindstrom-Gessel-Viennot determinant-to-paths family.
- P1's involution face (the chunk-15 C4 verdict: the sign-reversing involution a FACE of P1, ANALYSIS.md): THREE units are involution proofs by title - Franklin's proof of Euler's pentagonal number theorem, the Involution Principle for the directed Matrix Tree Theorem, and the LGV proof - the strongest instructional evidence yet recorded for that verdict; each unit a candidate worked-micro-proof aid for the P1 involution face.
- P5 (generating function): the enumeration spine of the early units (Catalan, Stirling, Eulerian, partition theory, MacMahon); honestly UNPINNED at syllabus level - the unit titles do not separate the GF engine from the bijective engine; 28b decides.
- P9 (pigeonhole): the Sperner's-property unit - the antichain line's instructional home (the K1/K5/K7 corpus line; the V11 Dilworth P9 precedent).
- P10 (averaging/expectation): the hook-length formula BY A RANDOM HOOK WALK - a probabilistic proof named in the unit title itself; candidate intuition-first walkthrough aid for P10 (the hook walk's engine read against the P10 dossier at 28b).
- P25 (reduction/encoding): candidate at the B.E.S.T. unit (Eulerian circuits counted via arborescences - an encoding-shaped reduction); honestly UNPINNED at syllabus level.
- P19 (rank/linear algebra): candidate at the Matrix Tree units (determinant counting via Cauchy-Binet - the linear-algebra family's instructional face); UNPINNED - the honest alternative is a coverage observation (determinant evaluation as an engine with no clean Atlas P-ID), decided at 28b.
- No-Atlas-P-ID substrate at syllabus level: the poset/lattice units (Birkhoff's theorem, differential posets, Greene-Schensted) - recorded as units used, pattern mapping deferred.

Honest syllabus-level misses: no unit titles the probabilistic method beyond the hook walk, no entropy (P29), no regularity (P30/P31), no compression (P23) - expected for an algebraic-combinatorics course; the accessible layer is P1/P5/P9/P10 plus the linear-algebra counting units.

Aid-type recommendations (Feynman style; the survey recommends, never edits the Atlas; all lifts deferred to the 28b full-text pass): intuition-first walkthrough - the random hook walk (P10); visual scaffold - the Franklin involution on partition diagrams and the LGV lattice-path pictures (P1's involution face); worked micro-proofs - Cayley's two bijective proofs (P1).

### T2-T7 - register-only records (mining deferred)

- T2 (6.042J, Spring 2015): the CS-side freshman canon (induction, pigeonhole, counting, probability, graphs) - expected instructional home of P4/P9/P1/P10/P13 (the Batch N accessibility datum's course-side mirror); the open Lehman-Leighton-Meyer textbook pinned on the OCW site; unit mapping at the mining pass.
- T3 (Flajolet-Sedgewick): the analytic-combinatorics school's own book (symbolic method, singularity analysis) - the CAND-C1/P43+ external canon's text; expected P5 coverage at the instructional level; Note 19's promotion question shadows the mapping.
- T4 (Jukna): the extremal course text - the counting/pigeonhole/linear-algebra/probability layer with explicit Lovasz-Local-Lemma and entropy chapters; expected P9/P2/P10/P13/P29 coverage at the instructional level.
- T5 (Levin-Peres): the mixing text (coupling, spectral, entropy) - expected P10/P21 coverage; P12-adjacent sampling material scanned honestly at mining.
- T6/T7 (print-only): aids citable from the print editions only; no open fetches (the zero-paywalled-fetch policy).

## 3. Sub-chunk plan (work style v2)

- 28b: the T1 full-text pass (the mapping pinned against the dossiers; aid lifts with pinpoint citations) + the T2 textbook census (Track B opens: the instructional census file, under the corpus census method's honesty rules).
- 28c: T3-T5 mining + the remaining Track B census passes.
- Then the contest canon (SOURCES 5.2): Putnam, IMO/shortlists, USAMO, Kurschak - free official sources only.
