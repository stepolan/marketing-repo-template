---
description: Check a draft against the author's voice profile and flag deviations
allowed-tools: Read, Glob, Grep
model: haiku
argument-hint: <file-path>
---

Run a voice consistency check on the specified draft file.

**Target file:** $ARGUMENTS

1. **Read the target draft file.**  If no file specified, ask which file to check.

2. **Load the voice profile:**
   - Read the relevant author's voice profile at `/authors/<name>/voice/voice-profile.md`
   - Read `/brand/voice-guidelines.md`

3. **Check the draft against voice patterns.  Flag:**
   - [ ] Contractions used (don't, won't, it's, etc.) — should be written out
   - [ ] Em dashes (—) or double hyphens (--) used — should use periods or colons
   - [ ] Single space after punctuation — should be two spaces
   - [ ] Passive voice — should be active
   - [ ] Preachy or teaching tone toward peers
   - [ ] Blame language toward engineers/teams
   - [ ] Corporate jargon (synergy, leverage, best-in-class)
   - [ ] Hype language (game-changing, revolutionary)
   - [ ] Lead is buried — most interesting insight not in first 3 sentences
   - [ ] Credentials listed in body (titles, companies, years)
   - [ ] Engagement bait closing ("Agree?" "Thoughts?")
   - [ ] Single-line poetry formatting (blog should be paragraphs, LinkedIn should be 2-3 sentence paragraphs)
   - [ ] Correct title used per `brand/author-bios.md`

4. **Report results:**

   ```
   ## Voice Check Results — [filename]

   ### PASS
   - [Rule]: [Brief confirmation]

   ### FAIL
   - [Rule] (line N): `[offending text]` → `[suggested fix]`

   ### Overall: [Strong / Needs Work / Off Voice]
   ```

   Every FAIL item must include a specific line number and a before/after suggestion.
