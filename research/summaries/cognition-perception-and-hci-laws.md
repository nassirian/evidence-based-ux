# Group C — Cognition, Perception & Motor/Time Constants

Summaries of 12 papers (full-text extraction; some OCR noise, flagged where it affects numbers).

---

## 02__Accot-Zhai-1997_Beyond-Fitts-law-steering-law — Beyond Fitts' Law: Models for Trajectory-Based HCI Tasks (Johnny Accot & Shumin Zhai, 1997, CHI 97)
**Type:** empirical + model  ·  **Sample/method:** 4 lab experiments (10, 13, 10, 11 subjects) steering a Wacom stylus through goals/tunnels on an SGI display (1 cm tablet = 20 px); MT regressed on derived ID.

**Core claim.** Trajectory ("steering") tasks — e.g., cascading menus, drawing, 3D navigation — are not modeled by Fitts' law; steering time through a tunnel is *linear* in path length divided by path width (more generally the integral of 1/W along the path).

**Key findings**
- Exp 1 (goal passing, two goals): follows Fitts form, MT = a + b·log2(A/W + 1); fit as extracted "MT = −1347 + 391·log2(A/W+1)", r² = 0.987 (intercept may be OCR-garbled; verify). Error 7.4%.
- Recursive argument: N goals → ID_N = N·log2(A/(NW) + 1) → as N→∞, ID → A/W. **Steering law: MT = a + b·(A/W).**
- Exp 2 (straight tunnel, A = 250–1000 px, W = 20–90 px): MT = −188 + 78·(A/W), r² = 0.968; mean error 6.41%.
- Exp 3 (narrowing tunnel, W1 = 20–50, W2 = 8): ID = [A/(W2−W1)]·ln(W2/W1); MT = −532 + 93·ID, r² = 0.978; error ≈ 18%.
- General (integral) law: T_C = a + b·∫_C ds/W(s). Exp 4 (spiral): MT = 115 + 169·ID, r² = 0.971; error 13.7%. All tunnel fits r > 0.96.
- Local law: v(s) = W(s)/τ — instantaneous speed proportional to path width. τ ≈ 50 ms (Exp 2; v = −0.064 + 0.020W, r² = 0.986), ≈ 70 ms (Exp 3), ≈ 110 ms (Exp 4). Linearity saturates at large widths (widest widths excluded).
- Menu application: selecting the nth item of a cascading menu = vertical steer + horizontal steer: T_n = 2a + b(n/x + x), x = item width/height ratio; minimized when x = √n, i.e., wider items help deeper menus (equation partly garbled in extraction; authors call it an approximation assuming the same law for both directions).

**Design rules derivable**
- Model any constrained-path interaction (hover-to-open submenus, drag along a slider track, lasso within a channel) with MT ∝ length/width, not log; widening a tunnel is far more valuable than shortening a log-dependent pointing move. [moderate]
- In hierarchical/cascading menus, make the corridor to the submenu wide relative to its length (wider items, or fewer items to traverse); long, narrow cascades are disproportionately slow. [moderate]
- Expect high error rates in narrow steering paths (6–18% even when told to minimize errors); provide tolerance (e.g., delay before a submenu closes) rather than relying on precision. [moderate — tolerance mechanism is extrapolation]
- Use b (or τ) from the steering law, not Fitts IP, to compare devices for drawing/tracing tasks. [moderate]
- MISUSE: applying Fitts' log law to menus, drawing, or tracing tasks; the authors note Fitts-paradigm studies show little mouse-vs-pen difference, which does not transfer to writing/drawing.

**Boundary conditions & caveats.** Stylus/tablet only; small N; direction (L→R vs R→L, clockwise, centripetal) and handedness likely matter but weren't modeled; curvature not in the law; upper-bound saturation for wide paths; error rates not modeled.


---

## 02__Card-Moran-Newell-1980_Keystroke-level-model — The Keystroke-Level Model for User Performance Time with Interactive Systems (Stuart K. Card, Thomas P. Moran, Allen Newell, 1980, Communications of the ACM 23(7))
**Type:** model + empirical validation  ·  **Sample/method:** 1,280 user-system-task observations (28 expert users, 10 systems — text editors, graphics editors, executive subsystems — 14 tasks); 855 (69%) error-free instances compared with predictions.

**Core claim.** An expert's error-free execution time for a routine unit task, given a fully specified method, can be predicted to within ~20% by summing a few primitive operator times: T_execute = T_K + T_P + T_H + T_D + T_M + T_R.

