# Dopamine FX

**22 free effects for Webflow. One script, one attribute.**

Dopamine FX is a free, dependency-free JavaScript library of 22 visual effects for Webflow: WebGL mesh gradients, auroras, particle fields, a dot globe, text animations, magnetic buttons, custom cursors and more. You add one script to your site and put a `data-dfx` attribute on any element. No GSAP, no jQuery, no build step. The full bundle is about 14 KB gzipped.

Built and maintained by [Dopamine Studio](https://www.dopaminestudio.io), a Webflow Certified Partner studio in Rome.

**Live demos and copy-paste setup:** [dopaminestudio.io/free-webflow-effects](https://www.dopaminestudio.io/free-webflow-effects)

---

## Quick start

**1. Add the script.** In Webflow, go to *Site settings → Custom code → Footer code* (or *Page settings → Before `</body>` tag*), then paste:

```html
<script src="https://cdn.jsdelivr.net/gh/DopamineStd/dopamine-fx@1.1.0/dist/dopamine-fx.min.js" defer></script>
```

**2. Add the attribute.** Select an element in the Designer, open *Element settings → Custom attributes* and add:

| Name | Value |
|---|---|
| `data-dfx` | `mesh-gradient` |

**3. Publish.** Effects run on the published site and in preview. They don't run inside the Designer canvas.

### Load only what you use

Each effect also ships as its own file (1–4 KB). Use one of these instead of the full bundle:

```html
<script src="https://cdn.jsdelivr.net/gh/DopamineStd/dopamine-fx@1.1.0/dist/effects/aurora.min.js" defer></script>
```

### Customize with options

Every option is a `data-dfx-*` attribute on the same element:

```html
<div data-dfx="aurora" data-dfx-colors="#ff5fa2,#7aa2ff,#ffc061" data-dfx-speed="0.6"></div>
```

In Webflow, add each option as its own custom attribute (Name: `data-dfx-colors`, Value: `#ff5fa2,#7aa2ff,#ffc061`).

### Combine effects

`data-dfx` accepts a space-separated list:

```html
<div data-dfx="tilt spotlight">…</div>
```

---

## Effects

### Backgrounds

| Effect | `data-dfx` | What it does | Options (default) |
|---|---|---|---|
| Mesh Gradient | `mesh-gradient` | Animated WebGL gradient with four blending colors | `colors` (`#ff2e63,#ffb400,#5b2bff,#08d9d6`), `speed` (`1`), `warp` (`0.35`), `grain` (`0.05`) |
| Aurora | `aurora` | Soft WebGL northern-lights band | `colors` (`#3cffb4,#4d7cff,#c44dff`), `speed` (`1`), `intensity` (`0.9`), `position` (`0.62`), `blur` (`18`) |
| Lightfall | `lightfall` | Columns of light falling through the section (WebGL) | `colors` (`#ffffff,#7aa2ff`), `speed` (`1`), `columns` (`22`), `density` (`0.45`), `intensity` (`1`) |
| Particle Field | `particles` | Drifting particles linked by lines, reacting to the pointer | `color` (`#ffffff`), `density` (`1`), `link` (`120`), `mouse` (`repel` · `attract` · `none`), `speed` (`1`), `size` (`2`) |
| Wave Lines | `wave-lines` | Layered flowing lines that bend toward the pointer | `colors` (`#ff5fa2,#7aa2ff`), `lines` (`28`), `amplitude` (`1`), `speed` (`1`), `width` (`1`) |
| Dot Grid | `dot-grid` | Dot grid that lights up and pushes away around the pointer | `gap` (`22`), `size` (`1.4`), `color` (`rgba(255,255,255,.28)`), `accent` (`#ffffff`), `radius` (`140`), `push` (`10`) |
| Dot Globe | `globe` | Rotating, draggable dotted globe with location markers | `color` (`#ffffff`), `marker-color` (`#ff5fa2`), `markers` (`lat,lng;lat,lng…`), `dots` (`1100`), `speed` (`1`), `tilt` (`18`), `label` (`Rotating globe`) |
| Film Grain | `grain` | Animated film-grain overlay for a section or the whole page | `opacity` (`0.08`), `fps` (`12`), `scale` (`160`), `blend` (`overlay`), `z` (`50`) |

### Cards & images

| Effect | `data-dfx` | What it does | Options (default) |
|---|---|---|---|
| Spotlight Border | `spotlight` | Glow and border highlight that follow the pointer | `color` (`rgba(255,255,255,.10)`), `border-color` (`rgba(255,255,255,.75)`), `border` (`1`), `radius` (`320`), `reach` (`160`) |
| Border Beam | `border-beam` | A beam of light travelling around the element's border | `colors` (`#ffc061,#ff5fa2`), `duration` (`4`), `length` (`90`), `width` (`1.5`), `glow` (`6`, `0` to disable) |
| Tilt + Glare | `tilt` | 3D tilt toward the pointer with a light glare | `max` (`10`), `scale` (`1.03`), `glare` (`0.25`), `perspective` (`900`) |
| Ripple Image | `ripple-image` | WebGL liquid ripple with chromatic split on hover (on an `img` or its wrapper) | `strength` (`1`), `chroma` (`1`), `radius` (`0.45`) |
| Image Trail | `image-trail` | Images inside the element spawn along the pointer path | `distance` (`90`), `size` (`180px`), `life` (`0.9`), `rotate` (`8`) |
| Parallax | `parallax` | Scroll-linked movement | `speed` (`0.3`), `axis` (`y` · `x`), `zoom` (`0`) |

### Text

| Effect | `data-dfx` | What it does | Options (default) |
|---|---|---|---|
| Split Reveal | `split-reveal` | Words or characters slide up into view | `by` (`word` · `char`), `stagger` (`0.06` / `0.02`), `duration` (`0.9`), `delay` (`0`), `from` (`110%`), `trigger` (`view` · `load`) |
| Text Scramble | `text-scramble` | Text decodes from random characters | `trigger` (`view` · `hover` · `load`), `duration` (`1.2`), `chars` |
| Typewriter | `typewriter` | Types and deletes a list of words | `words` (comma-separated), `type-speed` (`70`), `delete-speed` (`35`), `hold` (`1.6`), `delay` (`0`), `loop` (`true`), `caret` (`true`) |
| Gooey Text | `gooey-text` | Words melt into each other | `words` (comma-separated), `morph` (`1`), `hold` (`2`) |
| Number Ticker | `number-ticker` | Counts up to the number in the element when it enters view. Keeps prefixes and suffixes (`€`, `+`, `%`) | `from` (`0`), `duration` (`2`), `delay` (`0`), `decimals`, `locale` (auto), `grouping` (`true`) |
| Infinite Marquee | `marquee` | Seamless looping ticker of the element's children | `speed` (`60`), `direction` (`left` · `right`), `gap` (`48px`), `pause` (`true`, on hover), `scroll` (`false`, react to scroll) |

### Interaction

| Effect | `data-dfx` | What it does | Options (default) |
|---|---|---|---|
| Custom Cursor | `cursor` | Custom cursor for the page (put it on `body`) or for a single section. Add `data-dfx-cursor-text="View"` to any element to show a label on hover | `color` (`#ffffff`), `size` (`36`), `text-color` (`#000`), `blend` (`normal`), `hide` (`false`, hide the native cursor) |
| Magnetic | `magnetic` | Buttons and links pull toward the pointer | `strength` (`0.35`), `area` (`60`), `inner` (`true`, move the inner content too) |

---

## Built for production

- **Zero dependencies.** Plain JavaScript. Nothing else to load.
- **Respects reduced motion.** With `prefers-reduced-motion: reduce`, effects stop animating or show their final state.
- **Pauses off-screen.** Canvas and WebGL effects stop rendering when out of view.
- **Touch-aware.** Pointer-only effects (cursor, magnetic) switch off on touch devices.
- **Safe to load twice.** Each effect initializes once per page and once per element.

### Dynamic content (CMS, Finsweet, tabs, modals)

For elements added after page load, re-run the scan for that effect:

```js
window.DopamineFX.typewriter();   // or any effect name, e.g. DopamineFX["split-reveal"]()
```

Elements that are already running are skipped.

---

## Browser support

Current versions of Chrome, Edge, Safari and Firefox. WebGL effects (`mesh-gradient`, `aurora`, `lightfall`, `ripple-image`) need WebGL. `border-beam` uses CSS `@property`.

## Versioning

Pin a version in the CDN URL (`@1.1.0`) so your site never changes without you. See [CHANGELOG.md](CHANGELOG.md) and [Releases](../../releases).

## License

Free to use in personal and commercial projects, including client sites. Don't resell or redistribute it as your own effects library. Full terms in [LICENSE](LICENSE).

---

Made by [Dopamine Studio](https://www.dopaminestudio.io), a Webflow, 3D and AI studio in Rome. Need something custom? [Talk to us](https://www.dopaminestudio.io).
