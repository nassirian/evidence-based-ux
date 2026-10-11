# Navigation, search and data display

> How to structure navigation, menus, search, filtering, zooming views, tables and charts so users can find, compare and judge information. Evidence grades: **[A]** strong — replicated, large-N, meta-analytic, or an international standard; **[B]** moderate — one solid study or converging smaller studies; **[C]** weak — expert opinion, theory, small qualitative work, or extrapolation from lab psychology to UI.

## Rules

### NS-1. Start with an overview, then let users zoom and filter, then show details on demand
- **Do:** Open any data-exploration, catalog or search view with an overview of the whole collection (facets with top-level categories, a map, a summary chart). Let users narrow it by zooming and filtering. Show full item details only when the user selects an item.
- **Why:** The task-by-data-type taxonomy proposes this sequence as the starting structure for visual information seeking (Shneiderman 1996). A faceted interface that exposed every facet with its top-level categories on the start page was preferred by 29 of 32 users over a keyword baseline (Yee 2003). Supporting both an overview and a detail view improves interaction over single-view software (Cockburn 2009).
- **Evidence:** [B] — (Shneiderman 1996; Yee 2003; Cockburn 2009).
- **Limits:** Shneiderman calls the mantra only a starting point, and its cited support comes from small studies. For a simple known-item lookup, a plain keyword box can be enough (Yee 2003).

### NS-2. Update results within 100 ms of a filter change, using direct-manipulation controls
- **Do:** Couple filter controls to the result display so the display updates in under 100 ms. Use range sliders for continuous attributes and buttons or toggles for attributes with fewer than about 10 values. Prefer these to typed Boolean queries for exploratory filtering. Respond to simple display requests within 0.5–1.0 s.
- **Why:** Dynamic queries updated in under 100 ms even with tens of thousands of items. They produced faster performance and fewer errors than form fill-in (18 students), and graphical filter-flow queries gave better comprehension than textual Boolean queries and were preferred by all 20 subjects (Shneiderman 1996). In a faceted interface, per-step processing of 3.7–4.3 s (vs 0.3–0.37 s for the baseline) drew negative comments from more than half of users (Yee 2003). Smith & Mosier set 0.5–1.0 s for simple display requests (Smith 1986, 2.7.1/6).
- **Evidence:** [B] — (Shneiderman 1996; Yee 2003; Smith 1986).
- **Limits:** The 100 ms target and the <~10-value button rule come from prototypes and small studies. The 0.5–1.0 s value is a 1986 expert judgment.

### NS-3. Support all seven information tasks, including history and extract
- **Do:** Beyond overview, zoom, filter and details on demand, provide *relate* (select an attribute to show related items), *history* (undo, replay, progressive refinement of queries) and *extract* (save or export a sub-collection together with the query settings that produced it).
- **Why:** These seven tasks define a complete visual information-seeking tool, and most prototypes failed to support history and extract (Shneiderman 1996). Real searches gather results bit by bit across a session, so users need to keep and revisit what they collected (Bates 1989).
- **Evidence:** [C] — (Shneiderman 1996; Bates 1989).
- **Limits:** Taxonomy and theory. The value of each task has not been measured separately.

### NS-4. For exploratory search over richly described collections, combine hierarchical facets with keyword search
- **Do:** Offer hierarchical faceted navigation (several independent attribute hierarchies) integrated with a keyword box. Map keyword hits onto facet categories and offer disambiguation when a term matches several categories. Let users refine with terms from several facets at once.
- **Why:** In a 32-user study on about 35,000 images, the faceted interface was preferred overall by 29 of 32 users, judged more useful for usual tasks by 28 and as more likely to cause dead ends by only 3 (vs 28 for the baseline). Recall on "find all" tasks rose from 57% to 81% and from 21% to 77%. Users built multi-facet queries 19% of the time in unstructured tasks and 45% in structured ones (Yee 2003).
- **Evidence:** [B] — (Yee 2003).
- **Limits:** One lab study with domain experts and a well-annotated collection. The faceted interface was slower (12 min 6 s vs 9 min 30 s on task). For a single-facet task, preference split about 50/50 (15 vs 16). Do not force facets on simple lookups.

