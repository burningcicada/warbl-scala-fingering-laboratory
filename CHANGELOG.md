# Changelog

## v1.0.0-rc.1 — 2026-08-27

First public 1.0 release candidate.

### Preserved from the recovered lineage

- Lab Fingering is the normal performance authority when live raw WARBL sensors are available.
- Automatic remains a strict fail-closed verification mode.
- Source Scala remains canonical.
- Physical fingering and sounding/authorized degree remain separate witnesses.
- Local pitch-bend semantics remain anchored to the current physical fingering.
- Note Off releases the exact identity established at Note On.
- Realtime observer, recorder, and configuration work remains isolated from the hot musical path.

### Fixed for RC1

- Wired the previously dead Extended Scale Mapping `Generate / refresh systems` control.
- Wired `Download DAW workflow` and verified a nonempty payload.
- Repaired Pattern Tutor / Practice structural-signature calls.
- Restored Generate path, Play / begin, native exercise export, Start exercise, and Replay prerequisite flow.
- Added a permanent all-button wiring/effect release gate.
- Added explicit post-blocking raw-state reacquisition.
- Improved paired raw-hole byte commit behavior.
- Added a narrow 8 ms transition-sync opportunity for evidence-defined stale-raw attack transitions; the rejected historical blanket 18 ms delay remains rejected.
- Added close-pitch fidelity regression down to 0.1 cent internally.

### Verification

- 158 / 158 asserted software checks PASS.
- 2 informational benchmarks retained.
- Deterministic release packaging PASS.
- Physical WARBL2 acceptance still pending.
