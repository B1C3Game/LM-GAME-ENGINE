# Game Research & Adaptation Candidates

## Key Finding

**Most existing Werewolf/social deduction repos require local installation, APIs, or are Discord bots. No simple copy/paste prompt-based versions exist for ChatGPT/Claude.**

This is actually a **feature, not a bug**. Games built from scratch for LM-GAME-ENGINE will work better because:
- Optimized for text-only, asynchronous play
- No API keys, no setup, no infrastructure
- Clear communication through conversation (no hidden state)
- Designed around LLM strengths (honest refereeing, state tracking)

---

## Tier 1: Strong Candidates (Text-Native, Few Rules)

### Social Deduction

**Werewolf / Mafia**
- **Type:** Public domain (originated as party game)
- **Format:** Perfect for LLM referee
- **Rules complexity:** Low (discussion + voting)
- **Status:** Free to adapt; no licensing needed
- **Adaptation notes:** LLM can manage hidden roles, track votes, handle day/night cycles
- **Example:** https://github.com/search?q=werewolf+game (many open-source versions)

**Among Us (text version)**
- **Type:** Popular mobile game by Innersloth
- **Format:** Would need permission
- **Rules complexity:** Medium
- **Status:** Copyright Innersloth; would need licensing
- **Adaptation notes:** Remove visual elements, keep discussion/voting core

### Storytelling/Narrative

**Fiasco (Bully Pulpit Games)**
- **Type:** Tabletop RPG
- **Format:** Conversational, dice-less variant possible
- **Rules complexity:** Medium
- **Status:** Open License (OGL compatible)
- **Adaptation notes:** Could work; cooperative storytelling with LLM as narrator/mediator
- **Link:** https://www.bullypulpitgames.com/games/fiasco/

**Once Upon a Time (Atlas Games)**
- **Type:** Card-based storytelling
- **Format:** Adaptable to prompt-based (LLM assigns narrative prompts instead of cards)
- **Rules complexity:** Low
- **Status:** Proprietary; needs permission
- **Adaptation notes:** Players tell a story; LLM judges coherence/creativity

### Word/Logic Games

**20 Questions**
- **Type:** Classic parlor game (public domain)
- **Format:** Perfect for LLM
- **Rules complexity:** Minimal
- **Status:** Free to use
- **Adaptation notes:** LLM thinks of a concept; players ask yes/no questions; LLM answers honestly

**Codenames (Czech Games Edition)**
- **Type:** Board game
- **Format:** Text version without visual grid
- **Rules complexity:** Low-medium
- **Status:** Proprietary; needs permission
- **Adaptation notes:** LLM shows word list; one player gives one-word clues; other player guesses

**Rhyme Time / Word Association**
- **Type:** Simple word game (public domain)
- **Format:** Natural fit
- **Rules complexity:** Minimal
- **Status:** Free to use
- **Adaptation notes:** Players build off each other's words; LLM judges creativity

### Negotiation/Debate

**Structured Debate Formats (Lincoln-Douglas, Public Forum)**
- **Type:** Educational/competitive formats
- **Format:** Highly textual
- **Rules complexity:** High (but well-documented)
- **Status:** Public frameworks
- **Adaptation notes:** LLM as moderator; players take opposing positions; LLM scores arguments

**Apples to Apples (public domain variant)**
- **Type:** Party game
- **Format:** Judgment game
- **Rules complexity:** Low
- **Status:** Original game proprietary, but mechanics are simple/adaptable
- **Adaptation notes:** LLM shows adjective; players submit nouns; LLM judges best match

### Mystery/Investigation

**Detective (Local/DIY mystery games)**
- **Type:** Cooperative mystery
- **Format:** Text-based clues
- **Rules complexity:** Medium
- **Status:** Many are self-published or open
- **Adaptation notes:** LLM presents mystery; players ask questions to gather clues; solve within rounds

**20 Questions (Mystery variant)**
- **Type:** Variation of 20 Questions
- **Format:** One player thinks of a concept; others investigate
- **Rules complexity:** Low
- **Status:** Free to use
- **Adaptation notes:** Already fits LLM format perfectly

---

## Tier 2: Possible Candidates (Needs More Adaptation)

- **Catan (Settlers of Catan)** — Strategy game; could adapt trade/negotiation mechanics but complex resource tracking
- **One Night Werewolf** — Fast social deduction variant; simpler than full Werewolf
- **The Resistance** — Bluffing/deduction; text-adaptable
- **Coup** — Bluffing card game; roles could map to text prompts
- **7 Wonders Duel** — Two-player strategy; heavy rule overhead for LLM

---

## Tier 3: Lower Priority (Too Complex or Licensing Issues)

- **Dungeons & Dragons** — Too heavy; needs extensive system
- **Magic: The Gathering** — Card management; licensing restrictions
- **Chess/Go** — Game theory works but very different from LM-GAME-ENGINE philosophy
- **Fortnite/PUBG variants** — Real-time; doesn't fit async LLM model

---

## Licensing Quick Reference

| Game | Type | License | Contact | Notes |
|------|------|---------|---------|-------|
| Werewolf | Public Domain | Open | N/A | Can adapt freely |
| Fiasco | Tabletop RPG | OGL | Bully Pulpit Games | Check specific license |
| 20 Questions | Public Domain | Open | N/A | Can adapt freely |
| Codenames | Board Game | Proprietary | Czech Games Edition | Needs permission |
| Once Upon a Time | Card Game | Proprietary | Atlas Games | Needs permission |
| Among Us | Digital Game | Proprietary | Innersloth | Needs permission |

---

## Recommended Next Steps

1. **Quick Win**: Implement Werewolf and 20 Questions (both public domain, minimal licensing)
2. **Medium Lift**: Contact Bully Pulpit Games about Fiasco adaptation license
3. **With Permission**: Reach out to Czech Games Edition for Codenames, Innersloth for Among Us text variant
4. **Custom**: Design 1-2 original games that are uniquely suited to LLM format

---

## Research Status

- [ ] Finalize Werewolf adaptation (rules + master prompt)
- [ ] Finalize 20 Questions variant (rules + master prompt)
- [ ] Contact Bully Pulpit Games (Fiasco)
- [ ] Contact Czech Games Edition (Codenames)
- [ ] Contact Innersloth (Among Us text variant)
- [ ] Design 1 new mystery game tailored to LLM
- [ ] Design 1 new negotiation game tailored to LLM

---

**Last updated:** 2026-09-13
