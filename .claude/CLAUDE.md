# .claude/ — Claude Code Configuration

This directory holds the Claude Code commands and (optionally) custom skills for this repo.  The project-level guidance for working with the content lives in the root [`CLAUDE.md`](../CLAUDE.md) — read that first.

## First Run

If this is a fresh clone, run:

```
/setup
```

It asks for your company name, authors, and bios, then replaces the fictional Summit Fuel content (Caesar, Zira) with your own and wires up the directory structure.

## Available Commands

All commands live in [`commands/`](commands/) and are invoked from Claude Code with a leading slash:

| Command | Purpose |
|---------|---------|
| `/setup` | First-run setup.  Replaces fictional content with yours. |
| `/extract-voice [author]` | Reads `authors/<name>/samples/` and generates a voice profile. |
| `/draft-blog [author] [topic]` | Scaffolds a blog post with frontmatter and voice loaded. |
| `/draft-linkedin [author] [topic]` | Drafts a LinkedIn post for the named author. |
| `/voice-check [file]` | Checks a draft against the voice profile, flags violations. |
| `/content-status` | Scans all directories and reports what is published, drafted, in progress. |
| `/review-content [file]` | Full brand alignment review (voice, lead, proof points, pillar). |

## Custom Skills

[`skills/`](skills/) is empty by default.  Drop your own skill folders here if you want to extend the repo with reusable capabilities (e.g., a publishing workflow, a competitor scan, a newsletter formatter).  See the [Claude Code skills docs](https://docs.claude.com/claude-code) for the file format.

## Where Things Live

- Project-wide instructions for Claude: root [`CLAUDE.md`](../CLAUDE.md)
- Content calendar: [`strategy/content-calendar.md`](../strategy/content-calendar.md)
- Author voice profiles: `authors/<name>/voice/voice-profile.md`
- Brand voice (cross-author): [`brand/voice-guidelines.md`](../brand/voice-guidelines.md)
