# Batch V - pre-1960 foundations (extension corpus; gathered and mined; work style v2)

Chunk 24 under work style v2: three sub-chunks (24a V1-V5; 24b V6-V10; 24c V11-V15), each pushed as its own commit. Seeded from NEXT100.md (chunk 16 scouting, user-directed): the corpus's oldest rows start at Sperner 1928 / Ramsey 1930 - the founding century before them was never sampled systematically; this batch gathers the origins. It carries the WATCH-kempe ORIGIN-LINEAGE TEST (V2 Kempe 1879 the origin; V4 Heawood 1890 the flaw's discovery; V5 Birkhoff 1913 reducibility's father - the test the 22a reopening announced) and the P16 origins at V3 (Petersen's factor theorem), with Menger/Hall/V15-Tutte to follow at 24b/24c. ACCEPTED papers only; the chunk-16 citation figures remain ESTIMATES (the 2026-10-13 API incident, SOURCES.md section 6) - this gather verifies METADATA against web sources, not citation counts.

| Sub-chunk | Papers | Status |
|-----------|--------|--------|
| 24a | V1 Cayley trees; V2 Kempe four colours; V3 Petersen regular graphs; V4 Heawood map colour; V5 Birkhoff reducibility | DONE (section below) |
| 24b | V6 Redfield; V7 Menger; V8 Hall; V9 Whitney matroids; V10 de Bruijn sequences | PENDING |
| 24c | V11 Dilworth; V12 Redeai; V13 Kuratowski; V14 Shannon zero-error; V15 Tutte 1-factor | PENDING |

## Sub-chunk 24a (V1-V5) - gathered and mined 2026-10-13

All five papers metadata-verified (sources recorded per paper); ZERO SEED CORRECTIONS - V1/V3/V4/V5 confirmed with pages pinned, V2 confirmed with the pages honestly recorded as not-pinned in the consulted records (volume/issue pinned; a V3 title-form note recorded); moves at flagged-sketch level; zero paywalled fetches; no full texts needed under the scope rule (the open scans - Wikisource, Internet Archive, Project Euclid - and the standard histories carry the pattern decisions). HEADLINE: THE WATCH-KEMPE ORIGIN-LINEAGE TEST LANDS - V2 IS A GENUINE ORIGIN FIRING (the chain-swap engine IS the 1879 proof's central device; the fallacy Heawood found is elsewhere - the two-chain interference), V5 a PARTIAL (the interchanges inside the ring-colouring reducibility analysis), V4 scanned/not credited (the flaw's discovery is a counterexample role); the watch's arc is now origin-anchored: E-batch presentation level -> T2/T3 genuine at scale -> V2 genuine at the origin.

### Verification table

