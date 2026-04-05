# Decisions

## 2026-05-04
- Use GitHub as the source of truth for the project
- Keep the project portable across AI tools
- Start with a simple browser-based simulation
- Focus on a small first milestone before adding complexity
## 2026-04-05
- **Adopted Realism-First Philosophy**: The purpose of the simulation is to depict traffic as realistically as possible, not to artificially prevent traffic jams or crashes. We removed all "anti-crash engineering" (such as merge grace periods, magic ramp-awareness sensors, and teleportation). Cars now only obey physics-based rules (like leader-following gaps and line-of-sight yielding). If the traffic volume or layout dictates a crash, the crash must be allowed to happen.
