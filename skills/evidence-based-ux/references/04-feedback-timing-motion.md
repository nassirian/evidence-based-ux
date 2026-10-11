# Feedback, response time, progress and motion

> How fast a UI must respond, how to show status and progress during waits, how to signal changes, when and how to animate, how to keep motion safe, and how to time notifications and interruptions. Evidence grades: **[A]** strong — replicated, large-N, meta-analytic, or an international standard; **[B]** moderate — one solid study or converging smaller studies; **[C]** weak — expert opinion, theory, small qualitative work, or extrapolation from lab psychology to UI.

## Rules

### FT-1. Give every user action a noticeable reaction and keep status visible
- **Do:** Every input produces a perceptible response. The screen is never blank or silent after an action. Show the current mode, the current state and what the system is doing at all times. Confirm completion of each entry or command, or show an error.
- **Why:** Visibility of system status was the first factor in Nielsen's analysis of 249 usability problems (6.1% of variance), and "feedback: show receipt of input" added 13% marginal coverage of problems (Nielsen 1994). "Provide feedback" is one of the nine dialogue principles (Molich 1990). For every action there should be a noticeable reaction; indicate status at all times; give feedback for completion of data entry (Smith 1986, 4.1/1, 4.2/1, 1.0/12). The gulf of evaluation and gesture critiques point to the same need (Norman 2010).
- **Evidence:** [B] — (Nielsen 1994; Molich 1990; Smith 1986; Norman 2010).
- **Limits:** Nielsen's factor analysis used a single rater and explains previously found problems. The principle is consistent across every source in this set, so the direction is not in doubt; the specific timings come from FT-2 to FT-6.

### FT-2. Acknowledge input within 0.1 s
- **Do:** Show visual acknowledgement of a click, tap, key press or control activation within 0.1 s (keystroke echo no later than 0.1–0.2 s). Acknowledge pointing and data-entry actions within 0.2 s at most. Keep control lockouts under 0.2 s and show when a control is locked.
- **Why:** Control activation should be acknowledged within 0.1 s, and keystroke echo within 0.1–0.2 s (Miller 1968). Smith & Mosier set 0.2 s for acknowledging entry and pointing, and 0.2 s for lockouts (Smith 1986, 1.0/4, 1.1/5, 3.0/19). The perceptual processing constant is about 0.1 s (Card 1991). During active work, even a 0.5 s wait for input attention is disruptive (Miller 1968).
- **Evidence:** [B] — (Miller 1968; Smith 1986; Card 1991).
- **Limits:** All three are expert estimates or derived constants, not direct experiments, but they converge. Miller assumed skilled users.

### FT-3. Update continuous interactions within 0.1 s and degrade fidelity before frame rate
- **Do:** For direct manipulation, dragging, drawing, scrubbing and dynamic-query filters, update the display within 100 ms of each input change, with no perceptible variability. Repaint animation frames at least every 0.1 s. If rendering cannot keep up, drop detail (for example hide text during motion) rather than frame rate.
- **Why:** Dynamic-query sliders coupled to display updates in under 100 ms, even with tens of thousands of items, beat form fill-in on speed and errors (Shneiderman 1996). The screen must repaint at least every 0.1 s to keep the illusion of animation, and the Information Visualizer degraded rendering to hold that cycle (Card 1991). Light-pen drawing needs ≤ 0.1 s response with no perceptible variability (Miller 1968).
- **Evidence:** [B] — (Shneiderman 1996; Card 1991; Miller 1968).
- **Limits:** Shneiderman's supporting experiments were small (18 and 20 participants). Card 1991 is a position paper citing earlier constants.

