---
tags:
  - web
  - python
  - fast-api
  - framework
  - backend
---

# FastAPI

> [!INFO]
> **FastAPI** is a modern, fast (high-performance) web framework for building APIs with Python 3.8+ based on standard Python type hints.

**Related Notes:**
- [[Python]] – Language foundation.
- [[Poetry]] – Dependency management.
- [[Ide]] – Debug configurations for FastAPI.

---

## 🚀 Running with Uvicorn

1. **Dev Mode** (Auto-reload):
   ```shell
   uvicorn run:app --reload
   ```
2. **Specify Host/Port**:
   ```shell
   uvicorn run:app --host 0.0.0.0 --port 8000
   ```
3. **Debug Logging**:
   ```shell
   uvicorn run:app --reload --log-level debug
   ```
4. **Production** (Workers):
   ```shell
   uvicorn run:app --workers 4 --host 0.0.0.0 --port 8000
   ```

## 📝 Code Snippet (`run.py`)
```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def read_root():
    return {"message": "Hello World"}
```

## 📦 Install
```shell
poetry add fastapi uvicorn
# OR
pip install fastapi uvicorn
```