# Trust, credibility, persuasion and dark patterns

> How to earn credibility honestly, how to tell a nudge from a dark pattern, and how to audit choice screens, consent flows, pricing and prompts so they serve the user. Evidence grades: **[A]** strong — replicated, large-N, meta-analytic, or an international standard; **[B]** moderate — one solid study or converging smaller studies; **[C]** weak — expert opinion, theory, small qualitative work, or extrapolation from lab psychology to UI.

## Rules

### ET-1. Make undoing as easy as doing
- **Do:** Cancel, unsubscribe, withdraw consent, log out and delete an account through the same channel and with comparable effort (steps, clicks, screens) as sign-up, subscribe or consent. Provide in-app logout and account deletion, or a direct link to it. Disclose the cancellation method at the point of sign-up. Never require a phone call or business-hours contact to cancel an online sign-up.
- **Why:** Roach Motel ("easy in, hard out") is a core Obstruction pattern (Gray 2018). The ontology defines it as subverting the expectation that an action will be as easy to reverse as it is to make; EU courts and data-protection authorities have ruled against refusing consent being harder than giving it (Gray 2024). 41% of 240 popular Android apps had no logout or no account deletion (Di Geronimo 2020). Hard to Cancel appeared on 31 shopping sites (Mathur 2019). Phone-only cancellation is a named obstruction (Mathur 2021).
- **Evidence:** [B] — (Gray 2018; Gray 2024; Di Geronimo 2020; Mathur 2019; Mathur 2021).
- **Limits:** Prevalence counts are lower bounds (text-only crawl, first 10 minutes of app use). Regulatory backing is EU/UK/US-centric. Some friction on destructive actions (e.g., a confirmation) is not obstruction if it is equal in kind to the friction on the way in.

### ET-2. Set defaults in the user's interest; never preselect against it
- **Do:** Leave data sharing, marketing, notification types, add-ons, insurance and upsells unchecked. Require an explicit opt-in. Default product variants to the user's selection or the cheapest option, not the most expensive. When users are indifferent, make the pro-user option the default and keep opting out visible and easy.
- **Why:** Defaults are powerful: organ donation is >90% under opt-out vs ~15% under opt-in (background cited in Caraban 2019). Preselection appeared in 60% of 240 apps; notification preselection was the most frequent form (121 instances) and 81 apps preselected more than two notification types (Di Geronimo 2020). Sneak into Basket and Forced Enrollment were found on shopping sites (Mathur 2019). EU courts have forbidden preselection, which maps to the ontology's Bad Defaults: subverting the expectation that default settings will be in the user's best interest (Gray 2024).
- **Evidence:** [A] — regulator-backed and converging prevalence data (Gray 2024; Di Geronimo 2020; Mathur 2019; Caraban 2019).
- **Limits:** The >90%/15% figure is background, not a UI study. A pro-user default still needs a visible way out (Caraban 2019).

### ET-3. Give competing options equal weight and equal paths
- **Do:** Style accept/decline, subscribe/skip, and parallel options in parallel: same size, contrast, shape and position class. Never grey out an option that is active. Make the privacy-protective or decline option reachable in the same number of steps as accept; never hide "Deny" behind a multi-screen "Manage options".
- **Why:** False Hierarchy (e.g., a grey "custom" option that looks disabled) is a named Interface Interference pattern (Gray 2018) and was found in 61% of apps (Di Geronimo 2020). Visual Interference appeared on 24 shopping sites (Mathur 2019). "Asymmetric" (unequal burden across options) is one of the six dark-pattern attributes (Mathur 2021). The ontology lists Visual Prominence and Privacy Maze (Gray 2024). Consent obtained via Visual Interference is not valid GDPR consent (Mathur 2019).
- **Evidence:** [A] — (Gray 2018; Gray 2024; Di Geronimo 2020; Mathur 2019; Mathur 2021).
- **Limits:** A recommended option may be visually marked if the recommendation serves the user and the alternative stays equally reachable (see ET-20). Text-only crawls miss style-based patterns, so true prevalence is higher (Mathur 2019).