### FT-4. Meet the response-time ladder for discrete requests
- **Do:** Respond to simple display requests and page turns within 0.5–1.0 s (≤ 0.5 s while users scan or search). Complete other simple, routine requests within 2 s. Start complex graphic responses within 2 s and finish within 10 s. When a step takes several seconds, treat it as a defect to fix, not a norm.
- **Why:** Smith & Mosier give 0.5–1.0 s for simple display requests and NEXT PAGE, and ≤ 2.0 s for other simple entries (Smith 1986, 2.7.1/6, 3.0/18). Miller gives ≤ 1 s for next page, ≤ 2 s for routine requests and simple inquiries, and notes that above 2 s per frame users stop scanning (Miller 1968). Knowledge of results is effective within about 2 s (Miller 1968). Users of a faceted search interface with 3.7–4.3 s per refinement step (vs 0.3–0.37 s for the baseline) commented negatively on speed, even though they preferred the interface (Yee 2003).
- **Evidence:** [B] — (Smith 1986; Miller 1968; Yee 2003).
- **Limits:** Miller's values are "best calculated guesses" from 1968 terminals, and he states that a 2 s response is not a universal requirement. Smith & Mosier's values are 1986 judgments. Yee's latency was an implementation artefact, not a manipulated variable.

### FT-5. Put long delays only after a task closure
- **Do:** Keep responses inside a unit of work fast. If a delay longer than about 2 s is unavoidable, place it after a natural closure (submitting a form, finishing a step), not in the middle of a thought or a sequence of refinements. Let elementary task acts complete in about 10 s (5–30 s).
- **Why:** Delays over 2 s should follow only a task closure, and a standard 10 s system will not support sustained problem solving (Miller 1968). The unit task paces at about 10 s (5–30 s) (Card 1991). KLM places mental operators at chunk boundaries, and a system response before a mental step counts only if it exceeds 1.35 s (Card 1980).
- **Evidence:** [C] — (Miller 1968; Card 1991; Card 1980).
- **Limits:** The closure argument is theoretical. It converges across three sources but was not tested directly.

### FT-6. Beyond about 15 s, free the user; never block while the system works
- **Do:** For operations likely to exceed about 15 s, run them in the background, let the user continue other work, and notify on completion. Allow type-ahead so users can prepare the next input during short responses. After a failure, tell the user immediately how long recovery will take and preserve their work and context.
- **Why:** About 15 s rules out conversational interaction; above that, free the user to do other things. Recover from failures within 15 s, else within 5 min, tell the user how long, and preserve context (Miller 1968). Users should be able to issue the next request while agents work (Card 1991). Type-ahead lets system responses overlap user preparation (Card 1980).
- **Evidence:** [C] — (Miller 1968; Card 1991; Card 1980).
- **Limits:** Expert estimates. Some loading tasks tolerated ≤ 15 s favourably and ≤ 1 min acceptably (Miller 1968), so 15 s is a soft line.

### FT-7. For any wait beyond a few seconds, state the delay, show progress, and allow abort
- **Do:** Before or at the start of a long wait, say how long it may take and why. Show progress at regular intervals (at least every few seconds; status from background work about every 1 s). Provide a visible cancel or abort. Announce completion.
- **Why:** The long-wait specification is: tell the user it may take up to 30 s and why, add a progress indicator every 5 s, and provide abort (ESC); 74% of contest entrants spotted the missing delay warning (Molich 1990). Agents should give status feedback at intervals no longer than about 1 s (Card 1991). Smith & Mosier require user interruption, CANCEL, and indication of completion for lengthy processing (Smith 1986, 3.3/1, 3.3/3, 3.0/15). Missing exits during long retrieval were among the least-found problems (Molich 1990).
- **Evidence:** [B] — (Molich 1990; Smith 1986; Card 1991).
- **Limits:** Molich & Nielsen's design was never user-tested. The 5 s and 1 s intervals come from different contexts (dialogue terminals vs visualisation agents).

