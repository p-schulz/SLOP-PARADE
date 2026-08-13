# SLOP PARADE

SLOP PARADE is a single-file browser game about managing approval pressure during a fast coding session. The player has two minutes to finish each project by approving useful agent changes, rejecting dangerous requests, and using compact context at the right moments to control the queue.

## Play Locally

Open `index.html` in any modern browser. The game fills the browser window automatically. No install step, build tool, local server, or internet connection is required.

## Objective

Reach 100% project readiness before the two-minute timer expires. Completing a project advances to the next level, where prompts spawn more frequently and the active queue can grow larger.

## Level Progression

- Level 1: only useful approval prompts appear.
- Level 2: dangerous prompts begin appearing and must be declined.
- Level 3: Compact Context can appear, clearing the visible approval queue and pausing new approvals for 10 seconds.
- Level 4: unrequested AI image-generation popups can appear and must be dismissed.
- Level 5: token usage is tracked; if the active provider reaches its limit, approvals pause until the player switches providers.
- Level 6: project funds unlock a coffee-break prompt to buy the enterprise token plan.
- Level 7: Accept and Decline buttons use the same dark-gray styling, and their order can change between prompts.
- Level 8 and later: no new systems are introduced; prompt pressure continues to increase.

Approval prompts appear at random positions on the desktop:

- Accept useful changes to increase progress.
- Decline dangerous changes to avoid destructive actions.
- Accepting a dangerous prompt ends the game immediately.
- Declining a useful prompt removes time from the countdown.
- Letting more than 10 approval prompts remain open ends the game.
- Compact Context clears all visible approval prompts as correct and pauses new prompt spawning for 10 seconds.
- Dismiss image-generation popups when they appear.
- Switch providers when the token limit is exceeded.
- Buy the enterprise token plan once the coffee-break prompt appears.

## Game Feedback

The interface includes:

- Countdown timer
- Project readiness meter
- Current project level
- Correct approval count
- Risk-stopped count
- Active queue size
- Token usage
- Current provider and project funds
- Score
- Agent activity feed
- Terminal-style status output
- Clear win and game-over screens

## Extending Prompts

Prompt definitions live near the top of the embedded JavaScript in `index.html`:

```js
const PROMPT_LIBRARY = [
  { kind: "good", title: "...", detail: "...", file: "..." },
  { kind: "bad", title: "...", detail: "...", file: "..." }
];
```

Use `kind: "good"` for prompts where Accept is correct. Use `kind: "bad"` for prompts where Decline is correct.
