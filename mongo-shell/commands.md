# create database
> use characters
# add first document in the collection enemies (collection gets created now)
> db.enemies.insertOne({
    "name": "Blinky",
    "color": "Red"
})
 
# check if Blinky is added
> db.enemies.find().pretty()

# add multiple documents to the collection
> db.enemies.insertMany([ 
       {
        "name": "Inky",
        "color": "Cyan",
       },
       {
        "name": "Clyde",
        "color": "Orange"
       }])

# check if all documents are added (find all documents)
> db.enemies.find().pretty()

# find a specific document
> db.enemies.findOne({name: "Clyde"}).pretty()

# update one document
> db.enemies.updateOne({ name: "Inky" }, { $set: { color: "Red" } })

# update multiple documents
> db.enemies.updateMany({ color: "Red" }, { $set: { color: "Blue" } })

# delete one document from a collection
> db.enemies.deleteOne({name: "Clyde"})

# delete multiple documents from a collection
> db.enemies.deleteMany({color: "Blue"})