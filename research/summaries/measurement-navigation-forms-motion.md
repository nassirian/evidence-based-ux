# Group E — Measurement, Information Architecture/Search, Forms, Motion

---

## 04__Bargas-Avila-Hornbaek-2011_Old-wine-in-new-bottles-UX — Old Wine in New Bottles or Novel Challenges? A Critical Analysis of Empirical Studies of User Experience (Javier A. Bargas-Avila, Kasper Hornbæk, 2011, CHI 2011)
**Type:** review (systematic, QUOROM-adapted)  ·  **Sample/method:** 1254 search hits (ACM DL, ISI WoK, ScienceDirect; 2005–2009) screened to 51 publications reporting 66 empirical UX studies; interrater kappa = 0.851 (phase 3) and 0.821 (phase 4).

**Core claim.** Empirical UX research has shifted products and use situations (toward leisure, art, open use) but mostly reuses traditional HCI methods, rarely studies context or anticipated use, and often relies on unvalidated, unreported self-made questionnaires.

**Key findings**
- Products: art 21%, mobile apps/phones 21%, audio/video/TV 15%, websites 12%; leisure use 64%, work 18%, mixed 18%.
- Use situations: open use 61% (n=40), controlled tasks 33% (n=22), user-initiated use 20% (n=13).
- Context: fixed setting 45% (n=30); uncontrolled and undescribed 33% (n=22); only 21% (n=14) described some parts of context.
- Dimensions assessed: "generic UX" 41%, affect/emotion 24%, enjoyment/fun 17%, aesthetics 15%, hedonic quality 14% (all via AttrakDiff or a modified version), engagement/flow 12%.
- 45% of studies assessed only one dimension; 71% two or fewer; only 6% four or more. 45% also measured usability; only half of those related usability to UX.
- Methods: 50% qualitative, 33% quantitative, 17% mixed (contrast: CHI 2006 was ~14% qualitative, ~65% quantitative per Barkhuus & Rode). Questionnaires used in 53%.
- Of the 35 questionnaire studies, 51% used self-developed questionnaires with items not reported; 29% listed items; 11% partially; AttrakDiff, Lavie & Tractinsky aesthetics, and SAM each 20%. 6 of 11 enjoyment studies used self-made items; no validated enjoyment scale was used.
- Timing of measurement: before 20%, during 58%, after 70%, imagined 18%; only 17% measured before, during and after. No truly longitudinal (months/years) studies.
- New constructs (enchantment, engagement, tangible magic, relevance) are proposed without relating them to established constructs ("dimensionality explosion"); new methods (probes, collages, drawings) are rarely validated against existing methods.

**Design rules derivable**
- When measuring UX, use validated instruments (e.g., AttrakDiff, Lavie & Tractinsky, SAM) rather than ad hoc items; if custom items are necessary, publish every item. [strong]
- Measure UX at more than one time point (before/expectations, during, after), not only post-use. [moderate]
- Describe or deliberately vary the physical and social context of use; do not assume lab results transfer to context-dependent experience. [moderate]
- Assess more than one UX dimension and report how they relate to each other and to usability metrics. [moderate]
- Before adopting a new UX construct or constructive method (probes, collages), check that it is distinguishable from and validated against established constructs/methods. [moderate]
- Do not use instrumental vs. non-instrumental goals as the dividing line between "usability" and "UX" tasks; users invent goals even in open use. [weak]

**Boundary conditions & caveats.** Sample limited to papers using the exact phrase "user experience" and citing listed key UX authors; excludes practitioner work and design-only research; 2005–2009 window.


---

## 04__Brooke-1996_SUS-quick-and-dirty-usability-scale — SUS: A Quick and Dirty Usability Scale (John Brooke, 1996, book chapter in *Usability Evaluation in Industry*; scale © Digital Equipment Corporation 1986)
**Type:** tool  ·  **Sample/method:** 50 candidate items rated by 20 office-systems staff (secretary to systems programmer) on two systems judged extremely easy vs. almost impossible to use; most extreme-response items retained.

**Core claim.** Usability is context-specific, but a short, reliable, global subjective scale (SUS) enables low-cost comparison across versions and systems.

**Key findings**
- Selected items had intercorrelations of ±0.7 to ±0.9; half worded so the common response is strong agreement, half strong disagreement, to force respondents to read each item.
- Motivation: after 20–60 minute unassisted evaluation sessions, users would not complete questionnaires of more than 25 questions.
- SUS "correlates well" with other subjective measures (e.g., SUMI general usability subscale; personal communication) — no coefficient reported.
- **The 10 items** (5-point scale, 1 = strongly disagree … 5 = strongly agree):
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
- **Administration:** after the respondent uses the system, before any debriefing; record immediate responses; all items must be answered; if unable to answer, mark the centre point.
- **Scoring:** each item contributes 0–4. Items 1, 3, 5, 7, 9: contribution = scale position − 1. Items 2, 4, 6, 8, 10: contribution = 5 − scale position. Sum contributions and multiply by 2.5 → SUS score 0–100. Worked example: sum 22 × 2.5 = 55.
- Individual item scores are "not meaningful on their own"; only the composite is.

