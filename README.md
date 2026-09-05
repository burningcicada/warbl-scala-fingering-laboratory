![WARBL Scala Fingering Laboratory](docs/assets/WARBL_SFL_DOCUMENTATION_MASTHEAD.png)

# WARBL Scala Fingering Laboratory v1.1

A browser-based laboratory for loading **Scala tunings**, designing and testing **WARBL / WARBL2 fingering maps**, auditioning exact microtonal pitch, exploring playable fields, and relating physical fingering to what is actually sounding.

**Public release:** v1.1.0  
**Status:** stable public release

## Launch

Live GitHub Pages:

https://burningcicada.github.io/warbl-scala-fingering-laboratory/

For WARBL hardware input, use a current Chromium-based desktop browser with Web MIDI support and allow MIDI permission when prompted. A local copy can be opened with either `index.html` or `WARBL_Scala_Fingering_Lab_v1_1.html`; these two files are byte-identical in the release.

## What changed in v1.1

### Sustained-legato / finger commitment

v1.1 repairs the v1.0 edge case in which an uninterrupted-breath fingering change could remain attached to the previous Scala degree while continuity waited for unrelated additional bend travel. The G3.2 Finger Commitment Envelope keeps raw WARBL topology as degree authority, keeps Pitch Bend as continuous expression, allows very small finger movement to shade an established center, and bounds conservative internal-reference arrival on the Web Audio clock across 24→32 ms.

### Visual truth alignment

Pitch Geometry, Mapping Studio, Notation Preview, and Phrase Shape now share an explicit performance-witness model:

- **Physical** — the fingering topology currently observed from WARBL.
- **Mapped** — the Scala-degree candidate implied by that topology.
- **Sounding** — the degree that currently owns the audible carrier.
- **Live pitch** — sounding Scala center plus applied expressive deviation.

During a real transition, Physical/ mapped may move before Sounding. The primary musical highlight therefore follows **Sounding** while the other states remain visible as secondary witnesses. These displays are observational only and do not feed back into the pitch engine.

### Listening Space

Listening Space is available from Dry through **100%** send. This expands the existing listening/reverb range without changing Scala or fingering authority.

## Included WARBL2 reference preset

The repository includes `profiles/WARBL2/WARBL_SFL_reference_preset.warbl`, the controller-side reference preset used for much of the late physical testing. It is optional and is never applied automatically. See `profiles/WARBL2/README.md` before importing it into a WARBL2.

## What the Laboratory includes

Scala `.scl` import; Scale Discovery; Recommended Playable Fields; several mapping priorities; Mapping Studio; alternate-fingering exploration; exact-frequency Harmonic Reed reference listening; live WARBL raw-sensor observation; G3.2 finger commitment; rapid-alternation assistance; Listening Space; external retuned MIDI/MPE routing; Notation Preview; Practice/Listening tools; scenes; export; and Flight Recorder diagnostics.

## Documentation

- [Quick Start](docs/QUICK_START.md)
- [Discovery Manual](docs/DISCOVERY_MANUAL.md)
- [Deep Lab Manual](docs/DEEP_LAB_MANUAL.md)
- [WARBL2 reference preset](profiles/WARBL2/README.md)

## Reporting a problem

Use GitHub Issues: https://github.com/burningcicada/warbl-scala-fingering-laboratory/issues/new

When possible, include the Lab version, active tuning, browser/OS, WARBL firmware/preset information, and a Flight Recorder JSON that reproduces the behavior.

## Release discipline

The named release HTML is a preserved stable artifact. Changes are promoted only after regression work and appropriate physical witnesses.

**One bug → one witness → permanent regression.**

## Boundaries

External synth/DAW/MPE compatibility remains destination-specific. The public release does not claim that every external receiver reproduces the internal reference timing or pitch behavior identically.