### NS-5. Show result counts on every refinement option and never offer a link that leads to zero results
- **Do:** Show a query preview (the number of matching items) next to every facet value or filter option. Hide or disable any option that would return zero results given the current filters.
- **Why:** The faceted design that did this produced 26 empty result sets during structured tasks, against 82 for the keyword baseline, and users felt more confident they had found all relevant items (p < .05 to p < .001) (Yee 2003). Offering only available options is also a long-standing menu guideline (Smith 1986, 3.2/10).
- **Evidence:** [B] — (Yee 2003; Smith 1986).
- **Limits:** Counts must stay accurate and fast. Stale or slow previews reintroduce the latency cost in NS-2.

### NS-6. Let users group by any facet and pivot from an item's metadata
- **Do:** Allow results to be grouped or sorted by any facet. On an item's detail page, show each of its metadata terms in its hierarchy as a link that opens the set of items sharing that term.
- **Why:** The faceted design used group-by and an item "endgame" that exposed terms for lateral navigation (Yee 2003). Shneiderman's *relate* task is the same move (Shneiderman 1996). Searchers chain from one item to related ones (footnote chasing, citation searching, author searching) rather than issuing one query (Bates 1989).
- **Evidence:** [B] — (Yee 2003; Shneiderman 1996; Bates 1989).
- **Limits:** The pivot links were part of a package. Their separate contribution was not measured.

### NS-7. Design search for evolving queries and several strategies, with a place to collect finds
- **Do:** Let users refine or redirect a query without losing earlier results. Give single-step access to several strategies in one system: links in both citation directions, author or creator pages, browsing within a source, and category browsing at several levels of generality. Provide a "collect" or "flag" basket that persists across the session.
- **Why:** The berrypicking model describes real searches as evolving queries that gather information in bits across many sources and techniques. It lists six common techniques. In one survey cited, 69% of social-science faculty relied on footnote chasing and over 87% used abstracting journals only occasionally or less (Bates 1989).
- **Evidence:** [C] — (Bates 1989).
- **Limits:** Pre-web, academic and bibliographic context. The design proposals were not tested in the paper.

### NS-8. Pick overview+detail, zooming or focus+context by task
- **Do:** Use overview+detail (separate overview and detail panes) for document comprehension. Use focus+context or a wide display for dynamic tasks where switching between views is costly. Use zooming when visual-memory demands are low. In overview+detail, let users browse the overview without changing the detail view, reflect every detail-view change in the overview immediately, and let users hide the overview to recover space.
- **Why:** No technique wins across tasks. Overview+detail gave the highest reading comprehension and was most preferred, though slowest. Fisheye reading was fastest but gave the lowest comprehension. Zooming beat multiple overview+detail views only when visual-memory demands were low. A mixed-resolution focus+context display was up to 56% faster than overview+detail and zooming in one study (Cockburn 2009).
- **Evidence:** [B] — (Cockburn 2009).
- **Limits:** Narrative review of small, task-specific studies. The authors state that the research does not yet give clear guidelines. Overview panes cost screen space and the effort of integrating two views.

### NS-9. Make zooming smooth, reversible and concurrent with panning
- **Do:** Animate zoom transitions over 0.3–1.0 s, longer for larger scale changes. Provide one-handed concurrent pan and zoom rather than separate or two-handed controls. Give zoom visible controls and an obvious reverse action. Mark regions that contain content, or make empty regions unreachable, so users do not get lost in blank space ("desert fog").
- **Why:** Durations of 0.3–1.0 s are appropriate depending on domain and distance, and animated zoom helps users build a spatial model. Concurrent unimanual pan and zoom outperformed bimanual, serial and speed-dependent automatic zooming. Only 1 of 6 experienced Word users knew the hidden Ctrl+scroll zoom, and view changes are usually not undoable (Cockburn 2009). Smooth zooming preserves the sense of position (Shneiderman 1996).
- **Evidence:** [B] — (Cockburn 2009; Shneiderman 1996).
- **Limits:** No evidence that animated zoom shortens task time. Region zoom-in has no matching zoom-out, so offer it with care. Desert-fog guidance is weak.

