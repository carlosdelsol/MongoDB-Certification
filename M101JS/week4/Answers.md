# HOMEWORK

## HOMEWORK 4.1
'''
Suppose you have a collection with the following indexes:

> db.products.getIndexes()
[
	{
		"v" : 1,
		"key" : {
			"_id" : 1
		},
		"ns" : "store.products",
		"name" : "_id_"
	},
	{
		"v" : 1,
		"key" : {
			"sku" : 1
		},
                "unique" : true,
		"ns" : "store.products",
		"name" : "sku_1"
	},
	{
		"v" : 1,
		"key" : {
			"price" : -1
		},
		"ns" : "store.products",
		"name" : "price_-1"
	},
	{
		"v" : 1,
		"key" : {
			"description" : 1
		},
		"ns" : "store.products",
		"name" : "description_1"
	},
	{
		"v" : 1,
		"key" : {
			"category" : 1,
			"brand" : 1
		},
		"ns" : "store.products",
		"name" : "category_1_brand_1"
	},
	{
		"v" : 1,
		"key" : {
			"reviews.author" : 1
		},
		"ns" : "store.products",
		"name" : "reviews.author_1"
	}
'''
Which of the following queries can utilize an index to find all matching documents or to sort? Check all that apply.
* [ ] db.products.find({'brand':"GE"})
* [o] db.products.find({'brand':"GE"}).sort({price:1})
* [ ] db.products.find({brand:'GE'}).sort({category:1, brand:-1}).explain()
* [o] db.products.find({$and:[{price:{$gt:30}},{price:{$lt:50}}]}).sort({brand:1})

## HOMEWORK 4.2
MAL
* [ ] The query returns 251120 documents.
* [o] The query examines 251120 documents.
* [o] The query is a covered query.
* [ ] The query uses an index to determine which documents match.
* [o] The query uses an index to determine the order in which to return result documents.

## HOMEWORK 4.3
'''
Making the Blog fast
To get started, please download hw4-3.zip from the Download Handout link and unpack file to your computer. This assignment requires Mongo 2.2 or above.

In this homework assignment you will be adding some indexes to the post collection to make the blog fast.

We have provided the full code for the blog application and you don't need to make any changes, or even run the blog. But you can, for fun.

We are also providing a patriotic (if you are an American) data set for the blog. There are 1000 entries with lots of comments and tags. You must load this dataset to complete the problem.

# from the mongo shell
use blog
db.posts.drop()
# from the a mac or PC terminal window
mongoimport -d blog -c posts < posts.json
The blog has been enhanced so that it can also display the top 10 most recent posts by tag. There are hyperlinks from the post tags to the page that displays the 10 most recent blog entries for that tag. (run the blog and it will be obvious)

Your assignment is to make the following blog pages fast:

The blog home page
The page that displays blog posts by tag (http://localhost:8082/tag/whatever)
The page that displays a blog entry by permalink (http://localhost:8082/post/permalink)
By fast, we mean that indexes should be in place to satisfy these queries such that we only need to scan the number of documents we are going to return.

To figure out what queries you need to optimize, you can read the code in posts.js and see what queries it is doing to return the data needed for the relevant pages. Isolate those queries and use explain to explore.
'''
* db.posts.ensureIndex( { date: -1 } )
* db.posts.ensureIndex( { permalink: 1 }, { unique: true } )
* db.posts.ensureIndex( { tags: 1 } )

## HOMEWORK 4.4
'''
In this problem you will analyze a profile log taken from a mongoDB instance. To start, please download sysprofile.json from Download Handout link and import it with the following command:

mongoimport -d m101 -c profile < sysprofile.json
Now query the profile data, looking for all queries to the students collection in the database school2, sorted in order of decreasing latency. What is the latency of the longest running operation to the collection, in milliseconds?
'''
* [ ] 19776550
* [ ] 10000000
* [ ] 5580001
* [o] 15820
* [ ] 2350
