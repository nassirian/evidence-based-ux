# Group H — Computational UI evaluation, optimisation & mobile touch/interruption

## 10__Deka-2017_Rico-mobile-app-dataset — Rico: A Mobile App Dataset for Building Data-Driven Design Applications (Deka, Huang, Franzen, Hibschman, Afergan, Li, Nichols, Kumar, 2017, UIST)
**Type:** dataset / tool  ·  **Sample/method:** Hybrid crowdsourced (13 UpWork workers, 2,450 h over five months) + automated depth-first crawling of 9,772 free Android apps; autoencoder layout embedding.

**Core claim.** Combining human exploration (to get past logins and complex input) with automated crawling mines far more UI states than either alone, yielding the largest mobile design dataset of its time, which can support design search, layout generation, code generation, interaction modelling and perception prediction.

**Key findings**
- Dataset: 72,219 unique UIs, 10,811 user interaction traces, 9,772 apps, 27 Google Play categories. The authors excluded multimedia, productivity and personalisation categories. Average app rating is 4.1 stars.
- More than 3M elements, about 500k of them interactive. On average a UI has **eight interactive elements**.
- Hybrid exploration raised UI coverage by **40% on average** over human exploration alone. On Etsy it found screens from 7 Activities beyond the 18 that humans found.
- Automation alone had **26% lower coverage** than the hybrid approach, mostly because of gated experiences such as the login walls on Todoist and WeHeartIt.
- Content-agnostic similarity heuristic: two screenshots are treated as the same state if they differ by fewer than α pixels; otherwise they are different if their resource-id sets differ by more than β. Tested on 1,044 UI pairs from 12 apps, α = 99.8% and β = 1 gave 6% false positives and 3% false negatives.
- Crowd cost: US$19,200, about $2 per app. Workers used each app for up to 10 minutes, then the crawler ran for 1 hour per trace.
- The 64-d layout autoencoder (input 11,200, hidden layers 2,048 and 256) encodes text vs. non-text bounding boxes. It retrieves layout-similar UIs (lists, login, dialogs, image grids) and separates small- from large-thumbnail lists.

**Design rules derivable**
- When gathering reference examples for a screen, retrieve them by **layout structure** (element-type bounding boxes), not only by visual content. Structurally identical screens can look different because their content differs. [moderate]
- Benchmark element density against typical apps. About 8 interactive elements per screen is the Rico mean (a descriptive norm, not a quality target). [weak]
- Automated reviewer: treat screens that differ only in content (same structure and resource-ids) as one design state, and critique the template once rather than every instance. [moderate]
- Automated reviewer: for coverage, don't assume a crawler reached gated screens such as login or verification. Ask for them, or seed with human traces. [moderate]
- Play Store rating and downloads are only *proposed* proxies for design quality. Don't treat them as validated quality labels. [weak]

**Boundary conditions & caveats.** Android only and free apps only, with some categories excluded. The data dates from 2017 and the authors note it will go stale. Crowd workers came from the US (10) and the Philippines (3). The perceptual-prediction applications are proposed, not evaluated. The paper is mainly about infrastructure and contains no usability findings.


---

## 10__Duan-2024_LLM-feedback-on-UI-mockups — Generating Automatic Feedback on UI Mockups with Large Language Models (Duan, Warner, Li, Hartmann, 2024, CHI)
**Type:** tool / empirical  ·  **Sample/method:** Figma plugin that sends a GPT-4 JSON representation of the UI plus guideline text. Evaluated in three studies: a performance study (3 designers rated suggestions on 51 UIs), a manual heuristic evaluation by 12 experts on 12 UIs, and an iterative-use study with 12 more experts.

**Core claim.** GPT-4 can automate parts of heuristic evaluation. It is good at subtle visual inconsistencies, text problems and UI semantics. It is worse than humans on precision, global or contextual issues and visual understanding, and its usefulness drops as a design improves over iterations.

**Key findings**
- Performance study: **52% Accurate, 19% Partially, 29% Not accurate**. 49% were helpful or very helpful and 36% were slightly or not at all helpful. Fleiss' κ was 0.112 for accuracy and 0.100 for helpfulness.
- Against a ground truth of 100 violations: GPT-4 had **precision 0.603, recall 0.380, F1 0.466**. The average human expert had 0.829, 0.336 and 0.478. **62 violations were found only by humans, 29 by both, and 9 only by GPT-4.**
- Iterative use: in the first round, 52% of suggestions were rated accurate and 47% helpful. After edits, 39% were accurate and 35% not accurate, and **51% were slightly or not helpful**. Performance fell each round.
- By guideline set: CrowdCrit visual guidelines did best, Semantic Grouping had the lowest accuracy, and Nielsen had the lowest helpfulness. **Accurate:** Recognition rather than Recall, Match Between System and Real World, and Consistency & Standards (mostly alignment and size checks). **Worst:** Aesthetic and Minimalist Design. **Bimodal:** Emphasis (visual hierarchy).
- Prompt ablations on 12 UIs (total / helpful violations): full chain 63/38, one call 62/31, no heuristics in the prompt 50/14, generic "UI feedback" 57/24.
- Other models: GPT-3.5-16k 228/23, because it applied every guideline to every element. Claude 2 scored 7/1 and PaLM 2 12/3.
- Strengths: subtle issues (misalignment, spacing, contrast, redundant elements, unlabeled uncommon icons; 12/12 participants), text and grammar fixes with replacement copy (12/12), and semantic regrouping (8/12).
- Weaknesses: guidelines over-applied without context (12/12), for example labels demanded on universal icons such as ✕ and the bag, or "fixing" a deliberately thicker selected-tab underline. The same feedback repeated per element (6/12). Phantom overlaps and center alignment missed because the model worked from bounding boxes (8/12). Vague fixes (5/12). After a dismissal it re-raised the same issue under a different heuristic (5 participants).
- 9 of 12 would use the tool. 7 preferred a one-shot check and 5 iterative use.

