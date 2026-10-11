# Text, typography and color

> Scope: how to set, size, space, color and word on-screen text, and how to use color for coding and appeal, so text stays readable for all users and color carries meaning safely. Evidence grades: **[A]** strong — replicated, large-N, meta-analytic, or an international standard; **[B]** moderate — one solid study or converging smaller studies; **[C]** weak — expert opinion, theory, small qualitative work, or extrapolation from lab psychology to UI.

## Rules

### TX-1. Meet text contrast minimums
- **Do:** Give body text and images of text a contrast ratio of at least 4.5:1 against the background. Large-scale text (at least 18 pt, or 14 pt bold) needs at least 3:1. For enhanced (AAA) targets use 7:1 and 4.5:1. Compute the ratio as (L1 + 0.05)/(L2 + 0.05), where L1 is the lighter relative luminance; L = 0.2126R + 0.7152G + 0.0722B with each sRGB channel linearized (c ≤ 0.04045 → c/12.92, else ((c + 0.055)/1.055)^2.4). Put text over imagery on a solid background, not a translucent box.
- **Why:** WCAG 1.4.3 (AA) and 1.4.6 (AAA) set these ratios; the ratio ranges from 1:1 to 21:1 (W3C 2023). Color contrast was the second-largest cluster of expert critiques of mobile screens (655 critiques), with the most screen-level comments; experts flagged text on low-opacity boxes over images (Duan 2024 UICrit). On-screen text that was too small or low in contrast was a common complaint of low-vision users (7 of 20) (Kane 2009).
- **Evidence:** [A] — (W3C 2023; Duan 2024 UICrit; Kane 2009).
- **Limits:** Thresholds are consensus values; the standard gives no effect sizes. Exempt: inactive components, pure decoration, invisible text, text inside a picture with other significant content, and logotypes. Do not require AAA site-wide (W3C 2023).

### TX-2. Give UI components and graphics 3:1 contrast
- **Do:** Make input borders, icons, control states, focus indicators and chart elements needed for understanding at least 3:1 against adjacent colors. For an AAA focus indicator, use an area at least a 2 CSS px perimeter of the component with at least 3:1 change between focused and unfocused states.
- **Why:** WCAG 1.4.11 Non-text Contrast (AA) and 2.4.13 Focus Appearance (AAA) (W3C 2023). Figure-ground contrast also correlated with beauty ratings (r .51, web, 150 ms) (Miniukovich 2015).
- **Evidence:** [A] — (W3C 2023; Miniukovich 2015).
- **Limits:** Inactive components and unmodified user-agent controls are exempt.

### TX-3. Never use color as the only cue
- **Do:** Pair every color code with a second cue: text label, icon, shape, pattern, position or weight. Do not write instructions that depend only on color, shape, size or location. Run a color-blindness simulation of the three common types and check that meaning survives.
- **Why:** WCAG 1.4.1 Use of Color (A) and 1.3.3 Sensory Characteristics (A) (W3C 2023). Never code only by color (Smith 1986, 2.6/30). AIM includes a color-blindness simulation for this check (Oulasvirta 2018).
- **Evidence:** [A] — (W3C 2023; Smith 1986; Oulasvirta 2018).
- **Limits:** None known; applies to all screens.

### TX-4. Set line length in characters: about 55–70 for reading, longer only for scanning
- **Do:** Specify measure in characters per line (cpl), not physical width. For text meant to be read and understood, use about 55–70 cpl and never more than 80 (40 for CJK). For scan-only content (link lists, search results), up to about 85–100 cpl is acceptable. Avoid extremes near 25 cpl and 132 cpl.
- **Why:** 55 cpl gave better comprehension than 100 cpl and was rated easiest to read; 100 cpl was read fastest but only significantly faster than 25 cpl (Dyson 2004, reviewing Dyson & Kipping 1998 and Dyson & Haselgrove 2001). 85 and 100 cpl made visual search faster than 55 and 70 (e.g., 1511 ms vs 1752 ms), but users preferred shorter lines, with a large preference effect (η² = 0.224) and 70 cpl more accurate than 85 for correct rejections (Ling 2006). WCAG 1.4.8 (AAA) caps width at 80 characters (W3C 2023). Print guidance is ≤ 70 cpl (Spencer, as cited in Dyson 2004).
- **Evidence:** [B] — (Dyson 2004; Ling 2006; W3C 2023).
- **Limits:** Studies used 1980s–2005 displays, small text, young samples and mostly non-scrolling pages. Speed effects of line length are small (η² = 0.038). Window height had generally no reading-rate effect (Dyson 2004).

