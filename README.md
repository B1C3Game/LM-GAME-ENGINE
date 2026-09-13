# LM-GAME-ENGINE
## A Prompt-Based Game Platform for Language Models

**LM-GAME-ENGINE is a decentralized game platform where you play sophisticated games instantly through ChatGPT, Claude, or any LLM—no downloads, no accounts, no friction. Just a prompt and another player.**

---

## What Is This?

LM-ENGINE hosts games designed to work through pure conversation. The LM becomes the game engine, referee, and collaborative interface. Two players share one prompt and discover what happens.

### Current Games

- **[Concept Drift](games/concept-drift/)** — A transmission game. Can you explain a concept well enough that someone else can use it correctly? The test is locked before you start explaining. Copy the [master prompt](games/concept-drift/GAME-MASTER-PROMPT.md) and play instantly.

### What Makes These Games Different

1. **No UI required** — The game runs in the chat interface you already use
2. **Decentralized** — No server, no matchmaking, no infrastructure. Just copy a prompt, invite a friend
3. **Concept-first** — Games are structured around a clear mechanic, not a story or simulation
4. **Collaborative scoring** — You win or lose together. The LM referees fairly

---

## Quick Start

1. **Pick a game** from the list above
2. **Read the Rules** in the game's README
3. **Copy the Master Prompt** for your LM (ChatGPT, Claude, etc.)
4. **Invite another player** — they need to see the conversation thread
5. **Play**

No registration. No waiting. No installation.

---

## What's Coming?

Check [games/PIPELINE.md](games/PIPELINE.md) for games in development—like **Ghost**, the classical word game adapted for LLM refereeing. These have draft prompts and are awaiting player testing. Feedback and test runs move games from pipeline to verified.

---

## For Game Creators

Want to build a new LM game?

- Start with [GAME-SPEC.md](GAME-SPEC.md) to understand the format
- See [GAME-TEMPLATE.md](GAME-TEMPLATE.md) for the folder structure and required files
- Review how [Concept Drift](games/concept-drift/) is organized
- Submit via pull request (or contact the maintainer)

---

## Core Concepts

### What Makes a Valid LM Game?

- **Self-contained prompt**: A single master prompt that an LLM can execute
- **State management through conversation**: The LM tracks game state via dialogue, not a database
- **Deterministic win/loss conditions**: Score can be verified by the LM without human judgment (or has a clear appeals process)
- **Works with any LLM**: No API calls, no special integrations (unless explicitly optional)
- **Playable asynchronously**: Two players don't need to be online simultaneously

### The Three-Part Structure

Every LM game has:
1. **Rules** (What are we trying to do?)
2. **Master Prompt** (The complete game engine, formatted for copy/paste)
3. **Scenarios** (Variants or constraints—optional)

---

## Philosophy

**Games, not simulations.** The difference is scoring and termination.

**Collaborative, not competitive.** You learn more from a game where you win together than one where you prove dominance.

**Prompt-native.** The game should not apologize for being text-only or asynchronous. Lean into it.

---

## Links

- [Game Specification](GAME-SPEC.md) — How to define an LM game
- [Game Template](GAME-TEMPLATE.md) — Folder structure and file checklist
- [Onboarding Guide](ONBOARDING.md) — First time? Start here
- [Games Directory](games/) — Browse all available games

---

**Status**: Early beta. The first game (Concept Drift) is the reference implementation. More games coming.
