# Bibliotheca

A personal book-tracking app built as an installable Progressive Web App (PWA). Track every book you've read, own, are currently reading, or want to read — all in one unified library with no duplicates, rich filtering, and a detailed stats dashboard.

Runs entirely in your browser, installs to your iPhone/iPad home screen like a native app, and stores all data locally on your device. No account, no server, no backend required.

## Features

- **Unified library** — every book lives in one table with a status field (`Read`, `Currently Reading`, `Want to Read`), so the same book never gets duplicated across lists.
- **Ownership tracking** — independent `Owned` and `Borrowed` toggles, separate from reading status.
- **Multiple authors per book** — authors are stored in their own table and linked to books, supporting co-authored works.
- **Read logs** — track every time you've read a book, in any format (Paperback, Hardcover, Ebook, Audiobook), with optional month and year.
- **Search and filters** — search by title, author, or genre; filter by status; filter by a specific author.
- **Almanac (dashboard)** — books read per year and month, format breakdown, ratings distribution, and a tappable monthly calendar.
- **Ratings and notes** — optional 1–5 star rating and a free-text notes field per book.
- **Import / Export** — back up your entire library to a JSON file, or restore it on another device.
- **Offline-first** — built with a service worker so it keeps working without an internet connection after the first load.

## Tech overview

This is a single self-contained `index.html` file — no build step, no `npm install`, no bundler. It uses:

- **React 18** and **Babel Standalone**, loaded directly from a CDN, with JSX compiled live in the browser
- **`localStorage`** for data persistence on-device
- A **service worker** (`sw.js`) for offline caching
- A **web app manifest** (`manifest.json`) so it can be installed as a home-screen app on iOS/Android

Because everything is static files, it can be hosted for free on **GitHub Pages**, Netlify, Vercel, or any static file host.

## Files in this project

| File | Purpose |
|---|---|
| `index.html` | The entire app — UI, logic, and styling |
| `manifest.json` | PWA metadata (app name, icons, theme color) used when installing to a home screen |
| `sw.js` | Service worker that caches app files for offline use |
| `icon-192.png` / `icon-512.png` | App icons used on the home screen and app switcher |

---

## Setup: hosting your own copy

These steps assume no prior experience with GitHub or web hosting.

### Step 1 — Create a GitHub account (skip if you have one)

1. Go to [github.com](https://github.com) and click **Sign up**.
2. Follow the prompts to create a free account.

### Step 2 — Create a new repository

1. Once logged in, click the **+** icon in the top-right corner → **New repository**.
2. Name it something like `bibliotheca` (this name will appear in your app's URL).
3. Set visibility to **Public** (required for free GitHub Pages hosting).
4. Leave all other options as default, then click **Create repository**.

### Step 3 — Upload the project files

1. On your new repository's page, click **Add file → Upload files**.
2. Drag in all the files from this project: `index.html`, `manifest.json`, `sw.js`, `icon-192.png`, `icon-512.png`.
3. Scroll down and click **Commit changes**.

### Step 4 — Enable GitHub Pages

1. In your repository, go to **Settings** (top menu) → **Pages** (left sidebar).
2. Under **Source**, select **Deploy from a branch**.
3. Choose **`main`** as the branch and **`/ (root)`** as the folder.
4. Click **Save**.
5. Wait 30–60 seconds. GitHub will show a link like:
   ```
   https://YOUR-USERNAME.github.io/bibliotheca/
   ```
   That's your live app URL.

### Step 5 — Install on iPhone or iPad

1. Open **Safari** (must be Safari, not Chrome — "Add to Home Screen" only works fully in Safari on iOS).
2. Navigate to your GitHub Pages URL from Step 4.
3. Tap the **Share** button (square with an arrow pointing up).
4. Scroll down and tap **Add to Home Screen**.
5. Tap **Add** in the top-right corner.

The app icon now appears on your home screen and opens full-screen, just like a native app.

### Step 6 (optional) — Install on Android

1. Open **Chrome** and navigate to your GitHub Pages URL.
2. Tap the **⋮** menu in the top-right corner.
3. Tap **Add to Home screen** → **Add**.

---

## Updating the app later

If you make changes to `index.html` (or any other file) and want to push an update:

1. Go to your repository on GitHub.
2. Click on the file you want to update (e.g. `index.html`).
3. Click the **pencil/edit icon**.
4. Paste in the new content, then **Commit changes**.
5. GitHub Pages will automatically redeploy within about a minute.
6. Reload the app on your device. If you don't see changes, you may need to remove and reinstall it from the home screen once, since iOS aggressively caches PWAs via the service worker.

Alternatively, you can re-upload the file via **Add file → Upload files**, which will overwrite the existing one after you confirm.

## Data and privacy

All of your book data is stored in your browser's `localStorage`, on your device only. Nothing is sent to a server. This means:

- Your data **does not sync** automatically between multiple devices (e.g. iPhone and iPad each have their own separate library).
- Clearing your browser's site data, or uninstalling the app, will **delete your library permanently** unless you've exported a backup first.
- Use the **Export** button (under the Scribes tab → Data Tools) regularly to download a JSON backup of your library. You can re-import that file on the same or a different device using the **Import** button.

## Limitations

- No multi-device sync (by design, to keep setup simple and avoid cloud dependencies).
- No login or multi-user support — this is built for a single personal library.
- Requires an internet connection on first load to fetch fonts and the React/Babel libraries from CDNs; after that, the service worker allows most of the app to work offline.

## License

This project was built for personal use. Feel free to adapt it for your own library.
