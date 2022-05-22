MongoDBCheatSheet

This is MongoDb Cheat Sheet if you need some quick reference then it will help you

<h1>MongoDB Cheat Sheet</h1>

## Terminology

|        | |
| ----- | ----- |
| `Database` | A container for collections. This is the same as a database in SQL and usually each project will have its own database full of different collections. |
| `Collection` | A grouping of documents inside of a database. This is the same as a table in SQL and usually each type of data (users, posts, products) will have its own collection. |
| `Document`| A record inside of a collection. This is the same as a row in SQL and usually there will be one document per object in the collection. A document is also essentially just a JSON object. |
| `Field` | A key value pair within a document. This is the same as a column in SQL. Each document will have some number of fields that contain information such as name, address, hobbies, etc. An important difference between SQL and MongoDB is that a field can contain values such as JSON objects, and arrays instead of just strings, number, booleans, etc. |


## Basic Commands
|        | |
| ----- | ----- |
| `mongosh` |Open a connection to your local MongoDB instance. All other commands will be run within this mongosh connection. |
| `show dbs` | Show all databases in the current MongoDB instance |
| use \<dbname> `use myDatabase`| Switch to the database provided by dbname `Switch to myDatabase` |
| `db` | Show current database name |
| `cls` | Clear the terminal screen |
| `show collections` | Show all collections in the current database |
| `db.dropDatabase()` | Delete the current database |
| `exit` | Exit the mongosh session |

-------------------------------------


### Now Turn of CURD ( Create, Updated, Read, Delete )

## Create

#### Each of these commands is run on a specific collection

`db.<collectionName>.<command>`


| insertOne | Create a new document inside the specified collection |
| -------- | ------- |
| ```db.users.insertOne({ name: “Vishal” })``` | Add a new document with the name of Vishal into the users collection |

<br>

| insertMany | Create multi new documents inside a specific collection |
| -------- | ------- |
| ```db.users.insertMany([{ age: 14 }, { age: 15 }])``` | Add two new documents with the age of **14** and **15** into the users collection |

<br>


## Update

#### Each of these commands is run on a specific collection
`db.<collectionName>.<command>`


| updateOne | Update the first document that matches the filter object with the data passed into the second parameter which is the update object |
| -------- | ------- |
| ```db.users.updateOne({ age: 14 }, { $set: { age: 241 } })``` | Update the first user with an age of 14 to the age of 241 |

<br>

| updateMany | Update all documents that matches the filter object with the data passed into the second parameter which is the update object |
| -------- | ------- |
| ```db.users.updateMany({ age: 241 }, { $inc: { age: 3 } })``` | Update all users with an age of 241 by adding 3 to their age |

<br>

| replaceOne | Replace the first document that matches the filter object with the exact object passed as the second parameter. This will completely overwrite the entire object and not just update individual fields |
| -------- | ------- |
| ```db.users.replaceOne({ age: 12 }, { age: 13 })``` | Replace the first user with an age of 12 with an object that has the age of 13 as its only field |

<br>

## Read

#### Each of these commands is run on a specific collection
`db.<collectionName>.<command>`


| updateOne | Update the first document that matches the filter object with the data passed into the second parameter which is the update object |
| -------- | ------- |
| ```db.users.updateOne({ age: 14 }, { $set: { age: 241 } })``` | Update the first user with an age of 14 to the age of 241 |

<br>

| updateMany | Update all documents that matches the filter object with the data passed into the second parameter which is the update object |
| -------- | ------- |
| ```db.users.updateMany({ age: 241 }, { $inc: { age: 3 } })``` | Update all users with an age of 241 by adding 3 to their age |

<br>

| replaceOne | Replace the first document that matches the filter object with the exact object passed as the second parameter. This will completely overwrite the entire object and not just update individual fields |
| -------- | ------- |
| ```db.users.replaceOne({ age: 12 }, { age: 13 })``` | Replace the first user with an age of 12 with an object that has the age of 13 as its only field |

<br>