### NS-10. Do not use fisheye or other distortion where users must hit targets or judge distances
- **Do:** Avoid distortion views (fisheye menus, magnifying docks) for target selection and for tasks that need judgments of distance or direction. If distortion is required, stabilize targets (lock positions, flatten while moving fast, or expand only after selection) and add grid lines.
- **Why:** Distortion creates a moving-target problem. Fisheye menus were slower than hierarchical menus. Fisheyes impair relative spatial judgment, and grid lines help interpretation (Cockburn 2009).
- **Evidence:** [A] — (Cockburn 2009).
- **Limits:** Fisheye views helped in steering tasks, degree-of-interest source-code navigation and complex calendar tasks (Cockburn 2009). Expanding targets that grow late in the movement still speed acquisition.

### NS-11. Keep item positions stable and cue matches in place
- **Do:** Keep items at stable spatial positions across sessions so users can return to them by location. Highlight or group items that match the current search instead of moving them.
- **Why:** Space-filling thumbnails at stable page locations outperformed panning, zooming and overview+detail for revisitation. Cue-based highlighting of search matches gave performance benefits (Cockburn 2009). Users off-load memory onto spatial arrangement (Hollan 2000).
- **Evidence:** [B] — (Cockburn 2009; Hollan 2000).
- **Limits:** Stability conflicts with adaptive reordering by frequency. If you reorder, see NS-13 and weigh the cost to spatial memory.

### NS-12. Order menu options logically, else by frequency, and show only what is available
- **Do:** Order options by a logical sequence the user knows (task sequence, alphabetical, numeric, chronological). Where no logical order exists, put the most frequent first. Use a single-column list with one selection per menu. Give each menu an explanatory title. Show options explicitly rather than making users recall them. Disable or omit options that are not available in the current state.
- **Why:** These are Smith & Mosier guidelines 3.1.3/21, 3.1.3/2–3, 3.1.3/10, 3.1.3/16 and 3.2/10 (Smith 1986). Frequency-weighted placement near the entry point minimizes selection time in optimization models (Oulasvirta 2020).
- **Evidence:** [B] — (Smith 1986; Oulasvirta 2020).
- **Limits:** Smith & Mosier is a 1986 compilation, mostly expert judgment, written for character terminals.

### NS-13. Structure menus by frequency, association and group size
- **Do:** Put high-frequency commands in the lowest-cost positions near the menu's entry point. Place associated commands next to each other (copy, cut, paste). Lead each group with an item that signals what the group contains. Above about 20 items, add hierarchy (tabs, groups or submenus) and keep each group small, because decision time grows with log2 N (Hick–Hyman). Put items where users expect them from prior experience.
- **Why:** Optimization objectives grounded in Fitts' law, Hick–Hyman and search–decide–point models produced hierarchical menus that were significantly faster than commercial ones (N=24). Printing UIs that respected expected element locations were twice as fast (N=48). Menus of 20+ elements need hierarchy, and 50 commands can be ordered in about 10^158 ways, so structure must be chosen deliberately (Oulasvirta 2020).
- **Evidence:** [B] — (Oulasvirta 2020).
- **Limits:** A survey of models. Results are sensitive to how objectives are weighted, the empirical studies are few and small, and some optimized designs were rated lower than human ones.

### NS-14. Show where the user is, offer one action to go up, and give experts a bypass
- **Do:** Show the current position in any menu or page hierarchy (breadcrumb, highlighted path). Let one simple action return up one level. Let experienced users bypass menu sequences with a command, shortcut or typed entry. Offer step-by-step paths for beginners and direct commands for experts.
- **Why:** Smith & Mosier guidelines 3.1.3/30, 3.1.3/33, 3.1.3/35 and 3.0/3 (Smith 1986). Hidden shortcuts are rarely discovered, so the menu path must remain visible (Cockburn 2009).
- **Evidence:** [C] — (Smith 1986; Cockburn 2009).
- **Limits:** Expert judgment. Shortcuts should be optional extras, not the only path (Smith 1986).

