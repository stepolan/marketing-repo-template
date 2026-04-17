---
description: Analyze an author's existing content and extract a voice profile
allowed-tools: Read, Glob, Grep
model: sonnet
argument-hint: <author>
---

Analyze an author's existing content and generate a voice profile from it.

**Arguments:** $ARGUMENTS (the author name, matching a directory under `authors/`)

Execute the following steps:

1. **Find all content by this author:**
   - Scan `authors/<name>/posted/linkedin/` for published posts
   - Scan `authors/<name>/drafts/linkedin/` for drafts
   - Scan `corporate/drafts/blog/` for blog posts where the Author field matches
   - Scan `authors/<name>/samples/` for any imported prior work
   - If no content found, tell the user to add existing content first

2. **Read every file found.**  You need volume to extract patterns.  Read all of them.

3. **Analyze the writing for these dimensions:**

   **Sentence and paragraph structure:**
   - Average sentence length
   - How paragraphs are constructed (short/punchy vs. flowing)
   - Use of fragments vs. complete sentences

   **Rhetorical patterns:**
   - How do they open a piece?  (Question, bold claim, scenario, statistic)
   - How do they close?  (Question, call to action, reflection)
   - Do they use rhetorical questions?  How often?
   - Do they use lists, frameworks, or narrative arcs?

   **Tone and stance:**
   - Formal vs. conversational
   - Authoritative vs. exploratory
   - Contrarian vs. consensus-building
   - How do they handle disagreement or critique?

   **Word-level patterns:**
   - Contractions or no contractions
   - Punctuation habits (em dashes, semicolons, ellipses, exclamation marks)
   - Jargon level (technical terms, industry shorthand, plain language)
   - Filler or hedge words they use or avoid
   - Characteristic phrases or constructions that recur

   **Content patterns:**
   - Do they use data and citations?
   - Do they tell stories or paint scenarios?
   - Do they reference personal experience?
   - Do they name-drop or give credit to others?

4. **Generate a voice profile** following the structure in the existing template at `authors/<name>/voice/voice-profile.md`.  The output must include:
   - Core Characteristics (bulleted list of defining traits)
   - Voice Patterns (with named patterns and examples pulled from their actual writing)
   - Words/Phrases to AVOID (patterns you did NOT see and that would sound off-voice)
   - Formatting Rules (what you observed about structure)
   - Instructions for AI (numbered rules for reproducing this voice)
   - Voice Check (checklist of does/does-not sound like this author)

5. **Show the profile to the user for review** before writing it.  Ask if anything is wrong or missing.

6. **After approval, write it** to `authors/<name>/voice/voice-profile.md`.

7. **Report:**
   - How many pieces were analyzed
   - The strongest patterns (most consistent across pieces)
   - Any inconsistencies noticed (voice shifts between pieces that may need a decision)
