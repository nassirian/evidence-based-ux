# How an AI should review a UI

> Instructions for Claude when it critiques screenshots, mockups, Figma frames or UI code: what model-based critique does well and badly, how to run the review, and how to report findings so a human can act on them. Evidence grades: **[A]** strong — replicated, large-N, meta-analytic, or an international standard; **[B]** moderate — one solid study or converging smaller studies; **[C]** weak — expert opinion, theory, small qualitative work, or extrapolation from lab psychology to UI.

## Rules

### AR-1. Know where model critique is reliable and where it is not
- **Do:** Report with normal confidence on single-screen visual and text checks: alignment, spacing, size consistency, contrast, text size and weight, redundant elements, unlabeled uncommon icons, grammar and jargon. Lower confidence on aesthetic judgement ("aesthetic and minimalist design"), visual hierarchy, and anything that depends on the flow across screens.
- **Why:** GPT-4 critique was most accurate on Recognition rather than Recall, Match between System and Real World, and Consistency and Standards (mostly alignment and size checks), and worst on Aesthetic and Minimalist Design; emphasis results were bimodal (Duan 2024a). Experts found GPT-4 strong on subtle visual issues and on text fixes with replacement copy (12 of 12 participants) (Duan 2024a). Across automated tools, single-screen visual checks are where automation is reliable; flow-level heuristics and aesthetics remain weak (Duan 2024b; Wu 2024).
- **Evidence:** [B] — (Duan 2024a; Duan 2024b; Wu 2024).
- **Limits:** Results are for GPT-4 (2023), Gemini Pro Vision and 2024 VLMs. Newer models may differ, but no source shows the failure modes are gone.

### AR-2. Expect to miss most problems a human expert would find, and say so
- **Do:** Treat your review as one evaluator's pass, not a complete audit. State that a human review or user test is still needed for anything high-stakes. Never claim the list is exhaustive.
- **Why:** Against 100 known violations, GPT-4 had precision 0.603 and recall 0.380, vs 0.829 and 0.336 for the average expert; 62 violations were found only by humans, 29 by both, 9 only by GPT-4 (Duan 2024a). Only 13.1% of zero-shot Gemini comments were valid (Duan 2024b). Any single evaluator, human or not, finds a fraction: 20–51% of known problems (Nielsen 1990), 33% on average (Nielsen 1993).
- **Evidence:** [A] — (Duan 2024a; Duan 2024b; Nielsen 1990; Nielsen 1993).
- **Limits:** Precision and recall depend on the guideline set and the screens chosen.

### AR-3. Establish purpose, user, platform and stage before judging anything
- **Do:** Before critiquing, identify: what the screen is for (one-sentence caption), who uses it and in what context, the platform (iOS, Android, web, desktop), and the design stage (sketch, mockup, polished, shipped). Ask if these cannot be inferred. Judge each element against that stated purpose, not against generic taste.
- **Why:** UIClip judged quality together with relevance to a caption of the screen's purpose (Wu 2024). Preference between aesthetic and plain designs reversed with the use framing (Hartmann 2008). UX depends on context and the user's internal state (Law 2009). Method and critique must fit the design stage; rough early ideas should not be judged like finished prototypes (Greenberg 2008).
- **Evidence:** [B] — (Wu 2024; Hartmann 2008; Law 2009; Greenberg 2008).
- **Limits:** When purpose is unknown, state the assumption you used.

### AR-4. Ground every critique in explicit guideline text
- **Do:** Review against the rules in this skill's reference files and cite the rule ID for each finding (VH, TX, PT, FT, CL, FE, NS, AX, ET, AI, EV, AR). Do not produce free-form "general UI feedback."
- **Why:** Removing heuristics from the prompt cut helpful findings from 38 to 14; a generic "UI feedback" prompt gave 24 helpful findings out of 57 (Duan 2024a).
- **Evidence:** [B] — (Duan 2024a).
- **Limits:** Guidelines also cause over-application (AR-9), so grounding needs the guards in this file.

### AR-5. Run several passes with different lenses
- **Do:** Do not stop after one sweep. Make separate passes per category (AR-6), then a flow pass, an accessibility pass and an ethics pass (see Review procedure). Merge afterward.
- **Why:** Independent evaluations find different problems, and aggregating about five finds roughly two thirds where one finds 20–51% (Nielsen 1990). Detection is not a cumulative scale, so a "good" pass still misses easy problems (Nielsen 1990).
- **Evidence:** [B] — (Nielsen 1990; Nielsen 1993). Applying this to repeated passes by one model is an extrapolation.
- **Limits:** Passes by the same model are not truly independent; they reduce omissions but do not replace human evaluators.

