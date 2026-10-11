# Visual hierarchy, layout and aesthetics

> Scope: how to group, order, emphasize and style screen elements so users see the right things first, read the layout correctly, and judge the product as usable and credible. Evidence grades: **[A]** strong — replicated, large-N, meta-analytic, or an international standard; **[B]** moderate — one solid study or converging smaller studies; **[C]** weak — expert opinion, theory, small qualitative work, or extrapolation from lab psychology to UI.

## Rules

### VH-1. Keep first-screen visual complexity low to moderate
- **Do:** Limit the number of separate text groups, image areas and content regions on the first screen. Target moderate complexity (about 4 on the 1–10 perceptual model scale). When in doubt, err toward simpler, not denser. Keep layouts "easy to grasp", not "dense" or "patchy".
- **Why:** Complexity is the strongest first-impression predictor. Appeal peaks at complexity 4.2/10; high complexity costs far more than low complexity (d = 2.0 vs d = 0.6 from the peak) (Reinecke 2014, N ≈ 40,000). Complexity correlated with aesthetics r = −.55 and alone explained 30% of variance (Miniukovich 2014). Low-complexity sites were liked about as much as medium ones; colorfulness played a minor role (Reinecke 2013). Complexity is predicted by text area, non-text area, number of text groups and number of image areas (Reinecke 2013). The VisAWI Simplicity facet relates most to perceived usability (r .76 viewing only) (Moshagen 2010).
- **Evidence:** [A] — (Reinecke 2013; Reinecke 2014; Miniukovich 2014; Miniukovich 2015; Moshagen 2010).
- **Limits:** All measured from 50–500 ms or 4 s screenshot exposures, not use. Extremely plain designs still lose some appeal, more so for women and older users (Reinecke 2014). The 4.2 value is on a model-specific scale; use it as a relative target, not a pixel spec.

### VH-2. Make spacing the primary grouping signal
- **Do:** Make gaps inside a group clearly smaller than gaps between groups. Aim for a between/within distance ratio of at least 1.5 so the intended grouping wins. Use spacing to structure displays before adding lines or boxes.
- **Why:** Proximity is the strongest and best quantified Gestalt principle. Grouping log-odds is a linear function of relative distance only (pure distance law), and when a competing distance ratio exceeds about 1.5 the weaker grouping is almost never seen (Wagemans 2012). Spacing to structure displays is a standing display guideline (Smith 1986, 2.5/3).
- **Evidence:** [B] — (Wagemans 2012; Smith 1986).
- **Limits:** Quantification comes from dot lattices and simple displays. Transfer to rich UI layouts is assumed, not tested. Real layouts combine many cues synergistically.

### VH-3. Reinforce groups with similarity, common region, connectedness and common fate
- **Do:** Give items in a group a shared color, size, shape or brightness in addition to proximity. Use an enclosing region (card, panel, background tint) or a connecting line when related items cannot sit close together. Show belonging through simultaneous change (e.g., co-highlight related items on hover).
- **Why:** Similarity adds to proximity in dot lattices (parallel indifference curves). Common region and element connectedness speed grouping. Common fate is powerful and extends to common luminance change (Wagemans 2012).
- **Evidence:** [B] — (Wagemans 2012).
- **Limits:** Similarity is additive with proximity in lattices but can interact non-additively for contours. Do not rely on closure or symmetry alone to define groups; closure is a weak grouping cue once good continuation is controlled (Wagemans 2012).

### VH-4. Make intended figures read as figures
- **Do:** Make dialogs, cards and popovers convex, enclosed, smaller than their surroundings and placed on a homogeneous background. Shading gradients on the near side push a region forward. Avoid ragged, disordered edges on elements that should read as objects.
- **Why:** Convex regions are seen as figure in about 90% of trials with multiple regions; small area, surroundedness, lower region and shading gradients bias figure assignment; disordered contour terminations make a region read as ground or hole (Wagemans 2012). Low figure-ground contrast lowered beauty ratings (contrast r .51 with 150 ms ratings) (Miniukovich 2015).
- **Evidence:** [C] — (Wagemans 2012; Miniukovich 2015).
- **Limits:** Lab psychophysics with bipartite displays. Isolated cues are weak; they combine in natural scenes. Attention and familiarity also shift figure assignment.

