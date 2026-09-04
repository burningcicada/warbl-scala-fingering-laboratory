![WARBL Scala Fingering Laboratory](assets/WARBL_SFL_DOCUMENTATION_MASTHEAD.png)

# WARBL Scala Fingering Laboratory — Deep Lab Manual

**Version:** v1.1  


> **v1.1 update:** sustained-legato degree ownership now uses the G3.2 Finger Commitment Envelope with a conservative internal-reference 24→32 ms Web Audio-clock arrival; Listening Space range is 0–100%. Historical v1.0 sections below are retained where they document the prior release and its evidence.
**Companion build:** `WARBL_Scala_Fingering_Lab_v1_0_DEV.html` for developer-repository work  
**Audience:** advanced performers, instrument builders, tuning researchers, developers, testers, and anyone who needs to understand why the Laboratory behaves as it does.

## 1. Deep Laboratory: what changes and what does not

Switching from **Discover** to **Deep Laboratory** reveals the complete authoring, routing, validation, controller, notation, training, export, and diagnostic surface. It does **not** create a second project or a different tuning engine.

The core design keeps several authorities distinct:

1. **Scala source identity** — authored degree expressions, period, and source identity.
2. **Mapping interpretation** — how source degrees are associated with WARBL physical states.
3. **Playable-field interpretation** — a selected performance subset/lens of the source.
4. **Raw controller evidence** — MIDI bytes, hole states, bend, pressure, IMU/control messages.
5. **Musical interpretation** — what the Lab decides those observations mean for sounding degree, expression, navigation, or pedagogy.
6. **Destination realization** — internal exact-frequency reference audio or an external MPE/retuned receiver.

A bug in one layer should not be repaired by silently giving another layer more authority.

## 2. Controller evidence discipline

The Laboratory follows an evidence-first expressive-controller discipline:

- preserve raw MIDI/MPE/event order and timestamps;
- decode Note, Bend, Pressure, CC, and device/configuration messages neutrally before assigning musical meaning;
- distinguish hardware behavior from software interpretation;
- record provenance such as MIDI-observed, device-reported, manufacturer-documented, user-declared, inferred, or unknown;
- keep the Flight Recorder portable as diagnostic evidence rather than turning the trace itself into a hard-coded profile.

For WARBL2 this distinction is essential. Pitch Bend can reflect finger slide/vibrato and may also interact with pressure or IMU mappings depending on the user's Configuration Tool setup. The Lab therefore does not assume that a given bend component came from one physical source unless the evidence supports that decomposition.

## 3. MIDI connection and device state

### Play and route

The **Play and route** panel separates:

- **MIDI input**;
- **WARBL configuration output**;
- **Retuned MIDI destination**;
- **Retuning output mode**;
- **Playback route**.

The internal reference path and external output path are different destinations. A correct internal pitch result does not prove that an external receiver has the correct bend range, MPE zone, routing, or preset.

### WARBL / MIDI diagnostics

The diagnostic panel checks:

1. browser context;
2. Web MIDI API;
3. browser permission;
4. MIDI port scan;
5. selected WARBL input;
6. WARBL configuration output;
7. incoming MIDI traffic;
8. WARBL state response.

Use **Copy report** for a compact connection report and **Flight Recorder** for event-level evidence.

## 4. Source Scala, center, and mapping state

### Import

The original `.scl` expression is preserved separately from the generated MIDI/fingering realization. Fingerprints and project signatures are used to detect identity rather than relying only on filenames.

### Choose the center

The center defines the performance reference around which the Scala source is realized. The Lab exposes center degree, center MIDI note, A4 reference, mapping priority, bend range, intended destination, and policy for unused WARBL states.

### Mapping Studio

**Mapping Studio** is the manual authoring surface. A degree's fingering or MIDI anchor can be changed and locked. Manual-first mode treats locks as hard constraints. Generated strategies still publish their physical, bend, and access consequences.

The Lab does not hide close source degrees merely because they are inconvenient. If two Scala degrees are distinct, the mapping layer must not merge them by rounding.

