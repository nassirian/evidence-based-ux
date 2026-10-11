# Evaluating and measuring UX quality

> How to plan, run, score and interpret usability and UX evaluations (inspection, testing, questionnaires, models) so that conclusions match what the evidence can support. Evidence grades: **[A]** strong — replicated, large-N, meta-analytic, or an international standard; **[B]** moderate — one solid study or converging smaller studies; **[C]** weak — expert opinion, theory, small qualitative work, or extrapolation from lab psychology to UI.

## Rules

### EV-1. Never trust a single evaluator; aggregate 3–5 independent ones
- **Do:** Have 3–5 people inspect the interface independently, then merge their problem lists. Do not let evaluators discuss findings until each has finished. Report the merged list, not any one person's list.
- **Why:** Single evaluators found 20–51% of known problems across four experiments; aggregates of about five found roughly two thirds, with returns flattening between 5 and 10 (Nielsen 1990). Across 13 datasets one evaluator or user found 33% on average (λ = .31) (Nielsen 1993). Motivated industry designers found 37% of problems in a one-screen dialogue (11.2 of 30) and 44% of serious ones (Molich 1990). Detection is not cumulative: weak evaluators find some hard problems and strong ones miss easy ones, which is why pooling helps (Nielsen 1990).
- **Evidence:** [A] — (Nielsen 1990; Nielsen 1993; Molich 1990).
- **Limits:** Evaluators in these studies were mostly non-experts on small interfaces. Pooling assumes someone merges duplicates reliably. Working independently first is the authors' belief, not tested.

### EV-2. Iterate with small studies and estimate what remains
- **Do:** Run small rounds (about 3–5 users or evaluators), fix, and re-test instead of one large study. After two or more sessions, estimate λ and the total problem count with Found(i) = N(1 − (1 − λ)^i). From two evaluations: λ = 2 − Found(2)/Found(1), and N = Found(1)/λ. Stop when the predicted marginal yield is worth less than another session. Average Found(i) over all orderings of evaluators.
- **Why:** The model fit 13 datasets mostly with R² > .93. Benefit/cost peaked at about 3.2 test users and 4.4 evaluators per round for a medium-large project. The estimate of N stabilizes as data grows: SD 21% with 4 people, 11% with 5, 5% with 9–10 (Nielsen 1993).
- **Evidence:** [A] — (Nielsen 1993; Nielsen 1990).
- **Limits:** The model assumes independent detection and equal yield per evaluator, and slightly underestimates N. Estimates from 2–3 people are highly variable. Cost figures are 1993 illustrations.

### EV-3. Size the study from the discovery rate, not from "five users"
- **Do:** Compute the per-user discovery rate from early sessions. If it is near .3, about five users find most problems. If it is near .2, plan at least seven users for 80% discovery. Expect lower rates for minor problems than for severe ones.
- **Why:** λ ranged from .12 to .58 across studies (Nielsen 1993). In a user test of an e-learning portal, p = .22 overall (.30 severe, .21 moderate, .18 minor), so at least seven users were needed for 80% of problems (Hvannberg 2007).
- **Evidence:** [B] — (Nielsen 1993; Hvannberg 2007).
- **Limits:** Hvannberg is one study with user tasks derived from inspection predictions. λ depends on the interface, tasks, and evaluator skill.

### EV-4. Use evaluators with usability and domain expertise
- **Do:** Prefer usability specialists. Where possible add evaluators who also know the domain. If only developers are available, add more of them and validate with users.
- **Why:** On a banking system, each non-specialist found 22% of problems, each usability specialist 41%, and each usability-plus-domain specialist 60% (Nielsen 1993). Developers can inspect, but specialists normally do better (Nielsen 1994b). Novice evaluators had any-two agreement of only 0.046 (Hvannberg 2007).
- **Evidence:** [B] — (Nielsen 1993; Nielsen 1994b; Hvannberg 2007).
- **Limits:** The 22/41/60% figures come from one system.