### NS-15. Make the path into cascading submenus wide and forgiving
- **Do:** Treat hover-to-open submenus, slider tracks and drag channels as steering tasks. Keep the corridor to a submenu short and wide (wider items, fewer items to cross). Add tolerance, such as a delay before a submenu closes when the pointer leaves the corridor.
- **Why:** Steering time grows linearly with path length divided by width, not logarithmically as in Fitts' law (r² 0.968–0.978 across tunnel shapes). Error rates in narrow paths were 6–18% even when users tried to avoid errors. For cascading menus, wider items help deeper menus (Accot 1997).
- **Evidence:** [B] — (Accot 1997).
- **Limits:** Stylus and tablet, small samples. The menu equation is an approximation. The closing-delay tolerance is an extrapolation.

### NS-16. Meet the WCAG 2.2 navigation criteria
- **Do:** Provide a way to skip repeated blocks (2.4.1). Give each page a descriptive title (2.4.2). Keep focus order meaningful (2.4.3). Make link purpose clear from the link text and its context (2.4.4). Offer more than one way to reach a page, such as navigation plus search or a site map, except for steps in a process (2.4.5, AA). Write headings and labels that describe topic or purpose (2.4.6, AA). Keep repeated navigation in the same relative order on every page (3.2.3, AA) and give the same function the same name everywhere (3.2.4, AA).
- **Why:** These are Level A and AA success criteria of the international standard (W3C 2023). Smith & Mosier also call for consistent location of display features and consistent display format (Smith 1986, 2.5/1, 4.0/6).
- **Evidence:** [A] — (W3C 2023; Smith 1986).
- **Limits:** Consensus standard written for web content. See 08-accessibility-inclusion.md for the full baseline.

### NS-17. Display only the data needed, in a form users can use directly
- **Do:** From task analysis, show the data the user needs for the decision and nothing more. Present it in the units, formats and wording the user works in, so no mental conversion is needed. Recap context on screen rather than relying on the user's memory. Minimize abbreviations.
- **Why:** Smith & Mosier guidelines 2.0/1–3 (necessary data only, usable form), 2.0/11 (context), 2.0/12 (familiar wording) and 2.0/16 (abbreviations) (Smith 1986). Simple fixes of this kind (formatting, consistent wording, no abbreviations) gave 25% faster data entry and 25% fewer errors in one cited study (Smith 1986).
- **Evidence:** [B] — (Smith 1986).
- **Limits:** Guidelines say how to present, not what to present. Content selection still needs task analysis.

### NS-18. Show values in the terms users evaluate them
- **Do:** When users judge state, trend or distance from a target, display that directly: rate of change, difference from target, status against limits. Use analog or positional encodings (a marker within a meaningful range, target annotations) rather than a bare number when users judge relations. Before "cleaning up" a legacy display, check which perceptual cues experts rely on.
- **Why:** Showing a tank's rate of change, not only its level, shortens the semantic distance on the evaluation side (Hutchins 1985). Pilots use the round airspeed dial as an anchor for a space of meaningful speeds and rarely read speed as a number. Those cues were lost in digital tape displays, and one manufacturer reverted to a dial replica (Hollan 2000).
- **Evidence:** [B] — (Hutchins 1985; Hollan 2000).
- **Limits:** Theory and ethnography from expert, safety-critical domains. No effect sizes.

### NS-19. Use tables for comparison and align numbers on the decimal point
- **Do:** Use a table when users compare values across items or attributes. Right-justify integers and align decimals on the decimal point. Use lists for related items rather than running text. Group data by sequence of use, function, importance or frequency, and keep related data on the same page.
- **Why:** Smith & Mosier guidelines 2.3/1, 2.3/16, 2.1/19, 2.5/5 and 2.5/12–17 (Smith 1986).
- **Evidence:** [C] — (Smith 1986).
- **Limits:** Expert judgment from character-terminal displays.

