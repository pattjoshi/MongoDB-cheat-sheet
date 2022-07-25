# MongoDB-cheat-sheet

## In this Section, You will see a comprehensive list of all the mongodb commands you will ever need as a mongoDb beginner.This list covers almost all the most used commands in MongoDB.

 [Download MongoDB Community Server](https://www.mongodb.com/try/download/community)

[MongoDB-cheat-sheet](https://github.com/pattjoshi/MongoDB-cheat-sheet/blob/master/MongodB_cheat_sheat.md)

# What is MongoDB ? 
- MongoDB is a document database for ease for development and scaling.
- It is easy to use NoSQL Database.

# Difference between mongo and mongod ?
- "mongo" is the command-line shell that connects to specific instance of mongod.
- "mongod" is the 'Mongo Daemon' it's basically the host process for the database. 

# Compairison of MOngoDb with MySQL

<img width="432" alt="image" src="https://user-images.githubusercontent.com/78966839/175813896-0afebbf9-004d-47c8-a97d-67757641c770.png">


# SQL   VS NoSQL
*******
## SQL :-
- RDBMS IS a relational database management system and works on relational database.
- hear we create data base.
- it stores data n form of entity as tables.
- it use SQL to query database.(My sql,PostgreSQL )

*******************
## NoSQL:-
- it's non-relational, document-oriented data management system and woeks on document-based database.

- hear we create data base.
- MongoDb stores data in form of documents.
- MongoDB uses [BSON](https://www.mongodb.com/json-and-bson)    to query database.

<img width="424" alt="image" src="https://user-images.githubusercontent.com/78966839/175946142-bc2a3d30-291b-4088-9a21-8f4dacffa570.png">

*****
[Difference Between JSON and BSON](https://www.educba.com/json-vs-bson/)
****

# practice question

<img width="429" alt="image" src="https://user-images.githubusercontent.com/78966839/175993078-ef800054-8c21-4390-a1ff-81fff834de23.png">

# practice question (Update)
<img width="431" alt="image" src="https://user-images.githubusercontent.com/78966839/176003832-2d3913a3-25c4-4f5c-ac8b-58fdfb88457a.png">

# practice question (Delete the Documents)
<img width="432" alt="image" src="https://user-images.githubusercontent.com/78966839/176007383-70151f99-79b1-4b00-9800-1eaace6635f8.png">


# learning setup
<img width="951" alt="image" src="https://user-images.githubusercontent.com/78966839/175994774-7cd9dd28-4a94-416b-974f-7c987f7635fb.png">

# MongoDB GUI Compass
<img width="945" alt="image" src="https://user-images.githubusercontent.com/78966839/176168087-d111495e-0e05-4a09-ac2c-45a82b26c06b.png">

# Mongoose
- it helps us to established a connection between node.js and mongodb.

- Mongoose is an Object Data Modeling (ODM) libray for MongoDB and Node.js is manages relationships data. Provide Schema Validation, and is used to translate between "objects" in code and the representation fo those objects in MongoDB.
- It Provides an abstraction layer on top of MongoDB that eliminates the need to use named collaction.

<img width="802" alt="image" src="https://user-images.githubusercontent.com/78966839/180440986-1f99583e-a5b8-4250-bbe4-1c0432347a95.png">

**********

#  Connect NodeJS, Express to MongoDB using Mongoose

# what is connect method? 
- it's a method that mongoose has that connects to mongodb and returns a promise that resolves to a connection object that we can use to interact with the database and create models.

********

## connection created and create a new db called learnDb_dashboard
```
const mongoose = require("mongoose");

mongoose
  .connect(
    "mongodb://localhost/learnDb_dashboard",
    { useNewUrlParser: true },
    { useUnifiedTopology: true }
  )
  .catch((err) => console.log(err))
  .then(() => console.log("Connected to MongoDB")); // if no error, then console.log("Connected to MongoDB");
```

# explain mongose.connect
- mongose.connect is a method that mongoose has that connects to mongodb and returns a promise that resolves to a connection object that we can use to interact with the database and create models.
- mongose.connect takes two arguments:
- 1. the url of the database
- 2. an object that contains options for the connection
- the options object can contain the following properties:
- useUnifiedTopology: true
- useNewUrlParser: true
- useCreateIndex: true
- useFindAndModify: false








## 🙏 If you find this repo helpful then don't forget to give a star ❇️ to this repository. :)
