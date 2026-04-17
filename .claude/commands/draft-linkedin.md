---
description: Draft a LinkedIn post for an author on a given topic
allowed-tools: Read, Glob, Grep
model: sonnet
argument-hint: <author> <topic>
---

Draft a LinkedIn post for the specified author on the given topic.

**Arguments:** $ARGUMENTS (first argument is the author name, rest is the topic)

Execute the following steps:

1. **Load context:**
   - Read the author's voice profile at `/authors/<name>/voice/voice-profile.md`
   - Read `/brand/voice-guidelines.md`
   - Read `/brand/author-bios.md`
   - Check `/strategy/content-calendar.md` for related scheduled content

2. **Draft the post:**
   - Short paragraphs (2-3 sentences).  Not single-line poetry style.
   - Lead with the insight.  Never bury the lead.
   - No contractions, no em dashes, two spaces after periods
   - Active voice, positive framing
   - End with a genuine, specific question
   - Target 800-1500 characters
   - If promoting a blog post, link goes in the first comment (note this in the draft)

3. **Provide 2-3 alternative hooks** — different opening angles for the same topic

4. **Save** to `/authors/<name>/drafts/linkedin/YYYYMMDD-slug.md` or `/authors/<name>/drafts/linkedin/topic-draft-01.md`

5. **Add publishing notes:** blog dependency, link placement, campaign tag