### NS-20. Prefer bar charts, start aggregate scales at zero, and avoid 3-D
- **Do:** Use bar charts rather than pie charts. Start numeric scales at zero when users compare aggregate quantities. Do not use three-dimensional scaling or 3-D effects for quantitative data.
- **Why:** Bar graphs permit more accurate interpretation than pie charts (Smith 1986, 2.4.5/1). Scales should start at zero for comparing aggregates (2.4.1/6), and 3-D scaling should be restricted (2.4.1/13) (Smith 1986).
- **Evidence:** [C] — (Smith 1986).
- **Limits:** Guideline-level evidence from 1986. The zero-baseline rule is stated for comparing aggregates. The source gives no rule for other kinds of chart.

### NS-21. Give every chart a clear title and keep titles and extremes when shrinking
- **Do:** Title every chart and visualization with text that states what it shows. To raise an element's importance, make it larger, move it toward the center, give it a contrasting background or isolate it. When cropping or making thumbnails, keep the title, the main supporting text and the data extremes.
- **Why:** In click and eye-tracking data on 1,411 visualizations, text elements, especially titles, were the most looked-at and clicked elements, with click and fixation rankings correlating at rs = .96. The model also picked up data extremes. Importance-based thumbnails let users find a target in 1.96 clicks vs 3.25 with resized images (Bylinskii 2017).
- **Evidence:** [B] — (Bylinskii 2017).
- **Limits:** Clicks and annotations are attention proxies with a text bias. MTurk samples.

### NS-22. Limit the number of levels a single visual encoding must carry
- **Do:** If users must identify encoded values absolutely (which shade, which size), keep each visual dimension (hue, size, brightness, line length) to about 4–7 levels. Use at most five colors for category coding and never code by color alone. Treat brightness as two-valued. Make a larger symbol at least 1.5 times the height of the next smaller one. Put legends next to the data so users compare rather than recall. For more categories, combine dimensions or add labels.
- **Why:** Absolute judgment on one dimension averages about 2.6 bits, roughly 6.5 categories (range 3–15). Multidimensional stimuli raise total capacity, and relative judgments avoid the limit (Miller 1956). Smith & Mosier set five category colors, redundant color coding, two-level brightness and a 1.5× size step (Smith 1986, 2.6/22, 2.6/23, 2.6/26, 2.6/30). An optimization heuristic also caps color coding at four colors (Oulasvirta 2020).
- **Evidence:** [A] — (Miller 1956; Smith 1986; Oulasvirta 2020).
- **Limits:** The limit applies to absolute identification, not to scanning visible, labeled options. Sources differ slightly on the color cap (four vs five).

### NS-23. Highlight sparingly and mark what changed
- **Do:** Reserve highlighting for critical data. After automatic updates, highlight the data that changed. In scrolled or paged displays, show where the visible section sits within the whole. Indicate the active window or pane.
- **Why:** Smith & Mosier guidelines 2.6/1 (highlighting works best used sparingly), 2.7.3/2, 2.7.2/15 and 2.7.5/7 (Smith 1986). Cue-based highlighting of relevant items improves performance (Cockburn 2009).
- **Evidence:** [C] — (Smith 1986; Cockburn 2009).
- **Limits:** Expert judgment. Blinking should be reserved for urgent items (Smith 1986, 2.6/35).

