# Group F — Ethics, credibility, human-AI interaction (batch 1)

Evidence-strength key used in rules: [strong] = large-sample quantitative evidence or validated across many products/sources; [moderate] = systematic review / taxonomy / self-report or single large study; [weak] = principle, argument, or single-prototype illustration.

---

## 09__Amershi-2019_Guidelines-for-human-AI-interaction — Guidelines for Human-AI Interaction (Amershi, Weld, Vorvoreanu, Fourney, Nushi, Collisson, Suh, Iqbal, Bennett, Inkpen, Teevan, Kikin-Gil, Horvitz; 2019; CHI 2019)
**Type:** guideline (with validation study)  ·  **Sample/method:** 168 candidate recommendations → 35 concepts → 20 → 18 guidelines; internal modified heuristic evaluation (11 team members, 13 products); user study with 49 HCI practitioners testing 20 AI-infused products in 10 categories; expert review (11 experts).

**Core claim.** Twenty years of scattered AI-UX advice can be consolidated into 18 generally applicable, inspection-testable guidelines for AI-infused systems; practitioners can find applications and violations of every guideline across a broad range of real products.

**The 18 guidelines (final wording), grouped by phase:**
- *Initially*
  - G1 Make clear what the system can do. — Help the user understand what the AI system is capable of doing.
  - G2 Make clear how well the system can do what it can do. — Help the user understand how often the AI system may make mistakes.
- *During interaction*
  - G3 Time services based on context. — Time when to act or interrupt based on the user's current task and environment.
  - G4 Show contextually relevant information. — Display information relevant to the user's current task and environment.
  - G5 Match relevant social norms. — Ensure the experience is delivered in a way that users would expect, given their social and cultural context.
  - G6 Mitigate social biases. — Ensure the AI system's language and behaviors do not reinforce undesirable and unfair stereotypes and biases.
- *When wrong*
  - G7 Support efficient invocation. — Make it easy to invoke or request the AI system's services when needed.
  - G8 Support efficient dismissal. — Make it easy to dismiss or ignore undesired AI system services.
  - G9 Support efficient correction. — Make it easy to edit, refine, or recover when the AI system is wrong.
  - G10 Scope services when in doubt. — Engage in disambiguation or gracefully degrade the AI system's services when uncertain about a user's goals.
  - G11 Make clear why the system did what it did. — Enable the user to access an explanation of why the AI system behaved as it did.
- *Over time*
  - G12 Remember recent interactions. — Maintain short term memory and allow the user to make efficient references to that memory.
  - G13 Learn from user behavior. — Personalize the user's experience by learning from their actions over time.
  - G14 Update and adapt cautiously. — Limit disruptive changes when updating and adapting the AI system's behaviors.
  - G15 Encourage granular feedback. — Enable the user to provide feedback indicating their preferences during regular interaction with the AI system.
  - G16 Convey the consequences of user actions. — Immediately update or convey how user actions will impact future behaviors of the AI system.
  - G17 Provide global controls. — Allow the user to globally customize what the AI system monitors and how it behaves.
  - G18 Notify users about changes. — Inform the user when the AI system adds or updates its capabilities.

**Key findings**
- 785 examples of the 18 guidelines identified across 20 products (after adjustments): 313 applications, 277 violations, 89 neutrals, 106 "does not apply."
- Data cleaning removed 55 duplicates, 73 misuse-of-"does not apply" instances, 14 reviewer-disagreement instances; 20 "does not apply" were reclassified as violations; 56 instances were misinterpretations of one guideline for another.
- At least one application or violation of every guideline was found in every product category tested.
- Widely implemented (applications ≥40% more than violations): e.g., G1, G4, G12. Relevant but under-implemented (many more violations): G2, G11, G17. G11 had one of the highest violation counts and one of the fewest "does not apply" — users could imagine explanations but could not get them (e.g., "I have no idea why this is being shown to me").
- Highest "does not apply": G3, G5, G6. G3 judged irrelevant for "pull" (user-initiated) features; G5 and G6 rated least clear and hard to judge outside one's own social context.
- No G10 instances for the two social networks; no G14 instances for activity trackers (hard to observe in one session).
- Voice assistants had the most "does not apply"; photo organizers, activity trackers and voice assistants the fewest total applications/violations (non-GUI modalities).
- Confusable pairs fixed by rewording: G1/G2/G11 (13 misinterpretations: 5 between G1–G2, 8 between G1–G11); G4/G13 (6); G3/G4 (4); G12/G13 (7); G15/G17 (6). Experts (n=11) preferred revised wording for all revised guidelines except G15; 5 of 11 still found G1 vs G2 somewhat hard to distinguish.
- 8 of the 18 guidelines map to Horvitz's 1999 mixed-initiative principles.
- Dropped during consolidation: "explore vs. exploit in moderation," "be especially conservative in the beginning" (not observable in UI); "inform the user when to take control" and "fallback to a human" merged into G10; privacy permissions/private mode merged into G17.