### VH-5. Reduce clutter and contour congestion
- **Do:** Cut edge density and the number of distinct objects. Keep generous space between contours and edges; lines closer than about 20 px were treated as congested. Remove redundant borders and dividers before adding new ones.
- **Why:** Clutter and contour congestion lower both immediate (150 ms) and deliberate (4 s) beauty ratings on web and mobile (congestion r −.46 web) (Miniukovich 2015). Clutter's effect on aesthetics was fully mediated by perceived complexity (Miniukovich 2014). Each item on the VisAWI Simplicity facet rewards "well structured" over "too dense" (Moshagen 2010).
- **Evidence:** [B] — (Miniukovich 2014; Miniukovich 2015; Moshagen 2010).
- **Limits:** Mobile app ratings were much harder to predict (R² .13–.18 vs .49 web). The 20 px threshold is a metric parameter, not a tested perceptual limit.

### VH-6. Align blocks to a regular grid
- **Do:** Align element edges to a small number of shared grid lines. Use few distinct block sizes. Give the layout a clean rectangular outline without jagged edges. When restructuring, keep shared left and top alignments and the relative order of elements.
- **Why:** Grid quality predicted beauty ratings in the web model (Miniukovich 2015). Layout optimizers penalize unnecessary grid lines and jagged outlines (Oulasvirta 2020) and use grid quality as an objective; the optimized layout scored better on grid quality (0.005 vs 0.013) (Todi 2016). Familiarization restructuring preserved left and top alignments and order (Todi 2018).
- **Evidence:** [B] — (Miniukovich 2015; Oulasvirta 2020; Todi 2016; Todi 2018).
- **Limits:** Grid metrics explain part of variance only. Optimizer studies are small. Users "seldom can discern very small changes in position, size, or color", so do not chase sub-perceptual misalignment (Oulasvirta 2020).

### VH-7. Commit to symmetry or to clear asymmetry
- **Do:** Either make a layout clearly symmetrical or clearly asymmetrical. Avoid "almost symmetrical" layouts, especially on mobile. Do not treat symmetry as a main quality driver.
- **Why:** On mobile, partially symmetrical layouts were disliked more than fully symmetrical or fully asymmetrical ones (significant only at 4 s) (Miniukovich 2015). Symmetry metrics did not correlate with aesthetics (Miniukovich 2014), were pruned from the complexity model (Reinecke 2013), and users ranked symmetry low in importance (M = 2.39) (Moshagen 2010).
- **Evidence:** [C] — (Miniukovich 2014; Miniukovich 2015; Reinecke 2013; Moshagen 2010).
- **Limits:** The partial-symmetry finding is from one mobile study. Optimizers that favor balance (Todi 2016) produced layouts rated lower on symmetry yet not worse overall.

### VH-8. Put identity and key content where eyes land first
- **Do:** Place identity cues (logo, page title, headline, key image) top-left or top-center. Put primary task content center-left or center. Do not put must-see content in the right third above the fold. Keep critical content above the fold.
- **Why:** The four upper-left regions received attention fastest in both foraging and recognition tasks. The right third above the fold was neglected: about 3 s to first fixation in foraging, median fixation impact 0, almost no attention in the first second. Below-fold position carried negative weight (Buscher 2009).
- **Evidence:** [B] — (Buscher 2009).
- **Limits:** N = 20, 1024×768 displays, 2009-era layouts, left-to-right readers. Task type changes which regions matter (center-center for foraging, top-center and top-left for recognition). The predictive model missed important right-side elements.

### VH-9. Use size first, then centrality, contrast and isolation, to set importance
- **Do:** Make the element that must be seen first the largest. Make adjacent size steps clear (larger symbol at least 1.5× the height of the next smaller). To raise an element further, move it toward the center, give it a contrasting background, or isolate it from surrounding elements. Make primary actions visually dominant.
- **Why:** Size was the strongest single predictor of fixation (regression weight 0.318 foraging, 0.291 recognition) (Buscher 2009). A design-importance model learned that larger, more central, contrasting or isolated text gains importance (Bylinskii 2017). Size codes need adequate differences, at least 1.5× (Smith 1986, 2.6/22). Expert critiques ask that primary actions be visually dominant (Duan 2024 UICrit).
- **Evidence:** [B] — (Buscher 2009; Bylinskii 2017; Smith 1986; Duan 2024 UICrit).
- **Limits:** Importance data are click and annotation proxies for attention. The 1.5× value is 1986 expert judgment.

