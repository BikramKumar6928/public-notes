## `essentials` keyspace

```cql
CREATE KEYSPACE essentials WITH replication = {'class': 'SimpleStrategy', 'replication_factor': 1};
```

## `movies` table
```cql
CREATE TABLE movies_with_actor (
	actor TEXT,
	release_year INT,
	movie_id uuid,
	title TEXT,
	genres SET<TEXT>,
	rating FLOAT,
	PRIMARY KEY ((movie_id))
)
```


## `movies_with_actor` table

```cql
CREATE TABLE movies_with_actor (
	actor TEXT,
	release_year INT,
	movie_id uuid,
	title TEXT,
	genres SET<TEXT>,
	rating FLOAT,
	PRIMARY KEY ((actor), release_year, movie_id)
) WITH CLUSTERING ORDER BY (release_year DESC, movie_id ASC);
```