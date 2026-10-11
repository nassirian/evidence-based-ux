# Memory, mental models, consistency and learnability

> Scope: how to design screens and flows around the limits of human memory, users' learned conventions and mental models, and the path from novice to expert. Evidence grades: **[A]** strong — replicated, large-N, meta-analytic, or an international standard; **[B]** moderate — one solid study or converging smaller studies; **[C]** weak — expert opinion, theory, small qualitative work, or extrapolation from lab psychology to UI.

## Rules

### CL-1. Keep needed information visible instead of making users recall it
- **Do:** Show the objects, options and context the user needs at each step. Re-display the user's own input next to the result. Recapitulate earlier choices (selected item, filters, values from a previous screen) on the screen where they are used. Show small option sets explicitly instead of asking users to type a remembered value. When a control's effect depends on earlier actions, show that context.
- **Why:** In a corpus of 249 usability problems, "seeing/pointing vs. remembering/typing" was the single best explanation for serious problems (22% of the 82 serious problems; 7% of all problems) (Nielsen 1994). Re-displaying the entered phone number with the result was the most-found problem in a dialogue critique (95% of 77 entries) (Molich 1990), and overwriting the entered number was found by 95% of evaluators in a separate experiment (Nielsen 1990). Smith & Mosier codify this as 2.0/11 Context for Displayed Data, 3.0/9 Displayed Context, 3.1.3/16 Explicit Option Display and 4.4/13 Displayed Context, and state that designs should not rely on users remembering prior actions (Smith 1986). Pure short-term capacity is only about 4 chunks (Cowan 2001), so anything carried across steps competes for very few slots.
- **Evidence:** [B] — (Nielsen 1994; Molich 1990; Nielsen 1990; Smith 1986; Cowan 2001).
- **Limits:** Nielsen 1994 used a single rater on previously found problems. Showing everything conflicts with "only necessary data displayed" (Smith 1986, 2.0/2); show what the current step needs, not all history.

### CL-2. Do not ask users to hold more than 3–4 new items in mind across a step
- **Do:** Count the unrelated items (codes, numbers, settings, comparison values) a user must carry from one screen, field or moment to the next. Keep it at 3 or fewer for general audiences. If more are needed, keep them on screen, let users copy/paste, or carry them forward automatically. Design for the low end of individual capacity (about 2–3), not the mean.
- **Why:** When rehearsal and recoding are blocked, adults hold about 4 chunks (group means 3–5); individuals range from about 2 to almost 6; children hold fewer (ignored-speech means 3.51 adults, 2.99 4th graders, 2.34 1st graders) (Cowan 2001). Change detection is near perfect for 1–3 objects and drops beyond 4 (Cowan 2001). Miller's "seven" is a compound estimate inflated by rehearsal and chunking (Cowan 2001; Miller 1956).
- **Evidence:** [B] — (Cowan 2001; Miller 1956). The capacity limit itself is strong; the UI transfer is moderate.
- **Limits:** The limit applies to items that must be held without external support. It does not limit how many visible, recognizable options a screen may show (see Common misreadings). Commentators dispute the fixed-slot interpretation (Cowan 2001).

### CL-3. Chunk long strings and group related items so each takes one memory slot
- **Do:** Break codes, IDs, phone and account numbers into groups of about 3–4 characters with visible separators. Keep coded items users must enter to 5–7 characters or fewer. Group related fields and options into labeled clusters, and use spacing, common regions or headings so each cluster reads as one unit.
- **Why:** Memory span is roughly constant in chunks, not bits: about 7–8 decimal digits but only about 5 monosyllabic words; recoding binary digits into larger chunks let one trained subject recall about 40 digits (Miller 1956). Recall comes in bursts of about 4 items, and theoretical optimal chunk size is about 3.6 per hierarchy level (Cowan 2001). Smith & Mosier 1.0/15 limits coded data items to 5–7 characters (Smith 1986).
- **Evidence:** [B] — (Miller 1956; Cowan 2001; Smith 1986). Chunking itself is strong; the UI transfer is moderate.
- **Limits:** A chunk is only a chunk if the user already knows the pattern; unfamiliar groupings give no benefit. Visual grouping cues are covered in the perception reference.

