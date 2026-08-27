# WARBL Scala Fingering Laboratory

![WARBL Scala Fingering Laboratory](docs/images/warbl-scala-fingering-laboratory-banner.png)
A browser-based laboratory for loading **Scala tunings**, designing and testing **WARBL / WARBL2 fingering maps**, auditioning exact microtonal pitch, and preparing a validated **256-state custom chart** for installation on WARBL2.

> **Current public candidate:** `v1.0.0-rc.1`  
> **Status:** SOFTWARE VERIFIED RELEASE CANDIDATE — physical WARBL2 acceptance is still in progress.

The Laboratory is built around one central rule:

> **Controller behavior must never rewrite source-scale truth.**

A loaded `.scl` file remains the canonical tuning source. Fingering design, physical sensor observation, device MIDI, mapping, notation, reference synthesis, and exported controller charts are kept as distinct layers so they can be compared without silently changing the scale.

## What it does

- Loads Scala `.scl` files without rounding away close pitch distinctions.
- Builds and edits a 256-state WARBL fingering map.
- Auditions the selected tuning through an internal reference instrument.
- Uses live WARBL raw-sensor state as the normal Laboratory fingering authority.
- Keeps **Automatic verification** as a strict agreement-checking mode rather than forcing it into the normal playing path.
- Shows physical fingering and authorized/sounding pitch separately.
- Exports Scala, KBM, mapping, performance, scene, trace, and project artifacts.
- Compiles and installs a validated custom chart on a connected WARBL2 when prerequisites are satisfied.
- Includes a Flight Recorder for reproducible physical testing and regression diagnosis.

## Quick start

1. Download the current release candidate from [`releases/v1.0.0-rc.1`](releases/v1.0.0-rc.1/).
2. Open `WARBL_Scala_Fingering_Lab_v1_0_0_rc_1.html` in a compatible Chromium-based browser with Web MIDI support.
3. Click **Connect WARBL / MIDI**.
4. Load a Scala file.
5. Choose or edit a Laboratory fingering.
6. Play using **Lab Fingering** authority.
7. Use **Automatic verification** only when you want the Lab to compare device MIDI identity against concurrent Working-Fingering evidence.

Before installing any chart on hardware, review the generated 256-state map and the installation status shown by the Laboratory.

## Why `v1.0.0-rc.1` rather than `v1.0.0`?

This build passed the current software regression suite, but the project deliberately distinguishes software evidence from physical acceptance. The RC label stays until the exact public build has been exercised sufficiently on a real WARBL2.

### Current software gate

`v1.0.0-rc.1` passed **158 / 158 asserted software checks**, plus 2 informational benchmarks.

The suite includes:

- source / invariant regression;
- browser and authority workflow regression;
- all-button / control-effect checks;
- responsive-layout checks;
- realtime and local-bend stress;
- semantic / process simulation;
- prerequisite-sensitive WARBL2 installation simulation;
- close-pitch fidelity tests.

See [`releases/v1.0.0-rc.1/SIMULATION_RESULTS.md`](releases/v1.0.0-rc.1/SIMULATION_RESULTS.md) for the exact release evidence.

## Very close Scala pitches

The Laboratory intentionally preserves close scale degrees as distinct floating-point source values rather than merging or rounding them.

The RC regression suite includes a real test pair at:

- `852.5373134328358` cents
- `855.223880597015` cents

Difference: **2.6865671641791096 cents**.

Both remain separate through parsing, mapping, and the internal Reference Instrument. Synthetic **1.0-cent, 0.5-cent, and 0.1-cent** separations are also retained internally.

This is an **internal/reference-instrument software guarantee**, not a claim that every external 14-bit MPE receiver at every bend range can reproduce the same sub-cent resolution.

## Truth layers

The Laboratory keeps four kinds of truth separate:

1. **Source-scale truth** — the imported Scala tuning.
2. **Physical fingering truth** — what the controller sensors actually report.
3. **Tuning-output truth** — the pitch the Laboratory calculates and outputs.
4. **Hardware verification** — what has actually been confirmed on the physical WARBL / WARBL2.

This separation is why a device-chart mismatch can be diagnosed without allowing the device chart to overwrite the Scala file.

## Release files

The current candidate is in [`releases/v1.0.0-rc.1`](releases/v1.0.0-rc.1/).

**Exact application SHA-256**

```text
9d77a5a93cfa3d493a9ffdbd73b08a255e6d0a117e676760952f94f7253bc79c
```

**Release-candidate ZIP SHA-256**

```text
e0b95a259b82cf75ac6c97ce4bebc71fe3d12ef73697cf89f4fc4dd96de4a901
```

## Evidence vocabulary

Project records use these labels deliberately:

- **DESIGNED** — specified but not yet established by executable evidence.
- **SOFTWARE VERIFIED** — established by source, browser, simulation, or deterministic package evidence.
- **USER OBSERVED** — reported during real use but not necessarily instrumented.
- **PHYSICALLY VERIFIED** — established with physical WARBL / WARBL2 evidence.
- **REJECTED** — deliberately not accepted.
- **UNRESOLVED** — evidence remains open.

A build may be software verified without being physically verified.

## Reporting a problem

For musical or controller bugs, the most useful report includes:

- exact build/version;
- browser and operating system;
- WARBL / WARBL2 firmware when known;
- loaded Scala file;
- authority mode (`Lab Fingering` or `Automatic verification`);
- what you expected;
- what you heard or saw;
- a Flight Recorder JSON capture when possible.

Use the repository issue templates for either a normal bug report or a physical-test report.

## Updates

The repository contains a machine-readable release pointer at [`updates/latest.json`](updates/latest.json). It is intended to become the stable public source for the Laboratory's **Check for Updates** feature.

## Documentation

- [Architecture and truth boundaries](docs/ARCHITECTURE.md)
- [Testing and evidence discipline](docs/TESTING.md)
- [Contributing](CONTRIBUTING.md)
- [Release history](CHANGELOG.md)

## License

A public software license has **not yet been selected**. No `LICENSE` file is included intentionally. Please do not assume redistribution or derivative-work permissions until a license is explicitly added.

## Project status

This repository begins with a release candidate rather than pretending the recovery and physical-acceptance history never happened. Earlier recovered builds remain part of the project evidence lineage, while `v1.0.0-rc.1` is the first candidate intended to serve as the public 1.0 release line.
