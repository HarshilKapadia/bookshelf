# Bibliotheca

A personal book-tracking app. Track every book you've read, own, are currently reading, or want to read — all in one unified library with no duplicates, rich filtering, and a detailed stats dashboard.

It installs to your iPhone, iPad, or Android home screen like a native app and works offline. No account or login required.

## Features

- **Unified library** — every book lives in one place with a status (`Read`, `Currently Reading`, `Want to Read`), so the same book never gets duplicated across lists.
- **Ownership tracking** — independent `Owned` and `Borrowed` toggles, separate from reading status.
- **Multiple authors per book** — supports co-authored works.
- **Read logs** — track every time you've read a book, in any format (Paperback, Hardcover, Ebook, Audiobook), with optional month and year.
- **Search and filters** — search by title, author, or genre; filter by status or by a specific author.
- **Almanac (dashboard)** — books read per year and month, format breakdown, ratings distribution, and a tappable monthly calendar.
- **Ratings and notes** — optional 1–5 star rating and a free-text notes field per book.
- **Import / Export** — back up your library to a file, or move it to another device.

---

## How to use this app

There's nothing to install on a computer and no account to create — just open the link and add it to your home screen.

### Step 1 — Open the app link

On your iPhone or iPad, open **Safari** (this must be Safari — "Add to Home Screen" doesn't fully work in Chrome or other browsers on iOS) and go to:

```
https://harshilkapadia.github.io/bookshelf/
```

### Step 2 — Add it to your home screen

**On iPhone/iPad (Safari):**
1. Tap the **Share** button (square icon with an arrow pointing up, usually in the bottom toolbar).
2. Scroll down and tap **Add to Home Screen**.
3. Tap **Add** in the top-right corner.

**On Android (Chrome):**
1. Tap the **⋮** menu in the top-right corner.
2. Tap **Add to Home screen** → **Add**.

The Bibliotheca icon now appears on your home screen. Opening it launches the app full-screen, just like any other app — no browser bar, no tabs.

### Step 3 — Start using it

- **Acquire** — add a new book to your library.
- **Stacks** — browse, search, and filter your library. Tap any book to view details or edit it.
- **Almanac** — your reading stats: books per year/month, format breakdown, ratings.
- **Scribes** — browse books by author, or back up/restore your data.

That's it. No login, no setup. The app works fully offline after your first visit.

---

## Your data stays on your device

Everything you add is stored locally in your browser, not on any server. This means:

- Your library is completely private — no one else can see your books, including whoever shared this app with you.
- If you use the app on both an iPhone and an iPad, they each keep a **separate library**. Adding a book on one device doesn't show up on the other.
- If you clear your browser's site data, or delete the app from your home screen, your library is **permanently deleted** unless you've exported a backup first.

### Backing up your library

Go to **Scribes → Data Tools → Export library to JSON**. This downloads a file you can keep safe and re-import later — either to restore your own library, or to move it to another device — via **Scribes → Data Tools → Import from JSON file**.

⚠️ **Importing a file replaces your current library entirely.** Back up first if you're not sure your existing data is already saved elsewhere.

---

## Limitations

- No multi-device sync — your iPhone and iPad each keep their own separate library.
- No login or multi-user support — this is a single personal library, not a shared one.
- Needs an internet connection the first time you open it; after that, most of it works offline.

---

## About this app (optional technical background)

For anyone curious how it's built: this is a single self-contained web page with no backend server. It uses React for the interface and stores all data in your browser's local storage. It's built as a Progressive Web App (PWA), which is why it can be "installed" to your home screen and work offline, despite not being in the App Store.

## License

Built for personal use. Feel free to adapt it for your own library.
