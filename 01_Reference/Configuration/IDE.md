
# VS Code
### settings.json (black and isort on save)

```python

{
    "git.autofetch": true,
    "editor.minimap.enabled": false,
    "explorer.confirmDragAndDrop": false,
    "security.workspace.trust.untrustedFiles": "open",
    "[json]": {
        "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
    "liveServer.settings.proxy": {
        "enable": true,
        "baseUri": "/",
        "proxyUri": "http://localhost:4200"
    },
    "liveServer.settings.port": 4200,
    "liveServer.settings.donotShowInfoMsg": true,
    "git.openRepositoryInParentFolders": "never",
    "git.confirmSync": false,
    "explorer.confirmDelete": false,
    "terminal.integrated.enableMultiLinePasteWarning": false,
    "javascript.updateImportsOnFileMove.enabled": "always",
    "git.ignoreRebaseWarning": true,
    "docker.extension.enableComposeLanguageServer": false,
    "github.copilot.nextEditSuggestions.enabled": true,
    "docker.extension.dockerEngineAvailabilityPrompt": false,
    "sonarlint.focusOnNewCode": false,
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

## Debug Configs

### Core API

```python
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
          "APP_SETTINGS": "project.server.config.DevelopmentConfig",
          "CELERY_BROKER_URL": "redis://localhost:6379/0",
          "CELERY_RESULT_BACKEND": "redis://localhost:6379/0",
          "LOG_LEVEL": "info",
          "AWS_REGION": "eu-central-1",
          "DYNAMODB_ENDPOINT_URL": "http://localhost:8000",
          "DYNAMODB_TABLE_NAME": "ipid-jobs-dev01",
      }
    },
    {
      "name": "Python Debugger: FastAPI",
      "type": "debugpy",
      "request": "launch",
      "module": "uvicorn",
      "args": [
          "pid_api.main:app",
          "--reload",
          "--port", "8000"
      ],
      "env": {
          "FLASK_DEBUG": "14",
          "APP_SETTINGS": "project.server.config.DevelopmentConfig",
          "CELERY_BROKER_URL": "redis://localhost:6379/0",
          "CELERY_RESULT_BACKEND": "redis://localhost:6379/0",
          "POSTGRES_URL": "postgresql://postgres:example_password@localhost:5432/ipidDB",
          "LOG_LEVEL": "info",
          "FDS_OAUTH_TOKEN_BASEURL": "https://xc.eu1.sws.siemens.com",
          "FDS_IM_API_BASEURL": "https://cloud.eu1.sws.siemens.com/api/im/v3",
          "FDS_TECH_USER_ID": "ipiddev-techuser",
          "FDS_TECH_USER_SECRET": "g00C93bcQtr45Y0w",
          "FDS_TENANT_NAME": "ipiddev",
          "TOKEN_CACHE_SECONDS": "300"
      },
      "jinja": true
    }
  ]
}

```

### BFF API

```python
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Python: FastAPI",
      "type": "debugpy",
      "request": "launch",
      "module": "uvicorn",
      "python": "${workspaceFolder}/.venv/Scripts/python.exe",
      "args": [
        "run:app",
        "--reload",
        "--port",
        "8080",
      ],
      "jinja": true,
      "env": {
        "APP_URL": "http://localhost:8000"
      },
    }
  ]
}

```