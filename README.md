# My Time App ⏱️

A lightweight, fully client-side **time tracker** built with HTML, Tailwind CSS, and vanilla JavaScript. No server or install needed — just open `index.html` in your browser.

## Features

- **Projects** — Create and delete projects, each with a unique color indicator
- **Tasks** — Add, rename (double-click or pencil icon), and delete tasks under any project
- **Time tracking** — Start ▶️, Pause ⏸️, and Stop ⏹️ each task; only one task runs at a time
- **Session history** — Every start/stop cycle is saved as a session; total time is the sum of all sessions
- **Live timer** — Running tasks show a live ticking counter
- **Daily summary** — Header shows the total time tracked today across all tasks
- **Dark mode** — Vibrant purple/pink/teal color scheme on a dark background
- **Responsive** — Works on desktop and mobile browsers
- **Persistent** — All data is saved to `localStorage` (survives page refreshes)

## Getting started

1. Clone or download this repository
2. Open `index.html` in any modern web browser — no build step required

```bash
# Optional: serve locally
npx serve .
# or
python3 -m http.server
```

## Usage

| Action | How |
|---|---|
| Create project | Click **+ New Project** in the header |
| Delete project | Click the **×** button on the project card |
| Add task | Type in the "New task name" input and press **Enter** or **+ Add** |
| Rename task | Double-click the task name, or click the ✏️ pencil icon |
| Start timer | Click **▶ Start** on a task |
| Pause timer | Click **⏸ Pause** while a task is running |
| Resume timer | Click **▶ Start** again on a paused task |
| Stop & save | Click **■ Stop** to end the session and save it |
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
          "sessions": [
            { "start": "2026-04-08T10:00:00.000Z", "end": "2026-04-08T10:30:00.000Z" }
          ]
        }
      ]
    }
  ]
}
```

## Tech stack

- [Tailwind CSS](https://tailwindcss.com/) via CDN (no build step)
- Vanilla JavaScript (ES6+)
- `localStorage` for persistence
- Single `index.html` file — zero dependencies
