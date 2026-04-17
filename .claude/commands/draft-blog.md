---
description: Scaffold a blog post with proper structure, voice, and frontmatter
allowed-tools: Read, Glob, Grep
model: sonnet
argument-hint: <author> <topic>
---

Scaffold a blog post with proper structure, voice, and author bios.

**Arguments:** $ARGUMENTS (first argument is the author name, rest is the topic)

Execute the following steps:

1. **Load voice and brand context:**
   - Read the relevant author's voice profile at `/authors/<name>/voice/voice-profile.md`
   - Read `/brand/voice-guidelines.md` for corporate voice
   - Read `/brand/author-bios.md` for correct titles and bios

2. **Draft the post:**
   - **NEVER BURY THE LEAD** — Lead with the insight, not the journey
   - Lead with value/benefit, not features
   - Use flowing paragraphs, not single-line formatting
   - No contractions, no em dashes, two spaces after periods
   - Tie back to brand pillars
   - Use proper author bio (short bio for blog headers)
   - End with a genuine question, not engagement bait

3. **Save the draft** to `/corporate/drafts/blog/YYYYMMDD-slug.md` with this frontmatter:

   ```
   # Title

   **Author:** [Name], [Title], [Company]
   **Date:** [Date]
   **Tags:** [Relevant tags]
   **Pillar:** [Brand pillar]
   **Campaign:** [campaign-slug if applicable]
   **Author Bio:** See `brand/author-bios.md`

   ---
   ```

4. **Report:**
   - Which brand pillars are covered
   - Any gaps that need filling
