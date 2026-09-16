# Anchor — Student Life Dashboard

A unified Windows desktop app for tracking study sessions, tasks, expenses, and habits — all in one place, with a dashboard that ties them together.

Built in Java + JavaFX. Stores everything locally in SQLite. No accounts, no cloud, no internet needed.

![Java](https://img.shields.io/badge/Java-17+-blue)
![JavaFX](https://img.shields.io/badge/JavaFX-21.0.2-orange)
![Platform](https://img.shields.io/badge/platform-Windows-lightgrey)

---

## Features

- **Study Timer** — Pomodoro-style timer with auto-logging and session history
- **To-Do List** — Tasks with due dates, priorities, categories, and overdue indicators
- **Expense Tracker** — Log spending, see monthly totals and category breakdowns
- **Habit Tracker** — Build streaks, track daily completions, see longest streak
- **Unified Dashboard** — Consistency score, weekly charts, GitHub-style activity heatmap

---

## Requirements

- **Windows 10 or 11**
- **JDK 17 or newer**
- **Maven 3.8+**

---

## Run from Source

```bash
git clone https://github.com/<your-username>/anchor.git
cd anchor
mvn clean javafx:run
```

Your data is stored at `C:\Users\<you>\.anchor\anchor.db`. Delete that file to reset.

---

## Build a Windows Installer

Requires [WiX Toolset v3](https://github.com/wixtoolset/wix3/releases) and JDK 21 LTS.

```bash
mvn clean package
mkdir staging
copy target\anchor-1.0.jar staging\
jpackage --type exe --name Anchor ^
  --input staging ^
  --main-jar anchor-1.0.jar ^
  --main-class com.studentdashboard.Launcher ^
  --app-version 1.0 --vendor "Your Name" ^
  --win-shortcut --win-menu ^
  --dest dist
```

Produces `dist\Anchor-1.0.exe` — a standalone installer that includes its own Java runtime.

---

## Project Structure

```
src/main/java/com/studentdashboard/
├── Launcher.java              # JVM entry point (fixes shaded-JAR JavaFX check)
├── Main.java                  # JavaFX Application class
├── dao/                       # Data access objects (SQLite queries)
├── db/                        # Database initialization and schema
├── model/                     # Data records and classes
├── ui/                        # JavaFX views and components
└── util/                      # Toast, UndoManager, DateUtil, ConsistencyScore

src/main/resources/styles.css  # Application theme
```

---

## Data Storage

All data lives in a single SQLite file at:

```
%USERPROFILE%\.anchor\anchor.db
```

Back it up by copying that file. Nothing is transmitted anywhere.

---

## Tech Stack

| Layer      | Choice                    |
|------------|---------------------------|
| Language   | Java 17                   |
| UI         | JavaFX 21                 |
| Storage    | SQLite (via sqlite-jdbc)  |
| Build      | Maven + shade plugin      |
| Packaging  | JDK's jpackage            |

---

## License

MIT — see `LICENSE` for details.
