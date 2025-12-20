---
tags:
  - config
  - ide
  - vscode
  - json
  - debugging
---

# IDE Configuration (VS Code)

> [!INFO]
> Recommended settings and debug configurations for **VS Code** to work efficiently with the storage and API services.

**Related Notes:**
- [[IntelliJ]] – Alternative IDE configurations.
- [[Python]] – Python formatting settings included below.

---

## ⚙️ Settings (`settings.json`)
> *Add these to your workspace `settings.json` to enable auto-formatting with Black/Isort.*

```json
{
    "git.autofetch": true,
    "editor.minimap.enabled": false,
    "explorer.confirmDragAndDrop": false,
    "[json]": {
        "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
    "[python]": {
        "editor.defaultFormatter": "ms-python.black-formatter",
        "editor.formatOnSave": true
    },
    "editor.codeActionsOnSave": {
        "source.organizeImports": "explicit"
    },
    "isort.args": ["--profile", "black"],
    "black-formatter.args": ["--line-length", "88"]
}
```

## 🐞 Debug Configurations (`launch.json`)

### Core API (Celery & FastAPI)
```json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Python Debugger: worker",
      "type": "debugpy",
      "request": "launch",
      "module": "celery",
      "args": ["--app", "pid_api.tasks.celery", "worker", "-Q", "main", "--loglevel=info","--pool","solo","--without-mingle"],
      "env": {
          "FLASK_DEBUG": "1",
          "CELERY_BROKER_URL": "redis://localhost:6379/0",
          "AWS_REGION": "eu-central-1"
      }
    },
    {
      "name": "Python Debugger: FastAPI",
      "type": "debugpy",
      "request": "launch",
      "module": "uvicorn",
      "args": ["pid_api.main:app", "--reload", "--port", "8000"],
      "env": {
          "POSTGRES_URL": "postgresql://postgres:example_password@localhost:5432/ipidDB"
      }
    }
  ]
}
```