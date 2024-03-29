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
- /views contains the display for each of the routes including the javascript, css, and html in each .vue file
- /components contains vue code for individual components of the views, such as the sidebar which is used multiple times through the pages
- /assets contains the images and some of the css for the frontend
- package.json contains all of the dependencies for the projects and scripts than can be run within it
- router/index.ts contains the logic for setting up routes on the webpage

## Important Vue config files

- tsconfig.vitest.json has code required to run Vue tests via Vitest
- vite.config.ts

## How to Test Vue
- run `npm install` to install dependencies, and run `npm run test`
- run `npm run coverage` to see the code coverage with [c8](https://github.com/bcoe/c8)

## How to Run the Vue 
- Navigate to the `/frontend` folder
- run 'npm install' in the terminal
- run 'npm run dev' in the terminal
- Navigate to the url given in the console (the default is localhost:5173)
- this will start you on the welcome page

## API Folder Structure
- /api contains all source code for the api
- /controllers contains the api's controllers
- /service contains the service layer classes
- /repo contains the repository classes
- /models contains data models for the API
- /tests contains all tests, unit and integration
- /properties contains api project settings, such as swagger integration

## Building the API
- Navigate to `Build` in VS, or see Docker setup below.

## Running the API
- Run `git clone https://bitbucket.org/accutechcapstone/bsu.estatevault/src/master/` to retrieve the repo and store it wherever you please.
- Open the estatevaultapi.sln vile in Visual Studio.
  - The necessary packages will automatically install.
- To run the tests, you can either run `dotnet test` or run tests from the test menu.
- Similarily, to build the project, you may use `dotnet build` or run from the Build option in the toolbar.
- To run the project, you may use `dotnet run` or Click `EstateVaultApi` from the toolbar to run the project.
- SwaggerHub docs will be brougnt up automatically. You can make requests to the API and it will return the proper result.
## Migrations
- The migrations for this project are finicky. If you are running tests, you must delete the `Migrations` folder within Visual Studio. If replicating via Docker, you can either keep the migration folder or run `Add-Migration EstateVaultMigrations`. The connection string MUST be set to the local postgres database if this is the case.
## API Tests
- To run the tests for this project, you will need to create a local instance of our Postgres Database. The file, `estateVaultDump.sql`, can be found in the `api/EstateVaultApi` folder. 
    - On Windows, open command prompt and navigate to wherever you cloned the repository, and navigate to the above mentioned folder.
    - `psql -U postgres` . Input your local password.
    - Run `create database estatevaultdb;`. 
    - Run the command `psql -U postgres estatevaultdb < estateVaultDump.sql`.
- You can now run the tests. In `AppSettings.json`, the ConnectionString key should have a value of `"ConnectionString": "Host=localhost; Port=5432; Database=estatevaultdb; Username=postgres; Password=Indy!441"`.
- Ensure the Migrations folder is deleted before running the tests. They will conflict with the local postgres db.
- To execute the tests, you will first need to build a running solution. Execute 'dotnet build' in the VS terminal to build the program. The .net 6.0 SDK comes with the cli bundled.
- 'dotnet test' will run all unit tests in the solution. 

## Replicating via Docker
- The connection string must be set to `"ConnectionString": "Host=estatevault-db; Database=estatevaultdb; Username=postgres; Password=password`.
    - The last two fields will be filled in with your own personal postgres information.
- The migrations folder must be in place. See above to restore it.
- You may also need to uncomment out the line `db.Database.Migrate()` in the `program.cs` file to work with Docker.
- After opening the API in VS, run the following three commands in the developer powershell:
    - `docker compose down`
    - `docker compose build`
    - `docker compose up`
 - These may not work the first time. If this happens, run :
     - `psql -U postgres estatevaultdb < estateVaultDump.sql`.
     - Then, run the above three commands again.
- After these are done running, you can navigate to `localhost:5001/swagger/index.html` and access the Swagger docs. The frontend is already configured to use the docker ports.

## Linting and Formatting
- Lint the program by running `npm run lint` in the bsu.estatevault directory.  Adding the `--fix` flag will fix any simple errors or warnings
- The linting guidelines can be found in the `.eslintrc.json` file in the frontend directory
- Format the code using Prettier with `npm run format`
- The formatting guidelines can be found in the `.prettierrc.json` file in the frontend directory
