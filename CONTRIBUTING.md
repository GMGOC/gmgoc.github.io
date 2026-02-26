# How to Edit the Website

## Getting Started

1. Go to **<https://github.dev/GMGOC/gmgoc.github.io>** in your browser. This opens a code editor.
2. The first time you open it, you'll see a prompt to install recommended extensions. Click **Install** — these help you spot mistakes in your edits.

## Editing Events

The events list lives in the file `data/events.yaml`. Click on it in the file list on the left to open it.

Each event looks like this:

```yaml
- title: "GMGOC Meeting"
  date: "2026-03-17"
  location: "Philanthropic Inn"
  description: "Optional extra details about the event"
  club organiser: "Name"
```

**Rules to follow:**

- Every event must start with `- title:` at the very start of the line (no spaces before the `-`)
- Every event must have a `date:` in `YYYY-MM-DD` format (e.g. `"2026-03-17"`, not `"17th March"`)
- `location:`, `description:`, and `club organiser:` are optional
- Indentation matters — use exactly **2 spaces** before `date:`, `location:`, etc.
- If you see red or yellow squiggly lines under your text, something is wrong — hover over them to see what

**To add a new event**, copy an existing one and change the details. Keep events in rough date order.

## Editing Pages

The website pages are in the `content/` folder as `.md` (Markdown) files. You can edit the text directly.

## Saving Your Changes

1. After editing, click the **branch icon** in the left sidebar (it may show a number badge for your changes)
2. Type a short description of what you changed in the text box at the top (e.g. "Add June meeting")
3. Click the **tick/checkmark button** to save

Your changes will go live on the website automatically after a short delay.