### FT-8. Use a percent-done progress indicator, graphical, with stages and liveness
- **Do:** For operations of more than about 1 s, show a percent-done indicator. Use a graphical bar when exact numbers are not needed. For multi-pass work, use a sectioned bar; for nested tasks, show current step and whole task. When progress cannot be computed, show an animated liveness indicator. Make a frozen indicator mean "stopped". Show estimated time remaining when it can be computed.
- **Why:** 86.1% of users liked progress indicators, and systems with them were significantly preferred (p = 0.0006) with delays of 1–17 s. With indicators, users judged delay variability correctly; without them they looked away (Myers 1985). Animated progress and activity are one of the recognised roles of animation (Chevalier 2016).
- **Evidence:** [B] — (Myers 1985; Chevalier 2016).
- **Limits:** One study of mostly computer-science students measuring preference, not productivity. The graphical, multi-stage and liveness guidance is argued, not tested (Myers 1985).

### FT-9. Make determinate progress bars feel faster with backwards, decelerating ribbing
- **Do:** For determinate bars of roughly 5–15 s, add animated ribbing that moves opposite to the fill direction and decelerates. If using pulsation, make it speed up toward completion. Avoid forward-moving or constant-velocity ribbing.
- **Why:** A 5 s solid bar felt equal to a 5.61 s ribbed bar, and a 15 s solid bar to a 16.75 s ribbed bar, about 11–12% shorter perceived duration (p < .001). Backwards decelerating ribbing had the highest preference; increasing pulsation beat constant or decreasing pulsation (Harrison 2010).
- **Evidence:** [B] — (Harrison 2010).
- **Limits:** Single lab, small samples, attended viewing, 5 and 15 s only. It changes perception, not actual latency. Waits over 15 s were not tested.

### FT-10. Never treat silence as success; expose status to assistive technology
- **Do:** Every command or action reports explicit success or failure. Expose status messages (saved, results updated, errors, progress) through role or properties so screen readers announce them without moving focus (WCAG 4.1.3, AA). Announce progress as text, not as spinner characters or Unicode bars. Avoid ASCII-art decoration in text interfaces.
- **Why:** WCAG 2.2 requires programmatic status messages (W3C 2023). Silent success left screen-reader users without status; one created duplicate resources because no confirmation appeared. Spinners and bars were read aloud as characters (Sampath 2021). Smith & Mosier require confirmation of completion of data entry (Smith 1986, 1.0/12).
- **Evidence:** [A] — (W3C 2023); CLI findings [B] — (Sampath 2021).
- **Limits:** Sampath's studies had 12 participants, one CLI and Windows with JAWS.

### FT-11. Explicitly signal changes; do not rely on users noticing them
- **Do:** When content changes after an automatic update, reload, refresh or any blank or flash, highlight or cue what changed, or name it in text. Put critical status where users are already looking. Use a localised motion onset or explicit text cue for important updates. Do not make users compare before and after states.
- **Why:** In the flicker paradigm, changes to marginal-interest items took on average 17.1 alternations (10.9 s) to detect, sometimes more than 80 alternations (about 50 s), against 1.4 alternations without blanks. Valid verbal cues removed the central vs marginal difference (Rensink 1997). Smith & Mosier recommend highlighting changed data after automatic updates (Smith 1986, 2.7.3/2). Animation can replay or summarise changes to reduce change blindness (Chevalier 2016).
- **Evidence:** [B] — strong for the phenomenon, moderate for UI transfer (Rensink 1997; Smith 1986; Chevalier 2016).
- **Limits:** Lab flicker displays with photographs, 10 observers per experiment.

### FT-12. Report input errors when the user finishes the unit, not mid-entry
- **Do:** Validate at the completion of a field or entry, not during typing. Present the error message promptly after the user completes the thought (about 2–4 s). Do not interrupt mid-thought.
- **Why:** Inform about input errors 2–4 s after the user completes the thought (Miller 1968). Report errors at completion of entry without interrupting (Smith 1986, 1.7/3). Error messages within 2–4 s (Smith 1986, 3.0/18).
- **Evidence:** [C] — (Miller 1968; Smith 1986).
- **Limits:** Judgment-based values. See the forms reference for the empirical work on when to show validation errors.

