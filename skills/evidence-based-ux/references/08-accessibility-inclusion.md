# Accessibility and inclusive design

> A WCAG 2.2 Level AA baseline as the floor for every screen, plus research-based practice beyond WCAG for situational impairments, eyes-free touch, motor adaptation, text-based tools, dyslexia, older adults, and how to weigh accessibility evidence. Evidence grades: **[A]** strong — replicated, large-N, meta-analytic, or an international standard; **[B]** moderate — one solid study or converging smaller studies; **[C]** weak — expert opinion, theory, small qualitative work, or extrapolation from lab psychology to UI.

Rules AX-1 to AX-11 restate the WCAG 2.2 Level A and AA success criteria (SC) most relevant to UI design, grouped by the four principles: Perceivable, Operable, Understandable, Robust. Criteria marked **(new in 2.2)** did not exist in WCAG 2.1. Rules AX-12 to AX-20 cover research beyond WCAG.

## Rules

### AX-1. Treat WCAG 2.2 AA as the floor, not the goal
- **Do:** Meet every Level A and AA success criterion on every page, in every responsive variation, and across every step of a complete process (all checkout steps, not just the first). Adopt individual AAA criteria where they fit. Do not require AAA conformance site-wide.
- **Why:** AA conformance means all A plus all AA criteria are met, and conformance applies to full pages and complete processes. W3C does not recommend AAA as a site-wide requirement because some content cannot meet all AAA criteria. Four criteria apply even to content not relied on for conformance: 1.4.2, 2.1.2, 2.3.1 and 2.2.2 (W3C 2023).
- **Evidence:** [A] — (W3C 2023).
- **Limits:** WCAG states it will not address every user need and gives only some accommodation for learning and cognitive disabilities. Its numeric thresholds (4.5:1, 24 px, 44 px, 80 characters) are consensus values with no reported effect sizes. It is written for web content, so native apps and CLIs need interpretation (Sampath 2021).

### AX-2. Perceivable: give every non-text element a text equivalent and expose structure in code
- **Do:** Give all non-text content a text alternative, and give every control and input a name that describes its purpose (1.1.1, A). Make decorative content ignorable by assistive technology. Make visual structure and relationships (headings, lists, tables, label–field pairs) programmatically determinable (1.3.1, A). Keep reading order programmatically correct where order matters (1.3.2, A). Never write instructions that depend only on shape, color, size, position, orientation or sound (1.3.3, A). Expose input purpose for fields that collect user data, for example with autocomplete tokens (1.3.5, AA). Provide captions for prerecorded video (1.2.2, A) and live video (1.2.4, AA), and audio description for prerecorded video (1.2.5, AA).
- **Why:** These are A and AA criteria of the standard (W3C 2023). In a CLI study, tables without row and column semantics forced screen-reader users to memorize column order, and ASCII-art borders were read aloud as noise (Sampath 2021).
- **Evidence:** [A] — (W3C 2023; Sampath 2021).
- **Limits:** "Programmatically determinable" depends on the platform's accessibility API. Test with actual assistive technology.

### AX-3. Perceivable: meet contrast minimums and never use color alone
- **Do:** Give text and images of text a contrast ratio of at least 4.5:1, and large-scale text (≥ 18 pt, or ≥ 14 pt bold) at least 3:1 (1.4.3, AA). Give UI component boundaries, states, focus indicators, icons and chart elements needed for understanding at least 3:1 against adjacent colors (1.4.11, AA). Never use color as the only means of conveying information, indicating an action or distinguishing an element (1.4.1, A). Compute contrast as (L1 + 0.05)/(L2 + 0.05) using sRGB relative luminance.
- **Why:** Normative A and AA criteria (W3C 2023). Low-contrast and too-small on-screen text was among the problems reported by people with visual impairments (Kane 2009).
- **Evidence:** [A] — (W3C 2023; Kane 2009).
- **Limits:** Inactive components, pure decoration and logotypes are exempt. AAA raises text to 7:1 and large text to 4.5:1 (1.4.6).

