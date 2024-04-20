# MongoDB Session 1

## Introduction to MongoDB

### What is MongoDB?

MongoDB is a cross-platform, document-oriented database that provides, high performance, high availability, and easy scalability. MongoDB works on the concept of collections and documents.

### Features of MongoDB

1. **Document-Oriented** − MongoDB is a document database in which one collection holds different documents. Number of fields, content, and size of the document can differ from one document to another.
2. **Schema-less** − MongoDB is a schema-less database, which means you can create documents without first defining the structure, i.e., the fields or the types of their values. You can change the structure of documents simply by adding new fields or deleting existing ones.
3. **Indexing** − Indexes support the efficient execution of queries in MongoDB. Without indexes, MongoDB must perform a collection scan, i.e., scan every document in a collection, to select those documents that match the query statement. If an appropriate index exists for a query, MongoDB can use the index to limit the number of documents it must inspect.
4. **Replication** − MongoDB provides high availability with replica sets. A replica set consists of two or more copies of the same data.
5. **Load Balancing** − MongoDB uses sharding to scale the database. Sharding is the process of storing data records across multiple machines and is MongoDB’s approach to meeting the demands of data growth.
6. **Aggregation** − MongoDB provides the capability to perform aggregation operations, such as grouping, average, sum, count, etc. to provide more relevant results.
7. **Ad-hoc queries** − MongoDB supports search by field, range queries, and regular expression searches. Queries can return specific fields of documents and also include user-defined JavaScript functions.
8. **File Storage** − MongoDB can be used as a file system, taking advantage of load balancing and data replication features over multiple machines for storing files.
9. **Server-side JavaScript execution** − JavaScript can be used in queries, aggregation functions (such as MapReduce), and sent directly to the database to be executed.

### Where to Use MongoDB?

1. **Big Data** − MongoDB is a great choice for working with large amounts of data. It is a high-performance database.
2. **Content Management and Delivery** − MongoDB is best for content management and delivery applications.
3. **Mobile and Social Infrastructure** − MongoDB is ideal for building social infrastructure and mobile applications.
4. **User Data Management** − MongoDB can be used for managing user data storage.
5. **Data Hub** − MongoDB can be used as a central data hub for integrating data from multiple sources.
6. **Data Analytics** − MongoDB is used for data analytics and business intelligence applications.
7. **High Volume Data Feed** − MongoDB can store a high volume of data that is being generated continuously.
8. **Data Storage** − MongoDB can be used as a general-purpose operational database.

### MongoDB Database

A MongoDB database is a container for collections. Each database gets its own set of files on the file system. A single MongoDB server typically has multiple databases.

### MongoDB Collection

A collection is a group of MongoDB documents. It is the equivalent of an RDBMS table. A collection exists within a single database. Collections do not enforce a schema. Documents within a collection can have different fields. Typically, all documents in a collection are of similar or related purpose.

### MongoDB Document

A document is a set of key-value pairs. Documents have dynamic schema. Dynamic schema means that documents in the same collection do not need to have the same set of fields or structure, and common fields in a collection’s documents may hold different types of data.

### MongoDB Example

Here is an example of a document in MongoDB:

```json
{
   _id: ObjectId(7df78ad8902c),
   title: 'MongoDB Overview',
   description: 'MongoDB is no SQL database',
   by: 'tutorials point',
   url: 'http://www.tutorialspoint.com',
   tags: ['mongodb', 'database', 'NoSQL'],
   likes: 100
}
```

### MongoDB Relationships

In MongoDB, you can represent complex hierarchical relationships, data arrays, and other complex structures easily. You can also change the structure of records (which is not possible in a relational database).

### MongoDB Advantages

1. **Speed** − MongoDB is high-performance and provides high-speed read and writes operations.
2. **Scalability** − MongoDB is a scalable database. You can handle a huge amount of data with MongoDB.
3. **Manageable** − MongoDB is easy to use. You can perform a task like updating, deleting, etc. easily.
4. **Dynamic Schema** − In MongoDB, you can create collections without defining the structure, i.e., you can create a collection without defining its schema.

### MongoDB Disadvantages

