# WARBL Scala Fingering Laboratory v1.1.0 — GitHub deployment checklist

This package is prepared for the public `main` branch.

1. Open the repository and choose **Add file → Upload files**.
2. Upload the **contents of this ZIP**, preserving folders. Do not upload the ZIP itself into the repository root.
3. Existing `index.html` and `WARBL_Scala_Fingering_Lab_v1_1.html` should be replaced. Existing historical `WARBL_Scala_Fingering_Lab_v1_0.html` should remain untouched.
4. Confirm the new `profiles/WARBL2/` and `docs/verification/` folders are included.
5. Use commit message: `Promote v1.1.0 visual witness alignment`
6. Wait for GitHub Pages deployment to turn green.
7. Open the live Lab and confirm the blue status line begins **“WARBL Scala Fingering Lab v1.1 stable public release.”**
8. Import a Scala file, connect WARBL2, and verify a tonic→second-degree fingering transition: if Physical/ Mapped reach degree 2 before commitment, the primary Sounding identity must remain tonic until the audible carrier transfers.
9. Confirm **Latency & Wake Probe** is collapsed at launch.
10. If the live page passes, create/publish GitHub Release tag `v1.1.0` titled **WARBL Scala Fingering Laboratory v1.1** and attach the public release ZIP and named HTML artifact.

The optional reference controller preset is `profiles/WARBL2/WARBL_SFL_reference_preset.warbl`. It is never loaded automatically.