### EV-5. Inspect with the revised Nielsen heuristics and know what they cover
- **Do:** Use the nine heuristics as the primary inspection checklist: visibility of system status; match between system and the real world; user control and freedom; consistency and standards; error prevention; recognition rather than recall; flexibility and efficiency of use; aesthetic and minimalist design; help users recognize, diagnose, and recover from errors. Give extra attention to recognition over recall and visible actions, which explain the most serious problems. Consider domain-specific heuristics for unusual product classes.
- **Why:** Rating 101 heuristics against 249 real problems, the top seven factors explained only 30% of variance, and 53 factors were needed for 90%: problems have many causes. Still, Nielsen's set explained 82% of problems at a rating of 3 or more, ahead of six other published sets (73% down to 44%). Consistency alone explained 23% of all problems; "seeing/pointing vs. remembering/typing" explained 22% of serious ones (Nielsen 1994a). Error-prevention problems are the ones designers most often miss: 55% of contest entries mentioned none (Molich 1990).
- **Evidence:** [B] — (Nielsen 1994a; Molich 1990).
- **Limits:** One rater; the data explains problems already found, not how well the list helps find new ones. Nielsen's heuristics and Gerhardt-Powals' cognitive principles performed the same for novices (effectiveness 0.14 each) (Hvannberg 2007).

### EV-6. Combine inspection with user testing; do not substitute one for the other
- **Do:** Treat inspection findings as predictions. Confirm them with think-aloud testing, ideally with tasks that target the predicted problem areas. Report validity (confirmed / predicted) and thoroughness (confirmed / real) when you can.
- **Why:** Novice heuristic evaluation had validity 0.38, thoroughness 0.55 and overall effectiveness about 0.21 against user-test results; 53 of 85 predicted problems were false alarms (Hvannberg 2007). Inspection and testing find partly different problems, so combining methods works best (Nielsen 1994b; Nielsen 1990).
- **Evidence:** [B] — (Hvannberg 2007; Nielsen 1994b; Nielsen 1990).
- **Limits:** Hvannberg used novices on one portal. Expert inspection has higher yield (EV-4) but the same structural blind spots.

### EV-7. Write every problem in a structured report
- **Do:** Record each problem with: ID, short description, likely user difficulty, specific context (screen, element, task step), possible cause, heuristic(s) violated, and severity (severe / moderate / minor). Merge duplicates by matching context and cause.
- **Why:** This seven-attribute format was proposed to make merging and matching of problems across evaluators and methods possible (Hvannberg 2007). Neither the heuristic set nor the reporting medium changed effectiveness in that study, so structure is mainly for merging and validation.
- **Evidence:** [C] — (Hvannberg 2007).
- **Limits:** The definition of "context" was left unresolved by the authors.

### EV-8. Fit the method to the design stage; do not usability-test early ideas to death
- **Do:** In early design, sketch several distinct alternatives and critique them ("getting the right design") before iterative testing of one ("getting the design right"). Keep early representations visibly rough. Before any test, ask whether it can give meaningful results at this stage. For radical concepts, assess usefulness and fit to real practice, not only ease of use. Evaluate running prototypes when missing features matter.
- **Why:** Inspection and think-aloud find costs, not benefits, which biases early choices toward the familiar (Greenberg 2008). Usability is not usefulness; many products succeed by being useful first (Greenberg 2008). Problems caused by missing features were much harder to find in heuristic evaluation of paper mockups than of running prototypes (Nielsen 1993).
- **Evidence:** [C] — (Greenberg 2008; Nielsen 1993).
- **Limits:** Greenberg 2008 is a position paper. The authors say usability evaluation remains right in many cases.

### EV-9. Measure effectiveness, efficiency and satisfaction separately
- **Do:** Collect all three ISO aspects. Report each one on its own. Do not combine them into one usability score, and do not infer one from another. Report the correlations among the measures you collected.
- **Why:** A meta-analysis of raw data from 73 studies found low correlations: effectiveness–efficiency r = .247, efficiency–satisfaction r = .196, effectiveness–satisfaction r = .164 (Hornbæk 2007). For complex tasks, time predicted only about 2% of answer quality (rs = −0.156) (Frøkjær 2000). Only 13% of 180 studies measured all three aspects (Hornbæk 2006). Composite scores hide which component drives a difference (Hornbæk 2006).
- **Evidence:** [A] — (Hornbæk 2007; Frøkjær 2000; Hornbæk 2006).
- **Limits:** Correlations come from research studies, mostly short lab sessions.

### EV-10. Measure outcome quality, not just completion and time
- **Do:** For complex tasks, grade the work product with an explicit rubric (for example a 5-point quality scale judged by an expert). Never use task time as a usability indicator unless effectiveness is measured or controlled. Distinguish errors made along the way from task-completion errors. Do not treat clicks or pages visited as quality unless tied to outcomes.
- **Why:** 22% of studies neither measured nor controlled effectiveness; expert assessment of outcomes appeared in only 4% (Hornbæk 2006). Complex effectiveness measures showed no correlation with efficiency (average r = −.039) (Hornbæk 2007). Errors along the way correlated with efficiency at .441, task-completion errors at only .155 (Hornbæk 2007).
- **Evidence:** [B] — (Hornbæk 2006; Hornbæk 2007; Frøkjær 2000).
- **Limits:** Frøkjær's grades came from a single grader in one information-retrieval domain.

