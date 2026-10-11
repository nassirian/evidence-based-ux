# Group A: Accessibility & Typography: Paper Summaries

Files covered: 00__W3C-2023_WCAG-2.2, 06__Kane-2009, 06__Kane-2011, 06__Mack-2021, 06__Parhi-2006, 06__Sampath-2021, 06__Wobbrock-2011, 05__Bernard-2001, 05__Dyson-2004, 05__Ling-vanSchaik-2006, 05__Rello-BaezaYates-2013.

---

## 00__W3C-2023_WCAG-2.2 — Web Content Accessibility Guidelines (WCAG) 2.2 (W3C Accessibility Guidelines Working Group; text is the W3C Recommendation dated 12 December 2024; W3C standard)
**Type:** guideline (international standard)  ·  **Sample/method:** Consensus standard: 4 principles, 13 guidelines, testable success criteria (SC) at Levels A / AA / AAA. 4.1.1 Parsing is marked "Obsolete and removed".
**Core claim.** Web content is accessible when it is Perceivable, Operable, Understandable and Robust. Each guideline is made operational through technology-neutral, testable success criteria.

**Conformance basics (Section 5).** Level A = all A SC met; AA = all A + AA; AAA = all A + AA + AAA. Conformance applies to full pages, including every responsive variation, and to complete processes (every step of a checkout). W3C does *not* recommend requiring AAA site-wide because some content cannot meet all AAA SC. Four SC apply even to content not relied on for conformance (non-interference): 1.4.2, 2.1.2, 2.3.1, 2.2.2.
**Key definitions with numbers (glossary).**
- *Contrast ratio* = (L1 + 0.05)/(L2 + 0.05), ranging from 1:1 to 21:1. *Relative luminance* (sRGB) L = 0.2126R + 0.7152G + 0.0722B, with each channel linearized: if c ≤ 0.04045 then c/12.92, else ((c+0.055)/1.055)^2.4.
- *Large-scale text*: at least 18 pt, or 14 pt bold (roughly 1.5 em / 1.2 em bold of default body size), or the CJK equivalent.
- *General/red flash thresholds*: content passes if there are no more than 3 general and/or 3 red flashes in any 1 s, OR the combined concurrent flash area is ≤ 0.006 steradians within any 10° visual field (25% of the field). A general flash is a pair of opposing luminance changes of ≥ 10% of max relative luminance where the darker image is < 0.80. A 341 × 256 px rectangle at 1024 × 768 approximates a 10° field. Red flash (working definition): a transition to or from R/(R+G+B) ≥ 0.8 with a chromaticity difference > 0.2 (CIE 1976 UCS).
- *Lower secondary education level*: the 2–3 year period that begins after 6 years of school and ends 9 years after primary education begins.

### Principle 1: Perceivable
**1.1 Text Alternatives**
- **1.1.1 Non-text Content (A):** All non-text content has an equivalent text alternative. Controls and inputs have a name describing their purpose. Time-based media, tests and sensory content need at least a descriptive identification. CAPTCHAs need a described purpose plus alternative modalities. Decoration and formatting must be ignorable by assistive technology (AT).

**1.2 Time-based Media**
- **1.2.1 Audio-only & Video-only, prerecorded (A):** Provide a media alternative for audio-only content. For video-only, provide a media alternative or an audio track.
- **1.2.2 Captions, prerecorded (A).** **1.2.3 Audio Description or Media Alternative, prerecorded (A).**
- **1.2.4 Captions, live (AA).** **1.2.5 Audio Description, prerecorded (AA).**
- **1.2.6 Sign Language, prerecorded (AAA).** **1.2.7 Extended Audio Description (AAA)**, used where pauses in the foreground audio are insufficient. **1.2.8 Media Alternative, prerecorded (AAA).** **1.2.9 Audio-only, live (AAA).**

**1.3 Adaptable**
- **1.3.1 Info and Relationships (A):** Structure and relationships conveyed visually can be programmatically determined or are available in text.
- **1.3.2 Meaningful Sequence (A):** When order affects meaning, the correct reading order is programmatically determinable.
- **1.3.3 Sensory Characteristics (A):** Instructions do not rely solely on shape, color, size, visual location, orientation or sound.
- **1.3.4 Orientation (AA):** Content does not lock to portrait or landscape unless that orientation is essential (examples: bank check, piano app, VR).
- **1.3.5 Identify Input Purpose (AA):** Fields that collect user information expose their purpose programmatically (e.g. autocomplete tokens).
- **1.3.6 Identify Purpose (AAA):** The purpose of components, icons and regions is programmatically determinable.

**1.4 Distinguishable**
- **1.4.1 Use of Color (A):** Color is never the *only* visual means of conveying information, indicating an action, prompting a response or distinguishing an element.
- **1.4.2 Audio Control (A):** Audio that autoplays for **> 3 s** can be paused or stopped, or has its own volume control.
- **1.4.3 Contrast (Minimum) (AA):** Text and images of text **≥ 4.5:1**; large-scale text **≥ 3:1**. No requirement for inactive components, pure decoration, invisible text, text inside a picture with significant other content, or logotypes.
- **1.4.4 Resize Text (AA):** Text resizes to **200%** without AT and without loss of content or function (captions and images of text excepted).
- **1.4.5 Images of Text (AA):** Use real text unless the image is customizable or the presentation is essential (logotypes count as essential).
- **1.4.6 Contrast (Enhanced) (AAA):** Text **≥ 7:1**; large-scale text **≥ 4.5:1**. Same exceptions as 1.4.3.
- **1.4.7 Low or No Background Audio (AAA):** For prerecorded speech audio, there is no background sound, or it can be turned off, or it is **≥ 20 dB** below the speech (≈ 4× quieter), except occasional sounds of 1–2 s.
- **1.4.8 Visual Presentation (AAA):** A mechanism lets users choose foreground and background colors. Width is **≤ 80 characters (40 CJK)**. Text is not justified. Line spacing is **≥ 1.5** within paragraphs and paragraph spacing is **≥ 1.5×** the line spacing. Text resizes to **200%** with no horizontal scrolling on a full-screen window. (The mechanism may be provided by the user agent.)
- **1.4.9 Images of Text, No Exception (AAA):** Images of text only for pure decoration or where the presentation is essential.
- **1.4.10 Reflow (AA):** No two-dimensional scrolling at a **320 CSS px** width (vertical-scrolling content) or a **256 CSS px** height (horizontal-scrolling content). 320 px equals 1280 px at **400% zoom**. Maps, diagrams, video, games, data tables and similar are excepted.
- **1.4.11 Non-text Contrast (AA):** UI component boundaries and states, and graphical objects needed for understanding, have **≥ 3:1** against adjacent colors (excepting inactive or unmodified user-agent components).
- **1.4.12 Text Spacing (AA):** Nothing is lost when users set line height to **1.5×** font size, spacing after paragraphs to **2×**, letter spacing to **0.12×** and word spacing to **0.16×**.
- **1.4.13 Content on Hover or Focus (AA):** Content revealed by hover or focus is *dismissible* without moving pointer or focus (e.g. Esc), *hoverable* (the pointer can move onto it), and *persistent* until the trigger is removed, the user dismisses it, or it is no longer valid.

