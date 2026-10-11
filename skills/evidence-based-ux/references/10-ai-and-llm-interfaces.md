# Designing AI, agent and LLM-powered interfaces

> How to set expectations, gate autonomy, explain outputs, support correction, and scaffold prompting for AI-infused features, conversational agents, LLM tools and agents that act on the user's behalf. Evidence grades: **[A]** strong — replicated, large-N, meta-analytic, or an international standard; **[B]** moderate — one solid study or converging smaller studies; **[C]** weak — expert opinion, theory, small qualitative work, or extrapolation from lab psychology to UI.

## Rules

### AI-1. Inspect every AI feature against the 18 human-AI guidelines
- **Do:** Run a heuristic evaluation with at least 2–3 evaluators (the number used per product in the validation study; more find more, see EV-1) using all 18 guidelines, phase by phase:
  - *Initially:* G1 Make clear what the system can do. G2 Make clear how well the system can do what it can do.
  - *During interaction:* G3 Time services based on context. G4 Show contextually relevant information. G5 Match relevant social norms. G6 Mitigate social biases.
  - *When wrong:* G7 Support efficient invocation. G8 Support efficient dismissal. G9 Support efficient correction. G10 Scope services when in doubt. G11 Make clear why the system did what it did.
  - *Over time:* G12 Remember recent interactions. G13 Learn from user behavior. G14 Update and adapt cautiously. G15 Encourage granular feedback. G16 Convey the consequences of user actions. G17 Provide global controls. G18 Notify users about changes.
  Give extra scrutiny to G2, G11 and G17, which are the most often violated.
- **Why:** 49 practitioners testing 20 AI products found 313 applications and 277 violations; every guideline had at least one application or violation in every product category (Amershi 2019). G1, G4 and G12 were widely implemented; G2, G11 and G17 were relevant but under-implemented, and G11 had one of the highest violation counts (Amershi 2019). 8 of the 18 guidelines map to Horvitz's mixed-initiative principles (Amershi 2019; Horvitz 1999).
- **Evidence:** [B] — (Amershi 2019; Horvitz 1999).
- **Limits:** Validates relevance and clarity, not user outcomes. G3, G5 and G6 had the most "does not apply" ratings; G3 matters less for user-initiated ("pull") features. Less applicable to non-GUI AI (voice, sensors). High-risk domains may need specialized guidance. Guidelines can conflict (e.g., G16 vs G13 with complex models). Evaluators confused G1/G2/G11, G4/G13, G3/G4, G12/G13 and G15/G17; read the definitions carefully.

### AI-2. Reveal capabilities and limits proactively, not only at failure
- **Do:** At first use and in idle states, show what the AI can and cannot do with concrete, task-granular examples. Tell users whether and how it learns from them. Before users conclude the system "can't" do something after one failure, prompt them to rephrase.
- **Why:** G1 is the first guideline (Amershi 2019). Half of conversational-agent users explicitly did not know what their agent could do, whether capabilities changed, or whether it learned from them (Luger 2016). Users cannot form "how-to" procedures for an LLM (capability gap) (Subramonyam 2024). Non-experts over-generalized: one success was "fixed", one failure meant incapable ("I guess it doesn't like to tell jokes") (Zamfirescu-Pereira 2023). Capability uncertainty is one of two root causes of human-AI design difficulty (Yang 2020).
- **Evidence:** [B] — converging qualitative and framework sources (Amershi 2019; Luger 2016; Subramonyam 2024; Zamfirescu-Pereira 2023; Yang 2020).
- **Limits:** Luger 2016 is n=14 with 2014–2015 voice assistants; Zamfirescu-Pereira 2023 is n=10 with an older model.

### AI-3. State reliability as actionable limits, not a bare confidence score
- **Do:** Describe how often and in what ways the system errs, in task terms: "good enough for X, not for Y", "what kinds of mistakes", the precision/recall trade-off as consequences. Use hedging language for uncertain outputs ("we think you'll like"). Never show a bare confidence percentage as the only explanation for lay users.
- **Why:** G2 was among the most violated guidelines (Amershi 2019). Practitioners ranked raw performance information lowest; confidence scores were dismissed as non-actionable; users wanted "is the performance good enough for…" and "what kind of mistakes" (Liao 2020). Expectations for possibly wrong outputs must be set explicitly (Yang 2020).
- **Evidence:** [B] — (Amershi 2019; Liao 2020; Yang 2020).
- **Limits:** Liao 2020 elicited needs from 20 practitioners in one company, not end users. Performance may drift after deployment (AI-19).

