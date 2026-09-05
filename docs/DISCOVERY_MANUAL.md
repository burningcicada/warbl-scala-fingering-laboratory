![WARBL Scala Fingering Laboratory](assets/WARBL_SFL_DOCUMENTATION_MASTHEAD.png)

# WARBL Scala Fingering Laboratory — Discovery Manual

**Version:** v1.1  


> **v1.1 update:** sustained-legato degree ownership now uses the G3.2 Finger Commitment Envelope with a conservative internal-reference 24→32 ms Web Audio-clock arrival; Listening Space range is 0–100%. Historical v1.0 sections below are retained where they document the prior release and its evidence.
**Audience:** musicians, composers, educators, and curious microtonal performers who want to explore a tuning before entering the Laboratory's deepest controller, mapping, and diagnostic layers.

## Discovery is a musical path, not a simplified engine

The opening gateway offers **Discover** and **Deep Laboratory**. They are two views of the same project. Discover does not use a different tuning engine or a reduced musical law; it hides advanced authoring and diagnostics so the first questions remain musical:

1. What is this scale?
2. What does it sound like?
3. How might it fit the WARBL?
4. What does a playable subset preserve or omit?
5. How does it feel under the fingers?

The Lab's recurring principle is that **source tuning identity and performance organization are different layers**. A playable field, fingering proposal, notation view, or training exercise can reorganize access without claiming that the underlying Scala scale has changed.

## Why not just learn one WARBL fingering and use it for every Scala file?

**Yes — you can.**

You can learn one familiar WARBL fingering system and keep it for every Scala file. The WARBL can continue producing the same MIDI notes from the same fingerings while a Scala-aware instrument or retuning system determines the resulting pitches.

For many players, this may be the best approach.

### So why have the Laboratory?

Because a familiar fingering is only one possible physical arrangement of a scale.

Some scales have unusual numbers of notes, very uneven intervals, or important pitches that may fall on awkward fingerings. In those cases, another mapping may be easier to learn, more comfortable to play, or more useful musically.

The Laboratory lets you compare three approaches:

- **Keep the familiar mapping** — maximum muscle memory.
- **Use a scale-specific mapping** — arrange the fingerings around that particular scale.
- **Use a hybrid mapping** — preserve most familiar fingerings and change only the ones that benefit from a different placement.

The Scala file itself does not have to change. The Laboratory changes only the relationship between **physical fingering and scale degree**.

**The value of the Laboratory is not that every scale needs a new fingering. It is that the musician can test whether the familiar fingering is still the best way to play that scale.**

## 1. Import: preserve the authored Scala source

Use **Import** to open a `.scl` file or readable Scala text. The source expression remains immutable in the project model. The Lab calculates pitch structure from that source and keeps derived mappings separately identified.

The active scale identity includes its filename, description, fingerprint, degree count, period, and source expression. This makes it possible to distinguish:

- the original Scala source;
- the current performance mapping;
- the active playable field;
- the MIDI realization;
- the physical WARBL state.

That separation is essential when tunings contain close pitches, non-octave periods, ratios, or unusual degree counts.

## 2. Scale Discovery: build a local listening library

The **Scale Discovery** area can work with several local sources:

- `scalesdir.txt` catalogue data;
- the Huygens–Fokker `scales.zip` archive;
- selected `.scl` files;
- an extracted archive folder.

The archive is indexed locally in the browser; the Lab states explicitly that nothing is uploaded. When browser storage permits, the index can be remembered for the same stable page origin.

Discovery keeps evidence layers separate. Source facts, calculated pitch structure, source-tagged context, tentative text inference, and WARBL guidance are not collapsed into one certainty claim. Filename/keyword inference is not promoted into historical fact.

### Useful discovery lenses

The interface can help browse ideas such as:

- small playable fields;
- ratio-authored scales;
- non-octave systems;
- regular spacing;
- density and period classes;
- collection/source tags.

These are search and exploration aids, not value judgments about the tuning.

## 3. Build your own scale