### VH-10. Title every screen and chart, at the top
- **Do:** Give every screen, panel and data visualization a clear title placed at the top. When cropping or thumbnailing, keep the title, the main supporting text and data extremes.
- **Why:** Text elements, especially titles, were the most fixated and clicked elements in visualizations (click vs fixation ranking rs = .96). Importance-based thumbnails let users find targets in 1.96 vs 3.25 clicks (Bylinskii 2017). Display title at top is a standard guideline (Smith 1986, 2.5/10).
- **Evidence:** [B] — (Bylinskii 2017; Smith 1986).
- **Limits:** The model over-predicts title importance. Click data carry a text bias that may not hold for every chart type.

### VH-11. Organize content by sequence, function, frequency or importance
- **Do:** Show only the data users need for the task. Choose one organizing logic per display: sequence of use, function, importance or frequency. Keep related data on the same page; page crowded displays instead of cramming. Keep each kind of item in the same place and format across screens.
- **Why:** Display guidelines call for only necessary data (2.0/2), logical organization grouped by sequence, function, importance or frequency (2.5/12–17), related data on the same page (2.5/5), paging crowded displays (2.5/4) and consistent format and location (2.5/1, 4.0/6). Consistency is "the single objective on which experts agree" (Smith 1986). Credible sites are "arranged in a way that makes sense" (+1.48) and do not cram everything on the home page (Fogg 2001; Fogg 2003).
- **Evidence:** [C] — (Smith 1986; Fogg 2001; Fogg 2003).
- **Limits:** Smith & Mosier guidelines are 1986, judgment-based and written for 24×80 terminals. Grouping by function did not raise apparent usability of ATM layouts (r .075) and fewer groups looked more usable in Israel (Kurosu 1995; Tractinsky 1997); test grouping density with users.

### VH-12. Highlight sparingly and code consistently
- **Do:** Reserve highlighting for critical data. Define every display code and apply it the same way on every screen. Treat brightness coding as two-valued. Use blinking only for urgent items, at 2–5 Hz with at least 50% on time. Highlight data that changed after an automatic update.
- **Why:** Highlighting is most effective when used sparingly (2.6/1); codes must be defined and consistent across displays (2.6/6, 2.6/7); brightness coding is limited to two levels (2.6/23); blink coding is for urgent attention at 2–5 Hz (2.6/35, 2.6/37); highlight changed data (2.7.3/2) (Smith 1986).
- **Evidence:** [C] — (Smith 1986).
- **Limits:** Judgment-based guidance. Check any blinking against flash limits in WCAG 2.3.1 (no more than 3 flashes per second) (W3C 2023).

### VH-13. Put common features where users already expect them
- **Do:** Place logo, search, main menu, account and cart in the dominant positions used by peer products in the same domain. Follow conventional relative placement (e.g., search button to the right of the field in left-to-right locales). Use familiar conventions such as the telephone keypad layout. When localizing, use the conventions of that locale. If branding demands a deviation, account for the search cost.
- **Why:** Moving features to positions learned from prior sites cut search time from 2.8 s to 2.5 s (over 10%) and fixations from 3.4 to 2.6 (over 23%) (Todi 2018). Rule-generated printing UIs that respected expected locations were twice as fast (N = 48, as surveyed in Oulasvirta 2020). Keypad familiarity was the only built-in usability feature that tracked apparent usability (r .730) (Kurosu 1995). Israelis associated usability with the telephone keypad, Japanese with the horizontal keypad (Tractinsky 1997).
- **Evidence:** [B] — (Todi 2018; Oulasvirta 2020; Kurosu 1995; Tractinsky 1997).
- **Limits:** Todi 2018 tested one principle with N = 16 in the shopping domain only. Branding and identity costs were not measured.

