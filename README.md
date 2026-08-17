# GenLayer Portal Spinner

A community-submitted loading spinner for the GenLayer Portal — one self-contained
SVG file, animated with CSS, no dependencies.

Open `preview.html` in a browser to see it live on light/dark backgrounds at
several sizes.

## Concept

GenLayer's own brand language talks about a **static core** ("a static system
variable... uncompromised and isolated") surrounded by **autonomous, kinetic
action**. That's almost literally what a validator network does: independent
nodes moving around a fixed point of adjudication until they converge.

The spinner turns that into motion:

- **Three diamond nodes** orbit a shared center, each briefly brightening in
  turn as it passes — like signals moving between validators toward consensus.
- **One static core diamond** sits at the center and breathes gently (scale +
  glow), standing in for the fixed "adjudication" point everything resolves to.
- No wheel-of-dashes, no generic ring — the diamond motif echoes the angular,
  "stripped of visual noise" geometry described in GenLayer's brand guide,
  while staying simple enough to read at 16px.

## What's in this folder

| File | Purpose |
|---|---|
| `genlayer-spinner.svg` | The deliverable. Single file, inline `<style>`, infinite loop. |
| `preview.html` | Visual QA: the spinner at 16–80px on light and dark backgrounds. Open it directly in a browser. |
| `README.md` | This file. |

## Using it

**As an image** (simplest, good for static loading pages):

```html
<img src="genlayer-spinner.svg" width="32" height="32" alt="Loading">
```

**Inlined** (recommended inside the Portal app — lets you theme the color per
context):

```jsx
// paste the contents of genlayer-spinner.svg directly into your component
<svg viewBox="0 0 100 100" style={{ color: '#110FFF', width: 32, height: 32 }}>
  ...
</svg>
```

Color comes entirely from `currentColor`, driven by the `color` style on the
root `<svg>`. Default is **Kinetic Cobalt `#110FFF`** (GenLayer's primary
brand color) for light surfaces. On near-black surfaces (`Carbon Void
#070707`), swap in a lighter tint — `#4C6FFF` reads clearly and still sits
firmly in the brand's cobalt family. `preview.html` demonstrates both.

## Requirements checklist

- ✅ **Original animated spinner**, web-ready format (SVG + CSS animation,
  no external libraries or fonts).
- ✅ **Smooth infinite loop** — pure CSS `@keyframes`, GPU-friendly
  (`transform`/`opacity` only), no JS needed to run.
- ✅ **Works on light and dark backgrounds** — color is `currentColor`-driven,
  not baked in; see `preview.html`.
- ✅ **Readable at small sizes** — tested down to 16px; the shape is three
  diamonds + one diamond core, nothing finer than that.
- ✅ **GenLayer identity present** — uses the official Kinetic Cobalt
  (`#110FFF`), the diamond/angular motif from the brand's geometric mark, and
  a motion concept (nodes converging on a fixed core) drawn directly from
  GenLayer's own "autonomous core" positioning.
- Bonus: respects `prefers-reduced-motion` by slowing (not killing) the loop,
  and includes `role="status"` / `aria-label="Loading"` for screen readers.

## License

Submitted for GenLayer's use in the Portal — free to use, modify, and ship
under whatever license the GenLayer repo uses (MIT/CC0 recommended if none is
specified).
