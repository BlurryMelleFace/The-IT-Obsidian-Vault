## API
```text
.venv/Scripts/Activate.ps1
```

```text
.\automate_pidapi_docker.ps1
```

## BFF
```text
.venv/Scripts/Activate.ps1
```

```text
$env:APP_URL = "http://localhost:8000"
```

```text
uvicorn run:app --reload --port 8080
```

## UI

```text
"API_URL": "http://localhost:8080",
```
