# Group G (part 2): Human-AI interaction, conversational agents, LLM prompting, dark patterns

---

## 09__Liao-2020_Questioning-the-AI-XAI-UX — Questioning the AI: Informing Design Practices for Explainable AI User Experiences (Q. Vera Liao, Daniel Gruen, Sarah Miller, 2020, CHI 2020)
**Type:** empirical (qualitative interview study) + framework (XAI question bank)  ·  **Sample/method:** Semi-structured interviews (45–60 min) with 20 UX/design practitioners across IBM AI products, using an algorithm-informed "XAI question bank" as a card-based probe (MURAL); grounded-theory-style open/axial coding.

**Core claim.** Whether an explanation is good depends on the question the user is asking; explainability needs should be specified as prototypical user questions and then mapped to explanation methods, because current algorithm-centric XAI misses many real user needs (e.g., Why-not, How-to-be-that, change over time).

**Key findings**
- Question bank: 9 explainability-need categories — Input (training data), Output, Performance, How (global model), Why, Why not, What if, How to be that (minimum change for a different prediction), How to still be this (maximum permitted change for same prediction); plus an "Others" category.
- Table 1 maps explanation methods to questions: global (feature importance, decision-tree approximation, rule extraction) → How (+Why/Why not/What if); local (feature importance/saliency, local rules/trees) → Why, How to still be this; inspect-counterfactual (feature influence, contrastive features) → What if, How to be that, Why not; example-based (prototypes, counterfactual examples) → Why, Why not, How to be that.
- Product status: ~two-thirds of products (68.8%) had descriptive explanations about data or algorithm; only 37.5% explained individual decisions; some (e.g., chatbot) had neither.
- ~1000 minutes recorded; 607 passages; 24 axial codes; 170 user questions identified, 124 covered by the bank, 46 uncovered (22 excluded as non-generalizable; 24 yielded 5 new question forms).
- Motivations for explanation: gain insight/evidence for decisions, appropriately evaluate (calibrate, not just increase) trust, adapt usage/interaction, improve the model (feedback loop), ethical responsibility.
- Factors driving variability of needs: motivation, usage point (onboarding, reliance/delegation, abnormal results, breakdown, system change), algorithm/data type, decision context (criticality, time-sensitivity, complexity), user type (AI knowledge, domain knowledge, attitude, role).
- Why/Why-not about a specific prediction was ranked at the top and appeared in all products, typically after surprising outputs; tools answer Why but struggle with Why-not.
- Performance was "repeatedly ranked at the bottom," especially for non-AI users in less critical contexts; confidence scores were dismissed as non-actionable; users want "is the performance good enough for…" and "what kind of mistakes".
- Output questions focused on how to best utilize output, scope of capability, and how output impacts other system components; Input/Output explanations are "static," mostly needed at onboarding.
- Counterfactual (What if/How to be) was ranked low (only 3 user questions) but seen as high-potential utility features.
- New needs: how the system changes/adapts and how users can change it; follow-up and terminological questions ("what do you mean by…"); social explanations (other users' outcomes).
- Tensions: explainability vs. proprietary data, legal/marketing concerns, seamless workflow integration; over-transparency can expose rationales users find "wrong," "over-simplified," or "outdated."

**Design rules derivable**
- Specify explainability requirements by eliciting which user questions (from the 9 categories) arise at each usage point; prioritize before choosing an XAI algorithm. [moderate]
- Provide a local "Why this output?" explanation wherever outputs can surprise users; make it contrastive by letting users name the expected alternative (Why not X?). [moderate]
- Frame performance information as actionable limits ("good enough for what," "what kinds of mistakes," precision/recall trade-off in task terms), not raw accuracy or bare confidence scores. [moderate]
- Never present a bare confidence percentage as the sole explanation to lay users. [weak]
- Explain training-data provenance, sample size, sub-group coverage, and known biases at onboarding and for quality-control roles. [moderate]
- Offer multi-level "How" explanations (top features / is feature X used → full logic on demand) rather than one fixed depth. [moderate]
- Make explanations interactive/conversational so users can ask follow-ups and terminology questions. [moderate]
- Explain changes when the AI's behavior or model updates, and how users can influence it. [moderate]
- Choose explanation form by user goal: example-based explanations for insight-seeking/analogy-reliant users; both positive and negative evidence when the goal is bias mitigation. [weak]
- Don't let explanations break primary workflow; select one or two causes rather than exhaustive lists. [moderate]
- For conversational agents, use explanations to tell users what they can ask and how phrasing changes interpretation ("How to be that"). [weak]

**Boundary conditions & caveats.** Needs elicited from practitioners, not end users; single organization (IBM); products skewed to high-stakes analytics/decision support; XAI methods list not exhaustive and field moving fast; the question bank is a starting point, not exhaustive.


---

## 09__Luger-Sellen-2016_Conversational-agents-expectation-gulf — "Like Having a Really bad PA": The Gulf between User Expectation and Experience of Conversational Agents (Ewa Luger, Abigail Sellen, 2016, CHI 2016)
**Type:** empirical (qualitative)  ·  **Sample/method:** 14 semi-structured remote interviews (9 male, 5 female, aged 25–60; 19:32–48:50 min; Nov 2014–Feb 2015) with regular (≥1 month) users of Siri (10), Google Now (5), Cortana (1); Thematic Network Analysis to saturation.

**Core claim.** User expectations of conversational agents (CAs) are dramatically out of step with system capability; poor feedback about capability and "intelligence," reinforced by playful/humorous responses, produces wide gulfs of execution and evaluation, leading users to restrict CAs to trivial tasks.

**Key findings**
- Most frequent tasks were simple (weather, then reminders); users began with natural language, then simplified until success. All described an "economy of language" (keywords, slower/clearer enunciation, changed accent); over half said this hurt ease of use.
- Only one user reported the CA as their preferred task interface; for all but three, CAs were "entertaining/gimmicky." Two "serious" users invested effort (testing syntax, training contacts/locations) and were more satisfied and forgiving.
- All but one began with play (Easter eggs); play aided discovery but cemented anthropomorphic, inflated expectations.
- After failing a key task "between 2 and 6" times in most cases, expectations were set and the CA was relegated to basic tasks.
- Misrecognition was the most cited failure cause; all but one woman found the CA unable to dependably recognize their voice.
- Half explicitly did not know what their CA could do; users lacked understanding of what the system could do, what it was doing, how, whether capabilities changed over time, and whether it learned from them.
- Less technical users had higher initial expectations, blamed themselves for failures ("making me feel really stupid"), used gendered pronouns/anthropomorphism; technical users had modest expectations, blamed the technology, persisted.
- Users expected context carry-over between turns; defaulting to web search was "universally seen as a failure."
- Primary use case was hands-free during attention-demanding activities (driving, cycling, childcare); failures requiring manual intervention were rarely forgiven.
- Trust tied to precision and social cost: users avoided calls and messages; all sought visual confirmation for complex tasks; spoken confirmation sufficed for simple, repeatedly-successful tasks.
- Google Now users framed it as a tool (voice search) with more accurate expectations; Siri's personality raised expectations.

**Design rules derivable**
- Proactively reveal what the agent can and cannot do (examples, capability hints) outside of failure moments, not only after errors. [moderate]
- Never let humorous/personality responses imply general intelligence the system lacks; audit Easter eggs for the capability promise they make. [moderate]
- Provide visual (or explicit) confirmation before executing precise or socially costly actions (sending messages, calling); allow review/edit before commit. [strong — reported by all users]
- Carry conversational context across turns (follow-ups, sub-tasks) or clearly signal that context is not retained. [moderate]
- Never silently fall back to generic web-search results for an actionable request; state the failure and suggest a supported phrasing. [moderate]
- Design voice flows for divided attention: no forced switch to screen/manual input mid-task in hands-free contexts. [moderate]
- Communicate whether and how the system learns/adapts from the user. [moderate]
- Phrase failures so the system, not the user, takes responsibility; avoid designs that lead novices to self-blame. [weak]
- Ensure recognition performance is validated across voices/accents/genders before launch. [weak — small, unbalanced sample]
- Front-load reliable success on core tasks: early repeated failures (2–6) permanently fix low expectations. [moderate]

**Boundary conditions & caveats.** n=14, UK-centric, mostly male, mostly Siri; 2014–2015 systems; interaction themes rather than capability evaluation; self-report.


---

## 09__Mathur-2019_Dark-patterns-at-scale — Dark Patterns at Scale: Findings from a Crawl of 11K Shopping Websites (Arunesh Mathur, Gunes Acar, Michael J. Friedman, Eli Lucherini, Jonathan Mayer, Marshini Chetty, Arvind Narayanan, 2019, Proc. ACM HCI / CSCW 2019)
**Type:** empirical (large-scale measurement) + taxonomy  ·  **Sample/method:** Automated crawl of ~53K product pages (53,180) from ~11K (11,286) English shopping sites (from 361,102 Alexa sites → 46,569 shopping → 19,455 English), simulated add-to-cart/checkout via OpenWPM, page segmentation (~13M segments → ~1.3M unique), HDBSCAN clustering (10,277 clusters → 1,768 inspected), manual coding (Cohen's kappa 0.74); dynamic patterns monitored every 4 hours for 5 days.

**Core claim.** Dark patterns—UI choices that coerce, steer, or deceive users into decisions they might not make if fully informed—are measurable at web scale, common on popular shopping sites, often deceptive, and partly supplied by third-party vendors.

**Key findings**
- 1,818 instances on 1,254 sites (~11.1%); 15 types in 7 categories; a lower bound (text only; product/cart/checkout pages only).
- More popular sites more likely to have dark patterns (Spearman's rho = −0.62, p < 0.0001).
- Instances (sites) per type: Sneak into Basket 7 (7); Hidden Costs 5 (5); Hidden Subscription 14 (13); Countdown Timer 393 (361); Limited-time Message 88 (84); Confirmshaming 169 (164); Visual Interference 25 (24); Trick Questions 9 (9); Pressured Selling 67 (62); Activity Message 313 (264); Testimonials of uncertain origin 12 (12); Low-stock Message 632 (581); High-demand Message 47 (43); Hard to Cancel 31 (31); Forced Enrollment 6 (6).
- Category site counts: Sneaking 23; Urgency 437; Misdirection 244; Social Proof 275; Scarcity 609; Obstruction 31; Forced Action 6.
- Deception: 234 deceptive instances across 183 sites, including 157 deceptive countdown timers on 140 sites (reset or offer still valid after expiry), 29 deceptive activity notifications on 20 sites (random/hard-coded), 17 deceptive low-stock messages on 17 sites (16 decremented on schedule, 1 random; 8 used third-party JS such as Hurrify, Booster). 49 low-stock messages gave no quantity; 38 of 47 high-demand messages appeared regardless of product.
- Taxonomy of 5 attributes: Asymmetric, Covert, Deceptive, Hides Information, Restrictive; most patterns are covert, deceptive, and information-hiding; exploited biases: anchoring, bandwagon, default, framing, scarcity, sunk cost.
- 22 third parties providing dark patterns, embedded in 1,066 shopping sites and 7,769 Alexa top-million sites (Beeketing most prevalent: 406 shopping sites); two openly advertised deceptive capabilities ("Fake it till you make it"; plugin "will create fake orders").
- Deceptive practices are unlawful under FTC Act §5 and EU Unfair Commercial Practices Directive; Sneaking likely violates EU Consumer Rights Directive; consent via Trick Questions/Visual Interference is not valid GDPR consent.

**Design rules derivable**
- Never add items, insurance, or add-ons to a cart by default or via pre-checked boxes. [strong]
- Disclose all fees and the total price before checkout data entry; never reveal new charges at the final step. [strong]
- State recurring billing, renewal amount, and period explicitly at the point of purchase for any trial or "one-time" offer. [strong]
- Never display countdown timers that reset or offers that persist after expiry; every urgency claim must have a real, stated deadline. [strong]
- Only show stock/demand/activity messages generated from real, current data; never randomize or hard-code them. [strong]
- Never phrase a decline option to shame the user (e.g., "No thanks, I like paying full price"); use neutral, symmetric labels. [strong]
- Give opt-in and opt-out equal visual weight; never grey out a clickable decline option. [strong]
- Phrase consent checkboxes affirmatively and unambiguously; avoid double negatives and "check to opt out." [strong]
- Default product variants to the user's selection or the cheapest option, not the most expensive. [moderate]
- Allow cancellation through the same channel and with comparable effort as sign-up; disclose cancellation method upfront. [strong]
- Never bundle marketing consent with terms acceptance or require account creation just to browse. [strong]
- Attribute testimonials to verifiable sources. [moderate]
- Audit third-party conversion plugins for dark-pattern features before embedding. [moderate]

**Boundary conditions & caveats.** Text-only detection (misses style/color patterns); lower bound; only product/cart/checkout pages; no post-purchase flows; English sites; gray areas (e.g., free-shipping timers) contested; bias links may vary by individual; no user-impact measurement.


---

## 09__Mathur-2021_What-makes-a-dark-pattern-dark — What Makes a Dark Pattern… Dark? Design Attributes, Normative Considerations, and Measurement Methods (Arunesh Mathur, Jonathan Mayer, Mihir Kshirsagar, 2021, CHI 2021)
**Type:** review (scoping) + taxonomy + framework  ·  **Sample/method:** Scoping review of 20 academic papers plus legislation/regulatory materials (DETOUR Act, CPRA, CNIL report, NCC report); coded definitions, taxonomies, normative concerns, and user studies; synthesis with behavioral economics, philosophy, and law.

**Core claim.** "Dark pattern" is not one concept but a family of related concerns about modifying users' choice architecture; research should move from subjective labels to measurements grounded in explicit normative lenses (individual welfare, collective welfare, regulatory objectives, autonomy).

**Key findings**
- 19 definitions with four facets: UI characteristics (e.g., coercive, deceptive, misleading, steering), mechanism of effect (13 distinct mechanisms, e.g., subvert intent/preferences, undermine autonomy), designer role (intent, abuse of knowledge), benefits/harms. Nine definitions lack a UI characteristic, four lack a mechanism, eight lack designer role, ten lack benefit/harm elements.
- Definitions conflict with their own examples (e.g., "tricks"/"misleading" vs. fully transparent Confirmshaming, Forced Registration, Nagging).
- Six attributes in two themes: Modifying the decision space — Asymmetric, Restrictive, Disparate Treatment (new: disadvantages one user group, e.g., Pay to Skip), Covert; Manipulating the information flow — Deceptive, Information Hiding.
- Cited prevalence: Utz et al. >50% of 1,000 EU cookie banners had ≥1 dark pattern; Di Geronimo et al. >95% of 200 popular Android apps; Nouwens et al. only 11.8% of sites free of dark patterns; Soe et al. 297 of 300 consent notices; Mathur et al. 2019: >40% of timers reset or were inconsequential.
- Four normative lenses: Individual welfare (financial loss, privacy invasion, cognitive burden); Collective welfare (competition, price transparency, trust in market, unanticipated societal consequences); Regulatory objectives (FTC "reasonable consumer"/unfairness, GDPR consent "freely given, specific, informed and unambiguous," CPRA, DETOUR); Individual autonomy (right to act on one's own reasons; includes addiction-inducing infinite scroll, autoplay, lootboxes).
- Methods: compare against a baseline (regulation-specified, minimal variant omitting the pattern, or competitor design); thresholds (e.g., Luguri & Strahilevitz: uptake more than doubled vs. alternative); consider affected sub-populations and third parties.
- Case study (Trick Questions): measure preference-match vs. clear baseline (welfare), trust change (collective), comprehension of options (regulatory), awareness that options exist (autonomy).

**Design rules derivable**
- Audit every choice screen against six attributes: equal burden for all options, no eliminated choices, no group-differential treatment, visible influence, no false beliefs, no delayed/hidden necessary info. [moderate]
- Test consent/choice UIs against a neutral baseline variant; if choices diverge from stated preferences or uptake roughly doubles, redesign. [moderate]
- Make the privacy-protective/decline option reachable in the same number of steps as accept (never hide "deny" behind multi-screen "Manage options"). [strong — regulatory]
- Never require phone calls or restricted hours to cancel an online sign-up. [strong]
- Avoid repeated prompts (nagging) until the user accepts; respect a "no." [moderate]
- Never use fear, guilt, or emotion-laden framing to drive users away from privacy-respecting choices. [moderate]
- Verify comprehension: users should be able to correctly state what each option does (comprehension test in usability studies). [moderate]
- Avoid engagement mechanics that override user intent (infinite scroll, autoplay, variable-reward lootboxes) especially for children/teens; offer explicit stopping points. [weak]
- Evaluate dark-pattern risk for vulnerable sub-populations and non-users (e.g., contact-spam "growth hacks"). [weak]
- Never price- or option-discriminate covertly between user groups. [weak]

**Boundary conditions & caveats.** Scoping review (not systematic); dataset compiled Dec 2020; lenses acknowledged as unequally appealing; welfare baseline hard to define; autonomy lens sweeps broadly; thresholds require normative justification; case-study methods described as "relatively unsophisticated and naive."


---

## 09__Subramonyam-2024_Gulf-of-envisioning-LLM-prompting — Bridging the Gulf of Envisioning: Cognitive Challenges in Prompt Based Interactions with LLMs (Hari Subramonyam, Roy Pea, Christopher Lawrence Pondoc, Maneesh Agrawala, Colleen Seifert, 2024, CHI 2024)
**Type:** framework (theoretical) + design-pattern analysis  ·  **Sample/method:** Theory synthesis from cognitive science/HCI (Norman's seven stages, problem solving, Hayes & Flower writing model); analytic walkthrough of ChatGPT, Spellburst, Cursor; qualitative feature analysis of 12 systems clustered into design patterns.

**Core claim.** LLMs shrink the gulf of execution but open a "gulf of envisioning": users must form intentions and foresee outputs without adequate mental models, comprising a capability gap, an instruction gap, and an intentionality gap; interfaces should scaffold intention formation.

**Key findings**
- Three dimensions distinguish LLM interfaces: Functional Flexibility (dynamic vs. pre-set functions), Intent Specificity ("anything goes" input), Output Determinacy (probabilistic outputs).
- Norman's model treats "forming the intention" as given; with LLMs "intentions are the actions."
- Capability gap: users cannot formulate "how-to" procedures for the LLM; generative tasks are indeterminate, forcing trial-and-error.
- Instruction gap: slight wording changes cause significantly different outputs; users cannot anticipate interpretations, needing multi-turn interaction.
- Intentionality gap: when users state only a goal (Path 1), they skip planning and must evaluate output without internal benchmarks, risking over-reliance; distinct from Norman's gulf of evaluation (cognitive, not feedback-level).
- Iteration risks fixation/anchoring on first output and local minima; "20-questions" iteration is inefficient; batching intentions vs. iterating is a trade-off.
- Three pathways: (1) direct goal statement, (2) envisioning detailed intentions in the prompt, (3) leaving the chat for a dedicated tool or using a "prompt prompter" scaffold.
- ChatGPT: example prompts too coarse for planning; no regeneration history to compare outputs; custom instructions require foreseeing intentions upfront. Spellburst: example sketches, autocomplete from crowdsourced taxonomy, semantic operators, diff/extract. Cursor: example files, contextual tooltips, context references, codebase Q&A, but no regeneration history.
- Six design patterns with tenets: (1) visually track prompts and outputs (node-based) [T1]; (2) suggest ideas for prompting [T2 LLMs as cognitive partners; T3 clear, precise language]; (3) provide multiple outputs [T4 support divergent thinking]; (4) make output explainable [T5 errors are breakdowns of a distributed cognitive system needing collaborative repair]; (5) domain-specific prompting strategies [T6 task-specific mental models]; (6) manual control of output [T7 for well-defined tasks people prefer dedicated interfaces].
- Recommends semi-structured (templated) intent specification as a "sweet spot."

**Design rules derivable**
- Scaffold prompt construction with task-aware templates/questions that request missing elements (e.g., "who is your audience?"). [moderate]
- Offer concrete, task-granular example prompts and autocomplete from a shared vocabulary instead of only generic capability examples. [moderate]
- Preserve and display prompt/output history (including regenerations) side by side so users can map input changes to output changes. [moderate]
- Generate multiple alternative outputs per prompt and support grouping/comparison to counter fixation on the first result. [moderate]
- Let users branch, fork, and merge lines of exploration (node/tree views). [weak]
- Provide explanations of outputs (inline comments, diffs, multi-level summaries), but design against over-reliance by prompting validation. [moderate]
- Allow direct manual editing of outputs and intermediate artifacts (e.g., generated queries/goals). [moderate]
- For well-defined tasks, embed LLM features into dedicated task interfaces rather than a blank chat box. [moderate]
- Never ship a blank free-text box as the only affordance for complex generative tasks. [weak]
- Support repair: let users edit earlier prompts and see effects (transactional communication model). [weak]

**Boundary conditions & caveats.** Theoretical; no user study; analysis centered on writing; design patterns from 12 systems, not comprehensive; individual differences in intention formation; deep envisioning may be rare in practice; LLM capabilities evolving.


---

## 09__Yang-2020_Why-human-AI-interaction-is-hard-to-design — Re-examining Whether, Why, and How Human-AI Interaction Is Uniquely Difficult to Design (Qian Yang, Aaron Steinfeld, Carolyn Rosé, John Zimmerman, 2020, CHI 2020)
**Type:** framework (synthesis of literature, research-through-design, practitioner studies, teaching)  ·  **Sample/method:** Re-analysis of authors' projects: interviews with 14 product designers/managers + survey of 98, interviews with 10 AI engineers, interviews with 13 experienced UX practitioners; one-day workshops with 26 HCI master's students; a ~40-student studio course; >50 candidate frameworks critiqued by authors plus external experts and two research groups (~40 HCI, 12 ML researchers).

**Core claim.** Human-AI interaction is distinctively hard to design because of two properties—capability uncertainty and output complexity—not merely technical complexity or unpredictability; together they define four levels of AI systems, with Level 1 designable using standard HCI methods.

**Key findings**
- Literature-reported challenges across the double diamond: understanding AI capabilities; envisioning many novel, implementable AI ideas; iterative prototyping/testing (Wizard of Oz cannot simulate inference errors; field deployment loses rapid iteration); crafting interactions (setting expectations for unpredictable outputs; ethics); collaborating with AI engineers.
- No empirical evaluations were found of proposed AI design tools/guidelines/workflows.
- Capability uncertainty: what the system can do, how well, and its errors is most uncertain at ideation; performance can fluctuate post-deployment, improve for data-rich users and worsen for infrequent users/atypical contexts; situated, user-encountered errors are hard to anticipate.
- Output complexity: small fixed output sets (e.g., face/not face) can be designed via the four confusion-matrix cases; open-ended adaptive outputs that cannot be simulated (e.g., Siri) resist prototyping. "Output complexity is not output unpredictability" — a random-word bot is unpredictable but easily simulated.
- Four levels: Level 1 = probabilistic systems with known capability and few outputs, learning from a self-contained dataset (toxicity classifier, face detection, adaptive menus) — no particular new design challenges; Level 4 = evolving, adaptive systems learning after deployment with open-ended outputs (search, newsfeeds, auto-replies, recommenders, photo face-tagging) — full range of challenges; Level 4 challenges are a superset of Levels 2–3.
- Rule-based simulators are most effective for Levels 1–2 (especially Level 2's broad outputs) but cannot prototype systems learning from user data (Levels 3–4), which are "living, sociotechnical systems."
- AI fairness work focuses mostly on a fair system pre-deployment; situated UX of fairness is under-addressed.

**Design rules derivable**
- Classify an AI feature by capability uncertainty × output complexity before choosing prototyping methods. [moderate]
- For Level-1 features (fixed outputs, static model), design explicitly for all four outcomes: true positive, true negative, false positive, false negative. [strong]
- Prefer Level-1 AI features as low-risk entry points when teams lack AI design experience. [moderate]
- Use Wizard-of-Oz/rule-based simulation only for Levels 1–2; never treat it as evidence of how inference errors will be experienced. [moderate]
- For systems learning after deployment, plan for performance drift, monitor error modes over time, and design for degraded performance for infrequent users and atypical contexts. [moderate]
- Set user expectations appropriately for AI outputs that may be wrong; design graceful error recovery for each anticipated error type. [moderate]
- Prototype with real data/functioning models early to expose the gap between what data promise and what systems achieve. [weak]
- Involve AI engineers throughout design (not a final wireframe handoff) for evolving systems. [moderate]
- Evaluate fairness/bias as a situated user experience post-deployment, not only as an algorithmic property. [weak]

**Boundary conditions & caveats.** Cases drawn mostly from authors' own work — neither representative nor comprehensive; described as "a moderate first step"; framework not empirically validated; Level 2–3 definitions shown in a figure only.


---

## 09__Zamfirescu-Pereira-2023_Why-Johnny-cant-prompt — Why Johnny Can't Prompt: How Non-AI Experts Try (and Fail) to Design LLM Prompts (J.D. Zamfirescu-Pereira, Richmond Wong, Bjoern Hartmann, Qian Yang, 2023, CHI 2023)
**Type:** empirical (design probe, think-aloud)  ·  **Sample/method:** 10 participants with little/no prompt-design experience (varying programming backgrounds) used BotDesigner (no-code GPT-3 text-davinci-002 chatbot designer with preamble/first-turns/reminder fields, retry, labeling, and Error Browser for systematic testing) for up to 1 hour to improve a recipe-instruction bot toward "CarlaBot" behaviors; affinity diagramming and service blueprint analysis.

**Core claim.** Non-AI experts can prompt opportunistically but not systematically; their failures stem from over-generalizing from single observations and from human-to-human instruction expectations, echoing end-user programming and interactive ML barriers.

**Key findings**
- All participants could iterate ad hoc with local testing; 2 of 10 needed assistance to begin.
- Typical flow: chat until first error → edit preamble instructions (role descriptions, general directives, specific "don't say X") → retry until one success → declare victory and move on.
- None elicited more than one or two conversations or followed a conversation to task completion before fixing; zero used the systematic testing interface; labeling was rare and abandoned (some expected the bot to read labels).
- Over-generalization: stopped after a single success; or concluded incapability after one failure ("ok, I guess it doesn't like to tell jokes"); rarely rephrased.
- Social lens: all held a strong bias for direct instruction over examples; P5 was the only one to add example dialog unprompted; copying transcript dialog was effective (also shifted voice in later turns) yet none used it substantially afterward; some called it "cheating."
- "Do not do X" was much more common but much less effective than "Do Y"; negative instruction could cause the bot to say the forbidden phrase; removing the "Don't" version resolved one error.
- Politeness persisted (e.g., always "please"); repetition felt unnatural (only one participant used it).
- Mixed commands to bot and to end user in one prompt; expected memory across conversations and that in-chat instructions persist; confusion about one's role (designer vs. Carla vs. producer).
- Expected semantically equivalent instructions to yield equivalent results; every participant asked "why did it do that?"—usually unanswerable.
- Barriers mapped to EUP: design, selection, coordination, use, understanding, information.

**Design rules derivable**
- In prompt-authoring tools, build in and promote regression testing: require/encourage multiple test conversations and re-running saved failing cases after each prompt change. [moderate]
- Provide heuristics on how many conversations/error examples are needed before trusting a fix. [weak]
- Surface a searchable, context-specific library of working prompt examples at the moment users get stuck. [moderate]
- Show diffs between prompt versions alongside resulting output diffs across conversations. [moderate]
- Recommend positive phrasing ("do Y") over negations ("do not X") in prompt guidance and linting. [moderate]
- Encourage example dialogues (few-shot) rather than only abstract instructions; make adding examples easy. [moderate]
- Clearly show instruction scope/lifetime (preamble vs. reminder vs. in-conversation) and that the bot does not remember prior conversations. [moderate]
- Separate fields for instructions-to-the-bot vs. content-for-the-end-user. [weak]
- Consider "seamful" design that exposes non-humanness (e.g., auto-repeating instructions under the hood, templates) to counter social-actor assumptions. [weak]
- Set capability expectations explicitly so users neither assume AGI nor give up after one failure; prompt users to rephrase before concluding incapability. [weak]

**Boundary conditions & caveats.** n=10, STEM-skewed early adopters; 1-hour sessions; text-davinci-002 (older model); chatbot domain may amplify social expectations; interviewer advice not uniform across participants; formative, not prevalence claims.


---

## Cross-paper patterns in this group
- **Expectation calibration is the central human-AI design problem.** Luger & Sellen (CAs), Zamfirescu-Pereira (prompting), Subramonyam (capability gap), and Yang (capability uncertainty) all find users cannot form accurate models of what AI can do; interfaces must reveal capability and limits proactively, not only at failure.
- **Anthropomorphism and social framing inflate expectations and distort behavior.** Humor/personality (Luger & Sellen) and human-instruction habits like politeness and "don't" phrasing (Zamfirescu-Pereira) lead users astray; consider seamful designs that expose non-humanness.
- **Over-generalization from few observations.** Users fix low expectations after 2–6 CA failures (Luger & Sellen) or declare success/incapability after one prompt attempt (Zamfirescu-Pereira); tools should encourage multiple samples, alternatives (Subramonyam's multiple outputs), and regression testing.
- **Output-to-input traceability is missing.** Users ask "why did it do that?" (Zamfirescu-Pereira), want Why/Why-not explanations (Liao), and need prompt/output history and diffs (Subramonyam); explanations should be interactive and contrastive.
- **Confirmation and reversibility for high-stakes or precise actions.** Visual confirmation before sending/calling (Luger & Sellen) parallels honest, non-sneaky commitment points in commerce (Mathur 2019).
- **Performance metrics must be translated into actionable limits.** Raw accuracy/confidence is low-value (Liao); designers should frame "good enough for what" and error types, consistent with Yang's four-outcome design for Level-1 systems.
- **Scaffold intent rather than offering a blank box.** Templates, task-specific examples, and dedicated interfaces (Subramonyam), example libraries (Zamfirescu-Pereira), and capability examples (Luger & Sellen) converge.
- **Dark patterns are defined by choice-architecture manipulation.** Mathur 2019 measures prevalence (≥11.1% of shopping sites, 183 with deceptive messages); Mathur 2021 organizes them into decision-space vs. information-flow attributes and four normative lenses—usable as an audit checklist for any UI, including AI agents that could nudge users.
- **Measure against a neutral baseline.** Mathur 2021's baseline/threshold method and Zamfirescu-Pereira's regression-testing argument both call for comparative evaluation rather than single-instance judgment.
- **Evidence strength is mostly qualitative or theoretical.** Only Mathur 2019 is large-scale quantitative; Liao, Luger & Sellen, and Zamfirescu-Pereira are small qualitative studies (n=10–20); Yang and Subramonyam are frameworks—treat their rules as moderate/weak unless corroborated.