### VH-14. Lay out menus and command sets for frequency and association
- **Do:** Put the most frequent commands at the lowest-cost positions near the entry point (and for touch, near the typical start point of the finger, and larger). Place related commands next to each other (e.g., cut, copy, paste). Lead each group with an item that signals what the group holds. Order options logically, else by frequency. Above about 20 items, add tabs, groups or submenus.
- **Why:** Optimization objectives score selection time as frequency × Fitts time, association of related commands, and decision time growing with log2 N; ILP-optimized hierarchical menus were faster than commercial ones (N = 24) (Oulasvirta 2020). Fitts optimization places the most important element centrally and enlarges others around it (Todi 2016). Menus should be ordered logically, else by frequency (Smith 1986, 3.1.3/21).
- **Evidence:** [B] — (Oulasvirta 2020; Todi 2016; Smith 1986).
- **Limits:** Optimized layouts paid off only after first exposure: no difference in selection time until the first selection of each app was excluded (Todi 2016). Results are weight-sensitive and empirical studies are small.

### VH-15. Treat visual appeal as part of usability
- **Do:** Invest in a harmonious, coherent visual design, not only functional arrangement. Avoid disharmonious multicolor schemes and odd material textures on controls. In usability tests, control or report the visual polish of prototypes.
- **Why:** Beauty predicted pre-use apparent usability at r = .589 in Japan (Kurosu 1995) and r = .83–.92 in Israel across three methods (Tractinsky 1997). An appealing but functionally identical phone gave faster completion (147.7 s vs 198.5 s), fewer errors (2.0 vs 4.8 per trial) and higher perceived usability (PSSUQ 6.13 vs 5.19) (Sonderegger 2010). Tractinsky 2000 is reported as replicating the aesthetics–perceived usability link (as cited in Moshagen 2010 and Hartmann 2008). Aesthetics and usability ratings of mobile screens correlated r = 0.875 (Duan 2024 UICrit).
- **Evidence:** [A] for appearance → perceived usability before use; [B] for appearance → performance — (Kurosu 1995; Tractinsky 1997; Sonderegger 2010; Moshagen 2010; Duan 2024 UICrit).
- **Limits:** Apparent usability is judged without use. The performance effect came from adolescents in a school-like task; earlier studies (cited in Sonderegger 2010) found appealing designs slowed users in leisure contexts. Hassenzahl 2004 is cited as contradicting the link (as cited in Hartmann 2008).

### VH-16. Do not let appeal hide usability problems
- **Do:** Never replace labelled navigation with decorative metaphors. Label clickable metaphor objects. Do not read high appeal ratings as proof of usability. Collect aesthetic ratings after real task use if you need them separated from usability.
- **Why:** Animated metaphor versions had worse perceived usability (3.63 vs 4.99) and about twice the reported problems, yet were often preferred (Hartmann 2008). VisAWI–usability correlation fell from about .64 when viewing to .31 after tasks (Colorfulness .04, n.s.) (Moshagen 2010). Sonderegger et al. 2012 is reported as showing the positive aesthetic effect almost disappeared after initial use (as cited in Miniukovich 2015).
- **Evidence:** [B] — (Hartmann 2008; Moshagen 2010; Miniukovich 2015).
- **Limits:** Hartmann's samples are small, HCI-trained and mostly male. Hartmann's authors note the halo may evaporate when usability problems destroy trust.

### VH-17. Design the first glance deliberately
- **Do:** Treat the first screen as a fast, lasting judgment. Check the layout at a glance (blurred or brief exposure) for complexity, clutter and hierarchy before polishing detail.
- **Why:** Ratings after 150 ms and 4 s correlated r = .70 (web) and .58–.59 (mobile) (Miniukovich 2015). Lindgaard 2006 is reported as showing appeal judgments form in about 50 ms and differ only marginally from longer exposures (as cited in Reinecke 2013, Moshagen 2010, Sonderegger 2010 and Miniukovich 2015).
- **Evidence:** [B] — (Miniukovich 2015; Reinecke 2013; Lindgaard 2006 as cited in Reinecke 2013).
- **Limits:** First impressions are not long-term appeal, usability or trust (Reinecke 2013). Screenshot studies have no interaction.

