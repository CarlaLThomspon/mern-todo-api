# project mern-todo-proj/mern-todo-app

## Medium Article ##
(https://codingthesmartway.com/the-mern-stack-tutorial-building-a-react-crud-application-from-start-to-finish-part-2/)

## Features
  - Node.js Express Web Server*
  - Express: Light weight Web Server from Node.js
  - Body-parser: Middleware - Parses HTTP Request Body/Allow JSON parsing
  - Cors: Middleware - Expose Resources/Routes to be called from React GUI
  - Mongoose: Object Data Modeling (ODM) library for MongoDB and Node.js
  - MongoDB: a document database
  - Nodemon: Utility monitors for any changes in source, restarts server

### Installation dependencies
```
$ npm init -y
$ npm install express body-parser cors mongoose
$ npm install -g nodemon
```
You should see **NPM** download a lot of files. Once it's done you'll find all the downloaded packages under the **node_modules** directory.

### Start a MongoDB Server
```
bash
$ mongod --dbpath=/data
NETWORK  [thread1] waiting for connections on port 27017
```

### Connect to the running MongoDB Server and create todos collection
```
bash
$ mongo

> use todos
switched to db todos

> db.todos.deleteMany({})
{ "acknowledged" : true, "deletedCount" : 4 } - deletes all

>db.todos.find()
{ "_id" : ObjectId("5dbfb6b147875d3b0716ca01"), "todo_description" : "My first todo", "todo_priority" : "Medium", "todo_completed" : true, "__v" : 0 } - show all
```


### Troubleshooting:  MondoDB shuts down with Code 100
```
MongoDB needs a folder to store the database.
Create the “db” directory.
This is where the Mongo data files will live.
You can create the directory in the default location on macOs by running:

$ sudo mkdir -p /data/db

Make sure that the /data/db directory has the right permissions by running:

$ sudo chown -R $(whoami) /data
$ sudo chown -R $(whoami) /data/db

Retry starting MongoDB in a separate terminal

$ mongod --dbpath=/data

You should see the **mongod** process start up and print some status information.
```

###  Run Express Web Server in a separte terminal:
```
$ node server.js
```

## Postman: Send HTTP Requsts to test Endpoints ##
(https://www.getpostman.com/)

Verify all endpoints are working as expected before connecting to the React GUI/Frontend

## GET /todos - List All Todos
- http://localhost:4000/todos

## POST /todos/add - Add a Single Todo
- http://localhost:4000/todos/add

## GET /todos/<id> - Get a Single Todo
- http://localhost:4000/todos/5dbfb6b147875d3b0716ca01

## POST /todo/update/<id> - Change/Update Existing Todo
- http://localhost:4000/todos/update/5dbfb6b147875d3b0716ca01