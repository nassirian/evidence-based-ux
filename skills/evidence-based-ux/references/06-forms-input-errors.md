# Forms, data entry and error handling

> Scope: how to lay out forms, choose input controls, validate entries, write and place error messages, and protect users from costly or destructive mistakes. Evidence grades: **[A]** strong — replicated, large-N, meta-analytic, or an international standard; **[B]** moderate — one solid study or converging smaller studies; **[C]** weak — expert opinion, theory, small qualitative work, or extrapolation from lab psychology to UI.

## Rules

### FE-1. State format rules, required fields and units before the user types
- **Do:** Put format requirements (e.g., password rules, date format "MM / YYYY") in the label, inside the field or directly beside it, before input. Clearly separate or mark required vs. optional fields, consistently across the form. Put units of measurement in the label so users do not type them. Provide labels or instructions for every input.
- **Why:** In Seckler's study of three real registration forms (N = 65), missing format specification caused 17 initial errors on the original NZZ form vs. 2 on the improved one (Seckler 2014). Users rated format specification (guideline 13) and required/optional marking (guideline 4) as most important, and guideline 13 had a "remarkable effect" on submission trials (Seckler 2014). On the improved NZZ form, "I knew at every input which rules I had to stick to" correlated r = .64 with the improvement (Seckler 2014). Smith & Mosier: 1.0/24 Prompting Data Entry, 1.4/12 Marking Required and Optional Data Fields, 1.4/20 Data Format Cueing in Labels, 1.4/21 Labeling Units of Measurement (Smith 1986). WCAG 3.3.2 Labels or Instructions (A) (W3C 2023).
- **Evidence:** [A] — (Seckler 2014; Smith 1986; W3C 2023).
- **Limits:** Seckler's guidelines were applied together, so effects are not isolated per guideline. Seckler 13 says to give the rule without an extra example, while Molich & Nielsen suggest an example of valid input in the prompt (Molich 1990, weak). The evidence leans toward an explicit rule; add an example only if it does not lengthen the form much. Seckler 4b (color plus asterisk) was rated low by experts (2.21).

### FE-2. Ask only for what you need, and never make users enter the same data twice
- **Do:** Remove questions that are not needed. Reuse anything the user already entered in the same process (auto-populate or offer it for selection). Prefill sensible defaults and show them in their fields. Compute derived values instead of asking for them. Mark field purposes programmatically (e.g., HTML autocomplete tokens) so browsers and assistive tools can fill them.
- **Why:** Smith & Mosier 1.0/1 Data Entered Only Once, 1.8/1 Default Values, 1.8/4 Display of Default Values, 1.8/8 Automatic Computation of Derived Data; their data-entry objectives include minimal entry actions and minimal memory load (Smith 1986). WCAG 3.3.7 Redundant Entry (A) requires auto-population or selection of previously entered information, and 1.3.5 Identify Input Purpose (AA) requires programmatic purpose for user-information fields (W3C 2023). Seckler guideline 3 (keep the form short) was rated 3.86 by experts (Seckler 2014).
- **Evidence:** [A] — (W3C 2023; Smith 1986; Seckler 2014).
- **Limits:** WCAG 3.3.7 exceptions: re-entry essential, required for security, or the earlier data is no longer valid (W3C 2023). Seckler did not test guideline 3. Defaults must favor the user; preselecting choices against user interest is a dark pattern (see ethics reference).

### FE-3. Accept every correct format the user might reasonably type
- **Do:** Accept spaces, hyphens, parentheses and other separators in phone, card and ID numbers. Treat upper and lower case as equivalent for coded data. If the meaning is unambiguous, accept any format and normalize it yourself. Let people answer in formats familiar from everyday life.
- **Why:** Accepting parentheses, spaces and hyphens in phone numbers was found by only 8% of 77 contest entries, one of the least-detected problems (Molich 1990). Smith & Mosier 1.7/2 Accepting Correct Entries (every possible correct entry accepted) and 1.0/27 Upper and Lower Case Equivalent (Smith 1986). Seckler guidelines 1 (familiar formats, 3.79) and 2 (any format if unambiguous, 3.50) (Seckler 2014).
- **Evidence:** [B] — (Molich 1990; Smith 1986; Seckler 2014).
- **Limits:** When a format really matters (e.g., avoiding day/month confusion), constrain the input instead (FE-4).

