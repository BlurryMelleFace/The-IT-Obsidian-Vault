---
tags:
  - python
  - venv
  - environment
  - isolation
  - cheatsheet
---

# Python Virtual Environments

> [!INFO]
> A **Virtual Environment** is an isolated Python environment that allows you to manage dependencies for different projects separately, avoiding version conflicts.

**Related Notes:**
- [[Poetry]] – Modern tool that handles virtual environments automatically.
- [[Docker]] – Provides container-level isolation (an alternative or complement).

---

## 🐍 Built-in `venv`
1. **Create Env**:
   ```shell
   python -m venv <env_name>
   ```
   *Standard name is often `.venv`*
2. **Activate (Windows PowerShell)**:
   ```powershell
   .\<env_name>\Scripts\Activate.ps1
   ```
3. **Activate (macOS/Linux)**:
   ```shell
   source <env_name>/bin/activate
   ```
4. **Deactivate**:
   ```shell
   deactivate
   ```

## 🧬 Using `virtualenv` (Legacy/External)
1. **Create Env**:
   ```shell
   virtualenv <env_name>
   ```

## 📦 Managing with Poetry
> *See also: [[Poetry]]*

1. **Info**:
   ```shell
   poetry env info
   ```
2. **Remove Env**:
   ```shell
   poetry env remove python
   ```
3. **Use Specific Python**:
   ```shell
   poetry env use /path/to/python
   ```

## 💡 Pyenv (Python Version Management)
1. **List Versions**:
   ```shell
   pyenv versions
   ```
2. **Set Global Version**:
   ```shell
   pyenv global <version>
   ```
3. **Set Local Directory Version**:
   ```shell
   pyenv local <version>
   ```