---
name: connect-private-github-repo
description: Connect and verify private GitHub repository access through the ChatGPT Codex Connector. Use when Codex can authenticate a GitHub user but cannot find a private repository, returns 404 for a known repository, lists zero repositories, or needs to install the connector on the correct personal or organization account.
---

# Connect a Private GitHub Repository

Connect the GitHub identity, install the ChatGPT Codex Connector on the repository owner, grant repository access, and verify the result through the GitHub plugin.

## Core distinction

Treat authorization and installation as separate requirements:

- **Authorization** identifies the GitHub user and appears under **Authorized GitHub Apps**.
- **Installation** grants the connector access to repositories owned by a personal account or organization and appears under **Installed GitHub Apps**.

Do not assume successful authentication provides access to private repositories. A connector can identify the correct user while returning zero repositories because it is installed only on other accounts.

## Connect and install

1. Invoke the GitHub plugin with `@github` and complete GitHub sign-in.
2. Confirm the authenticated GitHub username matches the intended user.
3. Open the direct installation page:
   `https://github.com/apps/chatgpt-codex-connector/installations/new`
4. Select the personal account or organization that owns the repository.
5. Choose **All repositories** or **Only select repositories**.
6. When selecting individual repositories, include the target private repository.
7. Select **Install**. If an organization requires approval, ask an organization owner to approve the installation.

Install the connector separately for every repository owner that Codex must access. Authorizing the app once does not install it on every personal account or organization available to the user.

## Verify access

Use the GitHub plugin to perform all of these checks:

1. Retrieve the authenticated profile.
2. List GitHub App installations and confirm the repository owner's login is present.
3. List or search accessible repositories.
4. Fetch the target repository by exact `owner/name`.
5. Report its visibility, default branch, and effective permissions.

Consider the connection verified only when the direct repository lookup succeeds. Do not treat identity authentication alone as proof of repository access.

## Diagnose failures

### Known repository returns 404

1. Confirm the exact repository URL opens for the user while signed into GitHub.
2. Confirm spelling, capitalization, and the `owner/name` pair.
3. Confirm the connector installation list includes that owner.
4. Confirm the installation includes the target repository.
5. Retry the direct repository lookup after installation changes.

### Correct user but zero repositories

List connector installations. If only unrelated accounts appear, install the connector on the correct owner using the direct installation page. Reauthorizing the same identity is insufficient.

### App appears only under Authorized GitHub Apps

This proves user authorization, not repository installation. Use the direct installation page rather than searching that authorization details page for a Configure button.

### Organization repository remains unavailable

Confirm the connector is installed on the organization itself, not only the user's personal account. Check organization approval policies and request owner approval when required.

## Safety

- Prefer **Only select repositories** when broad access is unnecessary.
- Do not request tokens, passwords, or private keys.
- Do not revoke a working authorization merely to add another installation; install the connector on the additional owner instead.
- Treat connector write permissions separately from authorization to inspect a repository. Confirm the user's intent before changing repository content, issues, pull requests, or settings.

## Completion report

State:

- Authenticated GitHub identity
- Installed owner account or organization
- Verified repository `owner/name`
- Private or public visibility
- Default branch
- Effective read/write permissions

If verification fails, identify the exact missing layer: identity authorization, owner installation, repository selection, organization approval, or repository-name mismatch.