### FT-13. Give every animation a role, and use it to preserve object constancy
- **Do:** Name the role an animation serves (orientation, tracking a layout change, progress, feedback, revealing content, teaching a gesture) before designing it; remove animations without one. Animate transitions where objects move, appear or change layout, rather than cutting. Break complex transitions into stages. Keep motion away from content users must read or compare. Never use animation to mislead.
- **Why:** Chevalier identifies 23 roles in 5 categories and warns that animation's strong perceptual draw can stop users perceiving other parts of the display (Chevalier 2016). Animated zoom helps users form spatial models, though without evidence of faster task time (Cockburn 2009). Transitions preserve object constancy (Card 1991).
- **Evidence:** [C] — (Chevalier 2016; Cockburn 2009; Card 1991).
- **Limits:** Chevalier is a taxonomy, not effect evidence, and reports mixed outcomes for teaching animations. Evaluate animations against a static control and measure side effects such as dizziness and distraction.

### FT-14. Keep transitions between 0.3 and 1.0 s
- **Do:** Set view and zoom transitions to 0.3–1.0 s, longer for larger distances or more complex scenes. Avoid transitions so short that objects seem to jump or so long that users wait.
- **Why:** Zoom transitions of 0.3–1.0 s are appropriate depending on domain and distance (Cockburn 2009). Transition animations of about 1 s preserve object constancy; much shorter loses it and much longer causes boredom (Card 1991).
- **Evidence:** [B] — (Cockburn 2009; Card 1991).
- **Limits:** Card's 1 s is design rationale, untested in the paper. Chevalier gives no general timing rule and lists speed as an open research question (Chevalier 2016). Frequent micro-interactions likely need the low end of the range.

### FT-15. Keep flashes at or below three per second
- **Do:** Nothing flashes more than 3 times in any 1 s period, unless the flash is below the general and red flash thresholds (WCAG 2.3.1, A). Prefer no flashing at all (WCAG 2.3.2, AAA).
- **Why:** WCAG 2.2 defines a general flash as opposing luminance changes of ≥ 10% where the darker image is < 0.80, and permits small flashing areas (≤ 0.006 sr within any 10° field, about 341 × 256 px at 1024 × 768). 2.3.1 applies even to content not relied on for conformance (W3C 2023).
- **Evidence:** [A] — (W3C 2023).
- **Limits:** The threshold exception requires measurement; when in doubt, apply the 3-per-second limit without exception.

### FT-16. Let users pause, stop or hide motion and auto-updates
- **Do:** Moving, blinking or scrolling content that starts automatically, lasts more than 5 s and runs alongside other content can be paused, stopped or hidden. Auto-updating content can be paused, stopped, hidden or have its update rate controlled (WCAG 2.2.2, A). Motion animation triggered by interaction can be disabled unless essential (WCAG 2.3.3, AAA).
- **Why:** These are WCAG 2.2 requirements; 2.2.2 applies even to content not relied on for conformance (W3C 2023). Motion captures attention away from other content (Chevalier 2016).
- **Evidence:** [A] — (W3C 2023).
- **Limits:** 2.3.3 is AAA. Essential motion is excepted.

### FT-17. Reserve blinking for urgent items
- **Do:** Use blink coding only for items that need urgent attention, at 2–5 Hz with at least 50% on-time. Use highlighting sparingly so it keeps its meaning.
- **Why:** Smith & Mosier restrict blink coding to urgent attention, at 2–5 Hz with ≥ 50% ON, and note that highlighting is most effective when used sparingly (Smith 1986, 2.6/35, 2.6/37, 2.6/1).
- **Evidence:** [C] — (Smith 1986).
- **Limits:** Judgment-based 1986 guideline. Blinking that lasts more than 5 s must also be stoppable (FT-16), and must not exceed 3 flashes per second (FT-15); 2–3 Hz satisfies both.