### AI-4. Gate autonomy on confidence: do nothing, ask, or act
- **Do:** Define two thresholds per automated action. Below the lower one, do nothing (or show a passive hint). Between them, ask a clarifying question or offer 3–4 candidates. Above the upper one, act. Raise thresholds when the cost of an unwanted action is high (e.g., user in deep focus, irreversible action); lower them when errors are cheap (e.g., ample screen space for a dismissible suggestion).
- **Why:** Horvitz 1999 frames action as worthwhile only when the probability of the user's goal exceeds the point where expected utility of acting equals not acting; adding dialog creates two thresholds (inaction↔dialog, dialog↔action) that shift with context. G10 (scope services when in doubt) codifies disambiguation or graceful degradation under uncertainty and absorbed "fall back to a human" (Amershi 2019).
- **Evidence:** [B] — (Horvitz 1999; Amershi 2019).
- **Limits:** Horvitz 1999 is a position paper with one prototype; utilities must be assessed and vary by context. No G10 instances were observed in social networks (Amershi 2019).

### AI-5. When uncertain, do less but do it correctly
- **Do:** Under uncertainty, deliver a reduced-precision result that is right rather than a precise one that may be wrong. Example: open the relevant week instead of creating a guessed appointment; offer a list instead of auto-completing one choice.
- **Why:** Lookout showed a scoped week view when it could not identify a specific time, reflecting a preference for doing less but doing it correctly (Horvitz 1999). Minimizing the cost of poor guesses and scoping precision to uncertainty are principles 7 and 8 (Horvitz 1999); G10 (Amershi 2019).
- **Evidence:** [C] — (Horvitz 1999; Amershi 2019).
- **Limits:** Single prototype illustration; no controlled comparison.

### AI-6. Confirm before precise, costly, social or irreversible actions
- **Do:** Before an agent sends a message, places a call, purchases, deletes, or acts on the user's behalf in another system, show a visual summary of exactly what will happen and let the user review and edit before commit. Present agent results as editable drafts. A spoken confirmation is enough only for simple tasks that have succeeded repeatedly.
- **Why:** All conversational-agent users sought visual confirmation for complex tasks and avoided calls and messages where language had to be precise; spoken confirmation sufficed for simple, repeatedly successful tasks (Luger 2016). Horvitz 1999 recommends agent results as drafts the user refines (principle 9). G9 requires efficient correction (Amershi 2019). A visible commitment point parallels honest checkout design (cross-paper pattern in the summaries, with Mathur 2019).
- **Evidence:** [B] — (Luger 2016; Horvitz 1999; Amershi 2019).
- **Limits:** Luger 2016 is small (n=14). Confirming every trivial action adds friction; scale confirmation to cost (AI-4).

### AI-7. Make invoking, dismissing and stopping the AI one step each
- **Do:** Provide a one-step way to call the AI, ignore or dismiss a suggestion, and stop an agent mid-task. Accept natural rejections ("no", "not now", "go away"). Let unanswered offers time out gracefully, with the time-out set as a function of the agent's confidence that the user wants the service.
- **Why:** G7 (efficient invocation) and G8 (efficient dismissal) (Amershi 2019). Horvitz 1999 principle 6 (efficient direct invocation and termination); its social agent asked, waited, then made an apologetic gesture and disappeared if ignored, with the time-out a function of the inferred probability that the user wants the service (direction not specified).
- **Evidence:** [B] — (Amershi 2019; Horvitz 1999).
- **Limits:** Time-out behavior comes from one prototype with informal timing data.

### AI-8. Make outputs easy to correct and edit directly
- **Do:** Let users edit, refine or undo any AI output inline ("Tap to edit"). Expose intermediate artifacts (generated queries, goals, plans) for direct manual editing. Let users edit an earlier prompt and see its effect.
- **Why:** G9 (efficient correction) (Amershi 2019). Manual control of output is one of six LLM design patterns; for well-defined tasks people prefer dedicated interfaces; errors are breakdowns of a distributed system that need collaborative repair (Subramonyam 2024). Collaboration to refine results is Horvitz principle 9 (Horvitz 1999).
- **Evidence:** [B] — (Amershi 2019; Subramonyam 2024; Horvitz 1999).
- **Limits:** Subramonyam 2024 is theoretical with no user study.

