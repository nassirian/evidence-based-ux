# Group B — Heuristics, inspection methods, and foundational interaction principles

---

## 01__Hollan-Hutchins-Kirsh-2000_Distributed-cognition — Distributed Cognition: Toward a New Foundation for Human-Computer Interaction Research (Hollan, Hutchins, Kirsh, 2000, ACM TOCHI 7(2))
**Type:** theory (with illustrative case work)  ·  **Sample/method:** Position paper proposing a research framework; draws on the authors' prior cognitive ethnographies (US Navy ship navigation, airline cockpits, ATC), Kirsh's studies of space use (videos of cooking, assembly, packing; Tetris lab studies), and design projects (history-enriched digital objects, Pad++ / PadPrints).

**Core claim.** Cognition is not bounded by the individual skull: it is distributed across people, between internal and external (material) structure, and through time. HCI should take whole sociotechnical systems as the unit of analysis and ground design in cognitive ethnography plus experiment.

**Key findings**
- Two defining principles: (1) the unit of analysis is set by functional relationships among elements, not by the skin/skull; (2) a broader class of mechanisms (manipulation of objects, traffic of representations among people) counts as cognitive.
- Three kinds of distribution: across members of a social group; between internal and external structure; across time (earlier products transform later events).
- Core principles listed: people establish and coordinate different types of structure in their environment; it takes effort to maintain coordination; people off-load cognitive effort to the environment whenever practical; social organization offers improved dynamics of cognitive load-balancing.
- Airspeed case: pilots use the round-dial airspeed indicator as a "material anchor" for a conceptual space of meaningful speeds and "only rarely think of the speed as a number." These perceptual features were inadvertently removed from the digital airspeed tapes of then-current Airbus, McDonnell Douglas, Boeing and Fokker cockpits; the Boeing 737-700 reverted to a digital replica of the old dial.
- Use-history ("edit wear / read wear"): attribute-mapped scroll bars show who edited/read which sections; menus can brighten commonly chosen items; supports for expert performance are "sometimes actively, but mistakenly, designed out of 'clean' and 'simple' digital work environments" (A-320 example).
- PadPrints (zoomable multiscale browsing history) was shown more effective than traditional browsers on a variety of common search tasks (cited from Hightower et al. 1998; no numbers given here).
- Kirsh's space classification: spatial arrangements that simplify choice, that simplify perception, and spatial dynamics that simplify internal computation. Tetris players physically rotate pieces to save mental computation.
- Representations are used both "as the thing" and "as a representation" (fishermen's sonar talk; flight engineer flicking a gauge) — these shifts support cognition.

**Design rules derivable**
- Before redesigning a legacy display/tool, observe experts using it in situ and identify the perceptual/spatial features they actually rely on; preserve or amplify those in the new design. [moderate — rich single-domain ethnography]
- Prefer analog/spatial encodings (position within a meaningful range, target annotations) over bare numbers when users judge relations (above/below target, trend). [moderate]
- Let users off-load memory to the interface: allow free spatial arrangement, piles, grouping, leaving items "near" related items, open portals/windows as reminders. [moderate]
- Expose use-history on objects (recently/frequently edited sections, popular menu items, recency ordering) where it informs the task; give users ownership/consent over recorded history. [weak — prototypes, no effect sizes]
- Do not merely imitate the physical world; exploit computational properties (zoom, multiscale, active representations that surface what is relevant next). [weak]
- Treat "clean/simple" redesigns with suspicion if they remove incidental cues experts use. [moderate]

**Boundary conditions & caveats.** Programmatic paper; the integrated framework "does not yet exist." Evidence is largely ethnographic and from safety-critical expert domains; few quantitative results reported. Privacy issues of use-history recording flagged.


---

## 01__Hutchins-Hollan-Norman-1985_Direct-manipulation-interfaces — Direct Manipulation Interfaces (Hutchins, Hollan, Norman, 1985, Human-Computer Interaction 1)
**Type:** theory  ·  **Sample/method:** Cognitive analysis of the "feeling of directness"; examples from Steamer, spreadsheets, screen editors, statistics-by-icon prototype; no experiment.

**Core claim.** The feeling of directness has two sources: small *distance* (semantic and articulatory) across the gulfs of execution and evaluation, and *direct engagement* (a model-world rather than conversation metaphor, with inter-referential I/O). Directness involves trade-offs and is not the same as ease of use.

**Key findings**
- Restates Shneiderman's three properties: continuous representation of the object of interest; physical actions or labeled button presses instead of complex syntax; rapid incremental reversible operations whose impact is immediately visible.
- Gulf of execution (goals → system state) and gulf of evaluation (system state → goals); "the feeling of directness is inversely proportional to the amount of cognitive effort."
- Semantic distance: can the user say what they want, and concisely? Articulatory distance: relation between the meaning of an expression and its physical form (e.g., moving a mouse to move a cursor is articulatorily direct; a moving graph vs. a table of numbers can be semantically equal but articulatorily unequal).
- Water-tank example: displaying rate of change directly (vs. current level only) shortens semantic distance on the evaluation side.
- Automatization (practice) can make a poor interface *feel* direct ("dw" in vi) but does not reduce semantic distance.
- Requirements for direct engagement: semantic + articulatory directness for execution and evaluation; inter-referential input/output; responsiveness with no delays except those natural to the domain; unobtrusive interface.
- Problems: repetitive operations are better done by script; difficulty with variables and sets vs. individuals; accuracy burden on the user; risk of only supporting old ways of thinking; specialized languages lose generality.

**Design rules derivable**
- Present outputs in the terms of the user's evaluation goal (show rates, differences, status vs. target) rather than raw values the user must transform. [moderate — strong theoretical consensus, illustrative evidence]
- Make output objects usable as input (select/act on the item that a query or listing returned). [weak]
- Give rapid, continuous visual feedback of object state during manipulation; avoid delays not intrinsic to the task. [moderate]
- Provide reversible, incremental operations. [moderate]
- Offer symbolic/scripted alternatives for repetitive, set-wise, or precision tasks rather than forcing direct manipulation. [weak]
- Do not infer good design from expert users' claims of directness; test with less practiced users. [weak]
- Match the level of interface vocabulary to the task level users think in, accepting a loss of generality only deliberately. [weak]

**Boundary conditions & caveats.** Explicitly "no way to measure the trade-off values." Directness depends on the task (piano vs. violin example). Direct manipulation is "not a panacea"; poor domain knowledge is not cured by it.


---

## 01__Hvannberg-2007_Heuristic-evaluation-comparing-ways — Heuristic evaluation: Comparing ways of finding and reporting usability problems (Hvannberg, Law, Lárusdóttir, 2007, Interacting with Computers 19(2))
**Type:** empirical study  ·  **Sample/method:** 2×2 between-subjects HE (Nielsen heuristics vs. Gerhardt-Powals cognitive principles × paper vs. web-tool reporting), 20 novice evaluators (19 final-year CS BS students + 1 BS graduate), 5 per cell, on the EducaNext e-learning portal; then think-aloud user test (10 university staff, 8 task scenarios derived from HE predictions); two-way matching of predicted vs. actual problems.

**Core claim.** Neither the heuristic set nor the reporting medium significantly changed effectiveness, efficiency or inter-evaluator reliability; overall HE effectiveness by novices was low (~0.21), and the comparison framework itself is the main contribution.

**Key findings**
- 160 predicted usability problems (PUPs) → 148 after removing 12 duplicates/incomprehensible → 85 unique. Per-group PUPs: A (Nielsen/paper) 33, B (G-P/paper) 37, C (Nielsen/tool) 43, D (G-P/tool) 47; χ² n.s.
- User test: 125 raw UPs → 58 unique (10 severe, 27 moderate, 21 minor). Mean UPs per user 12.5 (SD 4.2) vs. 8.0 (SD 2.9) per HE evaluator.
- Hits = 32, False Alarms = 53. Validity = 32/85 = 0.38; Thoroughness = 32/58 = 0.55; Effectiveness = 0.21 (prior Study 1: 0.22).
- Nielsen vs. G-P: validity 0.40 vs 0.39; thoroughness 0.36 vs 0.36; effectiveness 0.14 each; mean time 2 h 18 min vs 2 h 23 min. Earlier Study 1 had found Nielsen significantly better; not replicated.
- Paper vs. tool: validity 0.41 vs 0.45; thoroughness 0.31 vs 0.40; effectiveness 0.13 vs 0.18 (n.s.); time 2 h 30 vs 2 h 14 min. Tool users typed more PUPs (Nielsen groups t = 2.21, df = 8, p = 0.06) but not higher quality.
- Inter-evaluator any-two agreement = 0.046 overall (vs. 0.101 among user-test participants).
- User-test discovery rate p = 0.22 → at least seven users needed for 80% of problems (contradicting "magic number 5"); p = 0.3 for severe, 0.21 moderate, 0.18 minor problems.
- Time spent vs. PUPs found: r = 0.48, p = 0.03. HE vs. UT frequency of hits not correlated (Spearman rs = 0.23, p = 0.2).
- Evaluators cited heuristics as both facilitator (n = 6) and hindrance (n = 7); training material helped 8 of 20.
- Structured 7-attribute problem report: ID, short description, likely user difficulties, specific context, possible causes, heuristic(s), severity (severe/moderate/minor).

**Design rules derivable** (mostly process rules)
- Do not rely on novice heuristic evaluation alone; expect most predicted problems to be unconfirmed and most real problems missed—validate with user testing. [moderate]
- Derive user-test tasks from HE-predicted problem areas to check predictions (falsification testing). [weak]
- Use a structured problem-report format (context, cause, severity, heuristic) to ease merging and matching. [weak]
- Plan for ≥7 test users when the per-user discovery rate is ~0.2. [moderate — single study, consistent with Poisson logic]
- Consider domain-specific heuristics; choose heuristic sets to fit the application class. [weak]
- Break long inspections into shorter iterative sessions to limit fatigue. [weak — suggestion]

**Boundary conditions & caveats.** Small n (5 per cell), novice evaluators, one e-learning portal, user tests only of HE-derived tasks; low statistical power acknowledged; problem-instance counting; definition of "context" unresolved.


---

## 01__Molich-Nielsen-1990_Improving-a-human-computer-dialogue — Improving a Human-Computer Dialogue (Molich & Nielsen, 1990, Communications of the ACM 33(3))
**Type:** empirical study (survey/contest) + guideline  ·  **Sample/method:** 77 entries to a Danish Computerworld contest (51 industry, 10 teachers/students, 16 unspecified) critiquing a one-screen phone-lookup dialogue ("MANTEL") on a 24×80 terminal; scored liberally against the authors' list of 30 problems (8 marked serious).

**Core claim.** Even motivated industrial designers and programmers find only about a third of the usability problems in a simple dialogue; a small, intellectually manageable set of dialogue principles is needed.

**Key findings**
- Nine principles (verbatim category names): Simple and Natural Dialogue; Speak the User's Language; Minimize the User's Memory Load; Be Consistent; Provide Feedback; Provide Clearly Marked Exits; Provide Shortcuts; Provide Good Error Messages; Error Prevention.
- Average problems found: 11.2 of 30 (37%); median 11; winner 18 (60%). Serious problems: average 3.5 of 8 (44%).
- Most-found: re-display the entered phone number with result (95%); avoid English terms (92%); use Danish characters (92%); remove unnecessary information (77%); warn about 30-s delay (74%).
- Least-found: accept parentheses, spaces and hyphens in phone numbers (8%); no exit from initial prompt; no exit during long retrieval; inability to edit input in prompt (lowest).
- 55% of entries mentioned no "Prevent errors" problem; apart from vague error messages, no error-message/prevention problem was mentioned by more than 42%.
- Good error messages are "defensive, precise, and constructive"; "ILLEGAL" intimidates; "Try again" is meaningless; a beep is not an error message.
- Long-wait feedback spec: tell the user it may take up to 30 seconds and why, add a progress indicator every five seconds, provide abort (ESC).
- Participants who critiqued a message often kept its flaws ("Illegal", "Try again!") in their rewrites.

**Design rules derivable**
- Remove irrelevant or rarely needed information from screens; every extra unit competes with relevant ones. [moderate]
- Echo the user's input alongside the result so they need not remember it. [moderate]
- Use one term per concept; place error messages in one consistent location coordinated with the parent system. [moderate]
- For any wait beyond a few seconds, state the expected delay and show periodic activity; allow aborting. [moderate]
- Provide a visible exit from every state and allow editing (backspace) of typed input. [moderate]
- Accept common input formats (spaces, hyphens, parentheses; letters O/l for digits 0/1) instead of rejecting them. [moderate]
- Write error messages that state what is wrong, what the system understood, and how to fix it, without blame words ("illegal"). [moderate]
- Show a concrete example of valid input in the prompt. [weak]
- Phrase prompts from the user's goal ("Enter telephone number for which you want name and address"). [weak]
- Use mixed case; avoid abbreviations where space allows; check spelling. [weak]

**Boundary conditions & caveats.** One hypothetical design, never user-tested; 30-problem list is the authors' judgment (they missed 2 initially); liberal scoring; Danish context; character terminal era.


---

## 01__Nielsen-1994_Enhancing-explanatory-power-of-heuristics — Enhancing the Explanatory Power of Usability Heuristics (Nielsen, 1994, CHI '94)
**Type:** meta-analysis (factor analysis of a problem database)  ·  **Sample/method:** 101 heuristics from 7 published sets rated 0–5 for how well each explains each of 249 usability problems from 11 projects (7 HE, 4 user tests; 4 early, 7 late; 2 character-based, 6 GUI, 3 telephone); 82 problems serious. Principal components analysis + greedy coverage analysis. Single rater (the author).

**Core claim.** No small set of factors explains most usability problems, but a set of nine heuristics provides broad explanatory coverage; this yields the revised list that became the standard "Nielsen heuristics."

**Key findings**
- Final nine heuristics (verbatim): visibility of system status; match between system and the real world; user control and freedom; consistency and standards; error prevention; recognition rather than recall; flexibility and efficiency of use; aesthetic and minimalist design; helping users recognize, diagnose, and recover from errors.
- Seven factors and % variance: Visibility of system status 6.1%; Match between system and real world 5.9%; User control and freedom 4.6%; Consistency and standards 4.2%; Error prevention 3.7%; Recognition rather than recall 3.1%; Flexibility and efficiency of use 2.8%. These seven sum to 30%; 25 factors ≥1% explain 62%; 53 factors needed for 90%.
- Greedy top-10 for all 249 problems (marginal / cumulative): Consistency (A4) 23/23%; Speak the user's language 16/39%; Feedback—show receipt of input 13/52%; Seeing/pointing vs. remembering/typing 7/59%; Aesthetic integrity 7/65%; Shortcuts/accelerators 6/71%; Real-world conventions 4/76%; Help error recognition/recovery 4/80%; Forgiveness (reversible actions) 3/83%; Salient repertoire of actions 2/85%.
- Top-10 for 82 serious problems starts with Seeing/pointing vs. remembering/typing (22%) and reaches 95% cumulative; heuristics distinctive to serious problems: make action repertoire salient, familiar conceptual model, prevent errors, easy-to-discriminate action alternatives, modeless interaction.
- Four heuristics with widest coverage explain 70% of major vs. 65% of all problems.
- Set performance (mean best score; % explained ≥3): Nielsen's ten 3.72/82%; SunSoft 3.31/73%; Macintosh 3.09/66%; Holcomb & Tharp 2.90/64%; Polson & Lewis 2.31/47%; Carroll & Rosson 1.99/44%; Star 2.38.
- Aesthetic integrity and shortcuts mostly explain minor problems but are retained (satisfaction/sales; expert performance).

**Design rules derivable**
- Use the nine heuristics as the primary inspection checklist. [moderate — large problem corpus, single rater]
- Prioritize visibility: show available actions and objects (recognition over recall) — it most explains serious problems. [moderate]
- Keep same things looking and behaving the same, and follow platform/real-world conventions. [moderate]
- Acknowledge every input immediately and keep users informed of status. [moderate]
- Provide undo/reversibility and clearly marked exits; avoid modes. [moderate]
- Make action alternatives easy to discriminate. [weak]
- Provide accelerators for experts without burdening novices. [moderate]

**Boundary conditions & caveats.** Ratings subjective, single rater (cited agreement among specialists only ~two-thirds); database partly from the original heuristics' own projects (bias toward set A); explains *previously found* problems—value for *finding* new ones untested.


---

## 01__Nielsen-1994_Usability-inspection-methods — Usability Inspection Methods (Nielsen, 1994, CHI '94 Conference Companion, tutorial summary)
**Type:** survey  ·  **Sample/method:** Two-page tutorial summary of inspection methods drawing on the CHI'92 workshop and the *Usability Inspection Methods* book.

**Core claim.** Usability inspection is a family of cost-effective, informal methods for finding usability problems, usable early on specifications; inspection and user testing find partly different problems, so combining them works best.

**Key findings**
- Four ways to evaluate UIs: automatically, empirically, formally, informally; automatic methods "do not work," formal methods are hard and don't scale.
- Methods defined: heuristic evaluation (specialists judge each element against heuristics—most informal); cognitive walkthrough (simulate user problem solving step by step); formal usability inspections (six-step procedure with defined roles); pluralistic walkthroughs (users, developers, human-factors people step through a scenario); feature inspection (check feature sequences for length, cumbersome or unnatural steps); consistency inspection (designers of multiple projects); standards inspection (compliance expert).
- HE, cognitive walkthrough, feature and standards inspection are individual; pluralistic walkthroughs and consistency inspection are group methods; HE combines independent individual reports.
- Regular developers can serve as evaluators, "though better results are normally achieved when using usability specialists."

**Design rules derivable** (process)
- Inspect specifications/prototypes early, before implementation. [moderate — cited literature]
- Combine inspection with user testing rather than substituting one for the other. [moderate]
- Use usability specialists as evaluators when possible. [moderate]
- Use cognitive walkthrough for walk-up-and-use flows; feature inspection to flag long or unnatural task sequences; consistency inspection across product lines. [weak]

**Boundary conditions & caveats.** No data in the text itself; summary of other work.


---

## 01__Nielsen-Landauer-1993_Mathematical-model-finding-usability-problems — A Mathematical Model of the Finding of Usability Problems (Nielsen & Landauer, 1993, INTERCHI '93)
**Type:** meta-analysis / model  ·  **Sample/method:** 11 studies (5 user tests, 6 heuristic evaluations; 13 datasets) fitted with a Poisson/geometric model; cost–benefit analysis with literature-derived costs.

**Core claim.** Problem discovery follows Found(i) = N(1 − (1 − λ)^i); this lets teams estimate remaining problems mid-study and choose the number of users/evaluators by cost–benefit.

**Key findings**
- Mean across studies: N = 41 problems, λ = 0.31; one evaluator/user found 33% on average. λ ranged widely (e.g., .12 Office System user test; .58 banking double-specialists). Fits mostly R² > .93.
- Banking system HE: non-specialists 22%, usability specialists 41%, double specialists (usability + domain) 60% of problems per evaluator.
- Office System: 145 problems from 15 users, model predicted 166; 76 problems seen by only one user.
- Estimation from two evaluations: λ = 2 − Found(2)/Found(1); N = Found(1)/λ. SD of estimated N: 21% (4 people), 11% (5), 9% (6), 8% (7), 6% (8), 5% (9–10); highly variable with 2–3.
- Prior evidence cited: same-evaluator correlation .57 across two HE studies; thinking-aloud problems found correlate .76 with methodological quality.
- Optimal numbers (HE / user testing): small project 9 / 7; medium-large 16 / 15; very large 21 / 20. HE benefit/cost ratio: 4.2 (small), 45 (medium-large), 247 (very large); user testing 34 (medium-large), 178 (very large).
- Maximum benefit/cost ratio at 3.2 test users and 4.4 heuristic evaluators (medium-large); with a $20,000 cost per iteration, 6.7 users and 7.9 evaluators. Abstract: "16 evaluations would be worth their cost, with maximum benefit/cost ratio at four."
- Problems in missing features were much harder to find by HE of paper mockups than of running prototypes.

**Design rules derivable** (process)
- Test with ~3–5 users or evaluators per iteration, then fix and re-test, rather than one large study. [strong — 13 datasets, consistent model]
- After a few sessions, estimate λ and remaining problems; stop when marginal value < marginal cost. [moderate]
- Average Found(i) across all orderings/combinations of evaluators, not first-come. [moderate]
- Prefer evaluators with both usability and domain expertise. [moderate]
- Evaluate running prototypes, not only paper, to catch missing-feature problems. [weak]

**Boundary conditions & caveats.** Assumes independence of detection and equal per-evaluator yield; model slightly underestimates N, so rely on "remaining problems" estimates. Costs/benefits are illustrative 1993 dollars. Model tested on single studies, extrapolated to iterative design.


---

## 01__Nielsen-Molich-1990_Heuristic-evaluation — Heuristic Evaluation of User Interfaces (Nielsen & Molich, 1990, CHI '90)
**Type:** empirical study  ·  **Sample/method:** Four experiments with non-expert evaluators: Teledata (37 CS students, 10 screen dumps, 52 known problems), Mantel (77 Computerworld readers, written spec, 30 problems), Savings voice-response (34 CS students, live, 48 problems), Transport voice-response (same 34 students, live, 34 problems). Monte Carlo aggregation (5,000–9,000 random aggregates per size).

**Core claim.** Individual evaluators are poor at heuristic evaluation, but aggregating independent evaluations from three to five people finds a large share of problems.

**Key findings**
- Nine heuristics used: Simple and natural dialogue; Speak the user's language; Minimize user memory load; Be consistent; Provide feedback; Provide clearly marked exits; Provide shortcuts; Good error messages; Prevent errors.
- Mean proportion found by single evaluators: 51%, 38%, 26%, 20% across the four experiments (overall range 20–51%).
- Same evaluators across the two voice systems: weak correlation (R² = 0.33, p < 0.01).
- Problem detection is not a strict cumulative scale (Guttman R = 0.85; minimal marginal reproducibility 0.80; coefficient of scalability 0.06): poor evaluators sometimes find hard problems, good ones miss easy ones—hence aggregation helps.
- Aggregates: curves rise steeply from 1 to ~5 evaluators, flatten 5–10, diminishing returns ~10; five evaluators find about two thirds (more than half even for the hardest, Transport).
- Voice interfaces were hardest to evaluate (low persistence of messages); individual differences larger for harder interfaces.
- Example detection rates: Mantel overwrites entered number (95%); Transport jumps to main menu without cue (62%); "UNKNOWN IP" message (54%); hidden online help (35%); organization-centric keys instead of bus numbers (12%).
- Few false positives; method is cheap, intuitive, needs no advance planning, usable early; but rarely gives fixes and won't produce breakthroughs.

**Design rules derivable** (process)
- Use 3–5 independent evaluators per heuristic evaluation; merge their lists afterward. [strong — replicated across 4 experiments, aggregated later by N&L 1993]
- Have evaluators work independently before discussing. [weak — authors' belief, untested]
- Supplement HE with thinking-aloud testing. [moderate]
- For voice/ephemeral interfaces, expect lower detection; give evaluators more time or transcripts. [weak]
- Keep the user's input visible with the result; signal menu-level changes in voice menus; make help discoverable without the manual. [moderate — high-frequency problems]

**Boundary conditions & caveats.** Non-expert evaluators; small-scale interfaces; "known problems" list not validated by user tests; aggregation assumes a perfect merging authority.


---

## 01__Norman-1999_Affordance-conventions-and-design — Affordance, Conventions, and Design (Norman, 1999, interactions 6(3))
**Type:** theory (essay)  ·  **Sample/method:** Conceptual clarification; no data.

**Core claim.** On screens, designers control mainly *perceived* affordances; most of what designers call "affordances" are really conventions, feedback and cultural constraints, and the underlying conceptual model matters most.

**Key findings**
- Gibson's affordances are actor–world relationships that need not be visible; Norman's POET concerned "perceived affordance."
- A screen with a pointing device affords clicking anywhere; icons/cursors are visual feedback that *advertise* affordances, i.e., perceived affordances or symbolic communication that works only via convention.
- Affordances, feedback and perceived affordances can be manipulated independently.
- Three behavioral constraints: physical (cannot be ignored; e.g., cursor cannot leave screen), logical (reasoning, e.g., one of five targets off-screen → scroll), cultural (conventions, e.g., scroll bar behavior). Logical and cultural constraints are weaker but powerful design tools.
- Conventions "are not arbitrary: they evolve, they require a community of practice"; slow to adopt, slow to go away.
- Whether users share a convention must be decided by observation in their normal environment; 3–5 people suffice for most purposes (citing Nielsen).
- Most important design tool: coherence and understandability via an explicit, perceivable conceptual model.

**Design rules derivable**
- Make desired, relevant actions readily perceivable (visible signifiers), not merely possible. [weak — expert opinion, widely accepted]
- Rely on established conventions for controls; violate them only with strong justification. [weak]
- Use physical constraints (disable/hide invalid targets, restrict input to fields) to prevent impossible actions. [weak]
- Use logical constraints: make the structure visible so users can deduce remaining steps (e.g., partially visible content cues scrolling). [weak]
- Verify convention comprehension by watching real users doing real activities. [weak]
- Design one coherent conceptual model and keep every element consistent with it. [weak]

**Boundary conditions & caveats.** Opinion essay; predates touch-first UIs (touch noted as a case where screens can detect touching).


---

## 01__Norman-2010_Natural-user-interfaces-are-not-natural — Natural User Interfaces Are Not Natural (Norman, 2010, interactions 17(3))
**Type:** theory (opinion)  ·  **Sample/method:** Essay with examples (Wii bowling, Xerox PARC drag-to-printer, multi-click selection, flick momentum).

**Core claim.** Gesture/touch/speech interfaces are not inherently natural; they must still obey basic interaction principles—feedback, visibility of possibilities, a clear conceptual model, undo—and need standardized conventions.

**Key findings**
- GUI strength is visibility: menus make all actions visible and discoverable; systems that avoid this "suffer."
- Gestures are ephemeral (no record of path), lack feedback, and make the set of possibilities and precise dynamics hard to discover; few gestures are innate; meanings vary across cultures (Indian head shake).
- Fixes require conventional elements: menus, help, traces, tutorials, undo, feedback, guides.
- Flick momentum must be coupled with viscous friction; tuning is "an art" needing to become science.
- Physical gestures have side effects: Wii players released the controller and broke TV screens; warnings failed, a wrist-strap redesign was needed ("Proper behavior comes about through careful design, not through instruction manuals and warnings").
- Recognition must balance false responses to unintended movement against misses of intended gestures.
- Complex systems need specification of scope, range, temporal order and conditionals—gestures alone are like a language of only verbs.
- "standards are more important than optimization" (QWERTY example).

**Design rules derivable**
- Pair every gesture with immediate, interpretable feedback and an undo path. [weak — expert opinion]
- Provide visible hints/guides for available gestures; don't rely on hidden gestures alone. [weak]
- Follow existing platform gesture conventions over novel "better" gestures. [weak]
- Tune recognizers to minimize unintended activations, and provide constructive feedback for ambiguous input. [weak]
- Fix misuse through design, not warnings. [weak]
- For animated scrolling, apply momentum with gradual deceleration. [weak]

**Boundary conditions & caveats.** Opinion piece, 2010-era; no empirical data.


---

## 01__Smith-Mosier-1986_Guidelines-for-designing-UI-software — Guidelines for Designing User Interface Software (Smith & Mosier, 1986, MITRE ESD-TR-86-278 for USAF)
**Type:** guideline  ·  **Sample/method:** Compilation of 944 guidelines from literature, earlier ESD reports, standards (e.g., Engel & Granda 1975, MIL-STD-1472) and expert judgment; each guideline has a one-sentence statement, examples, exceptions, comments, references. Organized into six functional areas: Data Entry (199), Data Display (298), Sequence Control (184), User Guidance (110), Data Transmission (83), Data Protection (70).

**Core claim.** User interface software design can be improved by tailoring a comprehensive set of functional guidelines into project-specific design rules early in development, then testing with users; the single objective all experts agree on is consistency.

**Key findings / context reported**
- Designers estimated UI at 30–35% of operational software (range 3–100%).
- Keister & Gallaway (1983): simple UI improvements (formatting, consistent wording, online guidance, explicit error messages, no abbreviations) yielded 25% faster data entry and 25% fewer errors.
- Survey: practitioners applied only 40% of guidelines from a previous report. ONR bibliography: 564 items, only 17 offering design guidelines.
- Most guidelines rest on judgment rather than experimental data; survey respondents preferred "judgment now" over waiting for research.
- Assumes ~24×80 character displays; many guidelines won't apply to small/handheld displays.

**General principles (from section introductions)**
- Recurring cross-cutting concepts: **context, consistency, flexibility**.
- Data entry objectives: consistency of transactions; minimal entry actions; minimal memory load; compatibility of entry with display; user flexibility. Maintain context so data are never re-entered; user-paced entry ("machine-paced tasks are stressful and error-prone").
- Data display: guidelines govern *how* to present, not *what*—content requires task analysis; display only what the user needs; data ≠ information.
- Sequence control: "it is the user who should decide what needs doing and when"; consistent control over "smart shortcuts" ("Perhaps the most frequent mistake" of UI designers), shortcuts only as optional extras; "make the user's most frequent transactions the easiest to accomplish"; destructive actions should be two-step; UNDO even better.
- Dialogue-type table (training required / tolerable response speed): Q&A little/none, moderate; Form filling moderate/little, slow; Menu little/none, very fast; Function keys moderate/little, very fast; Command language high, moderate/slow; Query language high/moderate, moderate; Natural language moderate/little, fast; Graphic interaction high, very fast.
- User guidance: "for every action (input) by the user there should be a noticeable reaction"; don't rely on users remembering prior actions—display context; instructions consistently placed (e.g., bottom); a 10-minute learning cost for a 10-second saving in a rare task means design has "outpaced user needs."
- Data protection dilemma: make legitimate transactions easy and mistaken/unauthorized ones hard; confirmations that are required for every routine overwrite become routine and lose protective value—confirm selectively, show enough file info to decide.
- Applying guidelines: select relevant ones, resolve conflicts, translate into specific documented design rules agreed by the team, weight them, evaluate the finished design against them; impose the *process* of rule-making, not the rules; guidelines cannot replace experience, task analysis, or prototype testing with users.

**Selected guidelines (number, title — statement condensed)**

*1 Data Entry*
- 1.0/1 Data Entered Only Once — users enter any datum once; system reuses it.
- 1.0/3 Feedback During Data Entry — feedback for all entry actions; echo keystrokes (except passwords).
- 1.0/4 Fast Response — acknowledge entry actions within 0.2 s.
- 1.0/5 Single Method for Entering Data — let users stay with one entry method.
- 1.0/7 Consistent Method for Data Change — always allow changing prior entries/defaults.
- 1.0/8 User-Paced Data Entry.
- 1.0/9 Explicit ENTER Action — no processing as a side effect of other actions.
- 1.0/11 Explicit CANCEL Action.
- 1.0/12 Feedback for Completion of Data Entry — confirm success or show error.
- 1.0/15 Keeping Data Items Short — coded items ≤5–7 characters.
- 1.0/24 Prompting Data Entry — prompt required formats and acceptable values.
- 1.0/27 Upper and Lower Case Equivalent (coded data).
- 1.1/5 Fast Acknowledgement of Entry — pointing acknowledged within 0.2 s.
- 1.1/13 Large Pointing Area for Option Selection — at least label area plus a half-character margin.
- 1.3/33 Reversible Actions — any text-editing action immediately reversible.
- 1.4/5 Data Field Labels; 1.4/8 Labels Close to Data Fields (but ≥1 space apart).
- 1.4/12 Marking Required and Optional Data Fields — clearly and consistently.
- 1.4/20 Data Format Cueing in Labels; 1.4/21 Labeling Units of Measurement in the label, not entered by user.
- 1.4/28 Automatic Cursor Placement — at the first entry field.
- 1.7/1 Automatic Data Validation; 1.7/2 Accepting Correct Entries — every possible correct entry accepted.
- 1.7/3 Non-Disruptive Error Messages — report at completion of entry; don't interrupt.
- 1.7/4 Deferral of Required Data Entry — allow marked temporary omission.
- 1.8/1 Default Values; 1.8/4 Display of Default Values in their fields.
- 1.8/8 Automatic Computation of Derived Data.

*2 Data Display*
- 2.0/1 Necessary Data Displayed; 2.0/2 Only Necessary Data Displayed — don't overload.
- 2.0/3 Data Displayed in Usable Form — don't make users convert data.
- 2.0/4 Consistent with User Conventions; 2.0/6 Consistent Display Format.
- 2.0/11 Context for Displayed Data — recapitulate so users needn't rely on memory.
- 2.0/12 Familiar Wording — users' task jargon, not programmers'.
- 2.0/16 Minimal Use of Abbreviation.
- 2.1/6 Conventional Use of Mixed Case; 2.1/11 Clarity of Wording; 2.1/13 Simple Sentence Structure; 2.1/16 Affirmative Sentences; 2.1/17 Active Voice.
- 2.1/19 Lists for Related Items rather than continuous text.
- 2.3/1 Tables for Data Comparison; 2.3/16 Justification of Numeric Data on decimal point / right-justify.
- 2.4.1/6 Numeric Scales Start at Zero (for comparing aggregates).
- 2.4.1/13 Restricted Use of Three-Dimensional Scaling.
- 2.4.5/1 Restricted Use of Pie Charts — bar graphs permit more accurate interpretation.
- 2.5/1 Consistent Format (location of features across displays); 2.5/3 Spacing to Structure Displays.
- 2.5/4 Paging Crowded Displays; 2.5/5 Related Data on Same Page.
- 2.5/10 Display Title at Top; 2.5/11 Command Entry, Prompts, Messages at Bottom.
- 2.5/12 Logical Data Organization; 2.5/14–17 group by sequence of use, function, importance, frequency.
- 2.6/1 Highlighting Critical Data — most effective when used sparingly.
- 2.6/6 Definition of Display Codes; 2.6/7 Consistent Coding Across Displays.
- 2.6/22 Adequate Differences in Size — larger symbol ≥1.5× height of next smaller.
- 2.6/23 Limited Use of Brightness Coding — treat as two-valued.
- 2.6/26 Color Coding for Data Categories — no more than five colors for category coding (≈11 distinguishable).
- 2.6/28 Conservative Use of Color; 2.6/29 add color only after monochrome design is effective; 2.6/30 Redundant Color Coding — never code only by color; 2.6/32 Conventional Assignment of Color Codes.
- 2.6/35 Blink Coding for urgent attention; 2.6/37 Optimal Blink Rate 2–5 Hz, ≥50% ON.
- 2.7.1/6 Fast Response to Display Request — 0.5–1.0 s for simple requests.
- 2.7.2/7 Consistent Orientation — panning vs. scrolling, chosen once.
- 2.7.2/15 Show Overview Position of Visible Section.
- 2.7.3/2 Highlighting Changed Data after automatic updates.
- 2.7.5/7 Indicate Active Window.

*3 Sequence Control*
- 3.0/1 Flexible Sequence Control; 3.0/2 Minimal User Actions.
- 3.0/3 Control Matched to User Skill — step-by-step for beginners, commands for experts.
- 3.0/5 Control by Explicit User Action; 3.0/6 Consistent User Actions.
- 3.0/9 Displayed Context when control effects depend on prior actions.
- 3.0/14 Feedback for Control Entries — every action gets an apparent reaction.
- 3.0/15 Indicating Completion of Processing for lengthy operations.
- 3.0/18 Appropriate Computer Response Time — NEXT PAGE 0.5–1.0 s; other simple entries ≤2.0 s; error messages 2–4 s.
- 3.0/19 Control Availability — lockouts ≤0.2 s; 3.0/20 Indicating Control Lockout.
- 3.1.3/2 Single Selection Per Menu; 3.1.3/3 Single-Column List Format.
- 3.1.3/10 Explanatory Title for Menu.
- 3.1.3/16 Explicit Option Display — show small option sets rather than requiring recall.
- 3.1.3/21 Logical Ordering of Menu Options — else by frequency, most frequent first.
- 3.1.3/27 Minimal Steps in Sequential Menu Selection — but not at the cost of crowding.
- 3.1.3/30 Indicating Current Position in Menu Structure; 3.1.3/33 one simple action to return up a level.
- 3.1.3/35 By-Passing Menu Selection with Command Entry for experts.
- 3.1.4/11 Indicating Active Function Keys.
- 3.1.5/5 Meaningful Command Names; 3.1.5/20 Interpreting Misspelled Commands.
- 3.1.8/4 Supplementary Verbal Labels for icons; 3.1.8/5 Direct Manipulation for casual users.
- 3.2/10 Only Available Options Offered.
- 3.3/1 User Interruption of Transactions; 3.3/3 CANCEL Option; 3.3/4 BACKUP Option.
- 3.4/4 Display of Operational Mode.
- 3.5/1 Appropriate Response to All Entries, correct and incorrect.
- 3.5/7 User Confirmation of Destructive Entries (esp. if not easily reversible).
- 3.5/10 UNDO to Reverse Control Actions; 3.5/11 Preventing Data Loss at LOG-OFF.

*4 User Guidance*
- 4.0/6 Consistent Display Format — same data always in the same place and way.
- 4.0/16 Familiar Wording; 4.0/17 Task-Oriented Wording; 4.0/19 Speaking Directly to Users.
- 4.0/25 Easy Ways to Get Guidance — switch easily between task and guidance.
- 4.1/1 Indicating Status at all times.
- 4.2/1 Consistent Feedback — every input yields perceptible response; screen never blank.
- 4.2/2 Fast Response with consistent timing; 4.2/8 Indicating Operational Mode.
- 4.3/1 Informative Error Messages — what is wrong and what can be done.
- 4.3/2 Specific; 4.3/3 Task-Oriented; 4.3/4 Advisory (list correct alternatives); 4.3/5 Brief.
- 4.3/6 Neutral Wording — no blame, no personalizing the computer, no humor.
- 4.3/7 Multilevel Error Messages (more detail on request).
- 4.3/13 Cursor Placement Following Error; 4.3/14 Displaying Erroneous Entries until corrected; 4.3/16 Removing Error Messages once fixed.
- 4.4/1 Guidance Information Always Available; 4.4/7 Prompting Entries.
- 4.4/13 Displayed Context.
- 4.4/23 HELP; 4.4/25 Task-Oriented HELP; 4.4/28 Multilevel HELP.

*5 Data Transmission*
- 5.0/4 Minimal Memory Load on User.
- 5.3/2 User Review Before Transmission.
- 5.4/7 Notification of Transmission Failure with explanation.
- 5.5/5 Nondisruptive Notification of Arriving Messages.

*6 Data Protection*
- 6.0/8 Appropriate Ease or Difficulty of User Actions — frequent/urgent easy; destructive harder.
- 6.0/11 Disabling Unneeded Controls.
- 6.0/13 Safe Defaults.
- 6.0/15 Explicit Action to Select Destructive Modes.
- 6.0/17 Warning Users of Potential Data Loss.
- 6.0/18 User Confirmation of Destructive Actions; 6.0/19–20 distinctive, separate CONFIRM action.
- 6.0/21 Reversible Control Actions (UNDO).
- 6.1/5 Private Entry of Passwords.
- 6.3/9 Immediate Error Correction; 6.3/17 Validating Data Changes.

**Design rules derivable**
- Acknowledge keystrokes/pointing within 0.2 s; respond to simple display requests within 0.5–1.0 s; other simple actions ≤2 s; announce longer delays and completion. [moderate — derived from cited standards/literature; values are 1986 judgments]
- Never require re-entry of known data; prefill defaults, derive computed values, accept all valid formats. [moderate]
- Require explicit commit (ENTER) and allow explicit cancel/back/undo at every step. [moderate]
- Validate at completion, keep the erroneous entry visible, place cursor at the error, remove message when fixed. [weak–moderate]
- Error messages: specific, task-worded, brief, neutral, offering correct alternatives and optional detail. [moderate — corroborated by Molich & Nielsen]
- Use ≤5 category colors, always redundantly coded; add color only after monochrome layout works. [moderate]
- Blink only for urgent items, 2–5 Hz. [weak]
- Prefer bar charts over pie charts; start comparative scales at zero; avoid 3-D scaling. [weak–moderate]
- Order menu options logically, else by frequency; show menu position; one action to go up; label icons with words. [moderate]
- Show current mode and context continuously. [moderate]
- Confirm only genuinely destructive or hard-to-reverse actions, with enough information to decide; prefer UNDO. [moderate]
- Turn general guidelines into a written, project-specific rule set before design starts. [weak — process advice]

**Boundary conditions & caveats.** 1986, character-terminal/military information-system context; many guidelines judgment-based; examples narrow and not meant to limit interpretation; some guidelines conflict and require trade-offs; much (e.g., function keys, 24×80 layout) is dated.


---

## Cross-paper patterns in this group
- **Feedback and visibility are the most robust principles.** They appear as Smith & Mosier's "every action gets a reaction," Molich & Nielsen's "Provide feedback," Nielsen 1994's top factor (visibility of system status), Hutchins et al.'s gulf of evaluation, and Norman 2010's critique of gestures. Recognition-over-recall (visible actions) best explains *serious* problems (Nielsen 1994: 22% marginal).
- **Consistency and convention are the next most cited.** Consistency is the single heuristic that explains the most problems (23%; Nielsen 1994) and the "single objective on which experts agree" (Smith & Mosier). Norman (1999, 2010) adds that conventions are real constraints and "standards are more important than optimization."
- **Error handling is under-practiced.** Designers rarely detect error-prevention issues (55% found none; 8% for accepting alternate formats). Guidance converges: prevent errors first, then give specific, constructive, non-blaming messages; keep input visible; provide undo, cancel, and clearly marked exits.
- **Single evaluators are unreliable.** One evaluator finds 20–51% (mean ~33%, λ = .31). Aggregating 3–5 independent evaluators finds roughly two thirds. Agreement between novice evaluators is very low (any-two 0.046), and even novice HE effectiveness can sit near 0.21 when checked against user tests. Expertise matters a lot: 22% → 41% → 60% per evaluator for none, usability, and usability+domain expertise.
- **"How many users/evaluators" depends on λ.** "Five" holds only when λ ≈ .3. With λ ≈ .22 you need at least 7 for 80% (Hvannberg). Iterate with small studies and estimate remaining problems from the data.
- **Inspection supplements user observation; it does not replace it.** Every empirical paper here recommends combining methods. Norman and Hollan et al. add that you should observe real people in real settings.
- **Directness and naturalness are not the same as usability.** Direct manipulation has costs (sets, variables, precision, repetition). "Natural" gestures still need feedback, discoverability, undo and standardization. Practice can make a bad interface *feel* direct.
- **Show information in the terms users evaluate it in.** Show rates, differences, positions relative to targets, and context recapitulation (water-tank rate display, airspeed dial as spatial anchor, Smith & Mosier 2.0/3 and 2.0/11).
- **Response-time thresholds are specific and old.** 0.2 s for input echo, 0.5–1.0 s for simple display requests, ≤2 s for simple actions, and announce longer waits with progress. They were judgment-based in 1986 but agree with Molich & Nielsen's 30-second-wait guidance.
- **Evidence strength varies by rule type.** Process rules (number of evaluators, combining methods) have the strongest quantitative support (13 datasets plus Monte Carlo). Most interface-level rules here rest on expert consensus or a single study. Treat them as well-established heuristics rather than effect-size-backed laws.