### FT-18. Time notifications and agent interruptions to the user's task
- **Do:** Defer non-time-critical notifications while users are in a complex task or in the middle of one. Deliver them at task boundaries or idle moments. Let users declare busy periods and postpone or suppress interruptions except emergencies (WCAG 2.2.4, AAA). For agent or AI offers, time them to the user's attention, let unanswered offers time out gracefully, and accept "not now".
- **Why:** Perceived disruption correlated strongly with task complexity (Kendall τ = 0.477) and was highest mid-task or near the end; each 1-point rise in disruption multiplied acceptance odds by 0.581 (Mehrotra 2016). Mixed-initiative systems should consider the user's attention when timing services and not interrupt deep focus (Horvitz 1999). Time when to act or interrupt based on the user's task and environment (Amershi 2019, G3). Smith & Mosier recommend non-disruptive notification of arriving messages (Smith 1986, 5.5/5).
- **Evidence:** [B] — (Mehrotra 2016; Horvitz 1999; Amershi 2019; W3C 2023).
- **Limits:** Mehrotra had 20 Android users and inferred seen time from unlocks. Horvitz's timing data came from a few users. G3 was often judged not to apply to user-initiated features (Amershi 2019).

### FT-19. Match notification presentation to urgency and make value legible
- **Do:** Use high-priority, blocking presentation (heads-up, sound) only for genuinely urgent items. Show the sender and the value of the content in the notification summary so users can triage. Hold system-generated notifications that come from no person to a high bar of usefulness. Do not assume silent mode prevents interruption.
- **Why:** High-priority notifications got responses in 11.94 s vs 25.91 s for low-priority ones. Disruption was highest when the sender was not a person. 54% of notifications rated disruptive were still clicked because they were useful or important. Silent alerts were missed only 14.63% of the time (Mehrotra 2016).
- **Evidence:** [B] — (Mehrotra 2016).
- **Limits:** Small, unbalanced sample; the personality results (N=11) are likely inflated and are not used here.

## Numbers at a glance
| Parameter | Value | Grade | Source |
|---|---|---|---|
| Perceptual processing / animation frame | ≤ 0.1 s | B | Card 1991 |
| Control activation acknowledgement | ≤ 0.1 s | B | Miller 1968 |
| Keystroke echo | ≤ 0.1–0.2 s | B | Miller 1968 |
| Entry and pointing acknowledgement | ≤ 0.2 s | C | Smith 1986 |
| Control lockout | ≤ 0.2 s | C | Smith 1986 |
| Dynamic-query display update | < 100 ms | B | Shneiderman 1996 |
| Simple display request / next page | 0.5–1.0 s | C | Smith 1986 |
| Immediate response / status interval | about 1 s | B | Card 1991 |
| Other simple entries | ≤ 2.0 s | C | Smith 1986 |
| Delay boundary needing closure | > 2 s | C | Miller 1968 |
| Error message after completed entry | 2–4 s | C | Miller 1968; Smith 1986 |
| Refinement latency users disliked | 3.7–4.3 s per step | B | Yee 2003 |
| Unit task | about 10 s (5–30 s) | B | Card 1991 |
| Free the user | > 15 s | C | Miller 1968 |
| Long-wait progress interval | every 5 s | B | Molich 1990 |
| Users who liked progress indicators | 86.1% | B | Myers 1985 |
| Perceived shortening, backwards decelerating ribbing | about 11–12% | B | Harrison 2010 |
| Zoom transition | 0.3–1.0 s | B | Cockburn 2009 |
| View transition | about 1 s | C | Card 1991 |
| Change detection, marginal items with blanks | 17.1 alternations (10.9 s) | B | Rensink 1997 |
| Flash limit | ≤ 3 per s | A | W3C 2023 |
| Auto-moving content needing pause/stop/hide | > 5 s | A | W3C 2023 |
| Blink rate for urgent items | 2–5 Hz, ≥ 50% on | C | Smith 1986 |
| Notification response, high vs low priority | 11.94 vs 25.91 s | B | Mehrotra 2016 |
| Acceptance odds per 1-point disruption | × 0.581 | B | Mehrotra 2016 |
| Disruptive notifications still clicked | 54% | B | Mehrotra 2016 |

