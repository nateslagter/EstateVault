# Deployment
## Database
- Postgres is used to store all of our user information.
- Through PostgreSQL installer[https://www.postgresql.org/download/], download PostGreSQL server, stack builder, and pgadmin 4. (Process is simpler if during installation you use defaults like postgres for username and 5432 for port.)
- In stack builder, select PostgreSQL server, open the Database Drivers tab, and install npgsql.
- Using the pgadmin 4 gui, drop down the server tab, then drop down postgresql 15, and right click the "Databases" tab and create a new database and name it "estatevaultdb" using the "database" field. Then, right click on it > restore. Then, for "filename", navigate to `bsu.estatevault/API/EstateVaultDB/dbb.sql` and select to automatically create and populate schema.
## Server
AS OF THIS ITERATION, THE DATABASE CANNOT BE LINKED TO VISUAL STUDIO ON MAC
- Running the backend server is done through the Visual Studio community[https://visualstudio.microsoft.com/].  
- When VS is downloaded, click the button to open solution. 
- The file you are looking for is `bsu.estatevault/API/EstateVaultAPI/EstateVaultAPI.csproj`.  
- Once this opens, navigate to `bsu.estatevault/API/EstateVaultAPI/Repos/UserRepo.cs` and on line 11, change the `Password=~~~~~` to `Password=[your postgres password]`. 
- Next click tools at the top and "Manage NuGet Packages", or "Extensions", search for `NPGSQL PostgreSQL Integration` and install it.  VS will need to restart to make these changes.
## Server and Database Connection
- In Visual Studio, click the search bar in the top and type in server explorer and open this new tab.
- Right click on Data Connections > Add a connection.
- Change Data Source to PostgreSQL Database > OK (without the aformentioned extension, this selection will not be in the list).
- Set Host to "localhost", Port to what you specified during PostgreSQL installation (default 5432), Database to "estatevaultdb", and enter the username and password you set up when installing postgres.
- Click Test Connection to make sure the connection succeeds, then click Ok.
- You should now have VS linked to your local PostgreSQL database.
- Click build at the top and build solution.
- Now hit the play button to run the backend.
## Frontend
- In VS Code, open the project and type `cd frontend` into the terminal.
- Type `npm install` into the terminal.
- Now type `npm run dev` into the terminal.
- The frontend is now running.
## Start and Stop System
- Closing the terminal in VS Code will terminate the frontend.
- In VS, clicking the stop icon at the top will terminate the backend.
- Closing PGAdmin will stop the database server.
## Troubleshooting
- If the frontend is having trouble connecting to the backend, make sure it is running and the server connection is set up. (see above)
- Some calls to the backend take a minute, so when sending forms, be patient.
## Source of Errors
- Most errors come from the backend and database connection not being set up properly.  This connection allows the whole system to run so it is important.
- If the calls from the frontend return a 400 (this can be seen by inspecting element and opening the browser console), this means the database is not connected.
- When this happens, restart PGAdmin 4 and refresh the database connection in the server connection window in Visual Studio.
## Critical or Vulnerable Pieces
- All three pieces need to be open and running for the project to work properly!  If the frontend, backend, and database are not working, users will not be able to log in and documents cannot be uploaded to AWS.
- If all of these things are running, the system should work accordingly.