**Key findings — operator values (Fig. 1)**
- **K** (keystroke/button press; SHIFT/CTRL count as separate K): best typist 135 wpm 0.08 s; good 90 wpm 0.12 s; average skilled 55 wpm 0.20 s; average non-secretary 40 wpm 0.28 s; random letters 0.50 s; complex codes 0.75 s; worst (unfamiliar with keyboard) 1.20 s. Users differ by up to a factor of 15.
- **P** (point with mouse): 1.10 s average; Fitts' form t_P = 0.8 + 0.1·log2(D/S + 0.5) s (range ~0.8 s to ~1.5 s for D/S = 128). Excludes the button press (0.2 s), coded as a following K.
- **H** (home hands between devices): 0.40 s.
- **D** (draw n_D straight segments of total length l_D cm, on 0.56 cm grid): 0.9·n_D + 0.16·l_D s.
- **M** (mental preparation): 1.35 s (fit R² = .84; SD ≈ 1.1 s).
- **R(t)** (system response): t, counted only for the non-overlapped part that makes the user wait; a response before an M counts only if > 1.35 s.
- M placement heuristics: Rule 0 insert M before all non-argument Ks and command-selecting Ps; delete if fully anticipated (PMK→PK), within a cognitive unit, before redundant terminators, or before terminators of constant strings.
- Accuracy: RMS error 21% per unit task; sequences of tasks 5% (editors) and 6% (graphics). Observed CV of task times ≈ .31. Varying t_M substantially (up to 2.0 s) raised RMS only 21%→23%.
- Simplifications are worse: keystrokes-only RMS 49% (r = .87); prorated mental overhead (67%) RMS 45% (r = .81); constant 0.43 s/operator RMS 34% (r = .92).
- Acquisition time (separate from execution): avg 2.0 s; 0.5 s from memory; 1.8 s from manuscript; 4.0 s when the user must also scan the display. Unit-task acquisition 2–3 s (manuscript), 5–30 s (routine design); execution rarely > 20 s.
- Benchmark: POET:SOS:DISPED predicted 100:84:45 vs observed 100:93:46. Parametric example: Backword vs Replace crossover at 4.9 words; proposed Backskip fastest for 2.7–10.2 words.

**Design rules derivable**
- Estimate expert task time at design time by writing the method as K/P/H/M/R operators and summing; compare alternatives before building. [strong — validated across 10 systems]
- Minimize device switching: each hand move between keyboard and mouse costs ~0.4 s, plus usually an M. [strong]
- Reduce decision points (each ~1.35 s) by making command sequences chunkable (consistent, predictable terminators; anticipated follow-ups). [moderate]
- Allow type-ahead so system responses overlap user preparation; responses under ~1.35 s that precede a mental step are largely hidden for experts. [moderate]
- Don't trust differences smaller than the model's error (21% single task; ~9% over a 5-task benchmark). [strong]
- MISUSE: applying KLM to novices, error recovery, learning, or method choice — it assumes experts, routine tasks, fully specified methods, error-free performance. Also misused: counting keystrokes only (RMS 49%).

**Boundary conditions & caveats.** t_M was estimated from the same data (inflates fit); M placement is ambiguous and expertise-dependent; pointing constant from 1978 mouse studies; executive tasks all over-predicted.


---

## 02__Card-Robertson-Mackinlay-1991_Information-visualizer — The Information Visualizer, an Information Workspace (Stuart K. Card, George G. Robertson, Jock D. Mackinlay, 1991, ACM CHI '91)
**Type:** theory/system design rationale  ·  **Sample/method:** design argument from information-cost-structure observations; describes an implemented system (3D/Rooms, Cognitive Co-processor, visualizations such as Cone Tree, Perspective Wall). No user study.

**Core claim.** Information retrieval should be reframed as managing the *cost structure* of information for work: enlarge and densify cheap "immediate storage," couple user and agents through fast interaction cycles tuned to human time constants, and raise abstraction via visualization.

**Key findings**
- Six observations: (1) hierarchy improves information processed per cost; (2) high cost ratios between near and far storage (RAM 80 ns, disk 20 ms → 2.5×10^5; optical 5 s → 2.5×10^2); (3) locality of reference (working set); (4) reference clustering — abrupt jumps between working sets; (5) systems adjust to maximize info/cost; (6) abstraction by lower levels.
- **Human time constants (Table 3):**
  - **Perceptual processing ≈ 0.1 s** — screen must repaint at least every 0.1 s to maintain the illusion of animation; a "Governor" degrades rendering quality (e.g., drops text during motion) to hold the cycle.
  - **Immediate response ≈ 1 s** — an unprepared response to a stimulus takes ~1 s; agents should give status feedback at intervals no longer than this; transition animations designed to take ~1 s (much shorter → loss of object constancy; much longer → boredom).
  - **Unit task ≈ 10 s (5–30 s)** — users should be able to complete an elementary task act within ~10 s; user stays active and can issue the next request while agents work.
- Single huge workspace: search cost rises rapidly with number of elements (unless space is meaningful); overload of immediate storage → thrashing. Rooms/3D Rooms add multiple, switchable, shareable workspaces; an 80-page org chart fit one 3D/Rooms screen.

**Design rules derivable**
- Keep animation/feedback frame time ≤ 0.1 s; degrade fidelity (e.g., hide text during motion) rather than drop below it. [moderate — constant from Card et al. 1983]
- Show progress/status from background work at least every ~1 s. [moderate]
- Make view-transition animations ~1 s to preserve object constancy. [weak–moderate — design rationale, untested here]
- Design so an elementary task act completes in ~10 s (5–30 s); never block the user while agents work. [moderate]
- Organize work into multiple task-specific workspaces matching reference clusters; keep frequently used items in the cheapest-access tier. [weak — argued, not tested]
- MISUSE: treating 0.1/1/10 s as Nielsen-style attention limits ("user leaves after 10 s"); here 10 s is the pacing of a unit task, and 1 s is about conversational status feedback/animation length.

**Boundary conditions & caveats.** Position paper; constants are cited from Card, Moran & Newell (1983) and Newell (1990); 1991 hardware ratios; benefits of 3D not empirically demonstrated in this paper.


---

## 02__Cowan-2001_Magical-number-4 — The Magical Number 4 in Short-Term Memory: A Reconsideration of Mental Storage Capacity (Nelson Cowan, 2001, Behavioral and Brain Sciences 24(1))
**Type:** review/theory (target article + ~40 commentaries)  ·  **Sample/method:** integrative review of capacity estimates across paradigms that block chunking/rehearsal; theoretical framework (embedded processes: capacity-limited focus of attention within activated LTM).