### FE-4. Use constrained controls when options are closed or easy to mistype
- **Do:** Use radio buttons, checkboxes or drop-downs to restrict options, for entries easily mistyped, or when the expected answer is unclear. Use checkboxes, not multi-select list boxes, for multiple selection. Use radio buttons for up to 4 options and a drop-down for more than 4. Order options intuitively (e.g., weekdays in order); otherwise alphabetically. Use a date drop-down when format errors must be avoided. Offer only options that are currently valid.
- **Why:** Seckler guidelines 8 (restrict options, 3.86), 9 (checkboxes for multi-select, 3.86), 10 (≤4 radio, >4 drop-down, 2.36), 11 (intuitive order, 4.71) and 12a (date drop-down, 3.57) (Seckler 2014). Smith & Mosier 3.2/10 Only Available Options Offered and 3.1.3/21 Logical Ordering of Menu Options (Smith 1986). Norman recommends physical constraints that make invalid actions impossible (Norman 1999).
- **Evidence:** [B] — (Seckler 2014; Smith 1986; Norman 1999).
- **Limits:** The 4-option threshold had a low expert rating (2.36) and was not tested alone. For fallback order, Seckler says alphabetical while Smith & Mosier say most frequent first; neither was tested head to head. Use alphabetical for lookup lists and frequency where a few options dominate.

### FE-5. Lay out forms in one column with labels above fields
- **Do:** Place each label above its field. Use a single column with one question per row. Keep labels close to their fields. Size each input to the expected answer length (e.g., a short field for a postcode, a longer one for a street). Place the cursor in the first field when the form opens.
- **Why:** On the improved NZZ form, fixations fell from 155 to 96, fixation duration from 62 s to 41 s and saccade time from 9 s to 4 s; scanpaths showed that side-by-side, left-aligned labels provoked longer saccades (Seckler 2014). Seckler guidelines 5 (labels above, 2.71), 6 (one column, 3.36) and 7 (field size matches answer, 3.29) (Seckler 2014). Smith & Mosier 1.4/5 Data Field Labels, 1.4/8 Labels Close to Data Fields, 1.4/28 Automatic Cursor Placement (Smith 1986).
- **Evidence:** [B] — (Seckler 2014; Smith 1986).
- **Limits:** Eye-tracking data came from one form; layout guidelines had moderate expert ratings. Mobile forms were not studied.

### FE-6. Validate when the user finishes, not while they are still typing
- **Do:** Do not interrupt a user in the middle of an entry. Validate at the completion of an entry unit or on submit. On submit, show all errors together, embedded in the form next to the fields concerned. If giving field-level feedback, do it after the user has completed that field, not on each keystroke.
- **Why:** Miller estimates that input errors should be reported 2–4 s after the user completes the thought, not mid-thought (Miller 1968). Smith & Mosier 1.7/3 Non-Disruptive Error Messages reports errors at completion of entry, and 3.0/18 gives 2–4 s as the response time for error messages (Smith 1986). Seckler guideline 16 shows errors after the form is sent, all together, embedded in the form (expert rating 4.29), and the improved forms with this guideline raised first-try submissions (Seckler 2014).
- **Evidence:** [B] — (Miller 1968; Smith 1986; Seckler 2014).
- **Limits:** All three sources agree on "not during entry". They differ on how soon after: per-unit at completion (Miller, Smith & Mosier) vs. on submit (Seckler). Only Seckler's on-submit approach was tested on real forms, and only as part of a bundle; Miller's numbers are expert estimates. The evidence leans to on-submit, embedded messages, with completed-field checks as an acceptable variant.

