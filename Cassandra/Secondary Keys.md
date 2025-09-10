## Need of secondary keys

We cannot make a `where` query on a particular column if it is not present in the keys. 
So, if we want to make a query containing a column, then we must use secondary indices.

## Syntax for creation

```cql
CREATE CUSTOM INDEX title on movies_by_actor (title) 
'org.apache.cassandra.index.sasi.SASIIndex' WITH OPTIONS = { 'mode' : 'CONTAINS' }; 
```

## Different modes

There are different modes for options, which determines what kind of queries you can make:-

- `CONTAINS` - Queries like '%man' or 'Bird%' or '%ird%' can be made.
- `PREFIX`
- `SPARSE`

## Example of query

If we create the secondary index, then we will be able to create this kind of query:-

```cql
SELECT * FROM movies_by_actor WHERE actor='Emma Stone' AND title LIKE '%man' 

```