### EV-11. Never treat preference or self-report as evidence of performance
- **Do:** Collect objective performance and subjective preference as separate measures. Do not use "users liked it" to claim "users did better with it", or the reverse. Do not replace measured time or accuracy with users' estimates of them. When performance is equal, preference is a valid tie-breaker.
- **Why:** Users' ratings of their own accuracy correlated r = .22 with actual accuracy, not different from zero (Hornbæk 2007). The divergence recurs across domains: longer lines were read faster but moderate lines were preferred (Dyson 2004; Ling 2006); preference and reading time correlated r = −0.13 for dyslexic readers (Rello 2013); users preferred overview+detail even when it was slower (Cockburn 2009); 29 of 32 preferred faceted search though it was slower (Yee 2003); students preferred a retrieval mode they did not perform best with (Frøkjær 2000); most users preferred aesthetic metaphor sites with objectively worse perceived usability and more reported problems (Hartmann 2008).
- **Evidence:** [A] — (Hornbæk 2007; Dyson 2004; Ling 2006; Rello 2013; Cockburn 2009; Yee 2003; Frøkjær 2000; Hartmann 2008).
- **Limits:** Satisfaction questionnaires and stated preference do correlate (mean r = .49, 10 studies) (Hornbæk 2007), so preference is meaningful as a satisfaction measure.

### EV-12. Use validated standardized questionnaires and report every item
- **Do:** Prefer an established, validated questionnaire over homegrown items. If you must write custom items, publish every item and check Cronbach's α ≥ .70. Avoid extreme-intensity wording. Do not measure a UX construct (for example enjoyment) with unpublished ad hoc items.
- **Why:** Standard questionnaires averaged α = .814 (range .73–.95); homegrown ones .736 (range .21–.92), with six below .70 (Hornbæk 2007). Only 7% of studies used standardized satisfaction questionnaires (Hornbæk 2006). 51% of UX questionnaire studies used self-made questionnaires without reporting items (Bargas-Avila 2011). Extreme item wording shifted SUS scores with d > 1.1 (cited in Sauro 2011).
- **Evidence:** [A] — (Hornbæk 2007; Hornbæk 2006; Bargas-Avila 2011; Sauro 2011).
- **Limits:** Validation contexts vary; check that the instrument fits the product type and language.

### EV-13. Administer and score SUS exactly as specified
- **Do:** Give SUS after the participant uses the system and before any debriefing. Require all 10 items; an item the person cannot answer gets the centre point (3). Score odd items (1, 3, 5, 7, 9) as position − 1 and even items (2, 4, 6, 8, 10) as 5 − position, sum, and multiply by 2.5 for a 0–100 score. Report only the composite. Check for reverse-coding errors (a negative α is a signal) and for contradictory answers. If you have no legacy SUS data to compare with, the all-positive version is acceptable. Compare SUS only across systems of the same kind.
  - The 10 standard items, rated 1 (strongly disagree) to 5 (strongly agree):
    1. I think that I would like to use this system frequently
    2. I found the system unnecessarily complex
    3. I thought the system was easy to use
    4. I think that I would need the support of a technical person to be able to use this system
    5. I found the various functions in this system were well integrated
    6. I thought there was too much inconsistency in this system
    7. I would imagine that most people would learn to use this system very quickly
    8. I found the system very cumbersome to use
    9. I felt very confident using the system
    10. I needed to learn a lot of things before I could get going with this system
  - All-positive wording for even items (Sauro 2011): 2 "I found the website to be simple"; 4 "I think that I could use the website without the support of a technical person"; 6 "I thought there was a lot of consistency in the website"; 8 "I found the website very intuitive"; 10 "I could use the website without having to learn anything new."
- **Why:** Brooke states individual item scores are not meaningful on their own (Brooke 1996). Standard and all-positive versions gave statistically equal means (73.4 vs 77.1; 52.2 vs 49.3) and similar reliability (α .91–.96). The alternating version caused real errors: 13% of standard questionnaires showed user mistakes, and 11% of 27 researcher datasets were miscoded (Sauro 2011).
- **Evidence:** [B] — (Brooke 1996; Sauro 2011).
- **Limits:** Brooke's original validation was thin (n = 20, two systems). Sauro's data are remote MTurk web tests. For non-native speakers, "awkward" has been suggested instead of "cumbersome" (cited in Sauro 2011).