**Design rules derivable**
- At first use, state what the AI feature can do (enumerate capabilities/metrics it tracks). [moderate]
- Communicate expected accuracy/error likelihood (e.g., hedging language "we think you'll like") rather than implying certainty. [moderate]
- Make every AI feature invocable on demand, dismissible in one step, and editable inline after it acts ("Tap to edit"). [moderate]
- When the model is uncertain, offer several candidates or disambiguate instead of auto-completing/acting (e.g., 3–4 suggestions). [moderate]
- Provide an accessible "why am I seeing this?" explanation for every recommendation/decision; never show a recommendation with no retrievable rationale. [moderate]
- Keep short-term conversational/session context so users can refer back ("who is he married to"). [moderate]
- When adapting, update only the part of the UI affected and keep previously seen content stable. [moderate]
- Offer instance-level feedback controls (mark important/not) separately from global settings; label global controls as such. [moderate]
- Show users immediately how a feedback action will change future behavior (e.g., "hiding this ad adjusts future ads"). [moderate]
- Provide global controls over what is monitored (location history, data use, private mode). [moderate]
- Announce new/changed AI capabilities (in-app callouts; pop-ups for changes requiring attention). [weak]
- Default personas/voices and language must not encode stereotypes; offer alternatives and audit with diverse evaluators. [weak]
- Use these 18 guidelines as a heuristic-evaluation checklist, with 2–3 evaluators per product. [moderate]

**Boundary conditions & caveats.** Validates relevance and clarity, not user outcomes/effectiveness. Evaluators recruited mostly from one large company (11 external). Some guidelines need long-term use or model knowledge to observe (G10, G14). Less applicable to non-GUI AI (voice, sensors); high-risk domains (autonomous vehicles, surgery, finance) may need specialized guidance. Guidelines can conflict (e.g., G16 vs. G13 with complex models). Ethics coverage is limited to G5/G6.


---

## 09__Caraban-2019_23-ways-to-nudge — 23 Ways to Nudge: A Review of Technology-Mediated Nudging in Human-Computer Interaction (Caraban, Karapanos, Gonçalves, Campos; 2019; CHI 2019)
**Type:** review / taxonomy  ·  **Sample/method:** PRISMA systematic review of 71 papers (2008–2017) from top HCI venues + Persuasive; 74 nudge examples; inter-rater Cohen's K = 0.77.

**Core claim.** Technology-mediated nudges in HCI use 23 distinct mechanisms in 6 categories, exploiting 15 cognitive biases; effectiveness depends on implementation and context rather than mechanism, and nudges need not be non-transparent or bypass reflection.

**The 23 mechanisms in 6 categories**
- **Facilitate** (reduce effort; status-quo bias): (1) Default options, (2) Opt-out policies, (3) Positioning, (4) Hiding, (5) Suggesting alternatives.
- **Confront** (pause unwanted action by instilling doubt; regret aversion etc.): (6) Throttling mindless activity, (7) Reminding of the consequences, (8) Creating friction, (9) Providing multiple viewpoints.
- **Deceive**: (10) Adding inferior alternatives (decoy), (11) Biasing the memory of past experiences (peak-end), (12) Placebos, (13) Deceptive visualizations.
- **Social influence**: (14) Invoking feelings of reciprocity, (15) Leveraging public commitment, (16) Raising the visibility of users' actions, (17) Enabling social comparisons.
- **Fear**: (18) Make resources scarce, (19) Reducing the distance.
- **Reinforce**: (20) Just-in-time prompts, (21) Ambient feedback, (22) Instigating empathy, (23) Subliminal priming.

**Transparency × automaticity framing (Hansen & Jespersen):** quadrants = influence behavior (automatic-transparent), prompt reflective choice (reflective-transparent), manipulate choice (reflective-non-transparent), manipulate behavior (automatic-non-transparent). Also mapped to Fogg Behavior Model triggers: facilitators (raise ability), sparks (raise motivation), signals (remind).