### AX-4. Perceivable: let text scale, reflow and respace without loss
- **Do:** Let text resize to 200% without assistive technology and without losing content or function (1.4.4, AA). Avoid two-dimensional scrolling at a width of 320 CSS px (equal to 1280 px at 400% zoom) for vertically scrolling content, or a height of 256 CSS px for horizontally scrolling content (1.4.10, AA). Lose nothing when users set line height to 1.5× font size, paragraph spacing to 2×, letter spacing to 0.12× and word spacing to 0.16× (1.4.12, AA). Do not lock orientation unless it is essential (1.3.4, AA). Use real text rather than images of text (1.4.5, AA). Beyond the minimum, let text scale to arbitrary sizes rather than capping it.
- **Why:** Normative criteria (W3C 2023). Seven low-vision participants raised text size, but settings did not usually give enough flexibility, and the authors recommend text scalable to an arbitrary size with scrolling or zooming as needed (Kane 2009).
- **Evidence:** [A] — (W3C 2023; Kane 2009).
- **Limits:** Maps, diagrams, video, games and data tables are excepted from reflow. 1.4.12 requires that layouts survive user overrides, not that authors use those values.

### AX-5. Perceivable: make hover and focus content dismissible, hoverable and persistent
- **Do:** For tooltips, popovers and menus that appear on hover or focus, let users dismiss them without moving pointer or focus (for example with Esc), let the pointer move onto them without them disappearing, and keep them visible until the trigger is removed, the user dismisses them, or they are no longer valid (1.4.13, AA). Let users pause, stop or control the volume of audio that plays automatically for more than 3 s (1.4.2, A).
- **Why:** Normative criteria (W3C 2023).
- **Evidence:** [A] — (W3C 2023).
- **Limits:** None stated beyond the criteria's own exceptions.

### AX-6. Operable: make everything work by keyboard with a visible, unobscured focus
- **Do:** Make all functionality operable through a keyboard interface without specific keystroke timings (2.1.1, A). Never trap focus; if leaving a component needs more than arrow, Tab or standard exit keys, tell the user how (2.1.2, A). Let single-character shortcuts be turned off, remapped or limited to when their component has focus (2.1.4, A). Keep focus order meaningful (2.4.3, A). Show a visible focus indicator (2.4.7, AA). Make sure sticky headers, footers and overlays never hide the focused component entirely (2.4.11, AA, **new in 2.2**). As a target, make the focus indicator at least the area of a 2 CSS px perimeter with at least 3:1 change between focused and unfocused states (2.4.13, AAA, new in 2.2).
- **Why:** Normative criteria (W3C 2023).
- **Evidence:** [A] — (W3C 2023).
- **Limits:** Path-dependent functions (such as freehand drawing) are excepted from 2.1.1. 2.4.13 is AAA, so treat it as a strong recommendation, not a floor.

### AX-7. Operable: offer simple-pointer alternatives to gestures, drags and motion
- **Do:** Give every multipoint or path-based gesture a single-pointer, non-path alternative (2.5.1, A). Fire single-pointer actions on the up-event, or allow abort or undo (2.5.2, A). Make the accessible name contain the visible label text, ideally at its start (2.5.3, A). Give motion-triggered functions (shake, tilt) a UI control and let motion response be disabled (2.5.4, A). Make every drag operation achievable with single-pointer actions without dragging (2.5.7, AA, **new in 2.2**).
- **Why:** Normative criteria (W3C 2023). Blind users performed gestures about twice as slowly as sighted users (925.90 vs 462.58 ms) with larger, more variable shapes (Kane 2011). Barrier pointing combined with lift-off selection helped a user with cerebral palsy (Wobbrock 2011), and it was the selection method in thumb-target studies (Parhi 2006).
- **Evidence:** [A] — (W3C 2023; Kane 2011; Wobbrock 2011; Parhi 2006).
- **Limits:** Gestures and drags that are essential to the function are excepted.