1. **No transaction** − MongoDB does not support transaction operations.
2. **Size** − MongoDB is not good for large size databases.
3. **No join** − MongoDB does not support join operations.
4. **Memory Usage** − MongoDB uses more memory.
5. **Not Supportive** − MongoDB is not supportive of ACID properties.
   1. Atomicity: An atomic transaction is an indivisible and irreducible series of database operations such that either all occur, or nothing occurs.
   2. Consistency: A consistent transaction is one that transforms one consistent state of the database into another consistent state.
   3. Isolation: An isolated transaction is one that is not affected by other transactions.
   4. Durability: A durable transaction is one that once committed, will survive permanently.

### MongoDB API

MongoDB provides various APIs:

1. **MongoDB provides a native API** to work with MongoDB databases.
2. **MongoDB also provides drivers for various programming languages** like Java, C, C++, C#, PHP, Python, Ruby, etc.
3. **MongoDB also provides a web-based administrative interface** called MongoDB Management Service (MMS) which is a part of MongoDB Enterprise Advanced.
4. **MongoDB also provides a cloud-based MongoDB as a service** − MongoDB Atlas.

### MongoDB Tutorial

This MongoDB tutorial is designed for beginners so you will be able to understand MongoDB even if you don’t have any prior knowledge of it. However, if you have some knowledge of any database, then it will be helpful.

#### Prerequisites

- MongoDB
- Mongo Express
- Mongosh

#### Create a Database

- connect to MongoDB

```bash
mongosh
```

- create a database

```bash
use mydb
```

- show all databases

```bash
show dbs
```

- drop a database

```bash
db.dropDatabase()
```

#### Create a Collection

- create a collection

```bash
db.createCollection('mycollection')
```

- show all collections

```bash
show collections
```

- drop a collection

```bash
db.mycollection.drop()
```

#### Insert Document

- insert a document

```bash
db.mycollection.insertOne({ x: 1 })
```

- insert multiple documents

```bash
db.mycollection.insertMany([{ x: 1 }, { x: 2 }, { x: 3 }])
```

#### Find Document

- find all documents

```bash
db.mycollection.find()
```

- find documents with a condition

```bash
db.mycollection.find({ x: 1 })
```

- find documents with a condition and projection

```bash
db.mycollection.find({ x: 1 }, { x: 1 })
```
- greater than condition

```bash
db.mycollection.find({ x: { $gt: 1 } })
```

- less than condition

```bash
db.mycollection.find({ x: { $lt: 1 } })
```

- greater than or equal to condition

```bash
db.mycollection.find({ x: { $gte: 1 } })
```

- less than or equal to condition

```bash
db.mycollection.find({ x: { $lte: 1 } })
```

- not equal to condition

```bash
db.mycollection.find({ x: { $ne: 1 } })
```

- and condition

```bash
db.mycollection.find({ x: 1, y: 2 })
```

- or condition

```bash
db.mycollection.find({ $or: [{ x: 1 }, { y: 2 }] })
```

- in condition

```bash
db.mycollection.find({ x: { $in: [1, 2] } })
```

- not in condition

```bash
db.mycollection.find({ x: { $nin: [1, 2] } })
```

- exists condition

```bash
db.mycollection.find({ x: { $exists: true } })
```

- not exists condition

```bash
db.mycollection.find({ x: { $exists: false } })
```

#### Update Document

- update a document

```bash
db.mycollection.updateOne({ x: 1 }, { $set: { x: 2 } })
```

- update multiple documents

```bash
db.mycollection.updateMany({ x: 1 }, { $set: { x: 2 } })
```

#### Delete Document

- delete a document

```bash
db.mycollection.deleteOne({ x: 1 })
```

- delete multiple documents

```bash
db.mycollection.deleteMany({ x: 1 })
```

#### Drop Collection

- drop a collection

```bash
db.mycollection.drop()
```

#### Drop Database

- drop a database

```bash
db.dropDatabase()
```

#### MongoDB Advanced Tutorial

This MongoDB tutorial is designed for professionals so you will be able to understand MongoDB in depth. You should have some knowledge of MongoDB before starting this tutorial.

- **MongoDB Aggregation**

MongoDB provides the aggregation pipeline to process data and return computed results. The aggregation pipeline is a framework for data aggregation modeled on the concept of data processing pipelines.

- **MongoDB Indexing**

Indexes support the efficient execution of queries in MongoDB. Without indexes, MongoDB must perform a collection scan, i.e., scan every document in a collection, to select those documents that match the query statement.

- **MongoDB Data Modeling**

Data in MongoDB has a flexible schema. Collections do not enforce document structure. This flexibility gives you data-modeling choices to match your application and its performance requirements.