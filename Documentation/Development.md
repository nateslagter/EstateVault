# Deployment

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
 
## Required IDEs, Frameworks

- No required IDE
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
- run 'npm install' in the terminal
- run 'npm run dev' in the terminal
- Navigate to the url given in the console (the default is localhost:5173)