**Miller 1968 acceptable delays (expert estimates, selected categories)**
| Situation | Acceptable delay |
|---|---|
| Control activation (click, detent) | ≤ 0.1 s |
| Keystroke visual echo | ≤ 0.1–0.2 s |
| Light-pen drawing | ≤ 0.1 s, no perceptible variability |
| Dragging a symbol into place | up to 1 s |
| Next page, first lines | ≤ 1 s (0.5 s is long while searching) |
| Routine request acknowledgement | ≤ 2 s |
| Simple inquiry of listed information | ≤ 2 s |
| Simple status inquiry | 2 s (7–10 s if user knows processing is needed) |
| Input error notice | 2–4 s after the user completes the thought |
| Complex tabular inquiry | ≤ 4 s (2 s preferable) |
| Impromptu complex request acknowledgement | ≤ 5 s |
| Complex graphic inquiry | begin ≤ 2 s, complete ≤ 10 s |
| Loading programs or data; resume where I left off | ≤ 15 s favourable, ≤ 1 min tolerable |
| "Run my problem" | ≤ 15 s to stay in problem-solving frame |
| Failure recovery | within 15 s, else < 5 min, with time stated |

## Common misreadings
- "The 2-second rule is universal." — Miller states that a 2 s response is not a universal requirement; acceptable delay depends on purpose and closure (Miller 1968).
- "Miller's response times are experimental findings." — They are expert estimates he asked to be verified (Miller 1968).
- "0.1 / 1 / 10 s are attention limits; users leave after 10 s." — In Card 1991, 0.1 s is perceptual processing and animation frame time, 1 s is immediate response and transition length, and 10 s is the pacing of a unit task (Card 1991).
- "Progress bars make variable response times acceptable" or "constant delays are better than variable ones." — Myers found no significant preference between constant and variable delays, with or without indicators (Myers 1985).
- "A faster-looking progress bar fixes latency." — Ribbing shortens perceived duration by about 11% at 5–15 s; it does not change actual time and was not tested on long waits (Harrison 2010).
- "If it is on screen, users will see the change." — Change detection needs focused attention; large changes can go unnoticed (Rensink 1997).
- "Silent mode means no interruption." — Silent alerts were still noticed most of the time (Mehrotra 2016).

## Review checklist
- [ ] FT-1: Does every user action produce a visible reaction, and are mode, state and completion always shown?
- [ ] FT-2: Is every click, tap and key press acknowledged within 0.1 s (at most 0.2 s)?
- [ ] FT-3: Do drags, sliders and live filters update within 100 ms, and does the design drop detail rather than frame rate under load?
- [ ] FT-4: Do simple display requests complete in ≤ 1 s and routine requests in ≤ 2 s?
- [ ] FT-5: Do any delays over 2 s fall after a task closure rather than inside a refinement loop or mid-sequence?
- [ ] FT-6: Are operations over about 15 s run in the background with completion notification, and is work preserved on failure?
- [ ] FT-7: Does each long wait state its expected duration, show periodic progress, and offer cancel?
- [ ] FT-8: Do waits over about 1 s show a percent-done or liveness indicator, with stages for multi-step work?
- [ ] FT-9: Do determinate progress bars avoid forward or constant-velocity ribbing?
- [ ] FT-10: Is success always confirmed explicitly, and are status messages announced to screen readers without moving focus?
- [ ] FT-11: Are automatic updates and post-refresh changes highlighted or named, especially outside the user's focus?
- [ ] FT-12: Are input errors reported after the user finishes the field, not during typing?
- [ ] FT-13: Does each animation have a stated role, and is motion kept away from content users must read?
- [ ] FT-14: Are view and zoom transitions between 0.3 and 1.0 s?
- [ ] FT-15: Does nothing flash more than 3 times per second?
- [ ] FT-16: Can auto-moving content over 5 s and auto-updates be paused, stopped or hidden, and can interaction-triggered motion be disabled?
- [ ] FT-17: Is blinking limited to urgent items at 2–5 Hz (2–3 Hz to stay under the flash limit)?
- [ ] FT-18: Are non-urgent notifications and agent offers deferred during complex or mid-task work, and can users postpone them?
- [ ] FT-19: Does each notification's presentation match its urgency, and does it show sender and value?

