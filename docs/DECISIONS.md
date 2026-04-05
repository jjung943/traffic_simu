# Decisions

## 2026-05-04
- Use GitHub as the source of truth for the project
- Keep the project portable across AI tools
- Start with a simple browser-based simulation
- Focus on a small first milestone before adding complexity
## 2026-04-05 (session 2)
- **Ramp geometry extended**: `RAMP_DROP` increased to make ramps long enough to visualize queuing. Ramp start X is now computed relative to screen width so the full ramp is always visible.
- **On-ramp merge redesigned with IDM gap acceptance**: Ramp cars now use IDM-based gap acceptance at the merge nose (checking front and rear gaps against `IDM_S0 + v * T_ACCEPT`). Cars that cannot merge decelerate toward a virtual stop bar at `STOP_PROG=0.90`. This replaces the old binary yield check.
- **Collision detection fixed for ramp-vs-lane4 pairs**: Onramp and offramp cars are on physically separate roads. Their bounding boxes overlap with lane-4 cars near the merge/split zones but this is not a crash — these pairs are now excluded from collision detection.
- **Ballistic (constant-acceleration) integration adopted**: Both lane cars and ramp cars now use ballistic integration (`pos += 0.5*(vel_old + vel_new)`) instead of Euler forward integration. This is the standard approach in movsim and prevents the gap from going negative when braking hard.
- **Post-update gap enforcement added**: After the IDM update, if any car has overlapped its leader (which can happen when the closing speed exceeds what `BMAX` can handle in a single frame), the follower is pushed back to maintain a minimum gap of `0.5 * IDM_S0`. This is a numerical safeguard, not a physics override — the IDM already applied maximum braking.
- **IDM_BMAX increased to 15 m/s²**: The previous value of 9 m/s² (≈0.9g) was insufficient for emergency braking at highway speeds. 15 m/s² (≈1.5g) is physically plausible for hard braking and reduces the required stopping distance.
- **MERGE_X moved to 40% of screen width**: Previously at 25%, the merge zone was too close to the left edge, leaving insufficient room for the l4Follower gap check. At 40%, there is enough screen space for the gap acceptance criterion to work correctly.

## 2026-04-05 (session 1)
- **Adopted Realism-First Philosophy**: The purpose of the simulation is to depict traffic as realistically as possible, not to artificially prevent traffic jams or crashes. We removed all "anti-crash engineering" (such as merge grace periods, magic ramp-awareness sensors, and teleportation). Cars now only obey physics-based rules (like leader-following gaps and line-of-sight yielding). If the traffic volume or layout dictates a crash, the crash must be allowed to happen.
- **Implemented AI Contradiction Protocol**: To protect the realism-first philosophy, any future user requests or design notes that introduce artificial safety logic must be flagged by the AI. The AI is required to explain the contradiction and ask the user to confirm the override before implementing the change.