### AR-6. Check the five core screen-level categories every time
- **Do:** For each screen, check: (1) layout: positioning, alignment, visual hierarchy, logical grouping, simplicity; (2) color contrast of text, icons, buttons and background; (3) text readability: font size and weight; (4) buttons: visual design, clarity of purpose, whether a button would simplify the task; (5) learnability: clarity of icons, regions, screen and labels.
- **Why:** These five clusters emerged from 3,059 expert critiques of 983 mobile screens (Duan 2024b). They map onto the CRAP principles used by UIClip (contrast, repetition, alignment, proximity) (Wu 2024).
- **Evidence:** [B] — (Duan 2024b; Wu 2024).
- **Limits:** Built from older Android screens; the dataset under-represents error prevention and system status (2 critiques), so these categories alone are not enough (AR-7, AR-17).

### AR-7. Hunt for global and contextual problems on purpose
- **Do:** Ask explicitly: Does the content match the screen's purpose? Is key information hidden or missing? Are there redundant navigation paths? Does any data look wrong for its context? Is anything the user needs to decide or recover missing?
- **Why:** Humans found these global issues and the LLM mostly missed them (Duan 2024a). Missing-feature problems are hard to find even for human inspectors working from mockups (Nielsen 1993).
- **Evidence:** [B] — (Duan 2024a; Nielsen 1993).
- **Limits:** Global findings need the purpose from AR-3; without it, mark them low confidence.

### AR-8. Locate issues on rendered pixels, and separate critique from localization
- **Do:** Judge alignment and overlap on the rendered image, not on bounding boxes or layer geometry. First decide what the problems are, then in a separate step locate each one. When you need coordinates, use rulers or numbered patches along the image edges, not a full grid overlay. Name each element by its visible label and position.
- **Why:** Working from bounding boxes produced phantom overlaps and missed center alignment of different-size elements (8 of 12 experts) (Duan 2024a). Combining critique and localization degraded critique quality; bounding-box IoU was 0.004 with the screenshot alone, 0.186 with edge coordinates, 0.222 with numbered patches, and near zero with a grid overlay (Duan 2024b). Running detection and rephrasing as one call lowered helpful findings from 38 to 31 (Duan 2024a).
- **Evidence:** [B] — (Duan 2024a; Duan 2024b).
- **Limits:** Even the best localization was weak in absolute terms.

### AR-9. Do not over-apply guidelines
- **Do:** Before reporting a violation, ask whether the guideline applies here. Do not demand text labels on universally recognized icons (close ✕, cart or bag). Before calling a difference "inconsistent", check whether it encodes state or emphasis (selected tab, primary action, current page). Do not apply every guideline to every element.
- **Why:** Over-application without context was the most common complaint (12 of 12 experts), including labels on universal icons and "fixing" a deliberately thicker selected-tab underline (Duan 2024a). GPT-3.5 applied every guideline to every element and produced 228 violations of which 23 were helpful (Duan 2024a).
- **Evidence:** [B] — (Duan 2024a).
- **Limits:** "Universal" icons vary by platform and audience; if unsure, ask.

### AR-10. Report fewer, better findings
- **Do:** Cap the list. Keep only findings you can tie to a specific element, rule and consequence. Drop speculative or vague items. Prefer five well-supported findings over twenty weak ones.
- **Why:** Zero-shot generation produced about twice as many comments of lower validity than few-shot (Duan 2024b). With precision near 0.6, roughly 4 in 10 LLM findings are not helpful (Duan 2024a). Vague fixes were a recurring complaint (5 of 12) (Duan 2024a).
- **Evidence:** [B] — (Duan 2024b; Duan 2024a).
- **Limits:** Do not drop a severe finding to meet a cap.

### AR-11. Deduplicate and respect dismissals
- **Do:** Report a repeated pattern once and list every affected element. If the user has dismissed or explained a finding, do not raise it again under a different heuristic or wording.
- **Why:** The same feedback repeated per element (6 of 12 experts), and after a dismissal the model re-raised the same issue under another heuristic (5 participants) (Duan 2024a). Critique the template once when screens differ only in content (Deka 2017).
- **Evidence:** [B] — (Duan 2024a; Deka 2017).
- **Limits:** Raise a dismissed issue again only if the design changed in a way that makes it worse, and say so.

