# AI Context

## Project
Traffic simulation project.

## Goal
Build a simple visual traffic simulation that can grow in complexity over time and model what it would look like for potential traffic solutions to be implemented. 

## Current direction
Start with a browser-based version that is easy to run and easy to iterate on.

## Conventions
- Keep changes small and focused
- Explain what changed
- Do not rename files unless needed
- Keep simulation logic separate from rendering when possible
- **Realism over Safety**: The simulation must model realistic physics and driver decisions. Artificial rules that prevent crashes (e.g., collision immunity grace periods, teleporting cars out of danger, or magic "ramp-awareness" sensors) are strictly forbidden. Crashes are a natural and expected outcome of dense traffic and must be allowed to occur.
- **Contradiction Protocol**: If a user requests a change or design feature that contradicts the "Realism over Safety" philosophy, the AI MUST flag the contradiction, explain why it reduces realism, and ask the user to confirm or rethink the request before writing any code. The user retains the right to override the AI's warning.

## Current priority
Begin implementing Phase 4: Controls and Metrics (start/pause/reset, speed controls, basic metrics).

## First milestone
Render a simple road layout and make one car move. (Completed)

## Phase 3 milestone
Multiple cars, 4-way intersection, traffic lights, stop/go behavior. (Completed)

## Notes for AI tools
- Read README.md and this file first
- Prefer simple implementations over clever ones
- Update docs when the project structure changes

## When making changes
- Update README if setup changes
- Add or update tests
- Keep commits focused