### Principle 2: Operable
**2.1 Keyboard Accessible**
- **2.1.1 Keyboard (A):** All functionality works through a keyboard interface with no specific keystroke timings. The exception is path-dependent functions (the exception concerns the function, not the input technique).
- **2.1.2 No Keyboard Trap (A):** Focus can always leave a component by keyboard. If that needs more than arrow, Tab or standard exit keys, the user is told how.
- **2.1.3 Keyboard, No Exception (AAA).**
- **2.1.4 Character Key Shortcuts (A):** Shortcuts made only of letters, punctuation, numbers or symbols can be turned off, remapped to include a non-printable key, or are active only while their component has focus.

**2.2 Enough Time**
- **2.2.1 Timing Adjustable (A):** For each time limit, at least one holds. The user can turn it off. Or the user can adjust it to **≥ 10×** the default. Or the user is warned and gets **≥ 20 s** to extend with a simple action, extendable **≥ 10 times**. Exceptions: real-time events, essential limits, and limits **> 20 h**.
- **2.2.2 Pause, Stop, Hide (A):** Moving, blinking or scrolling content that starts automatically, lasts **> 5 s** and runs in parallel with other content can be paused, stopped or hidden. Auto-updating content can be paused, stopped, hidden or have its update frequency controlled. Essential cases are excepted.
- **2.2.3 No Timing (AAA).** **2.2.4 Interruptions (AAA):** Users can postpone or suppress interruptions except emergencies.
- **2.2.5 Re-authenticating (AAA):** Users continue without data loss after re-authenticating. **2.2.6 Timeouts (AAA):** Warn users of the inactivity duration that causes data loss, unless data is kept **> 20 h**.

**2.3 Seizures and Physical Reactions**
- **2.3.1 Three Flashes or Below Threshold (A):** Nothing flashes **> 3 times in any 1 s**, unless it is below the general and red flash thresholds.
- **2.3.2 Three Flashes (AAA):** No more than 3 flashes per second, with no threshold exception.
- **2.3.3 Animation from Interactions (AAA):** Motion animation triggered by interaction can be disabled unless it is essential.

**2.4 Navigable**
- **2.4.1 Bypass Blocks (A):** A mechanism to skip blocks repeated across pages. **2.4.2 Page Titled (A):** Titles describe topic or purpose.
- **2.4.3 Focus Order (A):** Focus order preserves meaning and operability. **2.4.4 Link Purpose, In Context (A):** Purpose is clear from link text plus its programmatic context.
- **2.4.5 Multiple Ways (AA):** More than one way to locate a page, except steps in a process. **2.4.6 Headings and Labels (AA):** They describe topic or purpose.
- **2.4.7 Focus Visible (AA):** Any keyboard-operable UI has a mode in which the focus indicator is visible.
- **2.4.8 Location (AAA).** **2.4.9 Link Purpose, Link Only (AAA).** **2.4.10 Section Headings (AAA).**
- **2.4.11 Focus Not Obscured, Minimum (AA, new in 2.2):** A focused component is not *entirely* hidden by author content such as sticky headers or footers.
- **2.4.12 Focus Not Obscured, Enhanced (AAA, new):** *No part* of the focused component is hidden.
- **2.4.13 Focus Appearance (AAA, new):** The indicator area is **≥ the area of a 2 CSS px thick perimeter** of the unfocused component and has **≥ 3:1** contrast between the same pixels in focused and unfocused states (exceptions for user-agent indicators).

**2.5 Input Modalities**
- **2.5.1 Pointer Gestures (A):** Multipoint and path-based gestures also have a single-pointer, non-path alternative unless the gesture is essential.
- **2.5.2 Pointer Cancellation (A):** Single-pointer functions do not fire on the down-event, or they complete on the up-event with abort or undo, or the up-event reverses the down-event, or firing on down is essential (keyboard and keypad emulation counts as essential).
- **2.5.3 Label in Name (A):** The accessible name contains the visible label text. Best practice is to put the label text at the start of the name.
- **2.5.4 Motion Actuation (A):** Functions triggered by device or user motion also have UI controls, and motion response can be disabled.
- **2.5.5 Target Size, Enhanced (AAA):** Pointer targets **≥ 44 × 44 CSS px**, unless an equivalent control meets the size, the target is inline in text, it is a user-agent control, or the size is essential.
- **2.5.6 Concurrent Input Mechanisms (AAA):** Do not restrict the platform's available input modalities.
- **2.5.7 Dragging Movements (AA, new):** Any drag function is also achievable with a single pointer without dragging, unless dragging is essential.
- **2.5.8 Target Size, Minimum (AA, new):** Targets **≥ 24 × 24 CSS px**. The *spacing* exception: an undersized target passes if a **24 px-diameter circle** centred on it does not intersect another target or another undersized target's circle. Other exceptions: equivalent control, inline target, user-agent control, essential or legally required presentation. Sliders and color pickers count as one target.

### Principle 3: Understandable
**3.1 Readable**
- **3.1.1 Language of Page (A).** **3.1.2 Language of Parts (AA)** (proper names, technical terms and vernacular excepted).
- **3.1.3 Unusual Words (AAA):** A mechanism to define idioms and jargon. **3.1.4 Abbreviations (AAA):** A mechanism to show the expanded form.
- **3.1.5 Reading Level (AAA):** If text needs reading ability above *lower secondary education level*, provide supplemental content or a simpler version. **3.1.6 Pronunciation (AAA).**

**3.2 Predictable**
- **3.2.1 On Focus (A):** Focus never initiates a change of context. **3.2.2 On Input (A):** Changing a setting does not change context automatically unless the user was told beforehand.
- **3.2.3 Consistent Navigation (AA):** Repeated navigation keeps the same relative order. **3.2.4 Consistent Identification (AA):** Same function, same identification.
- **3.2.5 Change on Request (AAA).**
- **3.2.6 Consistent Help (A, new):** Repeated help mechanisms (human contact details, contact mechanism, self-help, automated contact) stay in the same relative order across pages.

