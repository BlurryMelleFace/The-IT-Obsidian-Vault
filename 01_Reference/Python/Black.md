---
tags:
  - python
  - formatter
  - pep8
  - style
  - code-quality
---

# Black (The Uncompromising Code Formatter)

> [!INFO]
> **Black** is "the uncompromising Python code formatter." By using it, you agree to cede control over minutiae of hand-formatting. It keeps your code compliant with PEP 8.

**Related Notes:**
- [[Poetry]] – Easily run via `poetry run black`.
- [[Isort]] – Often used together; Black should run after isort.

---

## 🖌️ Formatting
1. **Format Directory** (Recursive):
   ```shell
   poetry run black .
   ```
2. **Format Single File**:
   ```shell
   black <file_name>
   ```
3. **Dry Run** (Check only):
   ```shell
   black --check .
   ```
4. **Show Diff** (No changes):
   ```shell
   black --diff .
   ```

## ⚙️ Configuration & Options
1. **Custom Line Length** (Default is 88):
   ```shell
   black . --line-length 100
   ```
2. **Exclude Path**:
   ```shell
   black . --exclude <pattern>
   ```
3. **Config in `pyproject.toml`**:
   ```toml
   [tool.black]
   line-length = 88
   skip-string-normalization = true
   ```
