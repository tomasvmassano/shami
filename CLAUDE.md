# Shami

A single-file HTML web app for learning Syrian Levantine Arabic. The entire app lives in `index.html` — HTML, CSS, and JS all inline. Self-contained by design.

Deployed to GitHub Pages at https://tomasvmassano.github.io/shami/.

## Working on this repo

- Edit `index.html` directly. Don't split into multiple files.
- Don't refactor into modules, build steps, or external assets unless explicitly asked.
- The "one self-contained HTML" constraint is the point. Treat it as a hard rule.

## Deployment workflow

1. Make changes to `index.html`.
2. Commit with a clear message describing the change.
3. Push to `origin main` — GitHub Pages auto-deploys from the main branch.

No build, no CI, no preview environment. Pushed = live within ~1 minute.

## Design conventions

**Aesthetic:** terracotta on paper. Warm, hand-pressed, slightly imperfect. Brutalist typography offset against soft tones.

**Color tokens** (CSS custom properties on `:root`):
- `--ink` `#1a1410` — near-black text and borders
- `--paper` `#f4ede0` — primary background
- `--paper-dim` `#ebe2d2` — secondary surface
- `--terra` `#c1532b` — primary accent (terracotta)
- `--terra-deep` `#8a3818` — darker terracotta
- `--ochre` `#d4a24a` — warm yellow accent
- `--olive` `#5b6f3a` — green accent (correct/good states)
- `--plum` `#54243a` — deep purple accent

A subtle SVG paper grain overlay (`body::before`) sits over everything with `mix-blend-mode: multiply`. Don't remove it.

**Fonts** (loaded from Google Fonts):
- `Fraunces` — body and display (serif, variable). Default font.
- `JetBrains Mono` — monospace UI labels, stats, code-like text. Class: `.mono`.
- `Amiri` — Arabic script, RTL. Class: `.arabic`.

**Brutalist offset shadows:** the signature visual element. Hard-edged, no blur, offset toward bottom-right. Pattern: `box-shadow: Npx Npx 0 var(--color);` where N is typically 3–12px. Cards usually use `--ink`; accents use `--terra`, `--ochre`, `--olive`, or `--plum`. On hover, shadows often grow and the element translates by the same offset (e.g. `transform: translate(-3px, -3px)` paired with a larger shadow).

**Borders:** solid 2–3px `var(--ink)` — sharp, no border-radius unless intentional.

## Copy style

- **No em dashes (—) in user-facing copy.** Use commas, periods, parens, or rewrite. Em dashes are fine in this CLAUDE.md and other dev-facing notes, just not in the app itself.
- Tone: warm, direct, lightly playful. Not corporate, not chatty.
- Arabic always inside `<span class="arabic">` so it renders Amiri RTL.