The Discovery area links to **Scale Workshop** for creating, hearing, modifying, and converting tunings. Export `.scl`—and `.kbm` when needed—then import the result into the Laboratory.

The **Learn & Create** section also points outward to resources for Scala, Erv Wilson, Helmholtz–Ellis, Sagittal, Ben Johnston notation, and official WARBL documentation. These sites are study resources; the Lab does not copy their content or claim that every external notation system is currently rendered automatically.

The v1.1 notation choices are **Aperture** and **Conventional note + cents**.

## 4. Choose the center: establish a performance reference

Under **Choose the center**, set:

- **Performance center**;
- **Center MIDI note**;
- **A4 reference (Hz)**;
- **Fingering starting point**;
- **Mapping priority**;
- **Bend range**;
- **Intended destination**;
- handling of **Unused WARBL states**.

The default recommendation, **Neutral Sequential Opening**, treats the eight sequential tone-hole states as an ergonomic spine rather than an eight-note limit.

Mapping priorities include familiar fingerings, easy movement, small pitch bends, preservation of edits, and learnable patterns. If two strategies produce the same result, the Lab is designed to say so rather than inventing a difference.

## 5. Hear the scale before deciding how to play it

### Scale Listening

**Practice & Listening** contains the **Scale Listening** exact-frequency suite. Internal playback requires no VST, MTS, MIDI rounding, or receiver pitch-bend setup.

You can listen to:

- **Full Source Scale**;
- **Active Playable Field**;
- **Working / Lineage Fingering Path**.

You can choose ascending, descending, or up-then-down motion; connected, breath-like, or separated articulation; note duration and gap; and whether to sound the period closure.

### Compare playable fields

The Lab can play Field A and Field B directly so a field choice can be evaluated by ear rather than only by coverage percentages.

### Exact interval listening

Choose two degrees and hear them sequentially or together. This is useful when the mathematical relationship is known but its sound is not yet internalized.

### Hear · Find · Sustain

The practice exercise can choose a random or selected degree, hide or reveal notation/fingering at different stages, and require a sustained target. This turns the tuning into an ear-and-gesture study rather than a static table.

## 6. Pitch geometry: see relationships without replacing pitch identity

The **Pitch geometry** view visualizes the active tuning while keeping the exact source identity available. The Lab is intended to let ratios, cents, pitch locations, fingerings, and playable fields illuminate one another.

The visual geometry is explanatory. It does not authorize the software to merge two close source degrees or replace the Scala expression with a prettier diagram.

## 7. Why this mapping?

The Laboratory exposes mapping rationale instead of treating a generated fingering chart as magic. **Why this mapping?** and **Compiler validation** show why a proposal was selected and what its limitations are.

A mapping can be strong in one dimension and weaker in another. The Lab therefore distinguishes musical coverage, physical coverage, expressive headroom, and target/destination limitations.

## 8. Recommended Playable Field

A larger tuning does not have to be forced into one binary reading of the instrument.

**Recommended Playable Field** searches for a coherent single-WARBL view while preserving the complete source scale. The panel exposes:

- the field name;
- included degree count;
- result status;
- musical coverage;
- physical coverage;
- expressive coverage;
- the decision for each source degree.

You may mark a degree **required**, **exclude** it, or **include it anyway**. Recommendations recalculate deterministically.

The important conceptual distinction is:

**Source scale ≠ active playable field.**

A field is a performance lens. The source remains canonical and can be exported independently.

## 9. Notation Preview

**Notation Preview** links played notes, ratios, aperture degrees, and fingerings.

Scopes include:

- **Complete Source Scale**;
- **Active Playable Field**;
- **Live Focus**.

The native **Aperture** lens is intended to remain approachable and controller-aware. **Conventional note + cents** adds a familiar staff anchor while retaining the exact cent reference.

Pitch identity displays can emphasize ratio + cents, source ratio/expression, or cents. Fingering layers can be adaptive, compact, fixed, expanded, or hidden.

The period closure remains visible as source structure without being misrepresented as an extra independent fingering.

