---
title: "MongoDB-Schema Day 3 of 40 Days MERN Stack"
seoTitle: "MongoDB Schema: Day 3 MERN Stack Journey"
seoDescription: "Learn about MongoDB data modeling, including embedded and normalized data models, and how to design a database for client needs"
datePublished: Thu May 23 2024 18:42:28 GMT+0000 (Coordinated Universal Time)
cuid: clwjloeaq001308mr5cmh04m1
slug: mongodb-schema-day-3
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1716489623931/8ec03b9b-f88b-4bfb-9d14-1aa85c2ae8cf.png
tags: mongodb, full-stack, mern, mern-stack, full-stack-web-development, mern-stack-development

---

## MongoDB - Data Modelling

Data in MongoDB has a flexible schema.documents in the same collection. They do not need to have the same set of fields or structure Common fields in a collection’s documents may hold different types of data.

### Data Model Design

MongoDB provides two types of data models: — **Embedded data model** and **Normalized data model**. Based on the requirement, you can use either of the models while preparing your document

* Embedded Data Model
    

In this model, you can have (embed) all the related data in a single document, it is also known as de-normalized data model.

For example, assume we are getting the details of employees in three different documents namely, Personal\_details, Contact and, Address, you can embed all the three documents in a single one as shown below:

```json
{
_id: ,
Emp_ID: "10025AE336"
Personal_details:{
First_Name: "daily",
Last_Name: "tech",
Date_Of_Birth: "1995-09-26"
},
Contact: {
e-mail: "test@gmail.com",
phone: "123456789"
},
Address: {
city: "Hyderabad",
Area: "Madapur",
State: "Telangana"
}}
```

* Normalized Data Model
    

In this model, you can refer the sub documents in the original document, using references. For example, you can re-write the above document in the normalized model as:

***Employee:***

```json
{
_id: <ObjectId101>,
Emp_ID: "10025AE336"
}
```

***Personal\_details:***

```json
{
_id: <ObjectId102>,
empDocID: " ObjectId101",
First_Name: "daily",
Last_Name: "tech",
Date_Of_Birth: "1995-09-26"
}
```

***Contact:***

```json
{
_id: <ObjectId103>,
empDocID: " ObjectId101",
e-mail: "test@gmail.com",
phone: "123456789"
}
```

---

## Let’s design a Database according to client’s need.

* Every post has the unique title, description and url.
    
* Every post can have one or more tags.
    
* Every post has the name of its publisher and total number of likes.
    
* Every post has comments given by users along with their name, message, data-time and likes.
    
* On each post, there can be zero or more comments.
    

### Unique id , title , description and url can be written as:

```json
{
_id: POST_ID
title: TITLE_OF_POST,
description: POST_DESCRIPTION,
by: POST_BY,
url: URL_OF_POST
}
```

### One or more tags can be written as:

```json
{
tags: [TAG1, TAG2, TAG3]
}
```

### Name of its publisher and total number of likes.

```json
{
likes: TOTAL_LIKES,
by: POST_BY
}
```

### Comment can be made by list of comments:

```json
{
comments: [
{
user: 'COMMENT_BY',
message: TEXT,
datecreated: DATE_TIME,
like: LIKES
},
{
user: 'COMMENT_BY',
message: TEST,
dateCreated: DATE_TIME,
like: LIKES
}]
}
```

### The overall schema can be designed by combining all of the above:

```json
{
_id: POST_ID
title: TITLE_OF_POST,
description: POST_DESCRIPTION,
by: POST_BY,
url: URL_OF_POST,
tags: [TAG1, TAG2, TAG3],
likes: TOTAL_LIKES,
comments: [
{
user: 'COMMENT_BY',
message: TEXT,
datecreated: DATE_TIME,
like: LIKES
},
{
user: 'COMMENT_BY',
message: TEST,
dateCreated: DATE_TIME,
like: LIKES
}]}
```

  
Thats all for today...

Stay Tuned & Have a Good Day :)