### CL-4. Encode at most about 5–7 absolute levels on any one visual dimension
- **Do:** If users must identify a value absolutely (which hue, which size, which brightness level), use no more than about 5–7 levels per dimension, and no more than 5 colors for category coding. For more categories, combine dimensions redundantly or add text labels. Prefer designs that let users compare values side by side (adjacent legend, relative position) over designs that need absolute identification.
- **Why:** Unidimensional absolute judgment averages 2.6 bits (SD 0.6), about 6.5 categories (range 3–15); examples: pitch 2.5 bits, loudness 2.3, hue 3.1, line length 2.6–3.0 (Miller 1956). Adding dimensions raises total capacity (dot in square 4.6 bits, about 24 positions) but lowers per-dimension accuracy (Miller 1956). Relative judgment is one of three ways to beat the limit (Miller 1956). Smith & Mosier 2.6/26 caps category color codes at 5 (Smith 1986).
- **Evidence:** [B] — (Miller 1956; Smith 1986). The absolute-judgment limit is strong lab psychology; the per-dimension UI cap is an extrapolation.
- **Limits:** Data are pre-1956 and often pooled across subjects. Exceptions exist (absolute pitch). Color-specific rules (contrast, color-blind safety) are in the visual and accessibility references.

### CL-5. Make the same thing look, sound and behave the same everywhere
- **Do:** Use one term per concept. Keep the same function labeled and iconed the same across screens. Keep repeated navigation in the same relative order on every page. Keep help/contact mechanisms in the same relative order on every page. Put recurring elements (title, messages, prompts, error messages) in the same location on every screen. Keep codes (colors, symbols) consistent across displays.
- **Why:** Consistency was the heuristic that explained the most usability problems (23% marginal coverage across 249 problems) (Nielsen 1994). Smith & Mosier call consistency "the single objective on which experts agree" and cite consistent wording among simple changes that gave 25% faster data entry and 25% fewer errors (Keister & Gallaway, reported in Smith 1986); see 2.0/6, 2.5/1, 2.6/7, 3.0/6 and 4.0/6 (Smith 1986). Molich & Nielsen list "Be consistent" and one term per concept (Molich 1990). WCAG requires 3.2.3 Consistent Navigation (AA), 3.2.4 Consistent Identification (AA) and 3.2.6 Consistent Help (A) (W3C 2023).
- **Evidence:** [A] — (Nielsen 1994; Smith 1986; Molich 1990; W3C 2023).
- **Limits:** Consistency within the product can conflict with following an external convention; when they conflict, the platform convention usually wins (CL-6). Consistency inspection works best with designers from several projects (Nielsen 1994 coverage data is single-rater).

### CL-6. Follow platform and real-world conventions over a locally "better" design
- **Do:** Use the platform's standard controls, gestures, icons, placements and terminology. Depart from a convention only with strong, tested justification. Check that target users actually share a convention by observing a few (3–5) of them in their normal setting.
- **Why:** Conventions "require a community of practice" and are slow to adopt and slow to go away; on screens most so-called affordances are really conventions (Norman 1999). Norman argues "standards are more important than optimization" (QWERTY) and that gesture interfaces need standardized conventions (Norman 2010). Real-world conventions added 4% coverage in Nielsen's problem corpus, and a familiar conceptual model was distinctive for serious problems (Nielsen 1994). Smith & Mosier 2.0/4 requires displays consistent with user conventions and warns that "smart shortcuts" that break consistent control are "perhaps the most frequent mistake" (Smith 1986).
- **Evidence:** [B] — (Norman 1999; Norman 2010; Nielsen 1994; Smith 1986).
- **Limits:** Norman's essays are opinion without data. Conventions are culture-specific (CL-7). A convention that harms users (e.g., a dark pattern) is not a reason to copy it.

