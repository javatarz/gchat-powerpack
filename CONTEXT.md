# Google Chat Powerpack

A Chrome extension that extends Google Chat with productivity features layered on top of chat messages — starting with saving a message for later and optionally attaching a reminder to it.

## Language

**Saved Message**:
A reference to a Google Chat message that a user has marked via "Read later," together with any Reminder attached to it and its current Status.
_Avoid_: bookmark, clip, saved item, note.

**Read later**:
The user action (triggered from a Google Chat message) that creates a Saved Message. Opens a dialog where the user can optionally attach a Reminder before it's saved.

**Snapshot**:
The full message text captured on a Saved Message at the moment Read later is used. It is a point-in-time copy, not kept in sync with later edits to the original message — the Saved Message's deep link back to the live message is what's authoritative for current content.
_Avoid_: snippet, preview, cached text.

**Inbox**:
The complete collection of a user's Saved Messages, across every Status. Not a separate store from "task list" — that term is avoided (see below).
_Avoid_: task list, queue.

**Reminder**:
An optional Reminder Time attached to a Saved Message, set when the message is saved. When the Reminder Time elapses, the extension fires a notification.
_Avoid_: alarm.

**Due**:
The Status a Saved Message reaches after its Reminder fires and its Due Time then elapses without the message being Resolved — an escalation past the initial Reminder nudge. Reaching Due fires its own (second) notification. The Due Time defaults to 15 minutes after the Reminder Time but is user-adjustable, and the user can disable the escalation entirely — in which case Due Time equals Reminder Time, so the message becomes Due immediately when the Reminder fires.
_Avoid_: deadline, overdue.

**Status**:
The lifecycle stage of a Saved Message — one of:
- **Saved**: created via Read later; if a Reminder was set, its Reminder Time and Due Time are still pending.
- **Due**: only reached if a Reminder was set — see **Due** above.
- **Resolved**: terminal. The user has dealt with the Saved Message. A Resolved Saved Message does not reopen.

A Saved Message with no Reminder moves directly from Saved to Resolved.
