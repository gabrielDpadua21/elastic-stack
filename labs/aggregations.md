# Agregações

## Agregações de métricas

- Sum (soma)
```
{
    "size": 0,
    "aggs": {
        "sum.response_size": {
            "sum": {
                "field": "response_size"
            }
        }
    }
}
```


- Max (Valor máximo)

```
"aggs": {
    "max.response.size": {
        "max": {
            "field": "response_size"
        }
    }
}
```

- Min (Valor mínimo)

```
"aggs": {
    "min.response.size": {
        "min": {
            "field": "response_size"
        }
    }
}
```

- Size


- Valor médio (MEDIA)

```
{
    "size":0,
    "aggs": {
        "avg.response.size": {
            "avg": {
                "field": "response_size"
            }
        }
    }
}
```

- geoip (cardinality)

```
{
    "size": 0,
    "aggs": {
        "country_numbers": {
            "cardinality": {
                "field": "geoip.country_name.keyword"
            }
        }
    }
}
```

- Percentily

- date_histogram

```
{
    "size": 0,
    "aggs": {
        "logs_por_dia": {
            "date_histogram": {
                "field": "gtimestamp",
                "interval": "day"
            }
        }
    }
}
```

- histogram

```
{
    "size": 0,
    "aggs": {
        "logs_por_100_ms": {
            "histogram": {
                "field": "runtime_ms",
                "interval": 100
            }
        }
    }
}
```

- Range

```
{
    "size": 0,
    "aggs": {
        "runtime_range": {
            "range": {
                "field": "runtime_ms",
                "ranges": [
                    {
                        "from": 0,
                        "to": 100
                    },
                    {
                        "from": 100,
                        "to": 250
                    }
                ]
            }
        }
    }
}
```

- Terms

```
{
    "size": 0,
    "aggs": {
        "top_5_countrys": {
            "terms": {
                "field": "geoip.country_name.keyword",
                "size": 5
            }
        }
    }
}
```

- Terms - order by

```
{
    "size": 0,
    "aggs": {
        "top_5_countrys": {
            "terms": {
                "field": "geoip.country_name.keyword",
                "size": 5,
                "order": {
                    "_count": "desc"
                }
            }
        }
    }
}