## 10. Pattern & Gravity Tutor

The **Pattern & Gravity Tutor** generates paths from the active Scala tuning, playable field, operator layers, and current fingerings.

Patterns include:

- ascending/descending field;
- up then down;
- scale skips;
- neighbor motion;
- fingering trills;
- harmonic gravity / return to center;
- Scale Period Practice;
- departure and return;
- difficult transitions.

Practice modes include Listen, Watch fingerings, Play Along, and Wait for Me.

For octave scales, Scale Period Practice uses 2/1; for non-octave scales it uses the declared Scala period. The native exercise record preserves degree, fingering, field, and tuning identity; MIDI export is secondary.

## 11. Expression is not the same as pitch identity

During performance, the Lab keeps discrete and continuous roles separate.

A raw fingering can identify the destination degree while optical finger depth and other expressive signals shape the path. The accepted geometric-continuity law avoids a fixed-cent threshold that would abruptly turn small physical shading into a new discrete pitch.

When the performer repeatedly alternates the same physical edge and geometric debt repeatedly remains unfinished, the v1.0 rapid-alternation layer can recognize the recurrent gesture and move between exact centers. This is a gesture-topology rule, not simply “anything faster than N milliseconds.”

## 12. Discovering controller behavior without overwriting it

The WARBL can transmit more than note numbers. The Lab records and displays raw MIDI, pitch bend, pressure, hole state, and selected device/configuration information without pretending every signal has one universal musical meaning.

This becomes especially important in Deep Laboratory, where controller profiles and structural controls are visible.

For example, advanced yaw tuning navigation is **non-exclusive**. If a performer's profile already uses yaw for timbre or another expressive destination, the navigation observer does not consume or suppress that signal.

## 13. Export what you learned

Use **Export and install** to preserve the session.

A **Project Export Snapshot ZIP** can carry the active Scala, machine-readable project/profile information, mapping CSV, 256-state table, and external synth guidance. You can also export a human-readable PDF report.

For external instruments, download the current `.scl` and matching `.kbm`, then match the receiving synth's bend range and MPE configuration. A mapping file cannot automatically reconfigure a receiver.

## Three suggested discovery journeys

### Journey A — A small unfamiliar scale

1. Import it.
2. Listen to the full source.
3. Generate the Neutral Sequential Opening proposal.
4. View Pitch geometry and Notation Preview.
5. Connect WARBL2 and play through the internal Reference Instrument.

### Journey B — A large tuning

1. Import the full source.
2. Listen to the complete scale.
3. Open Recommended Playable Field.
4. Compare candidate fields by ear.
5. Apply one field and practice its path.
6. Return to the full source at any time to verify what the field did and did not include.

### Journey C — A non-octave system

1. Verify the declared Scala period.
2. Use Scale Period Practice rather than assuming 2/1.
3. Inspect register architecture and field operators in Deep Laboratory before assigning any period-changing physical control.

## Release evidence and limits

The v1.0 promotion gate preserved the accepted musical core while changing release identity, favicon, and documentation surfaces. The regression matrix passes 535 synthetic Scala × WARBL-profile cases.

The recorded multi-tuning WARBL2 trace contains 282 geometric arrivals, all reaching physical = mapped = sounding degree with 0¢ applied bend at arrival, plus 16 exact-center rapid-alternation commits. No critical Flight Recorder events were dropped. The trace also recorded browser/main-thread stalls during idle/non-sounding moments; that performance observation remains documented rather than being hidden.

Advanced yaw/button tuning navigation is intentionally **opt-in** and remains separately scoped for physical profile acceptance. External synth/DAW compatibility remains destination-specific.

## v1.1 performance-witness reading

When Physical/ mapped and Sounding disagree briefly, read that disagreement as a transition witness rather than as three competing pitch authorities. Sounding is the primary musical identity; Physical and Mapped describe the controller/topology state that may be leading toward the next commitment. Phrase Shape shows continuous live pitch on the imported Scala cent geometry.
