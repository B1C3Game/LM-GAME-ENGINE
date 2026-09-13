# Pipeline Games

Games with master prompts in development, awaiting verification through player testing.

These are candidates that have been researched, have draft prompts, but **have not yet been tested** with multiple LLM+player combinations. Once a game passes testing (≥2 player pairs, ≥2 different LLMs), it moves to the verified games catalog.

---

## Ghost

**Status:** Master prompt drafted, awaiting 2+ player test runs

- **Type:** LLM-Refereed word game
- **Players:** 2–4
- **Time:** 10–15 minutes per round
- **Difficulty:** Medium (vocabulary required)
- **Angle:** Classical word game adapted for LLM narration/refereeing
- **Core Rule:** Players take turns adding letters to a growing word fragment without completing a valid word. The player who completes a word loses the round.
- **LLM Role:** 
  - Maintains dictionary authority
  - Validates letter sequences (are they the start of a real word?)
  - Adjudicates challenges ("Can you name a word starting with these letters?")
  - Tracks game state and score
  - Decides which dictionary (e.g., Scrabble OSPD, common English)

**Critical Design Decision:** Dictionary source matters. A master prompt must specify which word list to use (Scrabble Players Dictionary, common usage, etc.) to avoid disputes.

**Next Steps:**
1. Draft master prompt with clear dictionary rules
2. Test with 2+ player pairs (Discord, ChatGPT, Claude)
3. Collect feedback on adjudication clarity
4. Move to `games/ghost/` when verified

---

## [Coming Soon]

Add more pipeline games here as they are researched and drafted.

---

## How to Contribute

Have a game idea or a classical game you think works as an LLM prompt?

1. Create an entry here with: game name, type, core rule, LLM role
2. Draft the master prompt following [GAME-TEMPLATE.md](../GAME-TEMPLATE.md)
3. Test with ≥2 player pairs and ≥2 LLMs
4. Open an issue or submit a PR with results
5. Once verified, it moves to the main games catalog

**Note:** Public-domain and original games are welcome. Licensed games require explicit permission.
