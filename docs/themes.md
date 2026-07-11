# Theme presets — Orbital Harmonic

This file contains ready-made theme classes you can drop into your project to quickly style the Orbital Harmonic loader. They rely only on CSS custom properties — no Sass required.

## How to use

- Include `css/motionforge.css` in your page.
- Import or paste these theme classes into your global stylesheet (or inline in a page).
- Apply the class alongside `orbital-harmonic`.

Example:

```html
<link rel="stylesheet" href="css/motionforge.css" />
<link rel="stylesheet" href="css/themes.css" />
<!-- contains the preset classes -->
<div class="orbital-harmonic orbital-theme-neon"></div>
```

## Preset theme classes

.orbital-theme-neon

- vibrant, high-contrast neon look

```css
.orbital-theme-neon {
  --oh-inner-color: #00f6ff;
  --oh-middle-color: #7c3aed;
  --oh-outer-color: #ff4d6d;
  --oh-inner-duration: 4s;
  --oh-middle-duration: 5.6s;
  --oh-outer-duration: 7s;
  --oh-inner-dot-duration: 2.6s;
  --oh-middle-dot-duration: 4s;
  --oh-outer-dot-duration: 5s;
  --oh-inner-glow-1: rgba(0, 246, 255, 0.36);
  --oh-inner-glow-2: rgba(0, 246, 255, 0.12);
  --oh-outer-dot-glow: rgba(255, 77, 109, 0.95);
}
```

.orbital-theme-warm

- soft warm palette, subtle glow

```css
.orbital-theme-warm {
  --oh-inner-color: #ffd6a5;
  --oh-middle-color: #ffadad;
  --oh-outer-color: #ff6b6b;
  --oh-inner-duration: 5s;
  --oh-outer-dot-duration: 6s;
  --oh-outer-glow-1: rgba(255, 107, 107, 0.18);
  --oh-outer-glow-2: rgba(255, 107, 107, 0.06);
}
```

.orbital-theme-subtle

- muted, low-glow theme for UI contexts

```css
.orbital-theme-subtle {
  --oh-inner-color: #9ad1ff;
  --oh-middle-color: #cbb4ff;
  --oh-outer-color: #ffb0c0;
  --oh-inner-duration: 5.6s;
  --oh-middle-duration: 6.8s;
  --oh-outer-duration: 8s;
  --oh-inner-glow-1: rgba(154, 209, 255, 0.12);
  --oh-inner-glow-2: rgba(154, 209, 255, 0.04);
  --oh-outer-dot-glow: rgba(255, 176, 192, 0.9);
}
```

.orbital-theme-mono

- monochrome, works well in headers and footers

```css
.orbital-theme-mono {
  --oh-inner-color: #ffffff;
  --oh-middle-color: #d1d5db;
  --oh-outer-color: #9ca3af;
  --oh-inner-duration: 5s;
  --oh-outer-dot-duration: 6s;
  --oh-inner-glow-1: rgba(255, 255, 255, 0.14);
  --oh-inner-glow-2: rgba(255, 255, 255, 0.06);
}
```

## Packaging suggestion

- Export a `themes.css` file that contains these classes and include it in your distribution ZIP alongside `css/motionforge.css`.
- Include an HTML preview page (`demos/demo-themes.html`) so buyers can see themes in action.