### AI-9. Provide a retrievable "why" for every output, including "why not"
- **Do:** Attach a "Why am I seeing this?" or "Why this result?" explanation to every recommendation, decision or surprising output. Make it contrastive: let users name the expected alternative and ask "Why not X?". Select one or two main causes rather than an exhaustive list.
- **Why:** G11 had one of the highest violation counts and one of the fewest "does not apply"; users could imagine explanations but could not get them (Amershi 2019). Why and Why-not about a specific prediction ranked top and appeared in all products, usually after surprising outputs; tools answer Why but struggle with Why-not; only 37.5% of products explained individual decisions (Liao 2020). Every prompt-design participant asked "why did it do that?" and usually could not find out (Zamfirescu-Pereira 2023).
- **Evidence:** [B] — (Amershi 2019; Liao 2020; Zamfirescu-Pereira 2023).
- **Limits:** Explanations can conflict with proprietary data, legal or marketing concerns; over-transparency can expose rationales users find wrong or outdated (Liao 2020).

### AI-10. Choose explanations from the user's question, at several levels, interactively
- **Do:** Specify explainability needs as user questions from the nine categories: Input (training data), Output, Performance, How (global logic), Why, Why not, What if, How to be that (minimum change for a different result), How to still be this (maximum change that keeps the result). Map each to an explanation method. Offer multi-level "How" (top features, then full logic on demand). Support follow-up and terminology questions ("what do you mean by…"). Explain data provenance and known biases at onboarding. Keep explanations from breaking the primary workflow.
- **Why:** Liao 2020 built a question bank of 9 categories; 124 of 170 observed user questions fit it. Needs vary by usage point (onboarding, reliance, abnormal results, breakdown, system change), decision context and user type. Input and Output questions are mostly needed at onboarding. Counterfactual questions were rarely raised but seen as high-potential. Users also asked follow-up and terminology questions.
- **Evidence:** [C] — practitioner interviews (Liao 2020).
- **Limits:** Single organization; products skewed to high-stakes analytics; the bank is a starting point, not exhaustive.

### AI-11. Time proactive AI to the user's attention
- **Do:** Offer proactive help when the user is likely ready, not mid-focus. Delay offers longer after longer content. Show information relevant to the current task and environment.
- **Why:** G3 (time services based on context) and G4 (show contextually relevant information) (Amershi 2019). Considering attention in timing is Horvitz principle 3; preferred dwell time before an offer rose nonlinearly (sigmoid) with message length (Horvitz 1999).
- **Evidence:** [C] — (Amershi 2019; Horvitz 1999).
- **Limits:** Timing data came from a few users (Horvitz 1999). G3 was often judged irrelevant for user-initiated features (Amershi 2019).

### AI-12. Remember recent context, and show what is and is not remembered
- **Do:** Carry context across turns so users can refer back ("who is he married to"). If context is not retained, say so. Show the scope and lifetime of instructions and memory (this turn, this conversation, all conversations).
- **Why:** G12 (remember recent interactions) (Amershi 2019); Horvitz principle 11 (Horvitz 1999). Users expected context carry-over between turns (Luger 2016). Prompt designers expected memory across conversations and in-chat instructions to persist (Zamfirescu-Pereira 2023).
- **Evidence:** [B] — (Amershi 2019; Horvitz 1999; Luger 2016; Zamfirescu-Pereira 2023).
- **Limits:** Memory also raises privacy questions; pair it with global controls (AI-13).

### AI-13. Provide global controls, aggressiveness settings and a manual-only mode
- **Do:** Let users globally control what the AI monitors (location history, data use, private mode) and how it behaves. Let users set how aggressive automation is. Offer a manual-only mode that shows, passively, what the agent would have done. Label global controls as global, separate from per-item feedback.
- **Why:** G17 (global controls) was under-implemented; privacy permissions and private mode were merged into it (Amershi 2019). Horvitz 1999 let users set utilities or thresholds directly and offered a manual-only mode with a passive indicator.
- **Evidence:** [B] — (Amershi 2019; Horvitz 1999).
- **Limits:** Evaluators confused G15 (granular feedback) with G17; keep the two visibly distinct (Amershi 2019).

