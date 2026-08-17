---
name: think-second-order
description: Traces consequences beyond the immediate effect of a decision by asking "and then what?" repeatedly. Use when the user asks "what could go wrong later", "what are the downstream effects", "what are we not seeing", or weighs a move that changes how others behave (pricing, hiring, incentives, policy). Not for trivial or easily reversible choices, and not for diagnosing why something already went wrong.
metadata:
  category: decide
  tier: lens
---

# Method

Second-order thinking, described by investor Howard Marks in The Most Important Thing (2011), goes past the immediate effect of a decision to ask "and then what?" again and again. First-order thinking sees the obvious result. Second-order thinking traces how customers, competitors, employees, and systems respond to that result, which is where most unintended consequences live. As Marks puts it: "First-level thinking is simplistic and superficial, and just about everyone can do it."

## When to use

Use for decisions whose effects ripple: pricing moves, hiring or restructuring, incentive and policy changes, anything that changes what other people do next.

Two tiers:

- **Quick pass** (default): the decision matters but time is short, or the user just wants a sanity check. Ask "and then what?" twice per option and answer in a few sentences.
- **Full analysis**: trigger when the decision is hard to reverse, affects many people, changes incentives, or the obvious answer feels too easy. Run the full procedure.

Not for: trivial or reversible decisions (check with think-reversibility first), or root-causing an existing failure.

## Procedure