### FE-7. Show each error next to its field, keep the entry, and never clear completed fields
- **Do:** Identify every detected error in text and describe it. Put the message next to (Seckler: to the right of) the erroneous field and make it noticeable at a glance with color, an icon and text together. Keep the erroneous entry visible until corrected. Move the cursor to the first error. Never clear fields the user already completed. Remove the message as soon as the error is fixed. Put error messages in one consistent location.
- **Why:** "Never clear already completed fields after an error" was the only guideline all 14 experts rated 5.00 (Seckler 2014). Error message location and design (guideline 17) had a "remarkable effect" on submission trials; on the original Sueddeutsche form 14 users resubmitted without corrections vs. 0 on the improved form (Seckler 2014). Smith & Mosier 4.3/13 Cursor Placement Following Error, 4.3/14 Displaying Erroneous Entries, 4.3/16 Removing Error Messages (Smith 1986). WCAG 3.3.1 Error Identification (A) requires errors identified and described in text, and 1.4.1 forbids color as the only cue (W3C 2023). Molich & Nielsen recommend one consistent location for error messages (Molich 1990).
- **Evidence:** [A] — (Seckler 2014; Smith 1986; W3C 2023; Molich 1990).
- **Limits:** Right-of-field placement may not fit narrow mobile layouts; Seckler did not test mobile. Keep the message adjacent to the field in whatever layout is used.

### FE-8. Write error messages that are specific, constructive, brief and neutral
- **Do:** Say that a problem occurred, what exactly is wrong, what the system understood, and how to fix it. Offer the correct alternatives or a suggested correction when known. Use the user's task language. Be brief, with more detail on request. Be polite and neutral: no blame, no "ILLEGAL", no "Try again", no humor, no personified computer. A beep alone is not an error message.
- **Why:** Smith & Mosier 4.3/1 Informative, 4.3/2 Specific, 4.3/3 Task-Oriented, 4.3/4 Advisory, 4.3/5 Brief, 4.3/6 Neutral Wording, 4.3/7 Multilevel Error Messages (Smith 1986). Good messages are "defensive, precise, and constructive"; "ILLEGAL" intimidates and "Try again" is meaningless (Molich 1990). Seckler guideline 14 (polite, familiar language, describe the mistake and the fix) was rated 4.57 (Seckler 2014). WCAG 3.3.3 Error Suggestion (AA) requires known correction suggestions (W3C 2023). "Help users recognize, diagnose, and recover from errors" is one of Nielsen's nine heuristics (4% coverage) (Nielsen 1994).
- **Evidence:** [A] — (Smith 1986; Molich 1990; Seckler 2014; W3C 2023; Nielsen 1994).
- **Limits:** WCAG 3.3.3 does not require a suggestion if it would compromise security or the purpose of the content (W3C 2023). Seckler allows an apology; Smith & Mosier forbid personalizing the computer. Keep any apology short and impersonal.

### FE-9. Make errors and status work when read aloud and for assistive technology
- **Do:** Write error messages that make sense when spoken: no regexes, raw codes or unexplained jargon, and always a next step. Expose error and status messages programmatically so screen readers announce them without moving focus. Never rely on silence as success; confirm success explicitly. Use text announcements for progress, not spinners or ASCII art.
- **Why:** In a study of blind developers using a CLI, error messages with regexes or jargon were hard to verbalize and not actionable; one participant spent 6 hours on a task expected to take 30 min because of an unclear error, and silent success led another to create duplicate resources (Sampath 2021). WCAG 4.1.3 Status Messages (AA) and 3.3.1 Error Identification (A) (W3C 2023).
- **Evidence:** [A] — (W3C 2023; Sampath 2021).
- **Limits:** Sampath had 12 participants, one CLI and one screen reader; the WCAG criteria are the strong part of this rule.