### CL-7. Put key features where users have learned to look for them
- **Do:** Place common features (logo, search, main menu, account, cart, primary keypad layout) where peer products in the same domain and locale place them. When localizing, check which convention the target culture uses (e.g., keypad orientation, progress symbols). When deviating for branding, count the visual-search cost.
- **Why:** Moving features of unfamiliar shopping sites to positions predicted by each user's browsing history cut visual search time from 2.8 s to 2.5 s (over 10%) and fixations from 3.4 to 2.6 (over 23%) (Todi 2018). Of seven built-in usability strategies in ATM layouts, only keypad familiarity tracked apparent usability (r = 0.730) (Kurosu 1995). In an Israeli replication, keypad type again tracked apparent usability (contingency .671–.760), but Israelis favored the telephone keypad and Japanese users the horizontal keypad (Tractinsky 1997).
- **Evidence:** [B] — (Todi 2018; Kurosu 1995; Tractinsky 1997).
- **Limits:** Todi 2018 had 16 participants, one domain, brief point-and-click tasks, and tested only one of four principles. Kurosu and Tractinsky measured apparent (pre-use) usability from static layouts, not performance.

### CL-8. Design one coherent conceptual model and make it perceivable
- **Do:** Decide the objects, actions and relationships the user should believe in, and make every screen and behavior consistent with that model. Make relevant actions visibly perceivable (signifiers), not merely possible. Use physical constraints (disable or hide invalid targets) and logical constraints (show structure so users can infer what remains, e.g., partially visible content signals scrolling).
- **Why:** Norman calls an explicit, perceivable conceptual model the most important design tool, and separates physical, logical and cultural constraints (Norman 1999). "Familiar conceptual model" and "salient repertoire of actions" were among heuristics distinctive to serious problems (Nielsen 1994). Norman argues that gesture and "natural" interfaces still need visible possibilities, feedback and a clear model (Norman 2010).
- **Evidence:** [C] — (Norman 1999; Norman 2010; Nielsen 1994).
- **Limits:** Expert opinion; no effect sizes. The essays predate touch-first interfaces.

### CL-9. Show outputs in the terms users evaluate them in
- **Do:** Present the quantity the user actually judges: rate of change, difference from target, status relative to a threshold, position within a meaningful range. Avoid raw values that users must convert or compare mentally. Where users judge relations (above/below target, trend), prefer spatial or analog encodings over bare numbers.
- **Why:** Hutchins et al. frame the gulf of evaluation (system state to user goals) and show that displaying rate of change directly, rather than only current level, shortens semantic distance (Hutchins 1985). Pilots use the round airspeed dial as a spatial anchor and "only rarely think of the speed as a number"; digital tapes removed these cues and one manufacturer reverted to a dial replica (Hollan 2000). Smith & Mosier 2.0/3 forbids making users convert displayed data (Smith 1986).
- **Evidence:** [C] — (Hutchins 1985; Hollan 2000; Smith 1986).
- **Limits:** Theory and ethnography from expert, safety-critical domains; no measured effect sizes.

### CL-10. Shorten the gulf of execution, but do not equate directness with ease
- **Do:** Let users act on continuously visible objects with rapid, incremental, reversible operations whose result shows immediately. Make output objects usable as input (act on an item a query returned). Match the interface vocabulary to the level at which users think about the task. Also offer symbolic or scripted paths for repetitive, set-wise or high-precision work.
- **Why:** Directness has two sources: small semantic and articulatory distance, and direct engagement with inter-referential input/output (Hutchins 1985). Direct manipulation struggles with repetition, variables and sets, and puts the accuracy burden on the user (Hutchins 1985). Direct-manipulation filters (dynamic queries updating in under 100 ms) gave faster performance and fewer errors than form fill-in in a small study (18 students) (Shneiderman 1996). Smith & Mosier 3.1.8/5 recommends direct manipulation for casual users (Smith 1986).
- **Evidence:** [C] — (Hutchins 1985; Shneiderman 1996; Smith 1986).
- **Limits:** Practice (automatization) can make a poor interface feel direct without reducing semantic distance, so expert reports of directness are not evidence of good design; test with less practiced users (Hutchins 1985).

