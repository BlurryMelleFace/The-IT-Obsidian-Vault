---
tags:
  - python
  - package-manager
  - dependency-management
  - venv
  - cheatsheet
---

# Poetry

> [!INFO]
> **Poetry** is a tool for dependency management and packaging in Python. It allows you to declare the libraries your project depends on and it will manage (install/update) them for you.

**Related Notes:**
- [[Virtual Environment]] – Poetry manages its own virtual environments effectively.
- [[Black]] & [[Isort]] – Common dev dependencies managed by Poetry.
- [[Docker]] – Often used with Poetry for reproducible builds.

---

## 📦 Project Setup
1. **New Project**:
   ```shell
   poetry new <project_name>
   ```
2. **Init in Current Dir**:
   ```shell
   poetry init
   ```

## 📥 Dependencies
1. **Install All** (from `poetry.lock` or `pyproject.toml`):
   ```shell
   poetry install
   ```
2. **Add Package**:
   ```shell
   poetry add <package_name>
   ```
3. **Add Dev Dependency**:
   ```shell
   poetry add --group dev <package_name>
   ```
   *(Old syntax: `poetry add -D <package_name>`)*
4. **Remove Package**:
   ```shell
   poetry remove <package_name>
   ```
5. **Show Dependency Tree**:
   ```shell
   poetry show --tree
   ```

## 🐍 Environment & Execution
1. **Spawn Shell**:
   ```shell
   poetry shell
   ```
2. **Run Command** (without entering shell):
   ```shell
   poetry run <command>
   ```
   *Example:* `poetry run python app.py`
3. **Env Info**:
   ```shell
   poetry env info
   ```
4. **List Envs**:
   ```shell
   poetry env list
   ```

## 🚀 Publishing
1. **Build Package**:
   ```shell
   poetry build
   ```
2. **Publish to PyPI**:
   ```shell
   poetry publish
   ```
