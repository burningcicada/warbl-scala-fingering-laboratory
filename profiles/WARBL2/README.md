# WARBL2 reference preset

`WARBL_SFL_reference_preset.warbl` is the controller-side WARBL2 preset used as the principal reference configuration during late WARBL Scala Fingering Laboratory physical testing.

## Evidence status

- **Artifact type:** device configuration snapshot, not a performance recording.
- **File signature/version:** `WARBL` / `1`.
- **Configuration messages:** 411.
- **SHA-256:** `879edef0640c9a16be4622bd79b7a5e714a5bbf34e83beddc8527a89181ef886`.
- The file is preserved byte-for-byte from the supplied reference preset.
- Physical behavior is established separately by Flight Recorder traces; the Laboratory does not infer performer behavior from this preset alone.

## Use

This preset is optional. It is provided so another WARBL2 user can reproduce the controller-side configuration associated with the reference development setup before comparing physical traces. Importing a WARBL preset changes the selected controller configuration, so save your own WARBL setup first. The Laboratory never applies this file automatically.

## Relationship to the Laboratory

The evidence chain is kept separate:

1. **WARBL preset** — intended controller configuration.
2. **Flight Recorder trace** — what the hardware and performer actually produced.
3. **Laboratory performance profile / interpretation** — how the software interprets that evidence.

This separation follows the project rule that raw/controller evidence must remain distinct from software interpretation.
