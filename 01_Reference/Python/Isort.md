---
tags:
  - python
  - imports
  - sorter
  - style
  - code-quality
---

# Isort (Import Sorter)

> [!INFO]
> **isort** is a Python utility / library to sort imports alphabetically, and automatically separated into sections and by type.

**Related Notes:**
- [[Black]] – Isort should be configured to be compatible with Black.
- [[Poetry]] – Used to manage isort as a dev dependency.

---

## 🧹 Sorting
1. **Sort Directory**:
   ```shell
   poetry run isort .
   ```
2. **Sort Single File**:
   ```shell
   isort <file_name>
   ```
3. **Check Only** (Dry Run):
   ```shell
   isort --check-only .
   ```
4. **Verbose Output**:
   ```shell
   isort . --verbose
   ```

## ⚙️ Configuration & Profiles
1. **Black Compatibility** (Crucial if using Black):
   ```shell
   isort . --profile black
   ```
2. **Django Profile**:
   ```shell
   isort --profile django
   ```
3. **Skip Files**:
   ```shell
   isort --skip <file_or_directory>
   ```

## 🐞 Linting & Debug
1. **Check for Sort Errors**:
   ```shell
   isort . --check-only --verbose
   ```
2. **Show Version**:
   ```shell
   isort --version
   ```