### TX-5. Let text scale to 200% and reflow at 320 px
- **Do:** Allow text to resize to 200% without assistive technology and without loss of content or function. At 320 CSS px width (1280 px at 400% zoom), content must reflow with no two-dimensional scrolling. Do not cap text size at a maximum. Use real text, not images of text, unless the presentation is essential (e.g., logotypes).
- **Why:** WCAG 1.4.4 Resize Text (AA), 1.4.10 Reflow (AA) and 1.4.5 Images of Text (AA) (W3C 2023). Low-vision users increased text size but settings "did not usually provide enough flexibility"; the authors recommend scaling to arbitrary size (Kane 2009).
- **Evidence:** [A] — (W3C 2023; Kane 2009).
- **Limits:** Reflow excepts maps, diagrams, video, games and data tables. Kane 2009 is a small qualitative 2009 study.

### TX-6. Survive user text-spacing overrides and set comfortable spacing
- **Do:** Ensure nothing is lost or clipped when users set line height to 1.5× font size, paragraph spacing to 2×, letter spacing to 0.12× and word spacing to 0.16×. For reading-heavy text, use line spacing of at least 1.5 within paragraphs, paragraph spacing at least 1.5× the line spacing, and left-aligned, non-justified text. Do not use fixed-height text containers.
- **Why:** WCAG 1.4.12 Text Spacing (AA) and 1.4.8 Visual Presentation (AAA) (W3C 2023). Older studies found double spacing marginally or significantly better than single (Dyson 2004).
- **Evidence:** [A] for 1.4.12 robustness; [C] for the spacing values as author defaults — (W3C 2023; Dyson 2004).
- **Limits:** 1.4.8 and 1.4.12 require that users *can* adjust presentation, not that authors use these values. Modern evidence on interlinear spacing is thin (Dyson 2004).

### TX-7. Use at least 14 pt body text for older readers
- **Do:** For audiences of older adults, set body text at 14 pt or larger, not 12 pt. Prefer a 14 pt sans serif as the default.
- **Why:** For 27 adults aged 62–83, 14 pt was more legible than 12 pt (F(1,26) = 14.10, p < .001) and preferred; both 14 pt sans serifs were preferred over all 12 pt fonts. 12 pt serif was read slower than 14 pt serif and 14 pt sans serif (Bernard 2001).
- **Evidence:** [B] — (Bernard 2001).
- **Limits:** Poster with limited statistics, 96 dpi CRT, only two sizes tested; sizes above 14 pt untested. Point size is not CSS px. Pair with TX-5 so users can go larger.

### TX-8. Avoid italic body text; default to a roman sans serif
- **Do:** Do not set body text in italics, especially for readers with dyslexia (avoid Arial Italic). Default to a roman sans serif (e.g., Helvetica, Arial, Verdana). A monospaced font is acceptable. Do not adopt "dyslexia fonts" expecting faster silent reading. Do not choose a font just because it was designed for screen.
- **Why:** For 48 readers with dyslexia, Arial Italic was slowest (34.99 s, 123% of Arial) with the longest fixations; italic vs roman fixations 0.27 vs 0.25 s; sans serif vs serif 0.24 vs 0.26 s; OpenDyslexic gave no benefit and was among the least preferred (2.57) (Rello 2013). Arial vs Times did not affect search or retrieval, but Arial was chosen by 72–74% after a visual-search task (only a 58–60% trend after information retrieval) (Ling 2006). Screen-optimized fonts did not differ from print-origin fonts (Bernard 2001). The review found no clear evidence of typeface legibility differences on screen (Dyson 2004).
- **Evidence:** [B] — (Rello 2013; Ling 2006; Bernard 2001; Dyson 2004).
- **Limits:** Rello used Spanish, 60-word texts, silent reading only and no non-dyslexic control; font-group effects on reading time were not significant (only fixation duration). Specialized fonts might help reading aloud, which was not tested.

