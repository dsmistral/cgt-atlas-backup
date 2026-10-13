# Next-100 seed list - the extension phase (batches O-Y)

Added 2026-10-13 (chunk 16 scouting, user-directed). The planned survey closed at chunk 15 (134 seed rows / 133 distinct); this file seeds the EXTENSION: roughly the next 100 papers, gathered in batches O-Y per work style v2 (sub-chunks of about three papers, one push_files commit each). Selection rule: SOURCES.md section 6 (about half citation-driven classics, about half strategic targets; ACCEPTED papers only, never proposals, never mere surveys).

Status of rows: SEED data, exactly like CORPUS.md - unverified until each batch's gather chunk pins the row against web sources; corrections are logged, never silently made. Citation figures are honest seed ESTIMATES: on 2026-10-13 OpenAlex (shared-IP daily budget exhausted), Semantic Scholar (rate-limited) and the anonymous GitHub REST API (rate-limited) were all unavailable; "citation classic (est.)" means the estimated count clears the section-6 bar (>=100 citations pre-2010, >=50 for 2010+), to be pinned at gather.

Dedupe: all rows were checked against CORPUS.md (126 rows / 125 distinct) and SOURCES.md on 2026-10-13; near-collision exclusions and same-author continuation flags are recorded in SOURCES.md section 6. Courseware and contest finds follow SOURCES.md section 5 and never enter this census. Gather order: chunks 17+ work the batches below in order, starting with Batch O.

## Batch O - the Lovasz Local Lemma arc (6)