### AX-8. Operable: size touch and pointer targets above the minimum, larger for thumbs and motor impairment
- **Do:** Make pointer targets at least 24 × 24 CSS px, or space smaller targets so a 24 px circle centered on each does not intersect another target or another small target's circle (2.5.8, AA, **new in 2.2**). Aim for 44 × 44 CSS px (2.5.5, AAA). For one-handed thumb use, make single-tap targets at least 9.2 mm and keys for sequential entry at least 9.6 mm, and use larger targets when speed matters (gains continue to about 11.5 mm). For blind or motor-impaired users, enlarge targets further or let users touch near a target, explore, then confirm.
- **Why:** WCAG sets 24 px (AA) and 44 px (AAA) as consensus values (W3C 2023). In a 20-person thumb study, errors at 9.6 mm did not differ from 11.5 mm, the 2-SD hit spread at 9.6 mm was 9.1 × 8.9 mm, and serial entry had higher error rates than single taps at every size (Parhi 2006). Blind users' touches landed 110.97 px from the target vs 48.84 px for sighted users (Kane 2011). SUPPLE's interfaces adapted to measured motor performance made motor-impaired users 28% faster and 73% more accurate (Wobbrock 2011).
- **Evidence:** [A] for the WCAG floor — (W3C 2023); [B] for the mm values and larger targets — (Parhi 2006; Kane 2011; Wobbrock 2011).
- **Limits:** CSS px and mm are not directly comparable. Convert via device density. Parhi's sample was young, mostly male and right-handed, standing still, on a 2006 PDA. Mirror location advice for left-handed users.

### AX-9. Operable: give users control over time, movement and flashing
- **Do:** For each time limit, let the user turn it off, adjust it to at least 10× the default, or warn before expiry and give at least 20 s to extend with a simple action, at least 10 times (2.2.1, A). Let users pause, stop or hide moving, blinking or scrolling content that starts automatically and lasts more than 5 s, and auto-updating content (2.2.2, A). Never flash more than 3 times in any 1 s unless below the general and red flash thresholds (2.3.1, A). Let users disable motion animation triggered by interaction unless essential (2.3.3, AAA).
- **Why:** Normative criteria (W3C 2023). Several participants had conditions that fluctuated with stress, fatigue, weather or medication (Kane 2009), so the time a task needs varies.
- **Evidence:** [A] — (W3C 2023).
- **Limits:** Real-time events, essential limits and limits over 20 h are excepted from 2.2.1.

### AX-10. Operable and Understandable: keep navigation, help and naming consistent and predictable
- **Do:** Provide a skip mechanism for repeated blocks (2.4.1, A), descriptive page titles (2.4.2, A), link text whose purpose is clear in context (2.4.4, A), more than one way to find a page (2.4.5, AA) and descriptive headings and labels (2.4.6, AA). Set the page language (3.1.1, A) and the language of passages in other languages (3.1.2, AA). Never change context on focus (3.2.1, A) or on input without prior warning (3.2.2, A). Keep repeated navigation in the same relative order (3.2.3, AA), give the same function the same name everywhere (3.2.4, AA), and keep repeated help mechanisms (contact details, chat, self-help) in the same relative order across pages (3.2.6, A, **new in 2.2**).
- **Why:** Normative criteria (W3C 2023). See 07-navigation-search-data-display.md for menu and search structure.
- **Evidence:** [A] — (W3C 2023).
- **Limits:** Steps in a process are excepted from 2.4.5.

### AX-11. Understandable: identify errors in text, prevent costly mistakes, and drop memory tests
- **Do:** Identify and describe detected errors in text (3.3.1, A). Provide labels or instructions for input (3.3.2, A). Suggest corrections when known (3.3.3, AA). For legal, financial or data-changing submissions, make them reversible, checked with a chance to correct, or confirmed after review (3.3.4, AA). Auto-fill or offer for selection information the user already entered in the same process (3.3.7, A, **new in 2.2**). Do not require a cognitive function test (remembering a password, solving a puzzle) at any login step unless an alternative or assisting mechanism is offered: allow password managers and paste (3.3.8, AA, **new in 2.2**). Expose status messages to assistive technology without moving focus (4.1.3, AA). Make name, role, state and value of every component programmatically available and announce changes (4.1.2, A).
- **Why:** Normative criteria (W3C 2023). 4.1.1 Parsing is obsolete and removed in 2.2. One CLI user spent 6 hours on a 30-minute task because of an unclear error message, and another created duplicate resources because no confirmation was shown (Sampath 2021).
- **Evidence:** [A] — (W3C 2023; Sampath 2021).
- **Limits:** 3.3.8 allows object recognition and personal-content tests at AA. The AAA version (3.3.9) removes those exceptions.

