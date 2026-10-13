# Batch J - Spectral and linear algebra methods (gathered and mined)

Session chunk 10, 2026-10-13. All 4 papers metadata-verified; move descriptions at flagged-sketch level from publisher pages, located open copies, and general knowledge; zero paywalled fetches (scope rule unused).

## Verification table

| ID | Verified citation | Corrections vs seed |
|----|------------------|---------------------|
| J1 | Hoffman, "On eigenvalues and colorings of graphs", in B. Harris (ed.), Graph Theory and its Applications, Academic Press (1970), pp. 79-91 | none; venue "verify" flag resolved (Advanced Seminar proceedings volume, Academic Press); reprint DOI 10.1142/9789812796936_0041 (World Scientific) |
| J2 | Lovasz, "On the Shannon capacity of a graph", IEEE Trans. Inform. Theory 25(1): 1-7 (1979), DOI 10.1109/TIT.1979.1055985 | none; OPEN PDF scan located (SFU) |
| J3 | Alon-Milman, "lambda_1, isoperimetric inequalities for graphs, and superconcentrators", J. Combin. Theory Ser. B 38(1): 73-88 (1985), DOI 10.1016/0095-8956(85)90092-9 | title pinned vs seed; year 1985 confirmed; OPEN PDF on Alon's Princeton page |
| J4 | Haemers, "Eigenvalue techniques in design and graph theory", Ph.D. thesis, Technische Hogeschool Eindhoven (1979), DOI 10.6100/IR41103 | TITLE corrected vs seed (seed: "Minimum rank of graphs (minrank; verify)"); peer-reviewed minrank records pinned (Szeged 1978 proceedings, Colloq. Math. Soc. Janos Bolyai 25, 1981; Linear Algebra Appl. 40 (1981)); OPEN thesis PDFs via the CWI repository |

## Pattern census (Atlas P-IDs firing in this batch)

| P-ID | Fires in | Notes |
|------|----------|-------|
| P21 spectral / Rayleigh | J1, J2, J3, J4 (secondary) | the designed flagship batch: the Hoffman chromatic bound (eigenvalues as averaging devices), the Lovasz theta umbrella (orthonormal representations + the eigenvalue program), the Alon-Milman lambda_1-isoperimetry engine (Rayleigh quotient / test-function estimates - the Atlas P21 definition fires verbatim), and Haemers' eigenvalue toolkit as the secondary engine at J4. P21 is Atlas-named (Ch. 8), so this is confirmation firing, not a silent-registry event |
| P19 rank / linear algebra | J4 | SECOND BATCH firing (batch I: I3/I4/I10/I11; now J4 minrank) - the rank engine crosses batches within the survey corpus; the minimum rank of matrices fitting the complement graph bounds the Shannon capacity |
| P11 explicit construction | J3 (secondary) | eigenvalue gaps + group representations deliver explicit linear-sized expanders and superconcentrators |
| P15 coloring | J1 (secondary) | the spectral bound enters the chromatic-number toolkit as the classical Hoffman bound |
| P37 duality | J2 (secondary - synthesis call) | the max/min characterizations of theta form an early primal-dual optimization argument; family note widens (E4 planar, H10 Konig, I11 LP, J2 optimization duality) - synthesis decides |

## Honest hypothesis-test results (the batch's yield)

- J2 P19 MISSED (expected): theta is an optimization/spectral quantity, not a rank/dimension bound. The honest twist: the rank answer arrives in the very next paper - Haemers' minrank (J4), introduced partly in response to questions Lovasz posed in the theta paper. The J2-J4 pair is the survey's cleanest same-problem engine contrast since H6 vs H7 (probabilistic vs deterministic minors).
- J1, J3: single-pattern seeds, both confirmed (P21; J3 with a P11 secondary).
- J4: P19 confirmed with a P21 secondary - the thesis title itself ("Eigenvalue techniques in design and graph theory") names the two patterns this batch was designed around.

## New-pattern candidates and gate status after ten batches

1. No new candidates this batch. Gate status unchanged: CAND-A1/A2/A3 crossed; CAND-A4 unfired in-corpus (watch M); CAND-B5/C1/G1 synthesis calls.
2. Silent-registry ledger: no changes this batch - P21 is Atlas-named (confirmation firing, not first evidence) and no silent pattern fires. Full ledger: P28 (B1/B2), P29 (B4), P33 (F5/F6/F7), P34 (E2/E6; H6/H7/H8), P37 (E4; H10; I11; J2 secondary - synthesis call), P40 (C5), P30 (G1), P31 (G5/G8/G9/G10/G11), P32 (G4), P38 (H10 via companion). P20 and P24 remain silent - Batch K (chunk 11) is their designed home; watch K.
3. Watch-items unchanged otherwise: Kempe-chain likely dies at synthesis; the slice-rank note stands (synthesis call); the J2-J4 theta-vs-minrank engine contrast recorded for teaching.

## Verification levels statement

Metadata: web-verified (sources per paper; the J1 venue resolved via the World Scientific reprint plus the companion Part II's Wiley page citing the Advanced Seminar proceedings; the J4 thesis pinned via the TU Eindhoven research portal with DOI). Moves: flagged-sketch summaries. Zero full-text fetches. Open copies located: J2 (SFU scan), J3 (Alon's Princeton page), J4 (CWI repository + author copies); J1 available via the World Scientific reprint (paywalled; the bound and its proofs are standard in textbooks and machine-verified in the Atlas Ch. 8 lab - scope rule unused).
