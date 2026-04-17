---
description: First-run setup — replace the fictional company and authors with yours
allowed-tools: Read, Write, Edit, Glob, Grep, Bash
model: sonnet
---

Walk the user through initial repo setup.  This replaces the fictional Summit Fuel company and placeholder authors with their real company and team.

Execute the following steps **interactively** — ask questions and wait for answers before proceeding.

## Step 1: Gather information

Ask the user for:

1. **Company name** — What is your company called?
2. **One-line company description** — What does the company do?  (e.g. "a sports nutrition company for endurance athletes")
3. **Authors** — Who will be writing content?  For each author, ask:
   - Name (first name or handle they publish under)
   - Title (e.g. "Co-Founder and CEO", "Head of Marketing")
   - One-sentence bio

Wait for all answers before proceeding.

## Step 2: Replace the company

Find and replace across the entire repo:
- "Summit Fuel" → their company name
- "a sports nutrition company for endurance athletes" → their company description (in voice-guidelines.md and author-bios.md)
- Update `brand/voice-guidelines.md` — keep the structure and rules, replace Summit Fuel references
- Update `CLAUDE.md` — replace any Summit Fuel references

## Step 3: Set up authors

For each author the user listed:

1. Rename an existing author directory.  Map the first author to `caesar/`, the second to `zira/`.  If they have more than two authors, create new directories following the same structure.
2. Update `brand/author-bios.md` with the real names, titles, and bios
3. Update the voice profile at `authors/<name>/voice/voice-profile.md` — replace the fictional author name but keep the template structure and "Status: Template — customize for your author" note.  The user will run `/extract-voice` next to fill it in properly.
4. Create the full directory structure for each author:
   - `authors/<name>/samples/` with the README.md explaining what to put there
   - `authors/<name>/drafts/linkedin/`
   - `authors/<name>/posted/linkedin/`
   - `authors/<name>/ideas/`
   - `authors/<name>/voice/voice-profile.md`

If there are fewer than two authors, delete the unused author directory entirely.

## Step 4: Clean example content

Delete all fictional example content:
- `corporate/drafts/blog/20260204-carb-intake-ultras.md`
- `authors/*/drafts/linkedin/carb-intake-ultras.md` (any files from the old author dirs)
- `campaigns/carb-intake-ultras/` (entire directory)

Reset `strategy/content-calendar.md` to an empty calendar — keep the structure and section headers, remove all Summit Fuel entries.

## Step 5: Update the content calendar

Update `strategy/content-calendar.md`:
- Replace author names in the Cadence Targets table
- Clear the Published, Scheduled, Unscheduled, and Blocked sections (keep headers and table structure)
- Reset the Idea Pipeline Summary with the new author names and zero counts

## Step 6: Report and next steps

Tell the user:

```
Setup complete.  Your repo is ready.

Next steps:
1. Drop existing writing into authors/<name>/samples/ for each author
2. Run /extract-voice <author> to generate voice profiles from real content
3. Start drafting with /draft-blog or /draft-linkedin
```

List every file that was modified so the user can review before committing.
