# Evidence-Based UX

A Claude skill for designing and reviewing user interfaces from the research record instead of from taste. It was built by reading 86 peer-reviewed HCI papers and the WCAG 2.2 standard in full, then turning what they found into 252 rules that Claude can apply to a screen, a mockup, a form or a block of front-end code.

Each rule says what to do, why, how strong the evidence is, and where it stops holding. When Claude uses the skill it cites rule IDs (`PT-1`, `FE-7`), so you can trace any recommendation back to the study behind it.

## What it changes

Ask a model to "make this form better" and you usually get advice that sounds right and can't be checked. With this skill loaded, the same request comes back with specifics like these:

- Errors go next to the field, in text as well as color, and completed fields are never cleared. On three real newspaper registration forms, applying the full guideline set this comes from cut completion time by 18–33% (Seckler et al., 2014).
- One-thumb touch targets should be at least 9.2 mm. Error rates climb steeply below 15 mm and pass 40% below 8 mm when people are hurried (Parhi et al., 2006; Henze et al., 2011, 120 million taps).
- Click and keystroke feedback should arrive within 0.1 s. Filters should update results within 100 ms, and anything longer than about 15 s should run in the background (Card et al., 1991; Shneiderman, 1996; Miller, 1968).
- Cancelling should take the same channel and the same number of steps as signing up. Dark patterns turned up in 95% of 240 popular Android apps, and most users didn't notice them (Di Geronimo et al., 2020).

It also corrects some design folklore that the cited papers never claimed. Miller's "7±2" was about absolute judgment, not menu length. "Five users find most problems" holds only when each user finds about a third of them. Fitts' law doesn't cover dragging along a path, which grows linearly with length.

## Install

In Claude, upload `evidence-based-ux.zip` from the [latest release](../../releases/latest) under **Customize → Skills**. In Claude Code, copy the skill folder into your skills directory:

```bash
git clone https://github.com/nassirian/evidence-based-ux.git
cp -r evidence-based-ux/skills/evidence-based-ux ~/.claude/skills/
```

[docs/SETUP.md](docs/SETUP.md) covers both, plus Codex and ChatGPT desktop.

Claude loads the skill on its own when a task involves designing, building or reviewing an interface. You can also ask for it by name: "Use the evidence-based-ux skill to review this checkout screen."

## How it is organized

```
skills/evidence-based-ux/
  SKILL.md                 14 core principles, a numbers card, design and review workflows
  references/
    01-visual-hierarchy-layout-aesthetics.md   VH  grouping, attention, complexity, aesthetics
    02-text-typography-color.md                TX  line length, type size, contrast, palettes, copy
    03-pointing-touch-gestures.md              PT  Fitts and steering laws, touch targets, thumb reach
    04-feedback-timing-motion.md               FT  response times, progress, animation, notifications
    05-cognition-consistency-learnability.md   CL  memory load, conventions, mental models, learnability
    06-forms-input-errors.md                   FE  forms, validation, error messages, destructive actions
    07-navigation-search-data-display.md       NS  menus, search, facets, tables and charts
    08-accessibility-inclusion.md              AX  WCAG 2.2 AA and the research beyond it
    09-trust-ethics-dark-patterns.md           ET  credibility, consent, pricing, dark patterns
    10-ai-and-llm-interfaces.md                AI  AI features, agents, explanations, prompting
    11-evaluation-and-measurement.md           EV  heuristic evaluation, testing, SUS, metrics
    12-automated-ui-review.md                  AR  how Claude should critique a UI, and its blind spots
research/
  BIBLIOGRAPHY.md          every source, with DOIs
  summaries/               paper-by-paper summaries the rules were drawn from
```

`SKILL.md` stays short enough to load on every design task. The reference files are read only when the work calls for them, and each one ends with a checklist that Claude runs during a review.

## Evidence grades

Every rule carries a grade. [A] means replicated, large-sample or meta-analytic findings, or the WCAG standard; 64 rules have it. [B] means one solid study, or several smaller ones that agree; that covers 143 rules. [C] marks expert opinion, theory, small qualitative studies, or lab psychology applied to screens, and applies to 45.

Most of HCI sits in the middle grade, and the skill doesn't pretend otherwise. When rules conflict, Claude is told to prefer the stronger grade and the closer match to the user's context, and to say when it has made that call.

## Reviewing with an AI

File 12 deals with the fact that the reviewer is itself a model. Published studies of GPT-4, Gemini and other vision-language models as UI critics found that they miss about six in ten problems a human expert catches. About four in ten of the findings they do raise aren't useful. And when asked which of two designs is better, they do little better than chance. The skill builds the known fixes into its review procedure: explicit guideline text, a fixed set of categories, a separate pass for flow-level problems, deduplication, and a list of things not to flag (labels on universal icons, differences that encode state, changes too small to see). Every finding states its rule, its evidence grade and how confident the reviewer is.

A review is still advice for a person to weigh. It does not replace testing with users, and the skill says so.

## Sources and limits

The corpus covers usability heuristics and inspection, cognitive and motor laws, visual aesthetics and first impressions, typography, accessibility, navigation and search, forms, credibility, dark patterns, human-AI interaction, computational layout evaluation, touch input and learnability. It runs from Fitts (1954) to work published at CHI and UIST in 2024. [`research/BIBLIOGRAPHY.md`](research/BIBLIOGRAPHY.md) lists all of it.

Some limits are worth knowing before you rely on it:

- About 30 relevant papers sit behind paywalls and were not read in full. They include Tractinsky et al. (2000), Lindgaard et al. (2006), Hassenzahl and Tractinsky (2006), Hick (1952) and Davis (1989). Where later papers report their findings, the skill cites them as secondary sources and labels them that way.
- Many studies used students, desktop screens and short lab sessions. Accessibility studies have a median of about 13 disabled participants, and 43% of them focus on blind and low-vision users.
- Apple's Human Interface Guidelines and Google's Material Design are not included. Platform conventions still matter, and the skill tells Claude to follow them.
- The research is older than most current products. The rules describe people, which change slowly, more than platforms, which change fast.

The paper PDFs are not in this repository. The DOIs in the bibliography lead to each one. The summaries are paraphrased notes written for this project and contain no quoted passages.

## License

MIT. See [LICENSE](LICENSE).
