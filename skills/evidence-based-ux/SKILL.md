---
name: evidence-based-ux
description: Evidence-based UI/UX design and review, distilled from 86 peer-reviewed HCI papers and WCAG 2.2. Use when designing, building, critiquing or auditing any interface (screens, mockups, Figma frames, front-end code, forms, navigation, dashboards, mobile apps, AI/chat features), when choosing sizes, timings, layout, color or copy, or when planning a usability evaluation.
---

# Evidence-based UX

This skill turns the research record on interface quality into rules you can apply. Every rule traces to a study or a standard, carries an evidence grade, and states where it stops holding. Use it to make design decisions, to review designs, and to explain *why* a choice is better.

## How to use this skill

1. **Identify the job.** Building or specifying a UI, reviewing one, evaluating with users, or designing an AI feature.
2. **Apply the core principles below.** They cover most decisions on their own.
3. **Load the reference file for the area you are working in** (see the map at the end) when you need the full rule, the numbers, the limits or the sources. Each reference file ends with a checklist.
4. **Cite rules by ID** (for example `PT-1`, `FE-7`) when you explain a decision or report a finding, so the reasoning can be checked.

### Evidence grades

- **[A] strong.** Replicated, large-sample, meta-analytic, or an international standard (WCAG).
- **[B] moderate.** One solid experiment, or several smaller studies that agree.
- **[C] weak.** Expert opinion, theory, small qualitative work, or lab psychology extrapolated to UI.

Lead with [A] rules. Treat [C] rules as sensible defaults that context can override. When two rules conflict, the one with the stronger grade and the closer match to the user's context wins. Say so when you make that call.

## Core principles

These 14 patterns recur across the corpus. Each one is backed by several independent sources.

### 1. Answer every action and keep status visible
Every input gets a perceptible reaction. Visibility of system status is the top factor in Nielsen's analysis of 249 usability problems, and "every action gets a reaction" runs through every guideline set in the corpus.
- Echo input and acknowledge clicks and taps within **0.1 s** (0.2 s at most). Keep continuous feedback (dragging, scrolling, animation frames) at **≤0.1 s per update**; reduce fidelity before frame rate.
- Answer routine requests within **~1–2 s**. Update filtered results within **100 ms** of a control change.
- Put any longer delay **after** a natural task boundary, not in the middle of a thought.
- For waits beyond a few seconds, say how long and why, show a **percent-done indicator** (graphical, with stages for multi-step work and visible liveness), and offer **cancel**.
- Beyond **~15 s**, free the user: run the job in the background and notify on completion.
- Never treat silence as success. Announce status to assistive technology.
→ `FT-1…FT-10`, `references/04-feedback-timing-motion.md`. Grade: [B] for feedback (FT-1), [A] for announcing status (FT-10, WCAG), [B]/[C] for the specific thresholds.

### 2. Let people recognize, not recall
Recognition over recall explains more *serious* usability problems than any other heuristic. Working memory holds about **4 chunks** (range ~2–6 between people), not "7±2".
- Keep the information a user needs **on screen** at the step where it is needed: echo what they entered, show context, show the current mode and location.
- Never require users to carry more than **3–4 new, unrelated items** from one step to the next.
- Chunk long codes and numbers (e.g. `4821 7730 1192`). Group related items so each group is one chunk.
- Make available actions visible and easy to tell apart. Hidden gestures and unlabeled icons are recall tasks.
→ `CL-1…CL-4`, `CL-14`. Grade: [A] for the capacity limit, [B] for the UI transfer.

### 3. Be consistent and conventional before being clever
Consistency is the single heuristic that explains the most usability problems (23%), and "the single objective on which experts agree" (Smith & Mosier). Standards beat local optimization.
- Same function: same name, same look, same place, same behavior. Across every screen.
- Follow platform and domain conventions. Put logo, search, menu, account and cart where users of that domain expect them: learned positions cut visual search time by over 10% and fixations by over 23%.
- Use one term per concept, in the user's language, not the system's.
- Avoid modes. If a mode is unavoidable, show it at all times.
→ `CL-5…CL-13`, `VH-13`. Grade: [A]/[B].

