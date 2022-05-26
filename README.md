<h1>MongoDB Cheat Sheet</h1>
This is MongoDb Cheat Sheet if you need some quick reference then it will help you


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


| find | Get all documents |
| -------- | ------- |
| ```db.users.find()``` | Get all users |

<br>

| find(\<filterObject>) | Find all documents that match the filter object |
| -------- | ------- |
| `db.users.find({ name: “Vishal” })` | Get all users with the name Vishal |
| `db.users.find({ “address.street”: “321 First Street” })` | Get all users whose adress field has a street field with the value 321 First Street |

<br>


| find(\<filterObject> \<selectObject>) | Find all documents that match the filter object but only return the field specified in the select object |
| -------- | ------- |
| `db.users.find({ name: “Vishal” }, { name: 1, age: 1 })` | Get all users with the name Vishal but only return their name, age, and _id |
| `db.users.find({}, { age: 0 })` | Get all users and return all columns except for age |

<br>

| findOne | The same as find, but only return the first document that matches the filter object |
| -------- | ------- |
| ```db.users.find({ name: “Vishal” })``` | Get the first user with the name Vishal |

<br>

| countDocuments | The same as find, but only return the first document that matches the filter object |
| -------- | ------- |
| ```db.users.countDocuments({ name: “Vishal” })``` | Get the number of users with the name Vishal |

<br>

## Delete

#### Each of these commands is run on a specific collection

`db.<collectionName>.<command>`


| deleteOne | Delete the first document that matches the filter object |
| -------- | ------- |
| ```db.users.deleteOne({ age: 20 })``` | Delete the first user with an age of 20 |

<br>

| deleteMany | Delete all documents that matches the filter object |
| -------- | ------- |
| ```db.users.deleteMany({ age: 12 })``` | Delete all users with an age of 12 |

<br>

-------------------------------------

## Complex Filter Object
### Any combination of the below can be use inside a filter object to make complex queries

<br>

| $eq | Check for equality |
| -------- | ------- |
| ```db.users.find({ name: { $eq: “Alan” } })``` | Get all users with the name Kyle |

<br>

| $ne | Check for not equal |
| -------- | ------- |
| ```db.users.find({ name: { $ne: “Turing” } })``` | Get all users with a name other than Turing |

<br>

| $gt / $gte | Check for greater than and greater than or equal to |
| -------- | ------- |
| ```db.users.find({ age: { $gt: 12 } })``` | Get all users with an age greater than 12 |
| ```db.users.find({ age: { $gte: 15 } })``` | Get all users with an age greater than or equal to 15 |

<br>

| $lt / $lte | Check for less than and less than or equal to |
| -------- | ------- |
| ```db.users.find({ age: { $lt: 12 } })``` | Get all users with an age less than 12 |
| ```db.users.find({ age: { $lte: 15 } })``` | Get all users with an age less than or equal to 15 |

<br>


## Feel free to Contribute if you know something about MONGO DB


# License

```
   Copyright 2022 Vishal
   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
```