## Sources
- Amershi et al. (2019). *Guidelines for human-AI interaction*. CHI '19. https://doi.org/10.1145/3290605.3300233
- Card, Moran, Newell (1980). *The keystroke-level model for user performance time with interactive systems*. Communications of the ACM. https://doi.org/10.1145/358886.358895
- Card, Robertson, Mackinlay (1991). *The information visualizer, an information workspace*. CHI '91. https://doi.org/10.1145/108844.108874
- Chevalier, Riche, Plaisant, Chalbi, Hurter (2016). *Animations 25 years later: new roles and opportunities*. AVI '16. https://doi.org/10.1145/2909132.2909255
- Cockburn, Karlson, Bederson (2009). *A review of overview+detail, zooming, and focus+context interfaces*. ACM Computing Surveys. https://doi.org/10.1145/1456650.1456652
- Harrison, Yeo, Hudson (2010). *Faster progress bars: manipulating perceived duration with visual augmentations*. CHI '10. https://doi.org/10.1145/1753326.1753556
- Horvitz (1999). *Principles of mixed-initiative user interfaces*. CHI '99. https://doi.org/10.1145/302979.303030
- Mehrotra, Pejovic, Vermeulen, Hendley, Musolesi (2016). *My phone and me: understanding people's receptivity to mobile notifications*. CHI '16. https://doi.org/10.1145/2858036.2858566
- Miller (1968). *Response time in man-computer conversational transactions*. AFIPS Fall Joint Computer Conference. https://doi.org/10.1145/1476589.1476628
- Molich, Nielsen (1990). *Improving a human-computer dialogue*. Communications of the ACM. https://doi.org/10.1145/77481.77486
- Myers (1985). *The importance of percent-done progress indicators for computer-human interfaces*. CHI '85. https://doi.org/10.1145/317456.317459
- Nielsen (1994). *Enhancing the explanatory power of usability heuristics*. CHI '94. https://doi.org/10.1145/191666.191729
- Norman (2010). *Natural user interfaces are not natural*. ACM interactions. https://doi.org/10.1145/1744161.1744163
- Rensink, O'Regan, Clark (1997). *To see or not to see: the need for attention to perceive changes in scenes*. Psychological Science. https://doi.org/10.1111/j.1467-9280.1997.tb00427.x
- Sampath, Merrick, Macvean (2021). *Accessibility of command line interfaces*. CHI '21. https://doi.org/10.1145/3411764.3445544
- Shneiderman (1996). *The eyes have it: a task by data type taxonomy for information visualizations*. IEEE Symp. Visual Languages. https://doi.org/10.1109/vl.1996.545307
- Smith, Mosier (1986). *Guidelines for designing user interface software*. MITRE / DTIC ESD-TR-86-278. https://doi.org/10.21236/ada177198
- W3C (2023). *Web Content Accessibility Guidelines (WCAG) 2.2*. W3C Recommendation. https://www.w3.org/TR/WCAG22/
- Yee, Swearingen, Li, Hearst (2003). *Faceted metadata for image search and browsing*. CHI '03. https://doi.org/10.1145/642611.642681