### 4. Make errors hard to make and easy to fix
Designers find error-prevention problems least often (55% of entries in one design-critique contest mentioned none).
- Prevent: constrain closed choices, accept every reasonable format (spaces, hyphens, parentheses in phone numbers), state format rules and required fields **before** input, use safe defaults.
- Recover: show each error **next to its field**, in text plus color/icon, keep the user's entry, **never clear completed fields**, move focus to the first error.
- Word messages as: what went wrong, in the user's terms, and exactly how to fix it. No blame words ("illegal", "invalid"), no bare "try again", no codes alone.
- Provide **undo**, cancel and a clearly marked exit from every state. Confirm only destructive or hard-to-reverse actions; routine confirmations train people to click through.
→ `FE-1…FE-17`, `references/06-forms-input-errors.md`. Grade: [A]/[B].

### 5. Group with space, rank with size and position
Proximity is the strongest, best-quantified grouping cue. Size is the strongest single predictor of where people look.
- Make gaps **between** groups clearly larger than gaps **within** them; competing groupings stop being seen at a distance ratio of about **1.5**. Reinforce groups with similarity, common background regions, or connecting lines.
- Set importance with size first, then position, contrast and isolation.
- Put identity and the key message top-left/top-center, where eyes land in the first second. Do not put must-see content in the right third above the fold; users treat it as ad space.
- Title every screen and every chart at the top. Titles draw the most attention in visualizations.
- Align to a small number of grid lines. Highlight sparingly; emphasis everywhere is emphasis nowhere.
→ `VH-2…VH-12`. Grade: [B]; proximity is the best-quantified cue, but from dot-lattice lab work.

### 6. Keep complexity low to moderate
Visual complexity is the largest penalty on first impressions, which form in **50–500 ms** and agree well with longer looks (r ≈ .70 between 150 ms and 4 s ratings), though they weaken after real use.
- First-impression appeal peaks at **moderate** complexity. Too complex is penalized far more (d ≈ 2.0) than too plain (d ≈ 0.6).
- Reduce clutter: fewer separate regions, text groups and image areas; fewer edges crowding each other.
- Use **few dominant colors**; smooth tonal range is fine and tends to help.
- Commit to symmetry or to clear asymmetry. Near-symmetry on mobile was liked least.
- Preferences shift by audience: highly educated users, and Finnish, Russian, French and German audiences, prefer plainer, less colorful designs; in the largest study, older users preferred *more* complex designs, not less. Test with the real audience.
→ `VH-1`, `VH-5…VH-7`, `VH-17`, `VH-20`, `TX-11`, `TX-14`. Grade: [A]/[B].

### 7. Treat visual quality as part of usability, and never as a substitute
Before use, how usable a product *looks* tracks how beautiful it looks (r = .59–.92). An appealing version of a phone UI with identical functions produced faster task times and fewer errors. "Design look" is the most-noticed credibility cue (46% of comments).
- Invest in craft: consistent concept, harmonious palette, clean alignment, quality imagery and type, zero typos or broken links.
- Do not let decoration replace labels or clear navigation. Attractive metaphor designs scored worse on usability and were still preferred, so appeal can mask problems.
- Polish prototypes to the level you will ship before testing them; an ugly prototype understates both ratings and performance.
→ `VH-15…VH-19`, `ET-15…ET-17`, `EV-15`. Grade: [B].