### CL-11. Let users off-load memory to the interface and keep positions stable
- **Do:** Allow free spatial arrangement, piles and grouping of items, and keep items where users put them. Keep item positions spatially stable across sessions so users can revisit by location. Preserve incidental cues experts rely on (use-history, recency, position) when redesigning. Do not reorder menus or toolbars silently.
- **Why:** "People off-load cognitive effort to the environment whenever practical"; supports for expert performance are sometimes "mistakenly designed out" of clean, simple redesigns (Hollan 2000). Space-filling thumbnails with stable page locations outperformed panning, zooming and overview+detail for revisitation (Cockburn 2009). When adapting, update only the affected part of the UI and keep previously seen content stable (Amershi 2019, G14).
- **Evidence:** [B] — (Hollan 2000; Cockburn 2009; Amershi 2019).
- **Limits:** Hollan 2000 is programmatic with few numbers. Recording use-history raises privacy issues; give users ownership and consent (Hollan 2000).

### CL-12. Speak the user's language, not the system's
- **Do:** Use the users' task vocabulary, language and characters. Avoid programmer jargon, internal codes and unexplained abbreviations. Phrase prompts from the user's goal. Use mixed case, affirmative sentences and active voice. Address the user directly.
- **Why:** "Speak the user's language" was the second-largest heuristic in coverage (16% marginal, 39% cumulative) (Nielsen 1994). In the MANTEL critique, 92% flagged English terms in a Danish system and 92% flagged missing Danish characters (Molich 1990). Organization-centric keys instead of bus numbers were found by only 12% of evaluators (Nielsen 1990). Smith & Mosier 2.0/12 and 4.0/16 Familiar Wording, 4.0/17 Task-Oriented Wording, 2.0/16 Minimal Use of Abbreviation, and 2.1/16–2.1/17 affirmative, active sentences (Smith 1986).
- **Evidence:** [B] — (Nielsen 1994; Molich 1990; Nielsen 1990; Smith 1986).
- **Limits:** The MANTEL design was never user-tested; problem lists are expert judgments.

### CL-13. Avoid modes; if a mode is unavoidable, show it at all times
- **Do:** Prefer modeless interaction where the same action always does the same thing. Where modes exist, display the current mode continuously and distinctively, and require an explicit action to enter a destructive mode.
- **Why:** Modeless interaction was among heuristics distinctive to serious problems (Nielsen 1994). Smith & Mosier require 3.4/4 Display of Operational Mode, 4.2/8 Indicating Operational Mode and 6.0/15 Explicit Action to Select Destructive Modes (Smith 1986).
- **Evidence:** [B] — (Nielsen 1994; Smith 1986).
- **Limits:** Smith & Mosier rules are 1986 judgment-based guidelines; Nielsen's corpus is single-rater.

### CL-14. Make the available actions salient and easy to tell apart
- **Do:** Show what can be done now: visible menus, labeled controls, visible hints for gestures. Offer only options that are currently available. Make alternative actions visually and verbally distinct. Do not rely on hidden gestures or shortcuts as the only path to a function. Label icons with words.
- **Why:** "Salient repertoire of actions" and "easy-to-discriminate action alternatives" were distinctive to serious problems (Nielsen 1994). GUI strength is visibility; gestures are ephemeral, hard to discover and few are innate (Norman 2010). Only 1 of 6 experienced Word users knew the Ctrl+scroll zoom shortcut (Cockburn 2009). Smith & Mosier 3.2/10 Only Available Options Offered and 3.1.8/4 Supplementary Verbal Labels for icons (Smith 1986).
- **Evidence:** [B] — (Nielsen 1994; Norman 2010; Cockburn 2009; Smith 1986).
- **Limits:** Showing every action can add clutter; balance with minimalist design and progressive disclosure.

