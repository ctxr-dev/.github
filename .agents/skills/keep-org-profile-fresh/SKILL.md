---
name: keep-org-profile-fresh
description: How to maintain the Contexter org profile (this repo). Use when editing profile/README.md, the animated SVGs, the stats line, the package tables, the badges, or the committed design language. Enforces brand rules (Contexter as the human name, ctxr-dev only as a URL slug), the dark-futurist palette, and the no-(default), no-new-emoji conventions.
---

# keep-org-profile-fresh

This repo (`ctxr-dev/.github`) backs the org landing at <https://github.com/ctxr-dev>. Local clone lives in a folder named `start/` (kept after a rename), remote `origin` points at `https://github.com/ctxr-dev/.github.git`. Treat this file as the maintenance manual.

## What lives where

| Path | Purpose |
| --- | --- |
| `README.md` | 5-line pointer for anyone landing on the repo page directly |
| `profile/README.md` | **The org landing.** GitHub renders this at github.com/ctxr-dev |
| `profile/assets/hero.svg` | Animated hero: 12-node constellation + typing terminal + sparkles |
| `profile/assets/footer.svg` | Slim animated signal trail under the contribute block |
| `.agents/skills/keep-org-profile-fresh/SKILL.md` | This file |
| `AGENTS.md` | Pointer that loads this skill for any AI agent working here |

Edits to `profile/README.md` propagate to the org page on the next page load. GitHub's camo proxy caches SVGs aggressively; force-reload with `?v=N` or hard refresh to bust the cache after pushing.

## Brand rules (these are not preferences)

1. **Project human name is `Contexter`.** Use it for prose, hero copy, headings, alt text, and the rendered SVG wordmark. Never use `ctxr-dev` as a brand name.
2. **`ctxr-dev` is the URL slug.** It appears only in `github.com/ctxr-dev/...`, `ctxr-dev/<repo>` GitHub paths, `raw.githubusercontent.com/ctxr-dev/...`, and similar identifiers. Anywhere a reader would naturally read it as "the project name", say Contexter.
3. **`@ctxr` is the npm scope.** It stays as-is inside install commands and badges.
4. **No 🆕 emoji** (or any "NEW" badge) to call out recently shipped items. Mention novelty in surrounding prose if needed.
5. **No `(default)` inline.** Lift the marker to its own line as `<br/><sub>recommended</sub>` (or whatever the marker is). Same rule for any inline parenthetical annotation.
6. **No em or en dashes** in copy. Use commas, colons, parentheses, or line breaks.

When you violate any of these, the user will catch it. Self-check before pushing.

## Design language (committed lane)

Lane: **neo-noir cyberpunk**. Reference: the Cyberpunk 2077 *Used To Live Here* still (dominant teal-cyan bar-interior glow with warm gold signage and muted magenta wall accents on deep teal-black). Drops the arcade-neon violet/cyan story; this is cinematic, not glitchy. See `references/design.md` in `@ctxr/skill-frontend-excellence` for the underlying playbook.

### Palette (semantic tokens)

| Token | Hex | Role |
| --- | --- | --- |
| bg            | `#0B1F23` | Dominant background, badge `labelColor`, eyebrow chip text on gold |
| teal-bright   | `#3DBE9C` | Brand signal: HUD rules, scan beam, MIT badge, terminal `$`, cursor, bridge packet |
| teal-dim      | `#1A6E64` | Static circuit traces |
| gold          | `#E5C547` | Brand primary: HUD brackets, key nodes, npm/GitHub badges, energy packets, wordmark halo, eyebrow chip background, `@ctxr/` in terminal |
| gold-dim      | `#C19A4A` | Dim node bodies and small-node fills |
| magenta       | `#A05080` | Accent nodes, MCP-native badge, footer packet, cluster halos |
| cream         | `#F0E8D5` | Wordmark, primary terminal text |
| cream-muted   | `#94A99A` | Subtitle, Cursor badge text |
| meta-teal     | `#5A8F86` | Top-right meta tag, footer caption |
| stats-muted   | `#7A8A82` | Stats line, terminal `install ` flag |
| scanline      | `#3DBE9C @ 5.5%` | CRT scanlines pattern |

