---
tags:
  - devops
  - windows
  - shell
  - scripting
  - cheatsheet
---

# PowerShell

> [!INFO]
> **PowerShell** is a cross-platform task automation and configuration management framework. This note helps with job management and file operations, often useful within Windows containers or CI/CD agents.

**Related Notes:**
- [[AWS]] – AWS CLI often runs in PowerShell on Windows.
- [[Docker]] – Managing Docker Desktop on Windows.

---

## ⚙️ Jobs (Background Tasks)
1. **Get All Jobs**:
   ```powershell
   Get-Job
   ```

2. **Stop All Jobs**:
   ```powershell
   Get-Job | Stop-Job
   ```

3. **Delete All Jobs** (Force clean):
   ```powershell
   Get-Job | Remove-Job -Force
   ```

## 📂 File System
1. **Recursive Delete** (Force):
   ```powershell
   Remove-Item -Path "C:\path\to\folder" -Recurse -Force
   ```
   *Unix Equivalent:* `rm -rf /path/to/folder`

2. **Empty Directory Contents**:
   ```powershell
   Get-ChildItem -Path "C:\path\to\folder" -Recurse | Remove-Item -Force
   ```