# Contributing

Contributions are welcome, but this project treats musical correctness and controller evidence as regression-sensitive.

## Before changing behavior

Please identify which layer is changing:

1. source-scale truth;
2. physical fingering observation;
3. tuning / output behavior;
4. hardware verification;
5. presentation / diagnostics only.

Do not make a controller observation silently rewrite imported Scala truth.

## Bug reports

Prefer a reproducible report with:

- exact version and SHA when possible;
- browser / OS;
- WARBL / WARBL2 model and firmware;
- Scala file;
- authority mode;
- expected behavior;
- observed behavior;
- Flight Recorder JSON if available.

## Evidence labels

Use the project's evidence vocabulary rather than treating simulation as hardware proof:

- DESIGNED
- SOFTWARE VERIFIED
- USER OBSERVED
- PHYSICALLY VERIFIED
- REJECTED
- UNRESOLVED

## Pull requests

A behavior-changing PR should explain:

- the defect or intended behavior;
- the truth layer affected;
- why source-scale authority remains safe;
- what regression tests were run;
- whether the result has physical WARBL / WARBL2 evidence.

Changes to realtime MIDI / sensor handling should include a stress or timing regression whenever possible.
