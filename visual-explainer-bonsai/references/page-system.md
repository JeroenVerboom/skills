# Bonsai page system

Use this reference for the HTML outside a Diagram Design figure. It adapts the useful reader-first parts of Visual Explainer to the Verboom Editorial system without creating a second diagram renderer.

## Page order

1. A small label that names the document type.
2. A direct headline that gives the answer or decision.
3. One short framing paragraph: what was examined and the source boundary.
4. The Diagram Design figure or a semantic table, whichever carries the evidence.
5. Evidence, trade-offs, and a single next action.

If a page has four or more main sections, use a sticky desktop contents rail that becomes a horizontally scrollable navigation bar on small screens. Otherwise leave it out.

## Verboom Editorial profile

Use these values only when the user requests the Bonsai or Verboom look, or when the current project confirms them. They are a page skin, not a replacement for Diagram Design’s semantic roles.

```css
:root {
  --vb-paper: #fffdf0;
  --vb-cream: #fcfaed;
  --vb-ink: #1a1a1a;
  --vb-terra: #c56c47;
  --vb-forest: #0b3d33;
  --vb-stone: #e9e6d6;
  --vb-muted: #747878;
  --vb-radius-card: 40px;
  --vb-radius-small: 8px;
  --vb-sans: Inter, Arial, sans-serif;
  --vb-serif: "EB Garamond", Georgia, serif;
  --vb-mono: ui-monospace, SFMono-Regular, Menlo, monospace;
}

* { box-sizing: border-box; }
html { font-size: 16px; }
body {
  margin: 0;
  background: var(--vb-paper);
  color: var(--vb-ink);
  font-family: var(--vb-sans);
  font-size: 1rem;
  line-height: 1.6;
  overflow-wrap: break-word;
}
.vb-wrap { width: min(100% - 2rem, 1280px); margin: 0 auto; }
.vb-label { font: 600 .75rem/1 var(--vb-sans); letter-spacing: .1em; text-transform: uppercase; }
.vb-title { font: 400 clamp(2.25rem, 7vw, 5rem)/.95 var(--vb-serif); letter-spacing: -.04em; }
.vb-panel { border: 2px solid var(--vb-ink); border-radius: var(--vb-radius-card); padding: clamp(1.5rem, 4vw, 4rem); }
.vb-forest { background: var(--vb-forest); color: var(--vb-paper); }
.vb-grid { display: grid; gap: 1.5rem; }
.vb-grid > * { min-width: 0; }
table { width: 100%; border-collapse: collapse; }
th, td { padding: .875rem; border-bottom: 1px solid var(--vb-stone); text-align: left; vertical-align: top; }
th { font-size: .75rem; letter-spacing: .08em; text-transform: uppercase; }
figure { margin: 0; }
figure svg { display: block; width: 100%; height: auto; }
figcaption { margin-top: .75rem; color: var(--vb-muted); font-size: .875rem; }
:focus-visible { outline: 3px solid var(--vb-terra); outline-offset: 3px; }
@media (max-width: 700px) { .vb-wrap { width: min(100% - 1rem, 1280px); } .vb-panel { border-radius: 24px; } .vb-table-wrap { overflow-x: auto; } }
@media (prefers-reduced-motion: reduce) { *, *::before, *::after { animation-duration: .01ms !important; transition-duration: .01ms !important; scroll-behavior: auto !important; } }
```

Map the confirmed project tokens to Diagram Design's `paper`, `paper-2`, `ink`, `muted`, `soft`, `rule`, `rule-solid`, `accent`, `accent-tint`, and `link` roles before drawing. For the Verboom profile, use Paper as `paper`, Ink as `ink`, Terra as `accent`, Forest as `link` or a data-emphasis role, and Stone as `rule-solid`. Retain one accent in the SVG.

## What not to inherit

Do not inherit Visual Explainer’s Mermaid final rendering, mandatory light/dark pairing, aesthetic rotation, gradients, glass effects, routine shadows, or mandatory browser opening. They conflict with a stable, branded reader-first page and Diagram Design’s editorial geometry.
