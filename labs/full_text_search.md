## QUERY BY MATCH PHRASE

```
GET /blogs/_search
{
  "query": {
    "match_phrase": {
      "content": {
        "query": "open data"
      }
    }
  }
}
```

## QUERY BY MATCH PHRASE WITH SLOP BETWEEN WORDS

```
GET /blogs/_search
{
  "query": {
    "match_phrase": {
      "content": {
        "query": "open data",
        "slop": 1
      }
    }
  }
}
```

## QUERY BY MULTI MATCH FILDS

```
GET /blogs/_search
{
  "query": {
    "multi_match": {
      "query": "elasticsearch training",
      "fields": [
        "title*2",
        "content",
        "author"
      ],
      "type": "phrase"
    }
  }
}
```

## QUERY WITH PARAM FIZZY 

- WARNING (High use of CPU)

```
GET /blogs/_search
{
  "query": {
    "match": {
      "content": {
        "query": "shark",
        "fuzziness": 1
      }
    }
  }
}
```

# BOOL QUERYS

## MUST QUERYS - MATCHS

```
GET /blogs/_search
{
  "query": {
    "bool": {
      "must": [
        {
          "match": {
            "content": "logstash"
          }
        },
        {
          "match": {
            "category": "engineering"
          }
        }
      ]
    }
  }
}
```

## MUST NOT - MATCHS

```
GET /blogs/_search
{
  "query": {
    "bool": {
      "must": [
        {
          "match": {
            "content": "logstash"
          }
        }
      ],
      "must_not": [
        {
          "match": {
            "category": "releases"
          }
        }
      ]
    }
  }
}
```

## SHOULD - get document and score ranking

```
GET /blogs/_search
{
  "query": {
    "bool": {
      "must": [
        {
          "match_phrase": {
            "content": "elastic stack"
          }
        }
      ],
      "should": [
        {
          "match_phrase": {
            "author": "shay banon"
          }
        }
      ]
    }
  }
}
```

## FILTER - get document if exists

```
GET /blogs/_search
{
  "query": {
    "bool": {
      "must": [
        {
          "match": {
            "content": "logstash"
          }
        }
      ],
      "filter": {
        "match": {
          "category": "engineering"
        }
      }
    }
  }
}
```