### EV-14. Measure UX at several time points, in context, on more than one dimension
- **Do:** Measure expectations before use, experience during use, and reflection after use. Describe or deliberately vary the physical and social context. Assess more than one UX dimension and relate them to usability measures. Treat usability as a precondition for good UX, not a substitute. Check that any new UX construct is distinguishable from established ones.
- **Why:** Only 17% of 66 UX studies measured before, during and after; none were truly longitudinal; 33% left context uncontrolled and undescribed; 45% assessed a single dimension (Bargas-Avila 2011). 275 practitioners and researchers agreed UX depends on context (4.32/5) and internal state (4.47), can change after interaction ends (3.93), and that usability is a necessary precondition (3.70) (Law 2009).
- **Evidence:** [B] — (Bargas-Avila 2011; Law 2009).
- **Limits:** Law 2009 is a self-selected opinion survey. Bargas-Avila covers 2005–2009 research only.

### EV-15. Measure aesthetics with a multi-facet scale after real use, and control prototype polish
- **Do:** Use the 18-item VisAWI (Simplicity, Diversity, Colorfulness, Craftsmanship), not a single "is it beautiful?" item. Collect aesthetic ratings after participants complete real tasks if you want them separate from perceived usability. In comparative tests, match the visual polish of the prototypes or report the difference.
- **Why:** VisAWI facets have α .85–.89 (total .94) (Moshagen 2010). When sites were only viewed, Simplicity correlated .76 with perceived usability; after task use the total correlation fell to .31 (Moshagen 2010). An appealing version of a functionally identical phone produced faster completion (147.7 s vs 198.5 s) and fewer errors (2.0 vs 4.8) (Sonderegger 2010), so an ugly prototype understates both perception and performance.
- **Evidence:** [B] — (Moshagen 2010; Sonderegger 2010; Hartmann 2008).
- **Limits:** VisAWI was built on German-speaking samples and websites. The direction of the aesthetics effect on performance may reverse in leisure contexts (Sonderegger 2010).

### EV-16. Define learnability before you measure it, and use a method that can see it
- **Do:** State whether you measure initial learnability (performance in a first task or interval) or extended learnability (improvement over time, or reaching a target level). Specify the user profile (computer, interface, domain and similar-software experience). Pick metrics from the task, command, mental, subjective, documentation, usability or rule categories. For extended learnability, consider a coach-based question-suggestion protocol rather than think-aloud alone. Measure retention after a delay for systems used repeatedly.
- **Why:** 45 of 88 papers used "learnability" with no definition (Grossman 2009). The question-suggestion protocol exposed 7.55 issues per 15-minute task vs 2.8 for think-aloud, and only it surfaced transitions to efficient behaviour (Grossman 2009). Learning was measured in only 5 of 180 studies and retention in 1 (Hornbæk 2006).
- **Evidence:** [B] — (Grossman 2009; Hornbæk 2006).
- **Limits:** Grossman's study had 10 AutoCAD users and one coach; issues were coded by the experimenter.

### EV-17. Predict expert task time with the Keystroke-Level Model, within its error band
- **Do:** For routine expert tasks, write the method as operators and sum: K (keystroke, 0.08–1.20 s; 0.20 s for an average skilled typist), P (point, 1.10 s average), H (home hands, 0.40 s), M (mental preparation, 1.35 s), plus system response time the user waits for. Use it to compare alternatives before building. Do not treat differences smaller than about 21% for a single task as real.
- **Why:** Across 10 systems and 28 experts, KLM predicted unit-task time with 21% RMS error, and 5–6% over task sequences. Counting keystrokes only gave 49% error (Card 1980).
- **Evidence:** [A] — (Card 1980).
- **Limits:** KLM assumes error-free experts, routine tasks and fully specified methods. It does not predict novice performance, learning, error recovery or method choice. M placement is ambiguous.

### EV-18. Test optimized or unfamiliar layouts with repeated use, not first exposure
- **Do:** When a layout is optimized or departs from convention, measure performance over repeated trials and exclude or separately report first encounters. Plan sessions longer than a single short task when learning matters.
- **Why:** An optimized phone home screen showed no selection-time gain overall, but a significant gain once each app's first selection was excluded; most learning happened on the first selection (Todi 2016). Median study interaction time was 30 minutes, and only 13 of 180 studies exceeded 5 hours (Hornbæk 2006).
- **Evidence:** [B] — (Todi 2016; Hornbæk 2006).
- **Limits:** Todi 2016 had 20 users on one task type.

