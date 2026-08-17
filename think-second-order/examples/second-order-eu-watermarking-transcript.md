# Second-order thinking, worked transcript

**Method:** think-second-order (Howard Marks, "and then what?" applied past the first-order effect).
**Move traced:** "The EU AI Act now requires AI-generated content, in images and text, to be marked as artificially generated (Article 50, applicable 2 August 2026)."
**Analysed headline:** "The EU now requires AI-generated content to be watermarked. And then what?"
**Register used:** MODIFY.
**Revised call, one sentence:** Comply as accountability, not as a fix for deception: invest in the disclosure and provenance you can enforce, and stop expecting invisible text watermarks to stop misuse.

This is a working transcript of the reasoning behind the client-facing report. It is a decide-tier lens applied to a regulatory move whose effects ripple through providers, deployers, platforms, bad actors and audiences.

---

## 1. The decision and its first-order effect

Article 50 carries two duties that bite on 2 August 2026. Providers of generative AI must mark their outputs (audio, image, video and text) in a machine-readable, detectable way, "robust and reliable as far as technically feasible". Deployers must give a human-perceivable disclosure of deepfakes and of AI-generated text published on matters of public interest, and chatbots must say they are AI. Penalties reach EUR 15M or 3% of worldwide annual turnover.

The naive, first-order reading: providers add machine marks (signed provenance metadata such as C2PA / Content Credentials, and invisible watermarks such as SynthID), deployers add a visible "this is AI" line, and audiences can now tell AI content from human content. The plan that follows from first-order thinking alone is "just watermark everything and the deception problem is solved."

That is where first-order thinking stops. The rest of the trace is who responds, and how.

## 2. The consequence chain (three rungs, each naming who responds)

**1st order, Providers and deployers, the intended result.**
Everything gets marked and labelled. Providers attach machine-readable marks; deployers attach the visible disclosure. On its face the labelling now separates AI content from human content for any reader.

**2nd order, Platforms and bad actors.**
The label falls off exactly where it is needed. Every major social platform (Instagram, X, LinkedIn, TikTok, Facebook) strips provenance metadata on upload, and a screenshot erases it, so the signed record rarely survives in the wild. The only mark that persists is the invisible watermark. Meanwhile, anyone who wants to deceive paraphrases or lightly edits the AI text, and text watermarks degrade under paraphrase, copy-paste and back-translation. So honest content keeps its label and deceptive content routes around it. C2PA 2.1 added invisible soft-binding watermarks precisely because metadata is stripped, which tells you the metadata channel is known to be fragile.

**3rd order, Audiences and the market.**
The signal inverts. A detection arms race opens, and "unmarked" begins to read as "human and trustworthy," so the incentive to strip marks grows rather than shrinks. Compliant enterprises carry the labels; the actors the rule was meant to catch evade them. Once people learn a mark is easy to remove, trust in the label itself erodes. The rule best disciplines the parties who were never the problem.

Reasoning note on the text channel: robust invisible text watermarking may be close to theoretically impossible. Soheil Feizi's work found watermarks unreliable, with false-positive and false-negative rates that yield near-zero usable information, and no reliable general-purpose AI-text detector exists. This is the single weakest link in the chain, and it is load-bearing for the whole "watermark everything" plan.

## 3. Feedback loops

**Reinforcing (danger): "The marking arms race."**
Every improvement in marking invites a matching improvement in stripping or paraphrasing. Better detectors are used to train better evaders, and each side's output becomes the other's training data. The race funds itself and never settles. This is the loop that turns a reasonable compliance step into an open-ended cost with no equilibrium.

**Balancing (counter-force): "Provenance where it counts."**
For high-stakes institutional content (official statements, journalism, legal evidence) verifiable provenance plus a named, accountable human holds, because the receiving side has a reason to check the signal and preserve it. This is the part of the duty that durably works, and it is the part worth investing in.

## 4. The 10/10/10 read

- **10 minutes (usually emotion): relief.** "We added a disclosure line and picked a compliant vendor, so we are covered." The box is ticked.
- **10 months (reality sets in):** the label is on all your compliant content and absent on the content that actually matters. An internal argument opens on whether text watermarking is worth its quality and effort cost.
- **10 years (the reversal):** provenance-by-default is normal for institutional content, watermark stripping is a routine known fact, and the durable value turns out to be human disclosure plus provenance for high-stakes content, not universal invisible text watermarking.

The 10-minute feeling (we are covered) is exactly reversed by the 10-year verdict (coverage was never the point; enforceable disclosure and high-stakes provenance were).

## 5. The scaling test: "what if everyone marks?"

If all legitimate content is marked and the marks are strippable, the absence of a mark becomes the thing bad actors want. Marking then identifies the honest actors more than it catches the dishonest ones. It is still worth doing, for accountability and consumer clarity, but it is not an anti-disinformation control. A move that works as an exception behaves differently as a universal norm, and this one inverts.

## 6. Traps named in this chain

- **Mistaking the machine mark for the binding duty.** The enforceable, novel obligation is the human-perceivable disclosure, not the fragile watermark. Effort spent chasing the watermark is spent where the law does not actually bind you.
- **Only tracing the downside.** Success has an upside: honest provenance becomes a real consumer-trust signal and a differentiator for brands that adopt it well. The failure mode is universal anti-deception, not the marking itself.
- **Chaining mechanics, not people.** The chain turns on platforms stripping, bad actors paraphrasing and audiences re-reading the signal. Trace file formats alone and you miss where it turns. Every rung above is deliberately kept about who responds.

## 7. The revised decision (MODIFY) and rationale

Register: **Modify.** Not Keep, because the naive "watermark everything to stop deception" plan fails the second and third rungs and the scaling test. Not Reject, because the duty is law, the visible disclosure is a real and enforceable obligation, and high-stakes provenance genuinely works.

What the chain changed about the naive plan: it splits one undifferentiated task into two. There is the marking you can enforce (the human-perceivable "this is AI" disclosure, plus verifiable provenance and human accountability for high-stakes content) and the marking you cannot (invisible text watermarks expected to survive determined misuse). The first is where compliance effort and trust-building belong. The second should be treated as a good-faith, technically-feasible best effort under Article 50(2), documented as such, and never leaned on as a control against bad actors.

**Single next action (the report's one terracotta call):** Split your Article 50 work into the marking you can enforce and the marking you cannot, before 2 August 2026.

Practical deployer note that follows from the trace: you cannot rely on the provider's machine mark alone, the enforceable and novel duty is the visible disclosure, and documenting genuine human editorial review is how you support the public-interest-text position. The Act is technology-neutral and does not mandate C2PA; compliant machine-marking, human disclosure and a voluntary code of practice as a safe harbour are the practical path.
