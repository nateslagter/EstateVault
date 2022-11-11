# Development

## Tech aspects

Tech stack is:
- Vue with TypeScript
- .Net with C#
- AWS S3
- PostgreSQL
- Docker
- BitBucket

## Technologies Needed

- node v16.9 to run any `npm` scripts
- .NET 6.0 SDK
- PostgreSQL
- Postman (Optional)
 
## Required IDEs, Frameworks

- Visual Studio 2022 w/ ASP.NET development package is required to run this program. VSCode can be used to run tests, but plugins are needed.
- Need a terminal to run the program
- Using Vue framework

## Vue Folder Structure

- src has source code
- App.vue is the main Vue file for the frontend; it contains the RouteViewer which allows routes such as "/documents" to be accessed
- /views contains the display for each of the routes
- /components contains vue code for individual components of the views, such as the header which is used multiple times through the pages
- package.json contains all of the dependencies for the projects and scripts than can be run within it
- router/index.ts contains the logic for setting up routes on the webpage

## Important Vue config files

- tsconfig.vitest.json has code required to run Vue tests via Vitest
- vite.config.ts

## How to Test Vue
- run `npm install` to install dependencies, and run `npm run test:unit`

## How to Run the Vue 
- Navigate to the `/frontend` folder
- run 'npm install' in the terminal
- run 'npm run dev' in the terminal
- Navigate to the url given in the console (the default is localhost:5173)

## API Folder Structure
- /api contains all source code for the api
- /controllers contains the api's controllers
- /service contains the service layer classes
- /repo contains the repository classes
- /models contains data models for the API
- /tests contains all tests, unit and integration
- /properties contains api project settings, such as swagger integration

## Building the API
- This API requires docker desktop; however, if using VS 2022, Docker Desktop will be installed automatically. Setup for containers TBD.

## Running the API
- Run `git clone https://bitbucket.org/accutechcapstone/bsu.estatevault/src/master/` to retrieve the repo and store it wherever you please.
- Open the estatevaultapi.sln vile in Visual Studio.
  - The necessary packages will automatically install.
- To run the tests, you can either run `dotnet test` or run tests from the test menu.
- Similarily, to build the project, you may use `dotnet build` or run from the Build option in the toolbar.
- To run the project, you may use `dotnet run` or Click `EstateVaultApi` from the toolbar to run the project.
- SwaggerHub docs will be brougnt up automatically. You can make requests to the API and it will return the proper result.

## API Tests
- To execute the tests, you will first need to build a running solution. Execute 'dotnet build' in the VS terminal to build the program. The .net 6.0 SDK comes with the cli bundled.
- 'dotnet test' will run all unit tests in the solution. 
- Additionally, you can make calls to the endpoints by using Postman. This is not required, but can help to gain a better understanding of the functionality of the API.

## Create Local PostgreSQL database with cmd.
- Local database houses stored user information.
- Through PostgreSQL installer, download PostGreSQL server, stack builder, and pgadmin 4 (optional). (Process is simpler if during installation you use defaults like postgres for username and 5432 for port.
- In stack builder, select PostgreSQL server, open the Database Drivers tab, and install npgsql.
- Make sure C:\Program Files\PostgreSQL\15\bin is linked to PATH so commands are functional in cmd
- Utilizing cmd, create a new database and name it "estatevaultdb" with the command `createdb -U [username] estatevaultdb`, then input password.
- navigate cmd to `bsu.estatevault\api\EstateVaultDB` and enter the command `pg_restore -U [username] -d estatevaultdb dbb.sql`, then input password.
- Your local database should now be created.


## Access PostgreSQL database in Visual Studio environment (This does not work for MacOS as VS developers have not implemented  Mac support).
- First you must install the extension "Npgsql PostgreSQL Integration" and restart VS. (Wait for a pop up to finish before reopening)
- Under the View tab at the top of VS, select server explorer and open the server explorer tab.
- Right click on Data Connections > Add a connection.
- Change Data Source to PostgreSQL Database > OK (without the aformentioned extension, this selection will not be in the list).
- Set Host to "localhost", Port to what you specified during PostgreSQL installation (default 5432), Database to "estatevaultdb", and enter the username and password you set up when installing.
- Click Test Connection to make sure the connection succeeds, then click Ok.
- You should now have VS linked to your local PostgreSQL database.  
`You will need to edit line 11 of UserRepo.cs to make sure the respective fields in the dbconnection variable match your personal information used during setup. Otherwise, VS will not be able to access the local database.`
