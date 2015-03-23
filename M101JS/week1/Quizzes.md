# QUIZZES

## QUIZ: WELCOME TO M101JS

What counts toward your final grade in the class?
* Homeworks
* Final Exam

## QUIZ: WHAT IS MONGODB?

Which of the following statements are true about MongoDB?
* MongoDB is document oriented.
* MongoDB is schemaless.

## QUIZ: MONGODB RELATIVE TO RELATIONAL

Which features did MongoDB omit in order to retain scalability?
* Joins
* Transactions across multiple collections

## QUIZ: QUICK INTRODUCTION TO THE MONGO SHELL

Which of the following expressions are valid JSON documents for MongoDB?
Remember, MongoDB doesn't require quotation marks around keys, as they must always be strings.
* { a : 1, b : 2, c : 3 }

## QUIZ: INTRODUCTION TO JSON

Which of the following are JSON documents that the MongoDB shell will accept?
* { a : 1, b : 2, c : 3 }
* { a : 1, b : 2, c : [ 1, 2, 3, 4, 5 ] }
* { a : 1, b : { }, c : [ { a : 1, b : 2 }, 5, 6 ] }
* { }

## QUIZ: JSON REVISITED

Write the JSON for a simple document containing a single key "fruit" that has as its value an array containing three strings: "apple", "pear", and "peach"
Note that this isn't a question about the mongo shell; you'll need to put quotation marks around your key.
* { "fruit": ["apple", "pear", "peach"] }

## QUIZ: JSON SUBDOCUMENTS

Write a JSON document with a single key, "address" that has as it value another document with the keys “street_address”, “city”, “state”, “zipcode”, with the following values: “street_address” is "23 Elm Drive", “city” is "Palo Alto", “state” is "California", “zipcode” is "94305"
* { "address": {"street_address": "23 Elm Drive", "city":"Palo Alto", "state": "California", "zipcode":"94305"} }

## QUIZ: BLOG IN RELATIONAL TABLES

let’s assume that our blog can be modeled with the following relational tables:
```
authors:
	author_id,
	name,
	email,
	password

posts:
	post_id,
	author_id
	title,
	body,
	publication_date

comments:
	comment_id,
	name,
	email,
	comment_text

post_comments:
	post_id,
	comment_id

tags
	tag_id
	name

post_tags
	post_id
	tag_id
  ```
In order to display a blog post with its comments and tags, how many tables will need to be accessed?
* 6

## QUIZ: BLOG IN DOCUMENTS

Given the document schema that we proposed for the blog, how many collections would we need to access to display the blog home page?
* 1

## QUIZ: BLOG IN DOCUMENTS
QUIZ: INTRODUCTION TO SCHEMA DESIGN
In which scenario is it impossible to embed data within a document (you must put the data in it a separate collection)?
* The embedded data could exceed the 16MB document limit within MongoDB.
