# WARBL Scala Fingering Laboratory v1.1 — Release Notes

**Release version:** v1.1.0  
**Date:** 2026-09-04

## Primary fix — sustained-legato pitch identity

v1.1 repairs the v1.0 live-sensor edge case in which an uninterrupted-breath fingering change could remain associated with the previous sounding degree while continuity waited for unrelated additional bend travel.

The promoted G3.2 Finger Commitment Envelope preserves these laws:

- raw fingering topology selects the Scala degree;
- Pitch Bend never selects the degree;
- weak/incipient movement may shade an established center rather than snapping immediately;
- coherent witness evidence may accelerate a real transition;
- conservative internal-reference arrival is pre-scheduled on the Web Audio clock across 24→32 ms so a busy JavaScript callback cannot indefinitely retain the old carrier;
- the bounded residual never becomes a second persistent pitch carrier.

## Listening Space

- Space amount range restored from the prior 30% UI ceiling to **0–100%**.
- Dry remains available.
- Existing Room/Hall/Pipe and embedded XenQuill IR topology is preserved.
- This is a range restoration, not a new tuning authority or fingering law.

## Physical evidence carried into promotion

The accepted v1.1 direction is based on physical WARBL2 Flight Recorder sessions plus performer audition. The most recent R100 session identified itself as the G3.2 audio-deadline/R100 branch and recorded **0 dropped** and **0 critical-dropped** events. The performer reported that the result was “much better” and then identified the present balance as a good compromise between consistent pitch and barely lifting a finger.

The physical evidence establishes the controller/software behavior observed in those sessions; it does not generalize external synth/DAW receiver behavior.

## Preserved behavior

- Exact Scala-source preservation and fingerprinted project identity.
- Harmonic Reed/P0.3 low-breath response.
- Rapid-alternation / trill assistance.
- Profile-safe opt-in yaw navigation.
- Flight Recorder evidence separation between physical input and software interpretation.
- External MIDI/MPE receiver behavior remains destination-specific.

## Not included in v1.1

The following remain outside this public promotion:

- CNEI / Seaboard peer-controller integration;
- polymorphic Piano / Lumatone / custom surface adapters;
- Aperture Witness redesign;
- a louder-than-current reference-instrument output ceiling.

Those branches remain separate so the accepted WARBL pitch/finger behavior is not disturbed.