### Familiar, scale-specific, and hybrid mappings

The Laboratory does **not** require a new fingering system for every Scala file. A performer may keep one familiar WARBL fingering system across many tunings and let the tuning destination determine the resulting pitches. For some musicians, that continuity of muscle memory is the most useful mapping strategy.

The mapping architecture therefore supports three musical intentions:

1. **Familiar mapping** — retain a known physical fingering vocabulary as consistently as possible.
2. **Scale-specific mapping** — optimize the physical arrangement around the intervals, degree count, and important tones of the current scale.
3. **Hybrid mapping** — retain most familiar fingerings while changing selected degrees where another placement offers a meaningful ergonomic or musical advantage.

These are interpretations of the same Scala source. Choosing among them changes the relationship between physical state and scale degree; it does not require rewriting the `.scl` file. The comparison itself is part of the Laboratory: it lets the performer determine whether familiarity, scale-specific ergonomics, or a hybrid is best for the music at hand.

## 5. Fingering grammar and 256-state architecture

The eight simple sequential tone-hole states are an **ergonomic spine**, not an eight-note ceiling. The Deep Lab exposes a wider 256-state mapping architecture and keeps register/modifier behavior separate from scale identity.

**Fingering Grammar & Register Architecture** offers concepts including:

- lineage-native behavior;
- Scala period shift;
- adjacent scale-degree window;
- generator shift;
- fixed ratio;
- custom operator;
- register amount;
- modifier role;
- comma / micro-adjustment;
- alternate fingering family;
- expression-reserved states;
- silence / hold control.

The software can record and explain these architectures, but physical thumb, half-hole, bell, button, and firmware behavior remain device-configuration facts. They are not inferred from a Scala file.

## 6. Playable Fields & Pitch Operators

**Playable Fields & Pitch Operators** applies exact software transformations to the active tuning. Operator types include:

- Scala period shift;
- adjacent degree window;
- generator shift in cents;
- fixed ratio;
- comma / micro-adjustment;
- custom cents operator.

Potential intended controls include bell, overblow, thumb/register, Button 1, Button 2, IMU elevation, or Unassigned.

The verification boundary is explicit: defining a software operator does not prove that a physical control is configured or stable enough to authorize that operator. A control must be configured, observed, and physically verified before it is treated as performance authority.

## 7. Bell Field Operator

The **Bell Field Operator** is deliberately experimental. It lets the performer simulate/observe covered and lifted states, choose a principal bell role, calibrate against actual knee/clothing conditions, and repeat transitions before authorizing structural use.

The recommended discipline is one primary structural role per control. Do not let bell, thumb, button, or another discrete control silently perform several incompatible jobs at once.

## 8. Control Roles & Performance Profiles

The profile layer exists to keep **scale identity, structural navigation, expression, ornament, and safety** visibly separate.

Starting profiles include **Natural Wind**, **Maximum Expression**, **Gestural Field**, **Experimental Operator**, and **Custom Performance Profile**.

The default rule shown in the UI is important:

> Discrete, deliberate controls may change field or pitch identity. Continuous gestures should normally preserve the note and shape dynamics, timbre, inflection, vibrato, or space.

### Hold and capture a fingering

Use **Capture current WARBL fingering** to capture an observed eight-sensor state and assign it to a selected degree. This is an explicit authoring operation; it does not require the performer to type binary data.

## 9. RC5.10 Geometric Finger Continuity — v1.0 pitch law

The protected geometric law is the center of the current physical feel.

When raw WARBL topology identifies a new destination degree:

1. the current audible pitch is preserved exactly at the instant of retargeting;
2. the logarithmic pitch distance to the new Scala center becomes **continuity debt**;
3. subsequent physical bend travel pays that debt;
4. the output is constrained between start and target rather than overshooting;
5. when the debt reaches zero, the sounding degree becomes the exact target and applied bend returns to 0¢;
6. if the finger retargets before arrival, the next journey begins from the current audible pitch with no discontinuity.