**Core claim.** When rehearsal, long-term-memory recoding, and sensory refill are prevented, adults hold about **4 chunks** (group means 3–5; individuals ~2–6); Miller's 7±2 is a *compound* estimate inflated by rehearsal and chunking. The limit lies in the focus of attention.

**Key findings**
- Four conditions for observing pure capacity: (1) information overload, (2) blocking recoding/rehearsal (e.g., articulatory suppression), (3) performance discontinuities, (4) indirect effects.
- Sperling whole report: ~4 items; partial-report cue useless after ~1 s (≈1.3 of 4 cued items × 3 rows ≈ 4). Auditory analog (Darwin et al.): ~4, decline over ~4 s.
- Luck & Vogel change detection (1–12 colored squares, 100 ms, 900 ms gap): near-perfect for 1–3, slightly worse at 4, much worse beyond. Limit applies to **integrated objects, not features** — retaining 4 feature dimensions per object as easy as 1. Individual estimates 2.2–4.7 (one trained student ≈ 6).
- Unattended spoken digits (Cowan et al. 1999): flat recall across list lengths ≈ 3.5 in adults; ignored-speech means adults 3.51, 4th graders 2.99, 1st graders 2.34 (attended 5.43, 4.31, 3.48); individual range ≈ 2 to almost 6.
- Errorless immediate recall ≈ 3–4 items. Enumeration (subitizing): errors near zero for 1–4 items, then rise ~15% per item; RT slope steepens after ~4. Multi-object tracking: 3 easy, 5 of 10 very hard.
- Recall comes in bursts/clusters of ~4 (≤5) items; Fisher's visual search fits k = 4 channels.
- Theoretical optima: Dirlam chunk size 3.59 per hierarchy level; MacGregor: grouping helps beyond 4 (exhaustive) or 5.83 (self-terminating) items.
- Chunk = concepts strongly associated with each other, weakly with other chunks; chunks can grow without bound via LTM, so the limit is in chunks, not items or bits.
- Commentary dissent (noted): Avons et al. argue the limit reflects memory for events/context, not a fixed item count; several (Nairne & Neath, Rensink, Taatgen) question the STM/LTM distinction; Baddeley contrasts with an episodic buffer.

**Design rules derivable**
- Don't require users to hold more than ~3–4 new, unrelated items in mind across a step (codes, settings from a previous screen, comparison values); keep them visible instead. [strong for the limit; moderate for the UI transfer]
- Group information into meaningful chunks (e.g., digit grouping, labeled clusters) so each occupies one slot; expect clusters of ~3–4 to work best. [moderate]
- When users must track multiple changing objects (dashboards, multi-object animation), assume ≤ ~4 trackable at once. [moderate]
- For counts users must read at a glance, ≤4 items are apprehended instantly; beyond that, show the number. [moderate]
- Design for the low end of individual differences (≈2–3), not the mean. [moderate — extrapolation]
- MISUSE: "no more than 4 items on a screen/menu." The limit concerns what must be *held in mind* without external support or chunking; visible, recognizable options are not stored in STM. Equally, "7±2 menu items" (see Miller 1956) is not rescued by changing the number to 4.

**Boundary conditions & caveats.** Pure capacity only observable under constrained lab conditions; real tasks yield compound estimates (rehearsal, LTM, sensory memory); chunk sizes rarely measured directly; many commentators dispute the fixed-slot interpretation.


---

## 02__Fitts-1954_Information-capacity-of-human-motor-system — The Information Capacity of the Human Motor System in Controlling the Amplitude of Movement (Paul M. Fitts, 1954, Journal of Experimental Psychology 47; reprinted JEP: General 1992)
**Type:** empirical  ·  **Sample/method:** 3 tasks — reciprocal tapping (16 right-handed men; 1-oz and 1-lb styluses; W = 0.25–2 in, A = 2–16 in), disc transfer (16 men; W = 1/16–1/2 in, A = 4–32 in), pin transfer (20 students; W = 1/32–1/4 in, A = 1–16 in).

**Core claim.** The motor system has an approximately constant information capacity (bits/s) for a given limb and movement type; movement time scales with the information required to hit a tolerance W at amplitude A.

**Key findings**
- **Index of difficulty: I_d = −log2(W_s / 2A) = log2(2A/W_s)** bits/response (2A chosen so the index is > 0; adds one bit).
- **Index of performance: I_p = −(1/t)·log2(W_s / 2A)** bits/s, t = mean time per movement.
- Movement time increased with A and with decreasing W in every task; conditions spanned 1–10 bits/response.
- Tapping (light stylus): eight best conditions 10.3–11.5 bits/s; heavy stylus similar (r = .97 between I_p profiles), slightly lower and optimum shifted to smaller A. Disc transfer: 7.5–10.4 bits/s (best 8 within 1.3). Pin transfer: 8.9–12.6 bits/s (best 10 within 1.0). Optimal capacity ≈ 10–12 bits/s.
- Errors low: 1.2% (light), 1.3% (heavy); worst condition (W = 0.25, A = 16) 3.6%/4.1%; errors slightly higher for tighter tolerances (subjects under-slowed).
- I_p falls off at extremes; amplitudes of 4–8 in most consistently efficient; 1–2 in and smallest tolerances less efficient.
- Practice effects small (3–6%).

