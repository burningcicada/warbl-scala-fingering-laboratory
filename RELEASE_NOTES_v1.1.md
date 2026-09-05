# WARBL Scala Fingering Laboratory v1.1 — Release Notes

**Release version:** v1.1.0  
**Date:** 2026-09-05

## Sustained-legato pitch identity

v1.1 repairs the v1.0 live-sensor edge case in which an uninterrupted-breath fingering change could remain associated with the previous sounding degree while continuity waited for unrelated additional bend travel.

The G3.2 Finger Commitment Envelope preserves these laws:

- raw fingering topology selects the Scala degree;
- Pitch Bend never selects the degree;
- weak/incipient movement may shade an established center rather than snapping immediately;
- coherent witness evidence may accelerate a real transition;
- conservative internal-reference arrival is pre-scheduled on the Web Audio clock across 24→32 ms;
- the bounded residual never becomes a second persistent pitch carrier.

## Performance-witness alignment

The four main pitch views now distinguish **Physical**, **Mapped**, and **Sounding** degree identity. A physical/mapped candidate may appear before G3.2 transfers musical ownership; the primary musical highlight remains on the degree that is actually sounding. Phrase Shape uses the same cent geometry as the imported Scala file and plots `sounding center + applied expressive deviation`.

This repair was prompted by a physical WARBL2 Flight Recorder trace in which the performer could hear tonic while a candidate second degree was already physically observed. The trace correctly retained `soundingDegreeKey = tonic`; the defect was visual ownership, not pitch authority. The release keeps the musical/runtime G3.2 path unchanged and repairs only the observational presentation layer.

## Listening Space

- Space amount spans **0–100%**.
- Dry remains available.
- Existing Room/Hall/Pipe and embedded XenQuill IR listening paths are preserved.
- Listening Space never becomes tuning or fingering authority.

## WARBL2 reference preset

The repository now includes the optional controller configuration artifact used as the principal late-development WARBL2 reference preset at `profiles/WARBL2/WARBL_SFL_reference_preset.warbl`, with provenance and safety notes in the adjacent README.

## Evidence boundary

Physical traces establish what was observed with the internal WARBL2/reference-instrument path. External MIDI/MPE receiver behavior remains destination-specific. The supplied WARBL preset is configuration evidence, not a performance trace.
