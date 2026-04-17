---
description: Scan all content directories and report status of drafts, ideas, and published content
allowed-tools: Read, Glob, Grep
model: haiku
---

Scan all content directories and report the current status.

1. **Scan these directories:**
   - `corporate/drafts/blog/` — blog post drafts
   - `authors/*/drafts/linkedin/` — LinkedIn drafts (per author)
   - `authors/*/posted/linkedin/` — published LinkedIn posts (per author)
   - `authors/*/ideas/` — idea backlog (per author)
   - `corporate/ideas/` — corporate ideas
   - `campaigns/` — active campaigns
   - `website/knowledge-base/` — AEO articles

2. **For each file found, report:**
   - Filename
   - Status (draft, published, idea)
   - Campaign tag (if present in frontmatter)
   - Last modified date

3. **Cross-reference with `strategy/content-calendar.md`:**
   - Flag any scheduled content that does not have a draft file
   - Flag any draft files not tracked in the calendar

4. **Output a summary table:**

   ```
   ## Content Status Report

   ### Blog Posts
   | File | Status | Campaign | Last Modified |
   |------|--------|----------|---------------|

   ### LinkedIn
   | File | Status | Campaign | Last Modified |
   |------|--------|----------|---------------|

   ### Campaigns
   | Campaign | Pieces | Status |
   |----------|--------|--------|

   ### Gaps
   - [List any scheduled content without drafts]
   - [List any drafts not in the calendar]
   ```
