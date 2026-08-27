# v1.0.0-rc.1 — Simulation Results

All tests below were run against the exact release-candidate HTML.

- Source / invariant regression: 50 / 50 PASS.
- New RC browser/control/close-pitch/raw-transition gate: 22 / 22 PASS.
- Inherited recovered.7 browser protections: 21 / 21 PASS.
- Inherited workflow / authority gate: 18 / 18 PASS.
- Responsive containment: 8 / 8 PASS.
- Realtime / local-bend / 5,000-bend stress: 8 / 8 PASS.
- Semantic / process suite: 29 / 29 PASS + 2 informational benchmarks.
- Targeted prerequisite-sensitive controls: 2 / 2 PASS (Copy 256 values; simulated WARBL2 install).

Cumulative distinct asserted checks: 158 / 158 PASS, plus 2 informational benchmarks.

## Close-pitch precision
- User-observed scale pair: 852.5373134328358 cents vs 855.223880597015 cents = 2.6865671641791096 cents apart.
- Internal frequencies remain distinct and ratio matches exact cents math.
- Reference Instrument renders both degrees separately with logical/reference frequencies equal.
- Synthetic 1.0-cent distinction survives.
- Synthetic 0.5-cent distinction survives.
- Synthetic 0.1-cent distinction survives.

These are internal software/reference-instrument results. External MIDI/MPE resolution remains receiver- and bend-range-dependent.

## Control surface
- 159 / 159 button elements have click wiring.
- Previously dead Extended Mapping buttons now have concrete effects.
- Pattern Tutor / Practice generation and native exercise export succeed.
- Principal export controls produce nonempty payloads.
- Copy 256 values writes 256 integers.
- Simulated verified WARBL2 chart installation reaches acknowledged-installed state.
