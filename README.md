# Michael Petrenko — Personal Brand Site

A one-page personal branding website built for **Business 1.2 — Marketing You**.
Plain HTML, CSS and JavaScript. No build step, no dependencies, no backend.

---

## Open it

Double-click **`index.html`**. That's it — it opens in any browser.

If you want it to behave exactly like a real hosted site (useful once you add a
video), run a tiny local server from this folder instead:

```
python3 -m http.server 8000
```

then open `http://localhost:8000` in your browser.

---

## Replace the two placeholders

### 1. Your photo

1. Save your photo into the `assets` folder as **`michael.jpg`**
   (portrait orientation, roughly 1000 × 1250 px works best).
2. Open `index.html` and search for `REPLACE #1`.
3. Delete the whole `<div class="photo__placeholder">` … `</div>` block.
4. On the line just above it, delete `<!--` from the start and `-->` from the end
   so the `<img>` tag becomes real code.

Before:

```html
<!-- <img src="assets/michael.jpg" alt="Michael Petrenko" width="1000" height="1250"> -->
```

After:

```html
<img src="assets/michael.jpg" alt="Michael Petrenko" width="1000" height="1250">
```

### 2. Your elevator pitch video

1. Save your video into the `assets` folder as **`pitch.mp4`**
   (landscape 16:9, about 30–45 seconds).
2. *Optional:* save a still frame as `assets/pitch-poster.jpg` — this is the image
   shown before someone presses play.
3. Open `index.html` and search for `REPLACE #2`.
4. Delete the whole `<div class="video__placeholder">` … `</div>` block.
5. Delete the `<!--` and `-->` around the `<video>` block above it.

If you don't add a poster image, delete `poster="assets/pitch-poster.jpg"` from the
`<video>` tag, otherwise the browser looks for a file that isn't there.

---

## Which file do I edit?

| I want to change… | Open this file | Look for |
|---|---|---|
| Any wording on the page | `index.html` | The section is labelled in a big comment block, e.g. `SECTION 3 — WHAT MAKES ME DIFFERENT` |
| Colours (including the electric blue) | `css/styles.css` | The `:root { }` block at the very top |
| Fonts | `css/styles.css` | `--font-display`, `--font-body`, `--font-mono` in `:root` |
| Text sizes | `css/styles.css` | `--step--1` through `--step-4` in `:root` |
| Spacing / section height | `css/styles.css` | `--gutter`, `--sp-1`…`--sp-6`, `--section-y` in `:root` |
| Corner rounding | `css/styles.css` | `--radius`, `--radius-s` |
| Animations and scroll behaviour | `js/main.js` | Numbered comment blocks 1–6 |
| The page title in the browser tab | `index.html` | `<title>` near the top |

**Almost every visual decision comes from the `:root` block in `css/styles.css`.**
Change `--accent` there and the entire site changes accent colour at once.

---

## Files

```
michael-petrenko-site/
├── index.html          ← all the text and page structure
├── css/
│   └── styles.css      ← all styling; design settings live in :root at the top
├── js/
│   └── main.js         ← scroll animations, nav highlighting, mobile menu
├── assets/             ← put michael.jpg and pitch.mp4 here
│   └── README.txt
└── README.md           ← this file
```

---

## How the site covers the assignment

| Marketing concept | Where it shows up |
|---|---|
| **Selling** | Hero, the three pillars, and the closing section all argue why someone should choose or remember you |
| **Promotion** | The whole site is the promotional material — shareable link, clear brand, memorable closing line |
| **Value proposition** | Stated word-for-word in the "What Makes Me Different?" section and labelled *My value proposition* |
| **Competitive advantage** | The CREATE / BUILD / PERFORM pillars plus the IDEA → BUILD → COMMUNICATE process rail |
| **Target audience** | Written for a teacher, an employer, a collaborator and a problem-solver; named directly above the closing headline |
| **Elevator pitch structure** | Each line of the written pitch is labelled: Hook, Solution, Value, Difference, Resilience, Call to action |
| **Name design** | The MICHAEL wordmark, with the "I" replaced by an electric-blue bar |
| **Personal logo** | The MP monogram in an incomplete square, drawn as SVG so it stays sharp at any size |

---

## Built-in details worth knowing

- **Responsive** — tested at 1440px, 1180px, 834px and 390px wide. The navigation
  collapses to a menu button below 820px.
- **Keyboard accessible** — every link and button has a visible blue focus ring, and
  there's a "Skip to content" link for screen readers.
- **Respects `prefers-reduced-motion`** — if someone has motion turned off in their
  system settings, all animation is disabled and everything shows instantly.
- **Works without JavaScript** — the full text still renders if `main.js` fails.
- **Prints cleanly** — Ctrl/Cmd+P gives a readable paper version with the navigation
  and buttons stripped out.
- **Fonts** load from Google Fonts (Archivo, Manrope, JetBrains Mono). If you present
  somewhere without Wi-Fi, the site still works — it falls back to Helvetica/Arial.