### TX-9. Decide typography on performance, and use preference to break ties
- **Do:** When testing type, line length or layout, measure performance (speed, accuracy, comprehension) and preference separately. Where performance is equal, pick the preferred option. Where they conflict, follow the task: comprehension for reading, speed for scanning. Offer users a font or presentation choice where feasible.
- **Why:** Preference and performance diverged in every typography source: long lines faster but moderate preferred (Dyson 2004; Ling 2006); serif faster at 14 pt but sans preferred (Bernard 2001); preference vs reading time r = −0.13 (Rello 2013). Subjective effect sizes were much larger than performance effect sizes (Ling 2006).
- **Evidence:** [B] — (Dyson 2004; Ling 2006; Bernard 2001; Rello 2013).
- **Limits:** Each component study is small; the convergence is the strong part.

### TX-10. Limit category colors to about four or five
- **Do:** Use no more than 4–5 colors to code categories. If more categories exist, add labels or a second coding dimension (shape, position) instead of more hues. Prefer relative comparison (legend next to the data, side-by-side) over asking users to identify a color absolutely.
- **Why:** Color coding for data categories: no more than five colors, though about 11 are distinguishable (Smith 1986, 2.6/26). Absolute judgment on one dimension is limited to about 2.6 bits (about 6.5 categories, range 3–15); hue alone about 3.1 bits; hue plus saturation about 11–15 (Miller 1956). Rule-based layout tools use "do not use more than four colors to code information" as a heuristic (Oulasvirta 2020).
- **Evidence:** [B] — (Smith 1986; Miller 1956; Oulasvirta 2020).
- **Limits:** Miller's data are pre-1956 lab judgments, not UI tests. The ≤ 4 and ≤ 5 values are heuristics and judgment, and Oulasvirta 2020 notes such Boolean heuristics have validity problems. Relative comparison raises the limit.

### TX-11. Keep few dominant colors, but allow rich tonal range
- **Do:** Keep the number of distinct, nameable dominant colors on a screen low. Smooth color depth (tints, shades, gradients of the same hues) is fine and can raise appeal. To add perceived colorfulness without adding complexity, use a few bright accents (e.g., buttons) on a light, neutral base.
- **Why:** Color variability splits into two factors: number of dominant colors raises complexity (r .61) and lowers aesthetics (r −.47), while color depth raises aesthetics (r .45) without adding complexity (r .01) (Miniukovich 2014). Color range correlated .56 with 150 ms beauty ratings and was the strongest positive term in the web model (Miniukovich 2015). Small bright buttons on white raised perceived colorfulness without raising complexity (Reinecke 2013).
- **Evidence:** [B] — (Miniukovich 2014; Miniukovich 2015; Reinecke 2013).
- **Limits:** Miniukovich 2014 had only 10 raters; dominant colors were n.s. at 150 ms in 2015 (−.20 at 4 s). Mobile effects were weaker. The accent finding comes from model error analysis, not a test.

### TX-12. Design in monochrome first, then add color conservatively and conventionally
- **Do:** Make the layout work in grayscale before adding color. Use color conservatively. Follow conventional color meanings in the domain. Define each color code and use it identically on every screen.
- **Why:** Conservative use of color (2.6/28); add color only after the monochrome design is effective (2.6/29); conventional assignment of color codes (2.6/32); definition and consistency of display codes (2.6/6, 2.6/7) (Smith 1986).
- **Evidence:** [C] — (Smith 1986).
- **Limits:** 1986 judgment-based guidelines. Conservative color does not mean colorless; see TX-14.

