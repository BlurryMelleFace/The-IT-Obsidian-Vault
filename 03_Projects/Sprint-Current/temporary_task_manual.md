So It seems like you know my repository. we have worked on the authentifications ervice and the user service . we are now able to recive the all the users of a specific tenant. via the get tenant users function. 

Now there is one thing which we will need to do now. 

Basically we have the jobs endpoint right: @router.get(

    "/jobs",

    summary="List all jobs",

Basicaly thi scalls the get jobs function in the database utility. 

Now the jobs currently also return the userid database which is good:                         {

but I in the fronend we want to display the names of the users and not the userid. 

So what I want you to do is to call the get tenant users functions when we call the get jobs api endpoint and map the jobs userids we recive from the database to the proper user name and return that payload.    

async def get_jobs(self, tenantID: str = 'tenantId'):

        try:

            if tenantID is None:

                tenantID = "tenantId"

            logger.info("inside get_jobs in task_utility")

            db_utility = DbUtility()

            jobs = await db_utility.get_jobs(tenantID)

            # Check if jobs is None

            if jobs is None:

                logger.warning(f"No jobs found for tenantID: {tenantID}")

                return []

            # Ensure jobs are JSON-serializable

            return jsonable_encoder(jobs)
So my guess is to do it somewhere here...