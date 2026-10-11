# RESUME — CHUNK 48g (INSTALL) — IN FLIGHT (session 2026-10-11)

Authoritative state: KNOWLEDGE.md (SESSION STATE + CHUNK STATE + working point) + this file. GitHub repo dsmistral/cgt-atlas-backup = MAIN SOURCE OF TRUTH (user direction, this session): checkpoint-push after every milestone so a disconnect or a local-layer failure loses at most the current sub-step; if the local file layer is inaccessible, rebuild from the repo.

## Context
- 48f DONE (STATUS LOG entry 52): the Ch. 12 master cgt-atlas-project/cgt-ch12-olympiad.md is COMPLETE pre-install — 166,459 canonical UTF-8 bytes / 962 lines / frontmatter name "cgt-ch12-olympiad" (= the planned canvas folder name).
- 48g scope: (i) turn the master’s three pre-install markers honest at install time — the Editions paragraph, the Standing-decisions tail, and the status footer (🟨 authored pre-install, chunks 48d–48f → 🟩 installed, chunks 48d–48g, naming the web-edition build as the remaining next chunk); (ii) install the canvas /home/user/canvases/cgt-ch12-olympiad/CANVAS.md byte-identically to the master; (iii) close-out — buffer (STATUS LOG entry 53 + CHUNK STATE row 48g ✅ + 48g WORKING LOG + SESSION STATE → 48h), atlas (row 48 48g-DONE note + Next cell 48g–48h → 48h + atlas canvas resync), GitHub pushes, fold this file into the 48g WORKING LOG + delete local.
- STANDING GOTCHA: UTF-8 byte work goes through the canonical path ONLY (TS read → in-memory verify → write → readback string-equality); the bash layer double-encodes UTF-8 intermittently (CHECKPOINT 48f-4).

## Step log (updated after EVERY sub-step)
0. ✅ Disconnect recovery: state verified — buffer holds only KNOWLEDGE.md (262,317 bytes / 354 lines); master untouched (footer still pre-install at line 962); no ch12 canvas (the pre-disconnect mkdir had not persisted — redone); atlas 257 lines. No 48g sub-step was lost.
1. ✅ RESUME.md created; pushed to GitHub as this commit (connectivity check + source-of-truth checkpoint).
2. [ ] Master edits: the three pre-install markers turned (anchor-asserted in-memory, single write, readback equal).
3. [ ] Canvas install: CANVAS.md == master (readback string-equality) + hygiene gate re-run.
4. [ ] Buffer close-out: entry 53, CHUNK STATE 48g ✅, 48g WORKING LOG, SESSION STATE → 48h (+ the new GitHub-source-of-truth standing direction recorded).
5. [ ] Atlas row 48: 48g-DONE note + Next cell → 48h; atlas canvas resync (canonical copy + readback equality).
6. [ ] Close push: atlas + KNOWLEDGE.md + RESUME (closed state).
7. [ ] Fold RESUME into the 48g WORKING LOG + delete local + tidy verify (buffer = KNOWLEDGE.md only; 2 knowledge topics; ch12 canvas present).

On retry: read this step log + KNOWLEDGE.md CHUNK STATE first; NEVER redo a completed sub-step.

## NEW STANDING DIRECTION (user, this session — to be folded into KNOWLEDGE.md SESSION STATE at close)
GitHub repo = the main source of truth; the local knowledge base is second. Checkpoint-push after every milestone (not just at chunk close); prioritize verification + intact, recoverable data; if the local file layer becomes inaccessible, rebuild from the repo.
