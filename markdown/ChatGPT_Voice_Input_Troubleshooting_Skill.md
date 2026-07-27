# Skill: Troubleshooting ChatGPT Voice Input (Waveform Appears but No Transcription)

## Purpose

Diagnose cases where ChatGPT detects microphone input (voice waveform is
visible) but fails to produce transcribed text after the user finishes
speaking.

------------------------------------------------------------------------

## Initial Symptoms

-   Voice waveform animates while speaking.
-   Clicking **Finish** produces no text.
-   No error message appears.
-   Device microphone works in other applications.

------------------------------------------------------------------------

## Decision Tree

### Step 1. Verify microphone hardware

Check whether the operating system can perform speech recognition.

**Pass examples** - macOS Dictation - Windows Voice Typing - iPhone
Dictation

If these work:

-   Microphone hardware is functioning.
-   OS permissions are likely correct.

------------------------------------------------------------------------

### Step 2. Verify browser microphone access

If ChatGPT displays the voice waveform:

-   Browser microphone permission is working.
-   Audio is reaching ChatGPT.

Therefore do **not** continue troubleshooting microphone permissions.

------------------------------------------------------------------------

### Step 3. Eliminate browser cache/extensions

Test in:

-   Chrome Incognito
-   Browser with extensions disabled

If the problem persists:

-   Browser extensions are unlikely to be responsible.

------------------------------------------------------------------------

### Step 4. Eliminate browser-specific issues

Test another browser.

Example:

-   Chrome
-   Safari

Interpretation:

  Result                      Interpretation
  --------------------------- ------------------------
  Works in one browser only   Browser-specific issue
  Same failure in both        Not browser-specific

------------------------------------------------------------------------

### Step 5. Test another device

Example:

-   iPhone ChatGPT app

Possible outcomes:

-   Works → desktop-specific issue.
-   Same failure → account/workspace/backend likely.

------------------------------------------------------------------------

### Step 6. Observe any error codes

If iOS reports:

    429 Too Many Requests

Interpretation:

Possible causes include:

1.  Voice usage quota reached.
2.  Temporary account rate limit.
3.  Organization (Edu/Enterprise) quota.
4.  Backend service limiting voice requests.

------------------------------------------------------------------------

### Step 7. Consider managed workspace

If using an institutional account (e.g. UCSF ChatGPT Edu/Enterprise):

Possible causes include:

-   Workspace feature configuration.
-   Workspace voice quota.
-   Account-specific backend issue.

------------------------------------------------------------------------

## Evidence Collected During This Case

Observed:

-   macOS Dictation works.
-   ChatGPT waveform responds normally.
-   Chrome fails.
-   Chrome Incognito fails.
-   Safari fails.
-   iOS ChatGPT returns **429 Too Many Requests**.
-   Failure occurs after recording rather than before recording.

------------------------------------------------------------------------

## Diagnostic Conclusion

Most likely causes (highest confidence first):

1.  Account-level voice rate limiting (429).
2.  Workspace (Edu/Enterprise) voice quota or configuration.
3.  Backend account-specific issue.

Unlikely causes:

-   Broken microphone.
-   macOS permissions.
-   Chrome extensions.
-   Browser cache.
-   Browser-specific compatibility.

------------------------------------------------------------------------

## Recommended Next Actions

1.  Wait for the rate limit window to expire (minutes to several hours;
    if persistent, try the next day).
2.  Retry voice.
3.  Verify whether only voice fails while normal text chat still works.
4.  If using an institutional workspace, contact the workspace
    administrator.
5.  Contact OpenAI Support and report:

> Voice recording succeeds (waveform visible), but transcription never
> begins. The issue reproduces on Chrome, Chrome Incognito, Safari, and
> the iOS ChatGPT app. The iOS app reports HTTP 429 ("Too Many
> Requests"). macOS Dictation functions normally, indicating the
> microphone is working.

------------------------------------------------------------------------

## Key Diagnostic Insight

If the waveform is visible, the microphone pipeline is functioning.

The failure is occurring **after audio capture**, during upload,
transcription, authorization, quota enforcement, or backend processing.
