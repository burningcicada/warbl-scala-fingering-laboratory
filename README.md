![WARBL Scala Fingering Laboratory](docs/assets/WARBL_SFL_DOCUMENTATION_MASTHEAD.png)

# WARBL Scala Fingering Laboratory

A browser-based laboratory for loading **Scala tunings**, designing and testing **WARBL / WARBL2 fingering maps**, auditioning exact microtonal pitch, exploring playable fields, and exporting a documented performance mapping.

**Public release:** v1.0  
**Status:** stable public release with a documented v1.0 legato-continuity edge case under active developer repair.

## Launch the Laboratory

### [Launch WARBL Scala Fingering Laboratory v1.0](https://burningcicada.github.io/warbl-scala-fingering-laboratory/)

The live Laboratory runs directly from GitHub Pages in a compatible browser. For WARBL hardware input, use a current Chromium-based desktop browser with Web MIDI support and allow MIDI permission when prompted.

Prefer a local copy? Download or clone this repository and open:

- `index.html` — simplest local launch and the GitHub Pages entry file;
- `WARBL_Scala_Fingering_Lab_v1_0.html` — explicitly named frozen v1.0 release artifact.

For v1.0, `index.html` is intended to contain the same stable Laboratory application as the named release file. It is **not a separate edition**. Future development belongs in the developer repository/build; the Pages entry should be regenerated from a promoted stable release rather than independently edited.

## Why this Laboratory exists

You do **not** need a new fingering system for every Scala file. A familiar WARBL fingering may remain the best musical choice.

The Laboratory lets the performer compare three practical approaches:

- **Familiar mapping** — preserve maximum muscle memory.
- **Scale-specific mapping** — arrange fingerings around the particular tuning.
- **Hybrid mapping** — keep familiar fingerings and change only the placements that benefit from another choice.

The Scala source remains unchanged. The Laboratory explores how physical fingering relates to the scale and how that relationship behaves in performance.

> **The value of the Laboratory is not that every scale needs a new fingering. It is that the musician can test whether the familiar fingering is still the best way to play that scale.**

## What v1.0 includes

- Scala `.scl` import and local Scale Discovery workflow.
- Recommended Playable Fields for larger tunings.
- Familiar, ergonomic, low-bend, manual-first, and pattern-coherence mapping priorities.
- Mapping Studio and alternate-fingering exploration.
- Internal exact-frequency reference listening with Harmonic Reed.
- Live WARBL raw-sensor observation and Lab Fingering performance mode.
- Geometric finger continuity and rapid-alternation / trill assistance.
- External retuned MIDI / MPE routing.
- Notation, practice, listening, scenes, export, and WARBL chart workflows.
- Flight Recorder diagnostics for reproducible physical testing.
- GitHub issue and manual update paths.

## Known issue — v1.0 legato continuity

A current physical Flight Recorder witness confirms an edge case in **Lab fingering / live-sensor mode**. During uninterrupted breath, a decisive fingering change can sometimes remain associated with the previous sounding degree while geometric continuity waits for additional bend travel. Breath-separated attacks centered correctly in the same controlled test.

**Current workaround:** if a sustained-legato transition sounds displaced, briefly re-articulate or take a new breath to establish the new Scala center.

This issue is being repaired in the developer line. Public v1.0 remains frozen while the repair is tested against the existing geometric-continuity behavior so that subtle expressive finger movement is not lost.

## Documentation

- [Quick Start](docs/QUICK_START.md)
- [Discovery Manual](docs/DISCOVERY_MANUAL.md)
- [Deep Lab Manual](docs/DEEP_LAB_MANUAL.md)

## Reporting a problem

Use the public [GitHub Issues page](https://github.com/burningcicada/warbl-scala-fingering-laboratory/issues/new).

When possible, include:

- Lab version;
- active tuning / `.scl` file;
- browser and operating system;
- WARBL firmware/preset information if relevant;
- a Flight Recorder JSON that reproduces the behavior.

The Flight Recorder preserves the distinction between raw controller evidence and the Laboratory's musical interpretation, which makes physical regressions much easier to diagnose.

## Release discipline

The public v1.0 HTML remains a frozen release artifact. Development changes are made in the developer line, tested against simulation and physical witnesses, and promoted only after the release gate passes.

**One bug → one witness → permanent regression.**
