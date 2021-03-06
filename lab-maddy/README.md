# Documentation:

### What this project does:
   The goal of this project is to practice using express, Mongo and mongoose.

  * We will be able to work with the MongoDB database management system
  * We will understand the primary concepts of working with a NoSQL database management system
  * We will be able to create custom data models *(schemas)* through the use of mongoose.js
  * We will be able to use mongoose.js helper methods for interacting with their database persistence layer

#### Feature Tasks
  * create an HTTP Server using `express`
  * create a resource **model** of my choice that uses `mongoose.Schema` and `mongoose.model`
  * use the `body-parser` express middleware to parse the `req` body on `POST` and `PUT` requests
  * use the npm `debug` module to log the functions and methods that are being used in my application
  * use the express `Router` to create a route for doing **RESTFUL CRUD** operations against your _model_

# Any resources that helped me complete this assignment:
- http://mongoosejs.com/docs/index.html

# How another dev could 'get started' with my api on their own:
      - How do you clone this project?
      First fork from my repository, then clone from your repo, then create a branch.
      - How do you start using this project?
          1. You will need to have NodeJS installed on your machine.
          2. You will need to install httpie in one terminal window.
          3. Then start up nodemon in a separate terminal window.


# Mongo database steps:
1. Create a toy directory in the data directory.
2. Have four windows open in terminal.
3. First window- 'mongod --dbpath ./data/db'

4. Second window- 'npm install mongodb' within the lab-maddy/data/db folder to start the mongo shell (to be able to see the database data)
  - should see:
    MongoDB shell version v3.4.7
    connecting to: mongodb://127.0.0.1:27017
    MongoDB server version: 3.4.7
    Welcome to the MongoDB shell.
    For interactive help, type "help".

5. Third window- 'npm run start:watch' within the lab folder of the project(ie- lab-maddy) to get the server running and listening for changes
6. Back in second window- 'mongo'

7. In forth window within lab-maddy folder, use this one to ping your server and make http requestss-

'http POST :3000/api/toy name=gavin desc=human'

* If the name and desc are not strings, mongo will throw a 400 error.

should see:
```
HTTP/1.1 201 Created
Allow-Access-Control-Headers: *
Allow-Access-Control-Origin: *
Connection: keep-alive
Content-Length: 150
Content-Type: application/json; charset=utf-8
Date: Thu, 07 Sep 2017 15:37:08 GMT
ETag: W/"96-NeBQ0TqCqht21DpkTG/FZh+C+bs"
X-Powered-By: Express

{
    "__v": 0,
    "_id": "59b167a41f2258fbdb489cc1",
    "createdAt": "2017-09-07T15:37:08.242Z",
    "desc": "human",
    "name": "gavin",
    "updatedAt": "2017-09-07T15:37:08.242Z"
}
```

8. Back in the second window- 'show dbs'
  - should see:
  admin    0.000GB
  local    0.000GB
  toy-dev  0.000GB

9. Then type- 'use toy-dev'
  - should see:
  switched to db toy-dev

10. Then type- 'show collections'
  - should see:
  toys

11. Then- 'db.toys.find()'. To make sure toys are being posted.
    Should see:
    ```
    { "_id" : ObjectId("59b167a41f2258fbdb489cc1"), "updatedAt" : ISODate("2017-09-07T15:37:08.242Z"), "createdAt" : ISODate("2017-09-07T15:37:08.242Z"), "name" : "gavin", "desc" : "human", "__v" : 0 }
    ```

    - db.toys.drop() will drop those collections

# NOTES FOR MYSELF:
- On lab 13 Tests are passing at 81.54%
- need to keep working on them
- but also need to start lab 14 now 3pm on 9/7s

HOW TO TEST POST IN Mongo:

http POST :3000/api/toy name=gavin desc=human

HOW TO TEST GET with Mongo:

http GET :3000/api/toy/f18a6d2b-753c-41f6-9c28-d2a7f0b41f21


```

```

HOW TO TEST A PUT IN Mongo:



HOW TO TEST DELETE IN Mongo:


# Packages and commands to remember:
For Mongo:
- To install Mongo-- npm install mongodb into your project directory
- Start the MongoDB process-- mongod
- Start the MongoDB shell-- mongo

For Mongoose:
- To install mongoose-- $ npm install mongoose

General:
  - In package.json's scripts, add- "start:debug": "DEBUG=http* nodemon server.js",
  - created an index.js and set it as the start point in package.json
  - deleted parse-url.json and ________
  - added a cors.js file

  - npm install express - DONE
  - npm install (for node modules) -
  - npm install httpie -
  - npm install superagent -
  - npm install uuid -
  - npm install -D jest -
    - npm test

  - node server.js or just nodemon (depending on the day??)
    - rs (restart, if needed)
  - run start: watch -
  - npm run start:debug - then attempt a POST and this will tell you where you're wrong

  - npm run debugger -
  - npm install bluebird (sets this as a dependency in package.json) -

# Notes:
  - Don't forget to git ignore your `db/` dir

  - I added the following to my package.json scripts:
  "debugger": "node inspect server.js",

  - I've added the server.js to the lib directory.

  - Then in terminal, within the project directory, type:
  npm run debugger
    - You should then see:
    > node inspect server.js

  - troubleshooting seeing ECONNREFUSED in terminal:
    - open another window and run 'mongod --dbpath ./data/db'



# Collaborators:
Isaac and Said.