### AX-12. When users perform poorly, change the system, not the user
- **Do:** Design around what users can do. Where performance is poor, adapt the interface (target size, spacing, pointer gain, timeouts, key debounce) instead of requiring retraining or add-on hardware. Base adaptations on measured or modeled user performance.
- **Why:** Ability-based design names ability and accountability as its two required principles. Projects built this way showed SUPPLE's generated UIs 28% faster and 73% more accurate for motor-impaired users, Angle Mouse more than 10% higher throughput and about 18% higher accuracy with no cost to nondisabled users, and time-based key filtering cutting typing errors by 80% (Wobbrock 2011). SUPPLE's 28% speed gain is also reported in an optimization survey (N=11) (Oulasvirta 2020).
- **Evidence:** [B] — (Wobbrock 2011; Oulasvirta 2020).
- **Limits:** The framework itself is untested, the examples are mostly the authors' own and mostly motor impairment, and SUPPLE used per-user models because Fitts' law fit poorly. Severe impairments may still need specialized solutions.

### AX-13. Make every adaptation visible, previewable and reversible
- **Do:** When the system adapts or offers to adapt itself, let users inspect, preview, override, undo, revert and save the adaptation. Suggest changes rather than applying them silently.
- **Why:** Transparency is one of the seven ability-based design principles, needed because adaptive UIs can be unpredictable. Only 6 of 14 example projects upheld it (Wobbrock 2011).
- **Evidence:** [C] — (Wobbrock 2011).
- **Limits:** A principle, not a tested result.

### AX-14. Design for situational impairments and changing abilities
- **Do:** Assume users may be walking, in glare or dim light, wearing gloves, in crowds or noise, or fatigued, and that some users' abilities fluctuate or decline over time. Keep presentation adjustable (text size, contrast, input modality). Consider a minimal-attention mode or context-triggered adaptation, but validate it with users before shipping. Let users configure settings in a calm setting (at home, from a computer) before using them on the go.
- **Why:** Walking reduced motor control and awareness, bright or dim light made screens unreadable for 5 low-vision participants, and 4 participants each had fluctuating or progressive conditions (Kane 2009). Situational impairments parallel health-related ones (Wobbrock 2011).
- **Evidence:** [C] — (Kane 2009; Wobbrock 2011).
- **Limits:** Walking UIs that enlarged text and targets gave mixed results (Wobbrock 2011). Automatic context adaptation is not yet well supported.

### AX-15. Build accessibility into mainstream software, with discreet output options
- **Do:** Deliver accessibility features (screen reader support, magnification, voice input, large targets) in the standard product on commodity devices rather than relying on special devices. Do not regress accessibility between versions. Offer private output alternatives (single earbud, haptics) where speech or visible magnifiers would be awkward in public.
- **Why:** People with visual and motor disabilities often chose mainstream devices, 5 citing cost. The most requested features were screen reader (9), voice input (8), large buttons (7) and magnification (6). Three participants said newer phones were less accessible than older ones. Speakerphone and talking devices were awkward in public, and one participant avoided using a magnifier in public (Kane 2009). No more than 60% of people who need access technology use it, and specialized systems have high abandonment (Wobbrock 2011).
- **Evidence:** [B] — (Kane 2009; Wobbrock 2011).
- **Limits:** Kane 2009 is a qualitative study of 20 US participants before mature built-in mobile accessibility.