**Key findings**
- Of 74 examples: 39 (52%) prompt reflective choice; 19 (26%) influence behavior (automatic but transparent); 16 (22%) manipulate behavior (automatic, non-transparent).
- 49 (66%) of the 74 empirically studied nudges had a significant effect; no overt relation between mechanism and effectiveness.
- Most-used biases: availability heuristic 24%, herd instinct 16%, status quo 13%, regret aversion 11%.
- Domains: health 31%, sustainability 20%, human performance 18%, privacy/security 9%. Platforms: web 38%, physical prototypes 20%, mobile 14%.
- Of 55 papers with user studies, median sample 64 (min 1, max 1610); only 18 (36%) of 50 lasted >1 day, 7 (14%) >1 month; only 7 (14%) checked persistence after nudge removal (Discussion reports 18 (35%) of 52 >1 day, 10 (19%) >1 month).
- Example effects: double-sided default → 15% less paper; color + positioning of secure Wi-Fi → significant increase for 60% of participants, positioning alone ineffective; hiding unhealthy snacks on last pages → 53% chose healthy; food swaps accepted median 4 of 12, more at selection than checkout; query-box halo → average query length 6 words; "98% of other participants fully answered this question" increased disclosure; TickTock (last hour only) → checks every ~9 min and more activity; opt-out vaccination appointments cancelled by 61%.
- Organ donation (background): >90% in opt-out vs ~15% in opt-in contexts.
- Failure reasons: lack of educational effect, effects not sustained, backfiring/unexpected effects (e.g., below-average energy users consume more; public commitments → fewer commitments), intrusiveness/reactance, poor timing/strength, strong preferences/habits.
- 94% of persuasive systems (Adams et al.) target the reflective mind; 95% of daily decisions are estimated to be automatic (cited background).

**Design rules derivable**
- Set the pro-user option as the default when users are indifferent; make the default visible and opt-out easy. [moderate]
- Order and color-code options so the recommended safe choice is first and labeled (positioning alone may not suffice; combine with cues). [moderate]
- Offer a better alternative at the moment of selection, not at checkout. [moderate]
- For impulsive, regrettable actions (posting, sharing), add a short reversible delay or a personalized consequence reminder (e.g., show who will see it). [moderate]
- Use social comparisons only against peers of similar performance; never compare to a norm that licenses worse behavior. [moderate]
- Tune signal timing and frequency: personalized, well-timed prompts beat generic periodic reminders; high frequency risks saturation/reactance. [moderate]
- Prefer transparent nudges (user can see intent and means); treat non-transparent automatic nudges (deceptive visualizations, subliminal priming, hidden opt-outs) as ethically high-risk. [moderate]
- Never use friction that the user cannot bypass; design friction to avoid reactance. [weak]
- Tailor nudges to users without strong prior preferences; expect little effect on entrenched habits. [moderate]
- Evaluate nudges long-term and after removal; test for backfire. [moderate]

**Boundary conditions & caveats.** Mostly short lab studies; effects context-dependent; review only covers research prototypes (commercial systems excluded); categorization is the authors'. Several "deceive"/"fear" mechanisms overlap with dark patterns if used against user interests.


---

## 09__DiGeronimo-2020_UI-dark-patterns-mobile — UI Dark Patterns and Where to Find Them: A Study on Mobile Applications and User Perception (Di Geronimo, Braz, Fregnan, Palomba, Bacchelli; 2020; CHI 2020)
**Type:** empirical (content analysis + online experiment)  ·  **Sample/method:** 240 trending free Android apps (30 × 8 categories), 10 min recorded walkthrough each (40 h), coded with Gray et al. 2018 taxonomy; online survey with 589 participants watching 30-s app videos.

**Core claim.** Dark patterns are nearly ubiquitous in popular mobile apps, and most users fail to recognize them ("DP-blindness"), though awareness/priming improves detection.

**Key findings**
- 95% of 240 apps contained ≥1 dark pattern; 1,787 instances total; mean 7.4 per app (SD 5). ~10% had 0–2 (N=33), 37% had 3–6 (N=89), 49% had ≥7 (N=118). 12 apps (5%) had none.
- Average 2.7 of the 5 macro-classes per app (SD 1.1); 4.3 of 16 subcategories (SD 2.6); 63% (N=152) had ≥4 subcategories.
- Most frequent subcategories: Nagging (N=352), False Hierarchy (N=299), Preselection (N=210).
- 55% of apps interrupted users (permissions, rating, ads); False Hierarchy in 61%; Preselection in 60% (notification preselection most frequent, N=121; 81 apps preselected >2 notification types); Privacy Zuckering 31%; Roach Motel (no logout / no account deletion) 41%; Price Comparison Prevention 23 times overall, in 77% of shopping apps.
- Worst apps: one with 23 DPs in 10 subcategories; another with 20 in 8. News & Magazines had significantly fewer DPs than five other categories (Welch ANOVA F[7,232]=3.390, p<0.05).
- Perception: across 1,178 DP-app answers, 55% did not spot malicious design, 20% unsure, 25% did; 86% correctly judged the control app clean. Only 7% of 366 open comments spontaneously mentioned a DP. Of those who spotted something, 24% matched the actual DP.
- Sneak into Basket + Preselection app had lowest detection (14%), significantly worse than others.
- Detection improved after the first app (order effect χ²(4)=58.201, p<0.001) and with prior knowledge (χ²(6)=81.699, p<0.001); no differences by age, employment, education.
- Background (Luguri & Strahilevitz): acceptance 11% (no DP) vs 26% (mild DP) vs 42% (aggressive DP).