### CL-15. Offer optional accelerators for experts without burdening novices
- **Do:** Give frequent actions the fewest steps. Provide shortcuts, command entry and other accelerators that bypass menus for experts, as optional extras on top of a consistent, visible path. Support step-by-step guidance for beginners and direct command for experts. Do not spend a large learning cost on saving seconds in rare tasks.
- **Why:** Shortcuts/accelerators added 6% coverage in the problem corpus and are retained for expert performance (Nielsen 1994). Smith & Mosier: 3.0/3 Control Matched to User Skill, 3.1.3/35 By-Passing Menu Selection with Command Entry, "make the user's most frequent transactions the easiest to accomplish", shortcuts only as optional extras; a 10-minute learning cost for a 10-second saving in a rare task means design has "outpaced user needs" (Smith 1986). "Provide shortcuts" is one of nine dialogue principles (Molich 1990).
- **Evidence:** [B] — (Nielsen 1994; Smith 1986; Molich 1990).
- **Limits:** Shortcuts mostly explain minor problems (Nielsen 1994). Hidden accelerators are rarely discovered (CL-14, CL-16).

### CL-16. Help users move to efficient methods with low-intrusion hints
- **Do:** Raise awareness of relevant functionality in context and at low intrusion, for example by showing the keyboard shortcut next to or after a menu command is used. Avoid interruptive assistant pop-ups. Make help aware of the user's current (possibly customized) layout so it can show where a function is. Support help queries about high-level task flows, not just single commands. Lower the perceived cost of trying a better method.
- **Why:** Learnability issues fall into five categories: task flow, awareness of functionality, locating functionality, understanding functionality, and transition to efficient behaviors (Grossman 2009). Novices mostly had awareness issues; users often know a better feature and do not use it (Grossman 2009). Teaching animations can show non-obvious gestures and be retired once learned (Chevalier 2016).
- **Evidence:** [C] — (Grossman 2009; Chevalier 2016).
- **Limits:** Grossman's guidelines are proposed directions from one application (AutoCAD), 10 users and one coach; they were not tested as interventions. Evidence for teaching animations is "mixed" (Chevalier 2016).

### CL-17. Define learnability before you design or measure for it
- **Do:** State which learnability you mean: initial (performance in a first task or interval) or extended (improvement over time, or reaching a target level). State the user profile (computer experience, experience with this interface, domain knowledge, experience with similar software). Pick explicit metrics: task (time, % completed without help, error decrease), command (growth in commands used), mental (think times, chunk size), subjective, documentation use, or novice vs. expert comparison. Measure retention after a delay for repeatedly used systems.
- **Why:** Of 88 CHI/TOCHI papers using "learnability", 45 gave no definition (Grossman 2009). A coach-based question-suggestion protocol found 7.55 vs. 2.8 learnability issues per 15-min task compared with think-aloud; think-aloud surfaced no transition issues (Grossman 2009). Only 5 of 180 usability studies measured learning and 1 measured retention; median interaction time was 30 min (Hornbaek 2006).
- **Evidence:** [B] — (Grossman 2009; Hornbaek 2006).
- **Limits:** Question-suggestion was tested in one study; the authors do not claim it is generally better than think-aloud. Perceived learnability is not time-to-proficiency (Hornbaek 2006).

### CL-18. Cost expert routines with the Keystroke-Level Model, and minimize decision points
- **Do:** For routine expert tasks, write each method as operators and sum: K keystroke (0.20 s average skilled typist; 0.08–1.20 s range), P point (1.10 s average), H home between devices (0.40 s), M mental preparation (1.35 s), plus non-overlapped system wait R. Reduce M operators by making command sequences chunkable (consistent, predictable terminators, anticipated follow-ups). Minimize keyboard–mouse switching. Allow type-ahead so system responses overlap user preparation.
- **Why:** KLM predicted expert error-free unit-task time with 21% RMS error per task (5–6% over task sequences) across 1,280 observations, 28 experts and 10 systems (Card 1980). Counting keystrokes only gave 49% RMS error, so mental operators matter (Card 1980). M placement rules delete M within a cognitive unit or when an action is fully anticipated (Card 1980).
- **Evidence:** [A] — (Card 1980).
- **Limits:** KLM assumes experts, routine tasks, fully specified methods and no errors. Do not use it for novices, learning, error recovery or method choice. Do not trust differences smaller than the model error (Card 1980). In Seckler's form study, measured time savings (18–33%) exceeded KLM predictions (7–23%) (Seckler 2014).