### VH-18. Cover all four aesthetic facets: simplicity, diversity, colorfulness, craftsmanship
- **Do:** Start from a simple, structured layout, then add controlled variety so the design does not feel uninspired. Use a matching color composition. Signal craftsmanship: one consistent concept, careful execution, up-to-date styling, quality images and typography. Measure aesthetics with the 18-item VisAWI, not a single "beautiful?" item.
- **Why:** VisAWI's four facets (α .85–.89, total α .94) were validated with over 2,000 participants. Craftsmanship separated pleasing from distorted versions most (d 1.60), then Colorfulness (1.12), Simplicity (0.94) and Diversity (0.49). A color-scheme change alone moved Colorfulness by d = 0.57 (Moshagen 2010). Diversity converges with expressive aesthetics (r .80) (Moshagen 2010), and expressive aesthetics tracked engagement (r .71–.89) (Hartmann 2008).
- **Evidence:** [A] for the instrument; [B] for the design levers — (Moshagen 2010; Hartmann 2008).
- **Limits:** German-speaking samples and websites only. Diversity items are abstract and hard to turn into specific design moves.

### VH-19. Look professional to look credible
- **Do:** Invest in a professional design look and a structure that makes sense. Remove all amateurism signals: typos, broken links, stale content, downtime, links to non-credible sites. Never make ads hard to distinguish from content; avoid pop-up ads. Make credibility cues (contact details, sponsor identity) prominent; unnoticed cues have no effect.
- **Why:** Design look was the most mentioned credibility cue (46.1% of 2,440 comments), then information design and structure (28.5%) (Fogg 2003). "Looks professionally designed" scored +1.55; ads hard to distinguish from content scored −2.08 (lowest of 51 items); pop-ups −1.56; broken link −1.45; typo −1.28; rarely updated −1.67 (Fogg 2001). Credibility impact = prominence × interpretation (Fogg 2003).
- **Evidence:** [B] — (Fogg 2001; Fogg 2003).
- **Limits:** Self-report from 1999–2003 web users. Low-involvement participants rely on peripheral cues. "Design look" was the broadest coding category. Cue weights differ by domain (e.g., reputation for e-commerce, bias for news).

### VH-20. Tune aesthetic targets to the audience and use context
- **Do:** Set complexity and colorfulness targets per audience, and test with that audience. Go simpler and less colorful for highly educated audiences and for Finnish, Russian, French and German markets; more colorful for e.g. Macedonia, Malaysia and Chile. Avoid very plain, colorless designs for older and female audiences. Use expressive, engaging visuals for leisure and children; plain, usable layouts for work, experts and the elderly. Do not copy award-winning sites as universal templates.
- **Why:** Preferred complexity ranged 2.5–4.8 and colorfulness 3.6–7.6 across subgroups; Russia preferred complexity 2.5; Finland, Russia, France and Germany preferred colorfulness 3.6–4.4 vs US 6.1; Macedonia 7.6; PhD holders 5.0 vs pre-high-school 6.9; complexity peak rose with age to 4.7 over 50 (Reinecke 2014). Under framing, the metaphor design was preferred for children (86%) and general use (96%), the menu design for university students (85%), experts (82%) and the elderly (89%) (Hartmann 2008). Webby nominees averaged 4.21–6.57 with mean SD 1.69 (Reinecke 2013).
- **Evidence:** [B] — (Reinecke 2014; Reinecke 2013; Hartmann 2008).
- **Limits:** Age results conflict: Reinecke 2013 found over-45s liked low complexity more, Reinecke 2014 found the complexity peak rises with age; the larger 2014 sample leans toward the latter. Effects are first impressions from self-selected online volunteers. Where feasible, localize or personalize rather than pick one universal style.

### VH-21. Preserve the cues experts rely on
- **Do:** Before redesigning a legacy tool, observe experts in situ and list the perceptual and spatial features they use. Keep or amplify them. Prefer spatial or analog encodings (position in a meaningful range, target marks) over bare numbers when users judge relations or trends. Let users arrange, pile and group items to off-load memory. Show useful use-history (recent, frequent, popular items) with user consent.
- **Why:** Pilots used the round airspeed dial as a material anchor and rarely read speed as a number; those cues were removed in digital tapes and one manufacturer reverted to a dial replica. Expert supports are "sometimes actively, but mistakenly, designed out" of clean, simple environments. People off-load cognitive effort to the environment whenever practical (Hollan 2000).
- **Evidence:** [C] — (Hollan 2000).
- **Limits:** Ethnographic evidence from safety-critical expert domains; few quantitative results.

