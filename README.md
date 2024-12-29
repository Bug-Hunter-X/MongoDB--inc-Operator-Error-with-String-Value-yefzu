# MongoDB $inc Operator Error with String Value
This repository demonstrates a common error when using the `$inc` operator in MongoDB update queries.  The `$inc` operator is designed to increment a numerical value. Attempting to increment a field with a non-numeric value will result in an error.

## Bug
The bug lies in the incorrect usage of the `$inc` operator. The following query attempts to increment the `count` field with a string value, which is not supported.

```javascript
db.collection('myCollection').updateOne({ _id: 1 }, { $inc: { count: 'abc' } });
```

This will produce a MongoDB error indicating that the value provided is not a valid numerical value.

## Solution
The solution involves ensuring the value passed to the `$inc` operator is a valid number.

```javascript
db.collection('myCollection').updateOne({ _id: 1 }, { $inc: { count: 1 } });
```