**Design rules derivable**
- Predict and compare target-acquisition cost via log2(distance/width): halving distance or doubling target size buys the same ~1 bit. [strong — massively replicated, per later work]
- Make frequently used targets larger and nearer; increases in size pay off logarithmically, so small targets far away are disproportionately costly. [strong]
- Very tiny tolerances degrade efficiency beyond the model; avoid requiring sub-millimetre precision. [moderate]
- MISUSE: quoting "Fitts' law" as MT = a + b·log2(D/W+1) and attributing it to this paper — Fitts used log2(2A/W) and a rate (I_p) per condition; the Shannon formulation is MacKenzie's. Also misused for tasks without aimed movement (see Accot-Zhai, MacKenzie).

**Boundary conditions & caveats.** 1-D reciprocal movements of the arm with visual feedback; index ignores direction, force, grasp; capacity differs by limb/muscle group (fingers possibly higher); information estimates depend on an arbitrary range assumption.


---

## 02__Harrison-2010_Faster-progress-bars — Faster Progress Bars: Manipulating Perceived Duration with Visual Augmentations (Chris Harrison, Zhiquan Yeo, Scott E. Hudson, 2010, CHI 2010 note)
**Type:** empirical  ·  **Sample/method:** 4 paired-comparison studies of 5 s (and 15 s) progress bars: Studies 1–2 with 20 participants, Study 3 with 10, Study 4 (method of adjustment) with 16; two-sided sign tests.

**Core claim.** Purely visual augmentations can make a progress bar of identical duration feel shorter; backwards-moving, decelerating ribbing works best (~11% shorter perceived duration).

**Key findings**
- Pulsation (sinusoidal light-blue↔blue; 1.1 Hz start): increasing frequency preferred over constant/decreasing (p < .05 / p < .001); best "Fast Increasing" (1.1→1.25 Hz), mean preference 0.21.
- Ribbing (bar moves right at 128 px/s; rib velocities ±7.8 to ±31.3 mm/s): backwards (opposite to progress) ribbing preferred over still and forward (p < .001); decelerating preferred over still and constant (Mac OS X–style) (p < .05). Backwards Decelerating had the highest average preference (0.34 vs 0.29 for Backwards Accelerating). Mechanism: induced motion — relative velocity increases perceived speed.
- Study 3: at 5 s only a trend (pulsating > solid, p < .1); at 15 s both ribbed and pulsating beat solid (p < .05); ribbed slightly preferred over pulsating (33 vs 30 trials, 17 equal).
- Study 4: a 5 s solid bar felt equal to a 5.61 s ribbed bar (SE 0.14; +12.2%); 15 s solid ≈ 16.75 s ribbed (SE 0.45; +11.7%), p < .001. 15 s results were still rising at round 8 — effect may grow with duration.

**Design rules derivable**
- For determinate progress bars, add animated ribbing that moves opposite to the fill direction, decelerating, to reduce perceived wait by ~11% at 5–15 s. [moderate — single lab, small N, significant]
- Prefer pulsation that speeds up toward completion over constant or slowing pulsation. [weak–moderate]
- Avoid forward-moving or constant-velocity ribbing if the goal is perceived speed. [moderate]
- MISUSE: claiming the effect holds for long waits or makes real latency irrelevant; durations > 15 s were not tested (attention collapsed in pilots), and the effect does not change actual time.

**Boundary conditions & caveats.** Very short durations (5/15 s); sequential, attended viewing in a lab; preference ≠ satisfaction; small samples (mean age 19–23); the 11% figure comes from one design vs a solid bar.


---

## 02__MacKenzie-1995_Movement-time-prediction-in-HCI — Movement Time Prediction in Human-Computer Interfaces (I. Scott MacKenzie, 1995 reprint of 1992 GI paper, in Baecker et al., Readings in Human-Computer Interaction, 2nd ed.)
**Type:** review + model refinement  ·  **Sample/method:** review of Fitts' law in HCI; example stylus data set (16 A×W conditions, ~470 trials each); worked design example.

**Core claim.** Fitts' law is a robust predictive tool for HCI pointing if three refinements are applied: the Shannon formulation, a 2-D definition of target width, and error-rate normalization via effective width.

**Key findings**
- Fitts: ID = log2(2A/W); MT = a + b·ID; IP (bandwidth) = 1/b.
- Welford: ID = log2(A/W + 0.5). **Shannon (preferred): ID = log2(A/W + 1); MT = a + b·log2(A/W + 1)** — better fit, mirrors the information theorem, never negative.
- Example stylus data: MT = 53 + 148·ID ms (r = .992); grand means 645 ms, 3.6% errors, 6.3 bits/s (direct) vs 6.8 bits/s (1/slope).
- Published mouse models vary widely: Card et al. 1978 MT = 1030 + 96 ID (10.4 bits/s by slope, but 2.0 bits/s by mean ID/MT — a factor of five); Boritz 1320 + 430 ID (2.3); Epps 108 + 392 ID (2.6); MacKenzie et al. −107 + 223 ID (4.5); Han 389 + 175 ID (5.7); Gillan 795 + 83 ID (12.0). Intercepts should be "a few hundred ms" at most.
- 2-D targets: "status quo" horizontal width gives low/negative IDs (e.g., Welford ID = −2.6 bits for a 6 cm word approached from 2 cm); use **W′ (width along approach vector)** or **SMALLER-OF(W, H)** — both beat status quo, no difference between them.
- **Effective width** We normalizes to a 4% error rate; e.g., 2% errors on a 5 cm target → We = 2.066/2.326 × 5 = 4.45 cm. Published error rates range 0–25%.
- Mouse pointing MT = 230 + 166 ID (6.0 bits/s); dragging MT = 135 + 249 ID (4.0 bits/s). File-delete example (14 cm, 2 cm icons): drag-to-trash 882 ms, point-select 728 ms, stroke-through 528 ms (~40% faster); point-select better only for A < 2.72 cm.
- Do not use for drawing, inking, cursive writing, isometric joysticks, or velocity-control devices.