### VH-22. Check hierarchy on the rendered design, and treat metrics as screening
- **Do:** Judge salience, alignment and clutter on the rendered screen (size, position, pixels), not on markup or bounding boxes. Use importance models trained on designs rather than natural-image saliency. Compare metric scores with peer designs. Report several objectives and their trade-offs, never one aggregate score.
- **Why:** Rendering features (size, position) predicted attention at r = .50; HTML-only features at r = .28 (Buscher 2009). Natural-image saliency models lack a notion of text (Bylinskii 2017). Screenshot metrics explain about 50% of web aesthetics variance but only 13–32% on mobile (Miniukovich 2015). Bounding-box reasoning produced phantom overlaps and missed center alignment (Duan 2024 LLM feedback). Optimizing one objective alone (clutter or visual search) produces degenerate layouts (Todi 2016).
- **Evidence:** [B] — (Buscher 2009; Bylinskii 2017; Miniukovich 2015; Todi 2016; Duan 2024 LLM feedback).
- **Limits:** AIM-style metrics come without validated thresholds (Oulasvirta 2018). Computed scores are screening tools, not verdicts.

## Numbers at a glance
| Parameter | Value | Grade | Source |
|---|---|---|---|
| Proximity: distance ratio beyond which the competing grouping is almost never seen | ~1.5 | B | Wagemans 2012 |
| Complexity peak for first-impression appeal (1–10 model scale) | 4.2 | A | Reinecke 2014 |
| Appeal penalty vs peak: low / high complexity | d = 0.6 / d = 2.0 | A | Reinecke 2014 |
| Colorfulness peak (1–9 model scale) | 6.1 | B | Reinecke 2014 |
| Subgroup range of preferred complexity / colorfulness | 2.5–4.8 / 3.6–7.6 | B | Reinecke 2014 |
| Complexity vs aesthetics correlation | r = −.55 | B | Miniukovich 2014 |
| Contour spacing treated as congested | < ~20 px | C | Miniukovich 2014 |
| 150 ms vs 4 s rating correlation | r = .70 web, .58–.59 mobile | B | Miniukovich 2015 |
| Screenshot metrics, variance explained | ~50% web, 13–32% mobile | B | Miniukovich 2015 |
| Time to first fixation, right third above fold (foraging) | ~3 s | B | Buscher 2009 |
| Size regression weight on fixation | 0.318 (foraging), 0.291 (recognition) | B | Buscher 2009 |
| Rendering vs HTML-only attention prediction | r = .50 vs .28 | B | Buscher 2009 |
| Importance thumbnails: clicks to find target | 1.96 vs 3.25 | B | Bylinskii 2017 |
| Minimum ratio between adjacent size codes | ≥ 1.5× height | C | Smith 1986 |
| Blink rate for urgent coding | 2–5 Hz, ≥ 50% on | C | Smith 1986 |
| Beauty vs apparent usability | r = .589 (Japan); .83–.92 (Israel) | A | Kurosu 1995; Tractinsky 1997 |
| Appealing vs unappealing phone: time / errors | 147.7 s vs 198.5 s / 2.0 vs 4.8 | B | Sonderegger 2010 |
| VisAWI–usability correlation: viewing vs after use | ~.64 vs .31 | B | Moshagen 2010 |
| VisAWI pleasing vs distorted: Craftsmanship / Colorfulness / Simplicity / Diversity | d 1.60 / 1.12 / 0.94 / 0.49 | A | Moshagen 2010 |
| Credibility: "design look" share of comments | 46.1% | B | Fogg 2003 |
| Credibility: ads hard to tell from content / typo / broken link | −2.08 / −1.28 / −1.45 (−3..+3) | B | Fogg 2001 |
| Familiar placement: search time / fixations | 2.8 → 2.5 s / 3.4 → 2.6 | B | Todi 2018 |
| Menu size at which hierarchy is needed | 20+ items | B | Oulasvirta 2020 |

