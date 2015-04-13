# QUIZZES

## QUIZ: CRUD AND THE MONGO SHELL

By the end of this week, you'll know which of the following?
* [X] MongoDB's basic document creation, retrieval, modification, and removal operations
* [X] Some features of the MongoDB shell, mongo
* [ ] How to measure performance of MongoDB operations
* [X] How to manipulate MongoDB documents from a language
* [ ] How to analyze data in MongoDB collections

## QUIZ: SECRETS OF THE MONGO SHELL

What does the following fragment of JavaScript output?
x = { "a" : 1 };
y = "a";
x[y]++;
print(x.a);
* asnwer: 2

## QUIZ: BSON INTRODUCED

Which of the following are types available in BSON?
* [X] Strings
* [X] Floating-point numbers
* [ ] Complex numbers
* [X] Arrays
* [X] Objects (Subdocuments)
* [X] Timestamps

## QUIZ: INSERTING DOCS

Insert a document into the fruit collection with the attributes of "name" being "apple", "color" being "red", and "shape" being "round". Use the "insert" method.

This is a fully functional web shell, so please press enter for your query to get passed to the server, just like you would for the command line shell.
* db.fruit.insert({"name": "apple", "color": "red", "shape": "round"})

## QUIZ: INTRODUCTION TO FINDONE

Use findOne on the collection users to find one document where the key username is "dwight", and retrieve only the key named email.
* db.users.findOne({"username": "dwight"}, {"email":true, "_id":false})

## QUIZ: QUERYING USING FIELD SELECTION

Supposing a scores collection similar to the one presented, how would you find all documents with type: essay and score: 50 and only retrieve the student field?
* db.scores.find({"type": "essay", "score": 50}, {"student":true, "_id":false})

## QUIZ: QUERYING USING $GT AND $LT

Which of these finds documents with a score between 50 and 60, inclusive?
* [ ] db.scores.find({ score : { $gt : 50 , $lt : 60 } } );
* [X] db.scores.find({ score : { $gte : 50 , $lte : 60 } } );
* [ ] db.scores.find({ score : { $gt : 50 , $lte : 60 } } );
* [ ] db.scores.find({ score : { $gte : 50 , $lt : 60 } } );
* [ ] db.scores.find({ score : { $gt : 50 } } );

## QUIZ: INEQUALITIES ON STRINGS

Which of the following will find all users with name between "F" and "Q" (Inclusive)?
* [X] db.users.find( { name : { $gte : "F" , $lte : "Q" } } );
* [X] db.users.find( { name : { $lte : "Q" , $gte : "F" } } );
* [ ] db.users.find( { name : { $gte : "f" , $lte : "Q" } } );
* [ ] db.users.find( { name : { $lte : "Q" } });

## QUIZ: USING REGEXES, $EXISTS, $TYPE

Write a query that retrieves documents from a users collection where the name has a "q" in it, and the document has an email field.
* db.users.find({name : {$regex: "q"}, email: {$exists: true}})

## QUIZ: USING $OR

How would you find all documents in the scores collection where the score is less than 50 or greater than 90?
Note: We're afraid that the parser has trouble recognizing when you switch the order, so be sure to put your "less than" operator before your "greater than" one.
* db.scores.find({$or: [{score : {$lt: 50}}, {score: {$gt: 90}}] })

## QUIZ: USING $AND

What will the following query do?
db.scores.find( { score : { $gt : 50 }, score : { $lt : 60 } } );
* [ ] Find all documents with score between 50 and 60
* [ ] Find all documents with score greater than 50
* [X] Find all documents with score less than 60
* [ ] Explode like the Death Star
* [ ] None of the above

## QUIZ: QUERYING INSIDE ARRAYS

Which of the following documents would be returned by this query?
db.products.find( { tags : "shiny" } );
* [X] { _id : 42 , name : "Whizzy Wiz-o-matic", tags : [ "awesome", "shiny" , "green" ] }
* [ ] { _id : 704 , name : "Fooey Foo-o-tron", tags : [ "blue", "mediocre" ] }
* [X] { _id : 1040 , name : "Snappy Snap-o-lux", tags : "shiny" }
* [ ] { _id : 12345 , name : "Quuxinator", tags : [ ] }

## QUIZ: USING $IN AND $ALL

Which of the following documents matches this query?
db.users.find( { friends : { $all : [ "Joe" , "Bob" ] }, favorites : { $in : [ "running" , "pickles" ] } } )
* [ ] { name : "William" , friends : [ "Bob" , "Fred" ] , favorites : [ "hamburgers", "running" ] }
* [ ] { name : "Stephen" , friends : [ "Joe" , "Pete" ] , favorites : [ "pickles", "swimming" ] }
* [X] { name : "Cliff" , friends : [ "Pete" , "Joe" , "Tom" , "Bob" ] , favorites : [ "pickles", "cycling" ] }
* [ ] { name : "Harry" , friends : [ "Joe" , "Bob" ] , favorites : [ "hot dogs", "swimming" ] }