### EV-19. Evaluate animations against a static control with role-specific measures
- **Do:** Name the role the animation serves (keeping context, teaching, UX, data encoding, discourse). Compare against a static version using measures for that role: object tracking or revisitation for context roles, pre/post comprehension tests for teaching, perception accuracy for data encoding. Also ask about dizziness, distraction and boredom.
- **Why:** Animation has 23 distinct roles; its value over static small multiples is unclear and its strong perceptual draw can stop users seeing other elements (Chevalier 2016). Animated zoom helped users build spatial models but had no evidence of faster task time (Cockburn 2009).
- **Evidence:** [C] — (Chevalier 2016; Cockburn 2009).
- **Limits:** Chevalier is a taxonomy without effect data.

### EV-20. Evaluate nudges over time and after removal, and test for backfire
- **Do:** Measure nudge effects for longer than one day, check whether behaviour persists after the nudge is removed, and look for backfire (for example, social comparison raising usage among below-average users).
- **Why:** 66% of 74 studied nudges had a significant effect, but only 36% of studies lasted more than one day, 14% more than a month, and 14% checked persistence after removal. Reported failures include effects not sustained, backfire and reactance (Caraban 2019).
- **Evidence:** [B] — (Caraban 2019).
- **Limits:** Review of research prototypes, mostly short lab studies.

### EV-21. Evaluate choice architecture against a neutral baseline
- **Do:** For consent, cancellation and other choice screens, test the design against a neutral baseline (a regulation-specified version, a minimal version without the pattern, or a competitor design). Measure whether choices match stated preferences, whether users can correctly state what each option does, and whether they know all options exist. Check effects on vulnerable sub-groups. Treat a large shift in uptake relative to the baseline (for example more than double) as a red flag, and justify any threshold you set.
- **Why:** "Dark pattern" covers several distinct concerns; measurement should rest on an explicit lens (individual welfare, collective welfare, regulatory objectives, autonomy) and a comparison baseline (Mathur 2021).
- **Evidence:** [B] — (Mathur 2021).
- **Limits:** Scoping review; the authors call the case-study methods relatively unsophisticated, and welfare baselines are hard to define.

### EV-22. Weight accessibility evidence by population and sample size
- **Do:** Do not generalize findings from one disability group to another. Treat numeric thresholds from single accessibility studies as provisional. Evaluate with disabled participants directly; use proxies only with justification. Do not use nondisabled performance as the baseline disabled users must reach.
- **Why:** Of 506 accessibility papers, 43.5% focused on blind and low-vision users, only 7.1% covered more than one community, the median sample of disabled or older participants was 13, and 8.0% used proxies (Mack 2021).
- **Evidence:** [A] — (Mack 2021).
- **Limits:** Limited to CHI and ASSETS papers.

### EV-23. Validate priorities with users and frame scenarios like real use
- **Do:** Present evaluation tasks in a framing that matches the real context of use. Check priority rankings of problems or guidelines against user data rather than expert opinion alone.
- **Why:** Preference between an aesthetic and a plain design reversed with framing: the aesthetic version was preferred for children at home (86%), the plain menu for university students (85%) and the elderly (89%) (Hartmann 2008). In web forms, the two guidelines users found most important were ranked only 7th and 9th of 20 by experts (Seckler 2014).
- **Evidence:** [B] — (Hartmann 2008; Seckler 2014).
- **Limits:** Both are single studies with small samples.

## Choosing a method

