# Marketing Content Repository

## Content Calendar

The content calendar and tracker is at `strategy/content-calendar.md`.  This is the source of truth for:
- All published content (blog posts, LinkedIn posts) with dates and URLs
- All scheduled upcoming content with dates and dependencies
- Unscheduled drafts that are ready or near-ready
- Blocked/gated content waiting on external triggers
- Idea pipeline summary

**Keep the calendar up to date.**  When content is published, move it from Scheduled to Published and add the URL.  When new content is scheduled, add it to the Scheduled section.  When drafts are created or completed, update the status.

## Key Directories

- `corporate/drafts/blog/` — Blog posts (filename format: `YYYYMMDD-slug.md`)
- `corporate/ideas/` — Corporate idea backlog
- `authors/<name>/drafts/linkedin/` — Author LinkedIn drafts
- `authors/<name>/posted/linkedin/` — Published LinkedIn posts (moved here after posting)
- `authors/<name>/ideas/` — Author idea backlog
- `authors/<name>/voice/voice-profile.md` — Per-author writing voice rules
- `campaigns/` — Campaign briefs and shared assets (see Campaigns section below)
- `website/knowledge-base/` — AEO articles for LLM discoverability
- `brand/author-bios.md` — Source of truth for author bios and titles
- `brand/voice-guidelines.md` — Company-wide voice guidelines

Each author has their own subdirectory under `authors/` with drafts, posted content, ideas, and voice profile.  This supports multi-author setups (co-founders, marketing team members, guest writers).

## Campaigns

Content is organized by medium (blog/, linkedin/) for publishing workflows, and linked by campaign for context.

**Campaign directory:** `campaigns/<campaign-slug>/` contains:
- `README.md` — index with links to all content, status, asset URLs
- `brief.md` — audience, goals, key messages, content piece inventory, dependencies
- `assets/` — shared media (images, video files, thumbnails, diagrams)

**Campaign frontmatter:** Every content file that belongs to a campaign includes `**Campaign:** <campaign-slug>` in its frontmatter header.  One-off posts (not part of a campaign) omit this field.

**Find all assets for a campaign:** `grep -r "Campaign: <slug>"` across the repo, plus check `campaigns/<slug>/assets/` for media.

**When to create a campaign:** When a topic produces more than one content piece (blog + LinkedIn promo, multi-day series, content with video assets).

**Every campaign has a README.md** — the index for the campaign.  Quick links to all content files, status table, asset URLs, and a directory listing.  The README is the entry point.  The brief has the tactical plan.  The strategy (if it exists) has the long-term arc.

## Voice Rules

Always follow the relevant author's `authors/<name>/voice/voice-profile.md` when writing for them.  Company-wide guidelines are in `brand/voice-guidelines.md`.  Critical rules that apply to most authors:
- No contractions, no em dashes, two spaces after sentence-ending punctuation
- Never bury the lead
- Active voice, positive framing, no hype language
- Blog posts use flowing paragraphs, not single-line poetry style
- LinkedIn posts use short paragraphs (2-3 sentences), not one-line-per-sentence

## Publishing Patterns

- **Blog-first strategy:** Write the blog post, then write a LinkedIn promo post that drives to the blog
- **Tuesday morning cadence:** Post to LinkedIn every Tuesday at minimum
- **Open source coordination:** When a post announces an open source repo, flip the repo to public on the same day
- **LinkedIn links:** Put the link in the first comment, not the post body (algorithm penalizes links in body)
- Move LinkedIn drafts from `authors/<name>/drafts/linkedin/` to `authors/<name>/posted/linkedin/` after posting
