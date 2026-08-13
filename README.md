# SLOP PARADE

SLOP PARADE is a single-file browser game about managing approval pressure during a fast coding session. The player has two minutes to finish a project by approving useful agent changes, rejecting dangerous requests, and using compact context at the right moments to control the queue.

## Play Locally

Open `codex-approval-rush.html` in any modern browser. No install step, build tool, local server, or internet connection is required.

## Objective

Reach 100% project readiness before the two-minute timer expires.

Approval prompts appear at random positions on the desktop:

- Accept useful changes to increase progress.
- Decline dangerous changes to avoid destructive actions.
- Accepting a dangerous prompt ends the game immediately.
- Declining a useful prompt removes time from the countdown.
- Compact Context clears all visible approval prompts as correct and pauses new prompt spawning for 10 seconds.

## Game Feedback

The interface includes:

- Countdown timer
- Project readiness meter
- Correct approval count
- Risk-stopped count
- Active queue size
- Score
- Agent activity feed
- Terminal-style status output
- Clear win and game-over screens

## Extending Prompts

Prompt definitions live near the top of the embedded JavaScript in `slop-parade.html`:

```js
const PROMPT_LIBRARY = [
  { kind: "good", title: "...", detail: "...", file: "..." },
  { kind: "bad", title: "...", detail: "...", file: "..." }
];
```

Use `kind: "good"` for prompts where Accept is correct. Use `kind: "bad"` for prompts where Decline is correct.
