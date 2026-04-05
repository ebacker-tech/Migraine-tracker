# 🧠 Migraine Tracker

A personal migraine tracking Progressive Web App (PWA) built for iPhone home screen use. Track pain levels, medications, and triggers on a color-coded calendar with month-by-month dashboard charts.

---

## 📱 How to Use on iPhone

1. Open Safari on your iPhone
2. Go to your GitHub Pages URL: `https://yourusername.github.io/migraine-app`
3. Tap the **Share button** (box with arrow at the bottom of Safari)
4. Tap **"Add to Home Screen"**
5. Tap **Add** — the app appears on your home screen like a native app

> ⚠️ Must be opened in **Safari** — Chrome and other browsers do not support "Add to Home Screen" as a PWA on iPhone.

---

## 🗂️ Files in This Repo

| File | Purpose |
|------|---------|
| `index.html` | The entire app — all HTML, CSS, and JavaScript |
| `manifest.json` | PWA configuration (app name, icon, theme color) |
| `sw.js` | Service worker — enables offline use and auto-updates |
| `icon.png` | Home screen icon (woman silhouette with explosion rays) |
| `README.md` | This file |

---

## ✨ Features

### 📅 Calendar Tab
- Monthly calendar view with color-coded pain levels (1–10)
- Navigate between months with arrow buttons
- Today's date is highlighted with a purple dot
- Each logged day shows:
  - Colored border indicating pain level
  - Colored background tint
  - 💊 Pill icon(s) in medication colors if medication was taken
- Tap any day to log or edit an entry

### 📊 Dashboard Tab
- Opens first when you launch the app
- **Migraine Days per Month** — bar chart for the last 12 months, bars colored by average pain level
- **Average Pain Level per Month** — line chart showing pain trends over time
- **Medication Usage (all time)** — horizontal bar chart of most-used medications
- **Top Triggers (all time)** — horizontal bar chart of most common triggers

### 🗂️ Data Tab
- **Export All Data to CSV** — saves a backup file to your iPhone
- **Import from CSV** — restores data from a previously exported backup
- **Summary** — shows total entries, first/latest entry dates, overall average pain, and last export date

---

## 📝 Logging an Entry

Tap any calendar day to open the log sheet. You can record:

### Pain Level (1–10)
Color-coded scale:
| Level | Color | Description |
|-------|-------|-------------|
| 1 | 🟢 Green | Barely noticeable |
| 2 | 🟢 Light green | Very mild |
| 3 | 🟡 Yellow-green | Mild |
| 4 | 🟡 Yellow | Moderate |
| 5 | 🟠 Light orange | Strong |
| 6 | 🟠 Orange | Intense |
| 7 | 🔴 Red | Severe |
| 8 | 🔴 Dark red | Very severe |
| 9 | 🔴 Deep red | Excruciating |
| 10 | 🔴 Darkest red | Debilitating |

### Medications
Default medications:
- Aleve (1 tablet)
- Aleve (2 tablets)
- Advil (3 tablets)
- Ubrelvy 100mg (1 tablet)
- Ubrelvy 100mg (2 tablets)
- ➕ Add custom medications — saved permanently

Medication pill icons on the calendar are color-coded:
- 🟤 Brown — Advil
- 🔵 Blue — Aleve
- 🩵 Teal — Ubrelvy
- 🟣 Purple — Custom medications

### Triggers
Default triggers:
- Lack of Sleep
- Food
- Sugar
- Stress
- Weather
- Period
- Jet Lag
- ➕ Add custom triggers — saved permanently

### Notes
Free text field for symptoms, how you're feeling, anything else.

---

## 💾 Your Data

- All data is stored in **Safari's localStorage** on your iPhone
- Data **never leaves your device** — no account, no cloud, no server
- Data **survives app updates** — uploading new code to GitHub does not affect your entries
- A **weekly backup reminder** appears if you haven't exported in 7 days

### To protect your data:
1. Tap **Export to CSV** regularly from the Data tab
2. Save the file to your iPhone's Files app or email it to yourself
3. If you ever lose data, tap **Import from CSV** to restore from your backup

### ⚠️ Data can be lost if:
- You go to **iPhone Settings → Safari → Clear History and Website Data**
- You delete the specific site data under **Settings → Safari → Advanced → Website Data → github.io**
- Never unpublish your GitHub Pages site while you have data you haven't backed up

---

## 🔄 How to Update the App

When changes are made to the app:

1. Download the updated file(s) from Claude
2. Go to your repo at `github.com/yourusername/migraine-app`
3. Click **Add file → Upload files**
4. Drag in the new file(s) — GitHub automatically replaces files with the same name
5. Scroll down and click **Commit changes**
6. Wait 1–2 minutes for GitHub Pages to rebuild
7. Close the app on your iPhone (swipe up → swipe it away) and reopen it

> The service worker is set to **network-first**, so updates come through automatically after reopening. No need to delete and re-add the home screen icon.

---

## 🛠️ How This Was Built

This app was built entirely in conversation with **Claude (Anthropic)** without any manual coding. The development conversation covered:

- Initial calendar with 5-level pain scale
- Expanded to 10-level pain scale with full color gradient
- Custom medication list (Aleve, Advil, Ubrelvy dosages)
- Color-coded pill icons per medication on the calendar
- PWA conversion for iPhone home screen (manifest, service worker, safe area insets)
- Bottom sheet modal (native iOS feel)
- Dashboard tab with 3 charts
- Data tab with export/import CSV
- Weekly backup reminder banner
- Triggers field with default and custom options
- Triggers chart added to dashboard
- App renamed from "Migraine Journal" to "Migraine Tracker"
- Custom app icon: woman with curly hair silhouette, explosion rays from top of head
- Three-tab navigation: Dashboard · Calendar · Data
- Network-first service worker to fix auto-update issues
- Storage key merging to recover data across versions

---

## 🎨 Design

- **Font:** DM Serif Display (headers) + DM Mono (body)
- **Theme:** Dark background (`#0f0e17`) with purple accent (`#a78bfa`)
- **Pain colors:** Green → Yellow → Orange → Red gradient across 10 levels
- **Icon:** Purple woman silhouette with curly hair, explosion rays bursting upward from top of head

---

## 📋 CSV Export Format

Exported files are named `migraine-tracker.csv` with columns:

```
Date, Pain Level, Medications, Triggers, Notes
2025-04-01, 7, "Ubrelvy 100mg (1 tablet)", "Stress; Weather", "Bad day, started around noon"
```

This file can be opened in Excel, Google Sheets, or Numbers.

---

## 🔮 Possible Future Features

- Pain location tracking (head region selector)
- Monthly summary email export
- Streak tracking (migraine-free days)
- Notes search
- Dark/light theme toggle

---

*Built with Claude · Hosted on GitHub Pages · Data stored locally on your iPhone*
