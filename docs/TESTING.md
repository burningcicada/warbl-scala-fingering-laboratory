# Testing and evidence discipline

## Release rule

A release candidate is not marked PHYSICALLY VERIFIED merely because browser tests are green.

## v1.0.0-rc.1 software gate

- Source / invariant regression: 50 / 50 PASS
- New RC browser/control/close-pitch/raw-transition gate: 22 / 22 PASS
- Inherited recovered.7 browser protections: 21 / 21 PASS
- Inherited workflow / authority gate: 18 / 18 PASS
- Responsive containment: 8 / 8 PASS
- Realtime / local-bend / 5,000-bend stress: 8 / 8 PASS
- Semantic / process suite: 29 / 29 PASS + 2 informational benchmarks
- Targeted prerequisite-sensitive controls: 2 / 2 PASS

Total: **158 / 158 asserted checks PASS**, plus 2 informational benchmarks.

## Button/control gate

The RC contains 159 button elements. The release gate asserts click wiring across all 159 and separately exercises effect-producing controls such as exports, clipboard output, Pattern / Practice, and simulated WARBL2 chart installation under appropriate prerequisites.

## Close-pitch gate

The software gate protects the distinction between very close Scala degrees through parsing, mapping, and the internal Reference Instrument.

Current fixtures include:

- 2.6865671641791096 cents (observed real scale pair)
- 1.0 cent
- 0.5 cent
- 0.1 cent

This verifies the internal path. External MIDI/MPE resolution remains dependent on receiver implementation and bend range.

## Physical-test priorities for RC1

- fast repeated attacks;
- transitions where Note On occurs near a raw-hole state change;
- sustained breath and local bend;
- very close Scala degrees;
- Print → return → play without moving fingers first;
- Project ZIP export;
- Pattern Tutor / Practice controls;
- Extended Mapping controls;
- Flight Recorder ON/OFF comparison.
