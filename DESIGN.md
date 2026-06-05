# Design

## Overview

Cleanapp uses a sharp indie SaaS visual system: high-contrast ink, a crimson brand anchor, lime confirmation accents, and compact app surfaces. Marketing pages can use stronger color and larger type. Authenticated app screens stay calmer, with the accent reserved for actions, status, and orientation.

## Color

Use OKLCH tokens in CSS. The palette is anchored by the impeccable seed hue near 20 degrees and balanced with a cooler chartreuse accent.

```css
:root {
  --ca-bg: oklch(1 0 0);
  --ca-surface: oklch(0.975 0.006 95);
  --ca-surface-strong: oklch(0.925 0.018 95);
  --ca-ink: oklch(0.135 0.018 250);
  --ca-muted: oklch(0.405 0.024 250);
  --ca-primary: oklch(0.43 0.14 20);
  --ca-primary-strong: oklch(0.33 0.12 20);
  --ca-accent: oklch(0.78 0.18 125);
  --ca-accent-soft: oklch(0.93 0.08 125);
  --ca-line: oklch(0.88 0.01 95);
  --ca-warning: oklch(0.68 0.16 55);
  --ca-success: oklch(0.58 0.14 145);
  --ca-danger: oklch(0.55 0.19 25);
}
```

## Typography

Marketing surfaces use the system stack with strong weight contrast and tight, readable display sizes. Product surfaces use the same family for speed and consistency. Avoid oversized display type inside app panels.

## Layout

Marketing should feel poster-like in the first viewport, with a visible product artifact rather than abstract decoration. App screens use a compact shell, a left navigation rail on desktop, sticky top controls on smaller screens, and data-first content regions.

## Components

Buttons use 10 to 12px radii, never oversized pill shapes for standard app actions. Cards and panels use light borders or flat tinted surfaces, not paired heavy shadows. Status pills use semantic colors with readable text. Tables keep row actions close to the URL data.

## Motion

Marketing can use short entrance and hover motion. Product UI motion should be 150 to 250ms and state-based only. All motion must respect `prefers-reduced-motion`.
