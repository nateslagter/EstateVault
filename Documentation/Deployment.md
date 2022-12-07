# Deployment
## Database
- Postgres is used to store all of our user information.
- Through [PostgreSQL installer](https://www.postgresql.org/download/), download PostGreSQL server, stack builder, and pgadmin 4. (Process is simpler if during installation you use defaults like postgres for username and 5432 for port.)
- In stack builder, select PostgreSQL server, open the Database Drivers tab, and install npgsql.
- The following guide will use `PGADmin 4`. Follow these steps to replicate the database on your local environment.
    - In the `Browser` tab, right click `Servers`, select `Register`, and then select `Server`.
    - In the `Name` field of the General tab, input `estatevaultdb`.
    - Next, switch to the `Connection` tab.
    - In the `Host name/ Address` field, insert the following endpoint:
    `estatevaultdb.csf5v0dcdkkv.us-east-2.rds.amazonaws.com`
    - Leave `Maintenance` and `Username` fields as default.
    - The password is `password`.
    - Select the `Save` button at the bottom of the window.
    - The database should now be located under the servers tab with the proper name of `estatevaultdb`.

## Frontend
- In [Visual Studio Code](https://code.visualstudio.com/download), open the project and type `cd frontend` into the terminal.
- Type `npm install` into the terminal.
- Now type `npm run dev` into the terminal.
- The frontend is now running.

## Backend
- Docker Desktop should prompt to install automatically when building for the first time. If it does not, you may download it from https://www.docker.com/products/docker-desktop/.
- To start the backend, you can either load the project in Visual Studio by opening the SLN file located at `\bsu.estatevault\api\EstateVaultAPI\EstateVaultAPI.sln`, or you can navigate to the `\bsu.estatevault\api\EstateVaultAPI` in your terminal of choice.
- Run the following commands:
    - `docker compose down`
    - `docker compose build`
    - `docker compose up`.

## Start and Stop System
- Closing the terminal in VS Code will terminate the frontend.
- In VS, clicking the stop icon at the top will terminate the backend.
    - If running from the docker container, you can use `docker compose down` or select the `Stop` icon in Docker Desktop.
- Closing PGAdmin will stop the database server.
## Troubleshooting
- If the frontend is having trouble connecting to the backend, make sure it is running and the server connection is set up. (see above)
- Some calls to the backend take a minute, so when sending forms, be patient.
## Source of Errors
- If you make any changes to the backend, you will need to run the above Docker commands or they will not be reflected on the frontend.
- Most errors come from the backend and database connection not being set up properly.  This connection allows the whole system to run so it is important.
- If the calls from the frontend return a 400 (this can be seen by inspecting element and opening the browser console), this means the database is not connected.
- The website will also handle errors that are sent back from the API. If an operation does not complete, the frontend will prompt the user as such.
- When this happens, restart PGAdmin 4 and refresh the database connection in the server connection window in Visual Studio.
- You also may need to restart the Docker container by following the steps above and remaking the container entirely.
## Critical or Vulnerable Pieces
- All three pieces need to be open and running for the project to work properly!  If the frontend, backend, and database are not working, users will not be able to log in and documents cannot be uploaded to AWS.
- If all of these things are running, the system should work accordingly.
