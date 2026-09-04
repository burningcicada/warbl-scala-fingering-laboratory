# WARBL Scala Fingering Laboratory v1.1 — GitHub Deployment Checklist

Upload/replace these paths on the repository's GitHub Pages branch (normally `main`):

1. `index.html` — replace current Pages entry.
2. `WARBL_Scala_Fingering_Lab_v1_1.html` — add named stable v1.1 artifact.
3. `README.md` — replace current README.
4. `RELEASE_NOTES_v1.1.md` — add release notes.
5. `updates/latest.json` — replace update manifest.
6. `docs/QUICK_START.md` — replace.
7. `docs/DISCOVERY_MANUAL.md` — replace.
8. `docs/DEEP_LAB_MANUAL.md` — replace.
9. `SHA256SUMS.txt` — replace/add release checksums.
10. `RELEASE_VERIFICATION_v1.1.txt` — replace/add release verification record.

The existing `WARBL_Scala_Fingering_Lab_v1_0.html` may remain in the repository as the frozen v1.0 historical artifact.

After committing, verify:

- https://burningcicada.github.io/warbl-scala-fingering-laboratory/ reports v1.1.0;
- the top status banner says **stable public release**, not developer repository build;
- the update checker reports v1.1.0 as current;
- `index.html` and `WARBL_Scala_Fingering_Lab_v1_1.html` have identical SHA-256;
- GitHub Release tag is `v1.1.0` and its primary HTML asset is `WARBL_Scala_Fingering_Lab_v1_1.html`.