**Design rules derivable**
- Use MT = a + b·log2(A/W + 1) with device-specific a, b to compare layouts before building. [strong]
- For non-square targets, compute W along the approach direction (or the smaller dimension); short wide targets approached vertically are effectively small. [moderate]
- Dragging is slower than pointing (≈4 vs 6 bits/s for mouse); prefer point-select or short gestures over long drags for frequent actions. [moderate]
- Report and compare devices/techniques using effective width (error-normalized throughput); don't compare speeds with unequal error rates. [strong — methodological]
- MISUSE: comparing bandwidths across studies with large intercepts or differing error rates; applying Fitts to steering/drawing tasks.

**Boundary conditions & caveats.** Assumes rapid aimed movements with negligible/known mental preparation, system response, and homing time; 3-D untested at time of writing; worked example ignores multi-file and undo.


---

## 02__Miller-1956_Magical-number-seven — The Magical Number Seven, Plus or Minus Two: Some Limits on Our Capacity for Processing Information (George A. Miller, 1956, Psychological Review 63(1))
**Type:** review/theory  ·  **Sample/method:** information-theoretic synthesis of absolute-judgment, subitizing, and memory-span experiments.

**Core claim.** Two different limits happen to sit near seven: the span of *absolute judgment* (limited in bits, ~2.6 bits for unidimensional stimuli) and the span of *immediate memory* (limited in chunks, ~7). Recoding into larger chunks is the powerful way around the memory limit; the shared "seven" is probably coincidence.

**Key findings**
- Channel capacities for unidimensional absolute judgments: pitch 2.5 bits (~6 categories); loudness 2.3 (~5); saltiness 1.9 (~4); pointer position 3.25 (Coonan & Klemmer 3.2–3.9; 10–15 positions); square size 2.2; size 2.8, hue 3.1, brightness 2.3; area 2.6–2.7; line length 2.6–3.0; direction 2.8–3.3; curvature 1.6–2.2. Mean 2.6 bits (SD 0.6) ≈ 6.5 categories (range 3–15).
- Multidimensional stimuli raise total capacity but lower per-dimension accuracy: dot in square 4.6 bits (~24 positions); pitch+loudness 3.1; salt+sweet 2.3; colors (hue+saturation) ~3.6 (11–15); 6 auditory dimensions × 5 levels 7.2 bits (~150 categories); 8 binary dimensions 6.9 bits (~120).
- Subitizing: up to 5–6 dots no errors; beyond ~7 estimation (>4 bits, 20–30 categories) — Miller doubts it's the same process.
- Memory span is roughly constant in *items*, not bits: ~9 binary digits, ~7–8 decimal digits, ~5 monosyllabic words (vs. 2–3 predicted if bits were constant).
- Recoding: Smith's subjects (20) span 9 binary, 7 octal; with 4:1/5:1 recoding one trained subject recalled ~40 binary digits.
- Three ways to stretch absolute-judgment limits: relative (not absolute) judgments, more dimensions, sequential judgments.

**Design rules derivable**
- Don't encode more than ~4–7 distinguishable levels on a single visual dimension (e.g., hue, size, brightness, line length) if users must identify levels absolutely; use redundant multi-dimensional coding or labels for more. [strong]
- Prefer relative comparison (side-by-side, legend adjacent) over absolute identification of encoded values. [strong]
- Group long strings (codes, numbers) into meaningful chunks to fit memory span. [strong]
- Seven-point rating scales are reasonable for unidimensional judgments. [moderate]
- MISUSE: "menus/navs should have 7±2 items" — the paper is about absolute judgment and unaided recall, not about scanning visible options; Miller himself calls the recurrence of seven a likely "Pythagorean coincidence." Also misused: treating 7 as a precise memory capacity (see Cowan 2001: ~4 pure).

**Boundary conditions & caveats.** Pre-1956 data, often pooled across subjects (underestimates); exceptions like absolute pitch (50–60 pitches); span depends on material and practice.


---

## 02__Miller-1968_Response-time-in-conversational-transactions — Response Time in Man-Computer Conversational Transactions (Robert B. Miller, 1968, AFIPS Fall Joint Computer Conference 33)
**Type:** theory / expert estimate  ·  **Sample/method:** analytic taxonomy of 17 response categories with estimated acceptable delays, grounded in psychological rationale (short-term memory, closure); author states these are "best calculated guesses."

**Core claim.** There is no single acceptable response time; acceptability depends on the user's purpose and whether a psychological closure has been reached. Efficiency drops in step-discontinuities, with ~2 s as a key boundary for maintaining thought continuity.

