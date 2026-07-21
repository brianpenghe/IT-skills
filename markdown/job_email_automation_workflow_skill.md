# Job Email Automation Workflow
**Version:** 1.0  
**Purpose:** Automatically ingest job subscription emails, convert them into structured text files, and make them available for an AI agent (Cursor) to process and update a GitHub repository.

---

# Goal

Automate the workflow:

```
Job Subscription Email
        ↓
Outlook
        ↓
Power Automate
        ↓
OneDrive Folder
        ↓
Local Sync / Git Repository
        ↓
Cursor AI Agent
        ↓
GitHub Repository
```

The objective is to eliminate manual copy/paste of job emails while maintaining a reliable, reproducible pipeline.

---

# Why Outlook Instead of Gmail?

Originally, the job subscriptions were delivered to Gmail.

Although Gmail can be automated, Outlook integrates directly with Microsoft Power Automate, making the workflow significantly simpler and more reliable.

Recommended approach:

- Subscribe using the Outlook email address directly.
- Avoid forwarding from Gmail whenever possible.
- This preserves the original sender information and reduces complexity.

---

# Power Automate Workflow

## Trigger

Use:

```
When a new email arrives (V3)
```

Configure:

- Folder: Inbox (or a dedicated Jobs folder)
- Filter by sender:

```
noreply@jobmail.naturecareers.com
reply@sciencecareers.org
```

Only emails from these addresses will trigger the automation.

---

## Action 1 – HTML to Text

Add:

```
HTML to text
```

Configuration:

Content:

```
Body
```

(using Dynamic Content)

Purpose:

- Remove HTML formatting.
- Produce clean plain text for downstream AI processing.

---

## Action 2 – Create File

Use:

```
Create file (OneDrive)
```

Folder:

```
/Documents/Bio-Jobs-Inbox
```

### File Name

Use:

```
Message Id.txt
```

This guarantees uniqueness and avoids filename collisions.

### File Content

```
=== EMAIL START ===

DATE:
[Received Time]

SOURCE_ID:
[Message Id]

CONTENT:

[Plain text from HTML to text]

=== EMAIL END ===
```

Insert all fields using **Dynamic Content**.

Do **not** manually type Power Automate expressions.

---

## Action 3 – Delete or Move Email

Option A:

```
Delete email (V2)
```

Message Id:

```
Message Id
```

Option B (recommended during testing):

```
Move email
```

Destination:

```
Processed
```

This provides a recovery buffer while validating the workflow.

---

# Repository Structure

Recommended layout:

```
repo/
│
├── inbox/
│     raw email files
│
├── processed/
│     archived email files
│
├── jobs.json
│
└── README.md
```

If using OneDrive synchronization:

```
OneDrive
      ↓
repo/inbox
```

Either:

- place the repository inside OneDrive

or

- create a symbolic link from the OneDrive folder into the repository.

---

# Cursor AI Agent

Important concept:

Cursor is **not** an email receiver.

Cursor is **not** a background watcher.

Cursor is the **processing engine**.

Recommended instruction:

```
Scan every file inside /inbox.

For each file:

- Extract job information.
- Normalize fields.
- Avoid duplicates using SOURCE_ID.
- Update jobs.json.
- Move processed files into /processed.
```

---

# Suggested Data Schema

Use a consistent structure.

Example:

```json
{
  "source_id": "",
  "company": "",
  "role": "",
  "location": "",
  "link": "",
  "deadline": "",
  "date_added": ""
}
```

Keeping a stable schema prevents repository drift.

---

# Current Automation Level

Current pipeline:

```
Email
    ↓
Power Automate
    ↓
Plain-text file
```

Processing:

```
Plain-text file
    ↓
Cursor
    ↓
GitHub
```

At present, Cursor is expected to be manually invoked.

---

# Possible Future Improvements

## 1. Automatic File Watching

Instead of manually running Cursor:

```
File appears
        ↓
Watcher Script
        ↓
Launch Cursor
```

---

## 2. Fully Automated Repository Updates

```
Email
    ↓
Power Automate
    ↓
File
    ↓
Watcher
    ↓
Parsing Script
    ↓
Git Commit
    ↓
GitHub
```

This removes the need for manual Cursor execution.

---

# Common Power Automate Lessons Learned

- Use **Dynamic Content** instead of manually typing expressions.
- Configure **HTML to text** before referencing its output.
- Use **Message Id** as the filename to avoid collisions.
- Rebuilding a broken step is often faster than repairing corrupted references.
- HTML-to-text conversion produces cleaner AI input than raw HTML.
- During testing, moving emails is safer than immediately deleting them.

---

# Best Practices

- Subscribe with Outlook directly whenever possible.
- Keep the raw email archive until the pipeline is stable.
- Use unique IDs (Message Id / SOURCE_ID) for deduplication.
- Separate ingestion (Power Automate) from processing (Cursor).
- Maintain a consistent schema for extracted job data.
- Test with a small number of emails before enabling automatic deletion.

---

# Final Architecture

```
Job Subscription
        ↓
Outlook
        ↓
Power Automate
        ↓
HTML → Plain Text
        ↓
OneDrive
        ↓
Repository Inbox
        ↓
Cursor AI Agent
        ↓
Structured Job Database
        ↓
GitHub
```

---

# Key Design Principle

Separate the pipeline into distinct stages:

1. **Ingestion**
   - Outlook
   - Power Automate

2. **Storage**
   - OneDrive
   - Repository inbox

3. **Processing**
   - Cursor AI Agent

4. **Publishing**
   - GitHub

Keeping each stage independent makes the system easier to maintain, debug, and extend.