### FE-10. Prevent errors before they happen
- **Do:** Review each field and step for likely slips and invalid states, and design them out: constrain input (FE-4), accept variants (FE-3), state rules up front (FE-1), disable unneeded or invalid controls, and keep users' input visible so they can check it.
- **Why:** 55% of 77 contest entries mentioned no error-prevention problem at all, and apart from vague error messages no prevention or error-message problem was found by more than 42% (Molich 1990). Error prevention was a distinct factor (3.7% variance) and among heuristics distinctive to serious problems (Nielsen 1994). Smith & Mosier 6.0/11 Disabling Unneeded Controls (Smith 1986). Physical and logical constraints prevent impossible actions (Norman 1999).
- **Evidence:** [B] — (Molich 1990; Nielsen 1994; Smith 1986; Norman 1999).
- **Limits:** The contest data show what designers miss, not measured user outcomes. Disabled controls need a visible reason or users may not know why an action is unavailable.

### FE-11. Echo input and acknowledge every entry quickly
- **Do:** Echo every keystroke (except passwords) and acknowledge every pointing action within 0.2 s. After an entry is completed, confirm success or show the error. Re-display what the user entered alongside the result.
- **Why:** Smith & Mosier 1.0/3 Feedback During Data Entry, 1.0/4 Fast Response and 1.1/5 Fast Acknowledgement of Entry (within 0.2 s), 1.0/12 Feedback for Completion of Data Entry (Smith 1986). Miller estimates keystroke echo at ≤0.1–0.2 s (Miller 1968). Re-displaying the entered number with the result was flagged by 95% of entries (Molich 1990).
- **Evidence:** [B] — (Smith 1986; Miller 1968; Molich 1990).
- **Limits:** The 0.2 s value is a 1986 judgment and a 1968 expert estimate, not an experimental result. Response-time guidance in general is in the feedback reference.

### FE-12. Require an explicit submit, keep entry user-paced, and provide exits
- **Do:** Process data only on an explicit submit action, never as a side effect of another action (e.g., focus or changing a setting). Provide an explicit cancel and back at every step. Let users edit any earlier entry or default. Let users temporarily skip a required field and come back. Do not change context automatically on input unless the user was told beforehand.
- **Why:** Smith & Mosier 1.0/9 Explicit ENTER Action, 1.0/11 Explicit CANCEL Action, 1.0/7 Consistent Method for Data Change, 1.0/8 User-Paced Data Entry ("machine-paced tasks are stressful and error-prone"), 1.7/4 Deferral of Required Data Entry, 3.3/3–3.3/4 CANCEL and BACKUP options (Smith 1986). "Provide clearly marked exits"; no exit from the initial prompt and no ability to edit input were among the least-found problems (Molich 1990). WCAG 3.2.1 On Focus and 3.2.2 On Input (A) forbid unannounced context changes (W3C 2023).
- **Evidence:** [A] — (Smith 1986; Molich 1990; W3C 2023).
- **Limits:** Live filters and dynamic queries intentionally apply changes immediately; that is acceptable when the effect is visible and reversible and does not change context.

### FE-13. Prevent double submission and confirm what happened
- **Do:** Disable the submit button once clicked. After a successful submit, show a confirmation page that thanks the user and states what happens next, and send a similar e-mail where relevant. Do not provide a reset button; if one is required, make it visually distinct from submit and place it away from it.
- **Why:** Seckler guidelines 18 (disable submit after click, 4.07), 19 (confirmation page and e-mail, 4.64) and 20 (no reset buttons, 4.14) (Seckler 2014). Lack of a confirmation led a screen-reader user to create duplicate resources (Sampath 2021). Smith & Mosier 1.0/12 Feedback for Completion of Data Entry (Smith 1986).
- **Evidence:** [B] — (Seckler 2014; Sampath 2021; Smith 1986).
- **Limits:** These guidelines were rated by experts and tested only inside the full bundle. Reset-button placement advice in Seckler (left-aligned, cancel right of submit) is expert opinion.