### TX-13. Choose a harmonious palette and keep recoloring subtle
- **Do:** Build the palette from a harmonic hue template: analogous hues varied in saturation, plus one complementary accent. Avoid disharmonious multicolor mixes. Give frequently searched items a distinctive color, but weigh this against overall color variety.
- **Why:** Layout optimizers score color harmony with hue-wheel templates (78 precomputed harmonic sets); single-objective optimization either made everything one color (clutter) or every item a unique color (visual search), so the goals conflict (Todi 2016). Garish harmonic recolorings were disliked as "so 90s" (Todi 2016). A color-scheme change alone shifted VisAWI Colorfulness by d = 0.57; "The colors do not match" is a reverse-keyed item (Moshagen 2010). An unappealing phone with disharmonious blue, yellow, pink and grey produced slower tasks and more errors (Sonderegger 2010).
- **Evidence:** [B] — (Todi 2016; Moshagen 2010; Sonderegger 2010).
- **Limits:** Todi 2016 color demonstrations were toy cases and the designer study was qualitative (N = 10). Sonderegger 2010 manipulated more than color.

### TX-14. Aim for moderate-to-high colorfulness, tuned to the audience
- **Do:** Default to medium-to-high colorfulness with low-to-medium complexity. Lower colorfulness for highly educated audiences and for Finnish, Russian, French and German markets. Raise it for audiences such as Macedonia, Malaysia and Chile, and for under-20s. Avoid plain, colorless designs for older users. For gender-neutral products, avoid stark saturated primaries on gray.
- **Why:** Colorfulness appeal peaked at 6.1/9 overall, with smaller penalties than complexity (high vs peak d = 0.8, low vs peak d = 0.3). Peaks: Finland, Russia, France, Germany 3.6–4.4; US 6.1; Macedonia 7.6; Chile and Malaysia 6.9; PhD 5.0 vs pre-high-school 6.9; male 5.8 vs female 6.3; under-20 and over-51 6.5. Older users found colorless sites least appealing (d 1.8) (Reinecke 2014). Colorfulness plays a minor role relative to complexity (Reinecke 2013).
- **Evidence:** [B] — (Reinecke 2014; Reinecke 2013).
- **Limits:** 500 ms first impressions from self-selected online volunteers. Peaks are on a model-specific scale. Male-preferred sites used saturated primaries on gray or white; female-preferred sites used more homogeneous schemes (Reinecke 2014).

### TX-15. Write UI text in the user's words, plainly
- **Do:** Use the users' task vocabulary, not programmer jargon. Write task-oriented, short, simple sentences. Use affirmative statements and active voice. Speak directly to the user. Use conventional mixed case, not all caps. Minimize abbreviations; where unavoidable, provide the expanded form. Present related items as lists, not running text. If text needs reading ability above lower secondary education, provide a simpler version or supplement.
- **Why:** Familiar wording (2.0/12, 4.0/16), minimal abbreviation (2.0/16), mixed case (2.1/6), clarity of wording (2.1/11), simple sentence structure (2.1/13), affirmative sentences (2.1/16), active voice (2.1/17), lists for related items (2.1/19), task-oriented wording (4.0/17) and speaking directly to users (4.0/19) (Smith 1986). Simple improvements including consistent wording, explicit messages and no abbreviations gave 25% faster data entry and 25% fewer errors (Keister & Gallaway 1983, as cited in Smith 1986). WCAG 3.1.3, 3.1.4 and 3.1.5 (AAA) address jargon, abbreviations and reading level (W3C 2023).
- **Evidence:** [C] — (Smith 1986; W3C 2023).
- **Limits:** Mostly expert judgment from terminal-era systems. The 25% figures are a secondary citation.

### TX-16. Word error and status messages so they can be acted on
- **Do:** Say what is wrong and what the user can do, specifically, in task terms. Offer correct alternatives. Keep it brief, with more detail on request. Use neutral wording: no blame, no humor, no personified computer. Write messages that still make sense read aloud; avoid regexes and jargon in user-facing errors.
- **Why:** Informative, specific, task-oriented, advisory, brief, neutral and multilevel error messages (4.3/1–4.3/7) (Smith 1986). Screen-reader users found regex- and jargon-laden error messages hard to verbalize; one spent 6 hours on a 30-minute task because of an unclear error (Sampath 2021). WCAG 3.3.1 and 3.3.3 require errors described in text with known correction suggestions (W3C 2023).
- **Evidence:** [B] — (Smith 1986; Sampath 2021; W3C 2023).
- **Limits:** Sampath 2021 is qualitative (N = 12) on one CLI.

