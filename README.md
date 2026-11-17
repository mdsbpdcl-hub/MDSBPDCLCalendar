# MD Calendar · SBPDCL

A small installable app (PWA) that shows the upcoming meetings of MD, SBPDCL as a sticky note:
today, 7, 15 or 30 days ahead. It works on desktop (Chrome / Edge) and on mobile (Android / iPhone).

It reads the meetings from the Apps Script attached to the *Calendar_Sync_Sheet_MD_SBPDCL* sheet.
**No meeting data and no link or key is stored in this repository.** The web app link and key are typed
once on each device and stay only on that device.

## One-time setup in Apps Script

1. Paste the latest `Dashboard.gs` into the Apps Script project of the calendar sheet.
2. Run `makeAppKey()` once. Copy the key shown in the Execution log.
3. **Deploy → Manage deployments → Edit → Version: New version.**
   *Execute as: Me*, *Who has access: Anyone* (the app needs this to read the feed; the feed itself
   only answers when the correct key is given).
4. Copy the web app link (ends with `/exec`).

## Open the app

`https://mdsbpdcl-hub.github.io/MDSBPDCLCalendar/`

First time on a device, paste the web app link and key. Or open this one-time setup link
(do not share it, it contains your key):

```
https://mdsbpdcl-hub.github.io/MDSBPDCLCalendar/#u=<WEB_APP_LINK>&k=<KEY>
```

## Install

- **Windows / Mac (Chrome or Edge):** click the install icon in the address bar (or the ⬇ button in the app).
  It opens in its own small window. Resize it into a narrow strip at the side of the screen.
  - Keep it on top (Windows): Microsoft PowerToys → *Always On Top*, then press **Win + Ctrl + T** on the window.
  - Open at start-up: Edge → `edge://apps` → the app → *Auto-start on device login*;
    Chrome → `chrome://apps` → right-click the app → *Start app when you sign in*.
- **Android (Chrome):** menu ⋮ → *Install app* / *Add to Home screen*.
- **iPhone (Safari):** Share → *Add to Home Screen*.

## How it behaves

- Refreshes every 5 minutes, and whenever the app is brought back to the front.
- Shows the next meeting with a countdown, time clashes, holidays, and fades meetings already over.
- Works offline with the last saved list.
- On desktop and Android, the app icon shows how many meetings are left today.