### FE-14. For legal, financial and data-changing submissions, allow review, correction or reversal
- **Do:** For submissions that create legal commitments, move money, or modify or delete user data, make at least one of these true: the submission can be reversed; input is checked and the user can correct errors; or the user can review, confirm and correct before final submission. Let users review data before it is transmitted.
- **Why:** WCAG 3.3.4 Error Prevention, Legal, Financial, Data (AA), with 3.3.6 extending it to all submissions at AAA (W3C 2023). Smith & Mosier 5.3/2 User Review Before Transmission and 6.3/17 Validating Data Changes (Smith 1986).
- **Evidence:** [A] — (W3C 2023; Smith 1986).
- **Limits:** A review step adds time; reserve it for consequential submissions and use reversibility where possible.

### FE-15. Make destructive actions harder, confirm selectively and prefer undo
- **Do:** Make frequent and urgent actions easy and destructive ones harder. Use safe defaults. Require an explicit action to enter destructive modes. Warn before potential data loss, including at log-off. Make destructive commands two-step with a distinctive, separate confirm action that shows enough information to decide (e.g., which file). Confirm only actions that are genuinely destructive or hard to reverse. Where possible, provide undo instead of a confirmation.
- **Why:** Smith & Mosier 6.0/8 Appropriate Ease or Difficulty of User Actions, 6.0/13 Safe Defaults, 6.0/15 Explicit Action to Select Destructive Modes, 6.0/17 Warning Users of Potential Data Loss, 6.0/18–6.0/20 distinctive, separate confirmation, 6.0/21 and 3.5/10 UNDO, 3.5/7 User Confirmation of Destructive Entries, 3.5/11 Preventing Data Loss at LOG-OFF; they note confirmations required for every routine overwrite become routine and lose protective value, and that destructive actions should be two-step, with UNDO "even better" (Smith 1986). Forgiveness (reversible actions) added 3% problem coverage (Nielsen 1994). WCAG 2.5.2 Pointer Cancellation (A) requires actions on the up-event, or with abort or undo (W3C 2023).
- **Evidence:** [B] — (Smith 1986; Nielsen 1994; W3C 2023).
- **Limits:** Smith & Mosier's rules are 1986 expert judgments. No source here quantifies how much confirmation fatigue reduces protection.

### FE-16. Let users finish without time pressure
- **Do:** Avoid time limits on forms. If one is needed, let users turn it off, adjust it to at least 10 times the default, or warn them and give at least 20 s to extend with a simple action, at least 10 times. Preserve entered data across re-authentication and timeouts.
- **Why:** WCAG 2.2.1 Timing Adjustable (A), with exceptions for real-time, essential and >20 h limits; 2.2.5 Re-authenticating and 2.2.6 Timeouts (AAA) protect data across sessions (W3C 2023). Smith & Mosier 1.0/8 User-Paced Data Entry (Smith 1986). After failures, preserve context so work is not lost (Miller 1968).
- **Evidence:** [A] — (W3C 2023; Smith 1986; Miller 1968).
- **Limits:** Essential time limits (e.g., auctions, exams) are exempt in WCAG.

### FE-17. Do not make authentication a memory or puzzle test
- **Do:** Allow paste into password and code fields, and support password managers (correct autocomplete attributes, no blocking of autofill). Do not require recalling or transcribing information or solving puzzles unless an alternative method or assistive mechanism is offered. Mask password entry.
- **Why:** WCAG 3.3.8 Accessible Authentication, Minimum (AA) bans cognitive function tests unless an alternative, an assisting mechanism (password manager, copy and paste), object recognition or personal content is offered; 3.3.9 (AAA) removes the last two exceptions (W3C 2023). Smith & Mosier 6.1/5 Private Entry of Passwords (Smith 1986).
- **Evidence:** [A] — (W3C 2023; Smith 1986).
- **Limits:** Object-recognition and personal-content checks pass AA but not AAA (W3C 2023).

### FE-18. Make AI-generated input easy to correct
- **Do:** When an AI feature fills fields, suggests values or acts on the user's behalf, present the result as an editable draft, let users edit, refine or undo it inline in one step, and offer several candidates instead of auto-filling when the system is uncertain.
- **Why:** Amershi G9 "Support efficient correction" (make it easy to edit, refine or recover when the AI is wrong) and G10 "Scope services when in doubt" (Amershi 2019). Horvitz recommends presenting agent results as editable drafts for the user to refine before committing (Horvitz 1999).
- **Evidence:** [C] — (Amershi 2019; Horvitz 1999).
- **Limits:** Amershi validated relevance and clarity, not user outcomes. Apply only when the form includes AI-generated content.

