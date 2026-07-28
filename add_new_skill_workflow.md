# Skill: Add a New Skill to the IT-skills Repository

## Goal

When the user asks to **include** / **add** a newly downloaded skill markdown
file (usually from `~/Downloads/`) into the **IT-skills** GitHub repo, follow
this workflow. Skills live in `markdown/`; this meta-skill stays at the **repo
root**.

------------------------------------------------------------------------

## Trigger phrases

Typical user requests:

-   “include the … skill in my Downloads/ folder”
-   “please include the newly downloaded … skill”
-   “add this skill to IT-skills”

Interpretation: find the matching `.md` in Downloads, copy it into
`markdown/`, update the catalog README, then **ask** before commit/push
unless the user already said to commit/push (e.g. “yes”).

------------------------------------------------------------------------

## Do / don’t

**Do**

-   Add the file under `markdown/` in the IT-skills repo
  (`https://github.com/brianpenghe/IT-skills`).
-   Keep the original filename from Downloads when possible.
-   Update `README.md` catalog and **Last updated** date.
-   Wait for an explicit “yes” / “commit” / “push” before committing,
    unless the same message already asks to commit and push.

**Don’t**

-   Install the file as a personal Cursor skill under `~/.cursor/skills/`
    unless the user explicitly asks to install it in Cursor.
-   Rewrite or heavily edit the skill body; copy the downloaded content
    as-is (minor path/link fixes only if needed).
-   Put ordinary troubleshooting skills at the repo root; only this
    add-skill workflow (and similar repo meta docs) belong at the parent
    level.

------------------------------------------------------------------------

## Step-by-step workflow

### 1. Locate the downloaded skill

In `~/Downloads/`, find the newest matching markdown by name keywords
(e.g. Okta, ChatGPT, Google Maps, Voice). Prefer the most recently
modified file when several match.

Confirm by reading the title / first lines so the README blurb is accurate.

### 2. Copy into `markdown/`

```bash
cp ~/Downloads/<Skill_File>.md markdown/<Skill_File>.md
```

Use the same basename as in Downloads unless the user renames it.

### 3. Update `README.md`

1.  Set **Last updated:** to today’s date.
2.  Add a catalog row under the best existing section, **or** create a
    new `### Section` if none fits (examples from past adds: Cursor,
    ChatGPT, macOS, Google).
3.  Row format (match existing tables):

| Skill | File | What it covers |
|-------|------|----------------|
| Short title | [`filename.md`](markdown/filename.md) | One-line summary of the goal |

Write the summary from the skill’s Goal / Purpose / Problem section.

### 4. Confirm with the user

After the file and README are updated, ask:

> Want me to commit and push?

Unless they already requested commit/push in the same turn.

### 5. Commit and push (only when asked)

Match existing commit style:

```text
Add <short skill name> skill and update README.
```

Then:

1.  `git status` / `git diff` / recent `git log` (repo style check)
2.  Stage `README.md` and the new `markdown/*.md` only
3.  Commit with a HEREDOC message
4.  `git push` to `origin` `main`
5.  Return the repo URL: https://github.com/brianpenghe/IT-skills

------------------------------------------------------------------------

## Catalog section guidance

Choose or create a section by topic, not by source app alone:

| Topic | Examples already in README |
|-------|----------------------------|
| iOS / Apple | App Store logout, contacts sync |
| Cursor | iPhone cloud agents |
| ChatGPT | Voice input troubleshooting |
| macOS | Night Shift, Sanger Okta / Chrome |
| Google | Maps work address, Maps reviews |
| Douyin / 抖音 | 异地开播考试 |
| Desktop / Hardware | Mouse right-click |
| OCR / Digitization | 古籍 PDF OCR |
| GitHub | Org custom properties |
| Automation / Workflows | Job email pipeline |

If unsure, pick the closest section or add a short new heading.

------------------------------------------------------------------------

## Quick checklist

-   [ ] Skill found in `~/Downloads/`
-   [ ] Copied to `markdown/` (original name preserved)
-   [ ] README row + section (new section if needed)
-   [ ] **Last updated** date bumped
-   [ ] User approved commit/push
-   [ ] Commit message: `Add … skill and update README.`
-   [ ] Pushed to `main`

------------------------------------------------------------------------

## Related

-   Human-facing short version also listed at the bottom of
    [README.md](README.md) under **Adding a new skill**.
-   Individual troubleshooting skills: [markdown/](markdown/).
