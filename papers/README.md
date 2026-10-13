# The CGT Paper-Pattern Survey

**Purpose.** The CGT Atlas's Master Pattern Index (P1-P42) was mined from textbook canon. This survey mines the primary literature instead: the most highly cited papers of combinatorics and graph theory, gathered chunk by chunk, to (1) check the index against the field's actual problem-solving practice, (2) give the silent forward-registry patterns (P20, P24, P27-P42) their first genuine usage evidence, and (3) hunt for load-bearing patterns the textbook canon did not surface (P43+ candidates).

**Scope decisions, user-locked at chunk 0 (2026-10-13):**
1. **Home:** this papers/ subfolder of the cgt-atlas-backup repository. The 37 root files are the Atlas light set; they are read-only for this survey.
2. **Depth:** deep sweep - 126 seed papers in 13 thematic batches A-M.
3. **Gathering:** per paper, verified citation metadata + abstract or faithful summary + the decisive proof moves. Fetch an open-access full text only when a candidate NEW pattern does not yet have enough published detail to write teaching material from, and a paywall-free copy exists online.
4. **Seed honesty:** the batch tables in CORPUS.md are seed data from general knowledge, NOT verified. Every field is confirmed at gather time; corrections and swaps are logged in the batch file, never made silently.

**Chunk protocol - one chunk per session (session-limit safety):**
- **Chunk 0 (done):** bootstrap - this charter, the seed corpus, the ledger.
- **Chunks 1-13:** one batch per session. Per batch: verify metadata (web source URL recorded per paper), gather abstract or summary, extract the decisive moves, tag each move with Atlas P-IDs, log candidate new patterns, then push papers/BATCH.md + per-paper files + updated STATE.md in ONE push_files commit.
- **Chunk 14:** synthesis - papers/ANALYSIS.md: recurrence-tested candidate patterns, proposed P43+ entries, usage evidence for the silent P-IDs, honest coverage gaps.

**Rules (Atlas conventions carried over):**
- **Push route:** push_files only (astral-safe). Never create_or_update_file for papers/ files. No emoji or other astral characters in files under papers/.
- **Extend, never rewrite:** published batch files are corrected by appending a correction log, not silent rewrites. Every session's changes are described in the commit message.
- **The load-bearing test (new-pattern gate):** a candidate pattern enters ANALYSIS.md only if it solves or decisively advances multiple problems across at least two different batches. Single-batch candidates are recorded in batch files but marked demoted.
- **Verification levels:** executed lab > complete proof > flagged sketch > formal track - each batch file records which level each claim reached. Web-sourced metadata always carries its source URL.
- **Expected-patterns columns in CORPUS.md are hypotheses to test at gather time, never conclusions.**

**Per-paper file template (papers/NN-slug.md):**

    # NN - short title
    - Metadata: authors, year, title, venue, DOI or arXiv id (verified at gather, with source URL)
    - Abstract or faithful summary (level stated: quoted vs summarized)
    - The decisive moves: numbered, each tagged [P##] or [CANDIDATE: name - evidence so far]
    - New-pattern candidates: shape, move, recurrence evidence so far
    - Full text: fetched (URL) or not needed - per the scope rule
    - Corrections log: what the gather verification changed vs the seed row


---

## Work style v2 (2026-10-13, user-directed - adopted after the chunk-11 session's retry)

Two structural changes, adopted as the standing method and recorded here so every new chat resumes into them directly:

1. **Sub-chunked gathering.** Batches are gathered in sub-chunks of about three papers, and EVERY sub-chunk is pushed as its own commit (per-paper files + the batch file's section + the STATE.md marker + the touched pattern files). A session may complete one or more sub-chunks; no gather work is ever carried unpushed across a turn boundary. Chunk numbering: chunk 12 = Batch L in sub-chunks 12a (L1-L3), 12b (L4-L6), 12c (L7-L9), 12d (L10-L12); chunk 13 = Batch M likewise (13a M1-M3, 13b M4-M6, 13c M7-M9).
2. **The pattern layer (papers/patterns/).** One file per Atlas pattern P1-P42 plus candidate/watch dossiers, grouped into family folders by similarity and interdependence. Census rows and hypothesis-test notes are quoted from the batch files, which remain the gather record. Updated incrementally at every sub-chunk close; the chunk-14 synthesis builds ANALYSIS.md from these dossiers.
3. **Light resume.** Survey sessions restore NO canvases (the Atlas light set in this repo is read-only for the survey). Resume = read the knowledge topic, then papers/STATE.md, then only the active batch's files and the touched pattern dossiers. Never load all batch files at once.