| Stage | Question | Method | Notes |
|---|---|---|---|
| Concept / early | Which direction is worth pursuing? | Several parallel sketches plus design critique; scenarios | Avoid formal usability tests of sketches (EV-8) |
| Concept / radical idea | Is it useful, will people adopt it? | Field or ethnographic study, usefulness assessment | Ease-of-use tests miss usefulness (EV-8) |
| Spec / wireframe | What usability problems are likely? | Heuristic evaluation by 3–5 independent specialists | Treat findings as predictions (EV-1, EV-5, EV-6) |
| Spec / wireframe | Can a first-time user walk up and use this flow? | Cognitive walkthrough | (Nielsen 1994b) |
| Spec / wireframe | How long will experts take on routine tasks? | KLM estimate | ±21% per task; experts only (EV-17) |
| Spec / layout | Is visual clutter, alignment, color or search cost off? | Computational metrics compared with peer designs | Screening, not verdicts (see 12-automated-ui-review) |
| Running prototype | Which predicted problems are real? | Think-aloud test, tasks aimed at predicted problems | Size from λ (EV-2, EV-3) |
| Running prototype | How usable is it overall, compared with the last version? | Task test with separate effectiveness, efficiency, satisfaction; SUS | Report each separately (EV-9, EV-13) |
| Running prototype | Is it learnable over time? | Repeated sessions; question-suggestion protocol; retention test | Define initial vs extended (EV-16, EV-18) |
| Running prototype | How do people judge its looks? | VisAWI after task use | Match polish across variants (EV-15) |
| Released / field | How does experience change with use and context? | Before/during/after measures in real contexts; validated UX instruments | (EV-14) |
| Released / field | Does a nudge or choice design help users? | Long-term field test, removal phase, neutral baseline | (EV-20, EV-21) |
| Any | Does an animation help? | Static-control comparison with role-specific measures | (EV-19) |

## Numbers at a glance
| Parameter | Value | Grade | Source |
|---|---|---|---|
| Problems found by one evaluator | 20–51% (four experiments) | A | Nielsen 1990 |
| Mean problems found by one evaluator or user | 33%; λ = .31; mean N = 41 | A | Nielsen 1993 |
| Problem-discovery model | Found(i) = N(1 − (1 − λ)^i) | A | Nielsen 1993 |
| Evaluators for good coverage | 3–5 (about two thirds found with five) | A | Nielsen 1990 |
| Per-evaluator yield by expertise | 22% / 41% / 60% (none / usability / usability + domain) | B | Nielsen 1993 |
| Max benefit/cost per round (medium-large project) | 3.2 users; 4.4 evaluators | B | Nielsen 1993 |
| Novice HE effectiveness | ~0.21 (validity 0.38, thoroughness 0.55) | B | Hvannberg 2007 |
| Users for 80% discovery at p ≈ .22 | at least 7 | B | Hvannberg 2007 |
| Novice any-two evaluator agreement | 0.046 | B | Hvannberg 2007 |
| Problems explained by Nielsen's set (rating ≥ 3) | 82% | B | Nielsen 1994a |
| Effectiveness–efficiency correlation | r = .247 | A | Hornbæk 2007 |
| Efficiency–satisfaction correlation | r = .196 | A | Hornbæk 2007 |
| Effectiveness–satisfaction correlation | r = .164 | A | Hornbæk 2007 |
| Time vs quality, complex tasks | rs = −0.156 (~2% variance) | B | Frøkjær 2000 |
| Perceived vs actual accuracy | r = .22 (not different from zero) | B | Hornbæk 2007 |
| Questionnaire reliability, standard vs homegrown | α .814 vs .736 | A | Hornbæk 2007 |
| Studies measuring all three ISO aspects | 13% | A | Hornbæk 2006 |
| SUS score range | 0–100 (sum of contributions × 2.5) | B | Brooke 1996 |
| SUS user mistakes (standard version) | 13% | B | Sauro 2011 |
| SUS datasets miscoded by researchers | 11% (3 of 27) | B | Sauro 2011 |
| UX studies measuring before, during and after | 17% | B | Bargas-Avila 2011 |
| VisAWI | 18 items, 4 facets, total α = .94 | B | Moshagen 2010 |
| Aesthetics–usability correlation, viewing vs after use | .76 (Simplicity, viewing) vs .31 (total, after use) | B | Moshagen 2010 |
| Learnability issues found, question-suggestion vs think-aloud | 7.55 vs 2.8 per 15-min task | B | Grossman 2009 |
| KLM error | 21% RMS per unit task; 5–6% over sequences | A | Card 1980 |
| KLM operators | K 0.08–1.20 s; P 1.10 s; H 0.40 s; M 1.35 s | A | Card 1980 |
| Nudge studies lasting > 1 day / checking after removal | 36% / 14% | B | Caraban 2019 |
| Median disabled/older participants per accessibility paper | 13 | A | Mack 2021 |

