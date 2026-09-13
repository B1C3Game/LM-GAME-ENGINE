# Game Template for LM-ENGINE

This is the boilerplate structure and checklist for creating a new LM game.

---

## Folder Structure

Use this exact structure:

```
games/my-new-game/
├── README.md                          # What is this game? (2–3 paragraphs)
├── RULES.md                           # Complete game rules (5–10 pages)
├── GAME-MASTER-PROMPT.md              # The copy/paste prompt
└── [OPTIONAL] SCENARIOS/
    └── scenario-name.md
```

---

## README.md Template

```markdown
# [Game Title]

## Overview

[2–3 sentences. What is the core challenge? Who plays? Why is it fun?]

## Quick Facts

- **Players:** [How many? Roles?]
- **Time:** [How long for one game?]
- **Rounds:** [How many turns typically?]
- **Difficulty:** [Easy / Moderate / Hard / Depends on players]

## How It Works

[Brief explanation of the game loop. 1–2 paragraphs.]

## Getting Started

1. Read [RULES.md](RULES.md) (takes ~10 min)
2. Copy the [master prompt](GAME-MASTER-PROMPT.md)
3. Paste it into ChatGPT or Claude
4. Have another player look at the conversation
5. Play!

## Learn More

- **[Full Rules](RULES.md)** — Complete specification
- **[Master Prompt](GAME-MASTER-PROMPT.md)** — Copy-paste ready
- [Sample game log](EXAMPLES/sample-1.md) — See it in action

---

**Status:** Tested and ready | First released: [DATE]
```

---

## RULES.md Template

```markdown
# [Game Title] — Complete Rules

## Objective

What are the players trying to achieve? State it clearly.

## Players & Roles

- **Count:** [How many players?]
- **Roles:** [If asymmetric, explain each role]
- **Turn order:** [How do turns rotate?]

## The Game Loop

### Phase 1: [Name]
[What happens in this phase?]

### Phase 2: [Name]
[What happens in this phase?]

[Continue for all phases...]

## Scoring

| Action | Points |
|--------|--------|
| [Action 1] | +X |
| [Action 2] | +Y |

[Explain point pools, deductions, bonuses, etc.]

## Win Condition

[When does the game end and who wins? Be specific.]

## Example Round

[Walk through a complete example game, showing:
- What each player does
- How the LLM scores it
- The final result]

## Special Rules & Edge Cases

[Clarifications on:
- What happens if a player tries something unexpected?
- How disputes are resolved
- Any ambiguous terms]

## Referee Guidelines for the LLM

[If the LM will make judgment calls, be explicit about how:
- \"Is this a valid move?\"
- \"Did the player meet the objective?\"
- \"How to score this edge case?\"]

## FAQ

Q: [Common question]  
A: [Answer]

---

**Version:** [DATE] | **Balance tested:** [How many rounds?]
```

---

## GAME-MASTER-PROMPT.md Template

```
# [Game Title] — Master Prompt

Copy everything below this line and paste it into ChatGPT, Claude, or another LLM.

---

# [GAME TITLE]

**Version:** [DATE]

## Welcome

Hello! You're about to play [game title]. Here's what's happening:

[2-3 sentences explaining the game to new players]

## The Rules

[Include the complete rules inline. No external references. Keep to <1500 words.]

### Objective
[What are we doing?]

### Players & Roles
[Who are we?]

### Phases
[Walk through each turn]

### Scoring
[How many points for what?]

### Win Condition
[When do we stop?]

## How I'll Run This

I will:
1. Track the game state (current round, scores, whose turn)
2. Evaluate your moves against the rules
3. Score fairly and transparently
4. Explain my decisions if you question them

You cannot see future information (no spoilers). I will keep tests, cards, or hidden information private until the right moment.

## Let's Begin

**Player 1 (or use your name):** Are you ready?
**Player 2 (or use your name):** Are you ready?

[Once both confirm, initialize the game]

---

## Example of Turn Format

I might say:

> **Round 1 | Player 1's Turn**
> 
> [Game state here]
> 
> What do you do?

You respond:

> I [action]

I then:

> You [resolved action]. [Updated state]
> 
> Player 2's turn.

---

[Rest of prompt continues below...]
```

---

## Checklist Before Launch

### Rules Document
- [ ] Objective is stated in one clear sentence
- [ ] All player roles are defined
- [ ] The game loop is described phase-by-phase
- [ ] Scoring is explicit (X points for Y action)
- [ ] Win condition is unambiguous
- [ ] At least one complete example round is shown
- [ ] Edge cases are addressed
- [ ] Length is 1000–2000 words

### Master Prompt
- [ ] Starts with a human greeting
- [ ] Rules are complete and inline (≤2000 words)
- [ ] First turn is shown as an example
- [ ] I (the LM) explain how I'll referee fairly
- [ ] Appeal process is clear if players dispute my scoring
- [ ] Prompt ≤3000 tokens total
- [ ] Tested with ChatGPT ✓
- [ ] Tested with Claude ✓
- [ ] Tested with 2+ real human pairs ✓

### File Structure
- [ ] README.md is friendly and clear
- [ ] RULES.md is complete
- [ ] GAME-MASTER-PROMPT.md is ready to copy/paste
- [ ] No typos or broken markdown
- [ ] All files use clear, concise language

### Meta
- [ ] Game has been played at least 3 times
- [ ] Known balance issues are documented (if any)
- [ ] You can explain the appeal of the game in 2 sentences

---

## Tips for Success

### Make It Replayable
The best LM games are playable multiple times because:
- Scenarios or concepts vary (like Concept Drift's Concept Space algorithm)
- Outcomes depend on player choices (not deterministic)
- Each play teaches something new

### Make Failure Fun
- Frame loss as discovery, not failure
- Show what went wrong (the "reveal" moment)
- Make the LM honest: "You lost because of X, not because the rules were unfair"

### Keep Prompts Readable
- Use short sentences
- Explain why a decision was made, not just what it was
- Don't hide game state (show the board, scores, etc. every turn)

### Test Rigorously
- Play at least 3 full games yourself (recruit friends)
- Note every moment where you're confused or arguing
- Fix those moments in the rules or prompt
- Test with a different LLM (GPT vs Claude)

---

## Questions?

- See [GAME-SPEC.md](../GAME-SPEC.md) for detailed specifications
- Review [Concept Drift](../games/concept-drift/) as a working example
- Ask in an issue or pull request

**Ready to create?** Copy this structure into `games/[your-game-name]/` and start writing.
