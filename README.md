# LMU FSAE Wiring Harness

Complete electrical harness for Loyola Marymount University's Formula SAE car, integrating a Honda CBR600RR engine with a Haltech Elite 1500 ECU over CAN bus.

Designed and constructed by **Maxwell Bispham** (Electronics Lead), with assistance from **[Partner Name]**.

## Overview

The harness is split into three sub-harnesses to simplify routing, fabrication, and serviceability:

| Sub-harness | Scope |
|---|---|
| Cockpit | Driver controls, master switches, shutdown circuit, dash/driver interface |
| Rear Systems | Power distribution, battery, rear-mounted components |
| Engine | ECU connections, sensors, injectors, ignition |

The full schematic covers 60+ circuits and was drawn in RapidHarness.

### Key features

- **ECU integration:** Honda CBR600RR engine running on a Haltech Elite 1500, with CAN bus communication
- **Sensor suite:** coolant temperature, MAP, TPS, oil pressure, and neutral switch
- **EMI mitigation:** shielded cabling on the knock sensor line
- **Safety:** FSAE-compliant shutdown circuit and dual master-switch ignition system with a cockpit override

## Design Philosophy and Constraints

This harness was built under a fixed deadline: the car had to be driving by the start of May. Several constraints shaped the design, and the decisions below were made deliberately to get a reliable, rules-compliant car on the ground in time.

**Learning while building.** This was my first wiring harness. Harness design, connector selection, termination, and fabrication were all learned over the course of the project. Every part of the process, from schematic to crimping to routing on the chassis, was done for the first time here.

**Late-arriving dependencies.** Physical harness design depends on knowing where everything lives on the car: chassis geometry, component mounting locations, and routing paths. Those subsystems were not finalized until February, which left roughly three months to design, fabricate, install, and debug the harness physically.

**Parallel responsibilities.** In addition to the harness, I was responsible for tuning the engine on the Haltech ECU (fuelling, cold start, and RPM limits). Harness work and tuning had to progress in parallel, and tuning could not begin until the harness was functional.

**Resulting decision: keep the electrical design simple.** Given these constraints, I scoped the electrical architecture to what was necessary for a safe, running, and tunable car rather than adding features that would put the deadline at risk. Priorities were, in order:

1. Rules compliance and driver safety (shutdown circuit, master switches)
2. Reliable engine operation and ECU communication
3. Sensor data needed for tuning
4. Serviceability through the three-sub-harness split

## Known Limitations and Future Work

The simple architecture was the right call for this season, and it leaves clear room for improvement in future iterations:

- [Example: formal power distribution module or fused/relayed circuits per load]
- [Example: additional sensors for data acquisition, such as wheel speed or suspension travel]
- [Example: improved connector standardization and labeling]
- [Example: weight and length optimization once component locations are stable earlier in the season]

## Tools and Components

- **Schematic:** RapidHarness
- **ECU:** Haltech Elite 1500
- **Engine:** Honda CBR600RR
- [Add connector families, wire gauge/spec, sleeving, and crimp tools used]

## Acknowledgments

Thanks to **Anemone Mehta** for help with fabrication and assembly, and to Loyola Marymount University for $1,700 in project funding.