**Design rules derivable**
- Automated reviewer: give the model **explicit guideline text**. Removing the heuristics cut helpful findings from 38 to 14. [strong]
- Automated reviewer: run detection and rephrasing as **separate calls**. A single call lowered the helpful count and broke the output format. [moderate]
- Automated reviewer: phrase each finding in Sadler's format: the expected standard, then the gap in this design, then a concrete step to close it. Name the guideline and link to the exact element. [moderate]
- Automated reviewer: don't demand text labels on universally recognised icons (close ✕, cart or bag, etc.). [moderate]
- Automated reviewer: before flagging an inconsistency, check whether the difference *encodes state*, such as a selected tab, emphasis or the primary action. [moderate]
- Automated reviewer: deduplicate. Report a pattern once with all affected elements rather than once per instance. [moderate]
- Automated reviewer: judge alignment and overlap on the **rendered pixels**, not on bounding boxes. Bounding boxes produce false overlaps and miss center alignment of elements with different sizes. [moderate]
- Automated reviewer: lower confidence on vague heuristics such as "aesthetic and minimalist" and on flow-level heuristics when only one static screen is available. [moderate]
- Automated reviewer: expect more false positives on an already-polished design. Raise the reporting threshold in later review rounds. [moderate]
- Automated reviewer: actively look for **global** issues: screen purpose versus content, hidden key information, redundant navigation paths, and data that doesn't match its context. Humans found these and the LLM mostly missed them. [moderate]
- UI: correct grammar and replace jargon in on-screen copy. LLMs fix this reliably. [moderate]
- Don't lean on GPT-4 critique alone. Its precision of 0.603 means roughly 4 in 10 findings are not helpful. Keep a human in the loop. [strong]

**Boundary conditions & caveats.** Only static single screens and mobile UIs from the Figma Community, chosen because they had room for improvement. The model received text JSON only; the multimodal GPT of the time performed worse. The 8.1k context limited few-shot prompting. Inter-rater agreement was only slight. The results are for GPT-4 in 2023, and newer models may differ.


---

## 10__Duan-2024_UICrit-UI-critique-dataset — UICrit: Enhancing Automated Design Evaluation with a UI Critique Dataset (Duan, Chen, Li, Hartmann, Li, 2024, UIST)
**Type:** dataset / model (prompting)  ·  **Sample/method:** 7 designers (1–16 years of professional experience) critiqued 983 randomly selected CLAY/Rico mobile screens, giving 3,059 critiques with bounding boxes and rubric ratings. They used Nielsen's heuristics, CrowdCrit and Apple HIG plus their own experience. Few-shot and visual prompting experiments used Gemini Pro Vision. A validation study used 6 experts (5–30 years of experience).

**Core claim.** A targeted expert-critique dataset, used for similarity-based few-shot prompting and coordinate visual prompting, improves LLM UI critique by **55% over zero-shot**. Human critiques remain clearly better.

**Key findings**
- About 3 critiques per UI. 74.6% came from humans, 8.3% from Gemini only and 17.1% from both. **Only 13.1% (776 of 5,927) of zero-shot Gemini comments were valid.**
- The five critique clusters (SentenceBERT + KMeans) and their sizes are below.
  - **Layout (696):** positioning and alignment, visual hierarchy, logical grouping, simplicity.
  - **Color Contrast (655):** text, icon, button and background contrast.
  - **Text Readability (591):** font size and weight.
  - **Usability of Buttons (601):** visual design, clarity of purpose, adding buttons to simplify tasks.
  - **Learnability (601):** clarity of icons, regions, the screen and labels.
- Under-represented: error prevention and visibility of system status (only 2 critiques). Flow-level heuristics were also missing (feedback, cross-screen consistency, help).
- Ratings follow a roughly normal distribution with means near 6.0/10, and few ratings fall below 4. **Aesthetics and usability ratings correlate at r = 0.875.** Screen ratings barely correlate with Play Store ratings (0.007, 0.022 and 0.023). The within-app SD is about half the dataset SD (aesthetics 0.65 vs 1.17).
- Layout critiques tend to target groups, text readability critiques target elements, and contrast critiques have the most screen-level comments.
- Region-of-interest task, average quality score: 8-shot visual similarity 0.44, 8-shot semantic 0.42, 8-shot random 0.31, 0-shot 0.24 (from 45 comments).
- Whole-screen task: 8-shot with **visual + task similarity** scored 0.58 comment quality and 0.53 rating accuracy, beating task-only and visual-only sampling.
- Bounding-box IoU: screenshot only 0.004, grid overlay 1.1e-5, numbered patches 0.222, coordinates on the edges 0.186.
- Validation: zero-shot 0.31 (29 comments, mean rank 2.6), few-shot + coordinates 0.48 (14 comments, rank 2.1), human 0.75 (17 comments, rank 1.3). Experts preferred few-shot over zero-shot 67% of the time and humans over few-shot 81%. Agreement was fair: κ about 0.29–0.31, and 0.55 for rankings.

**Design rules derivable**
- When reviewing a single screen, check these five categories every time: layout and grouping, colour contrast (text, icons, buttons, background), text size and weight, button affordance and clarity of purpose, and learnability of icons and labels. [strong]
- Make primary actions visually dominant and make button purpose clear from the label. [moderate]
- Replace or label icons that don't map to real-world concepts. Add placeholder text to input fields. [moderate]
- Don't put text on low-opacity or translucent boxes over imagery. Use a solid colour so the text stays readable. [weak; illustrative example]
- Automated reviewer: select few-shot critique examples by **visual and task similarity** to the target screen, never at random. [strong]
- Automated reviewer: generate critiques and localise them in **separate calls**. Combining them degraded critique quality. [moderate]
- Automated reviewer: give the screenshot coordinate rulers on its edges to localise issues. Avoid full grid overlays, which added noise. [moderate]
- Automated reviewer: fewer, better comments win. Zero-shot produced twice as many comments of lower validity, so cap volume and filter. [moderate]
- Automated reviewer: score aesthetics and usability separately, but expect them to move together. Note static-screen limits and say explicitly that flow-level heuristics such as error prevention and system status were not assessed. [moderate]
- Don't use app-store ratings to infer screen-level design quality. [moderate]

**Boundary conditions & caveats.** One annotator per UI and only 7 annotators in total. The screens are older published Android apps, so the dataset skews toward mid-quality rather than very poor design. Few-shot was capped at 8 shots because of context limits, and the pipeline still hallucinated. Critiques were judged for validity only and never implemented. The model was Gemini Pro Vision as of 2024.


---

