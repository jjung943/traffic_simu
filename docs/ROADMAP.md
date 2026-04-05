# Roadmap

## Phase 1: Foundation (Completed)
- [x] Set up repository structure
- [x] Choose initial stack (Vanilla HTML5 Canvas + JS, no build tools)
- [x] Create first runnable version (served via GitHub Pages)

## Phase 2: First Simulation (Completed)
- [x] Render a simple road or grid
- [x] Render one car
- [x] Move the car across the screen

## Phase 3: Traffic Behavior & Realism-First Physics (Completed)
*Note: The design pivoted away from intersections/traffic lights toward a realism-first highway model.*
- [x] Implement a 4-lane one-way highway
- [x] Add an on-ramp and off-ramp (Lane 4)
- [x] Implement continuous random spawning of multiple cars
- [x] Add leader-following gap physics (cars maintain safe distance based on speed)
- [x] Implement line-of-sight yield logic for on-ramp merging
- [x] Implement strict AABB collision detection across all cars
- [x] **Realism-first principle:** Remove all artificial crash-prevention logic; crashes happen organically when physics dictate they should

## Phase 4: Controls and DVR System (Completed)
- [x] Add live Traffic Volume slider to control spawn rates and density
- [x] Implement a DVR-style history buffer (stores last ~30 seconds of simulation state)
- [x] Add Play / Pause / Reset controls
- [x] Add click-to-toggle Rewind feature that works before and after a crash
- [x] Add Speed multiplier control (1×, 2×, 4× playback)
- [x] Add interactive Scrub Bar to jump to any recorded frame instantly
- [x] Implement post-crash Replay mode (frozen history replay without generating new frames)
- [x] Ensure crash outlines and banners persist correctly during scrubbing and replay

## Phase 5: Variability and complexity (In Progress)
- [x] Implement normal distribution (Box-Muller transform) for per-car characteristic sampling
- [x] Per-car **speed** drawn from N(μ, σ) — clamped to [0.5, 6.0] px/frame
- [x] Per-car **follow gap** drawn from N(μ, σ) — clamped to [2, 120] px
- [x] User-controllable μ and σ for both characteristics via the Driver Characteristics panel
- [ ] Add additional driver archetypes (e.g., aggressive, average, cautious)
- [ ] Assign driver archetypes characteristics
    - Propensity to switch lanes 
    - Aggression  
- [ ] Add toggles for each of the various behaviors to allow user to modify

## Phase 6: Simulation dashboard
- [ ] Add trial log to keep track of results and key characteristics of trial
- [ ] Visualize key metrics across numerous trials to understand key factors driving traffic  

## Phase 7: Solution testing 
- [ ] TBD

## Phase 8: Polish
- [ ] Improve visuals
- [ ] Refactor simulation logic
- [ ] Add tests for core behavior

## Phase 9: Refinements
- [ ] Import real road data from Google Maps and upgrade from simplified road structure