**Design rules derivable**
- For a quick global usability benchmark, administer SUS immediately after task use and before debriefing. [moderate]
- Report only the composite 0–100 score; never interpret single SUS items. [strong — per author's scoring rule]
- Reverse-score even items (5 − position) before summing; verify coding. [strong]
- Keep post-session questionnaires short (well under 25 questions) when users are fatigued or frustrated. [weak]
- Compare SUS across versions/competitors of the same kind of system; avoid cross-purpose comparisons ("apples and oranges"). [moderate]

**Boundary conditions & caveats.** Original validation is thin (n=20, two systems; no reliability coefficient reported in this text); "quick and dirty" by design; acknowledgement of source required for published use.


---

## 04__Frokjaer-2000_Effectiveness-efficiency-satisfaction-correlated — Measuring Usability: Are Effectiveness, Efficiency, and Satisfaction Really Correlated? (Erik Frøkjær, Morten Hertzum, Kasper Hornbæk, 2000, CHI 2000)
**Type:** empirical (reanalysis) + literature analysis  ·  **Sample/method:** 87 CS students solved 20 information-retrieval tasks (X Window programming docs) using five retrieval modes (BROWSE, LOGICAL, VENN, ALL, PAPER); 1555 graded answers from 83 subjects (648 hours); plus review of 19 complex-task studies in CHI '97–'99.

**Core claim.** For complex tasks, effectiveness (solution quality) and efficiency (time) are at most negligibly correlated, so all three ISO aspects must be measured independently.

**Key findings**
- Time vs. grade: Spearman rs = −0.156 (p < 0.001), rs² = 0.024 — only ~2% of grade variance predicted by time ("negligible"). Partial correlation controlling task and mode: rs = −0.170 (p < 0.001).
- Contingency χ²[16, N=1555] = 47.81, p < 0.001; the 20% fastest tasks received significantly higher grades than the 60% slowest.
- By mode: BROWSE rs = −0.150 (p = .008), LOGICAL −0.089 (p = .119), VENN −0.107 (p = .062), ALL −0.128 (p = .030), PAPER −0.265 (p = .001); rs² between 1.6% and 7.0% where significant. The two query-formulation modes showed no significant correlation.
- 85% of tasks showed no time–grade correlation; tasks 11 (rs = −0.308), 13 (−0.387) and 17 (−0.232) did (5–15% variance).
- Only 12 subjects (14%) showed a significant correlation (rs −0.758 to −0.453); for 86% time did not predict grade.
- Satisfaction: subjects overwhelmingly preferred ALL, not the mode they performed best with.
- CHI '97–'99: of 19 complex-task studies, 8 (42%) measured all three aspects, 7 measured two, 4 one — 11 of 19 relied on untested correlation assumptions. Example: Gutwin & Greenberg — all 38 participants preferred an interface whose time/communication benefits were only partial.

**Design rules derivable (evaluation)**
- In usability tests of complex tasks, measure effectiveness, efficiency and satisfaction separately; never infer one from another. [strong]
- Do not use task time as a usability indicator for complex tasks unless effectiveness (outcome quality) is controlled. [strong]
- Develop an explicit, graded outcome-quality measure (e.g., a 5-point quality rubric judged by an expert) for complex tasks. [moderate]
- Do not treat user preference as a proxy for performance; collect both. [moderate]
- Choose critical measures per domain and context of use; general correlation findings cannot tell you in advance which measures matter. [moderate]

**Boundary conditions & caveats.** Single experiment, IR domain, students, unsupervised 10-day setting; quality graded by one author; satisfaction data only as preference.


---

## 04__Greenberg-Buxton-2008_Usability-evaluation-considered-harmful — Usability Evaluation Considered Harmful (Some of the Time) (Saul Greenberg, Bill Buxton, 2008, CHI 2008)
**Type:** theory / position essay  ·  **Sample/method:** argument from experience, CHI publication trends (citing Barkhuus & Rode), and historical innovation cases (Marconi radio, automobile, Memex, Sketchpad, NLS, modern social web).

**Core claim.** Usability evaluation applied "by rule rather than by thought" can kill early or radical ideas, give weak science, and miss usefulness and cultural adoption; method choice must follow the question and design stage.

**Key findings (as reported/cited)**
- CHI evaluations are dominated by quantitative empirical usability evaluations (~70%) followed by qualitative ones (~25%); papers about methods have nearly disappeared (Barkhuus & Rode).
- Pinelle & Gutwin (CSCW 1990–1998): almost 1/3 of systems not formally evaluated; only about 1/4 evaluated in a real-world setting.
- Typical HCI validations are "existence proofs" (confirmatory), i.e., weak science; replications—scientifically stronger—are rarely valued or published.
- Common usability methods (think-aloud, walkthroughs, heuristic evaluation) find problems (costs) but not benefits, biasing early decisions toward the familiar ("local hill climbing").
- Usability ≠ usefulness: many products succeed by being useful/fashionable despite poor usability; usability often arrives after usefulness.

**Design rules derivable (process/evaluation)**
- In early design, generate and critique multiple parallel sketches ("getting the right design") before iterative usability testing ("getting the design right"). [moderate]
- Do not usability-test sketches as if they were prototypes; keep early representations visibly rough. [moderate]
- Before running a usability evaluation, ask whether it will yield meaningful results at this stage; if not, use design critique, rationale, scenarios, case studies or cultural probes. [moderate]
- For radical innovations, evaluate usefulness and cultural fit (field/ethnographic methods), not just ease of use with today's tasks. [weak]
- For modest variations of established designs, prefer risky (refutation-seeking) hypothesis tests over existence proofs, and publish data/software to enable replication. [moderate]
- Combine empirical, non-empirical and reflective methods to triangulate. [weak]

**Boundary conditions & caveats.** Opinion essay; no new data; the authors stress usability evaluation remains appropriate "in many, but not all cases" and should not be dropped.


---

## 04__Hornbaek-2006_Current-practice-in-measuring-usability — Current Practice in Measuring Usability: Challenges to Usability Studies and Research (Kasper Hornbæk, 2006, International Journal of Human-Computer Studies 64, 79–102)
**Type:** review (systematic)  ·  **Sample/method:** 180 studies (from 587 candidates) in TOCHI, BIT, HCI, IJHCS (2000–2001), CHI (2001–2002), INTERACT (1999, 2001); measures classified by ISO 9241-11; inclusion kappa .8/.9; classification agreement 89.7%.

**Core claim.** Usability measurement practice is often invalid or incomplete: outcomes go unmeasured, satisfaction measures are in disarray, learning/retention and long-term use are ignored, and subjective and objective measures are conflated.

**Key findings**
- Effectiveness: 65% of studies used any effectiveness measure; 22% neither measured nor controlled it; quality-of-outcome measures in 16%; expert assessment of outcomes in only 4%; 13% controlled effectiveness.
- Efficiency: task completion time 57%; any efficiency measure 74%; usage-pattern measures (clicks, pages visited) 24%; learning measured in only 5 studies; retention in 1; subjectively experienced time in 1.
- Median interaction time 30 min (mean 76.7, SD 239.4); only 13 studies exceeded 5 hours.
- Satisfaction: 62% used any; standardized questionnaires 7% (12 studies; QUIS 4%); of 112 satisfaction studies, 29 (26%) built on prior work and 10 reported validation/reliability; 93% used exclusively post-use questionnaires; 15 of 37 ease-of-use studies did not give item wording.
- 92% measured at least one of time/accuracy/satisfaction; only 13% measured all three.
- Combined scores (e.g., quality/time) can mask whether differences come from just one component.

**Design rules derivable (evaluation)**
- Always measure or control outcome quality (effectiveness); expert-graded work products are an underused, strong option. [strong]
- Use validated standardized satisfaction questionnaires instead of reinventing ease-of-use items; report all items. [strong]
- Report effectiveness, efficiency and satisfaction separately; avoid composite usability scores. [moderate]
- Do not treat usage patterns (clicks, pages visited) as quality-in-use unless tied to outcomes, time, or satisfaction. [moderate]
- Keep subjective and objective measures distinct (e.g., perceived learnability ≠ time-to-proficiency); consider subjective duration alongside objective time. [moderate]
- For systems used repeatedly, measure learnability (time to reach proficiency) and retention after a delay; study use beyond a single ~30-minute session. [moderate]
- Include macro tasks (hours–months, cognitively/socially complex) where relevant, not only micro tasks. [moderate]
- Supplement post-use questionnaires with during-use measures (e.g., physiological, reflex responses). [weak]

**Boundary conditions & caveats.** Research papers only (not industry practice); does not model how domain/task should drive measure choice; time window 1999–2002.


---

## 04__Hornbaek-Law-2007_Meta-analysis-usability-measures — Meta-Analysis of Correlations Among Usability Measures (Kasper Hornbæk, Effie Lai-Chong Law, 2007, CHI 2007)
**Type:** meta-analysis (raw data)  ·  **Sample/method:** raw datasets from 73 studies (2090 papers → 386 candidates; 48% author response; 92 datasets received, 19 discarded) across 8 HCI venues 2003–2005; Fisher r-to-z, weighted by n−3; >2000 participants in total.

**Core claim.** Correlations among effectiveness, efficiency and satisfaction are positive but low, so no single measure (or single usability score) captures usability.

**Key findings (correlations, Pearson r ± 95% CI)**
- Effectiveness–efficiency: **.247 ± .059** (54 studies; 87% positive).
- Efficiency–satisfaction: **.196 ± .064** (45 studies; 81% positive).
- Effectiveness–satisfaction: **.164 ± .062** (39 studies; 86% positive).
- Prototypical measures: errors–time .316 (±.070); errors–satisfaction .196 (±.184); time–satisfaction .145 (±.129); errors–preference .243 (±.158); time–preference .309 (±.146); satisfaction–preference .245 (±.281, only two studies).
- Errors-along-the-way vs. efficiency .441 ± .125 (14 studies); task-completion errors vs. efficiency .155 ± .08 (23 studies). Studies with complex effectiveness measures (quality, expert assessment; 6 studies) showed no significant correlation with efficiency; reported average with complex measures r = −.039.
- Task complexity did not moderate correlations (Qs = 0.58, 0.79, 1.89; all ps > .25).
- Perceived vs. objective: users' assessment of own effectiveness vs. actual r = .22 (range −.23 to .80; 6 studies), not different from zero; perceived-time items vs. actual time described as indistinguishable from zero ("on average r = .30 across five studies").
- Satisfaction questionnaires vs. stated preference: mean r = .49 (10 studies); task-level vs. aggregated satisfaction rs .38–.70 (3 studies).
- Reliability: standard questionnaires mean Cronbach α .814 (range .73–.95, n=16); homegrown .736 (range .21–.92, n=20); six homegrown fell below .70. Only 12 of 106 satisfaction measures (11%) were standard questionnaires.
- Illustrations: error rates ~18% on non-preferred vs. ~13% on preferred interfaces; preferred interface ~20% faster.
- Correlations about half those reported by Sauro & Kindlund (r ≈ .5), weakening the case for a single usability score.

**Design rules derivable (evaluation)**
- Collect effectiveness, efficiency and satisfaction measures separately; do not collapse into one score. [strong]
- Use standardized satisfaction questionnaires (higher, more stable reliability) over homegrown ones; check α ≥ .70 for any custom scale. [strong]
- Do not substitute users' self-reports of speed or accuracy for objective time or accuracy measures. [moderate]
- Include complex outcome measures (quality, expert assessment) when feasible—they add information not captured by time. [moderate]
- Report correlations among the usability measures you collect. [moderate]
- Distinguish errors-along-the-way from task-completion errors when reporting effectiveness. [weak]

**Boundary conditions & caveats.** Barebones meta-analysis; relies on ISO classification; 19% of candidate studies; unexplained task- vs. interface-level aggregation differences; no predictive theory of relations.


---

## 04__Law-2009_Understanding-scoping-defining-UX — Understanding, Scoping and Defining User eXperience: A Survey Approach (Effie L-C. Law, Virpi Roto, Marc Hassenzahl, Arnold P.O.S. Vermeeren, Joke Kort, 2009, CHI 2009)
**Type:** empirical (survey)  ·  **Sample/method:** online survey, 275 researchers/practitioners from 25 countries; agreement with 23 UX statements (5-point) and choice among 5 UX definitions (n=210).

**Core claim.** The community broadly agrees UX is dynamic, context-dependent and subjective, best scoped as an individual's experience of interacting with something that has a user interface; the draft ISO definition fits but needs clarification.

**Key findings**
- Highest agreement (mean): internal state (needs, motivations) affects experience 4.47; UX depends on context 4.32; prior exposure shapes UX 4.25; designing for UX must be grounded in UCD 4.11; UX can change after interaction stops 3.93.
- Lowest: UX best viewed as marketing 1.90; UX = emotional attachment 2.27; UX already covered by existing engineering approaches 2.56; each interaction is a unique, non-comparable experience 2.71.
- "UX should be assessed while interacting" 3.87 vs. "after interacting" 3.33; "usability is a necessary precondition for good UX" 3.70; "UX can be quantified" 3.50; "must be approached qualitatively" 3.59.
- "Imagined use can result in real experiences": 14% "I don't understand". Most controversial: "only an individual can have an experience".
- Only 12 of 230 background × statement tests (5%) significant; more UX/UCD experience → less agreement that UX is subjective (r = −.20/−.21) and less need for a standard definition (r = −.18). Finland vs. USA differed on subjectivity, emotional attachment, and qualitative approach.
- Definition preference: D2 (internal state + system + context) 31%, D1 (company/all aspects) 22%, D3 21%, D5 17%, D4 9%.
- Draft ISO definition: "A person's perceptions and responses that result from the use or anticipated use of a product, system or service."

**Design rules derivable**
- Evaluate UX during interaction, and also later, because experience changes after use and is shaped by prior exposure. [moderate]
- Treat context of use and users' internal state (needs, motivations, expectations) as required inputs to any UX evaluation. [moderate]
- Ground UX work in user-centred design practice; consider usability a precondition rather than a substitute. [moderate]
- When evaluating anticipated use (pre-product), make the context concrete with vivid use cases. [weak]
- Scope "UX" to interaction through a user interface; treat brand and face-to-face service experience as separate but influencing factors. [weak]

**Boundary conditions & caveats.** Self-selected, not representative; authors note quantitative results are a "rough picture"; statements written by the authors.


---

## 04__Sauro-Lewis-2011_Positive-usability-questionnaires — When Designing Usability Questionnaires, Does It Hurt to Be Positive? (Jeff Sauro, James R. Lewis, 2011, CHI 2011)
**Type:** empirical (two experiments) + data audit  ·  **Sample/method:** Mechanical Turk users on 11 websites; Exp. 1 n=161 (51 standard SUS, 110 all-positive; asynchronous); Exp. 2 n=213 (107/106; simultaneous, randomized); review of 27 SUS datasets for miscoding.

**Core claim.** Alternating positive/negative items buys no measurable protection against response bias but causes user mistakes and researcher miscoding; an all-positive SUS yields similar scores.

**Key findings**
- SUS means: Exp. 1 standard 73.4 (SD 17.6) vs. positive 77.1 (SD 17.1), p > .20; Exp. 2 standard 52.2 (SD 23.3) vs. positive 49.3 (SD 26.8), p > .39.
- Reliability: Cronbach α .91 vs. .92 (Exp. 1); .92 vs. .96 (Exp. 2).
- Acquiescence (agreements on odd items): Exp. 2 1.64 vs. 1.66 (p > .95); Exp. 1 3.2 vs. 3.69 (marginal, p > .07). Extreme responses: Exp. 2 1.68 vs. 1.36 (p > .30); Exp. 1 3.45 vs. 4.09 (p > .21).
- User mistakes (≥3 internal inconsistencies): 21 of 158 standard questionnaires = 13.3% (95% CI 8.8–19.5%). Inconsistent answers to items 2 and 3: 35.3% (Exp. 1), 49.5% (Exp. 2).
- Researcher miscoding: 3 of 27 SUS datasets = 11% (95% CI 3.0–28.8%).
- Prior work cited: extreme item wording shifted SUS significantly (Cohen d > 1.1); Bangor et al. (>2300 SUS) found small item biases (mean abs. deviation .19, max .47 on item 4); Finstad recommends "awkward" instead of "cumbersome" for non-native speakers.
- All-positive item wordings tested (even items): 2 "I found the website to be simple"; 4 "I think that I could use the website without the support of a technical person"; 6 "I thought there was a lot of consistency in the website"; 8 "I found the website very intuitive"; 10 "I could use the website without having to learn anything new."

**Design rules derivable (evaluation)**
- When designing new usability questionnaires, avoid negatively worded items. [moderate]
- If using standard SUS, verify reverse-coding of even items (e.g., a negative Cronbach's α signals miscoding). [strong]
- In moderated tests, add a procedural check (e.g., at debrief) for contradictory SUS answers. [moderate]
- Without legacy SUS benchmarks, the all-positive SUS can be used; scores are comparable. [moderate]
- Avoid extreme-intensity wording in questionnaire items. [moderate]

**Boundary conditions & caveats.** Remote unmoderated web tests with MTurk US respondents; Exp. 1 had an unexplained odd-item difference likely due to asynchronous collection; factor structures unstable at these sample sizes.


---

## 07__Bates-1989_Berrypicking — The Design of Browsing and Berrypicking Techniques for the Online Search Interface (Marcia J. Bates, 1989, Online Review 13(5), 407–424)
**Type:** theory (model + design proposals)  ·  **Sample/method:** conceptual model grounded in reviews of manual information-seeking research (Ellis, Stoan, Kuhlthau, Stenstrom & McBride, etc.).

**Core claim.** Real searches are evolving and gather information bit by bit across many sources and techniques ("berrypicking"), unlike the classic single-query/single-result-set IR model; interfaces should support that full range of moves.

**Key findings / claims**
- Berrypicking model: queries evolve; information is gathered in bits rather than one best set; searchers use many techniques and many sources.
- Six common techniques: footnote chasing (backward chaining), citation searching (forward chaining), journal run, area scanning (browsing collocated items), subject search in bibliographies/A&I services, author searching.
- Stenstrom & McBride: over 87% of social-science faculty used abstracting journals only occasionally, rarely, or never; 69% relied on footnote chasing.
- Area scanning is the "quintessential" manual browsing; its value is attributed to serendipitous juxtaposition and quick gestalt sense from full text.
- Browsing is part of directed searching ("semi-directed"), not a separate casual behaviour.

**Design rules derivable**
- Support evolving queries: let users refine, redirect, and pick results incrementally without losing earlier finds. [moderate]
- Provide multiple search strategies in one system (citation links both directions, author pages, browsing within a source, subject/category browsing) with single-step access to each. [moderate]
- Allow jumps between text and references in any direction indefinitely without returning to a start point. [weak]
- Offer browsing of classification/category structures at several levels of generality ("jump the rails"). [weak]
- Provide an easy "collect/flag" temporary store for items gathered across the session. [weak]
- Show substantial amounts of information at once and allow rapid scanning across large text; offer random "snapshots" (2–3 paragraphs) of full text. [weak]
- Use a familiar physical metaphor (e.g., library layout) as an orientation device at the start of a search. [weak]

**Boundary conditions & caveats.** Pre-web, largely academic/bibliographic context; proposals not empirically tested in the paper; spatial-metaphor benefits contested (Jones & Dumais).


---

## 07__Cockburn-2009_Overview-detail-zooming-focus-context — A Review of Overview+Detail, Zooming, and Focus+Context Interfaces (Andy Cockburn, Amy Karlson, Benjamin B. Bederson, 2008 [file dated 2009], ACM Computing Surveys 41(1), Article 2)
**Type:** review  ·  **Sample/method:** narrative review of systems and empirical evaluations, organized into overview+detail (spatial), zooming (temporal), focus+context (seamless/distortion), and cue-based techniques; low-level (target acquisition) and high-level (comprehension/search) studies tabulated.

**Core claim.** Supporting both focused and contextual views improves interaction over single-view software, but no approach is universally best; effectiveness depends strongly on task.

**Key findings**
- Zoom animation: transition durations between **0.3 and 1.0 second** are appropriate depending on domain and distance; animated zoom helps users form spatial models but no evidence it improves task time.
- Overview+detail: often preferred; for document comprehension no alternative has been found more effective; costs are screen space and the effort/time of integrating views. Hornbæk et al. 2002: overview slowed map tasks when semantic zooming was on, yet users preferred it; recall was better without overview.
- Reading (Hornbæk & Frøkjær 2003): fisheye fastest reading but lowest comprehension; O+D highest comprehension, slowest reading, most preferred.
- Pietriga et al. 2007 (multiscale search): O+D with pan/zoom fastest, then DragMag, then fisheye, pan-and-zoom last.
- Plumlee & Ware 2002: zooming beats multiple O+D views when visual-memory demands are low; inverse when high.
- Baudisch et al. 2002: mixed-resolution focus+context screen faster (by up to 56%) than O+D and zooming; split-attention costs hurt O+D in a driving simulation.
- Distortion/fisheye: moving-target problem harms acquisition (Mac OS X Dock); fisheye menus slower than hierarchical menus; expanding targets (even after 90% of movement) speed acquisition; fisheyes impair relative spatial judgment; grid lines aid interpretation. Fisheye benefits in steering tasks, source-code navigation (DOI-based), complex calendar tasks.
- Pan/zoom control: concurrent unimanual pan+zoom (e.g., OrthoZoom, pressure "zliding") outperforms bimanual or serial control and speed-dependent automatic zooming.
- Space-filling thumbnails (stable page locations) outperform panning/zooming/O+D for revisitation.
- Hidden zoom shortcuts are rarely discovered (1 of 6 experienced Word users knew Ctrl+scroll zoom); view changes are usually not undoable.
- Cue-based highlighting/grouping of search matches yields performance benefits.

**Design rules derivable**
- Let users browse the overview without changing the detail view, but reflect every detail-view change immediately in the overview. [moderate]
- Make overviews toggleable to recover screen space. [weak]
- Animate zoom transitions at 0.3–1.0 s, tuned to distance and domain. [moderate]
- Provide concurrent, one-handed pan+zoom control rather than serial or bimanual control. [moderate]
- Give zoom controls visible affordances and an obvious reverse action; offer region-zoom-in cautiously because it has no zoom-out equivalent. [moderate]
- Prevent "desert fog": mark regions that contain content or make empty regions unreachable. [weak]
- Avoid distortion (fisheye) where users must acquire targets or judge distances/directions; if used, stabilize targets (lock, speed-coupled flattening, or expand only after selection) and add grid lines. [strong]
- Prefer overview+detail for document comprehension; prefer focus+context/wide displays for dynamic tasks where switching views is costly. [moderate]
- Keep item positions spatially stable to exploit spatial memory for revisitation. [moderate]
- Highlight or group items matching search criteria (cue-based). [moderate]

**Boundary conditions & caveats.** Narrative review; many studies with small samples and task-specific results; preferences sometimes diverge from performance; authors explicitly say current research "fails to provide clear guidelines."


---

## 07__Shneiderman-1996_The-eyes-have-it — The Eyes Have It: A Task by Data Type Taxonomy for Information Visualizations (Ben Shneiderman, 1996, Proc. IEEE Visual Languages '96; UMD CS-TR-3665)
**Type:** theory (taxonomy) with cited empirical support  ·  **Sample/method:** conceptual taxonomy of 7 data types × 7 tasks, illustrated by research prototypes; cites small usability experiments.

**Core claim.** "Overview first, zoom and filter, then details-on-demand" is a useful starting point; full visualization tools should support seven tasks across seven data types.

**Key findings**
- Data types: 1-dimensional, 2-dimensional, 3-dimensional, temporal, multi-dimensional, tree, network.
- Tasks: Overview, Zoom, Filter, Details-on-demand, Relate, History (undo/replay/refinement), Extract (save sub-collections and query parameters).
- Dynamic queries: sliders/buttons coupled to display updates in **less than 100 milliseconds**, even with tens of thousands of items; benefits include no error messages and encouraged exploration.
- Dynamic queries vs. form fill-in (chemical table, 18 students, within-subjects): faster performance and lower error rates.
- Filter-flow graphical Boolean queries vs. textual (20 subjects): significantly better comprehension and composition; preferred by all 20.
- Overview+detail field-of-view box supports zoom factors of 3 to 30; fisheye zoom factors in prototypes limited to about 5.
- Complex treemaps take users 10–20 minutes to accommodate to.
- Buttons are suitable for attribute values when cardinality is small (say less than ten). Most prototypes fail to support History and Extract.

**Design rules derivable**
- Structure data-exploration UIs as: overview of the whole collection → zoom and filter → details on demand for selected items. [moderate]
- Update displays within 100 ms of filter-control changes. [moderate]
- Use direct-manipulation filters (range sliders, alphasliders, buttons for <~10 values) rather than typed Boolean queries for exploratory filtering. [moderate]
- Provide history (undo, replay, progressive refinement) and extraction (export results and query settings). [weak]
- Use smooth zooming to preserve users' sense of position and context. [weak]
- Offer "relate" actions: select an item attribute to show related items. [weak]
- Expect a learning period for unfamiliar visualizations (e.g., treemaps, parallel coordinates). [weak]

**Boundary conditions & caveats.** Largely a position/taxonomy paper; the mantra is explicitly "only a starting point"; empirical support cited is from small studies.


---

## 07__Yee-Hearst-2003_Faceted-metadata-search-browsing — Faceted Metadata for Image Search and Browsing (Ka-Ping Yee, Kirsten Swearingen, Kevin Li, Marti Hearst, 2003, CHI 2003)
**Type:** empirical (within-subjects usability study) + design  ·  **Sample/method:** 32 art-history students, ~35,000 Fine Arts Museum of San Francisco images; faceted category interface (FC) vs. Google-like baseline with category links; 2 structured + 2 unstructured tasks per interface; 9-point Likert scales.

**Core claim.** Hierarchical faceted navigation with query previews is strongly preferred over keyword search for exploratory image search, despite being slower and unfamiliar.

**Key findings**
- Overall preference: 29 of 32 for FC (abstract: 90%; text: 91%); "helped you learn more" 31 vs. 1 (abstract: 97%); "more useful for usual tasks" 28 vs. 4 (88%); "easiest to use" 23 vs. 8 (abstract: 72%); "most flexible" 24 vs. 6 (abstract: 75%); "more likely to result in dead-ends" Baseline 28 vs. FC 3.
- For a simple single-facet task (find roses), preference split ~50/50 (15 Baseline, 16 FC); for time-period and multi-attribute tasks FC preferred 30–2 and 29–1.
- Recall success, "find all" task: aquatints 57% (Baseline) vs. 81% (FC); woodcuts 21% vs. 77%; Baseline failures partly from not querying singular and plural forms.
- Empty results during structured tasks: 82 (Baseline) vs. 26 (FC).
- Users felt more confident they found all relevant images and more satisfied with results with FC (p < .05 to p < .001).
- FC was slower: per-step processing 3.7 s vs. 0.3 s (Task 2) and 4.3 s vs. 0.37 s (Task 3); time on task longer (12 min 6 s vs. 9 min 30 s); more than half commented negatively on speed.
- Multi-facet queries: 19% of the time in unstructured tasks, 45% in structured tasks.
- FC rated 7.6 for "simple" and not significantly more "overwhelming" than Baseline. Order effect: seeing FC first lowered Baseline ratings.
- Design features: facet + top-level categories on the opening page; query previews (counts) on every link; never show links that lead to zero results; per-facet hue coding; group-by any facet; keyword search integrated with facets plus a disambiguation panel; endgame shows item's terms in their hierarchies for lateral navigation.

**Design rules derivable**
- For exploratory search over richly described collections, provide hierarchical faceted navigation combined with keyword search. [strong — for preference/recall; weaker for speed]
- Show a result count (query preview) next to every refinement option. [moderate]
- Never display a refinement link that would yield zero results. [moderate]
- On the start page, expose each facet with its top-level categories to give an overview and many entry points. [moderate]
- Let users group/sort results by any facet and refine by adding terms from multiple facets. [moderate]
- On item detail pages, show the item's metadata terms as clickable links to pivot to related results. [moderate]
- Keep refinement latency low; multi-second delays provoke frustration and abandonment intent. [moderate]
- For simple known-item queries, a plain keyword box may suffice; do not force facets. [weak]

**Boundary conditions & caveats.** Domain experts with a well-annotated collection; single lab study; FC slower because of implementation; some metadata misfiled; time limits differed (3 extra minutes for FC on Task 2).


---

## 08__Seckler-2014_Designing-usable-web-forms — Designing Usable Web Forms – Empirical Evaluation of Web Form Improvement Guidelines (Mirjam Seckler, Silvia Heinz, Javier A. Bargas-Avila, Klaus Opwis, Alexandre N. Tuch, 2014, CHI 2014)
**Type:** empirical (between-subjects lab + eye tracking) evaluating a guideline set  ·  **Sample/method:** N = 65 (32 original, 33 improved); three real German-language news registration forms (Spiegel, NZZ, Sueddeutsche) rebuilt original vs. improved per 20 guidelines (Bargas-Avila et al.); measures: submissions, errors, time, fixations/saccades, SUS, ASQ, FUS, NASA-TLX, interviews; 14 HCI experts rated guideline importance (α = .90).

**Core claim.** Applying the 20 guidelines holistically to real high-traffic forms improves first-try success, speed, eye-movement efficiency and satisfaction.

**The 20 guidelines (near-verbatim) with expert severity rating M (range, 1–5)**
*Form content*
1. Let people answer in formats familiar from common situations; keep questions in an intuitive sequence. — 3.79 (2–5)
2. If the answer is unambiguous, allow answers in any format. — 3.50 (2–5)
3. Keep the form as short and simple as possible; do not ask for unnecessary input. — 3.86 (1–5) *(not applied in the study)*
4. (a) If possible and reasonable, separate required from optional fields — 4.07 (2–5); (b) use color and asterisks to mark required fields — 2.21 (1–4).
*Form layout*
5. Place labels above the corresponding input fields. — 2.71 (1–5)
6. Do not split a form into more than one column; one question per row. — 3.36 (1–5)
7. Match input field size to the expected answer length. — 3.29 (2–5)
*Input types*
8. Use checkboxes, radio buttons or drop-downs to restrict options, for entries easily mistyped, or when the expected answer is unclear. — 3.86 (2–5)
9. Use checkboxes instead of list boxes for multiple selection. — 3.86 (2–5)
10. Up to four options: radio buttons; more than four: drop-down menu. — 2.36 (1–4)
11. Order options intuitively (e.g., Monday, Tuesday…); otherwise alphabetically. — 4.71 (3–5)
12. (a) Use a drop-down for dates when format errors must be avoided — 3.57 (2–5); (b) use one input field and place format requirements (MM, YYYY) left of or inside the box for faster completion — 2.79 (1–5) *(expert table words 12b as the year field being twice as long)*.
*Error handling*
13. If a specific format is required, state the rule in advance (format specification, without an additional example). — 4.14 (3–5)
14. Error messages: polite, familiar language, say a mistake occurred, possibly apologize, describe the mistake and how to correct it. — 4.57 (3–5)
15. Never clear already completed fields after an error. — 5.00 (5–5)
16. Show error messages after the form is sent, all together, embedded in the form. — 4.29 (3–5)
17. Make error messages noticeable at a glance (color, icons, text) and explain the error and correction (refined: show in red at the right side of the field). — 3.57 (2–5)
*Form submission*
18. Disable the submit button once clicked. — 4.07 (2–5)
19. After sending, show a confirmation page that thanks the user and states what happens next; send a similar e-mail. — 4.64 (4–5)
20. Do not provide reset buttons; if used, make them visually distinct from submit, left-aligned with cancel to the right of submit. — 4.14 (1–5)

**Measured effects (holistic; not isolated per guideline)**
- Single-trial successful submission, original vs. improved: Sueddeutsche 10 vs. 24 (χ² = 11.20, p < .001); NZZ 9 vs. 24 (χ² = 12.93, p < .001); Spiegel 22 vs. 28 (χ² = 3.29, p = .035).
- Completion time (s): Sueddeutsche 113 → 85 (−25%, d = .93); NZZ 105 → 70 (−33%, d = 1.00); Spiegel 104 → 85 (−18%, n.s., d = .38). KLM predicted only −7% to −23%.
- NZZ initial errors from missing format specification: 17 (original) vs. 2 (improved). Sueddeutsche: 14 original-condition users resubmitted without corrections vs. 0.
- Eye tracking (NZZ): fixations 155 → 96 (r = .525), fixation duration 62 s → 41 s, saccade time 9 s → 4 s; scanpaths showed side-by-side left-aligned labels provoked longer saccades.
- Subjective (pooled): improved forms more usable (ASQ, FUS, SUS), less demanding (NASA-TLX) and more satisfying; per form only NZZ significant on all scales; improvements up to 16%. NZZ FUS item "I knew at every input which rules I had to stick to" r = .64.
- Guidelines 13 (format specification) and 17 (error message location/design) had a "remarkable effect" on submission trials; from users' viewpoint, 13 and 4 (required/optional identification) were most important—yet experts ranked them only 7th and 9th of 20.

**Design rules derivable**
- State format rules (e.g., password requirements) before input, not only in error messages. [strong]
- Clearly distinguish required from optional fields. [moderate]
- Place error messages next to (right of) the erroneous field, highlighted with color/icon/text, explaining the fix; never clear completed fields. [strong]
- Place labels above fields in a single column, one question per row. [moderate]
- Use the full guideline set as a checklist; a relatively small effort can yield 18–33% faster completion on real forms. [moderate]
- Validate guideline priorities with users; expert importance ratings can mis-rank what matters. [moderate]

**Boundary conditions & caveats.** Lab study, focused newspaper registration forms, guideline 3 not tested, effects confounded across guidelines; Spiegel (best original) showed small/non-significant effects; conversion and mobile not studied.


---

## 11__Chevalier-2016_Animations-25-years-later — Animations 25 Years Later: New Roles and Opportunities (Fanny Chevalier, Nathalie Henry Riche, Catherine Plaisant, Amira Chalbi, Christophe Hurter, 2016, AVI '16)
**Type:** taxonomy / review  ·  **Sample/method:** literature and commercial-product review (>200 examples by authors), iterated taxonomy, validated with informal interviews of 20 practitioners/researchers who supplied 95 more examples (98% fit the taxonomy).

**Core claim.** Animation in interfaces serves 23 roles in 5 categories—far beyond orientation—and evaluation should be "role-aware."

**Key findings**
- **Keeping in context:** (1) staying oriented during navigation (smooth zoom/pan; staged animation e.g., SpaceTree: shrink, re-center, grow); (2) supporting tracking during layout change ("nothing is lost… everything is transformed"); (3) maintaining up to date (notifications, "calm notification" that appears and fades); (4) replaying history/summarizing (reduce change blindness).
- **Teaching aid:** (5) affordance and preview (e.g., animated arrow prompting scroll, unlock gesture hint); (6) training/demonstration by example; (7) explaining how a system works; (8) illustrating an algorithm; (9) teaching a new representation (can be discontinued once learned).
- **User experience:** (10) hooking the user; (11) keeping the user engaged (most useful when content is lengthy and audience passive); (12) visual comfort and aesthetics (smooth vs. jarring; staggered animations with small start delays); (13) making activity/progress visible (busy cursors, progress bars, countdowns); (14) revealing/hiding content (side panels, drop-downs; ephemeral adaptation—predicted items appear immediately, others fade in); (15) virtual tour; (16) feedback of input mechanism (friction scroll, parallax, ripple).
- **Data encoding:** (17) revealing data relationships (e.g., Gapminder); (18) conveying uncertainty/randomness (risk icons repositioned **every 2 seconds** reduced misreading as 0%/100% risk); (19) encoding emotion; (20) encoding object attributes (category-specific trajectories, motion pointing).
- **Visual discourse:** (21) supporting a narrative; (22) highlighting content; (23) persuading/convincing.
- Hurts/risks: strong perceptual draw may stop users perceiving other display elements; value vs. static small multiples unclear; can distract, imply non-existent "magic," or deceive; questionnaires should capture dizziness, distraction, boredom. Empirical outcomes for teaching animations are "mixed."
- No timing guidance beyond the 2-second example; speed, number of stages and order are listed as open research factors.
- Evaluation methods by category: revisitation tasks and multiple-object tracking (vs. static control) for context roles; pre/post comprehension tests for teaching; viewing time, dropout, click/eye logs and A/B tests for UX roles; perception accuracy for data encoding; comprehension, behaviour change and memorability for discourse.

**Design rules derivable**
- Define the role an animation serves before designing it; drop animations that serve no role. [moderate]
- Animate transitions where objects move, appear or change layout so users can track them (prefer transformation over cut). [moderate]
- Break complex transitions into stages (e.g., remove obstructions → re-center → grow). [weak]
- Use animated progress/activity indicators during waits. [weak]
- Use short looping animations to reveal non-obvious gestures/affordances; retire teaching animations once learned. [weak]
- Avoid motion near content that must be read or compared, since motion captures attention. [moderate]
- Never use animation to mislead or misdirect attention. [weak]
- Evaluate animations with role-appropriate measures and against a static control; also measure side effects (dizziness, distraction). [moderate]

**Boundary conditions & caveats.** Taxonomy, not effect evidence; authors deliberately do not report published evaluation results; roles overlap; GUIs only (not AR/tangible).


---

## Cross-paper patterns in this group

- **Measure all three usability aspects separately.** Frøkjær 2000 (time–quality rs = −0.156), Hornbæk & Law 2007 (r = .164–.247) and Hornbæk 2006 (22% of studies with no effectiveness measure) converge: effectiveness, efficiency and satisfaction are only weakly related, so single scores or proxies mislead.
- **Preference ≠ performance.** Users preferred overview+detail even when it was slower (Cockburn), faceted search despite 10× latency (Yee-Hearst), and TeSS's ALL mode over their best-performing mode (Frøkjær). Evaluations must collect both.
- **Use validated questionnaires and report items.** Homegrown satisfaction scales are less reliable (α .736 vs .814; Hornbæk & Law); 51% of UX questionnaire studies hid their items (Bargas-Avila & Hornbæk); SUS is a validated, short, free option (Brooke) and can be written all-positive with comparable scores (Sauro & Lewis).
- **Self-reports do not substitute for objective measures.** Perceived accuracy/time correlate ~0 with actual measures (Hornbæk & Law); Hornbæk 2006 warns against conflating perceived learnability with learning.
- **Timing numbers converge on fast feedback, moderate transitions.** Filter feedback < 100 ms (Shneiderman); zoom animations 0.3–1.0 s (Cockburn); multi-second delays per refinement provoke frustration (Yee-Hearst: 3.7–4.3 s); Chevalier offers no general timing rules.
- **Overview first, with counts and no dead ends.** Shneiderman's mantra, Yee-Hearst's facet start page with query previews and zero-result suppression, and Cockburn's evidence on overviews all favour giving users a structured overview plus progressive refinement.
- **Search is iterative and multi-strategy.** Bates' berrypicking (evolving queries, many techniques) is reflected in Yee-Hearst's endgame pivots and Shneiderman's history/relate/extract tasks.
- **Animation helps comprehension and orientation more than speed.** Cockburn: animated zoom aids spatial models but not task time; Chevalier: many roles, mixed evidence, risk of attention capture.
- **Task determines which technique wins.** Fisheye vs. O+D vs. zoom results flip with task (Cockburn); faceted search beats keyword for multi-attribute but not single-facet queries (Yee-Hearst); Greenberg & Buxton argue evaluation method itself must fit the question and design stage.
- **Expert intuition can mis-prioritize.** Seckler: users' most important form guidelines (format specs, required-field marking) ranked only 7th and 9th by experts; Greenberg & Buxton caution against defaulting to whichever method reviewers favour.
- **Short, single-session studies dominate.** Median 30 min (Hornbæk 2006); no truly longitudinal UX studies (Bargas-Avila & Hornbæk); UX changes over time and after use (Law 2009) — longitudinal and learnability/retention measures are a recurring gap.