### ET-4. Ask for consent clearly, affirmatively, and unbundled
- **Do:** Phrase every consent checkbox as an affirmative opt-in. No double negatives, no "check to opt out". Never bundle marketing consent with terms acceptance. Do not require account creation just to browse. Do not make terms or privacy text tiny or greyed out. In usability tests, check that users can correctly state what each option does.
- **Why:** Trick Questions (opt-out checkboxes, double negatives) are a named pattern (Gray 2018; Gray 2024) found on 9 shopping sites (Mathur 2019). Consent via Trick Questions or Visual Interference is not valid GDPR consent, which must be freely given, specific, informed and unambiguous (Mathur 2019; Mathur 2021). Forced Registration is a Forced Action subtype (Gray 2024). Comprehension of options is the regulatory-lens measure in the Trick Questions case study (Mathur 2021).
- **Evidence:** [A] — regulatory standard plus taxonomies (Mathur 2019; Mathur 2021; Gray 2018; Gray 2024).
- **Limits:** Legal tests vary by jurisdiction. Registration may be essential for some services; the rule targets registration that is not needed for the task.

### ET-5. Show the full price up front
- **Do:** Show the total price, including taxes, fees and shipping, at the first price display and before checkout data entry. Never reveal new charges at the final step. State recurring billing, renewal amount and period at the point of purchase for any trial or "one-time" offer, and warn before a trial converts to paid. Never use fake reference ("was") prices. Show real-money cost when a virtual currency is used.
- **Why:** Sneaking hides or delays information relevant to the user: Hidden Costs (a 99¢ banner leading to a 4-week trial), Forced Continuity, Sneak into Basket (Gray 2018). The ontology adds Drip Pricing, Partitioned Pricing and Reference Pricing; Intermediate Currency obscures real cost (Gray 2024). Hidden Subscription had 14 instances on 13 sites and Hidden Costs 5 (Mathur 2019). Sneaking likely violates the EU Consumer Rights Directive (Mathur 2019).
- **Evidence:** [B] — (Gray 2018; Gray 2024; Mathur 2019).
- **Limits:** Mathur 2019 covered product, cart and checkout pages only, not post-purchase flows.

### ET-6. Make urgency, scarcity and social proof true or absent
- **Do:** Show countdown timers only for real, stated deadlines; never reset them or keep the offer after expiry. Generate low-stock, high-demand and activity messages only from real, current data; never randomize or hard-code them. Attribute testimonials to verifiable sources.
- **Why:** Low-stock messages appeared 632 times on 581 sites, countdown timers 393 times on 361 sites, activity messages 313 times on 264 sites (Mathur 2019). 157 timers on 140 sites were deceptive (reset, or offer still valid after expiry); 29 activity notifications on 20 sites were random or hard-coded; 16 of 17 deceptive low-stock messages decremented on a schedule; 38 of 47 high-demand messages appeared regardless of product (Mathur 2019). More than 40% of timers reset or were inconsequential (Mathur 2019, as cited in Mathur 2021). The ontology groups these under Social Engineering: Urgency, Scarcity and Popularity Claims, Social Proof (Gray 2024). Deceptive practices are unlawful under FTC Act §5 and the EU Unfair Commercial Practices Directive (Mathur 2019).
- **Evidence:** [A] — large-scale crawl of ~11K sites plus regulatory status (Mathur 2019; Gray 2024; Mathur 2021).
- **Limits:** Some cases are contested gray areas (e.g., free-shipping timers) (Mathur 2019). A true deadline shown honestly is not a dark pattern.

### ET-7. Ask once; remember the answer
- **Do:** Store every choice the user makes (notifications, location, rating prompts, cookie choice, upsell decline) and do not re-ask. Every recurring prompt offers a permanent "Don't ask again" with the same prominence as "OK". Do not interrupt the primary task with rating, permission or ad pop-ups; if one is unavoidable, include a permanent dismiss.
- **Why:** Nagging is redirection of expected functionality that persists beyond one or more interactions, e.g., a modal with only "Not Now"/"OK" (Gray 2018). It was the most frequent mobile dark pattern (352 instances) and 55% of apps interrupted users (Di Geronimo 2020). The EU Digital Services Act prohibits repeated requests for a choice already made, which maps to Nagging (Gray 2024). Repeated prompts until acceptance disrespect a "no" (Mathur 2021).
- **Evidence:** [A] — regulator-backed plus prevalence (Gray 2018; Gray 2024; Di Geronimo 2020; Mathur 2021).
- **Limits:** Re-asking after a material change in what is requested is a new choice, not nagging; say what changed.

