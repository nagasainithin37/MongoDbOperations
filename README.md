# MongoDb Operations

## To check all databases

    show dbs

## To check current db

    dbs

## To use a db or switch db

    use {db name}

## To create collection

    db.createCollection('name')

## To see collections in current database

    show collections

## Insert Operations

    db.collection-name.insertOne({})
    db.collection-name.insertMany([{},{},{},...{}])

## Reading documents

    findOne(condition)---->return first document satisfying condition
    find()            ----> return all documents satisfying the condition

    ex:

    findOne({field:{operator:value}})
    findOne({username:{$eq:'tempname'}})

## How to write Conditons

#### Some common used ones

    $eq     =   Equal to
    $lt     =   less than
    $lte    =   less than equal to
    $gt     =   greater than
    $gte    =   greater than equal to
    $ne     =   not equal to
    $in     =   in
    $nin    =   not in

#### Logical operators

    $and
    $or
    $not

    {$or:[{$and:[{salary:{$gte:10000}},{city:{$eq:'hyderabad'}}]},{$and:[{salary:{$gte:40000}},{city:{$eq:'Delhi'}}]}]}

    ===> (salary>=10000 && city=='hyderabad) or (salary>=40000 && city=='delhi')

## Projecting Specific fields of Document

    find({condition},{projection fields})

    find({},{name:1}) ===> only name is projected

## Update Values

    updateOne({conditon},{$set:{new values}})
    updateMany({conditon},{$set:{new values}})


    eg

        updateOne({name:{$e1:'ravi'}},{$set:{name:'ravi kumar',salary : 40000}})

## Deletion

    deleteOne({condition})
    deleteMany({condition})

## find().count()

    find({codition}).count() === > return no of docs with the conditions

## find().sort()

    find().sort({field:1})
    find().sort({field:-1})

    eg

    find().sort({age:1})