### AI-14. Collect granular feedback and show its consequence immediately
- **Do:** Offer instance-level feedback (mark important / not, hide this) during normal use. Immediately state how the feedback will change future behavior ("Hiding this ad adjusts future ads").
- **Why:** G15 (encourage granular feedback) and G16 (convey consequences of user actions) (Amershi 2019). Users did not know whether the agent learned from them (Luger 2016). Practitioners reported users want to know how they can change the system (Liao 2020).
- **Evidence:** [B] — (Amershi 2019; Luger 2016; Liao 2020).
- **Limits:** With complex models, G16 can be hard to honor accurately (Amershi 2019).

### AI-15. Adapt cautiously and announce changes
- **Do:** When learning or updating, change only the affected part of the UI and keep previously seen content stable. Announce new or changed capabilities (in-app callouts; pop-ups only for changes that need attention). Explain how behavior changed and why.
- **Why:** G13 (learn from user behavior), G14 (update and adapt cautiously), G18 (notify users about changes) (Amershi 2019). New explanation needs included how the system changes and adapts (Liao 2020). Continuing to learn by observing is Horvitz principle 12 (Horvitz 1999).
- **Evidence:** [C] — (Amershi 2019; Liao 2020; Horvitz 1999).
- **Limits:** G14 was not observable in one session for activity trackers (Amershi 2019).

### AI-16. Do not let personality inflate expected intelligence
- **Do:** Audit humor, Easter eggs and persona responses for the capability they imply. Prefer tool-like framing when capability is narrow. Phrase failures so the system, not the user, takes responsibility. Consider seamful cues that expose non-humanness.
- **Why:** Playful responses cemented anthropomorphic, inflated expectations; Siri's personality raised expectations while Google Now, framed as a tool, had more accurate ones; less technical users blamed themselves for failures (Luger 2016). Social expectations led prompt designers to politeness, "don't" phrasing and avoidance of examples (Zamfirescu-Pereira 2023).
- **Evidence:** [C] — (Luger 2016; Zamfirescu-Pereira 2023).
- **Limits:** Small samples; play did aid discovery (Luger 2016).

### AI-17. Never fail silently or fall back without saying so
- **Do:** When the agent cannot do the requested action, state that it failed, say why if known, and suggest a supported phrasing. Do not silently replace an actionable request with generic web-search results.
- **Why:** Defaulting to web search was universally seen as a failure (Luger 2016). Users repeatedly simplified their language until success, which hurt ease of use (Luger 2016). G10 calls for graceful degradation that the user can see (Amershi 2019).
- **Evidence:** [C] — (Luger 2016; Amershi 2019).
- **Limits:** Based on 2014–2015 voice assistants.

### AI-18. Make core tasks reliable first; early failures set expectations for good
- **Do:** Launch with a narrow set of tasks that succeed reliably, and steer first-time users toward them. Validate recognition across voices, accents and genders before launch.
- **Why:** After failing a key task 2–6 times, users fixed low expectations and relegated the agent to trivial tasks (Luger 2016). Misrecognition was the most cited failure; all but one woman found the agent unable to dependably recognize her voice (Luger 2016). Performance can be worse for infrequent users and atypical contexts (Yang 2020).
- **Evidence:** [C] — (Luger 2016; Yang 2020).
- **Limits:** n=14, mostly male, UK-centric (Luger 2016).

### AI-19. Classify the feature by capability uncertainty and output complexity, and design for every outcome
- **Do:** Before choosing methods, place the feature on two axes: capability uncertainty (how well it works, how that changes after deployment) and output complexity (few fixed outputs vs open-ended adaptive ones). For Level-1 features (known capability, few outputs, static model) design explicitly for true positive, true negative, false positive and false negative. For systems that learn after deployment (Level 4: search, feeds, recommenders, auto-replies), plan for performance drift, monitor error modes over time, and design for degraded performance for infrequent users. Prefer Level-1 features as entry points for teams new to AI.
- **Why:** Yang 2020 identifies capability uncertainty and output complexity as the two properties that make human-AI interaction hard and defines four levels; Level 1 can be designed with standard HCI methods; Level 4 challenges are a superset of Levels 2–3. Output complexity is not the same as unpredictability (Yang 2020).
- **Evidence:** [B] — framework built from multiple practitioner studies (Yang 2020).
- **Limits:** Not empirically validated; cases drawn mostly from the authors' own work; Level 2–3 definitions appear only in a figure (Yang 2020).