### ET-8. Use neutral, symmetric decline copy
- **Do:** Label decline options plainly ("No thanks", "Skip"). Never shame the user ("No thanks, I like paying full price"). Do not use fear, guilt, cuteness or emotion-laden framing to steer users away from privacy-respecting or cheaper choices.
- **Why:** Confirmshaming is a Toying with Emotion subtype (Gray 2018) and was found 169 times on 164 shopping sites (Mathur 2019). The ontology lists Shaming and Emotional or Sensory Manipulation (Cuteness, Positive or Negative Framing) (Gray 2024). Fear and guilt framing against privacy choices is flagged in Mathur 2021. Confirmshaming is fully transparent yet still counted as dark, which shows deception is not required for harm (Mathur 2021).
- **Evidence:** [B] — (Gray 2018; Gray 2024; Mathur 2019; Mathur 2021).
- **Limits:** Informative consequence statements ("You will stop receiving order updates") are not shaming if accurate and neutral.

### ET-9. Keep ads and paid content clearly distinct
- **Do:** Visually and verbally separate ads from content. Never disguise an ad as content, a button, a download or a feature. Never make a free-looking feature open a paywall or upsell. Avoid pop-up ads and ad-dominated layouts.
- **Why:** "Hard to distinguish ads from content" was the lowest-rated of all 51 credibility items at −2.08 on a −3..+3 scale; pop-up ads −1.56; ads on every page −0.77 (Fogg 2001, N=1,410). Advertising was mentioned in 13.8% of credibility comments overall and 24.6% for search sites; pop-ups were widely disliked (Fogg 2003, N=2,684). Disguised Ad is a named pattern (Gray 2018; Gray 2024). Di Geronimo 2020 flags features that open paywalls.
- **Evidence:** [A] — two large studies converge with taxonomies (Fogg 2001; Fogg 2003; Gray 2018; Gray 2024; Di Geronimo 2020).
- **Limits:** Fogg 2001 is self-reported hypothetical ratings from 1999 data. Topic-matched ads were tolerated (+0.21) (Fogg 2001).

### ET-10. Keep controls predictable and information consistent
- **Do:** A close "X" always closes. Never put a purchase or consent action where a habitual action usually sits. Make the outcome of each control predictable before it is pressed. Do not show conflicting information or information without context. Provide key information in the user's language and in plain wording.
- **Why:** Bait and Switch includes a red "X" that does not close and a buy button placed where the new-game button usually is (Gray 2018). The ontology names Feedforward Ambiguity, Conflicting Information, Information without Context, and Language Inaccessibility (Wrong Language, Complex Language) (Gray 2024). Dark patterns widen both the gulf of execution and the gulf of evaluation (Gray 2018).
- **Evidence:** [B] — (Gray 2018; Gray 2024).
- **Limits:** Taxonomic work without effect sizes.

### ET-11. Do not obstruct or force unrelated actions
- **Do:** Do not add steps to privacy-protective choices. Avoid dead-end links. Allow copying of product names and prices. Never condition core functions (unsubscribe, shutdown, access) on unrelated consent, data sharing, contact-list access or inviting friends. Do not require registration unless essential.
- **Why:** Obstruction makes a process harder than needed to dissuade an action; subtypes include Price Comparison Prevention and Intermediate Currency (Gray 2018). Price Comparison Prevention occurred 23 times, in 77% of shopping apps; Privacy Zuckering in 31% of apps (Di Geronimo 2020). Forced Action covers Social Pyramid, Friend Spam, Privacy Zuckering, Address Book Leeching and Forced Registration (Gray 2018; Gray 2024). "Restrictive" (eliminating choices) is one of the six attributes (Mathur 2021).
- **Evidence:** [B] — (Gray 2018; Gray 2024; Di Geronimo 2020; Mathur 2021).
- **Limits:** Some data access is essential to a feature; ask for it at the moment of need with a stated reason.

