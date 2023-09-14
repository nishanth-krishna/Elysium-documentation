---
layout: default
title: Types of Search
parent: Discover
# grand_parent: Log Analytics
nav_order: 12
redirect_from: analytics/discover/types-of-search
permalink: /analytics/discover/types-of-search/index.html
---

# Types of Search

## Quoted Search

This refers to a type of online search where the search terms are enclosed within quotation marks. This is also known as an exact match search. When quotation marks are used, the search engine will look for the exact phrase within the quotes and return results that match that exact phrase.

To search the data/records it will filter the given input values in the double quotes and will display the results based on matching the input values from the records stored in the database.

For Example,

![elysium-search]({{site.baseurl}}/images/elysium-search/image15.jpg)

Field/Property is denoted by username and the string value is denoted by "john smith"

*__Note:__ The field/property is optional, you can simply search by inputting the values. The search engine will find the records based on the given input from all the fields available in the database.*

## Unquoted Search

Unquoted search refers to performing a search in a search engine from the database without enclosing the search terms in quotation marks. In unquoted search, the Elysium search engine will return results that contain all the words in the search query in any order, and sometimes results that contain synonyms or related words.

To search the data/records it will filter the given input value and will display results based on matching the input values from the records stored in the database.

For example,

![elysium-search]({{site.baseurl}}/images/elysium-search/image14.jpg)

Field/Property is denoted by username and the string value is denoted by "smith"

*__Note:__ The field/property is optional, you can simply search by inputting the values. The search engine will find the records based on the given input from all the fields available in the database.*

## Wildcard Search

A wildcard search is a type of search that allows you to use special characters, called wildcards ( __*__ ), to represent one or more characters in a search term. This can be useful when you are looking for variations of a word or when you are searching for a term that has multiple spellings.

Wildcard search can only be used in unquoted search and the most commonly used wildcards are the asterisk ( __*__ ). The asterisk represents any number of characters. 

For example:

To search the data/records starting with ‘smith’ use the query syntax illustrated below

![elysium-search]({{site.baseurl}}/images/elysium-search/image16.jpg)

To search the data/records ending with ‘smith’ use the query syntax illustrated below

![elysium-search]({{site.baseurl}}/images/elysium-search/image13.jpg)

Wildcard search is also used to get all the records stored in the database using the query syntax illustrated below

![elysium-search]({{site.baseurl}}/images/elysium-search/image22.jpg)

*__Note 1:__ If you put the asterisk ( * ) at the starting and end ( *smith* ) of the input then it will explicit the values and consider as ( * ) will result in getting all records.

*__Note 2:__ The field/property is optional, you can simply search by inputting the values. The search engine will find the records based on the given input from all the fields available in the database.*

Field/Property denoted by username and string value denoted by "smith"

### Matching Multiple Fields in Wildcard Search

Wildcard search can also be used to query with multiple fields while searching the data where any of the sub-field (http.response) containing “error” as illustrated below

For example:

![elysium-search]({{site.baseurl}}/images/elysium-search/image7.jpg)

## Smart Search

This refers to a search algorithm or technology that uses advanced techniques to provide more relevant search results to users. on the other hand, uses artificial intelligence, machine learning, and natural language processing to understand the context and intent of a search query and deliver more accurate and personalized results.

When you’re searching for something on the Elysium search engine enables the smart search by default.

It can also understand the meaning of a query, rather than just matching keywords, and provide results based on the intent of the user's search.

It is the technology provided by Elysium Analytics that helps to improve the accuracy and relevance of search results, making it easier for users to find the information they need.


## Negating Search

Negating means to deny or negate the truth or validity of something. In logic and mathematics, negation refers to the operation of reversing or negating the truth value of a statement or proposition. 

In negate search specify some keywords with the query and the execution of the query resulting to retrieve the data.

Keywords that can be used to negate a query NOT, AND, OR 

### Negating search with NOT

NOT keyword is used to exclude the related data to the given query, you can use it in combination with other search terms to exclude certain results from your search.

For example,

![elysium-search]({{site.baseurl}}/images/elysium-search/image26.jpg)

The given query will filter the data except for the "HTTP GET methods” and will retrieve all the HTTP methods except the GET method.

### Negating search with AND

AND keyword is used to retrieve the data by combining two or more search queries to narrow down your results to only those that include both terms.

For example,

![elysium-search]({{site.baseurl}}/images/elysium-search/image27.jpg)

The given query will filter the data by combining both the queries and resulting to fetch all the HTTP GET methods including response code 400.

### Negating search with OR

OR keyword is used to help you find a wider variety of results that include any of the terms you are interested in querying.

For example,

![elysium-search]({{site.baseurl}}/images/elysium-search/image11.jpg)

The given query will tell the search engine to return results that include any of the terms.

### Negating Search with Combining Keywords

You can combine OR, AND, and NOT keywords with the parenthesis to create more complex search queries that include multiple search terms and operators. Here is an example of a search query that uses all three operators:

![elysium-search]({{site.baseurl}}/images/elysium-search/image23.jpg)

You can also use the parenthesis for shorthand syntax while generating multiple queries for the same field. 

For Example,

![elysium-search]({{site.baseurl}}/images/elysium-search/image8.jpg)

## Characters Need Escaping

Escaping is the process of inserting special characters, called escape sequences, into a string literal or character sequence. This is necessary when you need to include characters that would otherwise be interpreted as part of the programming language syntax, such as quotes or backslashes.

For example,

![elysium-search]({{site.baseurl}}/images/elysium-search/image10.jpg)

If you want to include a double quote character (") within a string literal that is also enclosed in double quotes, you need to escape the inner double quote character using a backslash ("). Otherwise, the string literal would be interpreted as ending at the first occurrence of the double quote, causing a syntax error.

Similarly, if you want to include a backslash (\) character within a string literal, you also need to escape it using another backslash (\). Otherwise, the backslash would be interpreted as an escape character, and the subsequent character would be interpreted as an escape sequence.

Characters that commonly need escaping including:

    \():<>"*[]{}







