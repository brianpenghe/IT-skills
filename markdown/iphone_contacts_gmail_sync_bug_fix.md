# iPhone Contacts Bug: Gmail Sync / Suggested Contact Cache Issue

**Date resolved:** July 2026  
**Main symptom:** Some iPhone contacts could be searched, but tapping them opened a blank card, the wrong person, or the previously opened contact.  
**Final resolution:** The affected contact came from **All Gmail Personal**, not iCloud. Cleaning/merging it in Google Contacts, then forcing the iPhone to discard and re-download the Gmail contact cache resolved the problem.

---

## 1. What was happening

The iPhone Contacts app was not completely broken. The problem was limited to certain contacts.

Observed symptoms included:

- New contacts sometimes did not seem to save correctly.
- Searching for a person found the name, but tapping the result did not open that person.
- Sometimes tapping a search result opened the previously viewed contact.
- Sometimes the result opened a blank white page with only an **Edit** button.
- Tapping **Edit** on the blank card showed no name, phone number, email, or other fields.
- Some contacts worked normally, while others were broken.
- Manually recreating the same person as a new contact worked correctly.

The most important clue was that the broken contact appeared under:

> **Contacts > Lists > All Gmail Personal**

That showed the problematic record was coming from the Google/Gmail contact source, not from iCloud.

---

## 2. Likely cause

The most likely cause was a **corrupted or stale Gmail-synced contact record** on the iPhone.

More specifically, the iPhone likely had one or more of these:

1. A stale local copy of an old Google contact.
2. A duplicate Google contact that had been merged on the Google side but not refreshed correctly on the iPhone.
3. A malformed contact or contact pointer created from Gmail/Siri suggestions.
4. A cached iPhone Contacts index that still pointed to the pre-merge or broken version.

So the bug was not simply “Contacts app is broken.” It was more like:

> Google Contacts had been cleaned or merged, but the iPhone was still holding onto an outdated Gmail contact cache.

This explains why the contact could appear in search but fail to open correctly.

---

## 3. What was ruled out

### Not primarily an iCloud problem

The broken person could not be found at **iCloud.com/contacts**. That strongly suggested the bad record was not stored in iCloud.

### Not a general iPhone hardware problem

Other contacts opened normally, and recreating the contact manually fixed that person. This made a general hardware or total Contacts database failure unlikely.

### Not fixed by UI-only tricks

Restarting helped only partially. Region/language changes, display/transparency changes, and other UI-level tricks were not the true fix because the root issue was the Gmail contact source/cache.

---

## 4. Final fix that worked

The successful approach was:

1. Identify that the broken contact was in **All Gmail Personal**.
2. Merge or clean the duplicate records in **Google Contacts**.
3. Force the iPhone to remove the stale Gmail contact cache.
4. Re-enable Gmail Contacts so the iPhone downloads a fresh copy.

### Exact iPhone steps

Go to:

```text
Settings > Apps > Contacts > Contacts Accounts > Gmail Personal
```

Then:

1. Turn **Contacts** off.
2. When prompted, choose:

```text
Delete from My iPhone
```

This removes the stale Gmail-synced contacts from the iPhone. It does not delete the contacts from Google.

3. Restart the iPhone.
4. Go back to the same Gmail Personal account settings.
5. Turn **Contacts** back on.
6. When prompted about existing local contacts, choose:

```text
Keep existing local contacts
```

This preserves local-only contacts and the manually recreated clean contact, while allowing Gmail contacts to sync back freshly.

---

## 5. Important prompt choices

The choices matter.

### When turning Gmail Contacts OFF

Choose:

```text
Delete from My iPhone
```

Reason: this clears the stale local Gmail contact cache from the iPhone.

### When turning Gmail Contacts back ON

Choose:

```text
Keep existing local contacts
```

Reason: this protects any local-only contacts or manually recreated clean contacts already on the phone.

---

## 6. How to diagnose this in the future

If the iPhone opens the wrong contact, a blank contact, or the previous contact, do not immediately assume all Contacts are corrupted.

Use this diagnostic path:

### Step 1: Check whether the issue affects all contacts or only some

- If all contacts are broken, it may be an iOS-wide Contacts or sync issue.
- If only some contacts are broken, suspect a specific account/source or a malformed record.

### Step 2: Check Contacts Lists

Open:

```text
Contacts > Lists
```

Then inspect each source separately:

- iCloud
- Gmail Personal
- Exchange / Outlook / work account
- Yahoo or other accounts
- On My iPhone, if present

Search for the broken person inside each list individually.

The list where the broken person appears is the source that needs fixing.

### Step 3: Check the web source

If the contact is under iCloud:

```text
iCloud.com/contacts
```

If the contact is under Gmail:

```text
Google Contacts
```

If the contact is under Exchange/Outlook/work:

```text
Outlook / People / institutional webmail contacts
```

Clean, merge, or delete the bad record from the source account when possible.

### Step 4: Resync only the bad account

Do not wipe all contacts unless necessary. Turn Contacts off/on only for the bad account.

For Gmail:

```text
Settings > Apps > Contacts > Contacts Accounts > Gmail Personal
```

Then turn Contacts off, delete from iPhone, restart, and turn Contacts back on.

---

## 7. Preventing recurrence

### Prefer manual creation for important contacts

If a contact is important, create it manually rather than relying on Siri/Gmail suggested contact chips.

### Check Google “Other contacts”

Google can store people in **Other contacts** based on interactions. A duplicate may hide there even after the main contact was merged.

Search by:

- Name
- Email address
- Phone number
- Partial phone number
- Alternate spelling

### Avoid blindly merging everything on iPhone

Do not use **Merge All** on the iPhone unless you are sure the duplicates are clean. A bad blank/suggested/stale card may get linked to a good contact.

### Set the default account intentionally

On iPhone, check:

```text
Settings > Apps > Contacts > Default Account
```

Choose the account where you actually want new contacts to be stored, such as iCloud or Gmail Personal.

---

## 8. Practical decision tree

```text
Problem: Contact search result opens blank/wrong/previous person

1. Does this happen to all contacts?
   - Yes -> Restart iPhone, update iOS, consider broader Contacts reset.
   - No -> Continue.

2. Which list contains the broken contact?
   - iCloud -> Fix/delete at iCloud.com/contacts, then resync iCloud Contacts.
   - Gmail Personal -> Fix/merge/delete in Google Contacts, then resync Gmail Contacts on iPhone.
   - Exchange/work -> Fix in Outlook/People/work account, then resync that account.
   - Nowhere obvious -> Suspect Siri/Spotlight suggested contact cache.

3. For Gmail Personal:
   - Clean/merge/delete the record in Google Contacts.
   - On iPhone, turn Gmail Contacts off.
   - Choose Delete from My iPhone.
   - Restart.
   - Turn Gmail Contacts back on.
   - Choose Keep existing local contacts.

4. Re-test search and opening the contact.
```

---

## 9. Key lesson

The decisive clue was not the blank page itself. The decisive clue was the contact source:

> The broken contact lived in **All Gmail Personal**.

Once the problem was treated as a **Gmail contact sync/cache problem**, rather than an iCloud or whole-iPhone problem, the fix became straightforward.