### AX-16. For eyes-free touch, use edges and corners, relax accuracy, and avoid speed and print-symbol gestures
- **Do:** Place critical functions on screen edges and corners. Reduce location-accuracy demands with larger targets or touch-to-explore then confirm (for example a second-finger tap). Do not use gesture speed as a recognition feature or parameter (such as kinetic scrolling) in eyes-free modes. Avoid print letters, digits and symbols as gestures, or offer alternatives and training. Make recognizers tolerant of unclosed shapes, wavy strokes and size variance. Consider familiar spatial layouts (QWERTY, phone keypad) for eyes-free input. Use physical screen edges as barriers for hard-to-hit targets.
- **Why:** Blind participants made 61.1% of edge gestures and 64.8% of corner gestures. Their gestures were about 2× slower, larger and more variable, and landed 110.97 px from target vs 48.84 px. Recognizer accuracy was lower for their gestures, and 2 blind participants skipped print-symbol gestures they did not know. Nine of 10 used QWERTY-key metaphors (Kane 2011). Barrier pointing along screen edges with lift-off cut one user's error rate from 66.7% to 13.3% and made him 48.5% faster, and Slide Rule's second-finger tap was adopted into VoiceOver (Wobbrock 2011).
- **Evidence:** [B] — (Kane 2011; Wobbrock 2011).
- **Limits:** Kane 2011 had 10 blind and 10 sighted participants who differed in age (49 vs 29), on a tablet. Elicitation shows preference, not efficiency. Barrier pointing is a single case.

### AX-17. Do not assume text-based interfaces are accessible; structure output and announce status
- **Do:** For CLIs, logs, terminals and other text-heavy tools: provide all documentation as HTML with real heading levels. Let long output export to text or HTML. Document each command's output structure in advance. Offer tables as CSV, HTML or key–value pairs. Report explicit success or failure for every command, and never rely on silence as success. Announce progress as text, not spinners or character-based bars. Avoid ASCII-art decoration. Write error messages that make sense read aloud and say what to do next.
- **Why:** Screen-reader developers took 129 min vs 21 min anticipated to create a VM and 132 vs 33 min to deploy a container. Spinners were read aloud as characters, ASCII table borders were described as very annoying, silent success led one user to create duplicate resources, and one user spent 6 hours on a 30-minute task because of an unclear error (Sampath 2021).
- **Evidence:** [B] — (Sampath 2021).
- **Limits:** 12 participants, one CLI (gcloud), Windows and JAWS only, self-reported times. Text and keyboard operability meet only a small subset of WCAG.

