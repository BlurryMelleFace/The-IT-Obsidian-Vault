---
tags:
  - prompts
  - testing
  - qa
  - construction-kit
---

# Test Writing Construction Kit

> [!INFO]
> A modular kit for building test generation prompts. Copy the sections you need.

## 🧱 1. Basic Context
```plaintext
For the following prompt, I have appended some files that you need to review to understand the topic.
```

## 🧪 2. Test Generation Request
```plaintext
Please help me write test cases for the appended functionalities and functions.
```

## 🛠️ 3. Technology Specifics

### FastAPI
```plaintext
Be sure to follow FastAPI's conventions to ensure that these tests are fully compatible and up to standard with the current tech stack.
```

### Python (Pytest)
```plaintext
Ensure the tests are written in pytest and follow best practices for modularity and maintainability.
```

### Docker
```plaintext
Make sure the tests account for running inside a Docker container and handle containerized dependencies properly.
```

## 🔌 4. API Testing
```plaintext
Write API test cases that verify endpoint availability, request validation, authentication, and data consistency.
```

## ✅ 5. Final Review Criteria
```plaintext
Ensure test coverage meets requirements, aligns with coding standards, and all edge cases are covered.
```
