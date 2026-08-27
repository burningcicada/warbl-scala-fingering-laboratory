# Architecture and truth boundaries

The WARBL Scala Fingering Laboratory is intentionally not a simple MIDI-note remapper.

Its central architectural invariant is:

> Controller behavior must never rewrite source-scale truth.

## Source-scale truth

The imported Scala file is canonical. Pitch geometry, listening, mapping, fingering recommendations, controller installation, and notation are derived from it; they do not silently modify it.

## Physical fingering truth

When live raw WARBL sensor data is available, the Laboratory can observe the actual hole state and resolve it against the active Working Fingering. This physical witness is separate from the MIDI note identity currently emitted by the device.

## Performance authority

### Lab Fingering

Normal performance uses the Laboratory Working Fingering from raw sensors plus local expression. A mismatch with the device's installed MIDI chart is therefore visible but does not automatically silence valid Lab-fingering performance.

### Automatic verification

Automatic is a stricter agreement-checking mode. When exact device MIDI identity and concurrent Working-Fingering evidence disagree, it fails closed rather than guessing.

## Tuning output

The Laboratory retains exact Scala cents internally and calculates reference frequencies directly. The 256-state WARBL chart is a controller note-anchor structure; exact microtonal performance may still require the Laboratory's retuned output or a tuning-aware external receiver.

## Note lifecycle

A note release must release the exact identity established by the corresponding Note On. Continuous bend changes expression, not structural degree.

## Realtime boundary

The hot musical path is kept separate from expensive diagnostics, formatting, full-view rebuilding, archive work, and non-realtime browser operations such as Print. The Flight Recorder exists to make failures traceable without redefining musical truth.
