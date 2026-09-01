# Google Chat Powerpack

A Chrome extension that extends Google Chat with productivity features layered on top of chat messages — starting with an optional reminder layered on top of Google Chat's own Star (bookmark) feature.

## Language

**Reminder**:
A record a user creates on an already-starred Google Chat message, tracking an escalation from a Reminder Time to a Due Time. Created via "Remind me" — offered proactively the moment a message is starred, and always available afterward from that message's own "More actions" menu (for messages starred before the extension was installed too). Automatically deleted if the underlying message is unstarred. We do not track plain starred messages that have no Reminder — Chat's own Star feature and its "Starred" list already cover "saved for later" with no reminder attached.
_Avoid_: Saved Message, saved item, alarm.

**Snapshot**:
The full message text captured on a Reminder at the moment it's created. It is a point-in-time copy, not kept in sync with later edits to the original message — the Reminder's deep link back to the live message is what's authoritative for current content.
_Avoid_: snippet, preview, cached text.

**Reminders**:
The complete collection of a user's Reminder records, across every Status. Not a mirror of every starred message — only ones with a Reminder appear here. Chat's own native "Starred" list is where plain saved-with-no-reminder messages live; we don't duplicate it.
_Avoid_: Inbox, task list, queue.

**Due**:
The Status a Reminder reaches after its Reminder Time fires and its Due Time then elapses without being Resolved — an escalation past the initial Reminder nudge. Reaching Due fires its own (second) notification. The Due Time defaults to 15 minutes after the Reminder Time but is user-adjustable, and the user can disable the escalation entirely — in which case Due Time equals Reminder Time, so the Reminder becomes Due immediately when it fires.
_Avoid_: deadline, overdue.

**Status**:
The lifecycle stage of a Reminder — one of:
- **Pending**: created, its Reminder Time and Due Time not yet elapsed.
- **Due**: see **Due** above.
- **Resolved**: terminal. The user has dealt with the Reminder, or the underlying message was unstarred. A Resolved Reminder does not reopen.
