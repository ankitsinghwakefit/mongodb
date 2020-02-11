#### write commands for following mongodb opertaions

1. create a database named `sports`
// Answer here ..

use sports

2. list all databases present in local mongod server.
// Answer here..

admin   0.000GB
config  0.000GB
local

3. create 3 collections named `cricket`, `football`, `TT` in sports database.

db.createCollection("cricket")
{ "ok" : 1 }
> db.createCollection("football")
{ "ok" : 1 }
> db.createCollection("TT")


4. add 3 players in each of above collections which should have fields like `name`, `age`, `email`, state and auction_price.
 db.TT.insert({name:"player1", age:21, email:"abc@gmail.com"})

db.cricket.insert({name:"player2", age:22, email:"abd@gmail.com"})

db.football.insert({name:"player3", age:23, email:"acf@gmail.com"})


5. list all collections in sports database.

show collections
TT
cricket
football


6. rename `TT` collection to `tennis`.

db.TT.renameCollection("tennis")

7. create a capped collection called `khokho` which should have max 3 documents.
  Try inserting more than 3 and output the result here ?


db.createCollection("khokho",{capped:true,max:3});
db.khokho.insertMany([{player1:"abc"},{player2:"acd"},{player3:"avd"}])
 db.khokho.insert({player4:"abcd"})
db.khokho.find()
{ "_id" : ObjectId("5e4083ab11b6ebca95c9dbe2"), "player1" : "abc" }
{ "_id" : ObjectId("5e4083ab11b6ebca95c9dbe3"), "player2" : "acd" }
{ "_id" : ObjectId("5e4083ab11b6ebca95c9dbe4"), "player3" : "avd" }
{ "_id" : ObjectId("5e40840811b6ebca95c9dbe5"), "player4" : "abcd" }


8. check whether a collection is capped or not?
false

9. remove all documents from `football` collection.

db.football.remove({})

10. delete cricket collection completely.

db.cricket.drop()

11. rename database sports to games
db.sports.renameCollection("games")

12. delete sports database. 
db.sports.dropDatabase();