**Design rules derivable**
- Never preselect notification, data-sharing or add-on (insurance) options; require explicit opt-in. [strong]
- Give accept/decline options equal visual weight; never style the app-favoring option as dominant. [strong]
- Do not interrupt the primary task with rating/permission/ad pop-ups; if needed, include a permanent dismiss. [moderate]
- Always provide in-app logout and account deletion (or a direct link to it). [moderate]
- Never disguise ads as content, buttons, or features; never make a free-looking feature open a paywall/upsell. [moderate]
- Do not make terms/privacy acceptance small or greyed out; disclose consent clearly. [moderate]
- Allow copying product names/prices. [moderate]
- Do not assume user complaints will surface DPs—users are largely blind to them; audit designs proactively. [moderate]
- Do not copy patterns from popular apps without an ethics check (mimicry spreads DPs). [weak]

**Boundary conditions & caveats.** Android, free, US-trending apps only; first 10 minutes only; no purchases/subscriptions (Forced Continuity, Gamification not coded); classification by UI outcome not intent; video viewing ≠ active use; Sneak into Basket confounded with Preselection; highly educated sample.


---

## 09__Fogg-2001_What-makes-web-sites-credible — What Makes Web Sites Credible? A Report on a Large Quantitative Study (Fogg, Marshall, Laraki, Osipovich, Varma, Fang, Paul, Rangnekar, Shon, Swani, Treinen; 2001; CHI 2001)
**Type:** empirical (self-report survey + factor analysis)  ·  **Sample/method:** 1,410 valid participants (U.S. 42%, Finland 58%), 51 site elements rated −3 ("much less believable") to +3 ("much more believable"), randomized order; 7 scales from factor analysis.

**Core claim.** Perceived web credibility (trustworthiness + expertise) is raised by real-world feel, ease of use, expertise, trustworthiness and tailoring, and lowered by commercial implications and amateurism.

**Key findings (item means, −3..+3)**
- *Real-World Feel* (α=0.66; largest positive): quick customer-service response 2.02; physical address 1.86; contact phone 1.71; contact email 1.53; photos of members 0.69.
- *Ease of Use* (α=0.67; second): search past content 1.57; looks professionally designed 1.55; arranged in a way that makes sense 1.48; long download −0.94; difficult to navigate −1.30.
- *Expertise* (α=0.63): respected news org 1.91; author credentials 1.49; citations/references 1.49; few stories but detailed 1.10; official site 0.85; ratings/reviews 0.79; award 0.45.
- *Trustworthiness* (α=0.57): linked from believable site 1.29; states content policy 1.26; links to outside sources 1.25; links to competitors 1.11; recommended by friend 1.07; nonprofit 0.93; corporate customers 0.62; .org 0.58.
- *Tailoring* (α=0.44; smallest positive): confirmation emails 1.41; preference-based news 0.57; recognizes return visit 0.37; requires login 0.07 (≈no effect).
- *Commercial Implications* (α=0.65; negative): radio/billboard ads 0.57; topic-matched ads 0.21; e-commerce 0.17; commercial purpose −0.63; paid subscription −0.71; ads on every page −0.77; pop-up ads −1.56; **hard to distinguish ads from content −2.08 (lowest of all 51)**.
- *Amateurism* (α=0.64; most negative): updated since last visit 1.55; multilingual 1.04; small site −0.28; third-party hosted −0.44; domain ≠ company name −1.06; typo −1.28; sometimes unavailable −1.28; broken link −1.45; links to non-credible site −1.53; rarely updated −1.67.
- Unscaled: organization you respect 1.93; info contradicting beliefs −0.77; many stories without detail −0.89.
- Demographic differences significant (p<0.00016) but small: younger harsher on amateurism; men lower overall (0.31 vs 0.42); Finns harsher on commercial/amateurism; Web experience made no difference on any scale.

