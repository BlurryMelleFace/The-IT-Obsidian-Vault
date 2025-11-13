# Refined Development Prompt

We’ve successfully implemented the **Authentication Service** and **User Service** in the repository. At this stage, we can retrieve all users belonging to a specific tenant using the `get_tenant_users` function.

Now, the next step is to enhance the **Jobs endpoint** functionality.

---

### Current Behavior

The `/jobs` endpoint is defined as:

```python
@router.get(
    "/jobs",
    summary="List all jobs",
)
```

This endpoint currently invokes the `get_jobs` function within the database utility. Each job record returned from the database includes a `userId` field, which correctly references the associated user.

---

### Goal

In the frontend, we want to **display user names** instead of user IDs. To achieve this, we need to enhance the backend logic so that the `/jobs` endpoint:

1. Calls the existing `get_tenant_users` function to fetch all users for the specified tenant.  
2. Maps each job’s `userId` to the corresponding user’s name.  
3. Returns the enriched payload, where each job includes a `userName` field instead of (or in addition to) `userId`.

---

### Suggested Implementation Location

The ideal place to integrate this logic is inside the following function:

```python
async def get_jobs(self, tenantID: str = 'tenantId'):
    try:
        if tenantID is None:
            tenantID = "tenantId"
        logger.info("inside get_jobs in task_utility")
        db_utility = DbUtility()
        jobs = await db_utility.get_jobs(tenantID)

        if jobs is None:
            logger.warning(f"No jobs found for tenantID: {tenantID}")
            return []

        # TODO: Map userIds to user names using get_tenant_users
        return jsonable_encoder(jobs)
```

---

### Summary of the Required Change

- Fetch tenant users via `get_tenant_users(tenantID)`.
- Create a mapping `{userId: userName}`.  
- Use this mapping to replace or augment `userId` fields in the `jobs` list.  
- Return the updated, JSON-serializable payload.

---

This will ensure that the frontend receives complete job data with human-readable user information, improving the clarity and usability of the interface.