The corpus holds the origin (A5), the independence refinement (A7) and the constructive proof (A9). The arc's middle is missing, and the chunk-15 synthesis recommended the LLL for the Atlas's external canon (or as P13's sparse-dependency strengthening) - these rows close that arc.

| ID | Paper (seed) | Venue (seed) | Selection basis | Expected Atlas patterns / target |
|----|--------------|---------------|-----------------|----------------------------------|
| O1 | Spencer (1977) Asymptotic lower bounds for Ramsey functions | Discrete Math. 20 (verify) | citation classic (est.) | P13 (asymmetric LLL), P12 |
| O2 | Beck (1991) An algorithmic approach to the Lovasz Local Lemma. I | Random Structures Algorithms 2 (verify) | citation classic (est.) | P13, P18 (first constructive version) |
| O3 | Erdos-Spencer (1991) Lopsided Lovasz Local Lemma and Latin transversals | Discrete Appl. Math. 30 (verify) | citation classic (est.) | P13 (lopsided dependency) |
| O4 | Moser (2009) A constructive proof of the Lovasz Local Lemma | STOC 2009 (verify pages) | citation classic (est., 2010+) | P13; candidate: entropy compression (the CAND-A4 external lineage) |
| O5 | Kolipaka-Szegedy (2011) Moser and Tardos meet Lovasz | STOC 2011 (verify) | target: algorithmic LLL | P13, P18 |
| O6 | Suen (1990) A correlation inequality and a Poisson limit theorem for nonexchangeable events | J. Appl. Probab. 27 (verify) | citation classic (est.) | P13-family (the Poisson-paradigm companion) |

## Batch P - containers: the ancestor and the applications (4)

B7/B8 are the origins; the chunk-15 synthesis called containers on external evidence. The arc needs its pre-history and its flagship applications.

| ID | Paper (seed) | Venue (seed) | Selection basis | Expected Atlas patterns / target |
|----|--------------|---------------|-----------------|----------------------------------|
| P1 | Kleitman-Winston (1982) On the number of graphs without 4-cycles | Trans. Amer. Math. Soc. 272 (verify) | citation classic (est.) | the container ancestor (superseded by B7/B8 - the arc's origin test) |
| P2 | Samotij (2015) Counting independent sets in graphs | European J. Combin. 48 (verify) | citation classic (est., 2010+) | candidate: containers (application flagship) |
| P3 | Morris-Saxton (2016) The number of C4-free graphs (verify title) | Combin. Probab. Comput. (verify) | target: container method | candidate: containers (P1's conjecture closed) |
| P4 | Balogh-Liu-Sharifzadeh-Treglown (2015/16) The number of maximal sum-free subsets (verify exact form) | J. Eur. Math. Soc. (verify) | target: container application | candidate: containers (arithmetic setting) |

## Batch Q - the Flajolet school: analytic combinatorics (5)

CAND-C1 fired three times, all within Batch C; the chunk-15 synthesis recommended the external Flajolet-Sedgewick canon. These rows test the school OUTSIDE the C batch.

| ID | Paper (seed) | Venue (seed) | Selection basis | Expected Atlas patterns / target |
|----|--------------|---------------|-----------------|----------------------------------|
| Q1 | Flajolet-Odlyzko (1990) Singularity analysis of generating functions | SIAM J. Discrete Math. 3 (verify) | citation classic (est.) | CAND-C1 origin (P5-adjacent asymptotics) |
| Q2 | Bender (1974) Asymptotic methods in enumeration (a methods article, not a results survey) | SIAM Rev. 16 (verify) | citation classic (est.) | P5, CAND-C1 |
| Q3 | Banderier-Flajolet (2002) Basic analytic combinatorics of directed lattice paths | Theoret. Comput. Sci. 281 (verify) | citation classic (est.) | CAND-C1, P5 |
| Q4 | Flajolet-Gourdon-Dumas (1995) Mellin transforms and asymptotics: harmonic sums | Theoret. Comput. Sci. 144 (verify) | citation classic (est.) | CAND-C1 (the school's second engine) |
| Q5 | Jacquet-Szpankowski (1998) Analytical de-Poissonization and its applications | Theoret. Comput. Sci. 201 (verify) | target: the school's toolkit | CAND-C1 |

## Batch R - flag algebras: the descendants decide (4)

Both in-corpus firings (M3/M4) are within Batch M; the chunk-15 verdict was RECOMMENDED on external evidence. These rows are that external evidence.

| ID | Paper (seed) | Venue (seed) | Selection basis | Expected Atlas patterns / target |
|----|--------------|---------------|-----------------|----------------------------------|
| R1 | Reiher (2016) The clique density theorem | Ann. of Math. 184 (verify pages) | citation classic (est., 2010+) | WATCH flag algebras (the K_r program completed) |
| R2 | Hatami-Hatami (2024) The space of graph homomorphism inequalities and the bipartite swapping trick (verify) | Adv. Math. (verify) | target: flag-algebra descendant | WATCH flag algebras; P25 |
| R3 | Grzesik (2012) The minimal density of 5-cycles (verify) | Electron. J. Combin. (verify) | target: the pentagon problem | WATCH flag algebras |
| R4 | Borgs-Chayes-Lovasz-Sos-Vesztergombi (2008) Counting graph homomorphisms | Combinatorica 28 (verify) | citation classic (est.) | the graph-limits companion program; P25 |

## Batch S - absorption (4)

WATCH opened at the L8 origin (Keevash 2014); the chunk-15 synthesis recommended the external canon (Glock-Kuhn-Lo-Osthus and descendants).

| ID | Paper (seed) | Venue (seed) | Selection basis | Expected Atlas patterns / target |
|----|--------------|---------------|-----------------|----------------------------------|
| S1 | Glock-Kuhn-Lo-Osthus (2019/21) The existence of designs via iterative absorption / Efficient designs (verify published form) | Invent. Math. (verify) | citation classic (est., 2010+) | WATCH absorption (the L4/L8 existence arc's competitor engine) |
| S2 | Montgomery (2019) Spanning trees in random graphs (verify venue) | Adv. Math. (verify) | target: absorption in random graphs | WATCH absorption; P12 |
| S3 | Glock-Joos (2018/20) Existence of resolvable designs (verify) | J. Combin. Theory Ser. A (verify) | target: absorption application | WATCH absorption; P11 |
| S4 | Kwan (2018/20) Nearly all Steiner triple systems have perfect matchings (verify) | J. Eur. Math. Soc. (verify) | target: absorption downstream | WATCH absorption; P41/P42 family |

## Batch T - discharging and tree-decomposition DP (6)

P36 (discharging) is fully silent - a corpus-sampling gap: the planar-discharging tradition was never sampled; P35's only in-corpus touch was a partial at M9. This batch is the silent registry's repair.

| ID | Paper (seed) | Venue (seed) | Selection basis | Expected Atlas patterns / target |
|----|--------------|---------------|-----------------|----------------------------------|
| T1 | Appel-Haken (1977) Every planar map is four colorable. Part I: Discharging | Illinois J. Math. 21 (verify) | citation classic (est.) | P36 flagship (discharging's computer-assisted origin) |
| T2 | Appel-Haken-Koch (1977) Every planar map is four colorable. Part II: Reducibility | Illinois J. Math. 21 (verify) | citation classic (est.) | P36 |
| T3 | Robertson-Sanders-Seymour-Thomas (1997) The four-colour theorem | J. Combin. Theory Ser. B 70 (verify) | citation classic (est.) | P36; P18 (the second proof's engine) |
| T4 | Borodin (1979) On acyclic colorings of planar graphs (verify) | Discrete Math. 26 (verify) | citation classic (est.) | P36 application (human-scale discharging) |
| T5 | Courcelle (1990) The monadic second-order logic of graphs. I. Recognizable sets of finite graphs | Inform. and Comput. 85 (verify) | citation classic (est.) | P35 designed flagship (tree-decomposition DP) |
| T6 | Bodlaender (1996) A linear-time algorithm for finding tree-decompositions of small treewidth | SIAM J. Comput. 25 (verify) | citation classic (est.) | P35 companion; P18 |

## Batch U - correlation inequalities and the reflection principle (5)

| ID | Paper (seed) | Venue (seed) | Selection basis | Expected Atlas patterns / target |
|----|--------------|---------------|-----------------|----------------------------------|
| U1 | Fortuin-Kasteleyn-Ginibre (1971) Correlation inequalities on some partially ordered sets | Comm. Math. Phys. 22 (verify) | citation classic (est.) | the FKG origin (P13-family positive-correlation engine) |
| U2 | Ahlswede-Daykin (1978) An inequality for the weights of two families of sets, their unions and intersections | (verify venue) | citation classic (est.) | the four-functions theorem (FKG's combinatorial face) |
| U3 | van den Berg-Kesten (1985) Inequalities with applications to percolation and reliability (verify) | (verify) | target: disjoint occurrence | the BK inequality (P13-family) |
| U4 | Andre (1887) Solution directe du probleme resolu par M. Bertrand (verify title) | C. R. Acad. Sci. Paris 105 (verify) | citation classic (est.) | the reflection principle origin |
| U5 | Kreweras (1965) Sur une classe de problemes de denombrement lies au treillis des partitions (verify) | Cahiers B.U.R.O. (verify) | citation classic (est.) | noncrossing partitions (reflection-adjacent lattice counting) |

## Batch V - pre-1960 foundations not in the corpus (15)

The corpus's oldest rows start at Sperner 1928 / Ramsey 1930; the founding century before them was never sampled systematically.

| ID | Paper (seed) | Venue (seed) | Selection basis | Expected Atlas patterns / target |
|----|--------------|---------------|-----------------|----------------------------------|
| V1 | Cayley (1889) A theorem on trees | Quart. J. Pure Appl. Math. 23 (verify) | citation classic (est.) | P1 (tree-counting origin; the Prufer-adjacent flagship) |
| V2 | Kempe (1879) On the geographical problem of the four colours | Amer. J. Math. 2 (verify) | citation classic (est.) | Kempe chains origin (the E-batch watch's ancestor) |
| V3 | Petersen (1891) Die Theorie der regularen Graphs | Acta Math. 15 (verify) | citation classic (est.) | P16 (the factor-theorem origin) |
| V4 | Heawood (1890) Map colour theorem | Quart. J. Pure Appl. Math. 24 (verify) | citation classic (est.) | the Heawood bound; Kempe's error found (T-batch ancestor) |
| V5 | Birkhoff (1913) The reducibility of maps | Amer. J. Math. 35 (verify) | citation classic (est.) | reducibility origin (T1/T2's ancestor) |
| V6 | Redfield (1927) The theory of group-reduced distributions (verify) | Amer. J. Math. 49 (verify) | citation classic (est.) | P39 symmetry averaging (Polya's overlooked predecessor; distinct from C1/C7) |
| V7 | Menger (1927) Zur allgemeinen Kurventheorie (verify) | Fund. Math. 10 (verify) | citation classic (est.) | P16 (Menger's theorem; the D-batch gap) |
| V8 | Hall (1935) On representatives of subsets | J. London Math. Soc. 10 (verify) | citation classic (est.) | P16 (Hall's theorem; the D-batch gap) |
| V9 | Whitney (1935) On the abstract properties of linear dependence | Amer. J. Math. 57 (verify) | citation classic (est.) | matroid origin (a coverage-gap engine; Y7's ancestor) |
| V10 | de Bruijn (1946) A combinatorial problem (De Bruijn sequences) | Nederl. Akad. Wetensch. Proc. 49 (verify) | citation classic (est.) | P25 encoding (same-author continuation of C7, distinct paper) |
| V11 | Dilworth (1950) A decomposition theorem for partially ordered sets | Ann. of Math. 51 (verify) | citation classic (est.) | P9-family poset structure (I1's structural companion) |
| V12 | Redeai (1934) Ein kombinatorischer Satz (verify) | Acta Litt. Szeged 7 (verify) | citation classic (est.) | tournament Hamilton paths (an induction classic) |
| V13 | Kuratowski (1930) Sur le probleme des courbes gauches en topologie | Fund. Math. 15 (verify) | citation classic (est.) | planarity characterization (M7's ancestor) |
| V14 | Shannon (1956) The zero-error capacity of a noisy channel | Bell System Tech. J. 35 (verify) | citation classic (est.) | the J2 zero-error lineage's origin |
| V15 | Tutte (1947) A ring in graph theory | Proc. Cambridge Philos. Soc. 43 (verify) | citation classic (est.) | P16 (the 1-factor theorem; Tutte's third corpus line, distinct from C3/E4) |

## Batch W - 1950-1990 classics not in the corpus (12)

| ID | Paper (seed) | Venue (seed) | Selection basis | Expected Atlas patterns / target |
|----|--------------|---------------|-----------------|----------------------------------|
| W1 | Gale-Shapley (1962) College admissions and the stability of marriage | Amer. Math. Monthly 69 (verify) | citation classic (est.) | P18; the N5/N6 stable-matching ancestor |
| W2 | Hoffman-Singleton (1960) On Moore graphs with diameters 2 and 3 | IBM J. Res. Dev. 4 (verify) | citation classic (est.) | P21 spectral; P8 extremal |
| W3 | Gomory-Hu (1961) Multi-terminal network flows | J. SIAM 9 (verify) | citation classic (est.) | P17 (flow trees; the D-batch extension) |
| W4 | Graham-Pollak (1971) On the addressing of graphs | Bull. Amer. Math. Soc. 77 (verify) | citation classic (est.) | P19 (address-matrix rank) |
| W5 | Gerencser-Gyarfas (1967) On Ramsey-type problems | Ann. Univ. Sci. Budapest. Eotvos Sect. Math. 10 (verify) | citation classic (est.) | path Ramsey (the F-batch extension) |
| W6 | Mirsky (1971) A dual of Dilworth's decomposition theorem | Amer. Math. Monthly 78 (verify) | citation classic (est.) | poset dual (V11's dual statement) |
| W7 | Erdos-Selfridge (1973) On a combinatorial game (verify) | J. Combin. Theory Ser. A 14 (verify) | citation classic (est.) | positional games origin (the B4/P13 family) |
| W8 | Erdos-Renyi (1961) On the strength of connectedness of a random graph | Acta Math. Acad. Sci. Hungar. 12 (verify) | citation classic (est.) | threshold arc extension (the A2/A3 lineage) |
| W9 | Tutte (1961) On the problem of decomposing a graph into n connected factors | J. London Math. Soc. 36 (verify) | citation classic (est.) | P16 (the n-factor theorem) |
| W10 | Seymour (1980) Decomposition of regular matroids | J. Combin. Theory Ser. B 28 (verify) | citation classic (est.) | matroid structure (V9 lineage; distinct from E6) |
| W11 | Bregman (1973) Some properties of nonnegative matrices and their permanents (verify) | (verify) | citation classic (est.) | P25/entropy-family (the permanent bound; the N2/N8 Holder-entropy lineage) |
| W12 | Edmonds (1965) Maximum matching and a polyhedron with 0,1-vertices | J. Res. Nat. Bur. Standards 69B (verify) | citation classic (est.) | P16; P37 (LP-duality origin; distinct from D3/D5) |

## Batch X - expansion and the second eigenvalue (6)

J-batch extension: the spectral school's algorithmic half was never sampled.

| ID | Paper (seed) | Venue (seed) | Selection basis | Expected Atlas patterns / target |
|----|--------------|---------------|-----------------|----------------------------------|
| X1 | Alon (1986) Eigenvalues and expanders | Combinatorica 6 (verify) | citation classic (est.) | P21 (distinct from J3) |
| X2 | Margulis (1973) Explicit constructions of concentrators (verify) | Problemy Peredachi Informatsii 9 (verify) | citation classic (est.) | expansion origin |
| X3 | Gabber-Galil (1981) Explicit constructions of linear-sized superconcentrators (verify title) | J. Comput. System Sci. (verify) | citation classic (est.) | explicit expanders |
| X4 | Lubotzky-Phillips-Sarnak (1988) Ramanujan graphs | Combinatorica 8 (verify) | citation classic (est.) | P21 flagship |
| X5 | Marcus-Spielman-Srivastava (2015) Interlacing families II: Mixed characteristic polynomials and the Kadison-Singer problem | Ann. of Math. 182 (verify) | citation classic (est., 2010+) | P21; the P22-adjacent polynomial bridge |
| X6 | Reingold-Vadhan-Wigderson (2002) Entropy waves, the zig-zag graph product, and new constant-degree expanders (verify title) | Ann. of Math. 155 (verify) | citation classic (est.) | P18; P21 |

## Batch Y - wildcards (7)

User-directed breadth: the strategic picks that fit no single theme - recent breakthroughs and missing pillars.

| ID | Paper (seed) | Venue (seed) | Selection basis | Expected Atlas patterns / target |
|----|--------------|---------------|-----------------|----------------------------------|
| Y1 | Linial (1992) Locality in distributed graph algorithms | SIAM J. Comput. 21 (verify) | citation classic (est.) | P18 (the LOCAL model; the M-batch algorithmic extension) |
| Y2 | Komlos-Sarkozy-Szemeredi (1997) The blow-up lemma | Combinatorica 17 (verify) | citation classic (est.) | P30 (regularity's flagship application) |
| Y3 | Ding-Sly-Sun (2022) Proof of the satisfiability conjecture for large k | Ann. of Math. 196 (verify) | citation classic (est., 2010+) | threshold arc extension (the B3/B5/B6 lineage) |
| Y4 | Hastad (2001) Some optimal inapproximability results | J. ACM 48 (verify) | citation classic (est.) | P25 (PCP reductions; the optimization boundary) |
| Y5 | Campos-Griffiths-Morris-Saxton (2023/25) The exponential improvement to diagonal Ramsey numbers (verify title/venue) | (verify journal) | target: F-batch descendant | P12 (the exponential-constant breakthrough) |
| Y6 | Bohman-Frieze (2001) Avoiding a giant component | Random Structures Algorithms 19 (verify) | citation classic (est.) | P12 (the Achlioptas-process origin; the B4 guided-random lineage) |
| Y7 | Adiprasito-Huh-Katz (2018) Hodge theory for combinatorial geometries | J. Amer. Math. Soc. 31 (verify) | citation classic (est., 2010+) | the log-concavity/Lefschetz engine (a coverage-gap engine; V9's descendant) |
