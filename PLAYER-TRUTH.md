# Player's Guide: What You're Actually Playing

**Before you start:** You're playing a game orchestrated by a language model, not a deterministic game engine. This matters. Here's what to expect.

---

## The Honest Facts

### 1. The LLM Is Not a Database

Language models are probabilistic. They predict the next token based on patterns, not by looking things up. This means:

- **Inconsistency is possible.** The LLM might call something a valid word one round and reject it the next
- **Hallucination is real.** The model might invent a "fact" or "rule interpretation" that sounds plausible but isn't in the prompt
- **Forgetting happens.** Long conversations can drift from the original game state if the model doesn't explicitly reference the ledger
- **Bias is baked in.** The training data shapes what the model thinks is "fair" or "correct"

**What to do:** Keep the game state visible in a `GAME STATE` block. Check it after every round. If the model contradicts it, pause and flag it.

### 2. The Model Is Not Impartial

OpenAI (ChatGPT), Anthropic (Claude), Google (Gemini) and others train their models with human feedback. This shapes behavior:

- **The model may try to make everyone happy.** It's trained to be helpful and agreeable, which sometimes conflicts with fair refereeing
- **Cultural assumptions vary by model.** Claude and ChatGPT have different notions of what's "appropriate" or "reasonable"
- **The model may protect its creators.** If a ruling would embarrass OpenAI or Anthropic, the model might reframe it
- **Content policies exist.** Some topics or words may be rejected or penalized even if they're part of the game rules

**What to do:** Read the ruling carefully. If it feels wrong, ask the model to explain its reasoning. Challenge it. The best game prompts make rulings falsifiable, not final.

### 3. You're Playing with Corporate Infrastructure

Every LLM game runs on servers owned by a major tech company. That means:

- **Availability is not guaranteed.** API outages, rate limits, or service changes can interrupt play
- **Privacy is conditional.** Your conversation may be used to improve the model (check the service's privacy policy)
- **Terms of service apply.** You're bound by ChatGPT's, Claude's, or Gemini's terms, which can change
- **The model can refuse to play.** If the game violates content policies, the model may stop mid-game

**What to do:** Keep a copy of the rules and game state locally. Don't assume a conversation will be preserved forever. If the model refuses to continue, try a different LLM or host (they have different policies).

### 4. Fairness Is Negotiated, Not Automatic

Because the LLM makes judgments, fairness requires:

- **Transparent reasoning.** The model should explain *why* it made each ruling
- **The ability to appeal.** A ruling should be reversible if the model made a mistake or contradicted itself
- **Clear precedent.** Early rulings should guide later ones (or the model should acknowledge why it's different)
- **Honest uncertainty.** If the model is unsure, it should say so instead of faking confidence

**What to do:** Build the appeal process into the game from the start. Require the model to cite its reasoning. If two runs produce different outcomes, that's not a bug—it's a feature. Discuss it.

---

## Why Play This Way Then?

**Instant setup.** No installation, no servers to run, no accounts to create. Copy a prompt and play in 30 seconds.

**Social play.** You get a conversational game master, not a rulebook you have to parse. The LLM can adapt pacing, explain things, and respond to your improvisation.

**Asymmetric play.** Some games benefit from the LLM's slight unpredictability. Concept Drift works *because* the model sometimes surprises you with its judgment.

**Iteration without friction.** You can play a new game variant every week without writing code or resetting a database.

The tradeoff is you sacrifice perfect fairness and consistency for speed and accessibility. That's a reasonable choice for social games—but only if you go in eyes open.

---

## When Things Go Wrong

### The model contradicts itself
**Example:** Round 1, the model says "GHOSTING" is a valid word. Round 2, it rejects it.

→ Pause. Pull up the explicit `GAME STATE` ledger. Point to the contradiction. Ask the model to explain or revert the decision.

### The model invents a rule
**Example:** You follow the prompt exactly, but the model says you violated a rule that isn't in the prompt.

→ Quote the prompt. Ask the model to cite where that rule appears. If it can't, explain that the prompt is the authority.

### The model stops responding
**Example:** You send a turn, and the model says "I can't continue with this game because..."

→ Start a new chat. Paste the prompt again. Copy your game state from the previous session. Resume from where you left off.

### The outcome feels unfair
**Example:** You lose on a judgment call that seems subjective or wrong.

→ **You get to disagree.** The game prompt should let you appeal. Present your evidence. The model may reconsider. If both sides still disagree, you can acknowledge the dispute and move on—or write down both interpretations and compare how different models rule.

---

## The Philosophy

A game that depends on an LLM is not less legitimate because it's probabilistic. It's just different.

Traditional games (chess, Monopoly, card games) rely on perfect rule enforcement through players or dealers. LLM games rely on negotiated fairness and transparent reasoning.

This works best when:
- Players are willing to speak up if something feels wrong
- The game prompt makes state and reasoning visible
- Everyone understands going in that rulings are subject to appeal
- You prioritize fun over perfect competitive balance

If you need a perfectly fair competitive game, use a traditional board game or a video game with a deterministic engine.

If you want a social, collaborative, improv-friendly game that you can play instantly in chat, this is the way.

---

## TL;DR

- ✓ The LLM is good at: narration, improvisation, explaining reasoning, adapting to surprises
- ✗ The LLM is bad at: perfect consistency, secure secrets, real-time fairness guarantees
- ⚠ You are responsible for: keeping state visible, speaking up when something's wrong, knowing the rules matter more than the model's authority

**Play well. Question rulings. Have fun.**