## Numbers at a glance
| Parameter | Value | Grade | Source |
|---|---|---|---|
| Filter-to-display update latency (dynamic queries) | < 100 ms | B | Shneiderman 1996 |
| Attribute cardinality suited to buttons | < ~10 values | C | Shneiderman 1996 |
| Faceted refinement latency that drew complaints | 3.7–4.3 s per step (vs 0.3–0.37 s) | B | Yee 2003 |
| Simple display request response | 0.5–1.0 s | C | Smith 1986 |
| Faceted UI preferred overall | 29 of 32 users | B | Yee 2003 |
| "Find all" recall, baseline vs facets | 57% → 81%; 21% → 77% | B | Yee 2003 |
| Empty result sets, baseline vs facets | 82 vs 26 | B | Yee 2003 |
| Multi-facet query use | 19% unstructured, 45% structured tasks | B | Yee 2003 |
| Zoom animation duration | 0.3–1.0 s | B | Cockburn 2009 |
| Focus+context speed gain over O+D and zoom (one study) | up to 56% | B | Cockburn 2009 |
| Overview+detail zoom factors / fisheye in prototypes | 3–30 / about 5 | C | Shneiderman 1996 |
| Menu size that needs hierarchy | > ~20 items | B | Oulasvirta 2020 |
| Choice time growth | log2 N (Hick–Hyman) | B | Oulasvirta 2020 |
| Speed gain from expected element locations | 2× (N=48) | B | Oulasvirta 2020 |
| Steering time | MT = a + b·(A/W), linear | B | Accot 1997 |
| Steering error rate in narrow paths | 6–18% | B | Accot 1997 |
| Absolute-judgment capacity, one dimension | ~2.6 bits ≈ 6.5 categories (3–15) | A | Miller 1956 |
| Category colors | ≤ 5 (≈11 distinguishable) | C | Smith 1986 |
| Size step between symbol sizes | ≥ 1.5× height | C | Smith 1986 |
| Clicks to find target, importance thumbnails vs resized | 1.96 vs 3.25 | B | Bylinskii 2017 |
| Click vs fixation importance ranking | rs = .96 | B | Bylinskii 2017 |
| Treemap learning period | 10–20 min | C | Shneiderman 1996 |

## Common misreadings
- "Menus and navigation bars should have 7±2 items." Miller's paper concerns absolute judgment and unaided recall, not scanning visible options, and he calls the recurring seven a likely coincidence (Miller 1956). Pure memory capacity is closer to about 4 chunks (Cowan 2001). Use frequency, association and log2 N choice cost instead (Oulasvirta 2020).
- "Overview first, zoom and filter, details on demand is a complete design method." Shneiderman presents it as only a starting point (Shneiderman 1996).
- "Animated zoom makes users faster." Animation helps users form spatial models, but there is no evidence that it improves task time (Cockburn 2009).
- "Fisheye views are a good general way to fit more on screen." They hurt target acquisition and spatial judgment. Benefits appear only in specific tasks (Cockburn 2009).
- "Users prefer the fastest design, so speed decides." Users preferred overview+detail while it was slower (Cockburn 2009) and faceted search despite much slower steps (Yee 2003). Measure preference and performance separately.
- "Faceted search always beats a keyword box." For a simple single-facet task, preference split about evenly (Yee 2003).
- "Fitts' law covers menu selection." Cascading menus involve steering, whose cost is linear in path length over width (Accot 1997).

