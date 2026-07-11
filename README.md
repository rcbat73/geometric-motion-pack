# Orbital Harmonic Loader — Geometric Motion Pack

A compact, customizable CSS/Sass animation pack that contains a set of geometric motion components. This package includes the "Orbital Harmonic" loader — three concentric orbital rings with glowing markers — plus build tooling and demos.

## Quick install

- Clone or include this repo in your project.
- Install dependencies and build the CSS:

```bash
npm install
npm run build   # compile scss/motionforge.scss -> css/motionforge.css
# or during development
npm run watch   # watch and recompile when SCSS changes
```

## Project structure

- `scss/` — source Sass partials and main entry (`scss/motionforge.scss`)
- `scss/loaders/` — loader implementations (including `_orbital-harmonic.scss`)
- `css/` — compiled stylesheet(s) (e.g. `css/motionforge.css`)
- `demos/` — example HTML pages
- `docs/` — documentation and usage notes

## Usage

Include the compiled CSS and add the component markup:

```html
<link rel="stylesheet" href="css/motionforge.css" />
<div class="orbital-harmonic"></div>
```

## Customization (runtime)

The component exposes a set of CSS custom properties you can override at runtime (no rebuild required). Example:

```html
<div
  class="orbital-harmonic"
  style="
	--oh-outer-color:#ff6b6b;
	--oh-outer-dot-duration:3s;
	--oh-outer-glow-1: rgba(255,107,107,0.45);
	--oh-outer-glow-2: rgba(255,107,107,0.18);
"
></div>
```

You can also make themed classes:

```css
.orbital-theme-warm {
  --oh-inner-color: #1ee7ac;
  --oh-middle-color: #ffd166;
  --oh-outer-color: #ff6b6b;
  --oh-inner-duration: 3s;
}
```

## Customization (source)

For structural changes or to change defaults, edit the Sass source `scss/loaders/_orbital-harmonic.scss` and rebuild. Key Sass variables:

- `$oh-wrapper-size` — overall component size
- `$oh-marker-size` — diameter of the orbiting dots
- `$oh-*-scale` — relative radius per ring
- `$oh-ring-border` — ring stroke thickness
- `$oh-*-duration` and `$oh-*-dot-duration` — default durations

Build after edits:

```bash
npm run build
```

## Exposed CSS properties (runtime overrides)

- `--oh-inner-color`, `--oh-middle-color`, `--oh-outer-color` — ring & dot colors
- `--oh-inner-duration`, `--oh-middle-duration`, `--oh-outer-duration` — ring spin durations
- `--oh-inner-dot-duration`, `--oh-middle-dot-duration`, `--oh-outer-dot-duration` — dot orbit durations
- `--oh-*-glow-1`, `--oh-*-glow-2` — ring glow RGBA layers
- `--oh-*-dot-glow` — dot glow color/opacity

## Files to inspect

- `scss/loaders/_orbital-harmonic.scss` — source defaults and geometry
- `scss/motionforge.scss` — main SCSS entry
- `css/motionforge.css` — compiled CSS
- `demos/index.html` — live demo

## Distribution notes

- Include a license appropriate for your sales model (MIT for permissive, or a custom commercial license).
- For distribution, include the compiled `css/motionforge.css` and `demos/` for previews.

## Next steps

I can add a `docs/themes.md` with preset theme classes and a `demos/demo-themes.html` preview for buyers — would you like that?
