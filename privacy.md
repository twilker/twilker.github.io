---
title: DailyFlow – Privacy Policy
layout: page
permalink: /dailyflow/privacy/
---

# DailyFlow – Privacy Policy

**Languages:** English · [Deutsch](/dailyflow/privacy/de/) · [Español](/dailyflow/privacy/es/) · [Português (BR)](/dailyflow/privacy/pt-br/)

**App:** DailyFlow / Alltagshelfer (`com.marvelsofcode.dailyflow`)
**Effective date:** 12 August 2026

## 1. Who is responsible

Tobias Wilker
Email: [tobias.wilker@gmail.com](mailto:tobias.wilker@gmail.com)

I am the controller for any processing described here. For questions about this policy or your data, write to the address above.

## 2. The short version

DailyFlow is a local-first app. Your tasks, recurring tasks, routines, checklists, statistics, history and settings are stored **only on your device**. There is no account, no sign-up, and no user profile on any server of mine. I do not collect, receive, sell or share your personal data.

The app contains **no advertising, no tracking and no analytics**. The Firebase Analytics SDK was deliberately removed from the app.

Two optional features send data off the device, and only if you use them: **group sharing / task delegation** and **Google Drive backup**. Both are described below.

## 3. Data stored on your device

The app stores locally: tasks and their due dates, recurring rules, routines, checklists and their items, completed-task history, statistics, profiles, group membership and cryptographic keys, and your app settings. This data is never transmitted anywhere except through the two optional features in sections 4 and 5.

Completed-task history is pruned automatically according to the retention period you configure in Settings.

Uninstalling the app deletes all of this data.

## 4. Group sharing and task delegation (optional)

If you join a group by scanning another device's QR code, you can share tasks, routines and checklists with the other members and delegate tasks to them.

- **End-to-end encryption.** Everything that leaves your device for another member is encrypted on your device with AES-256-GCM (a fresh random initialisation vector per message, 128-bit authentication tag).
- **The key never reaches a server.** The 256-bit group key is generated on your device and is transferred only inside the QR code that you show to the other person. It is never uploaded, and I never have it.
- **What the transport sees.** Encrypted messages are relayed by a Google Cloud Function of mine (Firebase project `dailyflow-502909`) and delivered through Firebase Cloud Messaging. The relay sees only the recipient's messaging token, the opaque ciphertext, a collapse key and a sending-device identifier. It cannot read the content, and the content is not stored in any database of mine.
- **Retention.** Messages that cannot be delivered immediately are held by Firebase Cloud Messaging for at most its maximum time-to-live of four weeks and are then discarded. The corresponding local send queue on your device is cleared on the same schedule.
- **Abuse protection.** Firebase App Check (Play Integrity) is used to keep the relay endpoint from being abused by other clients.
- **Processor.** Google Ireland Limited / Google LLC acts as processor for Firebase Cloud Messaging and Cloud Functions. Google's own privacy information: <https://firebase.google.com/support/privacy>.
- **Legal basis.** Art. 6(1)(b) GDPR — processing necessary to provide the sharing feature you requested. If you do not join a group, no data is transmitted.

Note that the other members of a group can, by design, see the content you share with them. Only share with people you trust.

## 5. Google Drive backup (optional)

If you start a backup, the app asks for authorization to a single Google Drive scope: `https://www.googleapis.com/auth/drive.appdata`. This scope grants access **only to the app's own hidden application-data folder** in your Drive. The app can never see, read or modify your other Google Drive files, and it does not request your name, email address or profile.

The backup archive contains your local database, your settings and a snapshot of your group configuration. It is stored **in your own Google Drive account**, under your control, and is protected by Google's encryption at rest. It is not additionally encrypted by the app. I have no access to your Drive or to the backup file. You can delete it at any time from your Google account's app-data storage, and you can revoke the authorization at <https://myaccount.google.com/permissions>.

**Legal basis.** Art. 6(1)(a)/(b) GDPR — you explicitly trigger the backup.

## 6. Permissions and why they are needed

| Permission | Purpose |
| --- | --- |
| Notifications | Alarms for due tasks and the optional daily summary |
| Exact alarms | Ringing at exactly the time you set — an inexact reminder alarm would be useless |
| Full-screen intent | Showing and dismissing the alarm from the lock screen |
| Foreground service (media playback) | Keeping the alarm sound playing while the alarm rings |
| Run at startup | Re-scheduling your pending alarms after the device restarts |
| Internet / network state | Only for the encrypted relay (section 4) and the Drive backup (section 5) |
| Camera | Scanning a group-invite QR code. No photo or video is stored or transmitted |

## 7. Children

DailyFlow is a general-audience productivity app. It is not directed at children and does not knowingly collect data from them.

## 8. Your rights

Under the GDPR you have the right of access, rectification, erasure, restriction, data portability and objection, and the right to lodge a complaint with a supervisory authority.

Because I hold no personal data about you, there is in practice nothing for me to disclose or erase. You exercise these rights directly: uninstall the app to delete all local data, delete your Drive backup and revoke the Drive authorization in your Google account, and leave any group you have joined. If you have questions, contact me at [tobias.wilker@gmail.com](mailto:tobias.wilker@gmail.com).

## 9. Changes to this policy

Changes are published on this page with a new effective date. Substantive changes will also be noted in the app's release notes.
