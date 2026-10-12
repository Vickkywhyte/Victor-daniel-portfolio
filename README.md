# Victor Daniel — Personal AI Portfolio · v2 (Sky-Blue Edition, with Motion)

A static portfolio site for **Victor Adegbe Daniel**, Generative AI Engineer.
Sky blue / white / black palette with a full motion layer.

---

## Motion features in this version

| | What it does |
|---|---|
| **Scroll progress bar** | Sky-blue gradient bar at the very top tracks scroll position |
| **Hero h1 reveal** | Each line of "Reliable / AI systems / for high-stakes / domains." slides up from below with staggered timing |
| **Section title word cascade** | Every section title splits into words, each fading up with a 60ms stagger |
| **Section label rule** | The accent underline grows from 0 to 64px when the section enters view |
| **Animated stat counters** | "10 shipped systems · 35% time cut · 5+ years · 100% checklist" count up from 0 |
| **Portrait floating** | After entry, the portrait gently floats up-and-down on a 7s loop |
| **Portrait 3D tilt** | Hovering the portrait tilts it in 3D space following your cursor |
| **Hero parallax** | The architectural grid background drifts as you move your mouse and scroll |
| **Custom cursor follower** | Sky-blue dot + ring, with the ring expanding on interactive elements (desktop only) |
| **Button shine sweep** | A diagonal shine sweeps across primary/secondary buttons on hover |
| **Nav underline** | Animated `scaleX` underline grows from left on hover |
| **Project row sweep** | A sky-blue underline grows across project rows on hover; the numeral slides right; the whole row washes pale blue |
| **Pill bounce** | Tech-stack pills lift and scale on hover |
| **Principle card lift** | Deployment standards cards translate up and the italic numeral scales when hovered |
| **Failure mode chevron** | Rows in the failure-mode table indent right on hover; row name shifts to sky-deep |
| **Contact list arrow** | Email/LinkedIn/phone slide slightly left on hover |
| **Scroll cue** | "Scroll" indicator at hero bottom with a pulsing line, fades in after 1.6s |
| **Reduced motion respected** | Everything above is disabled if user has `prefers-reduced-motion: reduce` |

All motion is CSS-driven where possible, with vanilla JS for orchestration (no
frameworks). The IntersectionObserver pattern ensures motion only runs when
visible. Cursor follower disabled on touch devices.

---

## Deploy to Vercel (3 ways)

### Option A — Drag and drop (fastest, no Git)
1. Go to https://vercel.com/new
2. Click **"Browse" → Upload this folder**
3. Click **Deploy**. Done.

### Option B — Vercel CLI
```bash
npm i -g vercel
cd portfolio-v2
vercel        # follow the prompts
vercel --prod # for production
```

### Option C — Git
1. Push this folder to GitHub
2. Import the repo at https://vercel.com/new
3. Framework preset: **Other**
4. Deploy

---

## File structure

```
portfolio-v2/
├── index.html       # the whole site, including all motion logic
├── victor.jpg       # portrait (800×800, ~110KB)
├── vercel.json      # Vercel config — caching + security headers
└── README.md
```

---

## Customise

- **Photo** — replace `victor.jpg` with any 800×800 square JPG
- **Sky blue tone** — change `--sky: #4ba3e8;` at the top of the `<style>` block
- **Disable motion** — find `/* === reduced motion override ===` and remove the media query wrapper to apply it to everyone (or just let users with `prefers-reduced-motion` get the static version automatically)
- **Cursor follower** — search for `cursor-dot` / `cursor-ring` and delete the markup + matching JS section to remove
- **LinkedIn** — already wired in (https://www.linkedin.com/in/victor-daniel-cfcs-453983191/)

---

## Tech notes

- **No framework, no build step.** Pure HTML/CSS/JS, ~50KB single file.
- **Fonts** — Fraunces serif, Inter sans, JetBrains Mono (all Google Fonts).
- **Performance** — `will-change` on animated elements, `requestAnimationFrame` for scroll handlers, `IntersectionObserver` to lazy-trigger motion.
- **Accessibility** — semantic HTML, alt text, sufficient contrast, full `prefers-reduced-motion` support.

Built reliable. Designed to fail safely.