| ID | Verified citation | Corrections vs seed |
|----|------------------|---------------------|
| V1 | Cayley, "A theorem on trees", Quart. J. Pure Appl. Math. 23 (1889) 376-378 (the Wikipedia Cayley's-formula reference list; the citation records uniformly pinning Quarterly Journal of Mathematics 23, 376-378) | NONE - CONFIRMED (pages pinned) |
| V2 | Kempe, "On the geographical problem of the four colours", Amer. J. Math. 2(3) (1879) (the JSTOR record 2369235; the Wikisource scan; the Internet Archive scan) | NONE - CONFIRMED (Vol. II No. 3 pinned); pages NOT pinned in the consulted records - recorded honestly |
| V3 | Petersen, "Die Theorie der regularen graphs", Acta Math. 15 (1891) 193-220, DOI 10.1007/BF02392606 (the open Project Euclid scan of the Acta volume; the Wikipedia Petersen's-theorem reference; the Semantic Scholar record) | NONE - CONFIRMED (pages + DOI pinned); title-form note: the journal's own title page prints "graphs" lowercase (the repo title ASCII-izes the umlaut) |
| V4 | Heawood, "Map colour theorem", Quart. J. Pure Appl. Math. 24 (1890) 332-338 (the ACM DL citing literature uniformly pinning the citation; the four-colour histories) | NONE - CONFIRMED (pages pinned) |
| V5 | Birkhoff, "The reducibility of maps", Amer. J. Math. 35 (1913) 115-128 (the AMS Bulletin bibliography record; the JSTOR record 2370276; the Internet Archive scan) | NONE - CONFIRMED (pages pinned) |

### Pattern census (sub-chunk 24a)

| P-ID | Fires in | Notes |
|------|----------|-------|
| WATCH Kempe | V2 (genuine, ORIGIN), V5 (partial), V4 (scanned, not credited) | V2: the chain-swap engine IS the 1879 proof's central device - four deployment cases each repaired by a two-colour chain interchange; the fallacy is elsewhere (the two-chain interference Heawood found); the watch's origin firing lands exactly as the 22a reopening predicted. V5: Kempe interchanges inside the ring-colouring reducibility analysis (the Birkhoff diamond) - partial, no double credit with T2/T3. V4: the flaw's discovery is a counterexample role, not an engine firing (the five-colour salvage's single chain is presentation-level credit only) |
| P1 | V1 (partial) | the labelled-tree count's origin (n^(n-2) plus the degree-refined multinomial extension, crediting Borchardt); the note's own argument is a flagged sketch, the bijection face is Prufer 1918 (uncorpus'd, retrospective) - the census credits the counting origin, not a bijective engine |
| P4 | V2 (partial), V5 (partial) | UNPLANNED by seed (the rows targeted the watch/lineage targets): V2 the minimal-counterexample induction frame (remove a low-degree region, extend the colouring - the extension step fails, the frame survives); V5 the frame institutionalized as reducibility (the configuration a smallest counterexample cannot contain - the concept the computer proofs completed) |
| P16 | V3 (partial) | the factor-theorem origin: cubic bridgeless => perfect matching, in connection with Tait's edge-colouring route to the four-colour problem; alternating-chain embryonics present, the modern augmenting-path engine retrospective (no double credit with the D-batch flagship firings); "by today's standards Petersen's proof is complicated" - the standard historical assessment |
| P2 | V4 (partial) | UNPLANNED by seed: the Heawood bound's Euler-formula counting - the vertex/edge/face counts combined through the Euler characteristic deliver the genus-to-colours bound; double counting in Euler-formula clothes |

### Engine contrast and lineage (sub-chunk 24a)

- THE FALLACY-VS-ENGINE DATUM (recorded for teaching): a FLAWED proof canonized a REAL engine. Kempe's 1879 argument fails (Heawood 1890's two-chain interference), but its central device - the two-colour chain interchange - survives into every later proof of the family: Heawood's valid five-colour salvage, Birkhoff's reducibility computations (V5), and the computer proofs' reducibility engine (T2/T3, "basing their methods on reducibility using Kempe chains" per the MacTutor record quoted at 22a). The pattern layer's census credits engines only when they are load-bearing, and the origin's engine passes that test even though its first deployment failed.
- THE ARC: V2 the origin (1879) -> V4 the flaw + the salvage (1890) -> V5 reducibility institutionalized (1913) -> T2/T3 the program completed (1977/1997) - the four-colour saga gathered at its own origins inside one sub-chunk, with the T-batch firings now origin-anchored.
- THE V1 ATTRIBUTION NOTES: Borchardt 1860 the formula's actual first discovery (a determinant computation, uncorpus'd); Cayley's note extends to degree-refined multinomial counts and credits Borchardt; the bijection face is Prufer 1918 (uncorpus'd, retrospective). The census splits honestly: the counting origin fires P1 partial at V1; the bijection engine belongs to Prufer and is not credited.
- Coverage observation (recorded for synthesis, not a WATCH): the reducibility PROGRAM itself (unavoidability + reducibility as a proof architecture) matches no Atlas P-ID - the frame's P4 partial is the census's honest ceiling at this gather; the architecture is the T-batch's own story and stays there.
