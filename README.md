
# [MERN QUS](https://spandanjoshi.notion.site/spandanjoshi/cedae34f553b4f3491f11aad442dbb0e?v=2eb63ccf8bc941afa40fcebd724b8ba5&p=c911a56bd2ea432b9a7339c1a4e85d42&pm=s)

# [NAMASTAY JS 🟢](https://alok722.github.io/namaste-javascript-notes/dist/lectures.html)



# MongoDB-cheat-sheet

## In this Section, You will see a comprehensive list of all the mongodb commands you will ever need as a mongoDb beginner.This list covers almost all the most used commands in MongoDB.

 [Download MongoDB Community Server](https://www.mongodb.com/try/download/community)

[MongoDB-cheat-sheet](https://github.com/pattjoshi/MongoDB-cheat-sheet/blob/master/MongodB_cheat_sheat.md)

# What is MongoDB ? 
- MongoDB is a document database for ease for development and scaling.
- It is easy to use NoSQL Database.

# Difference between mongo and mongod ?
- "mongo" is the command-line shell that connects to specific instance of mongod.
- "mongod" is the 'Mongo Daemon' it's basically the **host process** for the database. 

# Compairison of MOngoDb with MySQL

<img width="432" alt="image" src="https://user-images.githubusercontent.com/78966839/175813896-0afebbf9-004d-47c8-a97d-67757641c770.png">


# SQL   VS NoSQL
*******
## SQL :-
- RDBMS IS a relational database management system and works on relational database.
- hear we create data base.
- it stores data n form of entity as **tables**.
- it use SQL to query database.(My sql,PostgreSQL )

*******************
## NoSQL:-
- it's non-relational, document-oriented data management system and woeks on document-based database.

- hear we create data base.
- MongoDb stores data in form of **documents**.
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
- it helps us to established a connection **between node.js and mongodb**.

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

****************

# what is schma?
- it's a blueprint for a collection in mongodb that defines the structure of the data in the collection.
- default value, validators, etc.

```
  // create a new schema for our data
const playlistSchema = mongoose.Schema({
  name: String,
  ctype: String,
  videos: Number,
  author: String,
  date: {
    type: Date,
    dafault: Date.now,
  },
});
```
# what is model?
- it's a class that allows us to create documents in a collection.
- mongoose model provided an interface to the database for creation, querying, and updating of documents.
- class Playlist is a model that we can use to create documents in the collection. 

```
// collaction created in mongoDB
const  Playlist = mongoose.model("Playlist", playlistSchema);
```

# what is document?
- it's an object that represents a document in a collection.
- it's an instance of a model.


# what is collection?
- it's a group of documents.
- it's a group of instances of a model.


```
const createDocument = async () => {
  try {
    // instantiate a new document
    const reactPlaylist = new Playlist({
      name: "Node.js Playlist",
      ctype: "Back End",
      videos: 20,
      author: "Om Prakash Pattjoshi",
    });

    // save the document to the database
    const result = await reactPlaylist.save();
    console.log(result);
  } catch (error) {
    console.log(error);
  }
};
createDocument();
```

## All code

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

// create a new schema for our data
const playlistSchema = mongoose.Schema({
  name: String,
  ctype: String,
  videos: Number,
  author: String,
  date: {
    type: Date,
    dafault: Date.now,
  },
});

// collaction created in mongoDB
const Playlist = mongoose.model("Playlist", playlistSchema);

const createDocument = async () => {
  try {
    // instantiate a new document
    const reactPlaylist = new Playlist({
      name: "Node.js Playlist",
      ctype: "Back End",
      videos: 20,
      author: "Om Prakash Pattjoshi",
    });

    // save the document to the database
    const result = await reactPlaylist.save();
    console.log(result);
  } catch (error) {
    console.log(error);
  }
};
createDocument();


```
# o/p:
<img width="947" alt="image" src="https://user-images.githubusercontent.com/78966839/180745907-6810a0f4-b49b-4674-ac11-58782bdabdd1.png">

************
# Insert Multiple Documents using One Line in Mongoose
```
 // insertmany is used to insert multiple documents
    const result = await Playlist.insertMany([
      reactPlaylist,
      javascriptPlaylist,
      mongoPlaylist,
      expressPlaylist,
    ]);
```

# Insert Multiple doc
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

// create a new schema for our data
const playlistSchema = mongoose.Schema({
  name: String,
  ctype: String,
  videos: Number,
  author: String,
  date: {
    type: Date,
    dafault: Date.now,
  },
});

// collaction created in mongoDB
const Playlist = mongoose.model("Playlist", playlistSchema);

const createDocument = async () => {
  try {
    // instantiate a new document
    const reactPlaylist = new Playlist({
      name: "Node.js Playlist",
      ctype: "Back End",
      videos: 20,
      author: "Om Prakash Pattjoshi",
    });
    const javascriptPlaylist = new Playlist({
      name: "javaScript Playlist",
      ctype: "front-End",
      videos: 150,
      author: "Om Prakash Pattjoshi",
    });
    const mongoPlaylist = new Playlist({
      name: "MongoDB Playlist",
      ctype: "Database",
      videos: 10,
      author: "Om Prakash Pattjoshi",
    });
    const expressPlaylist = new Playlist({
      name: "express.js Playlist",
      ctype: "Back End",
      videos: 33,
      author: "Om Prakash Pattjoshi",
    });
    // insertmany is used to insert multiple documents
    const result = await Playlist.insertMany([
      reactPlaylist,
      javascriptPlaylist,
      mongoPlaylist,
      expressPlaylist,
    ]);
    console.log(result);
  } catch (error) {
    console.log(error);
  }
};
createDocument();

```
## Multiiple doc
<img width="849" alt="image" src="https://user-images.githubusercontent.com/78966839/180749578-22687806-5d7a-405b-9d21-3b7489208674.png">

# Read or Querying the Documents using Mongoose in Express

```
// read all documents
const getDocument = async () => {
  try {
    const result = await Playlist.find({ ctype: "Back End" })
      .select({
        name: 1,
      })
      .limit(1);
    console.log(result);
  } catch (error) {
    console.log(error);
  }
};

getDocument();

```
## O/p:- 
<img width="373" alt="image" src="https://user-images.githubusercontent.com/78966839/180768953-07dcc931-37a2-4dc1-ac25-3653c2e079e8.png">

# [ MongoDB Comparison Query Operators](https://www.mongodb.com/docs/manual/reference/operator/query-comparison/)

## comparison query operator

```
 $gt - greater than
$gte - greater than or equal to
 $lt - less than
 $lte - less than or equal to
 $ne - not equal to
 $in - in
 $nin - not in
 $regex - regular expression
 $exists - exists
 $type - type
```

##  $gt - greater than
```
 const result = await Playlist.find({ videos: { $gt: 20 } }).select({
      name: 1,
    });
```

<img width="392" alt="image" src="https://user-images.githubusercontent.com/78966839/180776662-ec847550-dd54-415d-a6e4-31acf2f5c352.png">

# $in
- $in is used to find the documents that match the criteria in the array provided in the query

```
 const result = await Playlist.find({ ctype: { $in: ["Back End"] } }).select(
      {
        name: 1,
      }
    );
```
<img width="377" alt="image" src="https://user-images.githubusercontent.com/78966839/180778063-84c2f4e5-36a6-4716-8f02-d39728b19c1e.png">

J************
# [MongoDB Logical Query Operators](https://www.mongodb.com/docs/v4.2/reference/operator/query-logical/)

## type of logical operater
- $and :- Both true then true
- $or :- One of true then true
- $nor
- $not

```
 $and: [{ ctype: "Back End" }, { author: "Om Prakash Pattjoshi" }],
```
<img width="353" alt="image" src="https://user-images.githubusercontent.com/78966839/180923031-c7b8cfb9-66e1-4405-81f9-a447eea1f65a.png">

*******
#  Sorting and Count Query Methods 

- count documents is use for counting the number of documents in a collection
```
.countDocuments();
```

- sort method 1 :-accending
- -1 :- decending

```
 .sort({ name: 1 });
```

# [MongoDB Update the Documents](https://www.mongodb.com/docs/mongodb-shell/crud/update/)

```

// update document
const updateDocument = async (_id) => {
  try {
    const result = await Playlist.findByIdAndUpdate(
      { _id },
      {
        $set: { name: "JavaScript Playlist" },
      },
      {
        // new is latest updated Document
        new: true,
      }
    );
    console.log(result);
  } catch (error) {
    console.log(error);
  }
};

updateDocument("62de6712022f0fa8ba036cae");

```

O/p:-
<img width="415" alt="image" src="https://user-images.githubusercontent.com/78966839/181021032-27061ea6-ee13-417d-a384-a08cbe4c2914.png">

**********
# delete document

```

// delete document
const deleteDocument = async (_id) => {
  try {
    const result = await Playlist.findByIdAndDelete({ _id });
    // console.log(result);
  } catch (error) {
    console.log(error);
  }
};
deleteDocument("62de6712022f0fa8ba036cae");

```
# [Mongoose Built-In Validation](https://mongoosejs.com/docs/validation.html)

# [Create Your Own Custom Validation using MongoDB](https://mongoosejs.com/docs/validation.html#custom-error-messages)

```
  videos: {
    type: Number,
    validate(value) {
      if (value < 0) {
        throw new Error("Videos must be greater than 0");
      }
    },
  },
```
*****

# [Using NPM Validator Package for Validation](https://www.npmjs.com/package/validator)

```
npm i validator
```
- adding in schema


# [POSTMAN](https://www.postman.com/)

- Postman is an interactive and automatic tool for varifying the APIs of your project.
- Postman is a Google Chrome app for interactin with HTTP APIs.

- It Presents you with a friendly "GUI" for constructing requests and reading resonses. It Works on the back-end, and makes sare that each API is wirking as intended.

<img width="435" alt="image" src="https://user-images.githubusercontent.com/78966839/181266731-f97b2bb5-ecb2-4e99-975d-aa9aa64af4e2.png">
********
## Postmas GUI:-

<img width="854" alt="image" src="https://user-images.githubusercontent.com/78966839/181274885-7583a121-5d35-4a6d-ba68-3f352f321a42.png">

*********
## REST Api:-
- Representational State Transfer Application Programming Interface
- It is a "software" that allows two applications to cmmunicate with each other over the internet and through various devices.

- Ever time you access on app like facebook or check the weather on our smartphone, on API is used.

<img width="392" alt="image" src="https://user-images.githubusercontent.com/78966839/181291364-447865e1-c6a8-4531-9cc5-38e78ba960cb.png">

- A RESTful API is an architectural style for an application program  interface (API) that uses HTTP requests to access and usr data. 

- REST is nota a programming language.

## HTTP Mehod:-
<img width="425" alt="image" src="https://user-images.githubusercontent.com/78966839/181294114-5e5fcaa0-994f-4a74-a541-64e76810e0ba.png">

## CRUD :-

- CREATE :- POST
- READ :- GET
- UPDATE :- PUT  , PATCH
- DELETE :- DELETE
*******
- PUT :- compit change
- PATCH :- specific path cahnge
**************
GET /api/users
***********

## May be Not


*************




## 🙏 If you find this repo helpful then don't forget to give a star ❇️ to this repository. :)