## Review checklist
- [ ] NS-1: Does the view open with an overview of the whole collection before requiring a query, with details shown only on selection?
- [ ] NS-2: Do filters update results within 100 ms, using sliders for ranges and buttons for attributes with fewer than about 10 values?
- [ ] NS-3: Can users undo or replay query steps and save or export a result set with its query settings?
- [ ] NS-4: For exploratory search over a richly described collection, are hierarchical facets offered alongside keyword search?
- [ ] NS-5: Does every refinement option show a result count, and are zero-result options hidden or disabled?
- [ ] NS-6: Can results be grouped by any facet, and do item detail pages link each metadata term to related items?
- [ ] NS-7: Can users refine a query without losing earlier finds, reach several search strategies in one step, and collect items in a session basket?
- [ ] NS-8: Does the choice of overview+detail, zoom or focus+context match the task, and does the overview reflect detail-view changes immediately?
- [ ] NS-9: Are zoom transitions animated over 0.3–1.0 s, is pan+zoom concurrent, is zoom-out visible and obvious, and are empty regions marked or unreachable?
- [ ] NS-10: Is distortion (fisheye, magnifying dock) absent wherever users must select targets or judge distance?
- [ ] NS-11: Do items keep stable positions, with search matches highlighted in place rather than moved?
- [ ] NS-12: Are menu options ordered logically or by frequency, in a single titled column, with unavailable options disabled or omitted?
- [ ] NS-13: Are frequent commands nearest the entry point, related commands adjacent, groups led by an indicative item, and menus over about 20 items split into a hierarchy?
- [ ] NS-14: Is the current position in the hierarchy shown, is "up one level" a single action, and is there an expert bypass?
- [ ] NS-15: Are cascading submenu corridors short and wide, with a closing delay or other tolerance?
- [ ] NS-16: Are there skip links, descriptive page titles, logical focus order, clear link text, at least two ways to reach each page, descriptive headings, and navigation in the same order on every page?
- [ ] NS-17: Is only task-relevant data shown, in the user's units and wording, with no mental conversion needed?
- [ ] NS-18: Where users judge trend or distance from a target, is that shown directly (rate, difference, position in range) rather than as a bare number?
- [ ] NS-19: Are comparisons shown in tables with numbers right-justified or aligned on the decimal point?
- [ ] NS-20: Are bar charts used instead of pie charts, do aggregate scales start at zero, and is 3-D absent?
- [ ] NS-21: Does every chart have a descriptive title, and do thumbnails or crops keep the title and data extremes?
- [ ] NS-22: Does each visual encoding use no more than about 4–7 levels for absolute identification, with at most five category colors, never color alone, and an adjacent legend?
- [ ] NS-23: Is highlighting reserved for critical or changed data, and is the visible section's position within the whole shown?

## Sources
- Accot, J., Zhai, S. (1997). *Beyond Fitts' law: models for trajectory-based HCI tasks*. CHI '97. https://doi.org/10.1145/258549.258760
- Bates, M. J. (1989). *The design of browsing and berrypicking techniques for the online search interface*. Online Review. https://doi.org/10.1108/eb024320
- Bylinskii, Z., et al. (2017). *Learning visual importance for graphic designs and data visualizations*. UIST '17. https://doi.org/10.1145/3126594.3126653
- Cockburn, A., Karlson, A., Bederson, B. B. (2009). *A review of overview+detail, zooming, and focus+context interfaces*. ACM Computing Surveys. https://doi.org/10.1145/1456650.1456652
- Cowan, N. (2001). *The magical number 4 in short-term memory*. Behavioral and Brain Sciences. https://doi.org/10.1017/s0140525x01003922
- Hollan, J., Hutchins, E., Kirsh, D. (2000). *Distributed cognition: toward a new foundation for HCI research*. ACM TOCHI. https://doi.org/10.1145/353485.353487
- Hutchins, E. L., Hollan, J. D., Norman, D. A. (1985). *Direct manipulation interfaces*. Human-Computer Interaction. https://doi.org/10.1207/s15327051hci0104_2
- Miller, G. A. (1956). *The magical number seven, plus or minus two*. Psychological Review. https://doi.org/10.1037/h0043158
- Oulasvirta, A., Dayama, N. R., Shiripour, M., John, M., Karrenbauer, A. (2020). *Combinatorial optimization of graphical user interface designs*. Proceedings of the IEEE. https://doi.org/10.1109/jproc.2020.2969687
- Shneiderman, B. (1996). *The eyes have it: a task by data type taxonomy for information visualizations*. IEEE Symp. Visual Languages. https://doi.org/10.1109/vl.1996.545307
- Smith, S. L., Mosier, J. N. (1986). *Guidelines for designing user interface software*. MITRE / DTIC ESD-TR-86-278. https://doi.org/10.21236/ada177198
- W3C (2023). *Web Content Accessibility Guidelines (WCAG) 2.2*. W3C Recommendation. https://www.w3.org/TR/WCAG22/
- Yee, K.-P., Swearingen, K., Li, K., Hearst, M. (2003). *Faceted metadata for image search and browsing*. CHI '03. https://doi.org/10.1145/642611.642681