### CL-19. Make adaptive and personalized interfaces transparent, reversible and cautious
- **Do:** When the interface adapts to the user (layout, target size, ordering, suggestions), let users see, preview, override, undo, store and revert each adaptation. Prefer suggesting over silently changing. Change only the part of the UI affected and keep previously seen content stable. Offer familiarity-based restructuring on demand (a toggle), not always on. When users perform poorly, change the system, not the user.
- **Why:** Ability-based design requires that systems, not users, adapt, and recommends transparency: users can inspect, override, discard, revert, store, retrieve, preview and test adaptations; only 6 of 14 example systems upheld transparency (Wobbrock 2011). Adaptation can pay off: SUPPLE's generated UIs made motor-impaired users 28% faster and 73% more accurate (Wobbrock 2011). Amershi G14 "Update and adapt cautiously" limits disruptive changes (Amershi 2019). Todi suggests familiarisation as an on-demand mode (Todi 2018).
- **Evidence:** [B] — (Wobbrock 2011; Amershi 2019; Todi 2018).
- **Limits:** Wobbrock 2011 is a position paper; examples are mostly the authors' own and mostly motor impairment. Adaptive UIs risk unpredictability, which conflicts with CL-5 and CL-11. Walking-adaptive UIs gave mixed results (Wobbrock 2011). Amershi validates relevance, not user outcomes.

## Numbers at a glance
| Parameter | Value | Grade | Source |
|---|---|---|---|
| Pure short-term memory capacity, adults | ~4 chunks (group means 3–5) | A | Cowan 2001 |
| Individual range of capacity | ~2 to almost 6 chunks | A | Cowan 2001 |
| Ignored-speech digit recall: adults / 4th grade / 1st grade | 3.51 / 2.99 / 2.34 | B | Cowan 2001 |
| Near-perfect change detection | 1–3 objects; drops beyond 4 | B | Cowan 2001 |
| Theoretical optimal chunk size per hierarchy level | 3.59 | C | Cowan 2001 |
| Absolute judgment, one dimension | mean 2.6 bits (SD 0.6), ~6.5 categories (range 3–15) | A | Miller 1956 |
| Memory span | ~7–8 decimal digits; ~5 monosyllabic words | A | Miller 1956 |
| Max colors for category coding | 5 | C | Smith 1986 |
| Max length of coded data items | 5–7 characters | C | Smith 1986 |
| Problem coverage, consistency heuristic | 23% of 249 problems (top) | B | Nielsen 1994 |
| Problem coverage, speak user's language | 16% marginal, 39% cumulative | B | Nielsen 1994 |
| Serious problems explained by seeing/pointing vs remembering/typing | 22% of 82 | B | Nielsen 1994 |
| Shortcuts / accelerators coverage | 6% marginal | B | Nielsen 1994 |
| Real-world conventions coverage | 4% marginal | B | Nielsen 1994 |
| Evaluators who flagged missing input echo | 95% | B | Molich 1990 |
| Simple UI fixes incl. consistent wording | 25% faster entry, 25% fewer errors | C | Smith 1986 (citing Keister & Gallaway) |
| Familiarised layout: search time | 2.8 s → 2.5 s (>10%) | B | Todi 2018 |
| Familiarised layout: fixations | 3.4 → 2.6 (>23%) | B | Todi 2018 |
| Keypad familiarity vs apparent usability | r = 0.730 (Japan); contingency .671–.760 (Israel) | B | Kurosu 1995; Tractinsky 1997 |
| Experienced Word users aware of Ctrl+scroll zoom | 1 of 6 | C | Cockburn 2009 |
| KLM M (mental preparation) | 1.35 s | A | Card 1980 |
| KLM K (average skilled typist) / P / H | 0.20 s / 1.10 s / 0.40 s | A | Card 1980 |
| KLM accuracy | 21% RMS per task; 5–6% over sequences; keystrokes-only 49% | A | Card 1980 |
| Papers using "learnability" with no definition | 45 of 88 | B | Grossman 2009 |
| Learnability issues per 15-min task, question-suggestion vs think-aloud | 7.55 vs 2.8 | B | Grossman 2009 |
| Usability studies measuring learning / retention | 5 / 1 of 180 | B | Hornbaek 2006 |
| SUPPLE adapted UIs for motor-impaired users | 28% faster, 73% more accurate | B | Wobbrock 2011 |
| Dynamic query update latency | < 100 ms | C | Shneiderman 1996 |

