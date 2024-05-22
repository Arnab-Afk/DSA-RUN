---
title: "MongoDB - Day 1 of MERN Stack"
seoTitle: "MERN Stack: MongoDB Introduction"
seoDescription: "Getting started with MongoDB in the MERN stack: installation, creating clusters, and basic database operations using mongosh"
datePublished: Wed May 22 2024 05:41:22 GMT+0000 (Coordinated Universal Time)
cuid: clwhec226000709la2jdcc7z6
slug: mongodb-day-1
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1716356166239/9ff4d5de-b0c5-4104-a30b-535ecb45bb19.png
tags: mongodb, mern, mongodb-atlas, full-stack-development, mern-stack-development

---

## MongoDB Getting Started

MongoDB is a document database and can be installed locally or hosted in the cloud.

MongoDB can be installed locally, which will allow you to host your own MongoDB server on your hardware. This requires you to manage your server, upgrades, and any other maintenance.

You can download and use the **MongoDB open source Community Server** on your hardware for free.

However we ’ll be using **MongoDB Atlas** as of now, a cloud database platform. This is much easier than hosting your own local database.

To be able to experiment with the code examples, you will need access to a MongoDB database.

Sign up for a free [**MongoDB Atlas**](https://www.mongodb.com/cloud/atlas/register) account to get started.

---

## Few steps to get started:

### Creating a Cluster

After you have created your account, set up a free "***Shared Cluster***" then choose your preferred cloud provider and region.

### Install MongoDB Shell (mongosh)

Use the [*official instructions*](https://docs.mongodb.com/mongodb-shell/install/) to install mongosh on your operating system.

To verify that it has been installed properly, open your terminal and type:

```bash
mongosh --version
```

### Connect to the database

In the MongoDB Atlas dashboard, under "***Databases***", click the "***Connect***" button for your Cluster.

Next, choose "***Connect with the MongoDB Shell***".

Copy your **connection string**.

```bash
mongosh "mongodb+srv://cluster0.ex4ht.mongodb.net/myFirstDatabase" --apiVersion 1 --username YOUR_USER_NAME
```

---

## MongoDB mongosh Create Database

### Create Database using mongosh

After connecting to your database using mongosh, you can see which database you are using by typing **db** in your terminal.

To see all available databases, in your terminal type ***show dbs***.

You can change or create a new database by typing ***use*** then the name of the database.

Create a new database called "***blog***":

```bash
use blog
```

We are now in the ***blog*** database.

![The MongoDB Basics: Databases, Collections & Documents | Studio 3T](https://studio3t.com/wp-content/uploads/2022/04/hierachy.png align="left")

---

## MongoDB mongosh Create Collection

There are 2 ways to create a collection.

* createCollection()
    
* insertOne(object)
    

You can create a collection using the ***createCollection()*** database method.

```bash
db.createCollection("posts")
```

We are here assuming object is a valid JavaScript object containing post data:

```bash
db.posts.insertOne(object)
```

---

## MongoDB mongosh Insert

**Insert Documents**

There are 2 methods to insert documents into a MongoDB database:

* insertOne()
    
* insertMany()
    

To insert a single document, use the ***insertOne()*** method. This method inserts a single object into the database.

```bash
db.posts.insertOne({
  title: "Post Title 1",
  body: "Body of post.",
  category: "News",
  likes: 1,
  tags: ["news", "events"],
  date: Date()
})
```

To insert multiple documents at once, use the ***insertMany()*** method.

This method inserts an array of objects into the database.

```bash
db.posts.insertMany([ 
{title:“post 1”} ,
{title:“post 2”}
])
```

---

## MongoDB mongosh Find

There are 2 methods to find and select data from a MongoDB collection:

* find()
    
* findOne()
    

To select data from a collection in MongoDB, we can use the ***find()*** method.

```bash
db.posts.find( {category: "News"} )
```

To select only one document, we can use the findOne() method.

This method accepts a query object. If left empty, it will return the first document it finds.

```bash
db.posts.findOne( {category: "News"} )
```

---

## MongoDB mongosh Update & Delete

### Update Document

There are 2 methods to update a document:

* updateOne()
    
* updateMany()
    

The ***updateOne()*** method will update the first document that is found matching the provided query.

Let's see what the "like" count for the post with the title of "Post Title 1":

```bash
db.posts.find( { title: "Post Title 1" } ) 
```

Now let's update the "**likes**" on this post to 2. To do this, we need to use the `$set` operator.

```bash
db.posts.updateOne( { title: "Post Title 1" }, { $set: { likes: 2 } } ) 
```

Check the document again and you'll see that the "like" have been updated.

```bash
db.posts.find( { title: "Post Title 1" } ) 
```

The `updateMany()` method will update all documents that match the provided query.

Update `likes` on all documents by 1. For this we will use the `$inc` (increment) operator:

```bash
db.posts.updateMany({}, { $inc: { likes: 1 } })
```

Now check the likes in all of the documents and you will see that they have all been incremented by 1.

## Delete Documents

There are 2 methods to delete documents in MongoDB:

These methods accept a query object. The matching documents will be deleted.

* deleteOne()
    
* deleteMany()
    

The `deleteOne()` method will delete the first document that matches the query provided.

```bash
db.posts.deleteOne({ title: "Post Title 5" })
```

The `deleteMany()` method will delete all documents that match the query provided.

```bash
db.posts.deleteMany({ category: "Technology" })
```

---

## Was this helpful?

Don't forget to like, share and drop a comment.