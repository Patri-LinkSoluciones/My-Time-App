# My Time App ⏱️

A lightweight, fully client-side **time tracker** built with HTML, Tailwind CSS, and vanilla JavaScript. No server or install needed — just open `index.html` in your browser.

## Features

- **Projects** — Create and delete projects, each with a unique color indicator
- **Tasks** — Add, rename (double-click or pencil icon), and delete tasks under any project
- **Time tracking** — Start ▶️, Pause ⏸️, and Stop ⏹️ each task; only one task runs at a time
- **Task goals** — Set an hour goal per task with a live progress bar; turns green when completed
- **Manual time edit** — Click on any task's timer to manually adjust the tracked time
- **Auto-pause** — Tasks are automatically paused after work hours (Mon–Thu 16:00, Fri 14:00)
- **Session history** — Every start/stop cycle is saved as a session; total time is the sum of all sessions
- **Live timer** — Running tasks show a live ticking counter
- **Daily summary** — Header shows the total time tracked today across all tasks
- **Export to CSV** — Download all sessions as a CSV file compatible with Excel
- **Dark mode** — Vibrant purple/pink/teal color scheme on a dark background
- **Animations** — Aurora background, staggered card entrance and smooth modal transitions
- **Responsive** — Works on desktop and mobile browsers
- **Persistent** — All data is saved to `localStorage` (survives page refreshes)

> ⚠️ Data is stored locally in your browser. It will not sync across devices or browsers. Export to CSV regularly as a backup.

## Getting started

1. Clone or download this repository
2. Open `index.html` in any modern web browser — no build step required

```bash
# Optional: serve locally
npx serve .
# or
python3 -m http.server
```

## Live demo

[https://patri-linksoluciones.github.io/My-Time-App](https://patri-linksoluciones.github.io/My-Time-App)

## Usage

| Action | How |
|---|---|
| Create project | Click **+ New Project** above the project list |
| Delete project | Click the **×** button on the project card |
| Add task | Type in the "New task name" input and press **Enter** or **+ Add** |
| Rename task | Double-click the task name, or click the ✏️ pencil icon |
| Start timer | Click **▶ Start** on a task |
| Pause timer | Click **⏸ Pause** while a task is running |
| Resume timer | Click **▶ Start** again on a paused task |
| Stop & save | Click **■ Stop** to end the session and save it |
| Edit time | Click on the timer display (when paused) and type the new time in `HH:MM:SS` |
| Set goal | Click **🎯 Goal** on a task, enter hours and click Save |
| Export data | Click **⇓ Export CSV** at the bottom of the page |
| Delete task | Click the **×** button on the task row |

## Data structure

Data is stored in `localStorage` under the key `myTimeAppData`:

```json
{
  "projects": [
    {
      "id": "uuid",
      "name": "My Project",
      "color": "#a855f7",
      "tasks": [
        {
          "id": "uuid",
          "name": "Design logo",
          "goal": 90000000,
          "sessions": [
            { "start": "2026-04-08T10:00:00.000Z", "end": "2026-04-08T10:30:00.000Z" }
          ]
        }
      ]
    }
  ]
}
```

> `goal` is stored in milliseconds (e.g. 90000000 = 25 hours). It is `null` when no goal is set.

## Tech stack

- [Tailwind CSS](https://tailwindcss.com/) via CDN (no build step)
- Vanilla JavaScript (ES6+)
- `localStorage` for persistence
- Single `index.html` file — zero dependencies

---

✨ Designed by Patri G ✨
