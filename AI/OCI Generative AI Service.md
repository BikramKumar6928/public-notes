#ai #notes
# OCI Generative AI

## Pretrained foundational models

Chat -> Chat models. Available models -> command-r-plus, command-r-16k, llama3-70b-instruct
Embedding -> Convert text to Vector Embeddings. Available models -> embed-english-v3.0, embed-multilingual-v3.0
## Dedicated AI clusters

OCI has dedicated AI clusters connected with RDMA for workloads.

# Vector Search

There are additional syntax added in Oracle Database 23ai for performing vector search. The SQL can combine vector search, relational search, etc.

Example SQL for fetching top 5 customers by similarity with a search photo vector

```sql
SELECT id, name, photo
FROM Customers
ORDER BY VECTOR_DISTANCE(photo_vec, :QUERY_VEC)
FETCH APPROXIMATE FIRST 5 ROWS ONLY;
```


# Select AI

The Select AI tool uses LLM to fetch data from a database using Natural Language. This can either return the results or the SQL to return the results

Example SQL for returning results

```sql
SELECT ai
What are the movies in which George Clooney acted;
```

Example SQL for returning query

```sql
SELECT ai showsql
What are the movies in which George Clooney acted;
```