### AX-18. For readers with dyslexia, avoid italics and prefer roman sans-serif fonts
- **Do:** Do not set body text in italics. Prefer roman sans-serif fonts such as Helvetica, Arial or Verdana; a monospaced font such as Courier is acceptable. Do not assume a dyslexia-specific font helps. Let users choose their font.
- **Why:** In an eye-tracking study of 48 readers with dyslexia, Arial Italic was slowest (34.99 s, 123% of Arial's 28.35 s) and had the longest fixations. Italic vs roman fixations were 0.27 vs 0.25 s, and serif vs sans 0.26 vs 0.24 s. OpenDyslexic gave no benefit and was among the least preferred fonts. Preference and reading time correlated only r = −0.13 (Rello 2013).
- **Evidence:** [B] — (Rello 2013).
- **Limits:** Spanish texts of 60 words, silent reading only, single sessions, no non-dyslexic control. Serif, monospace and italic groupings affected fixation duration but not reading time. Text was held at 14 pt, left-aligned, ≤ 70 characters per line, black on white; those settings were not tested.

### AX-19. For older adults, use at least 14 pt body text and test visual complexity with them
- **Do:** Set body text for older readers at 14 pt or larger. A 14-pt sans serif is the preferred compromise. Do not assume older users want the plainest possible design: test complexity and colorfulness with the actual audience.
- **Why:** Among 27 adults aged 62–83, 14 pt was significantly more legible than 12 pt, and both 14-pt sans serifs were preferred over all 12-pt fonts. Screen-optimized fonts made no difference (Bernard 2001). In one study, participants over 45 liked low-complexity sites more (Reinecke 2013). In a much larger study (39,975 participants), preferred complexity rose with age (4.7 for over-50s vs 4.1–4.2 for ages 12–40), and older users found plain, colorless sites least appealing (Reinecke 2014).
- **Evidence:** [B] — (Bernard 2001; Reinecke 2013; Reinecke 2014).
- **Limits:** Bernard is a poster with two sizes on a 96 dpi CRT and excluded vision worse than 20/40. Point size is not the same as CSS px. The two Reinecke studies conflict on age and complexity; the larger 2014 study leans toward moderate complexity and some color for older users. Both measure 500 ms first impressions, not usability.

### AX-20. Weigh accessibility evidence by population and involve disabled people directly
- **Do:** Do not generalize findings from one disability group to another (for example from blind and low-vision users to motor, cognitive, autistic or deaf users), or to people with multiple disabilities. Treat single-study numeric thresholds as provisional. Involve disabled people throughout design and testing, in sustained participation rather than one session. Use proxies (carers, experts) only with justification. Check design goals against what the community wants. Do not treat nondisabled performance as the norm disabled users must reach.
- **Why:** In 506 CHI and ASSETS accessibility papers (2010–2019), 43.5% focused on blind and low-vision users, 94.5% of those on that group alone, only 7.1% covered more than one community, and multiple disabilities were under 1.0%. The median sample of disabled or older participants was 13. Participatory design appeared in 10.3% of papers, and proxies in 8.0% (Mack 2021).
- **Evidence:** [A] — (Mack 2021).
- **Limits:** Covers CHI and ASSETS only. Category boundaries (cognitive, IDD, autism) are fuzzy.

## Numbers at a glance
| Parameter | Value | Grade | Source |
|---|---|---|---|
| Text contrast, AA (1.4.3) | ≥ 4.5:1; large text ≥ 3:1 | A | W3C 2023 |
| Text contrast, AAA (1.4.6) | ≥ 7:1; large text ≥ 4.5:1 | A | W3C 2023 |
| Large-scale text | ≥ 18 pt, or ≥ 14 pt bold | A | W3C 2023 |
| Non-text contrast (1.4.11) | ≥ 3:1 against adjacent colors | A | W3C 2023 |
| Text resize (1.4.4) | 200% without loss | A | W3C 2023 |
| Reflow (1.4.10) | 320 CSS px wide (= 400% zoom) or 256 CSS px high | A | W3C 2023 |
| Text-spacing overrides (1.4.12) | line 1.5×, paragraph 2×, letter 0.12×, word 0.16× | A | W3C 2023 |
| Autoplay audio control (1.4.2) | > 3 s | A | W3C 2023 |
| Target size, AA (2.5.8, new) | ≥ 24 × 24 CSS px or 24 px spacing circle | A | W3C 2023 |
| Target size, AAA (2.5.5) | ≥ 44 × 44 CSS px | A | W3C 2023 |
| Focus appearance, AAA (2.4.13, new) | ≥ 2 CSS px perimeter area, ≥ 3:1 change | A | W3C 2023 |
| Time limits (2.2.1) | off, ≥ 10× adjustable, or ≥ 20 s warning × ≥ 10 extensions | A | W3C 2023 |
| Auto-moving content needing pause (2.2.2) | > 5 s | A | W3C 2023 |
| Flashing (2.3.1) | ≤ 3 flashes in any 1 s | A | W3C 2023 |
| Line width, AAA (1.4.8) | ≤ 80 characters (40 CJK) | A | W3C 2023 |
| One-thumb single-tap target | ≥ 9.2 mm | B | Parhi 2006 |
| One-thumb sequential key | ≥ 9.6 mm | B | Parhi 2006 |
| Thumb speed gains level off | ~11.5 mm | B | Parhi 2006 |
| Hit spread at 9.6 mm (2 SD) | 9.1 × 8.9 mm | B | Parhi 2006 |
| Blind vs sighted gesture duration | 925.90 vs 462.58 ms | B | Kane 2011 |
| Blind vs sighted touch offset from target | 110.97 vs 48.84 px | B | Kane 2011 |
| SUPPLE vs default UI, motor-impaired users | 28% faster, 73% more accurate | B | Wobbrock 2011 |
| Key filtering error reduction | 80% | B | Wobbrock 2011 |
| Barrier pointing error rate, one user | 66.7% → 13.3% | C | Wobbrock 2011 |
| Access-technology use among those who need it | ≤ 60% | B | Wobbrock 2011 |
| CLI task time, actual vs anticipated (screen reader) | 129 vs 21 min; 132 vs 33 min | B | Sampath 2021 |
| Arial Italic reading time vs Arial (dyslexia) | 123% (34.99 vs 28.35 s) | B | Rello 2013 |
| Font preference vs reading time correlation | r = −0.13 | B | Rello 2013 |
| Older-adult body text | ≥ 14 pt | B | Bernard 2001 |
| Preferred complexity peak by age | 4.1–4.2 (12–40), 4.7 (over 50), 1–10 scale | B | Reinecke 2014 |
| Accessibility papers on blind/low vision | 43.5% | A | Mack 2021 |
| Median N, disabled or older participants | 13 | A | Mack 2021 |

## Common misreadings
- "WCAG thresholds are empirically optimal values." They are consensus values with no effect sizes reported (W3C 2023). Research sometimes points higher, for example thumb targets of 9.2–9.6 mm (Parhi 2006).
- "Meeting WCAG AA means the product is accessible to everyone." WCAG says it will not address every user need, and it gives only some accommodation for cognitive and learning disabilities (W3C 2023).
- "We should conform to AAA everywhere." W3C does not recommend AAA as a site-wide requirement (W3C 2023).
- "1.4.8 and 1.4.12 require authors to use 1.5 line spacing and 80-character lines." Those criteria mainly require that users can adjust presentation without loss (W3C 2023).
- "24 CSS px equals a known physical size." CSS px must be converted via device density, so WCAG and millimeter-based research values are not directly comparable (Parhi 2006).
- "A command-line or text interface is accessible by default." Unstructured output, spinners, ASCII art and silent success make CLIs slow and frustrating with screen readers (Sampath 2021).
- "Dyslexia fonts help dyslexic readers." OpenDyslexic gave no reading benefit and was disliked; avoiding italics mattered more (Rello 2013).
- "Older users always want the simplest, least colorful design." The larger study found older users preferred somewhat higher complexity and disliked plain, colorless sites (Reinecke 2014), which conflicts with the earlier result (Reinecke 2013).
- "Findings from blind users apply to all disabled users." Research is skewed toward blind and low-vision users, and only 7.1% of papers covered more than one community (Mack 2021).

## Review checklist
- [ ] AX-1: Is WCAG 2.2 AA met on every page, in every responsive variation, and across every step of each process?
- [ ] AX-2: Does every image, icon and control have an accessible name or text alternative, are decorative elements hidden from assistive technology, and are headings, lists, tables and label–field links exposed in code?
- [ ] AX-2: Do instructions avoid relying only on shape, color, size, position or sound, and do personal-data fields carry autocomplete tokens?
- [ ] AX-3: Is text contrast ≥ 4.5:1 (≥ 3:1 for large text), are component boundaries, focus rings, icons and chart marks ≥ 3:1, and is color never the only cue?
- [ ] AX-4: Does the layout survive 200% text resize, a 320 CSS px width without horizontal scrolling, the text-spacing overrides, and both orientations?
- [ ] AX-5: Can hover and focus popups be dismissed with Esc, hovered without disappearing, and do they persist until dismissed?
- [ ] AX-6: Is every function reachable by keyboard with no trap, logical focus order, a visible focus indicator, and no sticky element fully covering the focused item?
- [ ] AX-7: Does every gesture, drag and motion-triggered action have a single-tap or click alternative, do actions fire on pointer-up, and does each accessible name contain its visible label?
- [ ] AX-8: Are pointer targets ≥ 24 × 24 CSS px (or properly spaced), ideally 44 × 44, and for one-thumb mobile use around 9.2 mm (taps) and 9.6 mm (keys)?
- [ ] AX-9: Can every time limit be turned off, extended or adjusted, can auto-moving content over 5 s be paused, and does nothing flash more than 3 times per second?
- [ ] AX-10: Are there skip links, descriptive titles and headings, clear link text, two ways to reach each page, a set page language, no context change on focus, and consistent order for navigation and help?
- [ ] AX-11: Are errors described in text with suggestions, are costly submissions reversible or confirmed, is earlier input reused, does login allow paste and password managers, and are status messages announced without moving focus?
- [ ] AX-12: Where users struggle, does the design adapt the interface (size, spacing, timing) rather than demand retraining or extra hardware?
- [ ] AX-13: Can users see, preview, override and undo any automatic adaptation?
- [ ] AX-14: Can presentation and input modality be adjusted for walking, glare, gloves, noise and fatigue, with settings configurable ahead of time?
- [ ] AX-15: Are accessibility features built into the standard product, unchanged or improved from the previous version, with discreet output options?
- [ ] AX-16: In eyes-free touch modes, are critical functions on edges or corners, is accuracy relaxed, is gesture speed ignored, and are print-symbol gestures avoided or given alternatives?
- [ ] AX-17: For text-based tools, is output structured and exportable, is success or failure stated explicitly, is progress announced as text, is ASCII decoration absent, are docs available as HTML, and do errors read well aloud?
- [ ] AX-18: Is body text non-italic and in a roman sans-serif (or monospace) font, with a user font choice?
- [ ] AX-19: For older audiences, is body text ≥ 14 pt, and was visual complexity tested with that audience rather than assumed?
- [ ] AX-20: Were people with the relevant disabilities involved in design and testing, and are claims drawn only from evidence on the same population?

## Sources
- Bernard, M., Liao, C. H., Mills, M. (2001). *The effects of font type and size on the legibility and reading time of online text by older adults*. CHI EA '01. https://doi.org/10.1145/634067.634173
- Kane, S. K., Jayant, C., Wobbrock, J. O., Ladner, R. E. (2009). *Freedom to roam: a study of mobile device adoption and accessibility for people with visual and motor disabilities*. ASSETS '09. https://doi.org/10.1145/1639642.1639663
- Kane, S. K., Wobbrock, J. O., Ladner, R. E. (2011). *Usable gestures for blind people: understanding preference and performance*. CHI '11. https://doi.org/10.1145/1978942.1979001
- Mack, K., McDonnell, E., Jain, D., Wang, L. L., Froehlich, J. E., Findlater, L. (2021). *What do we mean by "accessibility research"? A literature survey of accessibility papers in CHI and ASSETS from 1994 to 2019*. CHI '21. https://doi.org/10.1145/3411764.3445412
- Oulasvirta, A., Dayama, N. R., Shiripour, M., John, M., Karrenbauer, A. (2020). *Combinatorial optimization of graphical user interface designs*. Proceedings of the IEEE. https://doi.org/10.1109/jproc.2020.2969687
- Parhi, P., Karlson, A. K., Bederson, B. B. (2006). *Target size study for one-handed thumb use on small touchscreen devices*. MobileHCI '06. https://doi.org/10.1145/1152215.1152260
- Reinecke, K., et al. (2013). *Predicting users' first impressions of website aesthetics with a quantification of perceived visual complexity and colorfulness*. CHI '13. https://doi.org/10.1145/2470654.2481281
- Reinecke, K., Gajos, K. Z. (2014). *Quantifying visual preferences around the world*. CHI '14. https://doi.org/10.1145/2556288.2557052
- Rello, L., Baeza-Yates, R. (2013). *Good fonts for dyslexia*. ASSETS '13. https://doi.org/10.1145/2513383.2513447
- Sampath, H., Merrick, A., Macvean, A. (2021). *Accessibility of command line interfaces*. CHI '21. https://doi.org/10.1145/3411764.3445544
- W3C (2023). *Web Content Accessibility Guidelines (WCAG) 2.2*. W3C Recommendation. https://www.w3.org/TR/WCAG22/
- Wobbrock, J. O., Kane, S. K., Gajos, K. Z., Harada, S., Froehlich, J. (2011). *Ability-based design: concept, principles and examples*. ACM TACCESS. https://doi.org/10.1145/1952383.1952384
