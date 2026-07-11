# Orbital Harmonic — Usage & Variable Reference

This document explains how to use and customize the Orbital Harmonic loader.

1. Quick markup

---

Include the compiled CSS, then add the component:

```html
<link rel="stylesheet" href="css/motionforge.css" />
<div class="orbital-harmonic"></div>
```

### Ember Ring — Quick markup

```html
<link rel="stylesheet" href="css/motionforge.css" />
<div class="ember-ring">
  <span></span>
  <span></span>
  <span></span>
  <span></span>
  <span></span>
</div>
```

### Dr Strange Ring — Quick markup

```html
<link rel="stylesheet" href="css/motionforge.css" />
<div class="particle-container dr-strange-preview">
  <div class="dr-strange-ring" data-total-particles="80"></div>
</div>
```

2. Runtime customization (recommended for themes)

---

Override CSS custom properties on the component or on ancestor selectors.

Examples:

- Inline override (fast):

```html
<div
  class="orbital-harmonic"
  style="--oh-outer-color:#ff6b6b; --oh-outer-dot-duration:3s;
  --oh-outer-glow-1: rgba(255,107,107,0.45); --oh-outer-glow-2: rgba(255,107,107,0.18);"
></div>
```

- Theme class (reusable):

```css
.orbital-theme-neon {
  --oh-inner-color: #1ee7ac;
  --oh-middle-color: #ffd166;
  --oh-outer-color: #ff6b6b;
  --oh-inner-duration: 3s;
  --oh-inner-dot-duration: 2s;
}
```

3. Source defaults (Sass)

---

Edit `scss/loaders/_orbital-harmonic.scss` for defaults and geometry. Useful for:

- Changing default colors used when no CSS variables are set
- Changing ring sizes, marker size, or stroke thickness
- Changing keyframe definitions (e.g. ease or turn counts)

Key source variables (Sass):

- `$oh-wrapper-size` — overall component width/height
- `$oh-ring-border` — ring stroke thickness
- `$oh-marker-size` — diameter of the orbiting dots
- `$oh-inner-scale`, `$oh-middle-scale`, `$oh-outer-scale` — per-ring scale factors
- `$oh-inner-duration`, `$oh-middle-duration`, `$oh-outer-duration` — default spin durations
- `$oh-inner-dot-duration`, `$oh-middle-dot-duration`, `$oh-outer-dot-duration` — default dot orbit durations
- `$oh-dot-offset` — extra offset for the dot relative to ring stroke

4. CSS custom properties (runtime overrides)

---

- `--oh-inner-color`, `--oh-middle-color`, `--oh-outer-color`
- `--oh-inner-duration`, `--oh-middle-duration`, `--oh-outer-duration`
- `--oh-inner-dot-duration`, `--oh-middle-dot-duration`, `--oh-outer-dot-duration`
- `--oh-inner-glow-1`, `--oh-inner-glow-2`
- `--oh-middle-glow-1`, `--oh-middle-glow-2`
- `--oh-outer-glow-1`, `--oh-outer-glow-2`
- `--oh-inner-dot-glow`, `--oh-middle-dot-glow`, `--oh-outer-dot-glow`

## Dr Strange Ring — Runtime customization

Override the Dr Strange ring color and radius on the `.dr-strange-ring` element or an ancestor.

Example:

```html
<div class="particle-container dr-strange-preview">
  <div
    class="dr-strange-ring"
    style="--ds-ring-color:#4fd1c5; --ds-ring-radius:100px; --ds-ring-glow:rgba(79,209,197,0.8);"
  >
    <!-- particles -->
  </div>
</div>
```

Supported CSS properties:

- `--ds-ring-color` — main ring particle color
- `--ds-ring-radius` — radius of the ring in px
- `--ds-ring-glow` — particle glow color

5. Theming recipes (examples)

---

- Fast subtle theme:

```css
.orbital-subtle {
  --oh-inner-color: #9ad1ff;
  --oh-middle-color: #cbb4ff;
  --oh-outer-color: #ffb0c0;
  --oh-inner-duration: 5s;
  --oh-outer-dot-duration: 8s;
  --oh-outer-glow-1: rgba(255, 176, 192, 0.12);
  --oh-outer-glow-2: rgba(255, 176, 192, 0.06);
}
```

