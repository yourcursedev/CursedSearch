<div align="center">

<!-- Replace the path below with your actual logo path in the repo, e.g. ./Assets/logo.png -->
<img src="Assets/logo.png" alt="CursedSearch Logo" width="96" height="96" />

# <span style="color:#FFFFFF;">Cursed</span><span style="color:#A855F7;">Search</span>

**Ultra-fast, typo-tolerant Windows desktop search & launcher utility wrapped in an Obsidian Black & Royal Purple glassmorphic interface.**

[![Platform](https://img.shields.io/badge/Platform-Windows%2010%20%2F%2011-09090B?style=flat-square&logo=windows&logoColor=A855F7)](#)
[![Framework](https://img.shields.io/badge/.NET-8.0%20WPF-09090B?style=flat-square&logo=dotnet&logoColor=A855F7)](#)
[![Build](https://img.shields.io/badge/Build-Passing-09090B?style=flat-square&logo=githubactions&logoColor=A855F7)](#)
[![License](https://img.shields.io/badge/License-MIT-09090B?style=flat-square&logoColor=A855F7)](#)

</div>

---

## 📖 Overview

**CursedSearch** is a high-speed Windows file search engine and command launcher inspired by utilities like *Listary*, *Everything*, and *PowerToys Run*. Built from the ground up for instant responsiveness (`<30ms` query execution), it pairs a multi-threaded background drive indexer and hybrid fuzzy-matching engine with a sleek, borderless glassmorphic UI and a standalone custom GUI installer/uninstaller.

---

## ✨ Key Features

- **🧠 Smart Typo-Tolerant Fuzzy Search:** Finds files, folders, and applications even when queries contain typos, extra/missing characters, or partial tokens (e.g., typing `Higggsfeld`, `higsfield`, or `hgfld` accurately ranks `HIGGSFIELD_Project_v2.mp4` at the top).
- **⚡ Real-Time Drive Indexing & Binary Cache:** Rapidly indexes local drives (`C:\`, `D:\`, etc.) with live `FileSystemWatcher` updates and persists an optimized index cache under `%LocalAppData%\CursedSearch\` for sub-second startup.
- **🎯 Power Prefixes & Instant Utilities:**
  - `app:` / `exe:` — Filter strictly for executable applications.
  - `folder:` / `dir:` — Filter strictly for directories.
  - `ext:png` / `*.mp4` — Filter by file extension.
  - `> ` — Execute Windows shell / CMD commands directly.
  - `= ` — Built-in instant math evaluator (e.g., `= 1450 * 0.18` → `261`).
- **⌨️ Global Hotkeys & Quick Preview:** Summon the floating command palette from anywhere via double-tap `Ctrl` (customizable), inspect files with the collapsible Quick Preview pane (`Tab`), or jump straight to parent folders in Explorer.
- **🌌 Obsidian & Royal Purple Glass UI:** Custom borderless WPF windows featuring deep obsidian gradients (`#09090B` → `#120C1C`), royal purple highlights (`#A855F7` / `#9333EA`), adjustable outer glow intensity, and panel opacity controls.
- **📦 Custom GUI Installer & Uninstaller:** Packaged with a themed setup wizard (`CursedSearch-Setup.exe`) supporting custom install paths, desktop shortcuts, startup registration, and a clean `Uninstall.exe`.

---

## ⌨️ Keyboard Shortcuts

| Shortcut | Action |
| :--- | :--- |
| **`Ctrl` (Double-Tap)** | Toggle CursedSearch floating palette globally |
| **`Esc`** | Hide search palette immediately |
| **`Enter`** | Launch selected application or open file |
| **`Ctrl + Enter`** | Open containing folder in File Explorer and highlight file |
| **`Ctrl + C`** | Copy full file/folder path to clipboard |
| **`Tab`** | Toggle Quick Preview & metadata side pane |
| **`Alt + Enter`** | Open custom dark-purple context menu |

---

## 🗂️ Repository Structure

```text
CursedSearch/
├── Assets/                 # Application icons (logo.png, CursedSearch.ico)
├── CursedSearch.Core/      # Drive indexer, binary cache, query parser & fuzzy matcher
├── CursedSearch.App/       # WPF glassmorphic UI, global hotkeys, tray icon & settings
├── CursedSearch.Installer/ # Standalone custom GUI Setup & Uninstaller
├── CursedSearch.Tests/     # Unit & performance benchmarks (xUnit)
├── scripts/                # Packaging & helper scripts
├── build.ps1               # End-to-end build, test & release packaging script
└── CursedSearch.slnx       # Solution file
```

---

## 🚀 Building from Source

### Prerequisites
- **Windows 10 / 11** (x64)
- **.NET 8.0 SDK**

### Build & Package
1. Clone the repository and open PowerShell in the root directory:
   ```powershell
   git clone https://github.com/YOUR_USERNAME/CursedSearch.git
   cd CursedSearch
   ```
2. Run the automated build and test pipeline:
   ```powershell
   powershell -ExecutionPolicy Bypass -File .\build.ps1
   ```
3. Once completed (`0 Warning(s), 0 Error(s)`), all compiled binaries and the standalone installer (`CursedSearch-Setup.exe`) will be generated inside the `dist/` folder.

> **Note:** If you install into a system-protected folder such as `C:\Program Files\CursedSearch`, run `CursedSearch-Setup.exe` as **Administrator**.

---

## 🛠️ Configuration & Data Paths

- **Index Cache & Logs:** `%LocalAppData%\CursedSearch\`
- **Uninstall Registry Key:** `HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall\CursedSearch`

---

## 📄 License

Distributed under the **MIT License**. See `LICENSE` for more information.