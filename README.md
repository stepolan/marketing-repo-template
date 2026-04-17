# Marketing Content Repo Template

A system for running marketing content through Claude Code (or any AI coding tool).  Blog posts, LinkedIn drafts, social media, campaign briefs, voice profiles, and content calendar.  All markdown.  All version controlled.  All AI-assisted.

## Why This Exists

Marketing content is just files.  Once you treat it that way, every tool that works on code works on content.  Git for version history.  PRs for review.  Commands for repeatable workflows.  Claude Code for the intelligence layer on top.

This repo is a template.  It includes the directory structure, Claude Code commands, per-author voice profiles, a content calendar, and an example campaign with placeholder content.  Fork it, replace the fictional company with yours, and start writing.

## What Is Included

```
.claude/
  commands/
    setup.md               # First-run setup — replace fictional company with yours
    extract-voice.md       # Analyze existing content and generate a voice profile
    draft-blog.md          # Scaffold a blog post with voice and structure
    draft-linkedin.md      # Draft a LinkedIn post for an author
    voice-check.md         # Check any draft against the voice profile
    content-status.md      # Scan all content and report status
    review-content.md      # Full brand alignment review

corporate/
  drafts/blog/             # Blog posts (YYYYMMDD-slug.md)
  ideas/                   # Corporate idea backlog

authors/
  caesar/                  # One directory per author
    samples/               # Drop existing writing here for voice extraction
    drafts/linkedin/       # LinkedIn drafts
    posted/linkedin/       # Published posts (moved here after posting)
    ideas/                 # Idea backlog
    voice/
      voice-profile.md     # Author's writing voice rules
  zira/
    samples/
    drafts/linkedin/
    voice/
      voice-profile.md

campaigns/
  carb-intake-ultras/
    README.md              # Campaign index (every campaign gets one)
    brief.md               # Tactical plan, content pieces, schedule
    assets/                # Shared media (images, video, diagrams)

brand/
  voice-guidelines.md      # Company-wide voice guidelines
  author-bios.md           # Source of truth for author bios and titles

strategy/
  content-calendar.md      # What is published, scheduled, and in progress

website/
  knowledge-base/          # AEO articles for LLM discoverability

CLAUDE.md                  # Instructions for Claude Code
```

## How It Works

### 1. Per-Author Voice Profiles

Each author has their own directory under `authors/` with a voice profile.  Different authors write differently.  The CEO's voice is not the scientist's voice.  The template includes two example authors to show the pattern.

To build a voice profile, drop 10+ pieces of existing writing into `authors/<name>/samples/` and run `/extract-voice <author>`.  Claude reads everything and generates the profile for you.

### 2. Commands

Run these from Claude Code:

- `/setup` — First-run setup.  Asks for your company name and authors, replaces all fictional content, and sets up your directory structure
- `/extract-voice [author]` — Reads an author's existing content and generates a voice profile from it
- `/draft-blog [author] [topic]` — Scaffolds a blog post with frontmatter, voice rules loaded, and structure
- `/draft-linkedin [author] [topic]` — Drafts a LinkedIn post
- `/voice-check [file]` — Checks a draft against the voice profile, flags violations with line numbers
- `/content-status` — Scans all directories and reports what is published, drafted, and in progress
- `/review-content [file]` — Full brand alignment review (voice, lead quality, proof points, pillar mapping)

### 3. Campaigns

When a topic produces more than one piece of content, create a campaign directory:

```
campaigns/my-campaign/
  README.md    # Index: links to all content, asset URLs, status
  brief.md     # Tactical plan: dates, channels, content pieces, dependencies
  assets/      # Shared media
```

Every content file that belongs to a campaign gets `**Campaign:** my-campaign` in its frontmatter.  Find everything for a campaign with `grep -r "Campaign: my-campaign"`.

### 4. Content Calendar

`strategy/content-calendar.md` is the source of truth.  Published content with dates and URLs, scheduled content with dependencies, unscheduled drafts, and the idea pipeline.

### 5. Publishing Flow

1. Draft in the appropriate directory
2. Run `/voice-check` to catch violations
3. Run `/review-content` for full brand review
4. PR for human review (optional, depends on team size)
5. Move LinkedIn posts from `authors/<name>/drafts/` to `authors/<name>/posted/` after publishing
6. Update the content calendar

## Getting Started

1. Fork this repo and open it in Claude Code
2. Run `/setup` — it asks for your company name, authors, and bios, then replaces all the fictional content and sets up your directory structure
3. Drop each author's existing writing into `authors/<name>/samples/` — blog posts, LinkedIn posts, newsletters, whatever you have.  More is better.  10+ pieces per author is ideal.
4. Run `/extract-voice <author>` for each author — Claude reads all the samples and generates a voice profile
5. Review the generated profile, adjust anything that is off, and approve it
6. Start writing with `/draft-blog` or `/draft-linkedin`

## The Fictional Company

This template uses **Summit Fuel**, a fictional sports nutrition company for endurance athletes, as placeholder content.  Two co-founders: Caesar (CEO, former ultra-marathoner) and Zira (Chief Science Officer, PhD in exercise physiology).  The company, the authors, and all content are fictional.  Replace everything with your own.

The author names are intentionally drawn from Planet of the Apes characters so nothing looks tied to any real person or brand.

## License

MIT