**3.3 Input Assistance**
- **3.3.1 Error Identification (A):** A detected error is identified and described in text. **3.3.2 Labels or Instructions (A).**
- **3.3.3 Error Suggestion (AA):** Give known correction suggestions unless that compromises security or purpose.
- **3.3.4 Error Prevention, Legal/Financial/Data (AA):** Submissions are reversible, checked with a chance to correct, or confirmed after review.
- **3.3.5 Help (AAA):** Context-sensitive help. **3.3.6 Error Prevention, All (AAA).**
- **3.3.7 Redundant Entry (A, new):** Information already entered in the same process is auto-populated or selectable (exceptions: essential, security, no longer valid).
- **3.3.8 Accessible Authentication, Minimum (AA, new):** No cognitive function test (remembering a password, solving a puzzle) at any authentication step unless one of these is offered: an alternative method, an assisting mechanism (password managers, copy and paste), *object recognition*, or *personal content*.
- **3.3.9 Accessible Authentication, Enhanced (AAA, new):** As 3.3.8 but without the object-recognition and personal-content exceptions.

### Principle 4: Robust
- **4.1.1 Parsing:** obsolete and removed in 2.2.
- **4.1.2 Name, Role, Value (A):** For all UI components, name and role are programmatically determinable, user-settable states and values are programmatically settable, and changes are notified to AT.
- **4.1.3 Status Messages (AA):** Status messages are exposed through role or properties so AT announces them without moving focus.

**Design rules derivable**
- Body text contrast ≥ 4.5:1; large text (≥ 18 pt or 14 pt bold) ≥ 3:1; target 7:1 / 4.5:1 for AAA. [strong; normative consensus standard]
- Icons, input borders, focus rings and chart elements ≥ 3:1 against adjacent colors. [strong]
- Interactive targets ≥ 24 × 24 CSS px, or spaced so 24 px circles don't overlap; aim for 44 × 44 CSS px (AAA). [strong as standard; numeric value is consensus]
- Layouts survive 200% text zoom and 400% zoom (320 px width) without 2-D scrolling. [strong]
- Layouts survive user text-spacing overrides (1.5 / 2 / 0.12 / 0.16). [strong]
- Never use color alone to convey state. Never rely on shape or position alone in instructions. [strong]
- Every drag, multi-finger or path gesture has a single-tap or click alternative. Fire actions on pointer-up with cancel or undo. [strong]
- Provide a visible focus indicator (AAA: ≥ 2 px perimeter area, ≥ 3:1 change). Sticky elements must never fully cover the focused item. [strong]
- Time limits can be turned off, extended (≥ 20 s warning, ≥ 10 extensions) or adjusted to ≥ 10×. [strong]
- No more than 3 flashes per second. Allow disabling of interaction-triggered motion (AAA). [strong]
- Don't require memory or puzzle tests for login. Allow password managers and paste. [strong]
- Keep help, navigation and identification consistent across pages. Don't re-ask for data already entered. [strong]
- For reading-heavy text (AAA): line length ≤ 80 characters, unjustified, line spacing ≥ 1.5, user-selectable colors. [strong as standard; see Dyson/Ling for nuance on line length]

**Boundary conditions & caveats.** WCAG states it "will not address every user need" and offers only "some accommodation for learning disabilities and cognitive limitations". New cognitive SC were limited by testability and consensus problems. Thresholds such as 4.5:1, 24 px, 44 px and 80 characters are consensus values; the standard itself gives no effect sizes. The SC are written for web content, so applying them to native apps or CLIs needs interpretation (Sampath 2021 notes that text and keyboard operability alone meet only a small subset). AAA should not be a blanket policy. Many visual-presentation SC (1.4.8, 1.4.12) require only that users *can* adjust presentation, not that authors use those values.


---

## 06__Kane-2009_Freedom-to-roam-mobile-accessibility — Freedom to Roam: A Study of Mobile Device Adoption and Accessibility for People with Visual and Motor Disabilities (Kane, Jayant, Wobbrock, Ladner, 2009, ASSETS '09)
**Type:** empirical study (qualitative: interviews + diary)  ·  **Sample/method:** 20 interviewees (13 F, 7 M, ages 19–66, mean 34.9) with blindness, low vision or motor impairment, in 60–90 min semi-structured interviews. 19 then did a 7-day diary study (ages 20–52, mean 34.1), producing 85 entries (63 web, 18 email, 4 voicemail). Open and axial coding.
**Core claim.** People with visual and motor disabilities often choose mainstream mobile devices and work around persistent accessibility barriers. Those barriers get worse with situational factors such as walking, lighting, crowds and fatigue, so devices should be far more configurable and context-adaptive.

**Key findings**
- 24 participants carried 90 devices weekly: phones/smartphones 24, music players 12, laptops 11, canes 13, magnifiers 3, GPS 2 (§4.1.2).
- Only 6 interviewees used phones with accessibility features. 5 cited cost as the reason for choosing a commodity device. 9 frequently used a specialized device (§4.1, 4.5.1).
- Problems reported: on-screen text too small or low contrast (7), key size (12), overall device size (9), recessed or flat buttons on thin flip phones (5). 3 said newer phones were *less* accessible than older ones (§4.2.1).
- Situational effects: crowded spaces (5); bright or dim light made screens unreadable for 5 low-vision participants; gloves and cold; walking reduced motor control and situational awareness; interruptions from incoming calls (§4.2.2).
- Abilities change over time: 4 had conditions that fluctuated with stress, fatigue, weather or medication; 4 had progressive conditions (§4.2.3).
- Adaptations: 7 low-vision participants increased text size, but settings "did not usually provide enough flexibility". 7 installed screen readers. 13 had phones that could not install apps. Workarounds included per-contact ringtones in place of caller ID, a wrist strap, attached magnifiers, holsters (§4.3.1), backup and redundant devices (4 owned backups), memorizing button sequences learned at home with a CCTV or magnifier, and a single earbud to keep situational awareness (§4.3).
- Privacy and stigma: speakerphone and talking devices were awkward in public, and one participant avoided using a magnifier in public (§4.5.2).
- Most requested features (Table 2): screen reader 9, voice input 8, large buttons 7, screen magnification 6, smaller device 5, OCR 3, improved contrast 3, backlit keys 2.

**Design rules derivable**
- Make text scale to arbitrary sizes, reflowing, scrolling or zooming as needed, rather than capping at a maximum. [moderate; qualitative N=20, explicit author recommendation §5.2]
- Provide accessibility through software on mainstream hardware (screen reader, magnification, voice input) rather than relying on special devices. [moderate]
- Detect context (walking, lighting, noise) and adapt the UI, e.g. switch input/output modality or offer a "minimal attention" mode. [weak; design implication, not tested here]
- Let users configure a device offline at home, or from a PC, before using it on the go. [weak]
- Prefer tactile, raised, well-separated physical keys and grippable form factors. Don't regress accessibility in hardware revisions. [moderate]
- Offer private, discreet output alternatives to speakerphone or visible magnifiers, such as a single-ear headset or haptics. [weak]

**Boundary conditions & caveats.** Small, US-based (Seattle) qualitative sample. Pre-dates mature iOS/Android built-in accessibility (2009). Diary entries were mostly written at home, not on the go, so on-the-go problems are under-sampled. No performance measures.


---

