# JobFill Privacy Policy

**Version:** 1.0.0 · **Effective date:** 2026-10-11

JobFill is a local-first browser extension. This policy describes exactly what
the shipped extension stores, what it can access, and what it sends. It does
not claim anything the implementation does not do.

## Summary

- JobFill has **no servers**. It makes **no network requests** of its own.
- Everything JobFill stores lives **on your device** (browser extension
  storage), never in a cloud service operated by us.
- **AI assistance is not enabled in the production release.** No AI provider
  is shipped; nothing is sent to any AI service.
- JobFill **never submits job applications** and never clicks Apply, Next or
  Continue for you.

## Data JobFill stores (on your device only)

| Data                                                                                              | Where it is stored                                          | Why                                                   |
| ------------------------------------------------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------- |
| Profile (name, contact details, links, work preferences, professional summary)                    | `chrome.storage.local`                                      | Fill the forms you approve                            |
| Answer Bank (saved answers to application questions)                                              | `chrome.storage.local`                                      | Suggest answers you approve per field                 |
| Resume files you import (PDF bytes, filename, metadata)                                           | IndexedDB (`jobfill.resume`)                                | Suggest profile values from your resume               |
| Extracted resume data (parsed text fields)                                                        | IndexedDB, with the resume record                           | Show reviewed suggestions; never auto-filled          |
| Settings and onboarding state                                                                     | `chrome.storage.local`                                      | Remember your choices                                 |
| Local usage counters (fills, undos, verification recoveries) and optional time entries you record | `chrome.storage.local`                                      | Local diagnostics you can clear                       |
| Problem reports you create                                                                        | Built locally; exported only when you copy or download them | Help you report issues without us collecting anything |

Nothing else is stored, synced or transmitted. `chrome.storage.sync` is never
used.

## Data JobFill sends externally

**None.** The extension contains no analytics, no telemetry, no crash
reporting, no advertising SDKs and no backend. A full network audit of the
shipped package confirms the extension itself never opens a network
connection.

Problem reports are exported by you (clipboard copy or local file download).
JobFill does not send them anywhere.

## Page access

JobFill's content scripts run on web pages (all frames) so it can find
application forms, including forms inside iframes. On those pages JobFill:

- reads form **metadata** only (field type, label text, attributes) to build
  its review list — it does not read the values already typed into fields;
- writes a value into a field **only** after you explicitly review and
  approve that field in the JobFill popup, for that fill session;
- never submits forms, never clicks Apply/Next/Continue, never navigates.

Detection snapshots (metadata only — no field values, no profile values) are
held in background memory for the popup and are discarded when the tab closes.

## AI

AI assistance is **not enabled** in this release and no AI provider ships
with the extension. The settings card states this. There is no path by which
profile or resume content could be sent to an AI service in this build.

## Deletion and control

- **Delete All My Data** (options page) removes profiles, Answer Bank,
  resumes, extracted resume data, settings, counters and time entries, and
  verifies the wipe by reading it back.
- Uninstalling the extension causes the browser to remove extension storage
  (`chrome.storage.local` and the extension's IndexedDB).
- Deletion removes JobFill's data **on this device only**. It cannot remove
  anything you previously submitted to job sites or any other service.
- You can export your profile and any problem report as local files at any
  time.

## Permissions

JobFill requests exactly one permission: **`storage`** (for
`chrome.storage.local`). Content scripts are injected into `http://*/*` and
`https://*/*` pages (all frames) as part of normal extension operation; no
optional or broad host permissions are requested, and no other Chrome APIs
(`tabs`, `scripting`, `webNavigation`, etc.) are used.

## Children

JobFill is a general-purpose productivity tool and is not directed at
children.

## Changes

Any future change that would transmit user data off-device (for example,
opting into a paid AI provider) will require a new explicit user action and
an updated policy. Local-first behavior is the default and remains the
default.

## Support

Use the in-app problem report export (options page) to create a redacted
local report, and the support contact published on the Chrome Web Store
listing. Do not include passwords, personal data or resume contents in any
manually submitted message.
