I added a **database migration script** that runs automatically at startup to make sure the `jobs` table schema is up to date.  

Specifically, I wrote an **idempotent migration function** that:

- Connects to the database via the shared SQLAlchemy engine (`DbConnection.engine`).
    
- Checks whether certain columns (like `userid` or `createdby`) exist in the `jobs` table.
    
- Executes raw SQL queries (`ALTER TABLE ...`) to add or remove columns if needed — safely and repeatably.

Was in some sbom meetings with lars rahul and georg

Today I will try and add a service layer in the API so we can call other APIs in our current case to fetch user information based on a user ID from the `FDS_USERS_API_ENDPOINT`