1. **State the decision and its first-order effect.** The intended, obvious result.
2. **Chain the consequences.** Ask "and then what?" at least three times. Focus on responses from people: who is affected, and what will they do about it?
3. **Time-shift with 10/10/10** (Suzy Welch's framework from her book 10-10-10, 2009): how does this decision look in 10 minutes, 10 months, and 10 years? The 10-minute answer is usually emotion; the 10-year answer usually reverses it.
4. **Run the scaling test.** Ask "what if everyone did this?" A move that works as an exception often fails as a norm.
5. **Spot feedback loops.** Does any consequence circle back to amplify or dampen the original decision? Flag reinforcing loops explicitly; they are what turn small choices into spirals.
6. **Revise the decision** in light of the full chain. Keep, modify, or reject.

### Worked chains

**Price cut (15% to win volume)**
- 1st: Sales volume rises.
- 2nd: Competitors match within a quarter; the volume gain evaporates while margins stay compressed for everyone.
- 3rd: Customers re-anchor on the lower price. Restoring the old price now reads as an increase, and the brand drifts toward the budget tier.
- Loop: thinner margins shrink the marketing and product budget, eroding the differentiation that justified the higher price, which invites more discounting.

**Headcount freeze (to protect the budget)**
- 1st: Payroll cost growth stops.
- 2nd: Workload concentrates on the remaining team. The most marketable people, usually your strongest, leave first for better offers and cannot be backfilled.
- 3rd: Quality and delivery slip, the rest burn out, and when the freeze lifts you rehire at market rates into a weakened team.
- Loop: reinforcing. Each departure raises the load on those who stay, triggering the next departure.

**Skip code review for urgent fixes (one software example)**
- 1st: The urgent fix ships faster.
- 2nd: The definition of "urgent" expands; more changes skip review.
- 3rd: Defect rates rise, creating more urgent fixes. The scaling test fails outright: if everyone does this, review becomes theater.

## Output contract


**Language:** write the deliverable in the language the user is using (Dutch, English, or another), in plain language at CEFR B2 level. Prefer everyday words over jargon. Where a method term is genuinely needed, keep it, but add a short plain explanation in parentheses on first use.

**Full analysis** delivers:
- Per option: a first, second, and third-order consequence chain, naming who responds and how.
- Any feedback loops spotted, marked reinforcing or balancing.
- The 10/10/10 read where time horizons change the answer.
- The revised decision with a one-paragraph rationale: keep, modify, or reject, and why.

**Quick pass** delivers: "and then what?" answered twice per option, plus a one-line recommendation, in a few sentences total.

## Rendered report (full analysis only)

When the user wants a shareable artifact, or a full analysis has earned one, render the result as a self-contained HTML report in the Verboom Editorial design system. Skip this for a quick pass: a few sentences do not need a document.

The stylesheet and a structure skeleton ship with this skill in `assets/`:
- `assets/verboom-report.css` — read it and inline the whole file into a `<style>` block, so the report is one standalone HTML file with no external requests.
- `assets/report-template.html` — the reference structure; follow its classes and section order exactly.

A rendered worked example is in [`examples/`](examples/second-order-eu-watermarking-example.html): the EU AI Act synthetic-content marking duty ("watermarks"), traced past its first order.

**File:** `second-order-[slug]-[timestamp].html`, saved to the user's workspace, then opened.

Section order, reader-first (the call first, then the chain that justifies it):
1. **Masthead** — the Verboom wordmark (with the terracotta dot), then a serif hero: the eyebrow "Second-order analysis", the decision or move as `h1`, a one-line framing `dek`.
2. **Report head + method note** — a `rep-head` bar, then the `methodnote`: second-order thinking traces past the immediate effect by asking "and then what", and the chains are directions of travel, not predictions.
3. **The revised call** — the page's one forest ground. A mint `clabel` reading "The call: Keep / Modify / Reject", the revised decision as one italic serif line (the only italic heading), the single next action as the page's only terracotta fill, then one rationale line.
4. **The consequence chain** — the signature `ol.chain`. One `li.rung` per order of consequence: the first rung calm (`.first`), the last the knock-on effect (`.deep`). Each rung names WHO responds in the `.who` label, then the effect as an `h4`, then one line of detail. Three orders is usually enough.
5. **Feedback loops** — a `.loop` per loop, `reinforcing` (the danger tint) or balancing. Omit the section if there are none.
6. **The 10/10/10 read** — three `.horizon` cards: 10 minutes, 10 months, 10 years. Show it only where a horizon changes the answer.
7. **The scaling test** — the `.scaling` callout: what if everyone did this.
8. **Traps** — optional `ul.traps`, the misreadings this chain invites, including any upside of success the downside-only reflex would miss.
9. **Footer** — the method disclaimer verbatim (this is a structured trace of plausible effects, not a forecast), an optional `note` for regulated or illustrative topics, and a site footer with the timestamp and what was traced.

Design rules the report must obey (all encoded in the CSS, do not override them):
- Warm paper ground, warm neutrals only. Never pure white, never cool grey. The revised call is the ONE forest ground; no other block sits on forest, and there is no dark theme anywhere else.
- Forest and terracotta are meaning, not decoration: forest marks the settled call and balancing forces; terracotta marks the one next action (its only fill) and, as a tint, the danger of a reinforcing loop. The terracotta fill stays well under 10% of the page.
- 8-12px radii on the call ground and the cards; 2px ink rules frame the masthead and report head; 1px stone hairlines divide rows; no shadows, no gradients, no background textures.
- Two type families only: EB Garamond for statements and reading text (falls back to Georgia), Inter for labels and UI (falls back to system-ui). No external font requests. UPPERCASE only at 12px label-caps. Sentence case everywhere else. No emoji, no exclamation marks, no em dashes: use a comma, a colon or a new sentence.
- Keep every rung about people, not mechanics: the `.who` label forces the question the method turns on.

## Traps

- **Stopping at the first order** because later effects feel speculative. They are uncertain, not optional; state them with confidence levels instead of skipping them.
- **Chaining mechanics instead of people.** Most second-order effects come from how others respond (competitors match, employees leave, users adapt), not from the thing itself.
- **Infinite chains.** Three orders per option is usually enough; beyond that, uncertainty swamps the analysis.
- **Only tracing downside.** Success has second-order effects too. Ask: if this works, what problems does success create?

## Combinations

- Part of the guided workflows: `think-structured-decision-workflow` and `think-structured-review-workflow` (they apply this lens within an end-to-end session).
- **think-feedback-loops**: when a consequence circles back on itself, hand off to map the loop structure properly.
- **think-premortem**: feed the worst chain into a premortem ("it is two years later and this decision failed; tell the story").
- **think-inversion**: work backward from the outcome you must avoid and check whether any chain leads there.
- **think-reversibility**: gate the effort; fully reversible decisions rarely deserve a full chain analysis.