### TX-17. Keep copy error-free and understated to protect credibility
- **Do:** Proofread all copy; a single typo is a credibility cost. Use an understated, non-sensational tone. Avoid slang and hard "marketing language". State clearly who runs the product and why.
- **Why:** A typo scored −1.28 on a −3..+3 credibility scale (Fogg 2001). Tone of the writing was mentioned in 9.0% of credibility comments; slang and marketing language hurt credibility (Fogg 2003).
- **Evidence:** [B] — (Fogg 2001; Fogg 2003).
- **Limits:** Self-report web credibility data from 1999–2003.

### TX-18. Format numbers and tables for comparison
- **Do:** Use tables when users compare data. Right-justify numbers or align them on the decimal point. Show data in the units users need, labelled in the header, so users never convert.
- **Why:** Tables for data comparison (2.3/1), justification of numeric data (2.3/16), data in usable form (2.0/3), units in labels (1.4/21) (Smith 1986).
- **Evidence:** [C] — (Smith 1986).
- **Limits:** Judgment-based guidance.

### TX-19. Use automated copy review, with a human check
- **Do:** Let an LLM reviewer correct grammar and replace jargon in on-screen copy and propose replacement text. Keep a human to accept or reject changes, and do not let it demand labels on universally recognized icons (close ✕, cart or bag).
- **Why:** Text and grammar fixes with replacement copy were a strength noted by 12 of 12 experts; over-application of guidelines without context (e.g., labels on universal icons) was a weakness noted by 12 of 12 (Duan 2024 LLM feedback). GPT-4 precision was 0.603 vs 0.829 for experts (Duan 2024 LLM feedback). Text readability (font size and weight, 591 critiques) is a core critique category (Duan 2024 UICrit).
- **Evidence:** [B] — (Duan 2024 LLM feedback; Duan 2024 UICrit).
- **Limits:** GPT-4 in 2023 on static mobile screens; newer models may differ.

## Numbers at a glance
| Parameter | Value | Grade | Source |
|---|---|---|---|
| Text contrast, AA: normal / large | ≥ 4.5:1 / ≥ 3:1 | A | W3C 2023 (1.4.3) |
| Text contrast, AAA: normal / large | ≥ 7:1 / ≥ 4.5:1 | A | W3C 2023 (1.4.6) |
| Large-scale text | ≥ 18 pt, or ≥ 14 pt bold | A | W3C 2023 |
| Non-text contrast (components, states, graphics) | ≥ 3:1 | A | W3C 2023 (1.4.11) |
| Contrast ratio formula | (L1 + 0.05)/(L2 + 0.05); range 1:1–21:1 | A | W3C 2023 |
| Relative luminance | 0.2126R + 0.7152G + 0.0722B (linearized sRGB) | A | W3C 2023 |
| Focus indicator (AAA) | ≥ 2 CSS px perimeter area, ≥ 3:1 change | A | W3C 2023 (2.4.13) |
| Text resize without loss | 200% | A | W3C 2023 (1.4.4) |
| Reflow width / height | 320 CSS px / 256 CSS px (= 400% zoom of 1280) | A | W3C 2023 (1.4.10) |
| Text spacing overrides: line / paragraph / letter / word | 1.5× / 2× / 0.12× / 0.16× font size | A | W3C 2023 (1.4.12) |
| Visual presentation (AAA): width / line spacing / paragraph spacing | ≤ 80 chars (40 CJK) / ≥ 1.5 / ≥ 1.5× line spacing; not justified | A | W3C 2023 (1.4.8) |
| Line length for reading | ~55–70 cpl | B | Dyson 2004; Ling 2006 |
| Line length for fast scanning | ~85–100 cpl | B | Ling 2006; Dyson 2004 |
| Line lengths to avoid | ~25 cpl and ~132 cpl | C | Dyson 2004 |
| Body size for older adults | ≥ 14 pt | B | Bernard 2001 |
| Arial Italic reading time vs Arial (dyslexia) | 123% (34.99 s vs 28.35 s) | B | Rello 2013 |
| Preference vs reading time (dyslexia) | r = −0.13 | B | Rello 2013 |
| Category colors | ≤ 5 (≈ 11 distinguishable) | C | Smith 1986 |
| Category colors, optimizer heuristic | ≤ 4 | C | Oulasvirta 2020 |
| Absolute-judgment span, one dimension | ~2.6 bits ≈ 6.5 levels (3–15) | C | Miller 1956 |
| Hue + saturation distinguishable levels | ~11–15 | C | Miller 1956 |
| Dominant colors vs aesthetics / complexity | r −.47 / .61 | B | Miniukovich 2014 |
| Color depth vs aesthetics / complexity | r .45 / .01 | B | Miniukovich 2014 |
| Colorfulness appeal peak (1–9 model scale) | 6.1 overall; 3.6–7.6 by subgroup | B | Reinecke 2014 |
| Color-scheme change effect on VisAWI Colorfulness | d = 0.57 | B | Moshagen 2010 |
| Credibility effect of a typo | −1.28 (−3..+3) | B | Fogg 2001 |
| LLM UI critique precision vs experts | 0.603 vs 0.829 | B | Duan 2024 LLM feedback |

