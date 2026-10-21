# FocusFlow — Student Productivity Dashboard

A polished, responsive task dashboard designed to help students turn deadlines into a clear daily plan. Built for the MFC frontend screening task with plain HTML, CSS, and JavaScript—no build step or dependencies required.

## Run locally

1. Download or clone this repository.
2. Open `index.html` in a modern browser.

For a local server, run `python -m http.server 5500` in the project folder and visit `http://localhost:5500`.

## Features

- Create, edit, complete, and delete tasks with title, subject, due date, priority, and status.
- At-a-glance counts for today, completed, overdue, and upcoming tasks.
- Today, upcoming, and all-task views; search by task or subject.
- Filter by subject and priority.
- Drag tasks between To do, In progress, and Completed columns.
- Daily completion ring and progress bar.
- Dark/light theme preference and tasks saved in `localStorage`.
- Responsive desktop and mobile layouts.
- 25-minute focus timer.
- Keyboard shortcuts: `N` to add a task, `T` to toggle theme, `Esc` to close the task form.

## Project structure

```text
├── index.html   # App structure and task form
├── styles.css   # Responsive layout, components, and themes
├── app.js       # Task state, rendering, filters, drag-and-drop, persistence
└── README.md
```

## State management

The app keeps its task list in a JavaScript array while it is open. Every task change calls `save()`, which serializes the array into `localStorage` under `focusflow.tasks.v1`. On the next visit, the app reads that saved JSON back into state. Theme preference is saved separately as `focusflow.theme`. This keeps the demo backend-free while preserving the user’s tasks and theme on the same browser and device.

The initial task list is sample data for the first launch. Once the app saves changes, the saved list becomes the source of truth. Clear the site’s local storage to restore the sample list.

## Notes

The focus timer is a simple in-page timer; it does not run in the background after the tab is closed. Task data is stored locally and is not synced across devices.