## QUIZ: QUERIES WITH DOT NOTATION

Suppose a simple e-commerce product catalog called catalog with documents that look like this:
{ product : "Super Duper-o-phonic",
  price : 100000000000,
  reviews : [ { user : "fred", comment : "Great!" , rating : 5 },
              { user : "tom" , comment : "I agree with Fred, somewhat!" , rating : 4 } ],
  ... }
Write a query that finds all products that cost more than 10,000 and that have a rating of 5 or better.
* db.catalog.find( { price : { $gt : 10000 } , "reviews.rating" : { $gte : 5 } } );

## QUIZ: QUERYING, CURSORS

When can you change the behavior of a cursor, by applying a sort, skip, or limit to it?
* [ ] This can be done at any point, and will reset the cursor.
* [ ] This can only be done when the cursor is created.
* [ ] This can be done only before the cursor is created.
* [X] This can be done at any point before the first document is called and before you've checked to see if it is empty.
* [ ] This can be done at any point, and will apply to any documents the cursor hasn't yet pulled.

## QUIZ: COUNTING RESULTS

How would you count the documents in the scores collection where the type was "essay" and the score was greater than 90?
* db.scores.count({type:"essay", score : { $gt : 90 } })

## QUIZ: WHOLESALE UPDATING OF A DOCUMENT

Let's say you had a collection with the following document in it:
{ "_id" : "Texas", "population" : 2500000, "land_locked" : 1 }
and you issued the query:
db.foo.update({_id:"Texas"},{population:30000000})
What would be the state of the collection after the update?
* [ ] { "_id" : "Texas", "population" : 2500000, "land_locked" : 1 }
* [ ] { "_id" : "Texas", "population" : 3000000, "land_locked" : 1 }
* [X] { "_id" : "Texas", "population" : 30000000 }
* [ ] { "_id" : ObjectId("507b7c601eb13126c9e3dcca"), "population" : 2500000 }

## QUIZ: USING THE $SET COMMAND

For the users collection, the documents are of the form
{
	"_id" : "myrnarackham",
	"phone" : "301-512-7434",
	"country" : "US"
}
Please set myrnarackham's country code to "RU" but leave the rest of the document (and the rest of the collection) unchanged.

Hint: You should not need to pass the "phone" field to the update query.
* db.users.update({"_id":"myrnarackham"},{$set:{"country" : "RU"}})

## QUIZ: USING THE $UNSET COMMAND

Write an update query that will remove the "interests" field in the following document in the users collection.
{
    "_id" : "jimmy" ,
    "favorite_color" : "blue" ,
    "interests" : [ "debating" , "politics" ]
}
Do not simply empty the array. Remove the key : value pair from the document.
* db.users.update({"_id":"jimmy"},{$unset:{"interests" : 1}})

## QUIZ: USING $PUSH, $POP, $PULL, $PUSHALL, $PULLALL, $ADDTOSET

Suppose you have the following document in your friends collection:
{ _id : "Mike", interests : [ "chess", "botany" ] }
What will the result of the following updates be?
db.friends.update( { _id : "Mike" }, { $push : { interests : "skydiving" } } );
db.friends.update( { _id : "Mike" }, { $pop : { interests : -1 } } );
db.friends.update( { _id : "Mike" }, { $addToSet : { interests : "skydiving" } } );
db.friends.update( { _id : "Mike" }, { $pushAll: { interests : [ "skydiving" , "skiing" ] } } );
* { _id : "Mike", interests : [ "botany", "skydiving", "skydiving" , "skiing" ] }

## QUIZ: UPSERTS

After performing the following update on an empty collection
db.foo.update( { username : 'bar' }, { '$set' : { 'interests': [ 'cat' , 'dog' ] } } , { upsert : true } );
What could be a document in the collection?
* [ ] { "_id" : ObjectId("507b78232e8dfde94c149949"), "interests" : [ "cat", "dog" ]}
* [ ] {"interests" : [ "cat", "dog" ], "username" : "bar" }
* [ ] {}
* [X] { "_id" : ObjectId("507b78232e8dfde94c149949"), "interests" : [ "cat", "dog" ], "username" : "bar" }

## QUIZ: MULTI-UPDATE

Recall the schema of the scores collection:
{
	"_id" : ObjectId("50844162cb4cf4564b4694f8"),
	"student" : 0,
	"type" : "exam",
	"score" : 75
}
Give every document with a score less than 70 an extra 20 points.
* db.scores.update({'score':{$lt : 70}},{$inc:{score : 20}},{multi : true})

## QUIZ

## QUIZ

## QUIZ

## QUIZ

## QUIZ