### AI-20. Do not trust Wizard-of-Oz tests for error experience; prototype with real models
- **Do:** Use Wizard-of-Oz or rule-based simulators only for Levels 1–2. Do not treat them as evidence of how inference errors will feel. Prototype early with real data and working models. Involve AI engineers throughout design, not at a final handoff. Evaluate fairness as a situated experience after deployment.
- **Why:** Wizard of Oz cannot simulate inference errors; rule-based simulators cannot prototype systems that learn from user data (Levels 3–4) (Yang 2020). No empirical evaluations of proposed AI design tools were found (Yang 2020). G6 (mitigate social biases) and G5 (match social norms) (Amershi 2019).
- **Evidence:** [C] — (Yang 2020; Amershi 2019).
- **Limits:** Framework-level guidance; G5 and G6 were rated hardest to judge outside one's own social context (Amershi 2019).

### AI-21. Replace the blank chat box with scaffolding for complex tasks
- **Do:** For generative or well-defined tasks, embed the LLM in a dedicated task UI rather than offering only a free-text box. Provide task-aware templates that ask for missing elements ("Who is your audience?"), concrete example prompts at task granularity, autocomplete from a shared vocabulary, and a searchable library of working examples shown when users get stuck.
- **Why:** LLMs open a gulf of envisioning with three gaps: capability (users cannot form procedures), instruction (small wording changes cause very different outputs) and intentionality (stating only a goal skips planning and leaves no benchmark for evaluating output) (Subramonyam 2024). Generic example prompts are too coarse for planning; semi-structured, templated intent is recommended as a sweet spot (Subramonyam 2024). Non-experts relied on ad hoc trial and error (Zamfirescu-Pereira 2023).
- **Evidence:** [C] — (Subramonyam 2024; Zamfirescu-Pereira 2023).
- **Limits:** Subramonyam 2024 has no user study and centers on writing; deep envisioning may be rare in practice.

### AI-22. Show multiple outputs, and keep history and diffs
- **Do:** Generate several alternative outputs per prompt and support grouping and comparison. Preserve every prompt, regeneration and output, side by side, with diffs between prompt versions and between outputs. Let users branch and fork lines of exploration.
- **Why:** Iteration risks fixation on the first output; multiple outputs support divergent thinking; ChatGPT and Cursor lacked regeneration history (Subramonyam 2024). Showing prompt diffs with output diffs helps users map input changes to output changes (Zamfirescu-Pereira 2023).
- **Evidence:** [C] — (Subramonyam 2024; Zamfirescu-Pereira 2023).
- **Limits:** Branching (node/tree views) is the weakest-supported pattern (Subramonyam 2024).

### AI-23. Calibrate trust; design against over-reliance
- **Do:** Aim explanations and UI at appropriate trust, not maximum trust. Prompt users to check outputs, especially when they stated only a goal. Provide inline comments, diffs or multi-level summaries that make outputs checkable.
- **Why:** Calibrating trust, not just raising it, was a stated motivation for explanation (Liao 2020). The intentionality gap leaves users without internal benchmarks, risking over-reliance (Subramonyam 2024).
- **Evidence:** [C] — (Liao 2020; Subramonyam 2024).
- **Limits:** No outcome data in either source.

