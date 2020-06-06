## SELECT Data - GET

```
GET /adega/_doc/1

```

## COUNT - count number of documents

```
GET /adega/_count

```

## GET WITH PARAMS

```
GET /blogs/_search
{
  "query": {
    "match": {
      "content": "ingest nodes"
    }
  }
}
```

## RELEVANCE

```
GET /blogs/_search
{
  "query": {
    "match": {
      "content": {
        "query": "ingest nodes",
        "operator": "and"
      }
    }
  }
}
```








