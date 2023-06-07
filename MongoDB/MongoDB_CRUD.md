# CRUD

help

use <db_name> -- create db (db_name)

db -- which db you are in

The MongoDB shell provides the following methods to insert documents into a collection:  
db.collection.insertone()  
db.collection.inserMany()  
```
use sample_mflix

db.movies.insertOne(
  {
    title: "The Favourite",
    genres: [ "Drama", "History" ],
    runtime: 121,
    rated: "R",
    year: 2018,
    directors: [ "Yorgos Lanthimos" ],
    cast: [ "Olivia Colman", "Emma Stone", "Rachel Weisz" ],
    type: "movie"
  }
)

show collections
```

Read operations retrieves documents from a collection
db.collection.find()  

Update Documents  
db.collection.updateOne()  
db.collection.updateMany()  
db.collection.replaceOne()  
```
use sample_mflix

db.movies.updateOne( { title: "Tag" },
{
  $set: {
    plot: "One month every year, five highly competitive friends
           hit the ground running for a no-holds-barred game of tag"
  }
  { $currentDate: { lastUpdated: true } }
})
```

db.collection.deleteOne()
db.collection.deleteMany()