### AI-24. In prompt-authoring tools, build in testing and good-prompt guidance
- **Do:** Encourage multiple test conversations and re-running saved failing cases after every prompt change (regression testing). Give heuristics on how many test cases are enough. Recommend positive phrasing ("Do Y") over negations ("Don't do X"), and lint for negations. Make adding example dialogues easy. Show instruction scope (preamble, reminder, in-conversation). Separate instructions to the model from content for the end user.
- **Why:** None of 10 participants ran more than one or two conversations before "fixing", none used the systematic testing interface, and labeling was abandoned (Zamfirescu-Pereira 2023). "Don't do X" was more common but less effective than "Do Y" and could trigger the forbidden phrase (Zamfirescu-Pereira 2023). Participants preferred direct instruction to examples, though copied example dialog worked (Zamfirescu-Pereira 2023). Users must be trained and encouraged to test systematically (Zamfirescu-Pereira 2023).
- **Evidence:** [C] — (Zamfirescu-Pereira 2023).
- **Limits:** n=10, STEM-skewed, 1-hour sessions, text-davinci-002; newer models may respond differently to negations.

### AI-25. Keep the agent's state and actions visible
- **Do:** Show what the agent is doing, has done, and plans to do, in plain terms. Log actions taken on the user's behalf and make each one reviewable and, where possible, reversible. In hands-busy contexts (driving, cycling, childcare), complete flows without forcing a switch to screen or manual input; if a switch is needed, say so up front.
- **Why:** Users did not understand what the system was doing or how (Luger 2016). Horvitz 1999 shows a passive indicator of what the agent would have done and treats the cost of poor guesses as central. G16 asks the system to convey consequences immediately (Amershi 2019). The primary voice use case was hands-free during demanding activities, and failures needing manual intervention were rarely forgiven (Luger 2016).
- **Evidence:** [C] — derived from (Luger 2016; Horvitz 1999; Amershi 2019); none of these studied autonomous multi-step agents directly.
- **Limits:** Extrapolation from 1999 prototypes and 2014–2015 voice assistants to modern agents.

## Numbers at a glance
| Parameter | Value | Grade | Source |
|---|---|---|---|
| Human-AI guidelines | 18, in 4 phases | B | Amershi 2019 |
| Applications / violations found | 313 / 277 across 20 products | B | Amershi 2019 |
| Most under-implemented guidelines | G2, G11, G17 | B | Amershi 2019 |
| Guidelines mapping to mixed-initiative principles | 8 of 18 | B | Amershi 2019 |
| Mixed-initiative principles | 12 | C | Horvitz 1999 |
| Autonomy thresholds | 2 (inaction↔dialog, dialog↔action) | C | Horvitz 1999 |
| Candidate suggestions when uncertain | 3–4 | C | Amershi 2019 |
| Failures before expectations are fixed | 2–6 | C | Luger 2016 |
| Users who did not know agent capabilities | about half of 14 | C | Luger 2016 |
| XAI question categories | 9 | C | Liao 2020 |
| Observed user questions covered by the bank | 124 of 170 | C | Liao 2020 |
| Products explaining data/algorithm vs individual decisions | 68.8% vs 37.5% | C | Liao 2020 |
| AI system levels (capability uncertainty × output complexity) | 4 | C | Yang 2020 |
| Gulf-of-envisioning gaps | 3 (capability, instruction, intentionality) | C | Subramonyam 2024 |
| LLM interface design patterns | 6 | C | Subramonyam 2024 |
| Prompt-design participants who used systematic testing | 0 of 10 | C | Zamfirescu-Pereira 2023 |

## Common misreadings
- "Show a confidence score and you have explained the AI." — Confidence scores were seen as non-actionable; users want limits and error types (Liao 2020).
- "AI is hard to design because it is unpredictable." — Output complexity, not unpredictability, is the issue; a random-word bot is unpredictable but easy to simulate (Yang 2020).
- "All AI features need new design methods." — Level-1 systems can be designed with standard HCI methods (Yang 2020).
- "A Wizard-of-Oz test shows how users will handle AI errors." — It cannot simulate inference errors (Yang 2020).
- "A chat box is the most flexible, so it is the best interface." — It shifts the burden of forming intentions onto users; dedicated, scaffolded UIs are preferred for well-defined tasks (Subramonyam 2024).
- "If the prompt worked once, it is fixed." — Single successes and single failures misled every participant (Zamfirescu-Pereira 2023).
- "The 18 guidelines are proven to improve outcomes." — Amershi 2019 validated relevance and clarity, not user outcomes.
- "A friendly personality builds trust." — Personality inflated expectations that later failures punished (Luger 2016).