## Common misreadings
- "Gestalt laws are fixed, equally strong rules." — Strengths differ greatly, cues interact, and experience and attention modulate them. Closure is weak as a grouping cue (Wagemans 2012).
- "More visual grouping always looks more usable." — In ATM layouts, fewer groupings went with higher apparent usability (r −.46 to −.67), and grouping by function did not track apparent usability (Tractinsky 1997; Kurosu 1995).
- "What is beautiful is usable." — Beauty strongly predicts how usable a design looks before use. After real use the link weakens (VisAWI .64 → .31), and aesthetic designs can have worse measured usability (Moshagen 2010; Hartmann 2008).
- "Simpler is always better." — Very low complexity loses some appeal (d 0.6), simplicity without variety reads as "uninspired", and "clean" redesigns can strip cues experts use (Reinecke 2014; Moshagen 2010; Hollan 2000).
- "Symmetry makes a layout beautiful." — Symmetry metrics did not predict aesthetics and users ranked symmetry low; only partial symmetry on mobile was penalized (Miniukovich 2014; Miniukovich 2015; Moshagen 2010).
- "Award-winning designs are universally liked." — Webby nominees averaged 4.21–6.57 with high spread; preferences vary by age, education, gender and country (Reinecke 2013; Reinecke 2014).
- "White space metric = designed spacing." — The 2015 white-space metric measured area not covered by visual blocks, i.e., badly distributed content (Miniukovich 2015).

## Review checklist
- [ ] VH-1: Is first-screen complexity low to moderate (few text groups, image areas and separate regions; no dense or patchy areas)?
- [ ] VH-2: Is every within-group gap clearly smaller than the gaps between groups (ratio ≥ ~1.5)?
- [ ] VH-3: Where items cannot be adjacent, are groups bound by shared styling, a common region or a connector, rather than closure or symmetry alone?
- [ ] VH-4: Do overlays and cards read as figures (convex, enclosed, on a homogeneous background, adequate figure-ground contrast)?
- [ ] VH-5: Are redundant borders and dividers removed and contours not crowded (no lines closer than ~20 px without reason)?
- [ ] VH-6: Do elements align to a few shared grid lines with few block sizes and a clean outline?
- [ ] VH-7: Is the layout clearly symmetric or clearly asymmetric, not almost symmetric?
- [ ] VH-8: Are identity cues top-left/top-center, primary content center-left, and nothing must-see in the right third above the fold?
- [ ] VH-9: Is the most important element the largest, with size steps ≥ 1.5× and the primary action visually dominant?
- [ ] VH-10: Does each screen, panel and chart have a clear title at the top?
- [ ] VH-11: Does the display show only needed data, organized by one clear logic, in a consistent location and format across screens?
- [ ] VH-12: Is highlighting reserved for critical data, with codes defined and consistent, and any blinking limited to urgent items at 2–5 Hz?
- [ ] VH-13: Are logo, search, menu, account and cart where peer products in the domain put them, with locale conventions respected?
- [ ] VH-14: Are frequent commands at the lowest-cost positions, related commands adjacent, groups led by an indicative item, and menus above ~20 items structured?
- [ ] VH-15: Is the visual design coherent and harmonious, and is prototype polish controlled or reported in any usability test?
- [ ] VH-16: Is all navigation labelled (no unlabelled decorative metaphors), and are appeal ratings not used as evidence of usability?
- [ ] VH-17: Does the screen communicate its hierarchy at a glance (brief or blurred view)?
- [ ] VH-18: Does the design show simplicity, controlled variety, a matching color composition and consistent craftsmanship; is any aesthetic measurement done with VisAWI?
- [ ] VH-19: Is the design free of typos, broken links, stale content and ad/content confusion, with credibility cues prominent?
- [ ] VH-20: Are complexity and colorfulness targets set for the stated audience and use context, not copied from award sites?
- [ ] VH-21: For a redesign of an expert tool, were the perceptual and spatial cues experts use identified and preserved?
- [ ] VH-22: Were salience, alignment and clutter judged on the rendered screen, with metrics reported as trade-offs and screening only?