### Typography

One family across the whole profile: `ui-monospace, SFMono-Regular, "JetBrains Mono", Menlo, Consolas, monospace`. Do not introduce a second family.

| Element | Size | Weight | Tracking |
| --- | --- | --- | --- |
| Title wordmark | 80px | 700 | -0.05em |
| Subtitle (uppercase) | 13.5px | 500 | 0.32em |
| Terminal | 14px | 400 | 0.02em |
| Stats (uppercase) | 11px | 400 | 0.26em |
| Eyebrow / meta | 9.5px | 400 | 0.24em / 0.20em |

### Motion

| Motion | Mechanism | Cadence |
| --- | --- | --- |
| Node pulse | CSS `@keyframes nodePulse` | 3.4s ease-in-out, staggered 0.28s per node |
| Edge messages (short) | SMIL `<animateMotion>` | 2.0-2.6s |
| Edge messages (long amber bridges) | SMIL `<animateMotion>` | 4.8s |
| Sparkles | SMIL `<animate attributeName="opacity">` | 2.2-2.6s, staggered |
| Terminal typing | SMIL `<animate attributeName="width">` on clipPath rect | 15s loop, 5 phrases × 3s each |
| Terminal cursor x | SMIL `<animate attributeName="x">` | 15s loop, synchronized with typing |
| Terminal cursor blink | SMIL `<animate attributeName="opacity" calcMode="discrete">` | 1s on/off |

`@media (prefers-reduced-motion: reduce)` disables CSS animations inside the SVGs. SMIL remains (small, continuous, not vestibularly aggressive).

### What NOT to do

- Purple-to-pink linear gradients (the AI cliche).
- Violet primary on midnight (the previous arcade-neon iteration) — the committed lane is teal-cyan + warm gold, not violet.
- Chromatic-aberration RGB-split on the wordmark or glitch bursts that intensify ghost text. The lane is cinematic neo-noir, not arcade-glitchy.
- `capsule-render` headers or `readme-typing-svg` banners (we have the bespoke hero instead).
- Stock badge colors that fight the palette. Repalette to gold/teal/magenta on `labelColor=0B1F23`.
- Diagonal constellation edges. The hero network is ORTHOGONAL only (horizontal + vertical segments forming circuit-board traces); one bridge routes up over the title via 90-degree corners.
- Circular nodes. The hero uses small filled squares (`<rect>`) with one or two larger key squares per cluster; an inner dark micro-square inside the key node reads as a status indicator.
- Centered-everything monotony. The hero is asymmetric: clusters on both sides of the wordmark, eyebrow chip top-left, meta tag top-right, stats line below the typing terminal.
- More than one type family. More than 4 weights.
- Inline `<svg>` in markdown (GitHub sanitises it). Always serve hosted SVGs via `<img src="https://raw.githubusercontent.com/...">`.

## Updating the hero

The hero SVG (`profile/assets/hero.svg`) is the most decorated artefact in this repo. Touch it carefully.

### Adding a new typing-loop phrase

The terminal cycles through 5 install commands in a 15-second SMIL loop. To add a 6th:

1. Decide the phrase. Measure char count, multiply by ~8.4 to get target `textLength` in px (14px monospace).
2. Add a new `<clipPath id="typeP6">` in `<defs>` with an `<animate attributeName="width">` whose `keyTimes` and `values` follow the existing 6-keyframe pattern. Each slot is now 15/6 = 2.5s.
3. **Recompute every existing phrase's keyTimes** so the 6 slots tile evenly. The current 5-slot keyTimes assume `slot_n = n / 5`.
4. Add the `<g clip-path="url(#typeP6)">` text element after the others.
5. Extend the cursor `<animate attributeName="x">` `values` and `keyTimes` arrays with the new slot's 5 keyframes (start, end-of-type, end-of-hold, end-of-erase, gap).
6. Verify with `xmllint --noout profile/assets/hero.svg`.

Loop layout per phrase, expressed as fraction of `dur`:

