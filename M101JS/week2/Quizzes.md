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
* [o] db.scores.find({ score : { $gte : 50 , $lte : 60 } } );
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
* [o] Find all documents with score less than 60
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
* [o] { name : "Cliff" , friends : [ "Pete" , "Joe" , "Tom" , "Bob" ] , favorites : [ "pickles", "cycling" ] }
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
* [o] This can be done at any point before the first document is called and before you've checked to see if it is empty.
* [ ] This can be done at any point, and will apply to any documents the cursor hasn't yet pulled.

## QUIZ

## QUIZ

## QUIZ

## QUIZ

## QUIZ

## QUIZ

## QUIZ

## QUIZ
