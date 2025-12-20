---
tags:
  - git
  - convention
  - best-practices
  - style
---

# Git Commit Messages (Conventional Commits)

> [!INFO]
> **Conventional Commits** provide a standard for creating an explicit commit history.  
> **Format:** `<type>(<scope>): <subject>`

**Related Notes:**
- [[Git Commands]] – How to execute the commits.

---

## 🌟 Common Types

| Type | Description | Example |
| :--- | :--- | :--- |
| **feat** | A new feature | `feat(auth): add google sso login` |
| **fix** | A bug fix | `fix(api): handle null pointer in user service` |
| **chore** | Maintenance (no prod code change) | `chore(deps): update react to v18` |
| **refactor**| Code change that neither fixes a bug nor adds a feature | `refactor(utils): simplify date parsing logic` |
| **docs** | Documentation only changes | `docs(readme): add installation steps` |
| **style** | Formatting, missing semi colons, etc; no code change | `style(css): fix indentation in navbar` |
| **test** | Adding missing tests or correcting existing tests | `test(auth): add unit tests for login` |
| **ci** | Changes to CI configuration files and scripts | `ci(github): add linting workflow` |
| **perf** | A code change that improves performance | `perf(image): optimize loading strategy` |
| **revert** | Reverting a previous commit | `revert: feat(auth): add google sso` |

## 🏗️ Structure

```text
<type>(<scope>): <subject>

<Optional detailed body>

<Optional footer (e.g., BREAKING CHANGE)>
```

### Examples

**Standard Feature:**
```text
feat(lang): add polish language support
```

**Breaking Change:**
```text
feat(api): change response format for user endpoint

BREAKING CHANGE: the user id field is now a string instead of an integer.
```