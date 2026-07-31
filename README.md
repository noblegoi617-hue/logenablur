# 🛡️ NEXIS - Ultimate USN Log Extractor

> **Powered by Knowx**

**NEXIS** is an aesthetic, dark-themed Windows utility designed to restore logging capabilities, bypass third-party OS optimizer restrictions, and extract permanent execution/deletion logs of `.exe` files from the NTFS **USN Journal**.

---

## 🌟 Key Features

* 🎨 **Liquid Glass Aesthetics**: Custom Dark Mode UI built with `customtkinter` and neon cyan accents.
* ⚙️ **Bypass OS Optimizers**: Force-enables Windows Audit Policies and process tracking disabled by tools like ReviOS, AtlasOS, or privacy tweakers.
* 📜 **USN Journal Recovery**: Verifies and forcefully initializes the NTFS USN Journal on the `C:` drive if missing or disabled.
* 🔍 **Targeted EXE Deletion Extraction**: Scans system logs specifically for `.exe` file deletion codes (`0x80000200`) and exports them cleanly to `DeletedExes.txt`.
* ⚡ **Multithreaded Performance**: Asynchronous background execution ensures the UI never freezes during extraction.

---

## 🛠️ Prerequisites & Installation

### 1. Requirements
Make sure you have Python 3.10+ installed. Install the required dependencies:

```bash
pip install customtkinter Pillow