## Review checklist
- [ ] AI-1: Has the feature been inspected against all 18 guidelines, with G2, G11 and G17 checked explicitly?
- [ ] AI-2: Does the UI show what the AI can and cannot do, with concrete examples, before any failure?
- [ ] AI-3: Is reliability expressed as task-level limits and error types rather than a bare confidence number?
- [ ] AI-4: Are there defined confidence thresholds for doing nothing, asking, and acting, tuned to the cost of error?
- [ ] AI-5: Under uncertainty, does the system return a correct reduced-precision result instead of a precise guess?
- [ ] AI-6: Are costly, social, precise or irreversible agent actions confirmed with a reviewable, editable summary?
- [ ] AI-7: Can the user invoke, dismiss and stop the AI in one step each, and do ignored offers time out gracefully?
- [ ] AI-8: Can every output and intermediate artifact be edited directly?
- [ ] AI-9: Does every output have a retrievable "why" and support "why not X?"
- [ ] AI-10: Were explanation needs specified as user questions from the nine categories, with multi-level, interactive answers?
- [ ] AI-11: Are proactive offers timed to the user's attention and relevant to the current task?
- [ ] AI-12: Is recent context carried across turns, and is the scope of memory and instructions visible?
- [ ] AI-13: Are there global controls over monitoring and behavior, an aggressiveness setting, and a manual-only mode?
- [ ] AI-14: Is per-item feedback available, with its effect on future behavior stated immediately?
- [ ] AI-15: Do adaptations change only affected UI, and are capability changes announced and explained?
- [ ] AI-16: Do persona, humor and copy avoid implying more intelligence than the system has, and does the system take blame for failures?
- [ ] AI-17: Are failures stated explicitly with a suggested alternative, with no silent fallback?
- [ ] AI-18: Do first-time users land on reliable core tasks, and was recognition validated across diverse users?
- [ ] AI-19: Is the feature classified by capability uncertainty and output complexity, with designs for all four confusion-matrix outcomes or for drift?
- [ ] AI-20: Was the design tested with a real model (not only Wizard-of-Oz), with engineers involved throughout?
- [ ] AI-21: Is the LLM embedded in a task-specific UI with templates and task-level examples instead of only a blank box?
- [ ] AI-22: Can users see multiple outputs, full history, and diffs between versions?
- [ ] AI-23: Does the UI prompt users to verify outputs rather than maximize trust?
- [ ] AI-24: Does the prompt-authoring tool support regression tests, positive phrasing, examples, and visible instruction scope?
- [ ] AI-25: Is the agent's current status and action log visible, reviewable and reversible, and does it work hands-free where needed?

## Sources
- Amershi, S., et al. (2019). *Guidelines for human-AI interaction*. CHI '19. https://doi.org/10.1145/3290605.3300233
- Horvitz, E. (1999). *Principles of mixed-initiative user interfaces*. CHI '99. https://doi.org/10.1145/302979.303030
- Liao, Q.V., Gruen, D., Miller, S. (2020). *Questioning the AI: informing design practices for explainable AI user experiences*. CHI '20. https://doi.org/10.1145/3313831.3376590
- Luger, E., Sellen, A. (2016). *"Like having a really bad PA": the gulf between user expectation and experience of conversational agents*. CHI '16. https://doi.org/10.1145/2858036.2858288
- Mathur, A., et al. (2019). *Dark patterns at scale: findings from a crawl of 11K shopping websites*. Proc. ACM HCI (CSCW '19). https://doi.org/10.1145/3359183
- Subramonyam, H., Pea, R., Pondoc, C.L., Agrawala, M., Seifert, C. (2024). *Bridging the gulf of envisioning: cognitive challenges in prompt based interactions with LLMs*. CHI '24. https://doi.org/10.1145/3613904.3642754
- Yang, Q., Steinfeld, A., Rosé, C., Zimmerman, J. (2020). *Re-examining whether, why, and how human-AI interaction is uniquely difficult to design*. CHI '20. https://doi.org/10.1145/3313831.3376301
- Zamfirescu-Pereira, J.D., Wong, R., Hartmann, B., Yang, Q. (2023). *Why Johnny can't prompt: how non-AI experts try (and fail) to design LLM prompts*. CHI '23. https://doi.org/10.1145/3544548.3581388
