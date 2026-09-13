# Game Specification for LM-ENGINE

## What Is an LM Game?

An LM game is a bounded, rule-based interaction designed to be orchestrated by an LLM through conversation. It's not a simulation, not a story generator, and not a tutorial. It's a game.

**Core Requirements:**

1. **Determinate outcome** — The game has a clear win/loss condition, not an open-ended narrative
2. **Measurable score** — Results can be quantified (points, pass/fail, rounds won)
3. **Referee-able by the LLM** — The LM can evaluate player actions and score honestly without human re-arbitration (or has explicit appeal rules)
4. **State preservable in conversation** — The game state can be tracked through the chat history alone
5. **Defined termination** — The game ends after N rounds or when a win/loss condition is met, not when players get bored

## The Three Pillars

### 1. Rules (Specification)

**Format:** Markdown document, 3–10 pages

**Covers:**
- **Objective:** What are the players trying to achieve?
- **Players:** How many? Roles? Asymmetry?
- **Phases:** The sequence of turns, decisions, and evaluations
- **Scoring:** How many points per action? Win conditions?
- **Termination:** When does the game end?
- **Appeals:** If the LM's judgment is questioned, what's the process?

**Reference:** [Concept Drift Rules](games/concept-drift/ROUND-FLOW.md)

### 2. Master Prompt

**Format:** A single, copy-paste-ready prompt for the LM

**Requirements:**
- Self-contained (references rules via the prompt, not external links)
- Stateless initialization — can be pasted fresh into a new chat
- State preservation — tracks game state by referencing previous messages
- Player identification — understands which player is which (usually by turn or explicit declaration)
- Honest refereeing — evaluates outcomes according to the spec, not by trying to keep players happy
- Verbose scaffolding — explains what it's doing so players can trust its decisions

**Length:** 500–3000 tokens typical

**Template structure:**
```
[GAME NAME]
Version: [DATE]

## How to Play This Game
[Brief explanation, as if to a friend]

## The Rules
[Complete game rules, inline]

## Let's Start
[Initialization prompt]
```

**Reference:** [Concept Drift Master Prompt](games/concept-drift/GAME-MASTER-PROMPT.md)

### 3. Scenarios (Optional)

**Format:** Markdown variants that adjust the game rules for specific contexts

**Examples:**
- **Customer Service Mode** (Concept Drift) — Concepts are drawn from customer support situations
- **Teaching Mode** — The game uses a curriculum of pre-selected concepts
- **Incident Response** — Faster rounds, higher pressure

**Scenarios are optional.** Not every game needs them, but they extend replayability.

---

## File Structure

Every game must have:

```
games/[game-name]/
├── README.md                          # Overview (What is this game?)
├── RULES.md                           # Complete rules (5–10 pages)
├── GAME-MASTER-PROMPT.md              # Copy/paste prompt for ChatGPT/Claude
├── [OPTIONAL] SCENARIOS/              # Variant rule sets
│   ├── customer-service.md
│   ├── teaching-mode.md
│   └── [other-scenario].md
├── [OPTIONAL] EXAMPLES/               # Sample round logs
│   ├── sample-round-1.md
│   └── sample-round-2.md
└── [OPTIONAL] CALIBRATION/            # Dev notes on balance testing
    └── balance-notes.md
```

---

## Validation Checklist

Before submitting a game to LM-ENGINE:

### Rules Document
- [ ] Objective is clear (what are we trying to do?)
- [ ] Win condition is unambiguous
- [ ] Termination is defined (not open-ended)
- [ ] Scoring is quantified
- [ ] All player roles are explained
- [ ] At least one example round is walked through
- [ ] Referee rules are clear (how does the LM decide disputes?)

### Master Prompt
- [ ] Starts with a human-readable greeting (explain what's about to happen)
- [ ] Includes full rules inline (no external references)
- [ ] Shows the first turn's setup
- [ ] Explains state tracking (how it will remember the game state)
- [ ] Is ≤3000 tokens (fits in one message)
- [ ] Has been tested with at least two different LLMs
- [ ] Has been tested with two real humans (not just one person playing both roles)

### Structure & Format
- [ ] README.md explains the game in 2–3 paragraphs
- [ ] RULES.md is comprehensive (>500 words)
- [ ] File names match the spec above
- [ ] Markdown is clean (no formatting errors)

---

## Scoring & Game Types

### Point-Based Games
Games where players earn points per turn and the winner has the highest score.

**Pros:** Easy to implement, clear progress  
**Cons:** Can feel arbitrary if points don't map to meaningful actions

### Pass/Fail Games
Games where the outcome is binary (you solved it or you didn't).

**Pros:** Clear win/loss, high narrative satisfaction  
**Cons:** Boring on loss; hard to replay

### Collaborative Scoring (Recommended)
Games where the two players score the same outcome and learn from joint failure.

**Pros:** Matches the decentralized ethos; removes winner/loser shame  
**Cons:** Requires thoughtful design so mutual loss feels like discovery, not waste

**Reference:** [Concept Drift's collaborative scoring model](games/concept-drift/GAME-CONCEPT.md#what-makes-failure-fun)

---

## Common Pitfalls

### 1. Relying on Perfect LLM Judgment
Don't assume the LM will always score fairly. **Build appeals into the prompt.** If the LM's decision is wrong, the game breaks. Make it easy for players to question and override.

### 2. Leaking Game State
If the LM needs to track, say, "the player's budget" or "cards in hand," make sure it can do so from the chat history alone. Test this by copying the prompt into a fresh chat thread mid-game.

### 3. Asymmetric Information Without Verification
If one player knows something the other doesn't (like a hidden test or answer), build a moment to verify they understood. Otherwise, players will argue forever about whether the information was ambiguous.

### 4. Open-Ended Termination
Avoid "play until you're satisfied" or "see how many rounds you can go." Define a hard stop: 10 rounds, 30 minutes, or "until someone wins."

### 5. Prompt Bloat
If the master prompt exceeds 3000 tokens, split it. Put optional rules in a separate document. The prompt should be copyable and readable, not a wall of text.

---

## Design Philosophy

**Why these constraints?**

- **Self-contained prompts** (no APIs) mean games work in ChatGPT, Claude, local models, and future LLMs without changing a line
- **Conversational state tracking** means no backend, no database, no infrastructure—just chat history
- **Determinate scoring** means the game doesn't devolve into players arguing about whether they won
- **Collaborative over competitive** means losing is less painful and teaches more

---

## Submission Process

Ready to publish a game?

1. Fork or branch this repository
2. Create a folder under `games/[your-game-name]/`
3. Add README.md, RULES.md, GAME-MASTER-PROMPT.md (and optionals)
4. Check every item in the Validation Checklist
5. Open a pull request with:
   - A one-paragraph summary of the game
   - A note on testing (who played it, how many rounds)
   - Any known balance issues or edge cases
6. Maintainer reviews for spec compliance, not for taste
7. Merged → available on LM-ENGINE

---

**Questions?** See [GAME-TEMPLATE.md](GAME-TEMPLATE.md) or review the [Concept Drift source](games/concept-drift/).