## 06__Kane-2011_Usable-gestures-for-blind-people — Usable Gestures for Blind People: Understanding Preference and Performance (Kane, Wobbrock, Ladner, 2011, CHI 2011)
**Type:** empirical study (gesture elicitation + controlled performance study)  ·  **Sample/method:** 10 blind (mean age 49.0) + 10 sighted (mean 28.8) participants on a 10.1" multi-touch tablet. Study 1: each invented 2 gestures for 22 commands (880 gestures). Study 2: each performed 40 reference gestures × 3 (2335 recorded instances, 785 ratings).
**Core claim.** Blind people prefer different touch gestures than sighted people: more edge/corner, multi-touch, mode-key and QWERTY-metaphor gestures. When they perform the same gestures, theirs are larger, slower, more variable and less precise in location, which calls for different design and recognition choices.

**Key findings**
- Self-rated "good match": blind 5.54 vs sighted 5.15 (significant, χ²=13.69, p<.001). "Easiness" did not differ (5.77 vs 5.72).
- Strokes per gesture: blind 1.52 vs sighted 1.24 (Z=5.63, p<.0001).
- Edge gestures were 12.8% of all, and blind participants made 61.1% of them (χ²=6.35, p<.05). Corner gestures were 24.2%, and blind participants made 64.8% (χ²=24.58, p<.0001).
- Multi-touch was 30.7% of gestures, and blind participants made 61.5% (p<.0001). Mode-key gestures (one finger held while another gestures): 63 by blind vs 10 by sighted participants.
- QWERTY-key metaphors (e.g. tapping where Ctrl then V would be) made up 21.6% of blind participants' gestures and were used by 9 of 10 blind participants. No sighted participant used them.
- Text entry ideas: on-screen QWERTY (7 blind, 9 sighted), handwriting (2/3), Perkins Braille (2 blind), T9 (2 blind).
- Performance: blind participants' gestures were larger (165.82 vs 148.05 px² bounding area, p<.01), more variable in size (SD 20.43 vs 13.59, p<.001), wider for glyphs (p<.0001), and **≈2× slower** (925.90 ms vs 462.58 ms, p<.0001).
- Location accuracy: offset from the target screen location was 110.97 px for blind vs 48.84 px for sighted participants (p<.0001). Blind participants were still worse on corners.
- Form closure (circle start-to-end distance): 149.12 vs 67.12 px. Line waviness (average angular acceleration, square): 0.47 vs 0.06.
- $N recognizer accuracy was significantly lower for blind participants' gestures (e.g. blind symbols vs self 68.2%, vs blind 52.0%, vs sighted 61.3%; sighted symbols vs sighted 78.7%). 2 blind participants skipped 15 print-symbol gestures they didn't know.

**Design rules derivable**
- Put critical functions on screen edges and corners, which act as physical landmarks. [moderate; N=20, strong effect sizes]
- Reduce location-accuracy demands: use larger targets, or let users touch near a target and explore by finger before confirming (e.g. second-finger tap). [moderate]
- Don't use gesture speed as a recognition feature or parameter (e.g. kinetic scrolling) for eyes-free use. [moderate]
- Avoid print letters, digits and symbols as gestures, or offer training and alternatives. [moderate]
- Reproduce familiar spatial layouts (QWERTY, phone keypad) for eyes-free input. [weak-moderate; preference data, efficiency untested]
- Tolerate unclosed shapes, wavy strokes and size variance in recognizers, or train them on target users. [moderate]

**Boundary conditions & caveats.** Small N. Blind and sighted groups differed in age (49 vs 29). Tablet only, not phones. Elicitation tells you about preference, not efficiency. Some blind participants were unfamiliar with print symbols, which confounds the symbol results.


---