## Common misreadings
- "Five users find 85% of problems." — Five is adequate only when the per-user discovery rate is near .3. At about .22, at least seven users are needed for 80% (Hvannberg 2007; Nielsen 1993). The model's real advice is to iterate small studies and estimate remaining problems.
- "One expert review is enough." — A single evaluator finds 20–51%; even specialists find under two thirds alone (Nielsen 1990; Nielsen 1993).
- "Heuristic evaluation replaces user testing." — Novice inspection was confirmed by testing only 38% of the time and caught 55% of real problems (Hvannberg 2007). Every source here recommends combining methods.
- "A single usability score captures usability." — The three ISO aspects correlate only .16–.25 (Hornbæk 2007).
- "Users preferred it, so it performs better." — Preference and performance diverge repeatedly (Dyson 2004; Ling 2006; Rello 2013; Yee 2003; Hartmann 2008).
- "SUS item 3 shows ease of use." — Brooke says individual SUS items are not meaningful on their own; only the composite is (Brooke 1996).
- "Alternating SUS items prevent response bias." — No measurable protection was found, while user mistakes and miscoding were real (Sauro 2011).
- "KLM predicts how long users take." — Only error-free experts on routine, fully specified tasks (Card 1980).
- "Beautiful means usable." — The link is strong when sites are only viewed and weakens after real use (Moshagen 2010).

## Review checklist
- [ ] EV-1: Does the evaluation plan use 3–5 independent evaluators and merge their lists?
- [ ] EV-2: Is testing planned as small iterative rounds, with remaining problems estimated from the data?
- [ ] EV-3: Is the number of users justified by an observed discovery rate rather than "five"?
- [ ] EV-4: Do evaluators include usability specialists, ideally with domain knowledge?
- [ ] EV-5: Were all nine heuristics applied, with explicit attention to error prevention and recognition over recall?
- [ ] EV-6: Are inspection findings labeled as predictions and checked with user testing?
- [ ] EV-7: Does each reported problem have context, cause, heuristic and severity?
- [ ] EV-8: Does the method suit the design stage (alternatives and critique early; testing later)?
- [ ] EV-9: Are effectiveness, efficiency and satisfaction measured and reported separately?
- [ ] EV-10: Is outcome quality measured or controlled when time is reported?
- [ ] EV-11: Are preference and performance claims kept separate?
- [ ] EV-12: Are questionnaires standardized, or are all custom items published with α ≥ .70?
- [ ] EV-13: Is SUS given before debriefing, scored correctly, reported only as a composite, and checked for miscoding?
- [ ] EV-14: Is UX measured at more than one time point and in a described context?
- [ ] EV-15: Are aesthetics measured with VisAWI after use, with prototype polish matched?
- [ ] EV-16: Is learnability defined (initial vs extended, user profile, metric) before it is measured?
- [ ] EV-17: Are expert-time predictions made with KLM and differences under ~21% treated as noise?
- [ ] EV-18: Are optimized or unconventional layouts tested beyond first exposure?
- [ ] EV-19: Are animations compared with a static control using role-specific measures?
- [ ] EV-20: Are nudges evaluated for longer than a day, after removal, and for backfire?
- [ ] EV-21: Are choice screens compared against a neutral baseline with comprehension checks?
- [ ] EV-22: Is accessibility evidence matched to the population it came from, with disabled participants involved?
- [ ] EV-23: Are scenarios framed like real use, and are priorities checked against user data?