| Fraction | Event |
| --- | --- |
| `slot_start` | width 0, cursor at prefix end |
| `slot_start + 0.4 × slot_dur` | width fully revealed, cursor at end of typed text |
| `slot_start + 0.733 × slot_dur` | hold completes |
| `slot_start + 0.933 × slot_dur` | erase completes, width back to 0 |
| `slot_end` | gap |

### Updating the stats line

`13 PACKAGES · 4 AGENTS · 3 SKILLS · 2 MEMORY BACKENDS · MIT`

Count packages from the README tables (installer 1 + skills 3 + agents 4 + MCP 1 + methodology 1 + libraries 1 + memory 2 = 13). Update both the SVG `<text class="stats">` and any prose elsewhere that cites a count when this changes.

### Updating the wordmark

Always `Contexter`. If you change the font-size, re-position the two outer title-flank sparkles (currently at x=478 and x=922 in a 1400-wide viewBox) so they don't collide with the new wordmark width.

## Updating profile/README.md

### Adding a new package row

The README tables follow this pattern (Installer / Skills / Agents / MCP / Methodology / Libraries):

```markdown
| [`@ctxr/<name>`](https://github.com/ctxr-dev/<name>) | one-line "use it to" | [![npm](https://img.shields.io/npm/v/@ctxr/<name>?style=flat-square&logo=npm&label=)](https://www.npmjs.com/package/@ctxr/<name>) [![stars](https://img.shields.io/github/stars/ctxr-dev/<name>?style=flat-square&label=%E2%98%85)](https://github.com/ctxr-dev/<name>) |
```

When you add a row:

1. Insert in the right type-of-thing table. Do not create a 7th category without discussion.
2. Update the mermaid diagram with the new node.
3. Update the stats line in `hero.svg` if the totals change.
4. If it's a skill or agent, consider whether it belongs in any starter stack and update those tables accordingly.

### Mermaid theme

The mermaid block in `profile/README.md` uses an `%%{init: ...}%%` directive with these tokens: `background:#0B1F23, primaryColor:#102E32, primaryTextColor:#F0E8D5, primaryBorderColor:#E5C547, secondaryColor:#163A3D, tertiaryColor:#0A1E22, lineColor:#3DBE9C, clusterBkg:#0A1E22, clusterBorder:#1A3A3A`. Keep these in lockstep with the SVG palette if you adjust either.

### Memory column

The Wiki vs RAG table uses `<th align="center">📒 Wiki<br/><sub>recommended</sub></th>`. The `recommended` lives on its own line; never inline as `(recommended)` or `(default)`.

## Validation before pushing

Run these checks from `start/`:

```bash
# 1. SVG XML well-formedness
xmllint --noout profile/assets/hero.svg profile/assets/footer.svg

# 2. Brand-rule checks (each should print nothing)
grep -nE '🆕'          profile/README.md README.md
grep -nF '(default)'  profile/README.md README.md
grep -nE '\b(ctxr-dev)\b' profile/README.md README.md \
  | grep -vE 'github\.com/ctxr-dev|raw\.githubusercontent\.com/ctxr-dev|ctxr-dev/[a-z]'

# 3. No em/en dash sneaking in
grep -nP '[\x{2013}\x{2014}]' profile/README.md README.md profile/assets/*.svg
```

If any output appears, fix before committing.

## Push and verify

```bash
git add -A
git commit -m "docs(profile): <one-line description>"
git push  # origin → ctxr-dev/.github
```

After push, verify:

```bash
# raw SVG is served as image/svg+xml (camo gets it next)
curl -sI https://raw.githubusercontent.com/ctxr-dev/.github/main/profile/assets/hero.svg \
  | grep -iE 'content-type|cache-control'

# org page is live
open https://github.com/ctxr-dev
```

GitHub camo caches images for ~5 minutes. To force a refresh in a viewer, hard-reload (Cmd+Shift+R).

## When in doubt

Open a saved decision in the shared knowledge store (Dify), keyword `ctxr-dev-org-profile-and-design-language`. That record holds the canonical palette, motion vocabulary, brand rules, and the GitHub-rendering constraints discovered the hard way. If you find yourself adding a new constraint, save it back to that record (upsert by name).