## 10__Oulasvirta-2018_Aalto-interface-metrics-AIM — Aalto Interface Metrics (AIM): A Service and Codebase for Computational GUI Evaluation (Oulasvirta, De Pascale, Koch, Langerak, Jokinen, Todi, Laine, Kristhombuge, Zhu, Miniukovich, Palmas, Weinkauf, 2018, UIST Adjunct poster)
**Type:** tool  ·  **Sample/method:** An open-source web service that computes 17 published metrics and models on a screenshot (with segmentation) of a URL, shows a histogram against other designs, and summarises the evidence for each metric. Compute times were measured on the top 10 Alexa sites.

**Core claim.** Pooling empirically validated perception and attention metrics in one extensible service makes computational GUI evaluation usable in design practice, with explanations and comparisons attached.

**Key findings — the 17 metrics (4 categories)**
- **Color Perception (7):**
  1. File size of the PNG or JPEG
  2. Color Variability: distinct colours in RGB, HSV and LAB
  3. Static Color Clusters: bins with more than 5 px, using 32×32×32 RGB bins
  4. Dynamic Color Clusters: distance-based bins
  5. Colorfulness: SD of pixels in RGB, after Hasler & Süsstrunk
  6. Luminance: SD of luminance corrected for display perception
  7. Color Harmony: the sum of pixel distances to a colour scheme
- **Perceptual Fluency (7):**
  1. Edge Density: edge pixels as a share of all pixels
  2. Contour Congestion: congested edge pixels as a share of all edge pixels
  3. Figure-Ground Contrast
  4. Symmetry: mirrored edges horizontally, vertically or diagonally
  5. Visual Complexity: balance, symmetry and equilibrium from a quadtree decomposition
  6. Grid Quality: alignment to grids
  7. White Space: share of non-covered space
- **Visual Guidance (2):** Itti-Koch Saliency, and Visual Search Performance (predicted search time for page elements).
- **Accessibility (1):** Color Blindness simulation of the three common types.
- Mean compute time per screenshot ranges from about 0.000 s (file size) to 42.4 s (dynamic clusters) and 71.5 s (color harmony).
- Python API: a metric takes a screenshot or segmentation and returns scores or an image. Visual search and grid quality are implemented in Common Lisp and MATLAB respectively.

**Design rules derivable**
- Automated reviewer: report quantitative proxies for clutter (edge density, contour congestion), colour load (number of colours, colorfulness), alignment (grid quality), white space, symmetry and balance, saliency and predicted search time. Compare each score to a distribution of peer designs rather than an absolute threshold. [moderate]
- Automated reviewer: run a colour-blindness simulation on every screen and check that meaning survives in all three simulations. [moderate]
- Automated reviewer: attach the underlying principle, the source and the strength of evidence to every metric-based finding. [moderate]
- Use a saliency map to check that the most salient regions are the intended focal elements. [weak; AIM provides the map but no thresholds]

**Boundary conditions & caveats.** A 2-page poster with no validation study. The paper gives no thresholds and no "good" values. The metrics were developed mostly on web pages and come from different source studies with different evidential strength. Comparisons rely on histograms of other designs.


---

## 10__Oulasvirta-2020_Combinatorial-optimization-of-GUI-designs — Combinatorial Optimization of Graphical User Interface Designs (Oulasvirta, Dayama, Shiripour, John, Karrenbauer, 2020, Proceedings of the IEEE 108(3))
**Type:** survey / model (formal)  ·  **Sample/method:** Survey of 92 initially selected articles, expanded through citation trees. Integer-programming formulations of GUI tasks. Review of objective functions and of empirical evaluations of optimised GUIs.

**Core claim.** GUI design can be formalised as combinatorial optimisation: a design space, objective functions grounded in empirically validated human models, and a task instance. With exact or black-box solvers this generates, adapts or critiques layouts, menus and functionality sets, and can put bounds on how far a design is from optimal.

**Key findings — objectives used to score designs**
- **Representations of evaluative knowledge.**
  - Boolean heuristics and constraints, e.g. AIDE's efficiency (path length), alignment, balance, and "do not use more than four colors to code information". They suffer conflict-resolution and validity problems.
  - Regression models: Fitts' law MT from D and W, and search–decide–point (SDP) for menus.
  - Image metrics: hue-template colour harmony, AIM.
  - Simulators: the Kieras–Hornof visual-attention model, reinforcement learning with KLM.
- **Functionality selection.** Usefulness U (with dependencies, e.g. print setup is useless without print), satisfaction S, ease of use E and profitability P. Fifty functions give 1,125,899,906,842,623 subsets.
- **Labels.** Memorability, typing time and consistency of labels for similar commands.
- **Icons.** Comprehensibility and identifiability (visually distinct). A crowd study found a high correlation between the comprehensibility score and human choices, but none for identifiability.
- **Menus.**
  - Selection time = Σ frequency × Fitts time.
  - Association: related commands are placed adjacent (e.g. copy/cut/paste).
  - Group size control via Hick–Hyman (log2 N).
  - An information-foraging objective puts semantically indicative items at the top of groups, finding 40–50-command menus in 20–30 min.
  - Menus with 20+ elements need hierarchy, and 50 commands can be arranged in 100! ≈ 10^158 ways.
- **Grid layouts.** Grid-like rectangular arrangement (penalising unnecessary grid lines and jagged outlines), proximity of semantically associated elements, conventional relative placement (Search to the right of the field in English locales), diverse near-optimal alternatives, and fast computation.
- Humans "seldom can discern very small changes in position, size, or color", so discretisation can be coarse.
- **Empirical outcomes.**
  - ILP hierarchical menus were significantly faster than commercial ones (N=24).
  - Familiarity-based web restructuring needed fewer fixations (N=16).
  - SUPPLE ability-based UIs gave 28% faster task completion for users with motor impairments (N=11).
  - Sketchplorer menus were faster after experience (N=20).
  - Rule-generated printing UIs were **twice as fast** when they accounted for expected element locations (N=48).
  - IFT-generated information displays drew 2× the attention of baseline displays.
  - Most professional designers (N=10, N=16) included optimiser suggestions in their final designs.

