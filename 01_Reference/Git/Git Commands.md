---
tags:
  - git
  - vcs
  - cheatsheet
  - cli
---

# Git Commands

> [!INFO]
> Essential Git commands for version control, branching, and repository management.

**Related Notes:**
- [[Git Commit Messages]] – Best practices for commit history.
- [[IntelliJ]] – Git integration in IDE.

---

## 🌿 Branching
1. **List Branches** (All):
   ```shell
   git branch -a
   ```
2. **Create & Switch**:
   ```shell
   git checkout -b <branch-name>
   ```
   *Modern:* `git switch -c <branch-name>`
3. **Switch Branch**:
   ```shell
   git switch <branch-name>
   ```
4. **Delete Local Branch**:
   ```shell
   git branch -d <branch-name>
   ```
5. **Delete Remote Branch**:
   ```shell
   git push origin --delete <branch-name>
   ```
6. **Fetch & Prune** (Clean up deleted remote branches):
   ```shell
   git fetch --prune
   ```

## 🔄 Syncing
1. **Pull Latest** (Rebase preferred for clean history):
   ```shell
   git pull --rebase origin main
   ```
2. **Push Branch**:
   ```shell
   git push -u origin <branch-name>
   ```
3. **Fetch All**:
   ```shell
   git fetch --all
   ```

## 💾 Staging & Committing
1. **Stage File**:
   ```shell
   git add <file>
   ```
2. **Stage All**:
   ```shell
   git add .
   ```
3. **Commit**:
   ```shell
   git commit -m "feat: add new login page"
   ```
4. **Amend Last Commit** (Change message/content):
   ```shell
   git commit --amend
   ```

## 📦 Stash
1. **Stash Changes**:
   ```shell
   git stash
   ```
2. **Apply Stash**:
   ```shell
   git stash pop
   ```
3. **List Stashes**:
   ```shell
   git stash list
   ```

## 🕰️ History & Undo
1. **Log (One-line)**:
   ```shell
   git log --oneline --graph --decorate
   ```
2. **Reset Hard** (Discard changes):
   ```shell
   git reset --hard HEAD
   ```
3. **Soft Reset** (Undo commit, keep changes staged):
   ```shell
   git reset --soft HEAD~1
   ```