### ET-12. Judge designs by user value, not only conversion or usability metrics
- **Do:** For every choice, consent, pricing or retention screen, test against a neutral baseline: a regulation-specified design, a minimal variant without the suspected pattern, or a competitor design. Measure (a) whether choices match users' stated preferences, (b) comprehension of options, (c) awareness that options exist, (d) trust change. If uptake roughly doubles versus the baseline, or choices diverge from stated preferences, redesign. Check effects on vulnerable sub-populations and on non-users.
- **Why:** Some dark patterns (forced action, nagging) test well on usability metrics at the expense of user choice (Gray 2018). Mathur 2021 proposes baseline comparison with thresholds and four normative lenses, and a Trick Questions case study measuring preference match, trust, comprehension and awareness. Background: acceptance rose from 11% (no dark pattern) to 26% (mild) to 42% (aggressive) (Luguri and Strahilevitz, cited in Di Geronimo 2020); uptake more than doubling vs an alternative is the cited threshold (Mathur 2021).
- **Evidence:** [B] — (Mathur 2021; Gray 2018; Di Geronimo 2020).
- **Limits:** Thresholds require normative justification; the welfare baseline is hard to define; the authors call their case-study methods relatively naive (Mathur 2021).

### ET-13. Audit proactively; users will not report dark patterns
- **Do:** Run an ethics audit (see below) before launch and after each growth experiment. Do not use absence of complaints as evidence of a clean design.
- **Why:** Across 1,178 answers about apps containing dark patterns, 55% did not spot malicious design, 20% were unsure, and 25% did; only 7% of 366 open comments mentioned one spontaneously; of those who spotted something, 24% identified the actual pattern; Sneak into Basket plus Preselection was detected by only 14% (Di Geronimo 2020). Detection improved with prior knowledge, not with age or education (Di Geronimo 2020). Privacy policies were rarely noticed on any of 100 sites (Fogg 2003).
- **Evidence:** [B] — (Di Geronimo 2020; Fogg 2003).
- **Limits:** Participants watched 30-second videos rather than using apps; highly educated sample (Di Geronimo 2020).