## Sources
- Buscher, G., Cutrell, E., Morris, M. R. (2009). *What do you see when you're surfing? Using eye tracking to predict salient regions of web pages*. CHI '09. https://doi.org/10.1145/1518701.1518705
- Bylinskii, Z., et al. (2017). *Learning visual importance for graphic designs and data visualizations*. UIST '17. https://doi.org/10.1145/3126594.3126653
- Duan, P., et al. (2024). *UICrit: enhancing automated design evaluation with a UI critique dataset*. UIST '24. https://doi.org/10.1145/3654777.3676381
- Duan, P., et al. (2024). *Generating automatic feedback on UI mockups with large language models*. CHI '24. https://doi.org/10.1145/3613904.3642782
- Fogg, B. J., et al. (2001). *What makes web sites credible? A report on a large quantitative study*. CHI '01. https://doi.org/10.1145/365024.365037
- Fogg, B. J., et al. (2003). *How do users evaluate the credibility of web sites?* DUX '03. https://doi.org/10.1145/997078.997097
- Hartmann, J., Sutcliffe, A., De Angeli, A. (2008). *Towards a theory of user judgment of aesthetics and user interface quality*. ACM TOCHI. https://doi.org/10.1145/1460355.1460357
- Hassenzahl, M. (2004). *The interplay of beauty, goodness, and usability in interactive products*. Human-Computer Interaction. https://doi.org/10.1207/s15327051hci1904_2 (secondary; as cited in Hartmann 2008)
- Hollan, J., Hutchins, E., Kirsh, D. (2000). *Distributed cognition: toward a new foundation for HCI research*. ACM TOCHI. https://doi.org/10.1145/353485.353487
- Kurosu, M., Kashimura, K. (1995). *Apparent usability vs. inherent usability*. CHI '95. https://doi.org/10.1145/223355.223680
- Lindgaard, G., Fernandes, G., Dudek, C., Brown, J. (2006). *Attention web designers: you have 50 milliseconds to make a good first impression*. Behaviour & Information Technology. https://doi.org/10.1080/01449290500330448 (secondary; as cited in Reinecke 2013 and others)
- Miniukovich, A., De Angeli, A. (2014). *Quantification of interface visual complexity*. AVI '14. https://doi.org/10.1145/2598153.2598173
- Miniukovich, A., De Angeli, A. (2015). *Computation of interface aesthetics*. CHI '15. https://doi.org/10.1145/2702123.2702575
- Moshagen, M., Thielsch, M. T. (2010). *Facets of visual aesthetics*. IJHCS. https://doi.org/10.1016/j.ijhcs.2010.05.006
- Oulasvirta, A., et al. (2018). *Aalto Interface Metrics (AIM)*. UIST '18 Adjunct. https://doi.org/10.1145/3266037.3266087
- Oulasvirta, A., Dayama, N. R., Shiripour, M., John, M., Karrenbauer, A. (2020). *Combinatorial optimization of graphical user interface designs*. Proceedings of the IEEE. https://doi.org/10.1109/jproc.2020.2969687
- Reinecke, K., et al. (2013). *Predicting users' first impressions of website aesthetics with a quantification of perceived visual complexity and colorfulness*. CHI '13. https://doi.org/10.1145/2470654.2481281
- Reinecke, K., Gajos, K. Z. (2014). *Quantifying visual preferences around the world*. CHI '14. https://doi.org/10.1145/2556288.2557052
- Smith, S. L., Mosier, J. N. (1986). *Guidelines for designing user interface software*. MITRE / DTIC ESD-TR-86-278. https://doi.org/10.21236/ada177198
- Sonderegger, A., Sauer, J. (2010). *The influence of design aesthetics in usability testing*. Applied Ergonomics. https://doi.org/10.1016/j.apergo.2009.09.002
- Sonderegger, A., et al. (2012). Longitudinal study of aesthetics and usability (secondary; as cited in Miniukovich 2015; not in corpus).
- Todi, K., Weir, D., Oulasvirta, A. (2016). *Sketchplore: sketch and explore with a layout optimiser*. DIS '16. https://doi.org/10.1145/2901790.2901817
- Todi, K., Jokinen, J., Luyten, K., Oulasvirta, A. (2018). *Familiarisation: restructuring layouts with visual learning models*. IUI 2018. https://doi.org/10.1145/3172944.3172949
- Tractinsky, N. (1997). *Aesthetics and apparent usability: empirically assessing cultural and methodological issues*. CHI '97. https://doi.org/10.1145/258549.258626
- Tractinsky, N., Katz, A. S., Ikar, D. (2000). *What is beautiful is usable*. Interacting with Computers. https://doi.org/10.1016/s0953-5438(00)00031-x (secondary; as cited in Moshagen 2010 and Hartmann 2008)
- Wagemans, J., et al. (2012). *A century of Gestalt psychology in visual perception I*. Psychological Bulletin. https://doi.org/10.1037/a0029333
- W3C (2023). *Web Content Accessibility Guidelines (WCAG) 2.2*. W3C Recommendation. https://www.w3.org/TR/WCAG22/