### AR-12. Raise the bar as the design gets better
- **Do:** On polished designs and in later review rounds, raise the reporting threshold. Report only findings you are confident change user outcomes. Say plainly when you have few or no substantive findings.
- **Why:** In iterative use, accuracy fell each round: 52% accurate in round one, 39% after edits, and 51% of later suggestions were rated slightly or not helpful (Duan 2024a).
- **Evidence:** [B] — (Duan 2024a).
- **Limits:** A polished look can hide flow and content problems; still run AR-7 and the flow pass.

### AR-13. Do not trust your own verdict on which design is better without region-tied evidence
- **Do:** When asked to compare designs, compare pairwise against the stated purpose. Tie every claim to specific regions in each design. Name only the principles that actually drive the difference. Be cautious with bold or unconventional designs and with iOS vs Android conventions.
- **Why:** GPT-4V picked the better design 51.58% of the time, near chance, and gave realistic-sounding but inaccurate reasoning; a small trained model reached 75.12% (Wu 2024). VLMs listed all four CRAP principles almost every time, inflating recall (Gemini 87.11%, GPT-4V 84.57%) until adjusted for choice (49.17%, 46.58%) (Wu 2024). Designers themselves agreed only modestly (Krippendorff's α = 0.37) (Wu 2024).
- **Evidence:** [B] — (Wu 2024).
- **Limits:** Models evaluated were 2024 versions.

### AR-14. Score aesthetics and usability separately, and do not infer one from the other
- **Do:** If you give ratings, rate visual quality and usability separately. Note that they tend to move together, and that attractiveness does not prove usability.
- **Why:** Expert aesthetics and usability ratings correlated r = 0.875 (Duan 2024b). Viewing-only judgements inflate the aesthetics–usability link; it falls after real use (Moshagen 2010). Aesthetic metaphor sites were preferred despite worse perceived usability and more reported problems (Hartmann 2008).
- **Evidence:** [B] — (Duan 2024b; Moshagen 2010; Hartmann 2008).
- **Limits:** A screenshot review is itself a viewing-only judgement, so treat usability ratings from it as low confidence.

### AR-15. Use computational metrics as comparisons, not verdicts
- **Do:** When you can compute or estimate metrics (clutter via edge density and contour congestion, number of colors and colorfulness, grid quality, white space, symmetry, saliency, predicted search time), compare each with a distribution of peer designs, not an absolute threshold. Run a color-blindness simulation for the three common types and check that meaning survives. Report trade-offs across several objectives instead of a single aggregate score. Attach the principle and evidence strength to each metric finding.
- **Why:** AIM bundles 17 published metrics in four categories (color perception, perceptual fluency, visual guidance, accessibility) and presents each against a histogram of other designs, with no thresholds (Oulasvirta 2018). Objectives conflict: minimizing clutter makes everything one color while optimizing search makes everything a unique color (Todi 2016). Weighted-sum aggregation is the most weight-sensitive approach (Oulasvirta 2020).
- **Evidence:** [B] — (Oulasvirta 2018; Oulasvirta 2020; Todi 2016).
- **Limits:** AIM is a poster with no validation study; metrics were developed mostly on web pages.

### AR-16. Do not flag differences users cannot perceive
- **Do:** Skip findings about one- or two-pixel offsets, near-identical sizes or barely different shades unless they create a visible misalignment, a broken grid line, or a contrast failure. Prefer validated predictive models (Fitts' law, KLM, visual search models) over unvalidated rules when making efficiency claims, and state their error bands.
- **Why:** Humans seldom can discern very small changes in position, size or color (Oulasvirta 2020). Validated models are preferred over Boolean heuristics, which have conflict and validity problems (Oulasvirta 2020). KLM is accurate to about 21% per task, so smaller predicted differences are noise (Card 1980).
- **Evidence:** [B] — (Oulasvirta 2020; Card 1980).
- **Limits:** Consistency of tokens in code (for example two near-identical grays) can still be worth noting as maintenance debt, labeled as such, not as a usability problem.

### AR-17. State what a static review cannot assess
- **Do:** End every review with a short "Not assessed" list. Typical entries: flow-level feedback and system status, error prevention and recovery, cross-screen consistency, help, gated screens (login, verification, payment) you were not shown, awareness of features and transition to efficient use, performance after repeated use, real content and data volume, and assistive-technology behavior that cannot be seen in pixels.
- **Why:** The expert critique dataset had almost no error-prevention or system-status critiques, and flow-level heuristics were missing (Duan 2024b). Think-aloud-style inspection surfaced no transition issues and fewer awareness issues than a coaching protocol (Grossman 2009). Automated crawling missed gated screens and had 26% lower coverage than hybrid exploration (Deka 2017). Optimized layouts paid off only after first exposure (Todi 2016).
- **Evidence:** [B] — (Duan 2024b; Grossman 2009; Deka 2017; Todi 2016).
- **Limits:** If you are given a full flow, code or recordings, assess what you can and shorten the list.

### AR-18. Compare feature placement to domain conventions
- **Do:** Check where key features (logo, search, main menu, account, cart, primary action) sit compared with the dominant placement in apps or sites of the same category and platform. Flag atypical placement of key features as a findability risk, and weigh it against any stated branding reason.
- **Why:** Moving features to where users expected them from prior browsing cut search time from 2.8 s to 2.5 s and fixations from 3.4 to 2.6 (Todi 2018). Rule-generated UIs that accounted for expected element locations were twice as fast (cited in Oulasvirta 2020).
- **Evidence:** [B] — (Todi 2018; Oulasvirta 2020).
- **Limits:** Todi 2018 tested 16 users in one domain (shopping).

### AR-19. Reason by layout structure, and ask for missing states
- **Do:** Identify the screen type by its structure (list, login, dialog, image grid, form) and compare with typical structures of that type. Treat screens with the same structure and different content as one design state. Ask for empty, error, loading and gated states if they were not provided.
- **Why:** Layout-structure similarity retrieved comparable screens independent of content; structurally identical screens can look different because content differs (Deka 2017). Automated exploration alone missed gated experiences such as login walls (Deka 2017).
- **Evidence:** [C] — (Deka 2017).
- **Limits:** Rico norms (for example about eight interactive elements per screen) are descriptive, not quality targets.

### AR-20. Use similar examples when you have them
- **Do:** If reference critiques or exemplar screens are available, choose those most similar to the target in both visual appearance and task, never at random.
- **Why:** Few-shot examples selected by visual plus task similarity gave the best whole-screen comment quality (0.58) and rating accuracy (0.53); random selection was clearly worse in the region task (0.31 vs 0.44) (Duan 2024b). Few-shot plus coordinates raised quality from 0.31 to 0.48, still below human critique at 0.75 (Duan 2024b).
- **Evidence:** [B] — (Duan 2024b).
- **Limits:** Gains were measured on Gemini Pro Vision with at most 8 examples.

### AR-21. Write each finding as standard, gap, concrete fix
- **Do:** For each finding, state the expected standard (with rule ID), the gap in this design (with element location), and a concrete step that closes it. For copy problems, give the replacement text.
- **Why:** Duan's tool phrased findings in Sadler's format (standard, gap, step) linked to the exact element; experts valued concrete fixes and complained about vague ones (Duan 2024a). Inspection methods rarely produce fixes unless asked (Nielsen 1990).
- **Evidence:** [B] — (Duan 2024a; Nielsen 1990).
- **Limits:** See Finding format below.

### AR-22. Suggest beside the work; never overwrite it
- **Do:** Present fixes as optional suggestions next to the designer's work. Do not silently rewrite their design or code. Offer both small local fixes and, where useful, one or two clearly different global alternatives. Keep recoloring suggestions subtle.
- **Why:** Sketchplore's suggestions appeared on the side and never overrode the designer's work; designers liked global "explore" alternatives most, 8 of 10 saved an aided design, and garish recolor suggestions were disliked (Todi 2016). Most professional designers included optimizer suggestions in final designs (Oulasvirta 2020).
- **Evidence:** [B] — (Todi 2016; Oulasvirta 2020).
- **Limits:** If the user explicitly asks you to apply fixes, do so, and list each change.

### AR-23. Report confidence and evidence grade on every finding
- **Do:** Give each finding a confidence (high / medium / low) and the evidence grade of the rule it cites. Lower confidence for vague heuristics, for flow-level claims from a single screen, and for aesthetic judgements. Present the review as advice for a human to decide on.
- **Why:** Expert raters agreed only slightly on LLM suggestions (Fleiss' κ 0.112 accuracy, 0.100 helpfulness) (Duan 2024a); expert agreement on critiques was fair (κ about 0.29–0.31) (Duan 2024b); designers agreed at α = 0.37 on which UI was better (Wu 2024); novice evaluators' any-two agreement was 0.046 (Hvannberg 2007).
- **Evidence:** [B] — (Duan 2024a; Duan 2024b; Wu 2024; Hvannberg 2007).
- **Limits:** Confidence is your own estimate; it is not calibrated by any source.

## Finding format

Use this structure for every finding. It combines Sadler's standard–gap–fix phrasing (Duan 2024a) with the structured problem report from Hvannberg 2007.

```
[ID] <Short title>
Rule:       <rule ID, e.g. VH-3, AX-2, AR-9>  · Evidence grade: <A|B|C>
Where:      <screen name> › <element, by visible label and position; coordinates if requested>
Standard:   <what the rule expects, one sentence>
Gap:        <what this design does instead, and the likely user difficulty>
Fix:        <concrete change; replacement copy if it is a text problem>
Severity:   <severe | moderate | minor>
Frequency:  <how often users meet it: every screen / core task / edge case>
Confidence: <high | medium | low> — <one-line reason, e.g. "static screen only">
```

- **Severity** uses Hvannberg's three levels. Severe: blocks or seriously derails a core task, causes data loss, or excludes a user group. Moderate: slows or confuses users but they recover. Minor: cosmetic or rare friction. If the user's team uses a 0–4 scale, map severe to 3–4, moderate to 2, minor to 1, and say that it is a mapping.
- **Priority** is severity combined with frequency. A moderate problem on every screen of the core task can outrank a severe problem in a rare edge case. Order the report by priority.
- Group repeated instances under one finding (AR-11).

## Review procedure

1. **Gather context and purpose (AR-3).** Write a one-sentence caption of what each screen is for, the user and context, platform, and stage. Note what you were given (screenshot, frame, code, flow) and what is missing. Ask for missing states (empty, error, loading, gated) if they matter (AR-19).
2. **Per-screen pass by category (AR-6).** Go through layout and grouping, contrast, text readability, buttons, and learnability of icons and labels. Check feature placement against domain conventions (AR-18). Judge on rendered pixels (AR-8). Apply guards (AR-9, AR-16).
3. **Global pass (AR-7).** Check purpose vs content, hidden key information, redundant paths, data that does not fit its context.
4. **Flow pass.** If more than one screen is available: feedback and system status after each action, error prevention and recovery, exits and undo, cross-screen consistency, and help. If only one screen is available, list these as not assessed (AR-17).
5. **Accessibility pass.** Check contrast and color-only meaning (simulate the three common color-vision deficiencies where possible) (AR-15), text size and scaling, target sizes, and programmatic structure if code is available. Cite AX rules. Do not generalize evidence from one disability group to others (EV-22).
6. **Ethics pass.** On choice, consent, pricing and cancellation screens, check for asymmetric burden between options, restricted choices, covert influence, deception, hidden information, and nagging. Cite ET rules. Recommend testing against a neutral baseline where uptake matters (EV-21).
7. **Dedupe and merge (AR-11).** Combine repeats into one finding listing all instances. Remove findings the user already dismissed.
8. **Filter and prioritize (AR-10, AR-12).** Drop low-value and sub-perceptual items. Order by severity × frequency. Keep the list short.
9. **Write findings (AR-21, AR-23)** in the Finding format, with fixes beside the work, not applied to it (AR-22).
10. **State what could not be assessed (AR-17)** and recommend the cheapest next evaluation step (for example three to five independent human reviewers, or a think-aloud test of the flagged flow) (EV-1, EV-6).

## Do not flag
- Missing text labels on universally recognized icons (close ✕, back arrow, cart or bag, search magnifier) unless the audience or platform makes them ambiguous (Duan 2024a).
- Visual differences that encode state or emphasis: a selected tab, the primary button, the current page, an error state (Duan 2024a).
- Overlaps or misalignments inferred only from bounding boxes or layer geometry and not visible in the render (Duan 2024a).
- Differences below perceptual thresholds in position, size or color (Oulasvirta 2020).
- The same issue once per element; report it once with all instances (Duan 2024a).
- An issue the user has dismissed, under a new heuristic name (Duan 2024a).
- All four CRAP principles by default; name only the ones that drive the finding (Wu 2024).
- Every guideline against every element (Duan 2024a).
- Content differences between screens that share one template; critique the template (Deka 2017).
- Flow-level failures (missing feedback, no undo, no error recovery) as confirmed defects when you have seen only a static screen; list them under "Not assessed" or mark them low confidence (Duan 2024b).
- Rough sketches judged as if they were finished visual designs (Greenberg 2008).
- Usability verdicts inferred from attractiveness alone (Moshagen 2010; Hartmann 2008).
- App-store ratings as evidence of screen quality; they barely correlate with expert ratings (Duan 2024b).
- A "which is better" verdict with no region-tied evidence (Wu 2024).

## Numbers at a glance
| Parameter | Value | Grade | Source |
|---|---|---|---|
| GPT-4 critique precision / recall / F1 | 0.603 / 0.380 / 0.466 | B | Duan 2024a |
| Expert precision / recall / F1 | 0.829 / 0.336 / 0.478 | B | Duan 2024a |
| Violations found only by humans / both / only GPT-4 | 62 / 29 / 9 (of 100) | B | Duan 2024a |
| Helpful findings with vs without heuristics in prompt | 38 vs 14 | B | Duan 2024a |
| GPT-3.5 total vs helpful violations | 228 vs 23 | B | Duan 2024a |
| Accuracy drop over iterations | 52% → 39% accurate | B | Duan 2024a |
| Zero-shot Gemini comment validity | 13.1% | B | Duan 2024b |
| Comment quality: zero-shot / few-shot + coordinates / human | 0.31 / 0.48 / 0.75 | B | Duan 2024b |
| Aesthetics–usability rating correlation | r = 0.875 | B | Duan 2024b |
| Expert agreement on critiques | κ ≈ 0.29–0.31 | B | Duan 2024b |
| GPT-4V picking the better design | 51.58% | B | Wu 2024 |
| UIClip picking the better design | 75.12% | B | Wu 2024 |
| Designer agreement on better design | α = 0.37 | B | Wu 2024 |
| Recall inflation from listing all CRAP principles | 87.11% → 49.17% (Gemini) | B | Wu 2024 |
| AIM metrics | 17 in 4 categories | C | Oulasvirta 2018 |
| Familiar placement: search time / fixations | 2.8 → 2.5 s / 3.4 → 2.6 | B | Todi 2018 |
| Automation-only coverage vs hybrid crawl | 26% lower | B | Deka 2017 |
| Mean interactive elements per Android screen | ~8 (descriptive) | C | Deka 2017 |
| Single-evaluator problem discovery | 20–51% | A | Nielsen 1990 |
| Novice any-two evaluator agreement | 0.046 | B | Hvannberg 2007 |
| Learnability issues: question-suggestion vs think-aloud | 7.55 vs 2.8 | B | Grossman 2009 |

## Common misreadings
- "An LLM review is a complete heuristic evaluation." — It found 38% of known violations and 62 of 100 were found only by humans (Duan 2024a).
- "More findings means a better review." — Higher-volume output had lower validity (Duan 2024b), and applying every guideline produced 228 findings with 23 helpful (Duan 2024a).
- "A vision model can tell which design is better." — General VLMs were near chance (Wu 2024).
- "Listing all four CRAP principles is thorough." — It inflates recall without adding accuracy (Wu 2024).
- "Every inconsistency is a defect." — Some differences deliberately encode state (Duan 2024a).
- "A good-looking screen is usable." — Aesthetics and usability ratings correlate strongly on viewing, but that link weakens after real use (Duan 2024b; Moshagen 2010).
- "Metrics give a pass/fail." — AIM provides no thresholds; compare with peer designs (Oulasvirta 2018).

## Review checklist
- [ ] AR-1: Are confidence levels lower for aesthetic, hierarchy and flow-level findings than for alignment, contrast and copy findings?
- [ ] AR-2: Does the review say it is one evaluator's pass and not exhaustive?
- [ ] AR-3: Is the screen's purpose, user, platform and stage stated before the findings?
- [ ] AR-4: Does every finding cite a rule ID from the skill?
- [ ] AR-5: Were separate category, flow, accessibility and ethics passes made?
- [ ] AR-6: Were layout, contrast, text readability, buttons and learnability checked on each screen?
- [ ] AR-7: Were global issues (purpose vs content, hidden information, redundant paths, wrong data) checked?
- [ ] AR-8: Are locations based on rendered pixels and given by visible label and position?
- [ ] AR-9: Are universal icons and state-encoding differences left unflagged?
- [ ] AR-10: Is the list short, with each finding tied to an element, rule and consequence?
- [ ] AR-11: Are repeats merged and dismissed issues not re-raised?
- [ ] AR-12: Was the threshold raised for a polished design or a later round?
- [ ] AR-13: Is any "better design" verdict backed by region-tied evidence against the purpose?
- [ ] AR-14: Are aesthetics and usability judged separately?
- [ ] AR-15: Are metric findings compared with peer designs, with color-blindness simulation and stated trade-offs?
- [ ] AR-16: Are sub-perceptual differences left out?
- [ ] AR-17: Is there a "Not assessed" list?
- [ ] AR-18: Is key-feature placement compared with domain conventions?
- [ ] AR-19: Were missing states (empty, error, loading, gated) requested or noted?
- [ ] AR-20: If examples were used, were they chosen by visual and task similarity?
- [ ] AR-21: Does each finding give standard, gap and a concrete fix?
- [ ] AR-22: Are fixes offered beside the work rather than applied silently?
- [ ] AR-23: Does each finding carry a confidence level and evidence grade?

## Sources
- Card, S. K., Moran, T. P., Newell, A. (1980). *The keystroke-level model for user performance time with interactive systems*. Communications of the ACM. https://doi.org/10.1145/358886.358895
- Deka, B., et al. (2017). *Rico: a mobile app dataset for building data-driven design applications*. UIST '17. https://doi.org/10.1145/3126594.3126651
- Duan, P., et al. (2024a). *Generating automatic feedback on UI mockups with large language models*. CHI '24. https://doi.org/10.1145/3613904.3642782
- Duan, P., et al. (2024b). *UICrit: enhancing automated design evaluation with a UI critique dataset*. UIST '24. https://doi.org/10.1145/3654777.3676381
- Greenberg, S., Buxton, B. (2008). *Usability evaluation considered harmful (some of the time)*. CHI '08. https://doi.org/10.1145/1357054.1357074
- Grossman, T., Fitzmaurice, G., Attar, R. (2009). *A survey of software learnability: metrics, methodologies and guidelines*. CHI '09. https://doi.org/10.1145/1518701.1518803
- Hartmann, J., Sutcliffe, A., De Angeli, A. (2008). *Towards a theory of user judgment of aesthetics and user interface quality*. ACM TOCHI. https://doi.org/10.1145/1460355.1460357
- Hvannberg, E. T., Law, E. L.-C., Lárusdóttir, M. K. (2007). *Heuristic evaluation: comparing ways of finding and reporting usability problems*. Interacting with Computers. https://doi.org/10.1016/j.intcom.2006.10.001
- Law, E. L.-C., Roto, V., Hassenzahl, M., Vermeeren, A. P. O. S., Kort, J. (2009). *Understanding, scoping and defining user experience: a survey approach*. CHI '09. https://doi.org/10.1145/1518701.1518813
- Moshagen, M., Thielsch, M. T. (2010). *Facets of visual aesthetics*. IJHCS. https://doi.org/10.1016/j.ijhcs.2010.05.006
- Nielsen, J., Landauer, T. K. (1993). *A mathematical model of the finding of usability problems*. CHI '93. https://doi.org/10.1145/169059.169166
- Nielsen, J., Molich, R. (1990). *Heuristic evaluation of user interfaces*. CHI '90. https://doi.org/10.1145/97243.97281
- Oulasvirta, A., et al. (2018). *Aalto Interface Metrics (AIM)*. UIST '18 Adjunct. https://doi.org/10.1145/3266037.3266087
- Oulasvirta, A., Dayama, N. R., Shiripour, M., John, M., Karrenbauer, A. (2020). *Combinatorial optimization of graphical user interface designs*. Proceedings of the IEEE. https://doi.org/10.1109/jproc.2020.2969687
- Todi, K., Weir, D., Oulasvirta, A. (2016). *Sketchplore: sketch and explore with a layout optimiser*. DIS '16. https://doi.org/10.1145/2901790.2901817
- Todi, K., Jokinen, J., Luyten, K., Oulasvirta, A. (2018). *Familiarisation: restructuring layouts with visual learning models*. IUI 2018. https://doi.org/10.1145/3172944.3172949
- Wu, J., Peng, Y.-H., et al. (2024). *UIClip: a data-driven model for assessing user interface design*. UIST '24. https://doi.org/10.1145/3654777.3676408
