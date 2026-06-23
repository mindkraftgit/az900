# AZ-900 Practice — Install on iPhone / iPad

This is a Progressive Web App (PWA): once installed it gets its own icon, runs
fullscreen with no Safari bars, and works completely offline.

There's one requirement: a service worker (the thing that makes it work offline)
only runs when the files are served over **https**, not when you open the file
directly. So the app needs to live at a URL. The free, no-cost way is GitHub Pages.
Takes about 5 minutes, one time.

---

## Option A — GitHub Pages (recommended, free, permanent URL)

1. Go to https://github.com and sign in (or create a free account).
2. Click **+** (top right) → **New repository**. Name it e.g. `az900`. Set it to
   **Public**. Click **Create repository**.
3. On the new repo page, click **uploading an existing file**.
4. Drag in ALL of these files from the bundle (keep the names exactly):
   - `index.html`
   - `manifest.webmanifest`
   - `sw.js`
   - `icon-192.png`
   - `icon-512.png`
   - `apple-touch-icon.png`
5. Click **Commit changes**.
6. Go to the repo's **Settings** → **Pages** (left sidebar).
7. Under **Branch**, choose `main` and `/ (root)`, then **Save**.
8. Wait ~1 minute, refresh. GitHub shows a green box with your URL, like:
   `https://YOURNAME.github.io/az900/`

### Then on the iPhone/iPad:
1. Open that URL in **Safari** (must be Safari, not Chrome, for install to work).
2. Tap the **Share** icon (square with an up-arrow).
3. Scroll down, tap **Add to Home Screen**.
4. Tap **Add**. The AZ-900 icon now sits on the home screen.
5. Open it once while online so it caches — after that it works with no internet.

---

## Option B — Just use it without installing

If the home-screen icon and offline mode don't matter, skip all of the above:
just open `index.html` in Safari (email it to yourself or AirDrop it, then tap it).
Everything works — multiple choice, show-answer, explanations, study links — except
the service-worker offline caching. Safari still keeps it cached in practice for a
while, so it's usually fine on a flaky connection too.

---

## Notes
- **Progress now saves automatically** on the device (answers, score, flags) and
  reloads when the app reopens — survives closing the app and restarting the phone.
  This works in the hosted/installed version (Option A) and also in Safari (Option B).
- **Export / Import**: use the Export button to save progress to a file (e.g. to back
  it up or move it to another device), and Import to load it back. Handy for syncing
  between iPhone and iPad, since on-device storage doesn't sync across devices on its own.
- **Reset** clears saved progress on that device.
- One edge case: iOS "Private Browsing" blocks on-device storage. If he studies in a
  private tab, progress won't persist — Export still works as a manual backup.
- To update the questions later, just re-upload a new `index.html` to the same repo;
  the app auto-updates next time it's opened online. Saved progress is keyed to
  question IDs, so it carries over as long as the question set is the same.
