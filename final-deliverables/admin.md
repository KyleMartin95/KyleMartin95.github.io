Chickenbus Admin Document
===================


This document contains all information regarding using, deploying, recovering, and changing the ChickenBus site.

----------


Using ChickenBus
-------------

####  Search page

On this page you can search for different bus routes. In order for it to work, the suggested places must be clicked before pressing search.

####  Register page

This page allows you to register fan account on ChickenBus. Provide a username, email , and password

####  Login Page
This page allows you to login to your ChickenBus account. Provide your username and password

#### Route Entry

This page allows you to create bus routes. Add all the information in the fields. Then you can preview the route to make sure it looks right. If so you can submit it to the database.

#### Bulk Entry
Another option is to upload a csv file, in the following format

|Name	|Cost	|Stops	|Sunday	|Monday	|Tuesday	|Wednesday	|Thursday	|Friday	|Saturday	|Duration	|Notes|
| ------- | --- | ------------------ | -----| -----| -----| -----| -----| -----| -----| -----| -----|
|Esteli - Matagalpa	|15	|Esteli nicaragua, Matagalpa nicaragua		|	| | | | | | | 23| notes|

Installing ChickenBus
-------------
- Install [Node](https://nodejs.org/en/)
- Frontend:
    - Clone the repo found [here](https://github.com/KyleMartin95/ChickenBus-Frontend)
    - In the root directory of the repo run `npm install` in a command line interface
- Backend:
    - Clone the repo found [here](https://github.com/KyleMartin95/ChickenBus-Backend)
    - In the root directory of the repo run `npm install` in a command line interface
- Mobile:
    - Download the [Expo](https://expo.io/) app from the app store on your phone.
    - Clone the repo found [here](https://github.com/KyleMartin95/ChickenBus-Mobile)
    - In the root directory of the repo run `npm install` in a command line interface

Changing the System
-------------
- Frontend:
    - The front end uses React with the entry point in `/dist/index.html`
    - We use webpack to bundle files in `/src/*` and then output them into the `/dist/` folder.
    - To make changes to the front end you must change the files in `/src/*`
    - We use React for the project. Each React component has a component folder structure that is described in the readme.md of the front end repository.
    - To make a new component do the following in the `src/components/` folder
        1. Create a directory for the component with the same name as the component.
        2. Create a file for its props with the name format ComponentName.Props.ts
        3. Create a file for the default css styles to apply to the component with the name format ComponentName.styles.ts
        4. Create a file for the component with the name formate ComponentName.tsx
        5. Create an index file that will export the props and components with the name index.ts
        6. Add an export statement to the index.ts file in the component directory that will export all files from the component's index file.
        7. You can now use this component in any other component by writing `import { componentName } from 'path to component from current file'` at the top of the component file you want to use it in.
        8. There is a component called example that has boilerplate code that you cna use as a starting point.
    - The app uses the basepage component as an entry point for our React components.

- Backend:
    - The api is divided into different sections in the `app/api` folder.
    - The files in that directory deal with handling different route requests.
    - You can add a route in the `api-router.js` file in that folder.
    - Any route added can also make use of the controllers in `app/controllers` which have the meat of the backend's functionality. Here you will find the functions that are described in the repo's readme.

- Mobile:
    - To start the app run `npm start` this will cause a QR code to pop up on the terminal. In the expo app on your phone you can scan this QR code
    - Most of the stuff you will want to change is in the App/Components or App/screens folder.
    - Any changes made to the system in these files will cause the app to restart on your phone automatically upon saving

Deploying ChickenBus
-------------
- Frontend/Backend
    - In order to push changes to the actual website, first push your changes to the master branch of the github repository
    - Then navigate to the [Cloudapps admin console](https://console.cloudapps.unc.edu/console/project/einsler/overview). You must be on the UNC network to do so. If you are off campus, use the vpn
    - Click on the builds button on the left and then click builds again
    - Click on chickenbus-frontend (or backend)
    - In the upper right hand corner, click start build. This process will take a few minutes.

- Mobile:
    - If you want to make the app publically accessible you can publish the application using expo

- Important notes about building/deploying the system:
    - If for some reason the database is down/taken down, you must get it up and running before starting the backend.
    - You can change the amount of pods being used for each container by clicking on the circle for each part of the app and using the up or down arrows next to the big circle. You can use these to take the system offline by reducing the amount of pods down to zero
    - If the build or deployment fails for any reason, you can check on the logs by going to the build and clicking logs.