**Design rules derivable**
- Show the real organization: physical address, phone, email, fast customer-service response. [strong]
- Never make ads hard to distinguish from content; avoid pop-up ads. [strong]
- Eliminate typos, broken links, and downtime; even one is damaging. [strong]
- Keep content visibly updated; stale content hurts credibility. [strong]
- Make navigation easy and structure sensible; provide search/archives. [strong]
- Show author credentials, citations and references for content. [moderate]
- Link out to sources (even competitors) and state a content policy. [moderate]
- Ensure domain name matches organization name. [moderate]
- Don't rely on tailoring/login for credibility; requiring login neither helps nor hurts. [moderate]
- Avoid an aggressively commercial feel; topic-matched ads are tolerated. [moderate]

**Boundary conditions & caveats.** Self-reported hypothetical ratings based on cumulative experience, not observed behavior on real sites; modest Cronbach's alphas (0.44–0.67); four factors explained only 15.1% of variance; 2 countries; data from Dec 1999.


---

## 09__Fogg-2003_How-users-evaluate-credibility — How Do Users Evaluate the Credibility of Web Sites? A Study with Over 2,500 Participants (Fogg, Soohoo, Danielson, Marable, Stanford, Tauber; 2003; ACM proceedings — venue name not stated in text)
**Type:** empirical (content analysis of open comments)  ·  **Sample/method:** 2,684 participants each compared 2 live sites from 100 sites across 10 categories; 2,440 comments coded by two independent coders + tie-breaker.

**Core claim.** When people actually evaluate live sites, the most *noticed* credibility cue is the site's visual "design look"; by Prominence-Interpretation Theory, credibility impact = Prominence × Interpretation.

**Key findings (% of comments mentioning)**
- Design Look 46.1%; Information Design/Structure 28.5%; Information Focus 25.1%; Company Motive 15.5%; Usefulness of Information 14.8%; Accuracy of Information 14.3%; Name Recognition & Reputation 14.1%; Advertising 13.8%; Bias of Information 11.6%; Tone of the Writing 9.0%; Identity of Site Sponsor 8.8%; Functionality of Site 8.6%; Customer Service 6.4%; Past Experience with Site 4.6%; Information Clarity 3.7%; Performance on a Test 3.6%; Readability 3.6%; Affiliations 3.4%.
- Category differences: e-commerce—name/reputation 25.9% (vs 14.1%), customer service 16.7% (vs 6.4%); news—bias 30.2% (vs 11.6%); nonprofit—structure 18.2% (vs 28.5%), identity 28.9% (vs 8.8%); opinion/review—bias 23.8%, accuracy 25.4%; travel—customer service 18.1%; web search—info design 42.6%, functionality 20.5%, advertising 24.6%, own tests 13.8% (vs 3.6%).
- Privacy policies were rarely noticed on any of the 100 sites.
- Pop-up ads widely disliked; slang/"marketing language" hurt credibility; sites with unclear motive (selling only) lost credibility.
- Participants: 58.1% female, mean age 39.9, 19.6 h/week web use.

**Design rules derivable**
- Invest in professional visual design (layout, typography, white space, color, imagery); it is the most-noticed credibility cue. [strong]
- Organize information clearly with multiple navigation layers; don't cram everything onto the home page. [moderate]
- Decide deliberately which elements are prominent; credibility cues that aren't noticed have no effect. [moderate]
- Do not count on privacy policies or seals to build credibility unless made prominent. [moderate]
- Avoid pop-up/pop-under ads and ad-dominated layouts. [moderate]
- Use understated, non-sensational, non-slang writing tone. [moderate]
- Clearly state who runs the site, its mission and contact details (especially for nonprofits). [moderate]
- Weight cues by domain: reputation/customer service for e-commerce, neutrality for news, search quality for search. [moderate]
- Run credibility checks with users as standard practice. [weak]

**Boundary conditions & caveats.** Low-involvement participants (charity-donation incentive) → reliance on peripheral cues (ELM); "design look" was the broadest coding category; percentages are approximate and depend on coding scheme, sites and sample; measures what is noticed, not how it is interpreted; non-representative sample.


---

## 09__Gray-2018_Dark-patterns-side-of-UX — The Dark (Patterns) Side of UX Design (Gray, Kou, Battles, Hoggatt, Toombs; 2018; CHI 2018)
**Type:** taxonomy (qualitative content analysis)  ·  **Sample/method:** corpus of 118 practitioner-shared artifacts (45 social media, 40 practitioner blogs, 19 news, 10 own interactions, 4 darkpatterns.org); a-priori coding with Brignull's 11 types, then open/axial coding.