## Sources
- Bargas-Avila, J. A., Hornbæk, K. (2011). *Old wine in new bottles or novel challenges? A critical analysis of empirical studies of user experience*. CHI '11. https://doi.org/10.1145/1978942.1979336
- Brooke, J. (1996). *SUS: a quick and dirty usability scale*. Usability Evaluation in Industry (Taylor & Francis).
- Caraban, A., Karapanos, E., Gonçalves, D., Campos, P. (2019). *23 ways to nudge: a review of technology-mediated nudging in HCI*. CHI '19. https://doi.org/10.1145/3290605.3300733
- Card, S. K., Moran, T. P., Newell, A. (1980). *The keystroke-level model for user performance time with interactive systems*. Communications of the ACM. https://doi.org/10.1145/358886.358895
- Chevalier, F., Riche, N. H., Plaisant, C., Chalbi, A., Hurter, C. (2016). *Animations 25 years later: new roles and opportunities*. AVI '16. https://doi.org/10.1145/2909132.2909255
- Cockburn, A., Karlson, A., Bederson, B. B. (2009). *A review of overview+detail, zooming, and focus+context interfaces*. ACM Computing Surveys. https://doi.org/10.1145/1456650.1456652
- Dyson, M. C. (2004). *How physical text layout affects reading from screen*. Behaviour & Information Technology. https://doi.org/10.1080/01449290410001715714
- Frøkjær, E., Hertzum, M., Hornbæk, K. (2000). *Measuring usability: are effectiveness, efficiency, and satisfaction really correlated?* CHI '00. https://doi.org/10.1145/332040.332455
- Greenberg, S., Buxton, B. (2008). *Usability evaluation considered harmful (some of the time)*. CHI '08. https://doi.org/10.1145/1357054.1357074
- Grossman, T., Fitzmaurice, G., Attar, R. (2009). *A survey of software learnability: metrics, methodologies and guidelines*. CHI '09. https://doi.org/10.1145/1518701.1518803
- Hartmann, J., Sutcliffe, A., De Angeli, A. (2008). *Towards a theory of user judgment of aesthetics and user interface quality*. ACM TOCHI. https://doi.org/10.1145/1460355.1460357
- Hornbæk, K. (2006). *Current practice in measuring usability*. IJHCS. https://doi.org/10.1016/j.ijhcs.2005.06.002
- Hornbæk, K., Law, E. L.-C. (2007). *Meta-analysis of correlations among usability measures*. CHI '07. https://doi.org/10.1145/1240624.1240722
- Hvannberg, E. T., Law, E. L.-C., Lárusdóttir, M. K. (2007). *Heuristic evaluation: comparing ways of finding and reporting usability problems*. Interacting with Computers. https://doi.org/10.1016/j.intcom.2006.10.001
- Law, E. L.-C., Roto, V., Hassenzahl, M., Vermeeren, A. P. O. S., Kort, J. (2009). *Understanding, scoping and defining user experience: a survey approach*. CHI '09. https://doi.org/10.1145/1518701.1518813
- Ling, J., van Schaik, P. (2006). *The influence of font type and line length on visual search and information retrieval in web pages*. IJHCS. https://doi.org/10.1016/j.ijhcs.2005.08.015
- Mack, K., McDonnell, E., Jain, D., Wang, L. L., Froehlich, J. E., Findlater, L. (2021). *What do we mean by "accessibility research"? A literature survey of CHI and ASSETS 1994–2019*. CHI '21. https://doi.org/10.1145/3411764.3445412
- Mathur, A., Kshirsagar, M., Mayer, J. (2021). *What makes a dark pattern... dark? Design attributes, normative considerations, and measurement methods*. CHI '21. https://doi.org/10.1145/3411764.3445610
- Molich, R., Nielsen, J. (1990). *Improving a human-computer dialogue*. Communications of the ACM. https://doi.org/10.1145/77481.77486
- Moshagen, M., Thielsch, M. T. (2010). *Facets of visual aesthetics*. IJHCS. https://doi.org/10.1016/j.ijhcs.2010.05.006
- Nielsen, J. (1994a). *Enhancing the explanatory power of usability heuristics*. CHI '94. https://doi.org/10.1145/191666.191729
- Nielsen, J. (1994b). *Usability inspection methods*. CHI '94 Companion. https://doi.org/10.1145/259963.260531
- Nielsen, J., Landauer, T. K. (1993). *A mathematical model of the finding of usability problems*. CHI '93. https://doi.org/10.1145/169059.169166
- Nielsen, J., Molich, R. (1990). *Heuristic evaluation of user interfaces*. CHI '90. https://doi.org/10.1145/97243.97281
- Rello, L., Baeza-Yates, R. (2013). *Good fonts for dyslexia*. ASSETS '13. https://doi.org/10.1145/2513383.2513447
- Sauro, J., Lewis, J. R. (2011). *When designing usability questionnaires, does it hurt to be positive?* CHI '11. https://doi.org/10.1145/1978942.1979266
- Seckler, M., Heinz, S., Bargas-Avila, J. A., Opwis, K., Tuch, A. N. (2014). *Designing usable web forms: empirical evaluation of web form improvement guidelines*. CHI '14. https://doi.org/10.1145/2556288.2557265
- Sonderegger, A., Sauer, J. (2010). *The influence of design aesthetics in usability testing*. Applied Ergonomics. https://doi.org/10.1016/j.apergo.2009.09.002
- Todi, K., Weir, D., Oulasvirta, A. (2016). *Sketchplore: sketch and explore with a layout optimiser*. DIS '16. https://doi.org/10.1145/2901790.2901817
- Yee, K.-P., Swearingen, K., Li, K., Hearst, M. (2003). *Faceted metadata for image search and browsing*. CHI '03. https://doi.org/10.1145/642611.642681
