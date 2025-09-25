## Definition

Consistency means that we do not read stale data. Stale data means that the data has already been modified somewhere in the cluster, but on reading, we still get the older data.

This is also called entropy of database.

## Levels of consistency

There are 3 levels of consistency:-

- `ALL` - In this, the confirmation is sent only after all the replicas has been updated.(This is generally **not recommended** as it causes high latency).
- `QUORUM` - In this, the confirmation is sent when the quorum number of nodes has been read/written.
  In case of multi-network clusters, there are 2 types of quorum:-
  - `LOCAL_QUORUM` - In this case, the response is sent when the nodes of a local cluster have been read/written to successfully.
  - `EACH_QUORUM` - In this case, the response is sent when the nodes of all the clusters in various clusters have been read/written to successfully. (This is generally **not recommended** as it causes high latency).
- `ONE` - In this, the confirmation is sent when 1 nodes has been read/written.
  This is a nice way to decrease latency, but the consistency is highly doubtful in these cases.