## 06__Mack-2021_What-do-we-mean-by-accessibility-research — What Do We Mean by "Accessibility Research"? A Literature Survey of Accessibility Papers in CHI and ASSETS from 1994 to 2019 (Mack, McDonnell, Jain, Wang, Froehlich, Findlater, 2021, CHI '21)
**Type:** survey (systematic literature review / meta-research)  ·  **Sample/method:** 836 accessibility papers (1994–2019) analyzed by counts and keywords. 506 papers (2010–2019; 291 ASSETS + 215 CHI) qualitatively coded with a 10-category, 52-subcode codebook (mean Krippendorff's α 0.76).
**Core claim.** Accessibility research is growing fast but is skewed. It focuses heavily on blind and low-vision users, relies on small samples, and has under-examined norms (proxies, ability comparisons, shallow "participatory" design) that risk reinforcing ableism.

**Key findings**
- Communities of focus (Table 2): BLV 43.5% (220/506); motor/physical 14.2%; DHH 11.3%; cognitive 9.1%; general disability 9.1%; older adults 8.9%; autism 6.1%; IDD 2.8%. 94.5% of BLV papers focused on BLV alone. Multiple disabilities < 1.0%. Only 7.1% of papers covered more than one community.
- Issues addressed: digital access 36.8%; understanding users 27.5%; physical access 20.8%; independence 18.4%; communication 16.0% (64.9% of DHH papers); behavior change 7.7% (32.3% of autism and 35.7% of IDD papers, which the authors critique).
- Contributions: empirical 60.3%, artifact 55.5%, theoretical 8.7%, methodological 3.2%, dataset 1.4%, survey 0.6%.
- 94.3% of papers had user studies. Methods: interviews 42.1%, usability testing 41.7%, controlled experiments 34.6%, surveys 25.6%. Participatory or co-design: 10.3%.
- Sample sizes: median 18 per paper overall. For participants with disabilities or older adults the median is **13** (IQR 13): autism 9, motor 10, IDD 11.5, BLV 13, older adults 15, cognitive 16, DHH 28. Compare medians of 15–16 for CHI 2020 lab, field and interview studies.
- Study locations: participants' home or usual places 34.1%, lab 32.1%, remote 24.2%, unclear 39.6%.
- Proxies were used in 8.0% of user-study papers (most often for autism, 22.6%). 13.6% compared disabled vs nondisabled participants.
- In 2019, accessibility papers were 7.8% of CHI papers (55/702), and "accessibility" was the 2nd most common CHI keyword.

**Design rules derivable** (methodological, for evidence-based design work)
- Weight accessibility evidence by population. Don't generalize BLV findings to motor, cognitive, autistic or DHH users, or to people with multiple disabilities. [strong; census of 506 papers]
- Expect small samples (median ~13) in accessibility studies. Treat single-study numeric thresholds as provisional and look for replication. [strong]
- Involve disabled people directly in design (sustained participatory design, not single sessions). Use proxies only with justification, and triangulate them with the disabled participants themselves. [moderate; normative recommendation]
- Check that design goals match community priorities. For example, don't design "behavior change" for autistic users who have said they don't want it. [moderate]
- Don't treat nondisabled performance as the "normal" baseline that disabled users should reach. [moderate]

**Boundary conditions & caveats.** Limited to CHI and ASSETS (excludes TACCESS, TOCHI and others). Keyword filtering may miss papers. Coding reflects the authors' positionality. Category boundaries (cognitive / IDD / autism) are fuzzy.


---

## 06__Parhi-2006_Target-size-one-handed-thumb — Target Size Study for One-Handed Thumb Use on Small Touchscreen Devices (Parhi, Karlson, Bederson, 2006, MobileHCI '06)
**Type:** empirical study (controlled experiment)  ·  **Sample/method:** 20 right-handed participants (17 M, 3 F, ages 19–42, mean 25.7), standing, right thumb only, on an HP iPAQ (240 × 320 px, 0.24 mm dot pitch). Lift-off selection with distractor targets and 0 mm spacing. Discrete phase: 5 sizes (3.8, 5.8, 7.7, 9.6, 11.5 mm) × 9 locations × 5 reps. Serial phase (4-digit keypad entry): 5 sizes (5.8–13.4 mm) × 4 locations × 5 reps.
**Core claim.** For one-handed thumb use, errors stop improving at about 9.6 mm for single taps and about 7.7 mm for sequential taps. Combining errors, hit spread and comfort, the authors recommend ≥ 9.2 mm targets for discrete tasks and ≥ 9.6 mm keys for serial tasks.

**Key findings**
- Discrete time: main effect of size, F(1,25)=70.42, p<.001. All pairwise differences were significant, even 9.6 vs 11.5 mm (p=.04). Results are consistent with Fitts' law. No effect of location (§5.1.1).
- Discrete errors: main effect of size, F(1,27)=49.18, p<.001. The two smallest sizes (3.8, 5.8 mm) were significantly worse than all others. 7.7 mm was worse than 11.5 mm. **No significant difference between 9.6 and 11.5 mm** (§5.1.2).
- Hit spread (2-SD boxes enclosing about 95% of taps): 3.8 mm → 6.5 × 6.5 mm; 5.8 → 7.0 × 8.6; 7.7 → 6.7 × 7.9; **9.6 → 9.1 × 8.9 mm** (Fig. 5). Taps on the bottom row landed above center. Taps in the right column landed right of center.
- Comfort: center rated most comfortable (μ=5.7/7); NW and SW least (μ=3.7). Smallest comfortable size: center 6.0 mm; NW 7.7, SW 7.6, SE 7.5 mm.
- Serial time: main effect of size, F(1,25)=60.02, p<.001. All sizes differed even though ID was constant, which the authors attribute to thumb-size accommodation. Serial errors: 5.8 mm was worse than ≥ 9.6 mm. Size × location interaction p=.039. Serial error rates were higher than discrete error rates at every size.
- Serial comfort: NE most comfortable (5.7), SE least (5.0). Smallest comfortable key: NE 8.3 mm; NW 8.9, SW 8.8, SE 8.8 mm.
- Pilot: performance leveled off above 11.5 mm. Standard widgets of the time were 2.64–4.8 mm.

**Design rules derivable**
- Make single-tap targets (buttons, checkboxes, radio buttons) at least 9.2 mm for one-thumb use. [moderate; single N=20 study, converging measures]
- Make keys for sequential entry (keypads, keyboards) at least 9.6 mm. [moderate]
- Expect speed to keep improving up to about 11.5 mm. Use larger targets when speed matters and space allows. [moderate]
- Extend targets on the dominant-thumb side all the way to the screen edge to absorb the outward tap bias. [weak-moderate]
- Put frequent or precise targets in the center or center column. Give the left side and bottom-right corner larger targets (for right-handed users). [weak; subjective + hit-spread trends, no significant location effect on performance]
- Use lift-off selection with drag-off-to-cancel for thumb input. [weak; used in method, not tested]

**Boundary conditions & caveats.** Mostly young, male, right-handed participants, standing still (not walking). One 2006 PDA with a 0.24 mm pitch resistive screen and one grip. Spacing was always 0 mm. Mirror the location advice for left-handed users. Desktop index-finger kiosk studies recommend much larger keys (20–25 mm, Colle & Hiszem). WCAG's 24/44 CSS px are in CSS pixels, not mm, so map them via device density.


---

## 06__Sampath-2021_Accessibility-of-command-line-interfaces — Accessibility of Command Line Interfaces (Sampath, Merrick, Macvean, 2021, CHI '21)
**Type:** empirical study (qualitative interviews + 2-week diary/usability study)  ·  **Sample/method:** Study 1: 6 developers who use screen readers and CLIs, in 90-min interviews. Study 2: 6 legally blind developers (1 dropped out) doing 4 gcloud CLI tasks over 2 weeks with JAWS, logging time and NASA-TLX-style 7-point ratings, plus exit interviews. Grounded-theory coding.
**Core claim.** CLIs are not inherently accessible just because they are text and keyboard based. Unstructured output, no or inaccessible progress indicators, ASCII decoration and poor error messages make screen-reader use slow and frustrating.

**Key findings**
- Task 2 (create a VM): actual time **129 (SD 111) min vs 21 (13.4) min anticipated**, t(4)=2.34, p=.039. Task 4 (deploy container): 132 (98.6) vs 33 (24.9) min, p=.02. Task 3: 107 vs 32 min, p=.06.
- Perceived success was mostly high, but effort and frustration were also high (e.g. Task 4 frustration 3–7, effort 3–7). One participant spent **6 hours** on a task expected to take 30 min because of an unclear error message.
- Unstructured text: terminal scrolling is hard with screen readers. Man pages can't be navigated by heading, so users write scripts to render them in a browser or fall back to web docs. Tables have no row/column semantics, so users memorize column order. Users copy long output into Notepad.
- Users don't use grep on output because they have no mental model or schema of what a command will output.
- Linux's silent-success convention leaves screen-reader users without status. One user created duplicate resources because no confirmation was shown. Another watched for screen brightness changes.
- Spinners and progress bars are read aloud as characters ("Little dots... blah, blah"). ASCII-art table borders are "beyond annoying".
- Error messages containing regexes or jargon are hard to verbalize and not actionable.

**Design rules derivable** (authors' 7 recommendations)
- Provide an HTML version of all documentation. Assume terminal-only docs are unavailable to screen-reader users. [moderate; N=12 qualitative, consistent across both studies]
- Offer export of long output to text or HTML with proper heading levels. [moderate]
- Document each command's output structure in advance. [moderate]
- Let tables be output as CSV, HTML or flattened key–value form. [moderate]
- Every command reports explicit status (success or failure), with progress for long operations. Never rely on silence as success. [moderate]
- Progress indicators must be screen-reader friendly: text announcements, not spinners or Unicode bars. Avoid ASCII-art decoration. [moderate]
- Write error messages that make sense read aloud and say what to do next. [moderate; Study 2 only]

**Boundary conditions & caveats.** 12 participants. Study 2 used one CLI (gcloud) and Windows + JAWS only. Self-reported times. Some themes came from only one study. The authors note that text and keyboard operability meet only a small subset of WCAG.


---

## 06__Wobbrock-2011_Ability-based-design — Ability-Based Design: Concept, Principles and Examples (Wobbrock, Kane, Gajos, Harada, Froehlich, 2011, ACM TACCESS 3(3), Art. 9)
**Type:** theory / design framework (illustrated with 14 prior projects)  ·  **Sample/method:** Conceptual article. Positions ability-based design against assistive technology, rehabilitation engineering, universal design, universal usability, design for all, UI4All, inclusive design and extra-ordinary HCI. Derives 7 principles and maps 14 systems onto them (Table II).
**Core claim.** Accessible design should shift from "what can't a person do?" to "what can a person do?". Systems, not users, should change to fit each person's abilities, often through adaptation based on measured performance and sensed context, using commodity hardware.

**Key findings / content**
- **7 principles (Table I).** Required: (1) *Ability*: focus on what users can do. (2) *Accountability*: respond to poor performance by changing the system, not the user. Recommended: (3) *Adaptation*: self-adaptive or user-adaptable interfaces. (4) *Transparency*: users can inspect, override, discard, revert, store, retrieve, preview and test adaptations. (5) *Performance*: monitor, measure, model or predict performance. (6) *Context*: sense context and anticipate its effects. Encouraged: (7) *Commodity*: low-cost off-the-shelf hardware and software.
- Across the 14 projects: all upheld principles 1, 2 and 7; 12 upheld performance; 10 adaptation; 6 transparency; 2 context. 11 of 14 targeted motor impairment.
- Evidence cited:
  - No more than 60% of people who need access technology use it, and specialized systems have high abandonment.
  - SUPPLE's auto-generated UIs made motor-impaired users **28% faster, 73% more accurate** and more satisfied than default UIs. It used per-user regression because Fitts' law fit poorly.
  - Angle Mouse gave >10% higher throughput and about 18% higher accuracy, with no detriment for nondisabled users.
  - Time-based key filtering (OverlapKeys) cut typing errors by 80%.
  - Barrier pointing along physical screen edges with lift-off cut one participant's (cerebral palsy) error rate from 66.7% to 13.3% and made him 48.5% faster.
  - Hurst et al. classified novice vs skilled users at 91% accuracy, and pointing problems at >90%.
  - Walking UIs that enlarge text and targets while the user walks gave mixed results.
  - Slide Rule's second-finger tap was adopted into VoiceOver as split-tap.
- Situational impairments (walking, glare, gloves, cold, noise, divided attention) parallel health-related impairments.

**Design rules derivable**
- When users perform poorly, change the interface, not the user. Avoid requiring add-on hardware or retraining. [weak-moderate; framework, supported by several project results]
- Let interfaces adapt (or be easily adapted) to measured user performance: target size, spacing, gain, timeouts, key debounce. [moderate; SUPPLE 28%/73%, Angle Mouse, OverlapKeys 80%]
- Make every adaptation visible and reversible, with preview, override and undo. Suggest rather than silently change. [weak; principle]
- Use physical screen edges as stabilizing barriers for hard-to-hit targets, responsive to the edge. [weak; single case study]
- Sense context (walking, lighting, noise) and scale text and targets or switch modalities. Validate the benefit, since early results were mixed. [weak]
- Prefer software solutions on commodity devices to reduce cost, stigma and abandonment. [moderate]

**Boundary conditions & caveats.** This is a position paper, so the principles themselves are not tested. Its examples are mostly the authors' own work and mostly motor impairment. Adaptive UIs carry their own risks (unpredictability), which is why transparency is needed. Specialized solutions remain warranted for severe impairments. Ability modelling for users with high variability is still an open problem.


---

## 05__Bernard-2001_Font-type-size-older-adults — The Effects of Font Type and Size on the Legibility and Reading Time of Online Text by Older Adults (Bernard, Liao, Mills, 2001, CHI 2001 Interactive Posters)
**Type:** empirical study (controlled experiment; short poster)  ·  **Sample/method:** 27 older adults (12 M, 15 F, ages 62–83, mean 70, vision 20/40 or better). 4 fonts (Times New Roman, Georgia, Arial, Verdana) × 2 sizes (12, 14 pt), within-subjects, Latin square. 15" 800 × 600, 96 dpi monitor at 57 cm. Passages of about 683 words with 10 substituted words, 640 px margins, black on white. Measures: "effective reading score" (accuracy ÷ time), reading time, and preference ranking.
**Core claim.** For older adults, 14-pt text is more legible, faster to read and preferred over 12-pt. Serif fonts tended to read faster at 14 pt, but sans serif fonts were preferred.

**Key findings**
- Legibility (reading efficiency): main effect of size, F(1,26)=14.10, p<.001, with 14 pt significantly better than 12 pt. No effect of font type and no interaction. (The OCR'd means read ".30" for 14 pt and ".34" for 12 pt. These look garbled relative to the stated direction, so don't use them.)
- Reading time: marginal type × size interaction, F(1,26)=3.39, p<.08. 12-pt serif was read significantly slower than 14-pt serif (p<.004) and 14-pt sans serif (p<.05). Reading times in Fig. 1 span about 250–290 s.
- Preference: significant ranking differences, χ²(7, N=27)=122.4, p<.001. Both 14-pt sans serifs (Arial, Verdana) were preferred over all 12-pt fonts. 14-pt serifs were preferred only over 12-pt serifs.
- Screen-optimized fonts (Georgia, Verdana) showed no difference from print-origin fonts (Times, Arial) at either size.

**Design rules derivable**
- Set body text for older readers at 14 pt or larger, not 12 pt. [moderate; N=27, single study, effect on legibility, speed and preference]
- If speed matters most for older readers, a serif at 14 pt is acceptable. If preference matters most, use sans serif. Prefer 14-pt sans serif as the compromise. [weak; marginal interaction]
- Don't pick a font just because it was "designed for screen". At these sizes it made no difference. [weak]

**Boundary conditions & caveats.** Poster with very limited stats. Only 2 sizes (sizes above 14 pt untested). CRT at 96 dpi and 800 × 600, so modern high-DPI rendering may change results. Characters per line varied with font (fixed 640 px width), so line length is confounded. Older adults with vision worse than 20/40 were excluded. Point size is not the same as CSS px.


---

## 05__Dyson-2004_Text-layout-reading-from-screen — How Physical Text Layout Affects Reading from Screen (Dyson, 2004, Behaviour & Information Technology 23(6), 377–393)
**Type:** critical literature review / synthesis  ·  **Sample/method:** Critical review of empirical studies (1980s–2002) on line length (characters per line, physical length, type size), columns, window height and interlinear spacing, with attention to confounds between variables.
**Core claim.** On screen, the number of characters per line (cpl) is the critical line-length variable. Longer lines (up to about 100 cpl) tend to be read *faster*, but readers *prefer* moderate lengths (about 55 cpl), and 55 cpl gave better comprehension than 100 cpl in one study. Subjective preference and objective performance often diverge.

**Key findings**
- Kolers et al. (1981): 70 cpl of narrow characters read more efficiently than 35 cpl. Duchnicky & Kolers (1983): more cpl gave faster reading (positive correlation); full and two-thirds screen width were faster than one-third; no comprehension difference (§2.1, 2.5).
- Dyson & Kipping (1998a), 48 participants, 10 pt Arial, 12 pt leading, 25–100 cpl: **100 cpl read fastest** (significant only vs 25 cpl). 55 cpl was rated easiest to read but was not fastest (§2.6, 2.9).
- Dyson & Haselgrove (2001): **55 cpl gave better comprehension than 100 cpl**, with no speed–accuracy trade-off. 25 cpl fell in between (§2.8).
- Bernard et al. (2002a): 45, 76 and 132 cpl showed no differences in reading time or efficiency. 132 cpl may exceed the useful limit (§2.6, §7).
- Youngman & Scharff (1998): longest line (about 100 cpl, no margin) gave the fastest scanning but was disliked most (§2.7).
- Type size: Bernard et al. (2002b) found 10 pt read more slowly than 12 pt, but a speed–accuracy trade-off removed the difference. Gould & Grischkowsky: visual angle has no effect over a middle range, with slower reading at very small or very large angles (§2.2–2.4).
- Columns: a single 80-cpl paged column was read faster than 3 columns of about 25 cpl (only for 18–24-year-olds), yet 3 columns were judged easiest to read. Grabinger: two columns judged more organized (§3).
- Window height: generally no reading-rate or comprehension effects (15/25/35 lines; 20 vs 60). Larger windows are preferred, and the 15-line window was judged hardest to read. Few-line windows (1–3) were slower than 4 or 20 lines (§4).
- Interlinear spacing: double spacing was marginally or significantly better than single in old studies (Kolers; Kruk & Muter). Grabinger's judgements favored single spacing. Little modern evidence (§5).
- Print guidance differs: ≤ 70 cpl (Spencer 1968), optimum about 52 cpl (Rayner & Pollatsek reading Tinker). Return-sweep and scrolling mechanics may explain why long lines are faster on screen (saccade duration ≈ 2.2A + 21 ms) (§7).
- Preference matches performance poorly across line length, columns, window size and type size (§7).

**Design rules derivable**
- Specify line length in characters per line, not physical width. [moderate; converging evidence]
- For text meant to be read and understood, aim for about 55 cpl, which is both preferred and better for comprehension. [moderate; preference replicated, comprehension in one study]
- For skimming or scanning, longer lines (up to about 100 cpl) are acceptable and can be faster. Avoid extreme lengths (about 132 cpl) and very short ones (about 25 cpl). [moderate]
- Don't rely on window height or lines per screen to speed reading. Give users larger windows for satisfaction. [weak-moderate]
- When testing typography, measure preference and performance separately, because they often diverge. [strong; consistent across many studies]

**Boundary conditions & caveats.** Many studies used 1980s displays, small N, confounded variables (type size, cpl, margins, leading) and unjustified text. Effects of interlinear spacing on long lines are untested on modern screens. Results depend on scrolling vs paging and on age and familiarity. The review deliberately excludes typeface comparisons and finds "no clear evidence" of typeface legibility differences on screen.


---

## 05__Ling-vanSchaik-2006_Font-type-and-line-length — The Influence of Font Type and Line Length on Visual Search and Information Retrieval in Web Pages (Ling & van Schaik, 2006, Int. J. Human-Computer Studies 64, 395–404)
**Type:** empirical study (two experiments)  ·  **Sample/method:** Experiment 1 (visual search for a link word on mock pages): 72 participants (57 F). Experiment 2 (information retrieval on 3-level sites, 40 questions): 99 participants (82 F, mean age 24). Both 2 (font between subjects: Arial 10 pt vs Times New Roman 12 pt, size-matched) × 4 (line length within subjects: 55, 70, 85, 100 cpl). 800 × 600, 14" monitors. Blue bold underlined links.
**Core claim.** Font (Arial vs Times) did not affect search or retrieval performance. Longer lines (85–100 cpl) made visual search faster, but users consistently preferred shorter lines (55–70 cpl) and Arial.

**Key findings**
- Experiment 1 hit reaction time: line-length effect F(3,210)=13.10, η²=0.038, p<.001. 85 and 100 cpl were faster than 55 and 70 (e.g. Times: 1511 ms at 85 cpl vs 1752 ms at 55). Font had no effect.
- Experiment 1 correct rejections: 70 cpl was more accurate than 85 cpl (p<.05; e.g. Arial 88.89% vs 84.05%), η²=0.004.
- Experiment 1 line-length preference: F(3,210)=3.95, η²=0.044. Preference declined with length (70 > 100 cpl, p<.05). Font preference: Arial chosen by 74% of the Arial group and 72% of the Times group, χ²=14.63, w=0.45, p<.001. Arial was rated higher aesthetically (F(1,67)=5.63).
- Experiment 2: no effect of line length or font on time or pages visited (96–98% correct). Line-length preference effect **F(3,291)=29.00, η²=0.224**: Times users preferred 55 cpl 40.07% of the time vs 100 cpl 10.64%. Arial preference was a trend (58–60%, p between .05 and .10).
- Preference was the most sensitive measure. Subjective effect sizes were much larger than performance effect sizes.

**Design rules derivable**
- For text meant to be read thoroughly (most web content), use short-to-moderate lines of about 55–70 cpl. [moderate; preference replicated across 2 experiments, large effect in Exp 2]
- For content meant to be scanned quickly (link lists, search results), longer lines (85–100 cpl) can speed search, though at some cost to accuracy and preference. [moderate; small effect]
- Arial vs Times does not matter for task performance. Choose the sans serif (Arial) to match user preference and expectation. [moderate]
- When performance is equal, decide on preference data. [moderate]

**Boundary conditions & caveats.** Young, mostly female student samples. 2005-era 800 × 600 CRTs with small text (10/12 pt). Tasks were search and retrieval, not sustained reading or comprehension. Pages did not scroll. Only two fonts. Font was between-subjects. The aesthetics scale was unreliable in Experiment 1.


---

## 05__Rello-BaezaYates-2013_Good-fonts-for-dyslexia — Good Fonts for Dyslexia (Rello & Baeza-Yates, 2013, ASSETS '13)
**Type:** empirical study (eye-tracking, within-subjects)  ·  **Sample/method:** 48 people with diagnosed dyslexia (ages 11–50, mean 20.96; 46 valid recordings) read 12 comparable 60-word Spanish texts in 12 fonts (Arial, Arial It., CMU, Courier, Garamond, Helvetica, Myriad, OpenDyslexic, OpenDyslexic It., Times, Times It., Verdana). 14 pt, left-aligned, ≤ 70 characters per line, black on white. Tobii 1750 at about 60 cm. Measures: reading time, mean fixation duration, comprehension check, 5-point preference. Friedman and Wilcoxon tests.
**Core claim.** Font choice affects readability for people with dyslexia. Sans serif, monospaced and roman (non-italic) fonts gave shorter fixations. Italics hurt, and Arial Italic should be avoided. Fonts designed specifically for dyslexia (OpenDyslexic) gave no benefit and were disliked.

**Key findings**
- Reading time: font effect χ²(11)=31.55, p<.001. Arial It. was slowest (mean 34.99 s, 123% of Arial's 28.35 s), significantly longer than Arial, CMU (both p=.011) and Helvetica (p=.034).
- Fixation duration: font effect χ²(11)=93.63, p<.001. Courier was shortest (0.22 s), shorter than 6 other fonts. Arial It. was longest (0.28 s), longer than 8 other fonts. 16 of 66 pairwise comparisons were significant.
- Italic vs roman fixation duration: 0.27 vs 0.25 s (p=.040). Serif vs sans: 0.26 vs 0.24 s (p=.008). Monospace vs proportional: 0.22 vs 0.26 s (p<.001). **None of these three groupings had a significant effect on reading time.**
- Preference: χ²(11)=79.61, p<.001. Verdana (3.79), Helvetica (3.62) and Arial (3.60) were top. Garamond (2.57), OpenDyslexic (2.57) and OpenDyslexic It. (2.43) were lowest. Verdana was preferred over Arial It., OpenDys, OpenDys It., Garamond and Times It.
- Preference and reading time correlated only r=−0.13, i.e. almost no relation.
- Fonts not dominated in both partial orders: Helvetica, CMU, Arial. Next: Verdana, Times. Overall recommendation: Helvetica, Courier, Arial, Verdana, CMU.

**Design rules derivable**
- Don't set body text in italics for readers with dyslexia. Avoid Arial Italic specifically. [moderate; N=48, significant on time and fixation]
- Prefer sans serif, roman fonts (Helvetica, Arial, Verdana) for dyslexia-friendly text. A monospaced font (Courier) is acceptable. [moderate for fixation duration; weak for reading speed]
- Don't assume "dyslexia fonts" (OpenDyslexic) help silent reading. Users found them no faster and liked them less. [moderate]
- Offer font choice, because preference doesn't track performance. [weak]
- Baseline layout for dyslexic readers: ≥ 14 pt, left-aligned, ≤ 70 characters per line, high contrast. [weak; held constant, not tested here]

**Boundary conditions & caveats.** Spanish texts and readers. Very short texts (60 words). Single sessions. Silent reading only (no reading-aloud or word-level errors, where specialized fonts might help). Grouped analyses (serif, monospace) are confounded by few fonts per group, e.g. monospace = Courier only. Effects on reading time are weaker than effects on fixation duration. No non-dyslexic control.


---

## Cross-paper patterns in this group
- **Preference and performance diverge.** This is the most consistent finding in the typography papers. Dyson (long lines faster, moderate preferred), Ling & van Schaik (long lines faster for search, short preferred; Arial preferred with equal performance), Bernard (serif faster at 14 pt, sans preferred) and Rello (preference vs reading time r=−0.13) all show it. Design rule: measure both, and use preference to break ties.
- **Line length is about 55–70 cpl for reading, longer for scanning.** Dyson (55 cpl best for comprehension and preference) and Ling & van Schaik (55–70 preferred) converge. WCAG 1.4.8 (AAA) caps width at 80 characters, Rello used ≤ 70 for dyslexia, and print guidance (Spencer) is ≤ 70. Speed favors 85–100 cpl only for scanning or search.
- **Font family matters less than size, style and population.** Ling (no Arial/Times performance difference), Bernard (no screen vs print font difference) and Dyson ("no clear evidence" of typeface differences) agree. Rello finds font effects for dyslexic readers, driven mainly by italics. Avoid italic body text. Sans serif is a safe, preferred default.
- **Size matters more for some groups.** Older adults read better at 14 pt than 12 pt (Bernard). Kane 2009 users wanted arbitrary text scaling. WCAG requires 200% resize, reflow at 320 px and text-spacing overrides. Design for scalable text rather than one "right" size.
- **Touch target size: independent evidence vs standard.** Parhi recommends ≥ 9.2 mm discrete and ≥ 9.6 mm serial for one-thumb use. WCAG 2.5.8 sets ≥ 24 × 24 CSS px (AA) and 2.5.5 sets ≥ 44 × 44 CSS px (AAA). Kane 2011 and Wobbrock argue for larger targets or accuracy-relaxed selection for blind and motor-impaired users. Converting px to mm depends on device density, so the two kinds of number are not directly comparable.
- **Screen edges and corners are accessibility assets.** Blind users prefer edge and corner gestures (Kane 2011). Barrier pointing along bezels cut errors from 66.7% to 13.3% for a user with cerebral palsy (Wobbrock). Parhi recommends extending edge targets to the bezel.
- **Alternatives for complex gestures.** Kane 2011 (avoid print-symbol gestures, don't use gesture speed) supports WCAG 2.5.1 (single-pointer alternative to path or multipoint gestures) and 2.5.7 (dragging alternative). Lift-off selection with cancel (Parhi, Wobbrock barrier pointing) aligns with WCAG 2.5.2 Pointer Cancellation.
- **Structure and status must be programmatic, not visual.** Sampath's CLI findings (unstructured tables, silent success, spinners read as characters) are direct cases of WCAG 1.3.1 Info & Relationships, 4.1.3 Status Messages and 1.1.1 (decorative content ignorable). A "text-based" interface is not accessible by default.
- **Change the system, not the user.** Wobbrock's accountability principle, Kane 2009's users fighting rigid settings caps, and WCAG's adjustable-presentation and timing SC (1.4.8, 1.4.12, 2.2.1) all push toward configurable, adaptive interfaces. Wobbrock adds that adaptations must be transparent and reversible.
- **Situational impairments extend accessibility to everyone.** Walking, glare, cold or gloves, crowds and noise (Kane 2009, Wobbrock) degrade abilities like disabilities do. Parhi's seated-standing study did not test walking, and Wobbrock's walking-UI results were mixed, so evidence for automatic context adaptation is still weak.
- **Weight the evidence carefully.** Mack shows accessibility studies have a median N of about 13 for disabled participants, and 43.5% of work is on BLV users. Most findings in this group are single studies with N=10–99 (moderate or weak). WCAG thresholds are consensus values, not effect-size-derived. Avoid generalizing BLV-derived rules to cognitive, autistic or DHH users.
