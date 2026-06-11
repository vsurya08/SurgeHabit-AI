# 30-Day Challenge Tracker

A beautiful, fully self-contained habit tracker for 30-day challenges. No app install, no account, no server — just open the link and start.

![30-Day Challenge](https://img.shields.io/badge/habit--tracker-30--day-4a9d6f?style=flat-square) ![No dependencies](https://img.shields.io/badge/dependencies-none-blue?style=flat-square) ![AI powered](https://img.shields.io/badge/AI-Claude%20powered-6b45c8?style=flat-square) ![Offline ready](https://img.shields.io/badge/offline-ready-brightgreen?style=flat-square)

---

## Live Demo

👉 **[Open the tracker](https://vsurya08.github.io/SurgeHabit-AI/)**

---

## What it does

You define your challenge. The tracker keeps you honest.

On first open, a short setup screen asks for:
- Your name
- A challenge title — type it and AI instantly suggests 6 relevant habits
- A start date
- 2–6 habits (pre-filled by AI, fully editable)

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
- **AI habit suggestions** — type your challenge name and Claude instantly suggests 6 relevant habits with icons and short labels. Regenerate anytime
- **Daily motivational quote** — a fresh AI-generated quote each morning, tailored to your specific habits and your name. Cached so it loads instantly on repeat visits

### Habits management
- **Drag to reorder** — rearrange habit tiles by dragging, settings panel updates to match
- **Add habits** — add up to 6 habits at any time from the settings panel
- **Edit habits** — rename the habit name and short label inline
- **Delete habits** — remove habits with a single click, progress re-indexes correctly
- **Set a target time** — assign a time to each habit (e.g. 06:30) for reminders and calendar events

### Reminders & calendar
- **Add to Calendar** — downloads a `.ics` file with one event per habit per day across all 30 days, with a built-in 5-minute alert. Opens in Apple Calendar, Google Calendar, or Outlook
- **Browser reminders** — enable in-browser notifications that fire 5 minutes before each habit's scheduled time while the tab is open

### Views
- **Calendar dates** — weekly and monthly views show the actual calendar date (e.g. Mar 27) under each day number
- **Check animation** — checking off a habit in the daily view triggers a spring pop, colour ripple, and row slide animation

### Other
- **User name personalisation** — your name appears in the daily quote and motivational message
- **Feedback button** — floating button links to a Google Form for user feedback
- **Google Analytics** — visitor tracking built in
- **Offline-ready** — works without an internet connection after the first load (AI features require connection)

---

## How data is stored

All your entries are saved to your browser's **localStorage** — they stay on your device, in your browser. Nothing is sent to a server. Your data is private by default.

This also means:
- Progress doesn't sync across devices or browsers
- Clearing browser data will erase progress
- Each person who opens the link gets their own fully independent tracker

---

## How to use

1. Open the link above
2. Type your challenge name — habits will be suggested automatically when you leave the field
3. Edit the suggested habits, add your name and start date
4. Click **Start my challenge**
5. Each day, open the tracker and tap habits in the Daily view to check them off
6. Use Weekly or Monthly views to spot patterns
7. Open **Customize habits** → set a time for each habit → click **Add to Calendar** to get native reminders on your phone

---

## Customising habits

Open the **Customize habits** panel at any time to:
- Edit the habit name and short label
- Set a target time for each habit
- Add a new habit (up to 6 total)
- Delete a habit you no longer want to track
- Download a `.ics` calendar file with reminders for all timed habits
- Enable browser notifications (fires 5 mins before each habit's time while tab is open)

---

## Deploying your own copy

This is a single `index.html` file with no build step, no framework, and no external dependencies beyond Google Fonts and the Anthropic API.

```bash
# Clone the repo
git clone https://github.com/vsurya08/30day-challenge.git

# Open index.html directly in a browser, or deploy to any static host
```

**Free hosting options:**
- [GitHub Pages](https://pages.github.com) — already set up if you're reading this
- [Netlify Drop](https://app.netlify.com/drop) — drag and drop for an instant URL
- [Vercel](https://vercel.com) — one-command deploy

---

## Tech stack

| Layer | What's used |
|---|---|
| UI | Vanilla HTML, CSS, JavaScript — zero frameworks |
| Fonts | DM Serif Display + DM Sans via Google Fonts |
| Storage | Browser localStorage |
| AI habits & quotes | Anthropic Claude API (claude-sonnet-4) |
| Analytics | Google Analytics 4 |
| Calendar | `.ics` file generation (iCalendar standard) |
| Notifications | Web Notifications API |

---

## Credits

Built as a personal productivity tool and open-sourced as a free template. Built entirely through conversation with Claude — no code written by hand.

Feel free to fork, modify, and share.

---

## Licence

MIT — use it, share it, build on it.
