Markdown# 🛡️ NEXIS - Ultimate USN Log Extractor

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
2. AssetsEnsure demo.ico (application logo) is placed in the same directory as logenable.py.🚀 How to Run⚠️ Important: Windows Administrative privileges are required for fsutil and auditpol commands to modify system journals and access raw NTFS structures.Open Command Prompt or PowerShell as Administrator.Run the script:Bashpython logenable.py
Click on INITIALIZE EXTRACTION.📦 Building Standalone Executable (.exe)To compile NEXIS into a single executable file with custom icons and no background console window, run:Bashpyinstaller --noconsole --onefile --add-data "demo.ico;." --icon=demo.ico logenable.py
Your compiled .exe will be located inside the dist/ directory.⚙️ Technical DetailsActionCommand ExecutedAudit Policy Enforcerauditpol /set /subcategory:"Process Creation" /success:enable /failure:enableUSN Journal Initializationfsutil usn createjournal m=33554432 a=8388608 c:Deleted EXE Filteringfsutil usn readjournal c: csv | findstr /i /c:.exe | findstr /i /c:0x80000200👤 CreditsDeveloper & Owner: KnowxFramework: CustomTkinter & Python 3
