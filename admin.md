Chickenbus Admin Document
===================


This document contains all information regarding using, deploying, recovering, and changing the ChickenBus site.

----------


Using ChickenBus
-------------

####  Search page

On this page you can search for different bus routes. In order fo it to work, the suggested places must be clicked before pressing search.

####  Register page

This page allows you to register fan account on ChickenBus. Provide a username, email , and password

####  Login Page
This page allows you to login to your ChickenBus account. Provide your username and password

#### Route Entry

This page allows you to create bus routes. Add all the information in the fields. Then you can preview the route to make sure it looks right. If so you can submit it to the database.

Another option is to upload a csv file to

Deploying ChickenBus
-------------
- Clone the repo found [here](https://github.com/KyleMartin95/ChickenBus-Frontend)
- Install [Node](https://nodejs.org/en/)
- In the root directory of the repo run `npm install` in a command line interface
- In the root directory of the repo run `npm run start`


Changing the System
-------------
- To change the front end, you must make changes to the front end repo found [here](https://github.com/KyleMartin95/ChickenBus-Frontend)
    - The front end uses React with the entry point in `/dist/index.html`
    - We use webpack to bundle files in `/src/*` and then output them into the `/dist/` folder.
    - To make changes to the front end you must change the files in `/src/*`
    - We use React for the project. Each React component has a component folder structure that is described in the readme.md of the front end repository. Follow the instructions there for making a new component.
    - The app uses the basepage component as an entry point for our React components.

- To change the back end, you must make changes to the back end repo found [here](https://github.com/KyleMartin95/ChickenBus-Frontend)
    - The app uses a seperate backend repo for our api.
    - The api is divided into different sections in the `app/api` folder.
    - The files in that directory deal with handling different route requests.
    - You can add a route in the `api-router.js` file in that folder.
    - Any route added can also make use of the controllers in `app/controllers` which have the meat of the backend's functionality. Here you will find the functions that are described in the repo's readme.

