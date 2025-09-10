# Cassandra Primary Keys

Cassandra has two types of primary keys:-

1.  Partition keys
2.  Clustering keys

## Partition Keys

The partition keys decide the node on which a particular data will be present.

For example, in the `movies_by_actor` table, `actor` is a partition key.

This means that all the movies of an actor will be on the same node.

## Clustering Keys

The clustering keys provide ordering to the rows in the node.