### FE-19. Prioritize form fixes by user impact, and test them with users
- **Do:** Use the full guideline set (FE-1 to FE-17) as a checklist, but rank fixes by observed user errors and failed submissions, not by expert opinion alone. Test improved forms with users for first-try submission success, completion time and errors.
- **Why:** Applying 20 guidelines raised first-try successful submissions from 10 to 24 (Sueddeutsche), 9 to 24 (NZZ) and 22 to 28 (Spiegel), and cut completion time by 25%, 33% and 18% (the last not significant), more than KLM predicted (7–23%) (Seckler 2014). Users' most important guidelines (13 and 4) were ranked only 7th and 9th of 20 by experts (Seckler 2014). Designers found only 37% of problems on average in a simple dialogue (Molich 1990).
- **Evidence:** [B] — (Seckler 2014; Molich 1990).
- **Limits:** Seckler used German-language newspaper registration forms in a lab; the form with the best original design (Spiegel) improved least. Conversion and mobile were not studied.

## Numbers at a glance
| Parameter | Value | Grade | Source |
|---|---|---|---|
| First-try successful submissions, original vs improved | 10 vs 24; 9 vs 24; 22 vs 28 (N = 65) | B | Seckler 2014 |
| Completion time reduction, improved forms | −25%, −33%, −18% (n.s.) | B | Seckler 2014 |
| KLM-predicted time reduction for the same forms | −7% to −23% | B | Seckler 2014 |
| Fixations / fixation duration / saccade time (NZZ) | 155 → 96; 62 s → 41 s; 9 s → 4 s | B | Seckler 2014 |
| Errors from missing format spec (NZZ) | 17 vs 2 | B | Seckler 2014 |
| Resubmissions without corrections (Sueddeutsche) | 14 vs 0 | B | Seckler 2014 |
| Subjective improvement (usability, load, satisfaction) | up to 16% | B | Seckler 2014 |
| Expert rating, "never clear completed fields" | 5.00 of 5 | C | Seckler 2014 |
| Radio buttons vs drop-down threshold | ≤4 radio; >4 drop-down (expert rating 2.36) | C | Seckler 2014 |
| Error report timing after user completes the thought | 2–4 s | C | Miller 1968; Smith 1986 |
| Acknowledge keystroke / pointing | ≤0.2 s | C | Smith 1986; Miller 1968 |
| Contest entries that found "accept parentheses, spaces, hyphens" | 8% | B | Molich 1990 |
| Contest entries with no error-prevention problem | 55% | B | Molich 1990 |
| Average problems found by designers | 11.2 of 30 (37%); serious 3.5 of 8 (44%) | B | Molich 1990 |
| Simple UI fixes incl. explicit error messages | 25% faster entry, 25% fewer errors | C | Smith 1986 (citing Keister & Gallaway) |
| Unclear CLI error: time lost | 6 h on a 30-min task (one participant) | C | Sampath 2021 |
| Time limit adjustment | off, or ≥10× default, or ≥20 s warning with ≥10 extensions | A | W3C 2023 |
| Coded data item length | ≤5–7 characters | C | Smith 1986 |

## Common misreadings
- "Validate inline on every keystroke so users get immediate feedback." — Miller 1968 and Smith & Mosier 1.7/3 say not to interrupt mid-entry; Seckler's tested forms showed errors after submit, embedded next to fields.
- "Confirm every delete and overwrite to be safe." — Smith & Mosier note that routine confirmations become routine and lose protective value; confirm selectively and prefer undo.
- "Experts know which form guidelines matter most." — Seckler 2014 found that the two guidelines users valued most were ranked 7th and 9th of 20 by experts.
- "Designers will catch error-handling problems in review." — Molich 1990: 55% of entries found no prevention problem and only 8% noticed rejected phone-number formats.
- "Blocking paste in password fields improves security." — WCAG 3.3.8 treats copy-and-paste and password managers as required assisting mechanisms when authentication relies on recall.

