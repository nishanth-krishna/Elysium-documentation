---
layout: default
title: Using Dashboards Query Language
parent: Exploring Data
grand_parent: Opensearch Dashboard
nav_order: 14
redirect_from: /analytics/opensearch-dashboard/exploring-data/using-dql/
permalink: /analytics/opensearch-dashboard/exploring-data/using-dql/index.html
---

# Using Dashboards Query Language

Dashboards Query Language (DQL) is a simple text-based query language for filtering data in OpenSearch Dashboards. Similar to  [Query DSL](https://opensearch.org/docs/latest/opensearch/query-dsl/index), DQL uses an HTTP request body. For example, to display your site visitor data for a host in the United States, you would enter  `geo.dest:US`  in the search field, as shown in the following image.

![Search term using DQL toolbar in Dashboard]({{site.baseurl}}/images/exploring-data/dql-interface.png)

Before you can search data in Dashboards, you must index it. In OpenSearch, the basic unit of data is a JSON document. Within an index, OpenSearch identifies each document using a unique ID. To learn more about indexing in OpenSearch, see  [Index data](https://opensearch.org/docs/latest/opensearch/index-data).

## Searching with terms queries[](https://opensearch.org/docs/latest/dashboards/discover/dql/#searching-with-terms-queries)

The most basic query specifies the search term, for example:

```
host:www.example.com

```

To access an object’s nested field, list the complete path to the field separated by periods. For example, use the following path to retrieve the  `lat`  field in the  `coordinates`  object:

```
coordinates.lat:43.7102

```

DQL supports leading and trailing wildcards, so you can search for any terms that match your pattern, for example:

```
host.keyword:*.example.com/*

```

To check whether a field exists or has any data, use a wildcard to see whether Dashboards returns any results,for example:

```
host.keyword:*

```

## Searching with Boolean queries[](https://opensearch.org/docs/latest/dashboards/discover/dql/#searching-with-boolean-queries)

To mix and match or combine multiple queries for more refined results, you can use the Boolean operators  `and`,  `or`, and  `not`. DQL is not case sensitive, so  `AND`  and  `and`  are the same, for example:

```
host.keyword:www.example.com and response.keyword:200

```

You also can use multiple Boolean operators in one query, for example:

```
geo.dest:US or response.keyword:200 and host.keyword:www.example.com

```

Remember that Boolean operators follow the logical precedence order of  `not`,  `and`, and  `or`, so if you have an expression like the one in the preceding example,  `response.keyword:200 and host.keyword:www.example.com`  is evaluated first.

To avoid confusion, use parentheses to dictate the order in which you want to evaluate operands. If you want to evaluate  `geo.dest:US or response.keyword:200`  first, you can use an expression like the following:

```
(geo.dest:US or response.keyword:200) and host.keyword:www.example.com

```

## Querying dates and ranges[](https://opensearch.org/docs/latest/dashboards/discover/dql/#querying-dates-and-ranges)

DQL supports numeric inequalities, for example,  `bytes >= 15 and memory < 15`.

You can use the same method to find a date before or after the date specified in the query.  `>`  indicates a search for a date after the specified date, and  `<`  returns dates before the specified date, for example,  `@timestamp > "2020-12-14T09:35:33`.

## Querying nested fields[](https://opensearch.org/docs/latest/dashboards/discover/dql/#querying-nested-fields)

Searching a document with  [nested fields](https://opensearch.org/docs/latest/opensearch/supported-field-types/nested/)  requires you to specify the full path of the field to be retrieved. In the following example document, the  `superheroes`  field has nested objects:

```
{
 "superheroes":[
    {
      "hero-name": "Superman",
      "real-identity": "Clark Kent",
      "age": 28
    },
    {
      "hero-name": "Batman",
      "real-identity": "Bruce Wayne",
      "age": 26
    },
    {
      "hero-name": "Flash",
      "real-identity": "Barry Allen",
      "age": 28
    },
    {
      "hero-name": "Robin",
      "real-identity": "Dick Grayson",
      "age": 15
    }
  ]
}

```

To retrieve documents that match a specific field using DQL, specify the field, for example:

```
superheroes: {hero-name: Superman}

```

To retrieve documents that match multiple fields, specify all the fields, for example:

```
superheroes: {hero-name: Superman} and superheroes: {hero-name: Batman}

```

You can combine multiple Boolean and range queries to create a more refined query, for example:

```
superheroes: {hero-name: Superman and age < 50}

```

## Querying doubly nested objects[](https://opensearch.org/docs/latest/dashboards/discover/dql/#querying-doubly-nested-objects)

If a document has doubly nested objects (objects nested inside other objects), retrieve a field value by specifying the full path to the field. In the following example document, the  `superheroes`  object is nested inside the  `justice-league`  object:

```
{
"justice-league": [
{
"superheroes":[
{
"hero-name": "Superman",
"real-identity": "Clark Kent",
"age": 28
},
{
"hero-name": "Batman",
"real-identity": "Bruce Wayne",
"age": 26
},
{
"hero-name": "Flash",
"real-identity": "Barry Allen",
"age": 28
},
{
"hero-name": "Robin",
"real-identity": "Dick Grayson",
"age": 15
}
]
}
]
}

```

The following image shows the query result using the example notation  `justice-league.superheroes: {hero-name:Superman}`.

![DQL query result]({{site.baseurl}}/images/exploring-data/dql-query-result.png)