**Core claim.** Practitioner "dark patterns" can be reorganized around five designer strategies—nagging, obstruction, sneaking, interface interference, forced action—in which user value is supplanted by shareholder value.

**Key findings — the 5 strategies and subtypes**
- **Nagging**: "redirection of expected functionality that persists beyond one or more interactions" (e.g., notification modal with only "Not Now"/"OK"; location prompt with tiny "Don't show again"; driver app pushing arbitrary income goal).
- **Obstruction**: "making a process more difficult than it needs to be, with the intent of dissuading certain action(s)." Subtypes: Roach Motel (easy in, hard out—e.g., cancel only by phone during business hours), Price Comparison Prevention (uncopyable product info), Intermediate Currency (virtual currency obscures real cost).
- **Sneaking**: "attempting to hide, disguise, or delay the divulging of information that is relevant to the user." Subtypes: Forced Continuity, Hidden Costs (99¢ banner → 4-week trial), Sneak into Basket, Bait and Switch (red "X" not closing; buy-moves button where new-game button usually is).
- **Interface Interference**: "manipulation of the user interface that privileges certain actions over others." Subtypes: Hidden Information (opt-out hidden in fine print), Preselection, Aesthetic Manipulation → Toying with Emotion (resetting countdown; confirmshaming "No thanks, I'll have a microwave dinner tonight"), False Hierarchy (grey "custom" option appearing disabled), Disguised Ad, Trick Questions (opt-out checkboxes, double negatives).
- **Forced Action**: "requiring the user to perform a certain action to access (or continue to access) certain functionality." Subtypes: Social Pyramid (incl. Friend Spam), Privacy Zuckering, Gamification (grinding; impossible levels to push purchases).
- Dark patterns undermine both gulf of execution (action possibilities) and gulf of evaluation (expected outcomes); some test well in usability metrics (forced action, nagging) at the expense of user choice.
- Many dark patterns resemble Fogg's persuasive strategies (tunneling/reduction ↔ forced action/obstruction; tailoring/suggestion ↔ interface interference; conditioning ↔ sneaking/nagging).

**Design rules derivable**
- Every recurring prompt must offer a permanent "don't ask again" with equal prominence. [moderate]
- Make cancellation/account deletion as easy and in the same channel as sign-up. [moderate]
- Disclose full price (taxes, fees, trial terms) at first price display. [moderate]
- Never add items to a cart or enable paid continuation without explicit action; warn before trial converts to paid. [moderate]
- Keep close/X controls and frequent-button positions behaving consistently; never place a purchase action where a habitual action sits. [moderate]
- Never preselect choices against user interest; avoid double negatives and opt-out checkboxes. [moderate]
- Style parallel options in parallel; never grey out an active option. [moderate]
- No confirmshaming copy or fake/resetting countdown timers. [moderate]
- Never condition core functionality (e.g., unsubscribe, shutdown) on unrelated consent or data sharing. [moderate]
- Evaluate designs with user-value criteria, not only conversion metrics, since some dark patterns test well. [weak]

