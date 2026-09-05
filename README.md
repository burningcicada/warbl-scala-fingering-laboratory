![WARBL Scala Fingering Laboratory](docs/assets/WARBL_SFL_DOCUMENTATION_MASTHEAD.png)

# WARBL Scala Fingering Laboratory v1.1

A browser-based laboratory for loading **Scala tunings**, designing and testing **WARBL / WARBL2 fingering maps**, auditioning exact microtonal pitch, exploring playable fields, and exporting a documented performance mapping.

**Public release:** v1.1.0  
**Status:** stable public release

## Launch the Laboratory

### Live GitHub Pages

https://burningcicada.github.io/warbl-scala-fingering-laboratory/

The live Laboratory runs directly from GitHub Pages in a compatible browser. For WARBL hardware input, use a current Chromium-based desktop browser with Web MIDI support and allow MIDI permission when prompted.

Prefer a local copy? Download or clone this repository and open:

- `index.html` — GitHub Pages / simplest local launch;
- `WARBL_Scala_Fingering_Lab_v1_1.html` — explicitly named v1.1 release artifact.

`index.html` and the named v1.1 release HTML are generated from the same promoted release and should remain byte-identical.

## What changed in v1.1

### Sustained-legato / finger-commitment fix

v1.0 had a documented live-sensor edge case: during uninterrupted breath, a decisive fingering change could remain attached to the previous sounding Scala degree while the continuity system waited for additional bend travel.

v1.1 replaces that failure mode with the physically tested **G3.2 Finger Commitment Envelope**:

- raw WARBL fingering topology remains the authority for **which Scala degree** is being selected;
- Pitch Bend remains continuous expression and never chooses the degree;
- tiny or incipient finger movement can shade the established center rather than causing an immediate binary snap;
- a coherent decisive change may commit faster when the physical witness supports it;
- otherwise the internal reference voice has a conservative **24→32 ms** audible arrival scheduled on the Web Audio clock so browser callback stalls cannot indefinitely retain the previous carrier.

This is intended to preserve the compromise between **consistent pitch identity** and the expressive reality of **barely lifting a finger**.

### Listening Space restored to 100%

The prior UI artificially limited Space amount to 30%. v1.1 restores the full **0–100%** range while retaining Dry as an option. This expands the existing reverb/Space send; it does not change Scala authority or fingering interpretation.

## What v1.1 includes

- Scala `.scl` import and local Scale Discovery workflow.
- Recommended Playable Fields for larger tunings.
- Familiar, ergonomic, low-bend, manual-first, and pattern-coherence mapping priorities.
- Mapping Studio and alternate-fingering exploration.
- Internal exact-frequency Harmonic Reed reference listening.
- Live WARBL raw-sensor observation and Lab Fingering performance mode.
- G3.2 Finger Commitment Envelope with bounded arrival behavior.
- Rapid-alternation / trill assistance.
- Listening Space from Dry through 100% send, including embedded XenQuill IR choices.
- External retuned MIDI / MPE routing.
- Notation, practice, listening, scenes, export, and WARBL chart workflows.
- Flight Recorder diagnostics for reproducible physical testing.
- GitHub issue and manual update paths.

## Why this Laboratory exists

You do **not** need a new fingering system for every Scala file. A familiar WARBL fingering may remain the best musical choice.

The Laboratory lets the performer compare three practical approaches:

- **Familiar mapping** — preserve maximum muscle memory.
- **Scale-specific mapping** — arrange fingerings around the particular tuning.
- **Hybrid mapping** — keep familiar fingerings and change only the placements that benefit from another choice.

The Scala source remains unchanged. The Laboratory explores how physical fingering relates to the scale and how that relationship behaves in performance.

> **The value of the Laboratory is not that every scale needs a new fingering. It is that the musician can test whether the familiar fingering is still the best way to play that scale.**

## Documentation

- [Quick Start](docs/QUICK_START.md)
- [Discovery Manual](docs/DISCOVERY_MANUAL.md)
- [Deep Lab Manual](docs/DEEP_LAB_MANUAL.md)

## Reporting a problem

Use the public GitHub Issues page:
https://github.com/burningcicada/warbl-scala-fingering-laboratory/issues/new

When possible, include the Lab version, active tuning, browser/OS, WARBL firmware/preset information, and a Flight Recorder JSON that reproduces the behavior.

## Release discipline

The named release HTML is a preserved stable artifact. Future changes belong in the developer line and are promoted only after simulation/regression work and appropriate physical witnesses.

**One bug → one witness → permanent regression.**

## Boundaries

Advanced yaw/button tuning navigation remains opt-in and should be tested with the performer's active controller profile. External synth/DAW/MPE compatibility remains destination-specific. The v1.1 release does not claim that every external receiver reproduces the internal reference timing or pitch behavior identically.
