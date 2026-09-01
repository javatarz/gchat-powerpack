# Google Chat Powerpack

A Manifest V3 Chrome extension that layers productivity features on top of Google Chat — see [`CONTEXT.md`](CONTEXT.md) for the domain model and [issue #1](https://github.com/javatarz/gchat-powerpack/issues/1) for the full spec.

## Loading the extension locally

Local unpacked install only for now — no Chrome Web Store listing.

1. Open `chrome://extensions` in Chrome.
2. Enable **Developer mode** (top-right toggle).
3. Click **Load unpacked** and select this repository's root folder.
4. The extension appears in the list as "Google Chat Powerpack".
5. Open [chat.google.com](https://chat.google.com) (or `mail.google.com/chat`) and check the DevTools console for `[Google Chat Powerpack] content script active on ...`, confirming the content script is running.

After editing extension files, click the reload icon on the extension's card in `chrome://extensions` to pick up changes.
