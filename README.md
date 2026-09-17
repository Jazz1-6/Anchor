# Anchor — Student Life Dashboard

A unified Windows desktop app for tracking study sessions, tasks, expenses, and habits — all in one place, with a dashboard that ties them together.

Built in Java + JavaFX. Stores everything locally in SQLite. No accounts, no cloud, no internet needed.

---

## What is Anchor?

Students today use 3–4 separate apps to manage their daily routine — a timer for study, a to-do app for tasks, an expense tracker for spending, and a habit tracker for routines. This fragmentation makes it hard to see the full picture of how consistent you actually are.

**Anchor** solves this by putting all four in one app, sharing the same date-based data model, and surfacing a unified **consistency view** on the dashboard.

---

## Features

### Study Timer
- Pomodoro-style timer with configurable session (default 25 min) and break (default 5 min) lengths
- Start, pause, stop, and reset controls
- Sessions auto-log with date, start time, duration, and optional subject tag
- Shows today's total study time

### To-Do List
- Add, complete, and delete tasks
- Fields: title, due date, priority (Low / Medium / High), and category
- Overdue tasks highlighted in red
- Tasks due today or tomorrow highlighted in orange
- Sorted by completion status, then due date, then priority

### Expense Tracker
- Log expenses with amount, category, date, and optional note
- Default categories: Food, Transport, Books, Subscriptions, Other
- Monthly total and category-wise pie chart
- Recent expenses list with color-coded amounts

### Habit Tracker
- Create custom habits (e.g., "Read 20 pages", "Sleep before 11pm")
- Daily checkbox to mark done / not done
- Current streak and longest streak per habit
- Fire emoji indicator when the streak is alive

### Unified Dashboard
- Daily summary cards: Study, Tasks, Spent, Habits, Consistency
- Weekly study time bar chart (last 7 days)
- Weekly spending line chart (last 7 days)
- 60-day activity heatmap (GitHub-style)
- Daily **Consistency Score** (0–100) combining all four modules

---

## How to Use

Once the app is installed and running, here's how to use each module.

### 1. Study Timer
1. Click **Timer** in the sidebar
2. (Optional) Type what you're studying in the subject field
3. Set your preferred session and break length using the spinners
4. Click **Start** — the timer counts down
5. When it finishes, the session is auto-logged and you're offered a break
6. Click **Stop & Save** at any time to log a partial session early

### 2. To-Do List
1. Click **To-Dos** in the sidebar
2. Enter a task title in the top field
3. (Optional) Pick a due date, priority, and category
4. Click **Add Task**
5. Check the box next to a task to mark it complete
6. Select a task and click **Delete** to remove it (with Undo option)

### 3. Expense Tracker
1. Click **Expenses** in the sidebar
2. Enter an amount, pick a category, pick a date
3. (Optional) Add a note like "Lunch with Sam"
4. Click **Add Expense**
5. The pie chart and monthly total update automatically
6. Select an expense and click **Delete Selected** to remove it

### 4. Habit Tracker
1. Click **Habits** in the sidebar
2. Type a habit name (e.g., "Exercise")
3. Click **Add Habit**
4. Tick the checkbox each day you complete the habit
5. Your streak grows automatically — don't break the chain
6. Click **Remove** on a habit to delete it and its history

### 5. Dashboard
1. Click **Dashboard** in the sidebar
2. See today's consistency score and stat cards
3. Scroll to see the weekly charts and 60-day heatmap
4. The heatmap gets darker as activity increases

### Keyboard Shortcuts
| Shortcut | Action |
|----------|--------|
| `Ctrl + 1` | Go to Dashboard |
| `Ctrl + 2` | Go to Timer |
| `Ctrl + 3` | Go to To-Dos |
| `Ctrl + 4` | Go to Expenses |
| `Ctrl + 5` | Go to Habits |
| `Ctrl + Z` | Undo last delete |
| `Ctrl + Q` | Quit |

---

## Requirements

- **Windows 10 or Windows 11**
- **JDK 17 or newer** (only needed if you're building from source)
- **Maven 3.8+** (only needed if you're building from source)

If you're just downloading and running the installer, you don't need Java installed.

---

## Installation

### Option A — Download the Installer (Recommended)

1. Go to the **Releases** page of this repository
2. Download `Anchor-1.0.exe`
3. Double-click it and follow the installer wizard
4. Launch **Anchor** from the Start Menu

No Java installation required. The installer bundles its own runtime.

### Option B — Run from Source

```bash
git clone https://github.com/Jazz1-6/Anchor.git
cd Anchor
mvn clean javafx:run
