# Chain and Cue

A personal life-system app. Four daily systems drawn as anchor chains rising from the
seabed, identity spheres that grow with what you actually do, and a quiet log with no
streaks and no scores.

Everything is stored in the browser on the device that runs it. Nothing is sent anywhere,
and there is no account, no server and no sync.

## Files

| File | What it is |
| --- | --- |
| `index.html` | The whole app — markup, styles and logic in one file |
| `sw.js` | Service worker. Caches the app so it opens with no connection |
| `manifest.webmanifest` | Name, colours and icons for the home-screen install |
| `icon-192.png`, `icon-512.png`, `icon-512-maskable.png` | Android and browser icons |
| `apple-touch-icon.png` | iPhone home-screen icon |

All paths are relative, so the app works from a subfolder such as
`https://<user>.github.io/chain-and-cue/`.

## Putting it on GitHub Pages

Easiest on a computer. On a phone it works but the upload step is awkward.

1. Sign in at github.com and create a new repository named `chain-and-cue`. Set it to
   **Public** — GitHub Pages needs that on a free account. Do not add a README; this one
   is already here.
2. On the empty repository page choose **uploading an existing file**, then drag in every
   file from this folder. Commit.
3. Go to **Settings → Pages**. Under *Build and deployment*, set Source to
   **Deploy from a branch**, branch `main`, folder `/ (root)`. Save.
4. Wait a minute, then open `https://<your-username>.github.io/chain-and-cue/`.

## Getting it onto the phone

- **iPhone:** open the address in Safari (not Chrome — only Safari can install).
  Share → Add to Home Screen.
- **Android:** open it in Chrome. Menu → Add to Home screen, or accept the install prompt.

Open it once while online so the service worker caches everything. After that it opens
with no connection.

## Moving your data across

The installed app has its own storage, separate from the artifact version and separate
from the browser you first opened it in.

1. In the version that holds your data, go to **Data → Copy backup**.
2. Open the installed app, go to **Data**, paste into the Restore box, and tap
   **Replace everything** twice.

Do that once at the start. After that, use one copy and ignore the others.

## Backups

Storage lives in the browser. Clearing site data erases it, and so does deleting the
installed app on some phones. Copy the backup out every few weeks and keep it somewhere
dull — a note, a file in Drive, an email to yourself.

## Updating the app

When `index.html` changes, also change the version string at the top of `sw.js`
(`chain-and-cue-v1` → `-v2`, and so on). Without that, installed copies keep serving the
old cached page.
