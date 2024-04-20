- find()

```bash
db.products.find()
```

- find() with condition

```bash
db.products.find({ Price: 1.99 })
```

- find() with condition and projection

```bash
db.products.find({ Price: 1.99 }, { Name: 1 })
```

- count()

```bash
db.products.find().count()
```

- limit()

```bash
db.products.find().limit(2)
```

- skip()

```bash
db.products.find().skip(2)
```

- sort()

```bash
db.products.find().sort({ Price: 1 })
```

- skip() and limit()

```bash
db.products.find().skip(2).limit(2)
```

- find() with condition and projection

```bash
db.products.find({ Price: { $gt: 1.99 } }, { Name: 1 })
```

- updateOne()

```bash
db.products.updateOne({ Price: 1.99 }, { $set: { Price: 2.49 } })
```

- update()

```bash
db.products.update({ Price: 1.99 }, { $set: { Price: 2.49 } })
```

- update() with multi

> update all documents with Price 1.99

```bash
db.products.update({ Price: 1.99 }, { $set: { Price: 2.49 } }, { multi: true })
```

- updateMany()

> update all documents with Price 1.99

```bash
db.products.updateMany({ Price: 1.99 }, { $set: { Price: 2.49 } })
```

- deleteOne()

```bash
db.products.deleteOne({ _id: ObjectId("5f0b3b3b3b3b3b3b3b3b3b3b") })
```

- deleteMany()

```bash
db.products.deleteMany({ Price: 1.99 })
```

- find() with or condition

```bash
db.products.find({ $or: [{ Price: 1.99 }, { Price: 2.49 }] })
```

- find() with in condition

```bash
db.products.find({ Price: { $in: [1.99, 2.49] } })
```

- find() with not in condition

```bash
db.products.find({ Price: { $nin: [1.99, 2.49] } })
```

- find() with exists condition

```bash
db.products.find({ Price: { $exists: true } })
```

- find() with not exists condition

```bash
db.products.find({ Price: { $exists: false } })
```

- find() null values

```bash
db.products.find({ Price: null })
```

- find() with and condition

```bash
db.products.find({ Price: 1.99, Name: "Pepsi" })
```

- find() with regex condition - search for products with name starting with A

```bash
db.products.find({ Name: { $regex: /P/ } })
```

- find() with projection

```bash
db.products.find({}, { Name: 1, Price: 1 })
```

- find() with projection excluding _id

```bash
db.products.find({}, { _id: 0, Name: 1, Price: 1 })
```



- find() greater than condition

```bash
db.products.find({ Price: { $gt: 1.99 } })
```

- find() less than condition

```bash
db.products.find({ Price: { $lt: 1.99 } })
```

- find() greater than or equal to condition

```bash
db.products.find({ Price: { $gte: 1.99 } })
```

- find() less than or equal to condition

```bash
db.products.find({ Price: { $lte: 1.99 } })
```

- top 2 products with highest price

```bash
db.products.find().sort({ Price: -1 }).limit(2)
```

- aggregate() with group

```bash
db.products.aggregate([
    { $group: { _id: "$Price", count: { $sum: 1 } } }
])
```

- aggregate() with match

```bash
db.products.aggregate([
    { $match: { Price: 1.99 } },
    { $group: { _id: "$Price", count: { $sum: 1 } } }
])
```

- aggregate() with group and project

```bash
db.products.aggregate([
    { $group: { _id: "$Price", count: { $sum: 1 } } },
    { $project: { _id: 0, Price: "$_id", count: 1 } }
])
```

- aggregate() with unwind

```bash
db.products.aggregate([
    { $unwind: "$Topings" }
])
```

- aggregate() with lookup

```bash
db.orders.aggregate([
    {
        $lookup: {
            from: "customers",
            localField: "CustomerID",
            foreignField: "_id",
            as: "Customer"
        }
    }
])
```

- aggregate() with unwind and lookup

```bash
db.orders.aggregate([
  { $match: { CustomerID: ObjectId('661dd8b2cc455df882a1f1e2')} },
  {
    $lookup: {
      from: "customers",
      localField: "CustomerID",
      foreignField: "_id",
      as: "Customer"
    }
  },
  { $unwind: "$Customer" },
  { $project: { CustomerID: 0, "Customer.Email": 0 } }
])
```


- create index

```bash
db.products.createIndex({ Price: 1 })
```

- create index with name
  
```bash
db.products.createIndex({ Price: 1 }, { name: "Price_1" })
```

- drop index

```bash
db.products.dropIndex("Price_1")
```

- explain()

```bash
db.products.find({ Price: 1.99 }).explain()
```

- explain() with executionStats

```bash
db.products.find({ Price: 1.99 }).explain("executionStats")
```

- about indexes

> - indexes are used to improve the performance of queries
> - indexes are created on fields that are used in queries
> - types of indexes: single field, compound, multikey, text, geospatial, hashed
> - single field index: index on a single field
> - compound index: index on multiple fields
> - multikey index: index on array fields
> - text index: index on text fields
> - geospatial index: index on geospatial fields

- sort by multiple fields

```bash
db.products.find().sort({ Price: 1, Name: 1 })
```