6. Build & test

---

- `npm run build` — compile once
- `npm run watch` — continuous compile during development
- Open `demos/index.html` in a browser to preview

7. Distribution tips

---

- Ship the compiled `css/motionforge.css` along with `demos/` as previews for customers.
- Consider adding an example `themes.css` file containing a few themed classes to speed integration.

## Contact / Support

If you want me to add a `docs/themes.md` and `demos/demo-themes.html` showing theme switching and prebuilt classes, say "yes" and I will add them.

## Platform integration (no-Sass / quick-start)

These examples assume you include the compiled stylesheet `css/motionforge.css` in your project and override CSS custom properties to theme the loader — no Sass required.

## React

1. Copy `css/motionforge.css` into your React `public` folder or import it from your build output.
2. Use the component in JSX and pass a `style` prop to override CSS variables:

```jsx
// src/components/OrbitalLoader.jsx
import React from "react";
import "/public/css/motionforge.css"; // or import '../css/motionforge.css' depending on bundler

export default function OrbitalLoader({ className = "", style = {} }) {
  return (
    <div
      className={`orbital-harmonic ${className}`}
      style={{
        "--oh-outer-color": "#ff6b6b",
        "--oh-outer-dot-duration": "3s",
        ...style,
      }}
      aria-label="Orbital harmonic loader"
    >
      <div className="ring ring--inner" />
      <div className="ring ring--middle" />
      <div className="ring ring--outer" />
    </div>
  );
}
```

## Tailwind (utility-based projects)

Tailwind projects can still use the compiled CSS. To theme via Tailwind utilities, add a helper class that sets CSS variables and apply it alongside `orbital-harmonic`.

```css
/* in your globals.css (imported by Tailwind) */
.orbital-theme-accent {
  --oh-inner-color: #60a5fa;
  --oh-middle-color: #7c3aed;
  --oh-outer-color: #fb7185;
  --oh-outer-dot-duration: 4s;
}
```

Usage in markup:

```html
<div class="orbital-harmonic orbital-theme-accent"></div>
```

## Webflow (no code)

1. Upload `css/motionforge.css` to your site settings (Custom Code → Head) or host it and add a link in the Page Settings → Head Code.
2. Add an HTML Embed block where you want the loader and paste:

```html
<div class="orbital-harmonic orbital-theme-accent"></div>
```

3. Add custom CSS variables in the Page Settings → Head Code or in the Embed with a `<style>` tag to theme.

## WordPress (theme or plugin)

- Enqueue the compiled CSS in your theme's `functions.php` or a plugin:

```php
function enqueue_motionforge() {
  wp_enqueue_style('motionforge', get_template_directory_uri() . '/css/motionforge.css', array(), '1.0');
}
add_action('wp_enqueue_scripts', 'enqueue_motionforge');
```

- Use the markup in posts/pages via the block editor (HTML block) or theme templates:

```html
<div class="orbital-harmonic"></div>
```

- To provide theme options, expose CSS variable values via the Customizer or block attributes and output them inline.

## Shopify (theme)

1. Upload `css/motionforge.css` to your theme assets (Admin → Online Store → Themes → Edit code → Assets).
2. Include it in your theme layout (e.g., `layout/theme.liquid`):

```liquid
<link href="{{ 'motionforge.css' | asset_url }}" rel="stylesheet" />
```

3. Place the component markup in a section/snippet or via the HTML editor:

```liquid
<div class="orbital-harmonic"></div>
```

4. For store-level theming, add theme settings that output CSS variables to `theme.liquid` inside a `<style>` block.

## Notes for no-Sass users

- All runtime customization can be done via CSS custom properties — consumers do not need to run Sass. Ship the compiled `css/motionforge.css` and instruct users to override the properties.
- If you want to provide a smaller subset of the pack (just the loader), export a minified CSS file containing only the relevant selectors and keyframes.
- Include `demos/` as preview pages so buyers can quickly test the loader in their environment.
