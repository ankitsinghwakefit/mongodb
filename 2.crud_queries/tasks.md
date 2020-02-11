1. Create a database named `blog`.

use blog

2. Create a collection called 'articles'.

db.createCollection("articles")

3. Insert multiple documents(at least 3) into articles. It should have fields

db.createCollection("articles")
db.articles.insertMany([{_id:1,name:"array"},{_id:2,name:"style"}])
db.articles.insertOne({_id:3,name:"html"})

db.createCollection("articles2")
db.articles2.insertMany([{_id:1,name:"array2"},{_id:2,name:"style2"}])


4. Find all the articles using `db.COLLECTION_NAME.find()`

db.articles.find()


5. Find a document using _id field.

db.articles.find({_id:1})


6. Find documents using title and author's name field.

db.articles.update({_id:1},{$set:{title:"about article1"}})
db.articles.update({_id:2},{$set:{title:"about article2"}})
db.articles.update({_id:3},{$set:{title:"about article3"}})

db.articles.find({title:{$eq:"about article1"}})
db.articles.find({name:{$eq:"array"}})


7. Find document using a specific tag.

db.articles.find({name:{$eq:"style"}})


8. Update title of a document using its _id field.

db.articles.update({_id:2},{$set:{name:"newName"}})


9. Update a author's name using article's title.

db.articles.update({title:"about article3"},{$set:{name:"newName"}})


10. rename details field to description from articles collection. 

db.articles.update({_id:1},{$set:{description:"desp about 1"}},{upsert: true})
------------------------------------------------------------------------------

11. Add additional tag in a specific document.
db.articles.update({_id:2},{$set:{tag:"tag1"}},{upsert:true})

12. Update an article's tags using $set and without $set.
  - Write the differences here ?
db.articles.update({_id:2},{tag:"tag1"})
if we update using set it will set some specified details but if we update without set it will overwrite whole document with given details.
{ "_id" : 1, "name" : "array", "title" : "about article1", "description" : "desp about 1" }
{ "_id" : 2, "tag" : "tag1" }
{ "_id" : 3, "name" : "newName", "title" : "about article3" }


13. Increment an auhtor's age by 5.  
db.articles.update({_id:2},{$set:{age:21}},{upsert:true})
db.articles.update({_id:2},{$inc:{age:2}})


14. Delete a document using _id field with `db.COLLECTION_NAME.remove()`.
db.articles.remove({_id:3})


Use sample.js data for below queries.

1. Find all males who play cricket.


2. Update user with extra golf field in sports array whose name is "Steve Ortega".

3. Find all users who play either 'football' or 'cricket'.

4. Find all users whose name includes 'ri' in their name.