There is **no fixed-cent commitment threshold**.

The local expression radius is tuning-aware and prefers physically reachable one-hole neighbors rather than blindly using the nearest degree anywhere in a dense scale.

## 10. RC5.11 recurrent-edge rapid alternation / trill assistance

A single fast transition is not automatically a trill. The Lab looks for recurrence on the same physical edge together with repeated unfinished geometric debt.

Conceptually:

**A → B → A → B**, same physical edge, repeated reversals, prior geometric journeys repeatedly unfinished.

Once recognized, the rapid-alternation layer can place the two known states on their exact mapped centers instead of forcing every reversal to complete the full slow geometric traversal first.

This is why the classifier is not a fixed “faster than N ms” rule. The same physical speed can be easy in a dense tuning and difficult in a wide-step tuning. Gesture recurrence and unfinished distance matter together.

The physical acceptance trace includes exact-center rapid alternation events with 0¢ applied bend.

## 11. Breath, Harmonic Reed, and reference audio

The default performer reference is **Harmonic Reed — Performer Reference**. The v1.0 line preserves the P0.3 whisper-emergence shaping so tiny breath can remain audible without converting pressure into pitch authority.

The internal **Reference Instrument level** affects only the internal reference audio. It does not change outgoing MIDI velocity, breath, or MPE expression.

Other reference choices remain available for measurement, A/B comparison, or historical comparison, including Pure Sine, Legacy Reference Voice, and Reference Pipe candidates.

### Listening Spaces

The reference path also exposes Dry and listening-space choices, including the embedded XenQuill-derived spaces. These alter the listening reference; they do not change Scala identity or fingering authority.

## 12. Audio Artifact Check

The **Audio Artifact Check** is a short browser-side engineering screen for clipping and unusually large adjacent-sample jumps. It is a diagnostic aid only. It does not replace a physical recording of the WARBL, audio interface, receiver, or performance environment.

## 13. Phrase Shape / Aperture

**Phrase Shape / Aperture** is an evidence-oriented gesture/narrative display. It can show reversible phrase information without claiming that every visual layer is a directly measured hardware channel.

Use it as a witness and teaching surface, not as a substitute for the raw Flight Recorder when diagnosing controller behavior.

## 14. Alternate Fingering Explorer

The **Alternate Fingering Explorer** searches for physically different states that retain the same exact Scala target. Suggestions are classified and scored by movement cost while preserving target identity.

Selecting an alternate is an explicit mapping decision. It should not change the source scale.

## 15. Advanced Performance Tuning Navigation

This is an **advanced, opt-in, boundary-safe** layer. It is OFF in normal Lab behavior.

### Bundled tuning bank

The v1.0 executable contains six source-preserved tuning files for this performance-navigation experiment:

- `slendro_s1.scl`
- `wilson_31(5).scl`
- `tri19-2(3).scl`
- `hexany27.scl`
- `zest24-supergoya17plus3_Db.scl`
- `XQ_BeeSwarm_Harmonic_Nectar_24.scl`

The gate checks that the embedded Scala text matches the supplied source files byte-for-byte.

### Yaw navigation

The performer must explicitly enable navigation and **Learn yaw MIDI CC**. The Lab does not assume a fixed WARBL yaw CC.

After learning, use **Set current yaw center** and set **Yaw turn amount**. One excursion triggers one advance; the control must return to the center band and re-arm before another advance.

#### Constitutional rule: navigation may observe yaw; it may not own yaw

The yaw branch is a non-exclusive sidecar observer. Learning or triggering navigation returns the MIDI event to the rest of the performance/profile path rather than consuming it.

The navigation observer **does not consume** the yaw event. Therefore, if the active WARBL profile already uses yaw for timbre, space, expression, or another destination, that role continues unchanged.

This does **not** mean the two meanings can never conflict musically. A normal expressive yaw motion could still cross the structural navigation excursion. The performer should therefore place the navigation excursion outside their ordinary expressive range or leave navigation disabled.

