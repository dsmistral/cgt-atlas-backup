---
name: cgt-plainhtml-buffer
description: "CGT Atlas session 57 — the plain-HTML export pass: all 16 .html exports (Ch. 1–16) converted to fully pre-rendered plain HTML, replacing the JS-rendered ones (user decisions: all 16, same paths); the session-56 banner miss fixed honestly. Temp resume buffer: read the STATUS LOG first on retry."
display_name: "CGT Atlas plain-HTML export pass buffer (temp)"
icon: 📄
---

# CGT Atlas — session 57: the plain-HTML export pass (RESUME POINT)

**What this is.** Temp durable buffer for session 57 (user: deep Mity; org deepsudden), user-directed: **convert the .html exports to plain HTML — fully pre-rendered content baked into the page, no base64 payload, no runtime script.** User decisions (at open): (1) **all 16 chapters** (Ch. 1–16 — every web gets a plain export, not just the 5 refreshed mirrors); (2) **replace** the existing JS-rendered .html exports at the same repo paths (no -plain.html duplicates). The .md web editions remain the canonical byte-identical embed route (payload oracles unchanged); only the .html export format changes.

**The session-56 banner miss (fixed honestly here).** The four renumbered webs' banners still said the OLD chapter numbers (`Chapter&nbsp;14` in ch13-web, 15 in ch14-web, 16 in ch15-web, 17 in ch16-web) — the `&nbsp;` HTML entity hid the token from the session-56 census (`Chapter N` literal search), so the renumbering never touched the banner line. Fix: renumber the banner `&nbsp;` tokens in the 4 .md webs (changed-line oracle: exactly one line per web; payload untouched); the stale-banner JS .html mirrors get replaced by the plain exports anyway.

**Build rule (the new .html format).** plain .html := the web .md frame (lines 7–46: doctype, head, style, banner with honest plain-export text + correct Chapter&nbsp;N) + `<main id="content">` + `renderMd(decoded payload)` + `</main></body></html>`. No `<script>`, no `MD_B64`. The renderer is NOT re-implemented from scratch: the frame's own `renderMd` JS block (web .md lines 50 through the pre-IIFE line) is extracted and evaluated verbatim in the sandbox — fidelity by construction, plus a hand-traced KAT. Oracle per chapter: payload decode == master stripped (unchanged rule) before rendering.

## MASTER TASK LIST

- [ ] R1. Session open: this buffer created + pushed; atlas row 57 IN PROGRESS + pushed.
- [ ] R2. Banner fix: the 4 renumbered .md webs' `Chapter&nbsp;N` banner tokens corrected (13←14, 14←15, 15←16, 16←17); changed-line oracle (exactly one line per web; payload line byte-identical); pushed.
- [ ] R3. Plain .html built for all 16 chapters from the local webs: per chapter — decode oracle green → eval the frame's own renderer → render → write locally. Renderer KAT green.
- [ ] R4. All 16 pushed at the existing repo paths (replace); local mirrors = all 16 .html (dir 41 → 52 files); verified: no `<script`/`MD_B64` in any export, blob SHA-1 repo == local ×16, repo dir = exactly 52 names.
- [ ] R5. Conventions + close: project KNOWLEDGE (.html list + inventory + counts), atlas/publishing refs checked; row 57 → COMPLETE; buffer-fate question (user).

## STATUS LOG

1. **SESSION 57 OPEN (chunk A).** User request: "convert htmls to plain html, not encrypted." Frame anatomy verified: all 16 webs share the uniform frame (payload `var MD_B64` at line 49, script end line 136, 138 lines); the JS renderer is lines 50–pre-IIFE, pure functions, no DOM. Banner miss found + scope decisions taken (all 16, replace). NEXT: R2 — the banner fix.