**Boundary conditions & caveats.** Corpus limited to practitioner-shared examples; no prevalence or effect data; intent is hard to infer (dark pattern vs. anti-pattern / Hanlon's Razor); authors explicitly do not propose the strategies as an ethical checklist.


---

## 09__Gray-2024_Ontology-of-dark-patterns — An Ontology of Dark Patterns Knowledge: Foundations, Definitions, and a Pathway for Shared Knowledge-Building (Gray, Santos, Bielova, Mildner; 2024; CHI 2024)
**Type:** taxonomy / ontology  ·  **Sample/method:** qualitative content analysis harmonizing 10 academic/regulatory taxonomies (Brignull, Gray 2018, Mathur, Luguri & Strahilevitz, Bösch; EU Commission, EDPB, CMA, FTC, OECD) + Brignull 2023 update; 262 source patterns (203 low, 59 high) → 65 final types; member-checked with a dark-patterns Slack community (>100 members).

**Core claim.** A three-level ontology (high = strategy, meso = angle of attack, low = concrete UI execution) with standardized definition syntax harmonizes academic and regulatory dark-pattern vocabularies.

**Key findings — the ontology (5 high / 25 meso / 35 low)**
- **Obstruction** — meso: Roach Motel (low: Immortal Accounts, Dead End); Creating Barriers (Price Comparison Prevention, Intermediate Currency); Adding Steps (Privacy Maze).
- **Sneaking** — meso: Bait and Switch (Disguised Ad); Hiding Information (Sneak into Basket; Drip Pricing/Hidden Costs/Partitioned Pricing; Reference Pricing); (De)contextualizing Cues (Conflicting Information; Information without Context).
- **Interface Interference** — meso: Manipulating Choice Architecture (False Hierarchy, Visual Prominence, Bundling, Pressured Selling); Bad Defaults; Emotional or Sensory Manipulation (Cuteness, Positive or Negative Framing); Trick Questions; Choice Overload; Hidden Information; Language Inaccessibility (Wrong Language, Complex Language); Feedforward Ambiguity.
- **Forced Action** — meso: Nagging; Forced Continuity; Forced Registration; Forced Communication or Disclosure (Privacy Zuckering, Friend Spam, Address Book Leeching, Social Pyramid); Gamification (Pay-to-Play, Grinding); Attention Capture (Auto-Play).
- **Social Engineering** — meso: Scarcity and Popularity Claims (High Demand, Low Stock); Social Proof (Endorsements and Testimonials, Parasocial Pressure, Activity Messages); Urgency (Countdown Timer, Limited Time Message); Shaming (Confirmshaming); Personalization.
- Definition syntax: High = "{pattern} is a strategy which {undesired action} that ... {distort/subvert/impede} users' autonomy"; Meso = "subverts the user's expectation that {X}, instead producing {effect}"; Low = "uses {high/meso} to {UI element altered}. As a result, {incorrect expectation} leads to {undesired effect}."
- Example meso definitions: Roach Motel "subverts the user's expectation that an action will be as easy to reverse as it is to make"; Bad Defaults "subverts the user's expectation that default settings will be in their best interest."
- Low-level patterns are the most detectable automatically; high-level require interpretation.
- Regulatory links: EU courts/DPAs have forbidden preselection (maps to Bad Defaults), refusing consent being harder than giving it, misinforming on data purposes; DSA prohibits repeated requests for an already-made choice (maps to Nagging); $245M FTC judgment against Fortnite.
- Extension examples: Linguistic Dead-End/Untranslation/Alphabet Soup (Japanese apps) → Language Inaccessibility; Extraneous Badges → Aesthetic Manipulation; account-deletion roadblocks → Roach Motel.

**Design rules derivable**
- Make reversal as easy as the original action (subscribe/cancel, consent/withdraw, create/delete account). [moderate — regulator-backed]
- Defaults must favor the user; never pre-select data sharing or upsells. [moderate — regulator-backed]
- Don't re-ask a choice already made (nagging); store and respect the decision. [moderate — regulator-backed]
- Show the full total price up front; no drip pricing or fake reference ("was") prices. [moderate]
- Never claim scarcity, demand, activity or urgency that isn't true; no resetting timers. [moderate]
- Present options in parallel with equal visual weight; don't place goal-relevant elements in competition with distracting prominent ones. [moderate]
- Keep task paths minimal—no extra steps for privacy-protective choices; avoid privacy mazes and dead-end links. [moderate]
- Provide key information in the user's language and plain wording. [moderate]
- Make the outcome of each control predictable (no feedforward ambiguity); avoid conflicting information. [moderate]
- Don't require registration or contact-list access unless essential; don't auto-play by default where it extends use beyond intent. [weak]
- Use the ontology's low-level patterns as an audit checklist for automated/manual detection. [weak]

**Boundary conditions & caveats.** Definitional/harmonization work, no new user data; validity is face validity from community feedback; some mappings disputable; counts inconsistent in text (abstract says 64 types, method/conclusion 65; "24" meso and "34" low definitions mentioned elsewhere vs 25/35 in the framework); sources limited to EU/UK/US regulators and highly cited academic taxonomies as of 2022–2023.


---

## 09__Horvitz-1999_Mixed-initiative-user-interfaces — Principles of Mixed-Initiative User Interfaces (Horvitz; 1999; CHI 1999)
**Type:** guideline / principles (illustrated with a prototype, Lookout)  ·  **Sample/method:** conceptual principles + decision-theoretic model; Lookout for Outlook (linear SVM trained on ~1000 messages, 500 relevant / 500 irrelevant); informal timing data from several users.

**Core claim.** Automation and direct manipulation should be combined: agents should act only when expected utility of action exceeds inaction (or dialog), considering uncertainty about goals, attention, and the costs of being wrong, while users retain efficient control.

**The 12 principles**
1. Developing significant value-added automation.
2. Considering uncertainty about a user's goals.
3. Considering the status of a user's attention in the timing of services.
4. Inferring ideal action in light of costs, benefits, and uncertainties.
5. Employing dialog to resolve key uncertainties.
6. Allowing efficient direct invocation and termination.
7. Minimizing the cost of poor guesses about action and timing.
8. Scoping precision of service to match uncertainty, variation in goals.
9. Providing mechanisms for efficient agent-user collaboration to refine results.
10. Employing socially appropriate behaviors for agent-user interaction.
11. Maintaining working memory of recent interactions.
12. Continuing to learn by observing.

**Key findings**
- Decision rule: act if p(G|E) > p* where expected utility of action equals inaction; adding dialog creates two thresholds (inaction↔dialog, dialog↔action). Thresholds shift with context (e.g., cost of unwanted action rises with user's depth of focus → higher threshold; more screen space lowers cost → lower threshold).
- Lookout policy: do nothing, ask, or act depending on inferred probability; when it cannot identify a specific time, it shows a scoped week view rather than guessing poorly ("doing less but doing it correctly").
- Social-agent modality: agent asks, waits, then makes an "apologetic gesture and evaporate[s]" if ignored; time-out scales with inferred probability; dismissable by "no," "not now," "go away."
- Timing: nonlinear (sigmoid) relationship between message length and preferred dwell time before automated scheduling is offered.
- Users can set utilities or thresholds directly; manual-only mode with a passive indicator of what the agent would have done.

**Design rules derivable**
- Automate only when the service adds genuine value beyond direct manipulation. [weak]
- Gate autonomous actions on confidence: below threshold do nothing, mid-range ask, high confidence act. [moderate]
- When uncertain, deliver a reduced-precision but correct result (e.g., open the relevant week, not a guessed appointment). [moderate]
- Always provide a one-click way to invoke and to terminate the agent. [moderate]
- Defer offers until the user is likely ready (e.g., longer content → longer delay); don't interrupt deep focus. [weak]
- Present agent results as editable drafts for the user to refine before committing. [moderate]
- Let unanswered suggestions time out gracefully and accept natural rejection. [weak]
- Expose user control over agent aggressiveness (thresholds/utilities) and offer a manual-only mode. [weak]
- Keep short-term memory of recent interactions for natural references; keep learning from usage under user-set policy. [weak]

**Boundary conditions & caveats.** Position paper; no controlled evaluation; single email-scheduling prototype; timing data from a few users; utilities must be assessed and may vary by context.


---

## Cross-paper patterns in this group
- **Reversibility and exit are a shared core value:** Amershi (G8 dismissal, G9 correction), Horvitz (direct termination, cost of poor guesses), Gray 2018/2024 (Roach Motel), Di Geronimo (41% Roach Motel) and Caraban (easy opt-out preserves autonomy) all converge on "make leaving/undoing as easy as entering/doing."
- **Uncertainty should reduce assertiveness:** Horvitz's thresholds and scoped precision became Amershi's G10; both say ask or degrade gracefully rather than act on low confidence.
- **Transparency of intent is the line between a nudge and a dark pattern:** Caraban's transparency axis, Gray's "user value vs. shareholder value," and Gray 2024's definition (harm applies "regardless of the designer's intent") all locate harm in hidden means and subverted expectations.
- **Defaults are powerful and dangerous:** opt-out yields >90% vs 15% (Caraban background); preselection is among the most common mobile DPs (60% of apps) and is ruled illegal in EU consent contexts (Gray 2024).
- **Visual hierarchy is both a credibility lever and a manipulation vector:** design look is the most-noticed credibility cue (46.1%), while False Hierarchy (61% of apps) abuses the same salience.
- **Ads blended with content are the worst credibility offense** (−2.08, the lowest of 51 items) and a named dark pattern (Disguised Ad).
- **Users are poor detectors:** DP-blindness (55% missed, 20% unsure), privacy policies rarely noticed, Amershi participants unable to find explanations—so protections must be built in by design, not left to user vigilance.
- **Explanations and "why" are wanted but missing:** Amershi G11 had among the most violations; Fogg finds motive/sponsor identity matters (15.5%, 8.8%).
- **Interruptions must respect attention:** Horvitz's attention-sensitive timing, Amershi G3, Caraban's timing/frequency warnings, and Nagging as the most frequent mobile DP (N=352) all argue for well-timed, dismissible-forever prompts.
- **Polish signals trust:** small errors (typos −1.28, broken links −1.45) and amateurism damage credibility; usability (navigation −1.30 when hard) is itself a credibility factor.
- **Evidence quality varies:** strongest numbers come from Fogg (large self-report/content analysis) and Di Geronimo (prevalence); Amershi validates relevance not outcomes; Horvitz and Gray are principled/taxonomic—rules from them should be treated as moderate/weak.
