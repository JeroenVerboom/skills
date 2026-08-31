---
name: visual-explainer-bonsai
description: Create reader-first, self-contained HTML explainers, reviews, recaps, tables, and dashboards. Use Diagram Design as the required rendering authority whenever structure, relationships, sequence, or quantitative comparison needs a visual.
license: MIT
metadata:
  author: Verboom AI Consulting
  version: "1.0.0"
---

# Visual Explainer Bonsai

Create visual explanations that let a reader see the answer before the detail. The page shell carries the argument; Diagram Design carries every diagram, chart, schema, and relational visual.

## Required engine

This skill requires Diagram Design 2.6.11 or later for diagram generation. Final HTML must work without remote requests or tracking.

Before creating an explainer, load the installed `diagram-design` skill. Do not substitute Mermaid, a CSS-box diagram, Canvas, or a chart library as the final renderer.

- If Diagram Design is unavailable, stop and ask the user to install or enable it. Do not silently make a weaker replacement.
- When the content needs a diagram, follow Diagram Design in full: select the semantic pattern when applicable, select the visual type, read that type reference, respect its complexity budget and connector rules, then run its `scripts/self_check.py` on the result.
- Mermaid and draw.io may be imported only through Diagram Design. They are never the final renderer.
- When a table or short prose communicates the content better, record that choice in the page. Diagram Design still owns the representation decision; do not force a decorative figure.

## Decide the deliverable

1. Establish the reader, their decision or question, the source boundary, and the one-sentence answer. Verify source-backed claims before layout; label proposals and unknowns.
2. Select a mode: `review`, `recap`, `audit`, `comparison`, `dashboard`, or `compound`.
3. In `compound` mode, create the Diagram Design SVG first and embed it as the primary `<figure>` inside the explainer page. Give the figure a claim-stating `figcaption`.
4. Read [the page system](references/page-system.md) before writing the surrounding HTML. Use its Verboom Editorial profile when the user asks for Verboom, Bonsai, or a matching local design system; otherwise use the project’s confirmed design tokens.

## Modes

### Review and recap

Lead with the conclusion, then show the current state, the relevant visual, evidence, trade-offs, and the next action. Keep claims tied to inspected source files, git history, or supplied material. Use `<details>` for supporting evidence that would distract from the decision.

### Audit and comparison

Use a semantic HTML `<table>` for a matrix, status register, or side-by-side comparison. Preserve row and column meaning, let long text wrap, and use words as well as colour for status. Add a Diagram Design figure only when it reveals a relationship that the table cannot.

### Dashboard

Put the decision-relevant measures first. Show a visual only if the scale, change, relationship, or distribution is the evidence. Do not make a decorative dashboard from sparse or invented data.

## Output contract

- Deliver one self-contained HTML file with embedded CSS, inline SVG, and only the minimum inline JavaScript required for requested interaction.
- Never request remote fonts, stylesheets, images, analytics, or tracking. Use local or system fallbacks and disclose an unverified font match.
- Use semantic HTML, keyboard-visible focus, responsive layout, `min-width: 0` on grid and flex children, and `overflow-wrap: break-word` for long tokens.
- For four or more major sections, add the responsive contents pattern in `page-system.md`; otherwise omit navigation.
- An embedded Diagram Design SVG keeps its `role="img"`, prefixed `<title>` and `<desc>`, and `aria-labelledby`. Do not alter its geometry after it has passed Diagram Design validation.

## Verify before delivery

1. Run Diagram Design’s `self_check.py` on every output containing an SVG figure.
2. Inspect at 375px, 768px, and 1440px. Check horizontal overflow, table scrolling, keyboard focus, print readability, and `prefers-reduced-motion`.
3. Confirm the first viewport states the answer and the figure caption states the claim.
4. Confirm every factual statement has a source or is labelled as a proposal, estimate, or unknown.
5. Confirm the final file makes no external request.

## Boundaries

- The Diagram Design 4px grid, 4–8px node radii, connector geometry, accessibility contract, and complexity limits apply inside the SVG.
- The surrounding Bonsai page may use the 40px editorial container radius. Do not leak it into diagram nodes.
- Terra is the sparse focal accent; Forest is a chamber or data-emphasis ground. Do not add gradients, glow, or routine shadows.
- Do not modify, deprecate, or replace the managed Diagram Design plugin from this skill.