## Common misreadings
- "Long lines are always bad." — Long lines (85–100 cpl) were faster for scanning and search; moderate lines won on comprehension and preference (Dyson 2004; Ling 2006).
- "The font users prefer is the one they read best." — Preference and reading time were almost unrelated (r = −0.13), and preferred options were often not the fastest (Rello 2013; Dyson 2004).
- "Dyslexia fonts help dyslexic readers." — OpenDyslexic was no faster for silent reading and was among the least preferred (Rello 2013).
- "Screen-optimized fonts are more legible." — Georgia and Verdana did not differ from Times and Arial at 12 or 14 pt (Bernard 2001).
- "WCAG 1.4.8 and 1.4.12 values are author defaults." — They require that users can apply these settings without loss; they do not mandate that authors ship them (W3C 2023).
- "4.5:1 and 80 characters are empirically derived thresholds." — They are consensus values; WCAG gives no effect sizes (W3C 2023).
- "7 ± 2 is the limit for colors or items." — Miller's limits concern absolute judgment and unaided recall; he calls the recurring seven a likely coincidence. Single-dimension absolute judgment averages about 6.5 levels (Miller 1956).
- "More color makes a design look worse." — Many dominant colors hurt, but color depth and range helped, and appeal peaked at moderate-to-high colorfulness (Miniukovich 2014; Miniukovich 2015; Reinecke 2014).

## Review checklist
- [ ] TX-1: Does all text meet 4.5:1 (normal) or 3:1 (large), with text over images on a solid background?
- [ ] TX-2: Do borders, icons, states, focus indicators and needed chart elements reach 3:1 against neighbors?
- [ ] TX-3: Is every color-coded meaning also carried by text, icon, shape or position, and does it survive a color-blindness simulation?
- [ ] TX-4: Is reading text set at about 55–70 cpl and never over 80 (40 CJK), with longer lines only for scan-only content?
- [ ] TX-5: Does text resize to 200% and reflow at 320 CSS px without loss, with real text instead of images of text?
- [ ] TX-6: Does the layout survive 1.5/2/0.12/0.16 spacing overrides, with left-aligned, non-justified reading text?
- [ ] TX-7: If the audience includes older adults, is body text at least 14 pt?
- [ ] TX-8: Is body text roman (not italic), in a plain sans serif or other tested face, with no reliance on "dyslexia fonts"?
- [ ] TX-9: Were typography choices tested on performance and preference separately, with preference used only to break ties?
- [ ] TX-10: Are category colors limited to about 4–5, with labels or a second dimension for more categories?
- [ ] TX-11: Is the number of distinct dominant colors low, with variation achieved through tints and accents?
- [ ] TX-12: Does the design work in grayscale, with color codes conventional, defined and consistent across screens?
- [ ] TX-13: Does the palette follow a harmonic scheme (analogous plus one accent) without disharmonious mixes?
- [ ] TX-14: Is colorfulness moderate-to-high and adjusted for the stated audience and market?
- [ ] TX-15: Is copy in user vocabulary, short, affirmative, active, mixed case, with few abbreviations and lists for related items?
- [ ] TX-16: Do error messages state the problem and the fix, specifically, neutrally, and in a form that reads well aloud?
- [ ] TX-17: Is the copy free of typos, slang and hype, and is the owner of the product clear?
- [ ] TX-18: Are comparable data in tables, numbers right- or decimal-aligned, and units in the labels?
- [ ] TX-19: If an LLM reviewed the copy, did a human accept its changes and reject label demands on universal icons?

