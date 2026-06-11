# SurgeHabit AI

A beautiful, AI-powered habit tracker for 30-day challenges. Sign in with Google, define your habits, and track them across every device you own.

![SurgeHabit AI](https://img.shields.io/badge/habit--tracker-SurgeHabit--AI-4a9d6f?style=flat-square) ![No dependencies](https://img.shields.io/badge/dependencies-none-blue?style=flat-square) ![AI powered](https://img.shields.io/badge/AI-Claude%20powered-6b45c8?style=flat-square) ![Firebase](https://img.shields.io/badge/auth-Firebase-orange?style=flat-square)

---

## Live Demo

👉 **[Open SurgeHabit AI](https://vsurya08.github.io/SurgeHabit-AI/)**

---

## What it does

You define your challenge. The tracker keeps you honest.

On first open, you sign in with Google, then a short setup screen asks for:

- Your name
- A challenge title — type it and AI instantly suggests 6 relevant habits with icons
- A start date
- 2–6 habits (pre-filled by AI, fully editable — keep names to 2–3 words)

After that, you get a full 30-day tracking dashboard with three views:

| View | What you see |
|---|---|
| **Daily** | Today's habits as large tap-to-check rows with animations — best for daily use |
| **Weekly** | All 5 weeks as a grid with checkboxes per day and actual calendar dates |
| **Monthly** | Full 30-day heatmap with coloured pips and calendar dates on every cell |

---

## Features

### Core tracking
- **Per-habit completion %** — each habit tile shows how consistent you've been across all 30 days with a colour-coded progress bar
- **Streak counter** — consecutive days where at least one habit was completed
- **Perfect days** — days where every habit was checked off, highlighted in green
- **Live stats** — current day, streak, overall completion %, and perfect days at a glance

### AI-powered
- **AI habit suggestions** — type your challenge name and Claude instantly suggests 6 relevant habits with icons. Regenerate anytime
- **Daily motivational quote** — a curated quote tailored to your challenge type, drawn from a pre-generated library of 210 quotes across 7 challenge types. Loads instantly, zero API cost

### Auth & sync
- **Google Sign-In** — one-tap sign in via Google OAuth
- **Cross-device sync** — your progress syncs to Firestore in real time. Open on your phone, pick up on your laptop
- **Multi-user on one device** — each Google account has completely separate data

### Habits management
- **Drag to reorder** — rearrange habit tiles by dragging
- **Add habits** — add up to 6 habits at any time from the settings panel
- **Edit habits** — rename any habit inline
- **Delete habits** — remove habits with a single click, progress re-indexes correctly
- **Set a target time** — assign a time to each habit for reminders and calendar export

### Reminders & calendar
- **Add to Calendar** — downloads a `.ics` file with one event per habit per day across all 30 days, with a built-in 5-minute alert. Opens in Apple Calendar, Google Calendar, or Outlook
- **Browser reminders** — enable in-browser notifications that fire 5 minutes before each habit's scheduled time while the tab is open

### Views
- **Calendar dates** — weekly and monthly views show the actual calendar date (e.g. Jun 11) under each day number
- **Timezone-aware** — day counter and date highlights use your local timezone, not UTC
- **Check animation** — checking off a habit triggers a spring pop, colour ripple, and row slide animation

### Notes & export
- **Notes per habit per day** — tap "+ Add note" on any habit to log how it went
- **Export progress summary** — downloads a full `.md` report with stats, per-habit completion %, and a day-by-day log with notes

### Other
- **Feedback button** — floating button links to a Google Form for user feedback
- **Google Analytics** — visitor and event tracking built in
- **Mobile-optimised** — responsive 3-column tile grid with fluid font sizes via `clamp()`

---

## How data is stored

Your data is stored in **Firestore** (Google's cloud database), linked to your Google account. It syncs automatically across every device you sign in on.

- Data is private to your Google account — no one else can access it
- Firestore security rules enforce that users can only read and write their own documents
- localStorage is used as a fast local cache for instant load times

---

## How to use

1. Open the link above
2. Click **Sign in with Google** — your progress is tied to your account
3. Type your challenge name — AI suggests 6 habits automatically when you leave the field
4. Edit the suggested habits (keep names to 2–3 words), set your start date
5. Click **Start my challenge**
6. Each day, open the tracker and tap habits in the Daily view to check them off
7. Use Weekly or Monthly views to spot patterns
8. Open **Customize habits** → set a time per habit → click **Add to Calendar** for native reminders

---

## Customising habits

Open the **Customize habits** panel at any time to:

- Edit the habit name (max 20 characters, 2–3 words recommended)
- Set a target time for each habit
- Add a new habit (up to 6 total)
- Delete a habit you no longer want to track
- Download a `.ics` calendar file with reminders for all timed habits
- Enable browser notifications
- Export your full progress summary as markdown

---

## Tech stack

| Layer | What's used |
|---|---|
| Frontend | Vanilla HTML, CSS, JavaScript — zero frameworks |
| Fonts | DM Serif Display + DM Sans via Google Fonts |
| Hosting | GitHub Pages |
| Identity | Google OAuth + Firebase Authentication |
| Database | Firestore — real-time cross-device sync |
| AI proxy | Cloudflare Workers — secure server-side proxy for Claude API |
| AI features | Anthropic Claude API (claude-sonnet-4) — habit suggestions, icon suggestions |
| Analytics | Google Analytics 4 |
| Calendar | `.ics` file generation (iCalendar standard) |
| Notifications | Web Notifications API |

---

## Deploying your own copy

This is a single `index.html` file with no build step and no framework. To run your own instance you need:

1. **Firebase project** — enable Google Auth and Firestore. Update the `firebaseConfig` in `index.html`
2. **Anthropic API key** — get one at `console.anthropic.com`
3. **Cloudflare Worker** — deploy a proxy worker that forwards requests to the Anthropic API with your key stored as a secret. Update the worker URL in `index.html`
4. **GitHub Pages** — push `index.html` to a repo and enable Pages

```bash
# Clone the repo
git clone https://github.com/vsurya08/SurgeHabit-AI.git

# Open index.html directly in a browser, or deploy to any static host
```

---

## Credits

Built as a personal productivity tool and open-sourced as a free template. Built entirely through conversation with Claude — no code written by hand.

Feel free to fork, modify, and share.

---

## Licence

MIT — use it, share it, build on it.