## Review checklist
- [ ] FE-1: Are format rules, required/optional status and units shown before input for every field that needs them?
- [ ] FE-2: Does the form ask only necessary questions, reuse data already entered, show defaults, and expose autocomplete purposes?
- [ ] FE-3: Are spaces, hyphens, parentheses and case variations accepted and normalized for unambiguous entries?
- [ ] FE-4: Do closed choices use constrained controls (radio ≤4, drop-down >4, checkboxes for multi-select) in an intuitive order?
- [ ] FE-5: Are labels above fields, in one column, one question per row, with field widths matching expected answers?
- [ ] FE-6: Is validation deferred until the user completes the field or submits, with no mid-entry interruptions?
- [ ] FE-7: Are errors described in text next to the field, using more than color, with entries kept, the cursor moved to the error, and completed fields never cleared?
- [ ] FE-8: Does every error message say what is wrong and how to fix it, in the user's language, briefly and without blame words?
- [ ] FE-9: Are errors and success/status messages announced to assistive technology and understandable when read aloud?
- [ ] FE-10: Have likely slips been designed out with constraints, accepted variants and up-front rules?
- [ ] FE-11: Is every keystroke and click acknowledged within 0.2 s, with completion confirmed or an error shown?
- [ ] FE-12: Does processing happen only on explicit submit, with cancel/back at every step and no unannounced context change on input?
- [ ] FE-13: Is submit disabled after the first click, is there a confirmation page stating next steps, and is there no reset button?
- [ ] FE-14: Can legal, financial and data-changing submissions be reviewed, corrected or reversed?
- [ ] FE-15: Are destructive actions two-step or undoable, with safe defaults and confirmations limited to hard-to-reverse cases?
- [ ] FE-16: Are time limits absent, or can users turn off, extend or adjust them without losing data?
- [ ] FE-17: Can users paste and use password managers, with no recall or puzzle test lacking an alternative?
- [ ] FE-18: Can AI-filled values be edited, refined or undone inline in one step?
- [ ] FE-19: Are form fixes prioritized by observed user errors and verified by user testing?

## Sources
- Amershi, S., et al. (2019). *Guidelines for human-AI interaction*. CHI '19. https://doi.org/10.1145/3290605.3300233
- Horvitz, E. (1999). *Principles of mixed-initiative user interfaces*. CHI '99. https://doi.org/10.1145/302979.303030
- Miller, R. B. (1968). *Response time in man-computer conversational transactions*. AFIPS Fall Joint Computer Conference. https://doi.org/10.1145/1476589.1476628
- Molich, R., Nielsen, J. (1990). *Improving a human-computer dialogue*. Communications of the ACM. https://doi.org/10.1145/77481.77486
- Nielsen, J. (1994). *Enhancing the explanatory power of usability heuristics*. CHI '94. https://doi.org/10.1145/191666.191729
- Norman, D. (1999). *Affordance, conventions, and design*. ACM interactions. https://doi.org/10.1145/301153.301168
- Sampath, H., Merrick, A., Macvean, A. (2021). *Accessibility of command line interfaces*. CHI '21. https://doi.org/10.1145/3411764.3445544
- Seckler, M., Heinz, S., Bargas-Avila, J. A., Opwis, K., Tuch, A. N. (2014). *Designing usable web forms: empirical evaluation of web form improvement guidelines*. CHI '14. https://doi.org/10.1145/2556288.2557265
- Smith, S. L., Mosier, J. N. (1986). *Guidelines for designing user interface software*. MITRE / DTIC ESD-TR-86-278. https://doi.org/10.21236/ada177198
- W3C (2023). *Web Content Accessibility Guidelines (WCAG) 2.2*. W3C Recommendation. https://www.w3.org/TR/WCAG22/