**Key findings — general**
- Conversation: response expected within ~2–4 s; silences > 4 s are embarrassing. Knowledge-of-results effective within ~2 s, peak ~0.5 s for simple responses.
- **General rule: delays > 2 s should follow only a task closure (perceived or structured).** A standard 10 s system won't support sustained problem solving; a 10 s system may be no better than 1 min or 5 min for some tasks.
- Delay tolerance: ±8% (16% range) for 2–4 s intervals; < 10% at 0.6–0.8 s; 20–30% at 6–30 s. "Psychological present" 2.3–3.5 s (up to 12 s).
- A response can carry several messages (heard, accepted, interpreted, working); it must meet the fastest component's time.

**Key findings — 17 topics (acceptable delay)**
1. Control activation (click, detent): ≤ 0.1 s. Keystroke visual echo: ≤ 0.1–0.2 s. Light-pen character selection brightening: within 0.2 s.
2. "Are you listening?" (session start): up to 3 s; best within 1 s. During active work, input attention must be immediate — 0.5 s wait is disruptive.
3. "Can you do work for me?": routine request ack ≤ 2 s; impromptu complex ≤ 5 s. Loading programs/data ≤ 15 s (≤ 1 min tolerable). "Resume where I left off" ≤ 15 s favorable, ≤ 1 min acceptable.
4. "Do you understand me?" (input error): inform 2–4 s after the user completes the thought — don't interrupt mid-thought.
5. Identification (badge): card-seated feedback < 0.4–0.5 s; "OK, read you" ≤ 2 s and a fixed length; inquiry-terminal identification up to 5–7 s.
6. "What work next?" (production slip): 10–15 s; CAI next topic < 5 s.
7. Simple inquiry of listed information: ≤ 2 s.
8. Simple status inquiry: 2 s, relaxable to 7–10 s if user knows processing is needed.
9. Complex tabular inquiry: ≤ 4 s; multi-part answers can arrive 4 s apart; 2 s preferable.
10. Next page: ≤ 1 s for first lines; when searching, 0.5 s is long; custom index frames 2 s (tell user); > 2 s per frame → users stop scanning; skipping 10 pages should be as fast as 1.
11. "Run my problem": ≤ 15 s to stay in problem-solving frame.
12. Light-pen vs keyboard category entry: 2 s vs 3 s; 1–1.5 s attention-shift adaptation; page-turn ≤ 1 s max.
13. Light-pen drawing: ≤ 0.1 s with no perceptible variability; dragging a menu symbol into place: up to 1 s.
14. Complex graphic inquiry: begin ≤ 2 s, complete ≤ 10 s.
15. Dynamic model manipulation: no estimate; scenarios compressible into ~50-min periods.
16. Structural design: rule-violation notice ~2 s; after completing a design chunk, user will wait 1–2 min; relevant motion ≤ 10 s keeps arousal; "heat" cools in interruptions < 1 min.
17. Command into operational system: acknowledge understanding ≤ 4 s; execution confirmation can take minutes.
- Postscript 1: ~15 s rules out conversation; if > 15 s, free the user to do other things.
- Postscript 2: recover after failures within 15 s, else < 5 min; immediately tell the user how long; preserve context so work isn't lost.

**Design rules derivable**
- Give mechanical/visual acknowledgment of any control activation within 0.1 s (keystroke echo ≤ 0.1–0.2 s). [moderate — consistent with later work, but here an estimate]
- Answer routine, frequent queries within 2 s; place any longer waits after a natural task closure. [moderate]
- Page/frame advance ≤ 1 s (≤ 0.5 s when users scan/search). [weak–moderate]
- Defer input validation errors until the user finishes the unit (2–4 s after), not mid-entry. [weak]
- Beyond ~15 s, release the user (background the job, notify on completion); after failures, state expected recovery time immediately and restore context. [moderate]
- Keep delays consistent (identification confirmations should be fixed-length). [weak]
- MISUSE: "the 2-second rule is universal" — Miller explicitly says it is not; also misused: citing these numbers as experimental findings (they are expert estimates he asks to be verified).

**Boundary conditions & caveats.** 1968 terminals/light pens; skilled users assumed (novices differ); no empirical tests; tolerance ranges mostly unspecified.


---

## 02__Myers-1985_Percent-done-progress-indicators — The Importance of Percent-Done Progress Indicators for Computer-Human Interfaces (Brad A. Myers, 1985, CHI '85 Proceedings)
**Type:** empirical + design discussion  ·  **Sample/method:** 48 unpaid volunteers (mostly CS grad students, ~1/5 novices) used a form-based query system (~14 queries) twice; delays constant 10 s or uniform 1–17 s (mean 8.601 s), with/without progress indicator; 10-item 9-point semantic differential.

**Core claim.** Users prefer systems with percent-done progress indicators; they reassure that the request was accepted and is progressing, and let users plan their time.

**Key findings**
- Progress vs no progress: significant preference (p = 0.0006). 86.1% liked progress indicators; mean usefulness 2.94 (1 = very useful, 9 = useless/annoying).
- Constant vs variable delay: **no** significant preference (p = 0.2046; without progress p = 0.1497), failing to replicate earlier claims (Miller 1977). Without progress: constant 5.73 > variable 5.41; with progress: variable 5.98 > constant 5.90 — not significant.
- With indicators, users judged variability correctly (interaction p = 0.0011); without them, users looked away and rated both the same.
- Second version rated lower than first (p = 0.0025).
- Design guidance: graphical > numeric for quick approximate reading, implies approximation, fits small spaces; stalled indicator signals a crash; multi-pass jobs → sectioned bar; nested tasks → two indicators (current step + whole task); when % can't be computed, show "random progress" (dots, busy bee, changing pattern) to show liveness; a centralized routine keeps indicators uniform.

