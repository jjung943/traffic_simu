# traffic_simu
inspired by DSAIL final project - let's model if we can stop traffic through a consumer tool

## Goal
A project to create a web-based app that models automobile traffic patterns based on modifiable human driver characteristics and implementable technology solutions.

## Stack
Undecided / TBD

## Current status
Highway layout with on/off ramp, collision detection, and physical rules implemented.

## Physical rules
- Cars cannot overlap; any contact triggers a crash and halts the simulation
- Cars may not stop inside the merge/split zone — they must commit or stop before it
- On-ramp cars yield until a gap is available in the highway lane

## Next steps
1. Add start/pause/reset controls (Phase 4)
2. Add simulation speed control
3. Track basic metrics (car count, wait time)

## How to run   
Simply open `index.html` in any modern web browser. No build steps or server required.