### ET-14. Do not copy patterns or plugins without an ethics check
- **Do:** Before reusing a pattern from a popular product, or embedding a third-party conversion, urgency or social-proof plugin, check it against the ethics audit. Disable fake-data features.
- **Why:** 95% of 240 trending apps contained at least one dark pattern (mean 7.4 per app) (Di Geronimo 2020). More popular shopping sites were more likely to have dark patterns (Spearman's rho = −0.62) (Mathur 2019). 22 third parties supplied dark patterns to 1,066 shopping sites and 7,769 top-million sites; two openly advertised fake orders or "Fake it till you make it" (Mathur 2019). Mimicry spreads dark patterns (Di Geronimo 2020).
- **Evidence:** [B] — (Mathur 2019; Di Geronimo 2020).
- **Limits:** Popularity correlation is not causal. "Common" does not mean "accepted by users"; it often means "unnoticed" (ET-13).

### ET-15. Show the real organization behind the product
- **Do:** Show a physical address, phone number and contact email; respond quickly to customer service. State who runs the site, its mission and motive, especially for nonprofits. Make the domain name match the organization name.
- **Why:** Real-World Feel had the largest positive effect: quick customer-service response +2.02, physical address +1.86, phone +1.71, email +1.53; domain not matching company −1.06 (Fogg 2001). Company motive was mentioned in 15.5% of comments and sponsor identity in 8.8%; for nonprofits, identity rose to 28.9%; sites with unclear, selling-only motive lost credibility (Fogg 2003).
- **Evidence:** [A] — two large-N studies (Fogg 2001; Fogg 2003).
- **Limits:** Fogg 2001 measures self-reported hypothetical ratings, not behavior; alphas are modest (0.44–0.67).

### ET-16. Remove amateur signals: typos, broken links, downtime, stale content
- **Do:** Ship with zero typos and zero broken links. Monitor uptime. Show visible update dates and keep content current.
- **Why:** Rarely updated −1.67, link to a non-credible site −1.53, broken link −1.45, typo −1.28, sometimes unavailable −1.28; updated since last visit +1.55 (Fogg 2001). Even one typo or broken link is damaging (Fogg 2001).
- **Evidence:** [A] — (Fogg 2001).
- **Limits:** Self-report; younger respondents judged amateurism more harshly; web experience made no difference (Fogg 2001).

### ET-17. Invest in professional visual design and sensible structure
- **Do:** Use a polished layout, typography, white space and imagery. Organize information in clear layers; do not cram everything on the home page. Provide search across past content. Keep pages fast.
- **Why:** Design look was the most-noticed credibility cue (46.1% of comments), then information design/structure (28.5%) (Fogg 2003). "Looks professionally designed" +1.55, "arranged in a way that makes sense" +1.48, search past content +1.57, difficult to navigate −1.30, long download −0.94 (Fogg 2001). For search sites, information design rose to 42.6% (Fogg 2003).
- **Evidence:** [A] — (Fogg 2001; Fogg 2003).
- **Limits:** Fogg 2003 participants had low involvement, so they leaned on peripheral cues; "design look" was the broadest coding category. Visual salience is also the lever abused by False Hierarchy, so polish must not be used to steer (ET-3).

### ET-18. Show expertise and sources, in an understated tone
- **Do:** Show author credentials, citations and references. Link to outside sources, including competitors where relevant. State a content policy. Write in an understated, non-sensational tone without slang or marketing language.
- **Why:** Respected news organization +1.91, author credentials +1.49, citations +1.49, content policy +1.26, links to outside sources +1.25, links to competitors +1.11 (Fogg 2001). Tone of writing was mentioned in 9.0% of comments; slang and marketing language hurt credibility; bias was noticed in 30.2% of news-site comments (Fogg 2003).
- **Evidence:** [A] — (Fogg 2001; Fogg 2003).
- **Limits:** Effects vary by category (ET-19). Information contradicting the user's beliefs lowered credibility (−0.77) regardless of quality (Fogg 2001).

### ET-19. Make credibility cues prominent and fit them to the category
- **Do:** Decide which credibility cues must be noticed and give them prominence. Weight cues by domain: reputation and customer service for e-commerce, neutrality for news, organizational identity for nonprofits, result quality for search. Do not count on privacy policies or seals to build credibility unless they are made prominent.
- **Why:** By Prominence-Interpretation Theory, credibility impact = prominence × interpretation; a cue nobody notices has no effect (Fogg 2003). E-commerce: name/reputation 25.9% and customer service 16.7% (vs 14.1% and 6.4% overall); news: bias 30.2%; nonprofit: identity 28.9%; travel: customer service 18.1%; search: functionality 20.5% (Fogg 2003). Privacy policies were rarely noticed (Fogg 2003).
- **Evidence:** [B] — (Fogg 2003).
- **Limits:** Percentages depend on the coding scheme, site set and sample; the study measures what is noticed, not how it is interpreted.

### ET-20. Nudge transparently and toward the user's own goals
- **Do:** Prefer nudges whose intent and means the user can see (defaults, positioning plus labeling, just-in-time prompts, consequence reminders). Treat non-transparent automatic nudges (deceptive visualizations, subliminal priming, hidden opt-outs, decoys) as high-risk. Never add friction the user cannot bypass. Combine positioning with a clear cue; positioning alone may not work.
- **Why:** Caraban 2019 found 23 mechanisms in 6 categories (Facilitate, Confront, Deceive, Social influence, Fear, Reinforce) across 74 examples, mapped on transparency × automaticity: 52% prompt reflective choice, 26% influence behavior transparently, 22% manipulate behavior non-transparently. There is no inherent conflict between nudging and transparency or reflection (Caraban 2019). Color plus positioning of secure Wi-Fi worked for 60% of participants; positioning alone did not (Caraban 2019). Several Deceive and Fear mechanisms overlap with dark patterns when used against user interests (Caraban 2019); many dark patterns resemble persuasive strategies (Gray 2018).
- **Evidence:** [B] — systematic review of 71 papers (Caraban 2019; Gray 2018).
- **Limits:** Mostly short lab studies of research prototypes; categorization is the authors' (Caraban 2019).

### ET-21. Time nudges well, test for backfire, and check persistence
- **Do:** Deliver nudges at the moment of decision (offer the better option at selection, not checkout). Use personalized, well-timed prompts instead of generic periodic reminders; limit frequency. Compare users only to peers of similar performance. Evaluate over weeks, after nudge removal, and test for backfire and reactance.
- **Why:** 49 of 74 (66%) studied nudges had a significant effect, with no clear link between mechanism and effectiveness (Caraban 2019). Food swaps were accepted more at selection than at checkout (median 4 of 12) (Caraban 2019). Failures came from no educational effect, unsustained effects, backfire (below-average energy users consumed more after comparison; public commitments led to fewer commitments), reactance, poor timing or strength, and strong habits (Caraban 2019). Only 7 studies (14%) checked persistence after removal (Caraban 2019).
- **Evidence:** [B] — (Caraban 2019).
- **Limits:** Median sample 64; few studies longer than one month. Expect little effect on entrenched habits.

### ET-22. Protect autonomy and treat groups equally
- **Do:** Avoid engagement mechanics that override user intent (infinite scroll, autoplay, variable-reward loot boxes), especially for children and teens. Offer explicit stopping points. Do not default to autoplay where it extends use beyond intent. Never covertly price- or option-discriminate between user groups (e.g., pay-to-skip that disadvantages one group).
- **Why:** The autonomy lens covers addiction-inducing infinite scroll, autoplay and loot boxes; "Disparate Treatment" is a new attribute (Mathur 2021). The ontology lists Attention Capture (Auto-Play) and Gamification (Pay-to-Play, Grinding) (Gray 2024). A $245M FTC judgment against Fortnite is cited (Gray 2024).
- **Evidence:** [C] — normative framework and taxonomy (Mathur 2021; Gray 2024).
- **Limits:** The autonomy lens sweeps broadly; not every scroll or autoplay is harmful.

## Ethics audit

Apply to every choice screen, consent flow, checkout, retention flow and recurring prompt. Any "no" is a finding.

**Six attributes (Mathur 2021)**
- [ ] Not asymmetric: every option costs the same effort (steps, clicks, visual weight).
- [ ] Not restrictive: no reasonable option is removed or hidden.
- [ ] No disparate treatment: no user group is covertly disadvantaged.
- [ ] Not covert: the user can see how the design is trying to influence them.
- [ ] Not deceptive: no claim creates a false belief (price, stock, demand, timer, testimonial, button outcome).
- [ ] No information hiding: necessary information (price, renewal, data use) is not delayed or buried.

**Five strategies to scan for (Gray 2018; Gray 2024)**
- [ ] Nagging: no repeated request for a choice already made.
- [ ] Obstruction: no roach motel, privacy maze, dead end, price comparison prevention, intermediate currency.
- [ ] Sneaking: no sneak into basket, drip pricing, hidden subscription, disguised ad, fake reference price.
- [ ] Interface interference: no preselection against the user, false hierarchy, trick question, confirmshaming, hidden information, feedforward ambiguity.
- [ ] Forced action / social engineering: no forced registration, contact leeching, friend spam, fake urgency, fake scarcity, fake social proof.

**Four normative lenses (Mathur 2021)**
- [ ] Individual welfare: no unexpected financial loss, privacy invasion or added cognitive burden.
- [ ] Collective welfare: does not erode price transparency, competition or trust in the market.
- [ ] Regulatory: consent is freely given, specific, informed and unambiguous; no unfair or deceptive practice.
- [ ] Autonomy: users act on their own reasons; stopping points exist.

**Method check (Mathur 2021; Gray 2018)**
- [ ] Compared against a neutral baseline variant, not only against conversion targets.
- [ ] Users' choices match their stated preferences; users can state what each option does.
- [ ] Third-party plugins and copied patterns were checked (Mathur 2019; Di Geronimo 2020).

## Persuasion that is acceptable

Persuasion is acceptable when it is transparent, serves a goal the user holds, and leaves every option equally reachable (Caraban 2019; Mathur 2021). Examples supported by the sources:
- A pro-user default (e.g., double-sided printing reduced paper use by 15%) with a visible opt-out (Caraban 2019).
- Ordering and labeling the safer option first, with color plus position, while the alternative stays equally available (Caraban 2019).
- A short, reversible delay or a consequence reminder before regrettable actions such as posting publicly (e.g., showing who will see it) (Caraban 2019).
- Just-in-time, personalized prompts toward a goal the user set, at low frequency (Caraban 2019).
- Social comparison only with similar peers, never against a norm that licenses worse behavior (Caraban 2019).
- True deadlines and true stock levels, shown plainly (Mathur 2019).

Not acceptable: anything that relies on the user not noticing it (Caraban 2019 "manipulate" quadrants), any claim that is false (Mathur 2019), and any friction the user cannot bypass (Caraban 2019).

## Numbers at a glance
| Parameter | Value | Grade | Source |
|---|---|---|---|
| Worst credibility item: ads hard to distinguish from content | −2.08 on −3..+3 (lowest of 51) | A | Fogg 2001 |
| Rarely updated / broken link / typo / sometimes unavailable | −1.67 / −1.45 / −1.28 / −1.28 | A | Fogg 2001 |
| Pop-up ads | −1.56 | A | Fogg 2001 |
| Quick customer-service response / physical address / phone | +2.02 / +1.86 / +1.71 | A | Fogg 2001 |
| Requires login | +0.07 (about no effect) | B | Fogg 2001 |
| Design look share of credibility comments | 46.1% | A | Fogg 2003 |
| Information design/structure share | 28.5% | A | Fogg 2003 |
| Shopping sites with dark patterns | 1,254 of ~11K (~11.1%, lower bound) | A | Mathur 2019 |
| Deceptive countdown timers | 157 on 140 sites | A | Mathur 2019 |
| High-demand messages shown regardless of product | 38 of 47 | A | Mathur 2019 |
| Third parties supplying dark patterns | 22, on 1,066 shopping sites | A | Mathur 2019 |
| Apps with at least one dark pattern | 95% of 240 (mean 7.4 per app) | B | Di Geronimo 2020 |
| Apps with Nagging / False Hierarchy / Preselection | 352 instances / 61% / 60% | B | Di Geronimo 2020 |
| Apps lacking logout or account deletion | 41% | B | Di Geronimo 2020 |
| Users who missed dark patterns / unsure / spotted | 55% / 20% / 25% | B | Di Geronimo 2020 |
| Acceptance with no / mild / aggressive dark pattern | 11% / 26% / 42% | B | Luguri and Strahilevitz, cited in Di Geronimo 2020 |
| Opt-out vs opt-in default (organ donation) | >90% vs ~15% | B | background in Caraban 2019 |
| Studied nudges with significant effect | 49 of 74 (66%) | B | Caraban 2019 |
| Nudge mechanisms / categories | 23 / 6 | B | Caraban 2019 |
| Ontology levels | 5 high / 25 meso / 35 low | C | Gray 2024 |

## Common misreadings
- "Dark patterns are rare edge cases." — 95% of popular apps had at least one (Di Geronimo 2020); 11.1% of shopping sites is a text-only lower bound (Mathur 2019).
- "If users don't complain, the flow is fine." — Most users do not recognize dark patterns (Di Geronimo 2020).
- "If it tests well in usability metrics, it is good design." — Some dark patterns test well at the expense of user choice (Gray 2018).
- "A nudge must be hidden to work." — Caraban 2019 finds no inherent conflict between nudging and transparency; 52% of examples prompted reflective choice.
- "A dark pattern requires deception or intent." — Confirmshaming and Nagging are transparent yet listed (Mathur 2021); the ontology defines harm regardless of designer intent (Gray 2024).
- "A privacy policy builds trust." — Privacy policies were rarely noticed (Fogg 2003).
- "Requiring login makes a site seem more credible." — Effect about zero (+0.07) (Fogg 2001).
- "Looks matter more than content." — Design look is the most noticed cue (Fogg 2003), but participants had low involvement and the study measured what was noticed, not how it was weighed.
- "Gray 2018's five strategies are an ethics checklist." — The authors explicitly do not propose them as one; use them as a scan list alongside Mathur 2021's attributes and lenses.
- "The ontology has exactly 64 types." — The paper's counts are inconsistent (64 vs 65 types; 24/34 vs 25/35 definitions) (Gray 2024).

## Review checklist
- [ ] ET-1: Can the user cancel, withdraw consent, log out and delete the account in the same channel and with no more effort than signing up?
- [ ] ET-2: Are all data-sharing, marketing, notification and add-on options unchecked by default, and do defaults favor the user?
- [ ] ET-3: Do accept and decline (or parallel options) have equal visual weight and the same number of steps?
- [ ] ET-4: Is every consent affirmative, unbundled from terms, free of double negatives, and understood by test users?
- [ ] ET-5: Is the full total price, including fees and recurring terms, shown at first price display?
- [ ] ET-6: Is every timer, stock, demand, activity and testimonial claim backed by real, current data?
- [ ] ET-7: Is each user choice stored, never re-asked, and every recurring prompt dismissible permanently?
- [ ] ET-8: Is decline copy neutral, with no shaming, guilt or fear framing?
- [ ] ET-9: Are ads clearly distinguishable from content, with no disguised ads or pop-ups?
- [ ] ET-10: Does every control behave as its appearance predicts (X closes, no swapped positions), with consistent plain-language information?
- [ ] ET-11: Is core functionality free of unrelated forced actions (registration, contacts, consent) and obstruction?
- [ ] ET-12: Was the design compared against a neutral baseline on preference match, comprehension and awareness, not only conversion?
- [ ] ET-13: Was a proactive ethics audit done rather than relying on user complaints?
- [ ] ET-14: Were copied patterns and third-party plugins checked for dark-pattern features?
- [ ] ET-15: Are address, phone, email, sponsor identity and motive visible, and does the domain match the organization?
- [ ] ET-16: Are there zero typos, zero broken links, and visible, recent update dates?
- [ ] ET-17: Is the visual design professional and the information structure layered and navigable, with search?
- [ ] ET-18: Are credentials, citations and outside links shown, in an understated tone?
- [ ] ET-19: Are the category-relevant credibility cues prominent enough to be noticed?
- [ ] ET-20: Is every nudge transparent, aimed at the user's own goal, and bypassable?
- [ ] ET-21: Are nudges timed at the decision point, frequency-limited, and evaluated for backfire and persistence?
- [ ] ET-22: Are there explicit stopping points, no autoplay by default, and no covert group-differential treatment?

## Sources
- Caraban, A., Karapanos, E., Gonçalves, D., Campos, P. (2019). *23 ways to nudge: a review of technology-mediated nudging in human-computer interaction*. CHI '19. https://doi.org/10.1145/3290605.3300733
- Di Geronimo, L., Braz, L., Fregnan, E., Palomba, F., Bacchelli, A. (2020). *UI dark patterns and where to find them: a study on mobile applications and user perception*. CHI '20. https://doi.org/10.1145/3313831.3376600
- Fogg, B.J., et al. (2001). *What makes web sites credible? A report on a large quantitative study*. CHI '01. https://doi.org/10.1145/365024.365037
- Fogg, B.J., Soohoo, C., Danielson, D.R., Marable, L., Stanford, J., Tauber, E.R. (2003). *How do users evaluate the credibility of web sites? A study with over 2,500 participants*. DUX '03. https://doi.org/10.1145/997078.997097
- Gray, C.M., Kou, Y., Battles, B., Hoggatt, J., Toombs, A.L. (2018). *The dark (patterns) side of UX design*. CHI '18. https://doi.org/10.1145/3173574.3174108
- Gray, C.M., Santos, C., Bielova, N., Mildner, T. (2024). *An ontology of dark patterns knowledge: foundations, definitions, and a pathway for shared knowledge-building*. CHI '24. https://doi.org/10.1145/3613904.3642436
- Mathur, A., Acar, G., Friedman, M.J., Lucherini, E., Mayer, J., Chetty, M., Narayanan, A. (2019). *Dark patterns at scale: findings from a crawl of 11K shopping websites*. Proc. ACM HCI (CSCW '19). https://doi.org/10.1145/3359183
- Mathur, A., Kshirsagar, M., Mayer, J. (2021). *What makes a dark pattern... dark? Design attributes, normative considerations, and measurement methods*. CHI '21. https://doi.org/10.1145/3411764.3445610