## Common misreadings
- "Menus and navigation should have 7±2 items." — Miller 1956 is about absolute judgment and unaided immediate recall, not scanning visible options. Miller calls the recurrence of seven a likely coincidence. Visible, recognizable options are not held in short-term memory.
- "So the real limit is 4: keep screens or menus to 4 items." — Cowan's ~4 chunks concerns what must be held in mind without external support or chunking. Replacing 7 with 4 does not rescue an item-count rule for visible content.
- "Short-term memory holds 7 items." — 7 is a compound estimate inflated by rehearsal and chunking; the pure limit is about 4 chunks, and the limit is in chunks, not items or bits (Cowan 2001).
- "Direct manipulation is easy to use." — Hutchins 1985 says directness is not the same as ease of use; it has costs for repetition, sets and precision, and practice can make a poor interface feel direct.
- "Natural user interfaces are natural." — Norman 2010: few gestures are innate, meanings vary across cultures, and gestures still need feedback, visibility, undo and standards.
- "A cleaner, simpler redesign is always better for experts." — Hollan 2000: clean redesigns can remove incidental perceptual and spatial cues experts depend on.
- "More visual grouping always looks more usable." — Tractinsky 1997 found fewer groups linked to higher apparent usability (r −.462 to −.667), contradicting conventional advice.
- "KLM tells you how long novices will take." — Card 1980 applies only to error-free expert execution of routine tasks.
- "Learnability is a single, well-understood metric." — Grossman 2009 found no accepted definition; specify initial vs extended learnability, user profile and metric.

## Review checklist
- [ ] CL-1: Does each step show the context, options and prior inputs the user needs, so nothing must be recalled from an earlier screen?
- [ ] CL-2: Must the user carry 3 or fewer unrelated new items across any step without on-screen support?
- [ ] CL-3: Are long codes and numbers displayed in groups of about 3–4 characters, and are coded entries 7 characters or fewer?
- [ ] CL-4: Does any single visual dimension encode more than about 5–7 absolute levels (or more than 5 category colors) without labels or redundant coding?
- [ ] CL-5: Is each concept named with one term, each function identified the same way, and navigation and help in the same relative order on every page?
- [ ] CL-6: Do controls, gestures, icons and placements follow platform conventions, with any departure justified and tested?
- [ ] CL-7: Are key domain features (logo, search, menu, account, cart, keypad) where peer products in that domain and locale put them?
- [ ] CL-8: Is there one coherent conceptual model, with invalid actions constrained and relevant actions visibly signified?
- [ ] CL-9: Are outputs shown in the terms users judge (difference, rate, status vs target) rather than raw values to convert?
- [ ] CL-10: Are operations incremental, reversible and immediately visible, with a scripted or batch path for repetitive or set-wise work?
- [ ] CL-11: Do items stay where users put them, and are positions stable across sessions and adaptive updates?
- [ ] CL-12: Is all wording in the users' task language, free of internal jargon, codes and unexplained abbreviations?
- [ ] CL-13: Is the interaction modeless, or is the current mode visible at all times with explicit entry to destructive modes?
- [ ] CL-14: Are available actions visible and distinct, with no function reachable only through a hidden gesture or shortcut?
- [ ] CL-15: Do frequent actions take the fewest steps, and are expert accelerators optional additions to a visible path?
- [ ] CL-16: Are efficient methods (shortcuts, better features) advertised in context without interruptive pop-ups?
- [ ] CL-17: Does the spec state initial vs extended learnability, the user profile and the learnability metric?
- [ ] CL-18: For routine expert tasks, has a KLM estimate been made, with decision points and device switches minimized?
- [ ] CL-19: Can users see, preview, override and revert every adaptation, and does adaptation leave previously seen content stable?