### Button navigation

The Lab can learn a safe discrete message for Button 1 or Button 2 only when the selected Lab role is free. It does not rewrite WARBL firmware. Button 3 remains guarded because of critical/power behavior.

### Safe-boundary tuning change

If a navigation request occurs while a note is sounding, the new tuning is queued. It commits at the final release boundary rather than retuning the currently sounding note underneath the performer.

### Acceptance boundary

The profile-safe yaw ownership rule is covered by executable/runtime testing. The structural yaw/button navigation layer remains opt-in and should be physically verified with the actual performer's controller profile before stage use.

## 16. Performance Scenes

**Performance Scenes** captures scale, fingering, register, MPE, and routing intention in a portable scene capsule. Manual Previous/Next buttons work inside the Lab; intended external command source/number are stored as metadata.

The v1.0 Laboratory does **not** claim atomic switching of WARBL chart + Scala realization + VST3 preset + DAW route. Incoming Program Change/CC/footswitch-to-scene binding belongs to a separate Performance Scene Bridge or external workflow.

## 17. Extended Scale Mapping

**Extended Scale Mapping** supports multi-system exploration and present-day overdubbing workflows.

A practical current workflow is:

1. export each system;
2. place charts in separate WARBL custom slots where supported;
3. use separate DAW tracks/tuning-aware receiver instances;
4. select the matching WARBL chart, retuned route, and armed track;
5. change systems only at tested boundaries or record separate passes.

Atomic continuous-performance switching is not claimed.

## 18. Notation Preview

The two public notation lenses are:

- **Aperture — approachable default**;
- **Conventional note + cents**.

Scopes can show complete source, active playable field, or live focus. Pitch identity can emphasize ratio + cents, source expression, or cents. Fingering layers can be adaptive or deliberately simplified.

Advanced automatic HEJI/Sagittal/Johnston rendering remains study/future work rather than a v1.0 claim.

## 19. Pattern & Gravity Tutor and Practice & Listening

The tutor and listening suite both operate from exact tuning/mapping data rather than twelve-tone approximations.

The tutor can generate field motion, skips, neighbor motion, fingering trills, harmonic-gravity returns, period practice, and difficult transitions.

The listening suite can play full source, active field, or working fingering path; compare two fields; hear exact intervals; and run Hear · Find · Sustain exercises.

For non-octave scales, Scale Period Practice uses the declared Scala period rather than assuming 2/1.

## 20. External MPE / receiver path

The **MPE Output Monitor** shows the exact performance data sent to the receiver: destination, bend range, note balance, expression, source and outgoing pitch, member channels, and lifecycle state.

For Full MPE lower-zone output, the Lab uses a manager channel and member channels so overlapping WARBL legato notes can retain separate pitch lifetimes.

Before performance:

- select the destination;
- match bend range;
- match MPE zone;
- import `.scl`/`.kbm` where supported;
- test held and overlapping legato notes.

The public v1.0 release does not claim universal receiver compatibility. External behavior remains destination-specific.

## 21. Performance Event Trace and Flight Recorder

**Performance Event Trace** is a rolling view for recent input and output-lifecycle events. **Flight Recorder** is the durable diagnostic capture.

Important semantic events in the current physical layer include:

- `geometric-finger-target`
- `geometric-finger-arrival`
- `rapid-alternation-enter`
- `rapid-alternation-center`
- `rapid-alternation-exit`
- note-on/off and live-degree correction events
- scale replacement lifecycle
- audio sentinel / realtime lag witnesses

The recorder may drop ordinary rolling-retention events in a long session, but critical evidence is maintained separately. Always inspect `criticalDropped` before treating a trace as complete critical evidence.

## 22. Direct WARBL2 installation

Under **Export and install**, Direct WARBL2 installation transmits the validated 256-value chart only after explicit confirmation.

It does not silently change:

- breath;
- legato;
- register;
- pressure;
- buttons;
- channel;
- bend range.