**Design rules derivable**
- Show a percent-done indicator for long operations (here ~1–17 s delays). [moderate — one significant study]
- Use a graphical bar, not just a numeric %, when exactness isn't needed. [weak — argued]
- For multi-stage work, show overall plus current-stage progress. [weak]
- If progress can't be estimated, show an animated liveness indicator; a frozen indicator should mean "stopped." [weak]
- Provide an estimated time remaining when it can be computed. [weak — suggested alternative]
- MISUSE: "progress bars make variable response time acceptable" — that hypothesis was not supported statistically.

**Boundary conditions & caveats.** Mostly expert CS students; subjective scales chosen "intuitively"; single 40-min session; preference not productivity.


---

## 02__Rensink-1997_To-see-or-not-to-see-change-blindness — To See or Not to See: The Need for Attention to Perceive Changes in Scenes (Ronald A. Rensink, J. Kevin O'Regan, James J. Clark, 1997, Psychological Science 8(5))
**Type:** empirical  ·  **Sample/method:** flicker paradigm (image A 240 ms, gray blank 80 ms, A, A′, A′…) with 48 real-world color scenes (27°×18°); 10 naive observers per experiment; changes in color, location, or presence; Central-Interest (CI, mentioned by ≥3 of 5 describers) vs Marginal-Interest (MI) targets.

**Core claim.** Change is perceived only when the changed object receives focused attention; brief blanks swamp the motion transients that normally draw attention, so large, repeated changes go unnoticed. Observers do not build a complete, detailed scene representation.

**Key findings**
- Exp 1: MI changes needed avg 17.1 alternations (10.9 s), sometimes > 80 alternations (50 s); CI changes 7.3 alternations (4.7 s); MI slower than CI for all change types (p < .001 presence, p < .05 color, p < .001 location) despite MI changes being >20% larger in area (22 vs 18 sq deg).
- Without blanks: 1.4 alternations (0.9 s), no MI/CI difference.
- Exp 2: longer uninterrupted display (560 ms) → only slight speedup; consolidation time not the cause.
- Exp 3: valid verbal cues (50% or 100% validity) greatly speed detection (p < .001 MI); with 100% valid cues MI/CI difference disappears; invalid cues slight (n.s.) slowdown → visibility is not the limit.
- Error rate 1.2%. Prior work: brief-display change detection poor with ISI > 60–70 ms; detection equivalent to monitoring 4–5 items. Scene gist available in 100–150 ms.
- Proposal: unattended items are overwritten by new input; only attended items enter a durable store; attention pulled by transients or pushed by high-level interest.

**Design rules derivable**
- When content changes during a screen refresh, page reload, blank/flash, or other transient-masking event, explicitly signal the change (highlight, animate, cue) — otherwise users may miss even large changes. [strong for the phenomenon; moderate for UI transfer]
- Use localized motion/transient onsets (or explicit textual cues) to draw attention to important updates; don't rely on users comparing before/after states. [moderate]
- Changes to peripheral/"marginal-interest" elements are noticed far later than changes to central ones; put critical status where users' interest is, or cue it. [moderate]
- Telling users what changed (a label naming it) dramatically speeds detection. [moderate]
- MISUSE: assuming users "see everything on screen" because it's visible, or that silent in-place updates will be noticed.

**Boundary conditions & caveats.** Lab flicker displays with artificial blanks; photographs not UIs; 10 observers per experiment; "interest" defined by verbal descriptions.


---

## 02__Wagemans-2012_Century-of-Gestalt-psychology — A Century of Gestalt Psychology in Visual Perception: I. Perceptual Grouping and Figure–Ground Organization (Johan Wagemans, James H. Elder, Michael Kubovy, Stephen E. Palmer, Mary A. Peterson, Manish Singh, Rüdiger von der Heydt, 2012, Psychological Bulletin 138(6))
**Type:** review  ·  **Sample/method:** comprehensive narrative review of a century of psychophysics, ecological statistics, computational and neural work on grouping and figure–ground.

**Core claim.** Gestalt principles are real, pervasive, and now partly quantified, but they operate at multiple levels, combine (sometimes additively, sometimes not), are tuned to natural-image statistics, and are influenced by experience and attention — not just innate, early, autonomous laws.