## Sources
- Bernard, M., Liao, C. H., Mills, M. (2001). *The effects of font type and size on the legibility and reading time of online text by older adults*. CHI EA '01. https://doi.org/10.1145/634067.634173
- Duan, P., et al. (2024). *UICrit: enhancing automated design evaluation with a UI critique dataset*. UIST '24. https://doi.org/10.1145/3654777.3676381
- Duan, P., Warner, J., Zhang, Y., Hsieh, G. (2024). *Generating automatic feedback on UI mockups with large language models*. CHI '24. https://doi.org/10.1145/3613904.3642782
- Dyson, M. C. (2004). *How physical text layout affects reading from screen*. Behaviour & Information Technology. https://doi.org/10.1080/01449290410001715714
- Fogg, B. J., et al. (2001). *What makes web sites credible? A report on a large quantitative study*. CHI '01. https://doi.org/10.1145/365024.365037
- Fogg, B. J., et al. (2003). *How do users evaluate the credibility of web sites?* DUX '03. https://doi.org/10.1145/997078.997097
- Kane, S. K., Jayant, C., Wobbrock, J. O., Ladner, R. E. (2009). *Freedom to roam: mobile device adoption and accessibility for people with visual and motor disabilities*. ASSETS '09. https://doi.org/10.1145/1639642.1639663
- Ling, J., van Schaik, P. (2006). *The influence of font type and line length on visual search and information retrieval in web pages*. IJHCS. https://doi.org/10.1016/j.ijhcs.2005.08.015
- Miller, G. A. (1956). *The magical number seven, plus or minus two*. Psychological Review. https://doi.org/10.1037/h0043158
- Miniukovich, A., De Angeli, A. (2014). *Quantification of interface visual complexity*. AVI '14. https://doi.org/10.1145/2598153.2598173
- Miniukovich, A., De Angeli, A. (2015). *Computation of interface aesthetics*. CHI '15. https://doi.org/10.1145/2702123.2702575
- Moshagen, M., Thielsch, M. T. (2010). *Facets of visual aesthetics*. IJHCS. https://doi.org/10.1016/j.ijhcs.2010.05.006
- Oulasvirta, A., et al. (2018). *Aalto Interface Metrics (AIM)*. UIST '18 Adjunct. https://doi.org/10.1145/3266037.3266087
- Oulasvirta, A., Dayama, N. R., Shiripour, M., John, M., Karrenbauer, A. (2020). *Combinatorial optimization of graphical user interface designs*. Proceedings of the IEEE. https://doi.org/10.1109/jproc.2020.2969687
- Reinecke, K., et al. (2013). *Predicting users' first impressions of website aesthetics with a quantification of perceived visual complexity and colorfulness*. CHI '13. https://doi.org/10.1145/2470654.2481281
- Reinecke, K., Gajos, K. Z. (2014). *Quantifying visual preferences around the world*. CHI '14. https://doi.org/10.1145/2556288.2557052
- Rello, L., Baeza-Yates, R. (2013). *Good fonts for dyslexia*. ASSETS '13. https://doi.org/10.1145/2513383.2513447
- Sampath, H., Merrick, A., Macvean, A. (2021). *Accessibility of command line interfaces*. CHI '21. https://doi.org/10.1145/3411764.3445544
- Smith, S. L., Mosier, J. N. (1986). *Guidelines for designing user interface software*. MITRE / DTIC ESD-TR-86-278. https://doi.org/10.21236/ada177198
- Sonderegger, A., Sauer, J. (2010). *The influence of design aesthetics in usability testing*. Applied Ergonomics. https://doi.org/10.1016/j.apergo.2009.09.002
- Todi, K., Weir, D., Oulasvirta, A. (2016). *Sketchplore: sketch and explore with a layout optimiser*. DIS '16. https://doi.org/10.1145/2901790.2901817
- W3C (2023). *Web Content Accessibility Guidelines (WCAG) 2.2*. W3C Recommendation. https://www.w3.org/TR/WCAG22/
