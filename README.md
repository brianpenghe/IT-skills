# IT Skills

This repository is a collection of my troubleshooting skills, stored as Markdown files.

You are welcome to browse the [markdown](markdown/) folder and use AI tools to help solve problems similar to ones I have already worked through.

**Last updated:** August 3, 2026

> **Date caveat:** Prefer the curated skills listed below. An additional
> **729 historical Blogger notes** (mostly 2013–2022) live under
> [markdown/archive/blogger-published-notes/](markdown/archive/blogger-published-notes/).
> Each archived note is stamped with its original creation date—many are
> outdated; take them with a grain of salt.

## Skills in this repo

### iOS / Apple

| Skill | File | What it covers |
|-------|------|----------------|
| App Store account switching | [iOS-store-logout.md](markdown/iOS-store-logout.md) | Sign out of one regional Apple ID and sign into another on Media & Purchases without changing iCloud or device region |
| iPhone contacts Gmail sync bug | [iphone_contacts_gmail_sync_bug_fix.md](markdown/iphone_contacts_gmail_sync_bug_fix.md) | Blank or wrong contact cards caused by Gmail sync / suggested-contact cache; fix via Google Contacts cleanup and cache refresh |

### Cursor

| Skill | File | What it covers |
|-------|------|----------------|
| Cloud agents from iPhone | [Cursor_iPhone_Cloud_Agent_Skill.md](markdown/Cursor_iPhone_Cloud_Agent_Skill.md) | Use Cursor iOS cloud agents on GitHub organization repos (e.g. lab website) via dashboard Integrations and the same Cursor account |
| Workspace custom color theme | [workspace-custom-color-theme-consensus-skill.md](markdown/workspace-custom-color-theme-consensus-skill.md) | Tint one Cursor/VS Code workspace (title bar, sidebar, editor, terminal) via `.code-workspace` or `.vscode/settings.json` without changing global settings |

### ChatGPT

| Skill | File | What it covers |
|-------|------|----------------|
| Voice input troubleshooting | [ChatGPT_Voice_Input_Troubleshooting_Skill.md](markdown/ChatGPT_Voice_Input_Troubleshooting_Skill.md) | Diagnose ChatGPT voice waveform with no transcription after speaking |

### macOS

| Skill | File | What it covers |
|-------|------|----------------|
| Night Shift | [macos-night-shift-skill.md](markdown/macos-night-shift-skill.md) | Enable Night Shift on macOS to reduce blue light and eye strain, including setup for external monitors |
| Sanger Okta / Chrome / Google Drive | [Sanger_Okta_Chrome_Google_Drive_Troubleshooting.md](markdown/Sanger_Okta_Chrome_Google_Drive_Troubleshooting.md) | Stop Chrome from opening leftover Sanger Okta login after leaving the institute and removing the old Chrome profile |

### Google

| Skill | File | What it covers |
|-------|------|----------------|
| Google Maps work address | [google_maps_work_address_ios_skill.md](markdown/google_maps_work_address_ios_skill.md) | Update the saved Work address in Google Maps on iPhone |
| Google Maps reviews export | [google_maps_reviews_skill.md](markdown/google_maps_reviews_skill.md) | Export place reviews via Google Takeout (Maps your places) and convert JSON to readable CSV/Excel |

### Douyin / 抖音

| Skill | File | What it covers |
|-------|------|----------------|
| 异地开播考试 | [Douyin_异地开播考试_Skill_v2.md](markdown/Douyin_异地开播考试_Skill_v2.md) | Verified answers and question patterns for the remote live-streaming compliance exam |

### RedNote / 小红书

| Skill | File | What it covers |
|-------|------|----------------|
| Portfolio / Album | [RedNote_Portfolio_Album_Skill.md](markdown/RedNote_Portfolio_Album_Skill.md) | Create a Portfolio (合集) in English RedNote; clarifies Portfolio vs Collection terminology |

### Desktop / Hardware

| Skill | File | What it covers |
|-------|------|----------------|
| Mouse right-click fix | [mouse_right_click_troubleshooting_skill.md](markdown/mouse_right_click_troubleshooting_skill.md) | Restore right-click by reconnecting the USB mouse receiver; clears temporary USB/HID communication glitches |

### OCR / Digitization

| Skill | File | What it covers |
|-------|------|----------------|
| 古籍 PDF OCR 与校勘 | [SKILL_古籍PDF_OCR_校勘_SearchablePDF_Workflow.md](markdown/SKILL_古籍PDF_OCR_校勘_SearchablePDF_Workflow.md) | Workflow for classical Chinese PDF OCR, proofreading, and searchable PDF generation with Cursor Agent, PaddleOCR, and ChatGPT |

### GitHub

| Skill | File | What it covers |
|-------|------|----------------|
| Organization custom properties | [GitHub_Organization_Custom_Properties_Skill.md](markdown/GitHub_Organization_Custom_Properties_Skill.md) | Classify and search organization repositories using GitHub Custom Properties |

### Automation / Workflows

| Skill | File | What it covers |
|-------|------|----------------|
| Job email automation | [job_email_automation_workflow_skill.md](markdown/job_email_automation_workflow_skill.md) | Pipeline from Outlook job emails through Power Automate and OneDrive to Cursor processing and GitHub |

### Archived Blogger notes (historical)

Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`. **Not curated**—kept for search/history.

| Resource | Link | What it covers |
|----------|------|----------------|
| Archive overview + age bands | [archive/blogger-published-notes/README.md](markdown/archive/blogger-published-notes/README.md) | Why dates matter; counts by age |
| Full dated index | [archive/blogger-published-notes/INDEX.md](markdown/archive/blogger-published-notes/INDEX.md) | All 729 notes sorted by original creation date |
| Notes | [archive/blogger-published-notes/notes/](markdown/archive/blogger-published-notes/notes/) | Individual stamped markdown files |

## Adding a new skill

For the full agent/human workflow (Downloads → `markdown/` → README →
commit/push), see [add_new_skill_workflow.md](add_new_skill_workflow.md)
at the repo root.

Short version:

1. Add the `.md` file to [markdown](markdown/).
2. Add a row to the appropriate section above (or create a new section if needed).
3. Update the **Last updated** date at the top of this README.
4. Commit and push only when asked (typical message: `Add … skill and update README.`).

