# The CGT Atlas - backup and master repo

The durable, self-sufficient backup of the CGT Atlas project: a combinatorics & graph theory book (21 chapters, Volumes I-V, the 45-pattern Master Pattern Index P1-P45) authored in the Feynman-lecture style with machine-verified labs, plus its sibling projects. The repo is designed so that the ENTIRE project state - all work records, protocols, and next-step queues - can be resumed from this repo alone, without the original platform, account, or assistant.

## Repo map

- `cgt-atlas-project/` - the book + the Atlas project record.
  - `cgt-atlas.md` - the Atlas master: chapter map, the Master Pattern Index (P1-P45), session log, verification records.
  - `cgt-ch1-counting.md` ... `cgt-ch21-engines.md` - the 21 chapter masters (the canonical text).
  - `cgt-chN-web.html` - the 21 web exports (pre-rendered plain HTML, embed the masters byte-identically).
  - `cgt-ch1-web.md` - the canonical web frame (the renderMd v2 engine master).
  - `cgt-lean-track.md` - the unnumbered Lean formalization track (project idea; to merge with the computational-toolkit companion per the 2026-10-15 companion-volumes decision).
  - `cgt-publishing.md` - publishing conventions.
  - `cgt-pattern-map.html` - the Pattern Map: the companion registry of all 45 patterns (P1-P45) with every name the book uses for each across the chapters, plus a SHA-1-pinned JSON payload - the immutable join reference (P-ID = key) for automated validation/improvement pipelines.
  - `KNOWLEDGE.md` - the Atlas project record: current state, full session history, standing protocols, the expansion charter and the companion-volumes decision. A cold resumer (human or AI) reads this file FIRST.
- `papers/` - the paper-pattern survey (sibling project, COMPLETE): the 133-paper corpus, per-pattern dossiers, contest and teaching censuses, the ANALYSIS.md synthesis.
  - `KNOWLEDGE.md` - the survey project record: resume protocol, standing deferrals (including the OpenAI Oct-2026 math-release watch list), the gather/verification protocol. Read second.
  - `STATE.md` - the survey chunk ledger.
- `youth-math-research-collection/` - a future-project note (a compiled collection of pre-doctoral math research, by discipline; to start after the survey). See its `KNOWLEDGE.md`.

## How to resume

1. Read `cgt-atlas-project/KNOWLEDGE.md` (its Resume protocol section), then `papers/KNOWLEDGE.md`.
2. Current work lines, in order: (a) the lecture-level expansion campaign (charter in the Atlas record), driven by learner feedback on Ch. 1 gathered user-side; (b) the Probability companion and the toolkit/Lean merge (companion-volumes decision in the Atlas record); (c) the standing deferrals, including the OpenAI watch list (in the survey record).
3. Governing conventions: extend, never rewrite; every quantitative claim machine-verified before printing (documented engines, exact censuses, printed receipts); sessions end with records written AND pushed (push_files, git blob-SHA-1 verified mirrors); the 21 chapter numbers stay pinned; nothing enters the book on any external release's own say-so - verification first.

## Verification culture

Every chapter was authored with machine-verified numbers (documented Lehmer/MINSTD engines, exact censuses), adversarially reviewed chunk-by-chunk (two arguing experts, sessions 59-75), and the repo mirrors are verified byte-exact by git blob SHA-1. Web exports are pre-rendered plain HTML (no scripts) generated from the masters by the oracle-validated renderMd v2 engine.
