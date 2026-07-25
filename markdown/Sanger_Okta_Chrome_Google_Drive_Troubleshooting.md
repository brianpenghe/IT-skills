# Troubleshooting Chrome Opening Sanger Okta Login on macOS

## Problem

After leaving the Wellcome Sanger Institute and deleting the old Chrome
profile, Google Chrome would still occasionally open a Sanger Okta login
page, especially after restarting the computer.

The browser appeared to be trying to authenticate:

-   **Sanger Okta**
-   `ph12@sanger.ac.uk`

even though the account was no longer in use.

------------------------------------------------------------------------

## Initial hypotheses

Possible causes considered included:

-   Chrome cookies or cached sessions
-   Chrome Sync restoring old data
-   Startup pages or session restore
-   Chrome extensions
-   Enterprise policies
-   macOS MDM (device management)
-   A desktop application launching an OAuth flow

------------------------------------------------------------------------

## MDM investigation

Terminal:

``` bash
profiles status -type enrollment
profiles show
```

Results:

-   Mac enrolled in **UCSF Jamf MDM**
-   MDM server: `https://jss.ucsf.edu:8443/mdm/ServerURL`
-   No user configuration profiles installed

Conclusion:

-   The Mac is managed by **UCSF**, **not Sanger**.
-   Sanger was not managing the computer.

------------------------------------------------------------------------

## Critical clue #1: OAuth URL

The Chrome popup URL contained:

-   `https://sanger.okta.com/app/google/...`
-   `login_hint=ph12@sanger.ac.uk`
-   `redirect_uri=http://127.0.0.1:<port>`

Interpretation:

-   This is a **Google Workspace OAuth** request.
-   Google redirects Sanger accounts to **Sanger Okta**.
-   `login_hint` proves an application was explicitly requesting
    authentication for `ph12@sanger.ac.uk`.
-   `127.0.0.1` indicates a **desktop application** (installed-app OAuth
    flow), not a normal website.

Therefore:

> Chrome was **not** spontaneously opening Sanger Okta. Another local
> application was launching an OAuth login, and Chrome was simply the
> browser used to complete authentication.

------------------------------------------------------------------------

## Critical clue #2: Google Drive

Opening Google Drive for desktop showed:

-   Active account:
    -   `brianpenghe@gmail.com`
-   A second account:
    -   `ph12@sanger.ac.uk`
    -   Status: **"Loading your account..."**

This identified the real source.

Google Drive was still attempting to initialize the old Sanger Google
Workspace account.

Authentication chain:

``` text
Google Drive
      ↓
Google OAuth
      ↓
login_hint = ph12@sanger.ac.uk
      ↓
Google Workspace (Sanger)
      ↓
Sanger Okta
      ↓
Chrome popup
```

------------------------------------------------------------------------

## Root cause

A **stale Google Drive for desktop account** remained configured.

At every startup, Google Drive attempted to authenticate all configured
accounts.

Because the old account belonged to Sanger Google Workspace, Google
redirected authentication through **Sanger Okta**, which opened in
Chrome.

The issue was **not** caused by:

-   Chrome profiles
-   Chrome cookies
-   Chrome Sync
-   UCSF MDM
-   Sanger managing the Mac

------------------------------------------------------------------------

## Resolution

In Google Drive:

1.  Open **Settings / Preferences**
2.  Disconnect the account:
    -   `ph12@sanger.ac.uk`
3.  Allow Google Drive to copy any remaining unsynced files to a local
    folder.
4.  Restart the computer.
5.  Verify that Google Drive now contains only the desired Google
    account.

Expected result:

-   Google Drive no longer requests authentication for the Sanger
    account.
-   Chrome no longer opens the Sanger Okta login page.

------------------------------------------------------------------------

## Diagnostic lessons

When an Okta login page appears unexpectedly:

1.  Inspect the full URL.
2.  Look for:
    -   `login_hint`
    -   `redirect_uri`
3.  If the redirect URI is `127.0.0.1`, suspect a desktop application
    rather than the browser.
4.  Determine which application is initiating OAuth.
5.  Check Google Drive, cloud sync clients, IDEs, or other
    Google-integrated desktop software before blaming Chrome itself.

------------------------------------------------------------------------

## Useful commands

### Check macOS MDM

``` bash
profiles status -type enrollment
profiles show
```

### Check Chrome enterprise status

    chrome://management
    chrome://policy

### Identify localhost OAuth listener (while popup is active)

``` bash
lsof -iTCP:<PORT> -sTCP:LISTEN
```

Replace `<PORT>` with the port shown in the OAuth redirect URI.

------------------------------------------------------------------------

## Final conclusion

The Sanger Okta popup was caused by **Google Drive for desktop retaining
a stale Sanger Google Workspace account**, not by Chrome or macOS
management. Removing that account from Google Drive resolved the
authentication attempts.
