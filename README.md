Read the Project Specfications [here](https://docs.google.com/document/d/1zZjNk9cbNLz0mp_-YtyZxhMzUph97fVgCkSE4u2k5EA/edit?usp=sharing).

## Instructions to setup and run project
This project uses MongoDB, Node.js, express, mongoose, nodemon, axios, cors, bcrypt, and no additional packages.

For the project to run you need to npm install all the packages mentioned in both the client and server directory.

Database Instance runs at `mongodb://127.0.0.1:27017/fake_so`<br/>
Client Instance runs at `https://localhost:3000`<br/>
Server Instance runs at `https://localhost:8000`<br/>


Personally I run my server with `npx nodemon server.js` in the server directory. And client with `npm start` in the client directory. I open my database with `"C:\Program Files\MongoDB\Server\5.0\bin\mongod.exe" --dbpath="c:\data\db"`

After the instances are opened you would want to populate the database by navigating to the server directory and running the populate_db.js with the argument mongodb://127.0.0.1:27017/fake_so. `node populate_db.js mongodb://127.0.0.1:27017/fake_so`. This will populate the database for you. 

You can alter the data that is generated in populate_db.js to your liking. If you wish to create your own custom data, you can use the following provided methods in the populate section of the code.

userCreate(username, email, hashed password, register_date)<br/>
username: String, REQUIRE <br/>
email: String, REQUIRE<br/>
hashed password: String (processed by bcrypt.hash), REQUIRE<br/>
reputation: Integer<br/>
register_date: Date objects<br/>

tagCreate(name, tag_by)<br/>
name: String, REQUIRE<br/>
tag_by: User object, REQUIRE<br/>

commentCreate(text,comment_by)<br/>
text: String, REQUIRE<br/>
comment_by: User object, REQUIRE<br/>

answerCreate(text, ans_by, ans_date_time, upvote, downvote, comment)<br/>
text:String, REQUIRE<br/>
ans_by: User object, REQUIRE<br/>
ans_date_time: Date object<br/>
upvote: array of User objects<br/>
downvote: array of User objects<br/>
comment : array of Comment objects<br/>

questionCreate(title, summary, text, tags, answers, asked_by, ask_date_time, views, upvote, downvote, comment)<br/>
title: String, REQUIRE<br/>
summary: String, REQUIRE<br/>
text: String, REQUIRE<br/>
tags: array of Tag objects, REQUIRE<br/>
answers: array of Answer objects<br/>
asked_by: User objects<br/>
ask_date_time: Date object<br/>
views: Integer<br/>
upvote: array of User objects<br/>
downvote: array of User objects<br/>
comment : array of Comment objects<br/>

You can test project with the following user:

username: some1 <br/>
email: some1@gmail.com<br/>
password:123<br/>
reputation: 0<br/>

username: some2 <br/>
email: some2@gmail.com<br/>
password:1234<br/>
reputation: 100<br/>

username: some3 <br/>
email: some3@gmail.com<br/>
password:1235<br/>
reputation: 50<br/>

username: some4 <br/>
email: some4@gmail.com<br/>
password:1236<br/>
reputation: 101<br/>

## Data Model

![alt text](images/uml.PNG)
The UML model describes the schema for all documents in the MongoDB database
