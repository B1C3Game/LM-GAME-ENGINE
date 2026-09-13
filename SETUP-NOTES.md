# LM-GAME-ENGINE Platform — Setup Notes

**Date:** 2026-09-13  
**Status:** Core documentation scaffolded; Concept Drift integration complete  
**GitHub:** https://github.com/B1C3Game/LM-GAME-ENGINE

---

## What's Been Created

### Core Platform Files

- **[README.md](README.md)** — Platform overview and quick start
- **[GAME-SPEC.md](GAME-SPEC.md)** — What makes a valid LM game (design requirements)
- **[GAME-TEMPLATE.md](GAME-TEMPLATE.md)** — Folder structure and file checklist for game creators
- **[ONBOARDING.md](ONBOARDING.md)** — New player guide (first-time experience)
- **[games/README.md](games/README.md)** — Game catalog index

### Folder Structure

```
LM-ENGINE/
├── README.md                    # Platform overview
├── GAME-SPEC.md                 # Game design specification
├── GAME-TEMPLATE.md             # Template for new games
├── ONBOARDING.md                # New player guide
├── SETUP-NOTES.md               # This file
└── games/
    ├── README.md                # Game catalog
    └── concept-drift/           # [TO BE ADDED]
```

---

## Next Steps

### 1. Integrate Concept Drift

Currently, Concept Drift lives at:  
`C:\2\B1C3\B1C3-GAME-STUDIO\Concept-drift\`

**Option A: Move it**  
Move the entire Concept-drift folder into LM-ENGINE:  
`games/concept-drift/`

**Option B: Mirror it**  
Copy key files (RULES.md, GAME-MASTER-PROMPT.md, etc.) from Concept-drift into a new games/concept-drift folder, keeping the original as the "development source."

**Recommendation:** Option A (move) — Single source of truth, cleaner platform structure.

**Files to include in games/concept-drift/:**
- README.md (from Concept-drift/README.md, adapted)
- RULES.md (from Concept-drift/ROUND-FLOW.md or consolidated)
- GAME-MASTER-PROMPT.md (extract from existing prompts)
- SCENARIOS/ (customer-service.md, teaching-mode.md, etc.)
- EXAMPLES/ (sample game logs from chatpumps/ folder)

### 2. Create a Build/Generation System (Optional)

For web deployment (if you want this browsable at a URL later):

- Static site generator (Hugo, Jekyll, 11ty) to convert Markdown → HTML
- GitHub Pages or Netlify auto-deploy from this folder
- Search index (for browsing games by tags, mechanics, difficulty)

For now, keep it Markdown-native. It's portable and version-control friendly.

### 3. Document Game Discovery & Browsing

Add to games/README.md:

- Tagging system (e.g., `#collaborative`, `#transmission`, `#strategy`)
- Filtering by players, time, difficulty
- Search by game mechanic or theme

Example:

```
### Filter by Mechanic
- [Transmission Games](tags/transmission.md) — Explaining concepts, teaching
- [Negotiation Games](tags/negotiation.md) — Bargaining, persuasion
- [Mystery Games](tags/mystery.md) — Revelation, discovery
```

### 4. Add Version Control Metadata

Each game should track:

```yaml
---
title: Concept Drift
version: 1.0
released: 2026-09-13
tested_with:
  - ChatGPT-4
  - Claude-3-Opus
tested_players: 5 pairs (10 individual players)
balance_status: Stable
known_issues: None
---
```

Add a frontmatter block at the top of README.md for each game.

---

## Platform Philosophy (Preserved)

✓ **Decentralized:** Games are protocols, not servers  
✓ **Prompt-native:** Copy and play, no infrastructure  
✓ **Collaborative:** Players score together, not against each other  
✓ **Replayable:** Outcomes vary, designed for multiple plays  

---

## Hosting Strategy

### Phase 1: GitHub (Current)
- Games stored as Markdown in this repo
- Players fork/clone or read the docs
- Share via GitHub links or raw Markdown files

### Phase 2: Simple Web (Optional)
- Auto-generate HTML from Markdown
- Host on GitHub Pages (free, automatic)
- Simple search and browsing UI

### Phase 3: Distributed (Future)
- Games published as .zip or Git repos
- Scenario packs as downloadable modules
- Version management and dependency tracking

---

## Immediate Action Items

- [ ] Move or mirror Concept Drift into games/concept-drift/
- [ ] Extract/create GAME-MASTER-PROMPT.md for Concept Drift (finalize format)
- [ ] Test the master prompt with 2+ LLMs and 2+ human pairs
- [ ] Update games/README.md to feature Concept Drift with link
- [ ] Update main README.md to reflect Concept Drift availability
- [ ] Publish and share with beta testers

---

## Questions & Decisions Pending

1. **Source of Truth:** Should Concept Drift live only in LM-ENGINE/games/concept-drift, or should Concept-drift/ folder (elsewhere) remain as the authoring source?

2. **Documentation:** Should we consolidate Concept Drift's many markdown files (ROUND-FLOW.md, CONCEPT-GENERATION-ALGORITHM.md, etc.) into the three-file structure (README.md, RULES.md, GAME-MASTER-PROMPT.md), or keep them as reference docs?

3. **Platform Scope:** Should LM-ENGINE also host:
   - A testing/debugging guide for game creators?
   - Analytics dashboard (to track which games are popular)?
   - Community forum or feedback system?

4. **Version Pinning:** Should games pin the version of the master prompt in use? (E.g., players can request "Concept Drift v1.0" or "v1.1")

---

## References

- **Main Workspace:** C:\2\B1C3\
- **Game Studio Folder:** C:\2\B1C3\B1C3-GAME-STUDIO\
- **LM-ENGINE:** C:\2\B1C3\B1C3-GAME-STUDIO\LM-ENGINE\
- **Concept Drift (Source):** C:\2\B1C3\B1C3-GAME-STUDIO\Concept-drift\

---

**Last Updated:** 2026-09-13  
**Status:** Waiting for next action (Concept Drift integration)