**Design rules derivable**
- Place high-frequency commands at the lowest-cost positions near the entry point (e.g. top-left in tabbed menus). [strong]
- Group logically associated commands adjacently, and lead each group with an item that signals what the group contains. [strong]
- Balance menu breadth and depth. Above about 20 items, introduce tabs, groups or submenus, and keep group size in check, since decision time grows with log2 N. [moderate]
- Align elements to a small number of shared grid lines and give the layout a clean rectangular outline. Avoid jagged edges. [moderate]
- Place semantically related widgets close together and follow conventional relative placements, such as the search button to the right of the field in LTR locales. [moderate]
- Choose icons for comprehensibility and make icons in a set visually distinct from one another. [moderate]
- Choose command labels that are memorable, quick to type and consistent across similar commands. [moderate]
- Put elements where users expect them from prior experience. [moderate]
- Automated reviewer: score a layout on several objectives at once (selection time, search, grouping and association, alignment, colour harmony, familiarity). Report the trade-offs, not one aggregate number. [moderate]
- Automated reviewer: don't flag sub-perceptual differences in position, size or colour. [moderate]
- Automated reviewer: prefer predictive models with empirical validation over unvalidated heuristics, and calibrate model parameters (e.g. Fitts' a and b) to the device and users. [moderate]

**Boundary conditions & caveats.** This is a survey. Many objectives need parameterisation, and results are sensitive to the weights chosen. Weighted-sum aggregation is the most common approach and the most weight-sensitive. Some optimised designs were rated *lower* than human designs, e.g. in a portrait-to-landscape study. Empirical studies are few and small. Simulators are often too slow for exact solvers.


---

## 10__Todi-2016_Sketchplore-layout-optimiser — Sketchplore: Sketch and Explore with a Layout Optimiser (Todi, Weir, Oulasvirta, 2016, DIS)
**Type:** tool / empirical  ·  **Sample/method:** A multitouch sketching tool with real-time multi-objective layout optimisation (variable neighbourhood search plus associative memory). Study 1 had 20 end users select apps on an optimised versus a factory Windows Phone home screen (55 apps, 275 trials each). Study 2 had 10 trained designers sketch a blog page for 30 min.

**Core claim.** A model-based optimiser can run alongside sketching. It infers the design task implicitly and offers local fixes and recolourings plus global alternatives that push designers toward more usable and aesthetic layouts without overriding them.

**Key findings**
- The five objectives, normalised to [0,1] and weighted to sum to 1:
  - **Visual clutter** (Rosenholtz): the determinant of the colour-feature covariance, so lower variety means less clutter.
  - **Visual search** (Kieras–Hornof availability plus a log memory term, assuming an expert with 1,000 searches).
  - **Target acquisition** (Fitts' law for touch, starting from the display centre).
  - **Grid quality** (Balinsky symmetry).
  - **Colour harmony** (hue-wheel templates, with 78 precomputed harmonic sets).
- Optional canvas-level terms: alignment lines and packing efficiency.
- Single-objective outcomes: clutter makes everything the same colour, and visual search makes everything a unique colour clustered top-left. These objectives **conflict**, so weights trade aesthetics against search.
- Fitts optimisation places the most important element centrally and enlarges the others around it.
- Design space: a 24×32 grid has 158,400 one-element layouts and about 10^41 eight-element layouts.
- Study 1 predictions: better visual search (0.106 vs 0.117, about 270 ms) and grid quality (0.005 vs 0.013), similar colour harmony, worse clutter. The selection score was reported as 0.108 vs 0.104 (about 90 ms).
- Study 1 results: no overall difference in selection time (t(19)=−0.95). The difference was **significant once the first selection of each app was excluded** (t(19)=−2.67, p<0.05). Most learning happened on the first selection.
- Use of colour was rated higher (Z=2.38) and symmetry lower (Z=−2.65) for the optimised layout. Overall aesthetics did not differ, and 10 of 20 users preferred the optimised layout.
- Study 2: 8 of 10 designers saved at least one optimiser-aided design, and they rated aided designs as equally good. The global "explore" alternatives were liked most. Some recolour suggestions were called "so 90s" or flashy. Performance was limited to designs with 10 or fewer elements.

**Design rules derivable**
- Place the most frequently used targets nearest the typical start point of the finger or cursor, and make them larger. [moderate]
- Give frequently searched items a distinctive colour, while keeping overall colour variety low enough to avoid clutter. Treat these as competing goals and weigh them deliberately. [moderate]
- Choose palettes that fit a harmonic hue template (analogous hues varied in saturation, plus a complementary accent). [moderate]
- Align element edges to shared lines and favour balanced, symmetric arrangements where they don't hurt efficiency. [moderate]
- Expect performance gains from an optimised layout only after first exposure. Evaluate with repeated use, not first-trial times. [moderate]
- Automated reviewer: present suggestions as optional alternatives beside the designer's work. Never overwrite it. Offer both small local fixes and distinctly different global alternatives, filtered for diversity. [moderate]
- Automated reviewer: don't optimise a single aesthetic metric alone, because each one alone produces unbalanced designs. [moderate]
- Automated reviewer: recolouring suggestions should be subtle. Garish harmonic palettes were disliked. [weak]

**Boundary conditions & caveats.** The models cover only visual and spatial aspects, not semantics, naming or grouping. The usage data (LiveLab) was several years old. The colour-patch demonstrations are toy cases. The designer study was qualitative with N=10, on a 55-inch touch display.


---

## 10__Todi-2018_Familiarisation-restructuring-layouts — Familiarisation: Restructuring Layouts with Visual Learning Models (Todi, Jokinen, Luyten, Oulasvirta, 2018, IUI)
**Type:** model / tool / empirical  ·  **Sample/method:** Familiariser, a browser that restructures a new web page so its features (logo, search, menus, cart, etc.) sit where the user's own browsing history predicts. It defines four familiarity principles. The study had 16 participants on 30 shopping sites, with 25 learning trials on 5 sites and 100 test trials, with eye tracking.

**Core claim.** Moving features of an unfamiliar layout to the positions a user has learned from previously visited designs in the same domain reduces visual search time and fixations.

**Key findings**
- The four principles:
  - **I. Frequency:** f = visits × average duration.
  - **II. Serial-position curve:** F = 0.4·frequency + 0.4·recency + 0.2·primacy.
  - **III. Visual statistical learning:** a per-feature spatial probability map over the history.
  - **IV. Cognitive model:** a simulation of eye movement, visual short-term memory and associative long-term memory with activation decay, which predicts where users will look.
- Restructuring keeps element sizes and resolves overlaps with ILP rules: keep left and top alignments, penalise displacement, keep pairwise order, don't change the width.
- Familiarisation was enabled after **25 page visits** with 5 or fewer unique pages, a value set by trial and error.
- Results with principle III: search time **2.8 s → 2.5 s** (t(663)=5.3, p<.001) and fixations **3.4 → 2.6** (t(596)=4.7, p<.001), each with β = 0.35. That is a search-time reduction of over 10% and over 23% fewer fixations.

**Design rules derivable**
- Put common features (logo, search, main menu, account, cart) where users of that domain already expect them. Learned position conventions speed visual search. [moderate]
- When deviating from domain conventions for branding, account for the visual-search cost to users. [moderate]
- Weight what users recall: frequency and recency matter most, primacy less. [weak]
- When restructuring a layout, keep shared left and top alignments, keep the relative order of elements and don't truncate content. [moderate]
- Automated reviewer: compare feature positions with the dominant positions in peer sites or apps of the same category, and flag atypical placement of key features as a findability risk. [moderate]
- Adaptive UIs: offer familiarisation on demand, for example as a toggle similar to a reader mode, instead of always on. [weak]

**Boundary conditions & caveats.** Only one principle (III) was tested and the four were not compared. The task was a brief point-and-click on known targets. Feature detection relied on DOM names and classes. The sample was small (16) in one domain, shopping. Branding and identity costs were not measured.


---

## 10__Wu-2024_UIClip-assessing-UI-design — UIClip: A Data-driven Model for Assessing User Interface Design (Wu, Peng, Li, Swearngin, Bigham, Nichols, 2024, UIST)
**Type:** model / dataset  ·  **Sample/method:**
- CLIP B/32 (151M parameters), fine-tuned on JitterWeb: 2.3M synthetic pairs from about 300k crawled web pages that were degraded with "jitter" functions grounded in CRAP.
- Also fine-tuned on BetterApp: 12 designers, about 1,200 pairwise ratings (892 usable pairs), and screens from VINS plus LLM-generated screens.
- Benchmarked against GPT-4V, Claude-3-Opus, Gemini-1.0-Pro, LLaVA-1.6-13B, Qwen-VL and CLIP variants.

**Core claim.** A small vision-language model trained on large-scale synthetic design-defect pairs plus some human preferences judges relative UI quality and flags CRAP-type defects better than much larger general VLMs, which perform near chance.

**Key findings**
- Jitter functions and the CRAP principles each one degrades:
  - Color Swap and Color Noise: contrast and repetition
  - Font Size swap and Text Noise: contrast and repetition
  - Text Color and Background Color (reduced contrast): contrast
  - Spacing noise in margins and padding: alignment and proximity
  - Complexity (random removal of images, text or styling): all four principles
  - Layout flow changes: alignment and proximity
- In an inspection of 100 jittered UIs, 9 were judged of similar quality to the original.
- Design-choice accuracy: the best UIClip (with web pairs) reached **75.12% overall** and 87.1% on jittered web pages. Adding human pairs gave 73.88%, and the CLIP objective alone 65.42%.
- Baselines: **GPT-4V 51.58%** (it refused about 10% of comparisons) and LLaVA 54.59%. Base CLIP was worst, because it associated dark, unreadable backgrounds with *better* design.
- All models found synthetic or LLM-generated screens easier than real apps. UIClip scored 67.65% vs 57.89%, and all models averaged 56.05% vs 51.50%.
- Design suggestions: VLMs listed all four CRAP principles almost every time, which inflated recall (Gemini 87.11%, GPT-4V 84.57%). Choice-adjusted recall dropped to 49.17% and 46.58%. UIClip variants were best.
- Designer agreement was low (Krippendorff's α = 0.37), which reflects subjectivity and platform familiarity (iOS vs Android).
- Retrieval MRR: the CLIP-objective model scored best (0.3851 / 0.4085). Pairwise-trained variants fell to 0.0962–0.1214, a trade-off between ranking quality and relevance.

**Design rules derivable**
- Keep a consistent palette and text-size hierarchy (repetition). Don't let subheadings and body text swap sizes. [moderate]
- Maintain strong text-to-background contrast. Low-contrast text and backgrounds close to the text colour were among the defects the model learned. [moderate]
- Use consistent margins and padding and keep related items close (alignment, proximity). Noisy spacing signals poor design. [moderate]
- Don't let text overflow its containers. [moderate]
- Automated reviewer: when comparing designs, use pairwise or relative judgements against a caption of the screen's purpose. Score quality *and* relevance to the intended function. [moderate]
- Automated reviewer: don't trust a general VLM's verdict about which screen is better, and require evidence tied to specific regions. Their accuracy was near chance and their reasoning plausible but wrong. [strong]
- Automated reviewer: name only the CRAP principles that actually drive a judgement. Listing all four is a known failure mode. [moderate]
- Automated reviewer: be cautious with bold or unconventional designs, which the model can misjudge, and with platform differences between iOS and Android. [weak]
- Use a learned quality score to rank multiple generated UI candidates ("best-of-n") before showing them to users. [weak; demonstrated, not user-tested]

**Boundary conditions & caveats.** Covers only single-screenshot visual design (CRAP). The model can't localise defects and doesn't assess flows or semantics. Synthetic defects may not match real-world defect distributions. The human data was small and the authors' human-data results were mixed. Baseline LVLMs are 2024 versions.


---

## 12__Bergstrom-Lehtovirta-Oulasvirta-2014_Functional-area-of-thumb — Modeling the Functional Area of the Thumb on Mobile Touchscreen Surfaces (Bergstrom-Lehtovirta, Oulasvirta, 2014, CHI)
**Type:** model / empirical  ·  **Sample/method:** A kinematic derivation plus data from 20 participants (finger span 161–220 mm, mean 189.7 mm). Each swept the thumb's maximal reach on an iPad Mini while the index-finger position on the back (d) was controlled in 15 mm steps. This gave 160 trajectories.

**Core claim.** The boundary of the screen area reachable by the thumb of the holding hand is a parabola. It can be predicted from finger span (s) and the index-finger distance on the back of the device (d), which lets designers check whether targets are reachable without a grip change.

**Key findings**
- Model: f(x) = a_y(x + h)² + s − d(1 + a_k) − b_k, with **a_y = −0.013, h = −15.996 mm, a_k = −0.257, b_k = 64.655**.
- The peak of the reachable area lies about **16 mm to the side of the index-finger axis**.
- A quadratic fit to individual trajectories gave mean R² = 0.958 (range 0.822–0.998). The final model fit averaged trajectories with mean R² = 0.949.
- Leave-one-out cross-validation gave mean R² = 0.6799 and mean **RMSE = 16.024 mm**, about the width of a fingertip.
- Of 8 hand measures, only **finger span** correlated with reach (r = 0.687). Reach maximum k correlated with d at r = 0.996. Curvature and the vertex x did not depend on d.
- The model predicted a published tablet grip's active-region width as 57.9 mm, against 57.6 mm reported.
- For a female user (s = 184.25 mm) holding a Nokia Lumia 900 obliquely, the call button was not reachable without a change of grip.
- Common designer "thumb-zone" heuristics are inconsistent. One shows the opposite upper corner as reachable, which the data contradict.

**Design rules derivable**
- For one-handed use, keep frequent and critical targets inside the predicted thumb reach of the smaller-handed target users at likely grips. Targets outside it force a grip change or the second hand. [strong]
- Don't place targets near the edge of the predicted reach. Place them toward the thumb's comfortable middle region. The model's error is about one fingertip (≈16 mm), and prior work shows performance improves toward the screen centre. [moderate]
- On larger phones, don't put frequent actions in the corner diagonally opposite the holding thumb. [moderate]
- Design for a range of hand sizes (finger span about 161–220 mm), not the average hand. [moderate]
- Automated reviewer: given device size, target positions and an assumed grip, estimate each target's reachability or "grip coverage", and flag frequent controls with low coverage. Don't rely on generic thumb-zone diagrams. [moderate]

**Boundary conditions & caveats.** Right hand only, at a fixed index orientation of 90° during data collection. Assumes the index finger is extended on the back, which gives conservative estimates. Participants were allowed to support the device with the other hand. Small sample of 20. The model doesn't predict performance *within* the reachable area. The tablet held horizontally was used as a measuring surface. Accuracy is insufficient for small targets near the limits of reach.


---

## 12__Grossman-2009_Survey-of-software-learnability — A Survey of Software Learnability: Metrics, Methodologies and Guidelines (Grossman, Fitzmaurice, Attar, 2009, CHI)
**Type:** survey / empirical  ·  **Sample/method:** Literature review, including 88 CHI and TOCHI papers that use "learnability". A study with 10 AutoCAD users (2 months to 5 years of experience) and one expert coach compared think-aloud with a new question-suggestion protocol.

**Core claim.** Learnability lacks a shared definition. A taxonomy (initial vs. extended learnability, crossed with user experience dimensions) plus a catalogue of metrics clarifies it. A coach-based question-suggestion protocol exposes far more learnability issues than think-aloud, including efficiency-transition issues.

**Key findings**
- Of the 88 papers: 45 used "learnability" without a definition, 17 meant first-time performance, 8 change in performance over time, 7 generic ease of learning, 4 first-time performance after instructions, 4 ability to master, 3 generic usability, and 2 retention.
- Taxonomy: **initial learnability** (performing well during an initial task or interval) and **extended learnability** (improving over an interval or the whole history, or eventually reaching a specific or optimal level).
- The user is described on four dimensions: experience with computers, with this interface, domain knowledge, and experience with similar software ("subsequent learning").
- **Metric categories:**
  - **Task:** % completing optimally, % completing without help, time to complete, decrease in errors, judged quality of work.
  - **Command:** success rate after training, growth in commands used, growth in command complexity, % of commands known and used.
  - **Mental:** think times, chunk size, mental-model tests, EEG.
  - **Subjective:** learnability comments, questionnaires.
  - **Documentation:** help use over time, time spent with docs.
  - **Usability:** quality of use over time, novice vs. expert comparison.
  - **Rule:** number of rules needed to describe the system.
- The question-suggestion protocol found **7.55 vs 2.8** learnability issues per 15-min task compared with think-aloud (F(1,6) = 48.8, p < .001). Issues decreased with experience.
- **Five issue categories:** Task Flow, Awareness of functionality, Locating functionality, Understanding functionality, and Transition to efficient behaviours.
- Novices mostly had awareness issues. Experts rarely had task-flow issues. Think-aloud surfaced proportionally more locating issues and no transition issues.
- Participants felt they progressed faster, were less frustrated and learned more under question-suggestion (all p < .05).
- Cited figure: users lose up to 40% of their time to "frustrating experiences" (Lazar et al.).

**Design rules derivable**
- Help users find **high-level task flows**, not only individual commands. Support goal-level queries in help. [weak]
- Raise awareness of relevant functionality with low-intrusion, context-relevant hints, e.g. showing the hotkey when a menu item is used. Avoid Clippy-style interruptions. [moderate]
- Make help and documentation aware of the user's current, possibly customised, UI layout so it can show where a function is. [moderate]
- Explain complex operations by demonstration in the user's own interface or with multimedia, rather than text alone. [weak]
- Encourage the shift to efficient methods by lowering the perceived cost of trying them, since users often know a better feature and don't use it. [weak]
- Define learnability explicitly before evaluating it: initial vs. extended, which user profile, and which metric (e.g. T2 or T5 for walk-up products). [moderate]
- Automated reviewer: classify learnability findings as task flow, awareness, locating, understanding or transition. Note that static or think-aloud-style inspection under-detects awareness and transition issues. [moderate]

**Boundary conditions & caveats.** The study had one application (AutoCAD), 10 participants and one coach. The experimenter coded issues without external validation. The guidelines are proposed directions, not tested interventions. The authors don't claim question-suggestion is generally "better" than think-aloud.


---

## 12__Henze-2011_100M-taps-touch-performance — 100,000,000 Taps: Analysis and Improvement of Touch Performance in the Large (Henze, Rukzio, Boll, 2011, MobileHCI)
**Type:** empirical (large-scale, in the wild)  ·  **Sample/method:** An Android Market game ("Hit It!") with tap-the-circle tasks under time pressure. It collected 120,626,225 touches from 91,731 installations. Analysis focused on the 4 most common devices or resolutions. A compensation function was then shipped in an update (quasi-experiment: 15,326,444 touches from 12,201 installations).

**Core claim.** Touch error falls with target size and is much higher at screen borders. Touches are systematically skewed toward a point near the lower-right of the screen, so a simple position-dependent shift reduces errors.

**Key findings**
- Error rate rises steeply **below 15 mm** and exceeds **40% for targets under 8 mm**, consistently across four devices. Targets were circles, measured by diameter.
- At **10.89 mm** diameter, the observed error was 14.19–18.86%, against 5% and 12.3% in earlier lab studies. The authors attribute the higher figure to time pressure and animated backgrounds.
- **Position:** on the HTC Wildfire, targets under 12 mm had a **31.68% error at the screen border vs 17.59% in the centre**. That difference corresponds to enlarging a target from 8 mm to 11 mm.
- **Offsets:** top-left targets were hit at a mean offset of +4.90 px and +6.64 px (toward the lower right), and bottom-right targets at −2.55 px and −2.24 px. Offset vectors converge on a point about 1.33 cm left of and 2.12 cm above the lower-right corner (Galaxy S), or about 25% of width and height. Other devices ranged 0.90–1.49 cm left and 1.35–2.44 cm up, consistent with a right-hand thumb.
- **Compensation:** offline simulation reduced errors by about 3.5% with discrete vectors and about 3.8% with continuous polynomial functions.
- In the field, the compensation **cut error rate by 7.79%** (from 13.39% to 12.34%, p < .0001, r = 0.04). By resolution the reduction was 10.69%, 2.38%, 7.53% and 6.17%. Touch-to-centre distance also fell.
- Context cited: near-perfect accuracy needs targets over 20×20 mm. The iOS HIG optimum was 6.74×6.74 mm at the time.

**Design rules derivable**
- Make touch targets as large as layout allows. Error rises sharply below about 15 mm and passes 40% below 8 mm, at least under time pressure. [strong]
- Make targets at screen edges and corners **larger** than central ones, or move critical targets toward the centre. [strong]
- Don't pack small, closely spaced targets along screen borders. [moderate]
- Systems and platforms: apply position-dependent offset compensation to touch input, because offsets are systematic. [moderate]
- Automated reviewer: flag touch targets under about 8 mm as high risk and under about 15 mm as elevated risk, especially near edges. Weight severity by frequency of use. [moderate]

**Boundary conditions & caveats.** The game task was speeded and had animated backgrounds, so absolute error rates are inflated. The authors expect relative differences to transfer. Circles were used, not squares. Grip and handedness were unknown. Many participants were Western (48.31% en_US). The effect sizes of compensation were very small, and the function was tuned to this task.


---

## 12__Holz-Baudisch-2010_Perceived-input-point-touch-accuracy — The Generalized Perceived Input Point Model and How to Double Touch Accuracy by Extracting Fingerprints (Holz, Baudisch, 2010, CHI)
**Type:** model / empirical / tool  ·  **Sample/method:**
- Study 1: 12 participants, 600 trials each, acquiring a crosshair target on a capacitive pad at 5 pitch levels (15°–90°), 5 roll levels (−15°–90°) and 2 yaw levels, committing with a footswitch.
- Study 2: 12 new participants, 650 trials each, comparing a simulated capacitive baseline, the RidgePad fingerprint-based correction and 6-DOF optical tracking.

**Core claim.** Most touch inaccuracy is not random "fat finger" noise. It comes from systematic offsets that depend on finger posture (pitch, roll, yaw) and on the individual user's mental model. A device that knows these factors and applies per-condition offsets can greatly improve accuracy.

**Key findings**
- The generalised model explained **67%** of the touch inaccuracy previously attributed to the fat-finger problem.
- Pitch, roll, yaw and user each produced significantly distinct touch clusters. A flatter finger shifted the sensed location toward the palm. Roll also shifted touches mainly along the finger axis. There was a strong user × posture interaction.
- Published "minimum target sizes" vary widely: **10.5 mm** (Vogel & Baudisch), **11.5 mm** (Wang & Ren) and **26 mm** (Hall et al.). The authors attribute the spread to differing posture conditions and calibration.
- Projected 95% button diameter: **15 mm** with no correction, about **5.4 mm** when correcting per posture and per user, a factor of 2.75.
- Study 2 mean spread: control 2.75 mm, RidgePad 1.24 mm, optical 0.85 mm. Minimum target size was **1.8× smaller** with RidgePad and **3.3× smaller** with optical tracking, so "up to 10×" more controls fit in the same area.
- Dot targets (occluded) versus crosshairs showed no significant difference in spread.
- Offset-cursor style aids add a 250–1000 ms time penalty (citing Vogel & Baudisch).

**Design rules derivable**
- On today's uncorrected touchscreens, budget about **15 mm** diameter for targets that must be hit about 95% of the time across varied postures and users. Below about 10.5 mm, expect reliability problems. [moderate]
- Expect users to hold the finger differently, e.g. flatter when reaching far. Don't assume one global offset, and allow a generous hit area around targets that are reached at awkward angles. [moderate]
- Platforms: apply calibrated offsets per user and per posture (or at least per yaw) before resorting to slower targeting aids. [moderate]
- Automated reviewer: treat a nominal minimum size, e.g. about 7–10 mm, as dependent on the device and its sensing. Flag small targets especially where users likely approach with flat fingers or at an angle (far reach, tabletops). [weak]

**Boundary conditions & caveats.** Right index finger only. Participants kept their heads fixed (parallax controlled) and committed with a footswitch, not finger lift-off. No time pressure. The fingerprint scanner and optical rig are prototypes, and the comparison takes 200–300 ms. Results are for pads and tables, not thumbs on phones.


---

## 12__Mehrotra-2016_Receptivity-to-mobile-notifications — My Phone and Me: Understanding People's Receptivity to Mobile Notifications (Mehrotra, Pejovic, Vermeulen, Hendley, Musolesi, 2016, CHI)
**Type:** empirical (in situ, experience sampling)  ·  **Sample/method:** An Android app logged notifications and triggered up to 4 experience-sampling questionnaires a day for about 2 months. The final set covers 20 users (11 male, 9 female, aged 19–50), 10,372 notifications, 474 questionnaire responses and 11 Big Five personality tests.

**Core claim.** How quickly users respond to a mobile notification and how disruptive they find it depend on the alert modality, the presentation, the sender relationship, the type, complexity and stage of the ongoing task, and personality. Disruptive notifications still get clicked when their content is valuable.

**Key findings**
- **Alert modality:** users missed alerts 14.63% (silent), 15.38% (vibrate), 23.75% (sound) and 21.05% (sound + vibrate) of the time, so silent mode doesn't prevent interruption.
- Mean seen time: **vibrate 3 min 21 s** (fastest), sound + vibrate 4:50, sound 5:57, **silent 7.332 min** (F(3,4925) = 26.41, p < .001).
- **Ongoing task:** notifications were seen fastest while communicating (mean 47 s) and slowest when idle (9 min 30 s).
- Higher task complexity went with *faster* noticing, a weak negative correlation (|ρ| = 0.183, p = 0.005).
- **Presentation:** high-priority (heads-up, blocking) notifications got a mean response of **11.94 s vs 25.91 s** for low-priority ones (t(2951) = 17.694, p < .001).
- **Sender:** decision time was fastest for a partner (3.315 s) and immediate family (4.891 s), and slowest for extended family (11.93 s) and service providers (8.146 s).
- **Disruption:**
  - It correlates strongly with task complexity (Kendall τ = 0.477, p < .001).
  - It is highest in the middle of or near the end of a task, and lowest when idle or starting a task.
  - It is highest when the user is working and lowest when idle.
  - It is highest when the sender is not a person or is a subordinate, and lowest for extended family.
- **Acceptance:** each 1-point rise in perceived disruption multiplies the odds of acceptance by **0.581** (95% CI 0.497–0.675; R² = 0.1434).
- 104 of 474 notifications were rated disruptive, yet **54% of these were clicked**, mainly because the content was useful (35.2%) or important (33.3%).
- Reasons to click: "I was free" 37.2%, sender important 31.5%, content useful 31.5%. Reasons to dismiss: not urgent 43.5%, not important 40.6%, not useful 38.4%.
- **Personality:** extroversion predicted higher reported disruption (R² = 0.737, N = 11). Extroversion, conscientiousness and neuroticism predicted seen time, and extroversion and neuroticism predicted decision time.

**Design rules derivable**
- Defer non-time-critical notifications while users are engaged in complex tasks or in the middle of one. Deliver at task boundaries (starting a task) or idle moments. [moderate]
- Let users declare busy periods during which only time-critical notifications get through. [moderate]
- Reserve high-priority, blocking presentation for genuinely urgent items. It roughly halves response time and interrupts the current task. [moderate]
- Make the sender and the value of the content legible in the notification summary, e.g. highlighting priority contacts, so users can triage quickly. [moderate]
- Be cautious with system or app-generated notifications that come from no person, which were rated most disruptive. Make sure they carry useful, actionable content. [moderate]
- Don't assume silent mode means a notification won't interrupt. Users still notice most alerts. [weak]
- Automated reviewer: for any notification spec, check its urgency against its presentation level, whether sender and content value are visible, and whether delivery respects user context. [moderate]

**Boundary conditions & caveats.** Small, unbalanced sample. The personality analysis has N = 11, so its very high R² values are likely inflated. Seen time was inferred from unlock events. The experience-sampling prompts themselves added notifications. The data independence assumption is untested. Android only. Context-sensor data wasn't analysed.


---

## Cross-paper patterns in this group
- **General-purpose LLMs and VLMs are weak UI judges without grounding.**
  - GPT-4 critique had precision 0.603 against 0.829 for experts (Duan LLM).
  - Zero-shot Gemini comments were 13.1% valid (UICrit).
  - GPT-4V picked the better design 51.58% of the time (UIClip).
  - Grounding consistently helps: explicit guideline text, similarity-selected few-shot examples, task-specific training, and splitting detection, phrasing and localisation into separate calls.
- **Shared failure modes for automated critics:**
  - Over-applying guidelines without context (labelling universal icons, "fixing" intentional state differences).
  - Listing every principle, which inflates recall.
  - Repeating the same finding per element.
  - Hallucinated issues from structural representations (false overlaps from bounding boxes).
  - More false positives as designs improve.
  - Missing global or contextual problems.
  - A skill should explicitly guard against each of these.
- **Single-screen visual-design checks are where automation is reliable.** Alignment, spacing, size consistency, contrast, text size and weight, and copy errors work well (Duan, UICrit, UIClip, AIM). Flow-level heuristics (error prevention, system status, help, cross-screen consistency) and aesthetic judgement remain weak.
- **Recurring critique taxonomy across sources:**
  - Layout, grouping and alignment
  - Colour contrast
  - Text readability
  - Button affordance and clarity of purpose
  - Learnability of icons and labels (UICrit)
  - These map closely to CRAP (UIClip) and to the high-accuracy LLM heuristics (Consistency & Standards, Recognition vs Recall).
- **Human expert agreement is low** (κ ≈ 0.1–0.31, Krippendorff's α = 0.37). An automated reviewer should report confidence and rationale, and treat its output as advice for a human to decide on.
- **Multi-objective scoring beats any single metric.**
  - Clutter vs. visual search, and aesthetics vs. Fitts efficiency, conflict.
  - Optimising one objective produces degenerate layouts (Sketchplore, Oulasvirta 2020).
  - Report trade-offs with empirically grounded models: Fitts, visual search, colour harmony, grid quality, association and grouping, familiarity.
- **Familiarity and convention are measurable performance factors.**
  - Placing features where users expect them cut search time over 10% and fixations over 23% (Todi 2018).
  - Location-aware generation doubled speed in printing UIs (survey in Oulasvirta 2020).
  - Optimised layouts paid off only after first exposure (Sketchplore).
- **Touch target sizing has converging but context-dependent numbers.**
  - Uncorrected 95% reliability needs about 15 mm (Holz & Baudisch).
  - Errors climb steeply below 15 mm and exceed 40% under 8 mm under time pressure (Henze).
  - Literature minimums range 10.5–26 mm.
  - Edges and corners are much worse than the centre (31.68% vs 17.59%), equivalent to about 3 mm of target size.
- **Touch offsets are systematic, not random.** They depend on screen position, finger posture and the individual user. Generous hit areas, larger edge targets and platform-level compensation (7.79% fewer errors) follow from this.
- **One-handed reach is bounded and predictable.** A parabolic thumb area depends on finger span and grip (Bergstrom-Lehtovirta). Keep frequent targets well inside it rather than at its limits, and design for small hands.
- **Interruptions should be matched to context and value.** Defer during complex or mid-task work, reserve blocking presentation for urgent items, and surface sender and content value for quick triage (Mehrotra). This links to learnability guidance that hints should be low-intrusion and relevant to context (Grossman).
- **Evaluation method shapes what problems are found.** Coach-based question-suggestion found 2.7× more learnability issues than think-aloud, including awareness and transition issues that observation misses (Grossman). Likewise, static screenshot critique structurally can't see flow problems, so a skill should say what its method can't detect.
