---
tags:
  - devops
  - python
  - task-queue
  - cheatsheet
---

# Celery

> [!INFO]
> **Celery** is an asynchronous task queue/job queue based on distributed message passing. It is focused on real-time operation, but supports scheduling as well.

**Related Notes:**
- [[Docker]] – Often used to containerize Celery workers.
- [[AWS]] – Can use SQS as a broker.

---

## 🐞 Debugging & Inspection

1. **Inspect Registered Tasks**:
   ```shell
   celery inspect registered
   ```

2. **Inspect Active Queues**:
   ```shell
   celery inspect active
   ```

3. **Inspect Scheduled Tasks**:
   ```shell
   celery inspect scheduled
   ```

4. **Show Stats**:
   ```shell
   celery inspect stats
   ```