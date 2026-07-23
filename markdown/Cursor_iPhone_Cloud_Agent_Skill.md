# Skill: Use Cursor Cloud Agents from iPhone with GitHub Organization Repositories

## Goal

Use the Cursor iOS app to launch cloud agents that modify repositories
stored in a GitHub organization (e.g. the lab website), without needing
a Mac.

------------------------------------------------------------------------

## Key Concepts

-   **Workspace**: A Git repository opened in Cursor. One workspace
    corresponds to one Git repository.
-   **Cloud Agent / Background Agent**: An AI running in a remote cloud
    VM. It clones the repository, creates a branch, edits code, runs
    commands/tests, and prepares changes for review.

The iPhone app is primarily a control interface for cloud agents rather
than a full IDE.

------------------------------------------------------------------------

## Correct Setup

### 1. Sign in to the same Cursor account

Use the same Cursor account on both:

-   Cursor Desktop (Mac)
-   Cursor iOS

The account shares workspaces, GitHub integration, and cloud agents.

------------------------------------------------------------------------

### 2. Connect GitHub through the Cursor Dashboard

The reliable method is:

1.  Open the Cursor web dashboard.
2.  Go to **Integrations**.
3.  Connect GitHub.
4.  Choose the GitHub organization (e.g. `Peng-He-Lab`).
5.  Install/authorize the Cursor GitHub App for:
    -   All repositories, or
    -   Selected repositories (such as the lab website).

This step is preferable to searching through GitHub Organization
Settings because GitHub's UI changes frequently.

------------------------------------------------------------------------

### 3. Understand GitHub authorization

There are two separate permissions:

#### A. Authorized GitHub App

GitHub

Settings → Applications → Authorized GitHub Apps

This authorizes Cursor to act as your GitHub account.

#### B. Organization installation

The Cursor GitHub App must also be installed on the GitHub organization
and granted access to the desired repositories.

This is most easily managed from the Cursor Dashboard → Integrations.

------------------------------------------------------------------------

### 4. Verify the connection

Open the Cursor iOS app.

If the organization repository appears as an available workspace (for
example, the lab website repository), then the integration is working.

No additional GitHub configuration is usually required.

------------------------------------------------------------------------

## Typical Workflow

1.  Open Cursor on iPhone.
2.  Select the lab website workspace.
3.  Start a Background Agent.
4.  Give natural-language instructions such as:

> Update the Publications page with these new papers.

or

> Add a new lab member and update the homepage.

The cloud agent will:

-   clone the repository
-   create a working branch
-   modify files
-   run build/test commands if instructed
-   prepare a commit or pull request
-   allow review from the iPhone or later from the desktop

------------------------------------------------------------------------

## Recommended Prompt

When modifying the lab website, ask the agent to verify the site builds
successfully before finishing.

Example:

> Update the Publications page with the attached citations. Build the
> website, fix any build errors, and stop only after the build succeeds.
> Then summarize the changes.

------------------------------------------------------------------------

## Notes

-   The iPhone app is ideal for content updates, documentation, and
    website maintenance.
-   Heavy interactive coding is still easier on the desktop.
-   Cloud agents continue running even if the phone or Mac is offline.