Assignment to the active preset is optional. Complete 256-value readback from a pre-existing custom slot is not claimed. Exact Scala offsets still require a tuning-aware destination, MPE/pitch bend, MTS, or another retuning method.

## 23. Export model

The **Project Export Snapshot ZIP** is the most complete portable project artifact. It can contain:

- authoritative current `.scl`;
- matching `.kbm`/receiver guidance where applicable;
- profile/project JSON;
- mapping CSV;
- 256-state data;
- human-readable rationale and limitations.

Separate exports include Profile JSON, Mapping CSV, WARBL notes/256 values, and Print/Save PDF.

The export system preserves source tuning and derived realization as separate concepts.

## 24. Installed build

The **Installed build** area is the in-application provenance/acceptance summary. In public v1.0 it identifies the v1.0.0 executable, recovery lineage, cumulative realtime repairs, geometric/trill/profile-safe-yaw promotion history, and the current acceptance boundary. Use this section when comparing a user's report against an older RC or developer build.

## 25. Support and updates

Public support is routed through GitHub Issues. The Lab pre-fills version, active tuning, and browser/OS information. Attach Flight Recorder evidence whenever it can reproduce the issue.

The update checker reads `updates/latest.json` from the public repository. It does not silently install or replace the HTML.

## 26. v1.0 release evidence

The promotion gate checks the actual generated release/dev HTML, not only a model of the logic.

At promotion:

- JavaScript syntax and duplicate-ID checks pass;
- the accepted geometric, trill, and tuning-navigation functions are invariant across the RC5.11.2 source, v1.0 release, and v1.0-dev after normalizing version strings;
- the GitHub Issues path replaces the former email support path;
- the approved favicon bytes are embedded exactly;
- all six tuning-bank sources are embedded exactly;
- the 535-case Scala × WARBL-profile synthetic matrix passes;
- a runtime smoke test confirms yaw navigation triggers without consuming the yaw MIDI event.

### Physical multi-tuning evidence carried into v1.0

The accepted physical trace predates the final v1.0 label, but the gate proves that the promoted musical/runtime functions are unchanged.

That trace contains:

- **282 geometric arrivals**;
- **282/282** arrivals with physical degree = mapped degree = sounding degree and 0¢ applied bend at arrival;
- **16 rapid-alternation center commits**;
- **16/16** exact mapped centers with 0¢ applied bend;
- **19 Note Ons / 19 Note Offs** in the retained semantic lifecycle;
- **0 critical Flight Recorder drops**;
- **0 audio-sentinel anomalies**;
- five intentional manual scale replacements used to stress the musical logic across tuning changes.

The same trace recorded main-thread/UI stalls, including a multi-second outlier. Every retained lag/long-task event occurred while no note was sounding, so this remains a documented performance warning rather than a pitch-law failure.

## 27. v1.0-dev developer build

`WARBL_Scala_Fingering_Lab_v1_0_DEV.html` begins with the same promoted musical/runtime core as v1.0. It exists so subsequent developer changes can be made without silently modifying the public release artifact.

A future dev change should not be promoted simply because it “sounds better.” The standard engineering gate is:

**build code → run simulation → preserve failures → update audit/build ledger → repair → rerun → repeat until PASS → physical witness where required → manual-vs-build audit → package release.**

Controller-profile changes must additionally preserve the evidence distinction between raw hardware behavior and software interpretation.

## 28. Known boundaries to keep visible

v1.0 deliberately does not claim:

- universal external synth/DAW/MPE compatibility;
- atomic chart + tuning + VST + route switching during a continuous performance;
- automatic incoming Program Change/CC/footswitch scene advancement;
- complete 256-value readback from an arbitrary existing WARBL custom slot;
- automatic advanced notation rendering beyond the public Aperture and Conventional note + cents lenses;
- physical stage acceptance of the optional yaw/button tuning-navigation feature for every controller profile;
- that a continuous IMU/pressure/bend stream has one universal musical meaning.

Those boundaries are part of the Laboratory's reliability model, not omissions to hide.
