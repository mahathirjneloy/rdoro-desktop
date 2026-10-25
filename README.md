# RDORO Desktop

RDORO is a lightweight, offline Pomodoro timer and study tracker for Windows 10 and Windows 11, built with Tauri 2 (Rust + WebView2), Preact, TypeScript, and SQLite. It brings the visual design and workflow of the RDORO Android app to the desktop with a minimal memory and disk footprint.

## Features

- **Per-Mode Adaptive Theme:** Smoothly transitions across three color palettes depending on the active phase—Focus (mint green), Short Break (sky blue), and Long Break (lavender purple).
- **Drift-Free Timer Engine:** Calculates remaining time against an absolute target timestamp paired with a Rust background watchdog thread, staying accurate across window minimization, sleep, and system lock.
- **Local Study Tracker:** Logs completed and partial focus sessions to a local SQLite database (`%APPDATA%\RDORO\rdoro.db`) with subject tags, daily/weekly/monthly/yearly SVG bar charts, streak tracking, and CSV/JSON export.
- **Mini Mode:** Collapses into a `300 x 150` always-on-top compact window (`Ctrl + M`) so it can sit beside code editors, PDFs, or lecture notes.
- **Native Windows Integration:** System tray controls, taskbar progress bar, native toast notifications, global start/pause hotkey, and synthesized Web Audio completion chimes with zero external audio assets.

## Keyboard Shortcuts

| Shortcut | Action |
| :--- | :--- |
| `Space` | Start / Pause / Resume timer |
| `R` | Reset current phase |
| `S` | Skip to next phase |
| `1` / `2` / `3` | Switch to Focus / Short Break / Long Break |
| `Ctrl + M` | Toggle Always-on-Top Mini Mode |
| `Ctrl + T` | Open Study Tracker statistics |
| `Ctrl + ,` | Open Settings |
| `Ctrl + Alt + P` | Global Start / Pause shortcut (works in background) |
| `Esc` | Close active panel or dialog |

## Installation

1. Go to the **Actions** tab in this repository and select the latest successful **Build RDORO Windows Installer** workflow run.
2. Scroll down to **Artifacts** and download **`RDORO-Windows-Installer`**.
3. Extract the `.zip` archive and run **`RDORO_1.0.0_x64-setup.exe`** (or the `.msi` installer).

## Building from Source

Prerequisites: Node.js (v20+), pnpm, Rust stable toolchain, and Microsoft Visual Studio C++ Build Tools.

```powershell
pnpm install
pnpm tauri icon app-icon.svg
pnpm tauri dev      # Run in development mode
pnpm tauri build    # Build production .exe and .msi installers