### 8. Make targets big, near and forgiving
Pointing time grows with log₂(distance/width + 1); path-constrained movement (submenus, drag tracks) grows **linearly** with length/width.
- Touch: plan for about **9–10 mm** minimum for one-thumb taps (convert to px/pt/dp with the target device's density; CSS px are not millimetres); errors rise steeply below **~15 mm** and pass **40% below 8 mm** under time pressure. **15 mm** is needed for 95% reliability across postures without platform correction.
- Web floor: **24×24 CSS px** or equivalent spacing (WCAG 2.5.8, AA); aim for **44×44 CSS px** (2.5.5, AAA).
- Edge and corner targets miss more often (31.7% vs 17.6% centre for small targets): make them larger or move critical ones inward. Keep frequent one-handed targets well inside thumb reach; avoid the corner diagonally opposite the holding thumb.
- Put the most frequent commands closest to where the pointer or thumb already is.
- Make submenu corridors wide and tolerant. Every drag, multi-finger or path gesture needs a single-tap alternative. Fire on release and let users slide off to cancel.
→ `PT-1…PT-18`. Grade: [A] for Fitts and WCAG, [B] for the mm values.

### 9. Write and set text for reading
- Line length in characters: about **55–70 characters per line** for reading; longer lines (85–100) only for scanning lists. Cap at 80 for accessibility.
- Body text of **14 pt or larger** for older readers. Let text scale to **200%** and reflow at **320 CSS px** without loss.
- Avoid italic body text. A roman sans-serif is a safe default; "dyslexia fonts" showed no benefit.
- Contrast: **4.5:1** for body text, **3:1** for large text (≥18 pt or 14 pt bold) and for UI component boundaries and icons. Never use color as the only cue.
- Write in the user's words: plain, affirmative, active voice, minimal abbreviations, no slang or hype.
- Preference and performance often disagree on typography. Decide on performance; use preference to break ties.
→ `TX-1…TX-19`. Grade: [A] for WCAG, [B] for line length and size.

### 10. Meet WCAG 2.2 AA as the floor
Accessibility is not a separate feature; it is the minimum quality bar. Situational impairments (walking, glare, gloves, noise) make it everyone's issue.
- Text alternatives, programmatic structure (headings, labels, roles, states), keyboard operability with a visible, unobscured focus, no keyboard traps.
- Contrast, resize, reflow, text-spacing and color rules above.
- Time limits users can extend or turn off. No more than 3 flashes per second. Users can pause motion.
- Consistent navigation, naming and help location. No memory or puzzle tests for login; allow paste and password managers. Don't re-ask for data already given.
- When users struggle, change the system, not the user. Make any adaptation visible and reversible.
→ `AX-1…AX-20`, `references/08-accessibility-inclusion.md`. Grade: [A].

### 11. Respect the user's choices: no dark patterns
Dark patterns appear in 95% of popular mobile apps and on about 11% of shopping sites, and most users fail to spot them. Some "test well" on conversion and usability metrics while harming the user.
- Undoing must be as easy as doing: cancel, unsubscribe, delete account and withdraw consent in the same channel and number of steps as sign-up.
- Defaults serve the user. No pre-checked add-ons, data sharing or marketing consent.
- Present accept and decline with equal visual weight and equal path length. Neutral decline copy; no confirmshaming.
- Show the full price up front. Urgency, scarcity, stock and activity messages must be true or absent. Ads must be clearly distinct from content.
- Ask once and remember the answer.
→ `ET-1…ET-22`. Grade: [A]/[B]; several rules are also legal requirements in the EU and US.

### 12. Design AI features for calibrated trust
AI features fail differently: capability is uncertain, outputs vary, and users over-generalize from one or two tries.
- Say what the feature can do **and how well**, before first use, in actionable terms ("good for X, often wrong about Y"), not as a bare confidence score.
- When unsure, do less but do it correctly: ask, offer a few options, or narrow the scope instead of acting.
- One step each to invoke, dismiss, stop and correct the AI. Make outputs editable in place.
- Give a retrievable "why" (and "why not") for outputs. Confirm before precise, costly, social or irreversible actions taken on the user's behalf.
- Don't let personality or humor promise intelligence the system lacks. Never fall back silently (for example, to a web search).
- Replace the blank prompt box with scaffolding for complex tasks: templates, task-specific examples, multiple outputs, history and diffs.
→ `AI-1…AI-25`, `references/10-ai-and-llm-interfaces.md`. Grade: [B]/[C]; the 18 Amershi guidelines are the most validated set.

### 13. Interrupt only when it is worth it
- Deliver non-urgent notifications at task boundaries or idle moments, not mid-task or during complex work.
- Match presentation to urgency: blocking, heads-up presentation roughly halves response time, so reserve it for genuinely urgent items.
- Make sender and value legible in the summary so people can triage at a glance. Let users postpone interruptions.
→ `FT-18`, `FT-19`, `AI-11`. Grade: [B].

### 14. Evaluate with the right method, and measure more than one thing
- One evaluator finds 20–51% of problems. Pool **3–5 independent** evaluators, or test with a few users, fix, and test again. "Five users" holds only when each user finds ~30% of problems; at ~20%, plan for 7+.
- Combine inspection with user testing; they find different problems.
- Measure effectiveness, efficiency and satisfaction **separately**; they correlate only about .16–.25. Preference is not performance, and self-reported speed or accuracy is not actual speed or accuracy.
- Use validated questionnaires (SUS, VisAWI, AttrakDiff) and report every item.
- Early on, sketch and critique several alternatives before usability-testing one.
→ `EV-1…EV-23`, `references/11-evaluation-and-measurement.md`. Grade: [A] for the process rules.

## Numbers card

| Decision | Value | Grade | Rule |
|---|---|---|---|
| Input echo / click acknowledgment | ≤ 0.1 s (≤ 0.2 s max) | B | FT-2 |
| Continuous feedback / animation frame | ≤ 0.1 s | B | FT-3 |
| Dynamic filter result update | < 100 ms | B | NS-2 |
| Routine request answered | ≤ 1–2 s | C | FT-4 |
| Show progress + cancel | waits beyond a few seconds | B | FT-7 |
| Free the user (background + notify) | > ~15 s | C | FT-6 |
| Transition / zoom animation | 0.3–1.0 s | B | FT-14 |
| Flashing | ≤ 3 per second | A | FT-15 |
| Working memory across a step | ≤ 3–4 new items | B | CL-2 |
| Absolute levels on one visual dimension | ≤ ~5–7 | B | CL-4 |
| Category colors | ≤ ~5 | C | TX-10 |
| Body text contrast / large text & UI | 4.5:1 / 3:1 | A | TX-1, TX-2 |
| Text resize / reflow width | 200% / 320 CSS px | A | TX-5 |
| Line length for reading | ~55–70 characters | B | TX-4 |
| Body size for older readers | ≥ 14 pt | B | TX-7 |
| Pointer target floor (web) | 24×24 CSS px (AA); 44×44 (AAA) | A | PT-2 |
| One-thumb touch target | ≥ 9.2 mm tap, ≥ 9.6 mm keypad | B | PT-1 |
| Touch target for ~95% hits, uncorrected | ~15 mm | B | PT-1 |
| Proximity grouping breaks at | gap ratio ≈ 1.5 | B | VH-2 |
| Evaluators per heuristic evaluation | 3–5 independent | A | EV-1 |
| Usability measures intercorrelation | r ≈ .16–.25 | A | EV-9 |

## Workflow: designing or building a UI

1. **Purpose and people.** Write down the screen's job, the primary user, their context (device, grip, attention, environment), and the one action that matters most.
2. **Structure.** Overview first, then filter and zoom, then details on demand. One primary action per screen. Order content by sequence of use, then frequency, then importance.
3. **Layout.** Group with spacing (principle 5), align to a grid, keep complexity moderate (principle 6), put identity and the key task where eyes land first.
4. **Controls.** Conventional controls in conventional places. Size and place targets by frequency (principle 8). Radios for up to about four options, a dropdown beyond that, checkboxes for multi-select.
5. **Text.** User's words, line length and size per principle 9, labels above fields, format rules stated up front.
6. **States.** Design every state, not just the happy path: empty, loading, partial, error, success, offline, permission denied, and first use. For AI features, design for correct, wrong, uncertain and refused outputs.
7. **Feedback and timing.** Apply principle 1 to every action and wait.
8. **Accessibility pass.** Run the `AX` checklist. Code must expose names, roles, states and structure.
9. **Ethics pass.** Run the `ET` audit on every choice, price, consent and cancellation screen.
10. **Self-review.** Review your own output with the procedure below before presenting it.

When you generate front-end code, encode these rules directly: semantic HTML and ARIA, visible focus styles, min target sizes, contrast-checked tokens, `prefers-reduced-motion` handling, inline validation on submit with field-level messages, disabled-after-submit buttons, and explicit loading and progress states.

## Workflow: reviewing a UI

Follow `references/12-automated-ui-review.md`. In short:

1. **Establish context first:** purpose, user, platform, stage (sketch, mockup, production). Ask for flows and missing states rather than assuming.
2. **Screen pass.** Check the five categories that matter on every screen: layout and grouping, color contrast, text readability, button clarity and affordance, and learnability of icons and labels.
3. **Flow pass.** Feedback and status, error prevention and recovery, consistency across screens, exits and undo. A single static screen cannot show these; say so.
4. **Accessibility pass** (`AX`) and **ethics pass** (`ET`).
5. **Merge and prioritize.** Deduplicate (report a pattern once with every instance). Rank by severity × frequency. Report fewer, better findings.
6. **State the limits** of what you could assess.

Write each finding as:

```
[Severity: severe | moderate | minor] [Confidence: high | medium | low] [Rule: FE-7, grade A]
Where: <screen / element / location>
Standard: <what good looks like, with the number if there is one>
Gap: <what this design does instead>
Fix: <one concrete change>
```

Guard against the known failure modes of model-based critique. It misses roughly 6 in 10 problems an expert finds, and about 4 in 10 of its findings are unhelpful. Specifically:
- Do not demand labels on universal icons (close ✕, search, cart).
- Do not "fix" differences that encode state (selected tab, primary button, error color).
- Do not flag differences too small to perceive.
- Do not list every principle when one explains the issue.
- Judge alignment and overlap on rendered pixels, not on element bounding boxes.
- Raise the reporting bar as a design gets more polished.
- Never declare one design "better" without pointing to specific regions as evidence.

## Folklore to correct

| Claim | What the research says |
|---|---|
| "Menus should have 7±2 items." | Miller (1956) was about absolute judgment and unaided recall, not scanning visible options. He called the recurring seven a likely coincidence. Visible options do not load working memory. |
| "Users can only handle 4 things on a screen." | Cowan's ~4 chunks is what people can *hold in mind* without support. It argues for keeping information visible, not for hiding it. |
| "Every response must be under 2 seconds." | Miller (1968) explicitly says no single limit is universal; acceptable delay depends on the task and whether the user has reached a closure. |
| "Users leave after 10 seconds." | In Card et al. (1991), ~10 s is the pacing of a unit task, not an attention cliff. |
| "Five users find 85% of problems." | Only when each user finds about 31% of problems. Discovery rates of 0.12–0.58 have been measured; plan from your own rate. |
| "Fitts' law covers all pointer movement." | It models rapid aimed pointing. Moving along a constrained path (submenus, drag tracks, drawing) follows the steering law, where time grows linearly with path length/width. The common MT = a + b·log₂(D/W + 1) is MacKenzie's Shannon form, not Fitts' original. |
| "Gestures are natural." | Few gestures are innate. They are invisible, ephemeral and need feedback, undo and conventions like any control. |
| "Beautiful means usable." | Beauty predicts *perceived* usability before use. After real use the link weakens, and appealing designs can hide real problems. |
| "Progress bars make variable delays acceptable." | Users prefer progress bars, but the claim that they make variable delays as good as constant ones was not supported. |

## Reference map

| File | Code | Load when you are working on |
|---|---|---|
| `references/01-visual-hierarchy-layout-aesthetics.md` | VH | Layout, grouping, visual hierarchy, complexity, aesthetics, credibility of look |
| `references/02-text-typography-color.md` | TX | Type, line length, contrast, color palettes, UI copy |
| `references/03-pointing-touch-gestures.md` | PT | Target size and placement, touch, mobile reach, gestures, drag |
| `references/04-feedback-timing-motion.md` | FT | Response times, loading and progress, animation, notifications |
| `references/05-cognition-consistency-learnability.md` | CL | Memory load, consistency, conventions, mental models, onboarding, expert paths |
| `references/06-forms-input-errors.md` | FE | Forms, validation, error messages, destructive actions, authentication |
| `references/07-navigation-search-data-display.md` | NS | Information architecture, menus, search and filters, tables and charts |
| `references/08-accessibility-inclusion.md` | AX | WCAG 2.2 AA, assistive tech, inclusive and adaptive design |
| `references/09-trust-ethics-dark-patterns.md` | ET | Credibility, persuasion, consent, pricing, cancellation, dark patterns |
| `references/10-ai-and-llm-interfaces.md` | AI | AI features, chat and agent UIs, explanations, prompting |
| `references/11-evaluation-and-measurement.md` | EV | Usability testing, heuristic evaluation, metrics, questionnaires |
| `references/12-automated-ui-review.md` | AR | Reviewing screenshots, mockups or UI code as an AI critic |

The paper-by-paper summaries behind these rules are in the repository's `research/summaries/` folder, and the full bibliography is in `research/BIBLIOGRAPHY.md`.