**Key findings — grouping principles**
- **Proximity:** strongest, best quantified. Oyama: time ratio t_h/t_v = (d_h/d_v)^−α, α ≈ 2.89. Kubovy et al. **pure distance law**: grouping log-odds is a linear function of relative distance only, independent of lattice configuration; if a distance ratio exceeds ~1.5 that grouping is almost never seen. Scale-invariant; natural contours follow a power law with α = 2.92 (Elder & Goldberg) — matching perception.
- **Similarity** (color, size, orientation, brightness, contrast): **additive** with proximity in dot lattices (parallel indifference curves, Kubovy & van den Berg 2008); for contours, contrast reversal effects interact non-additively; ecologically, brightness informative, contrast weak.
- **Common fate:** powerful (breaks camouflage); **generalized common fate** includes common luminance changes.
- **Synchrony:** simultaneous changes group even if different in direction; existence and mechanism contested (possible artifacts).
- **Good continuation:** strong for contour integration ("association field"); supported by natural-image statistics.
- **Closure:** as a grouping cue, only a small advantage once good continuation is controlled (possibly probability summation); its main role is turning contour into 2-D shape. Can dominate continuity in some displays.
- **Symmetry & parallelism:** grouping/simplicity cues; symmetry easily overruled by good continuation and convexity; global symmetry enhances detection.
- **Convexity:** grouping cue for contour fragments.
- **Common region:** elements within a bounded region group (faster RDT).
- **Element connectedness:** connected elements group (faster RDT; Balint's patient could see two circles when connected by a line).
- **Uniform connectedness:** proposed basis for entry-level units; not accepted as sole determinant.
- Grouping occurs both pre- and post-constancy (final percept uses perceived 3-D distance and lightness, not retinal). Infants 3–4 months group by good continuation, proximity, connectedness, common region; form similarity only at 6–7 months; 3-month-olds insensitive to closure.

**Key findings — figure–ground factors**
- **Convexity:** convex regions seen as figure ~90% (8 regions, long exposure); only 57% with 2 regions → 89% with 8 at 100 ms (convexity context effect; requires homogeneous concave regions).
- **Symmetry:** weak against convexity; ~3/4 of trials in 2-region brief displays.
- **Small area, surroundedness (enclosure):** classic factors, often confounded in early studies.
- **Lower region:** region below a border seen as figure/closer (retinal frame dominant); ecologically valid for near-horizontal edges.
- **Top-bottom polarity:** wider-at-bottom regions more often figure.
- **Extremal edges/gradient cuts:** side with shading/texture gradient seen as nearer — even against other cues.
- **Edge-region grouping:** any grouping factor linking edge and region (common fate, blur, color, orientation, proximity, flicker synchrony) affects figure assignment.
- **Articulating motion** (concave hinge vertices) overrides convexity/symmetry; **advancing region** overrides small area.
- **Contour entropy:** disordered terminations make a region read as ground/hole.
- **Past experience/familiarity** influences figure assignment (upright familiar shapes); **attention and perceptual set** bias figure assignment; but figure–ground can also occur preattentively.
- Isolated cues are weak; disparate weak cues combine synergistically in natural images.

**Design rules derivable**
- Use spacing as the primary grouping signal; make within-group gaps clearly smaller than between-group gaps (competing groupings fail once the distance ratio exceeds ~1.5). [strong]
- Combine proximity with similarity (color/shape) to reinforce intended groups; their effects add. [moderate–strong]
- Use enclosing regions (cards, boxes, backgrounds) or connecting lines to bind items that cannot be placed close together. [moderate]
- Use common motion/simultaneous change to show items belong together (e.g., co-highlight on hover). [moderate]
- Make intended figures (dialogs, cards) convex, enclosed, smaller than and placed on homogeneous surroundings; use shading gradients on the near side. [moderate]
- Don't rely on symmetry or closure alone to define groups or figures. [moderate]
- MISUSE: treating "Gestalt laws" as fixed, equally strong, innate rules — strengths differ greatly, interact, and are modulated by experience and attention; closure in particular is weak as a grouping cue.

**Boundary conditions & caveats.** Most quantification uses dot lattices, Gabor fields, and simple bipartite displays; UI layouts are richer (cue combination is synergistic and not fully modeled); many factors measured by phenomenal report.


---

## Cross-paper patterns in this group
- **Logarithmic vs linear costs:** Aimed pointing time grows with log2(distance/width) (Fitts, MacKenzie), but constrained-path steering grows *linearly* with length/width (Accot-Zhai). Size and tolerance are the cheapest levers in both; path width matters most in menus and drag tracks.
- **Time-scale hierarchy converges across sources:** ~0.1 s (perceptual fusion; control feedback; animation frame — Card 1991, Miller 1968), ~1 s (immediate response, page turn, transition animation), ~2 s (conversational continuity; Miller 1968), ~10 s (unit task; graphic completion), ~15 s (end of conversational interaction — free the user). These are largely expert estimates and derivations, not direct experiments.
- **Closure governs tolerance for delay:** Miller 1968 (delays after closure), KLM (unit tasks; M operators at chunk boundaries), and Card 1991 (unit task ~10 s) all locate acceptable pauses at task-unit boundaries.
- **Perception of waiting is malleable:** progress indicators are preferred (Myers) and visual design can shorten perceived duration ~11% (Harrison); neither changes actual latency, and neither tested very long waits.
- **Capacity is in chunks, not items or bits:** Miller 1956 introduced chunks and recoding; Cowan 2001 tightens the pure limit to ~4 chunks (objects, not features). Both support chunking/grouping, and neither justifies item-count limits on visible menus.
- **Attention is the bottleneck for perception and memory:** Rensink (change needs focused attention; ~4–5 items monitored), Cowan (focus of attention holds ~4), Wagemans (attention biases figure–ground). Design must cue what matters rather than assume visibility equals awareness.
- **Grouping is how chunks are formed visually:** proximity, similarity, common region, and connectedness (Wagemans) are the perceptual means of producing the chunks Miller and Cowan describe.
- **Models are bounded by their populations:** KLM and Fitts-based predictions assume error-free experts and rapid aimed movement; Miller 1968's thresholds assume skilled users. Novices, errors, and learning need other evidence.
- **Methodology matters for comparisons:** Error-rate normalization (MacKenzie), RMS error bounds (KLM ±21%), and individual differences (Cowan 2–6 chunks) all warn against over-interpreting small differences or population means.
- **Folklore misuses cluster around single numbers:** "7±2 menu items", "4-item screens", "the universal 2-second rule", "0.1/1/10 s attention limits". The source papers themselves either disclaim these readings or give them narrower meanings.