## Sources
- Amershi, S., et al. (2019). *Guidelines for human-AI interaction*. CHI '19. https://doi.org/10.1145/3290605.3300233
- Card, S. K., Moran, T. P., Newell, A. (1980). *The keystroke-level model for user performance time with interactive systems*. Communications of the ACM. https://doi.org/10.1145/358886.358895
- Chevalier, F., Riche, N. H., Plaisant, C., Chalbi, A., Hurter, C. (2016). *Animations 25 years later: new roles and opportunities*. AVI '16. https://doi.org/10.1145/2909132.2909255
- Cockburn, A., Karlson, A., Bederson, B. B. (2009). *A review of overview+detail, zooming, and focus+context interfaces*. ACM Computing Surveys. https://doi.org/10.1145/1456650.1456652
- Cowan, N. (2001). *The magical number 4 in short-term memory*. Behavioral and Brain Sciences. https://doi.org/10.1017/s0140525x01003922
- Grossman, T., Fitzmaurice, G., Attar, R. (2009). *A survey of software learnability: metrics, methodologies and guidelines*. CHI '09. https://doi.org/10.1145/1518701.1518803
- Hollan, J., Hutchins, E., Kirsh, D. (2000). *Distributed cognition: toward a new foundation for HCI research*. ACM TOCHI. https://doi.org/10.1145/353485.353487
- Hornbaek, K. (2006). *Current practice in measuring usability*. IJHCS. https://doi.org/10.1016/j.ijhcs.2005.06.002
- Hutchins, E., Hollan, J., Norman, D. (1985). *Direct manipulation interfaces*. Human-Computer Interaction. https://doi.org/10.1207/s15327051hci0104_2
- Kurosu, M., Kashimura, K. (1995). *Apparent usability vs. inherent usability*. CHI '95. https://doi.org/10.1145/223355.223680
- Miller, G. A. (1956). *The magical number seven, plus or minus two*. Psychological Review. https://doi.org/10.1037/h0043158
- Molich, R., Nielsen, J. (1990). *Improving a human-computer dialogue*. Communications of the ACM. https://doi.org/10.1145/77481.77486
- Nielsen, J., Molich, R. (1990). *Heuristic evaluation of user interfaces*. CHI '90. https://doi.org/10.1145/97243.97281
- Nielsen, J. (1994). *Enhancing the explanatory power of usability heuristics*. CHI '94. https://doi.org/10.1145/191666.191729
- Norman, D. (1999). *Affordance, conventions, and design*. ACM interactions. https://doi.org/10.1145/301153.301168
- Norman, D. (2010). *Natural user interfaces are not natural*. ACM interactions. https://doi.org/10.1145/1744161.1744163
- Seckler, M., Heinz, S., Bargas-Avila, J. A., Opwis, K., Tuch, A. N. (2014). *Designing usable web forms: empirical evaluation of web form improvement guidelines*. CHI '14. https://doi.org/10.1145/2556288.2557265
- Shneiderman, B. (1996). *The eyes have it: a task by data type taxonomy for information visualizations*. IEEE Symp. Visual Languages. https://doi.org/10.1109/vl.1996.545307
- Smith, S. L., Mosier, J. N. (1986). *Guidelines for designing user interface software*. MITRE / DTIC ESD-TR-86-278. https://doi.org/10.21236/ada177198
- Todi, K., Jokinen, J., Luyten, K., Oulasvirta, A. (2018). *Familiarisation: restructuring layouts with visual learning models*. IUI 2018. https://doi.org/10.1145/3172944.3172949
- Tractinsky, N. (1997). *Aesthetics and apparent usability: empirically assessing cultural and methodological issues*. CHI '97. https://doi.org/10.1145/258549.258626
- W3C (2023). *Web Content Accessibility Guidelines (WCAG) 2.2*. W3C Recommendation. https://www.w3.org/TR/WCAG22/
- Wobbrock, J. O., Kane, S. K., Gajos, K. Z., Harada, S., Froehlich, J. (2011). *Ability-based design: concept, principles and examples*. ACM TACCESS. https://doi.org/10.1145/1952383.1952384
