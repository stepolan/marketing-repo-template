---
description: Review content for brand alignment, lead placement, bio consistency, and proof points
allowed-tools: Read, Glob, Grep
model: sonnet
argument-hint: <file-path>
---

Review the specified content file for brand alignment and quality.

**Target file:** $ARGUMENTS

1. **Read the file** and load context:
   - The relevant author's `authors/<name>/voice/voice-profile.md`
   - `brand/voice-guidelines.md`
   - `brand/author-bios.md`

2. **Check these areas:**

   **Lead quality:**
   - Does the first 3 sentences deliver the main insight?
   - Journey trap? (building up chronologically)
   - Context trap? (front-loading background before the point)
   - Fairness trap? ("many valid approaches" before taking a position)

   **Voice consistency:**
   - Run the full voice check (contractions, em dashes, passive voice, tone, etc.)

   **Bio and title:**
   - Correct title per `brand/author-bios.md`?
   - Bio format matches the content type?

   **Proof points:**
   - Are claims supported with specifics?
   - Any unsupported assertions?

   **Formatting:**
   - Blog: flowing paragraphs?
   - LinkedIn: short paragraphs (2-3 sentences)?
   - Frontmatter complete (author, date, tags, pillar, campaign)?

3. **Report:**
   ```
   ## Content Review — [filename]

   ### Lead Quality: [Strong / Needs Work]
   [Details]

   ### Voice: [Strong / Needs Work / Off Voice]
   [Details with line numbers]

   ### Brand Alignment: [Aligned / Gaps]
   [Details]

   ### Recommended Actions
   1. [Specific action]
   2. [Specific action]
   ```
