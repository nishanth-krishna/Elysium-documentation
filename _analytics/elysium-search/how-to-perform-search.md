---
layout: default
title: How to Perform Search
parent: Discover
# grand_parent: Log Analytics
nav_order: 11
redirect_from: analytics/discover/perform-search
permalink: /analytics/discover/perform-search/index.html
---

# How to Perform a Search

1. Launch the Elysium Analytic app, log in with your credentials, and click on the __Discover__ page under the Analytics section at the left sidebar.

    ![elysium-search]({{site.baseurl}}/images/elysium-search/image20.jpg)

2. Click on the Change Index Pattern dropdown and make sure you have selected the correct index to search the data.

    ![elysium-search]({{site.baseurl}}/images/elysium-search/image19.jpg)

3. Type the query in the search bar and set the parameters from the search options, then set the date and time as your choice from the calendar picker. 

    The search will be automatically performed or you can also click on the __Refresh__ button to execute the search with aggregated results.

    ![elysium-search]({{site.baseurl}}/images/elysium-search/image1.gif)

__Note:__ You can apply multiple types of search in the Elysium search such as Quoted search, Unquoted search, Wildcard search, and more. For more information follow the “Types of Search” section.

## Search Options

The search operation can be optimized based on your query requirements by switching between different search options.

### Case Sensitivity

In this option, uppercase and lowercase letters are considered distinct and are treated as separate characters while performing the search. For example, the words "hello" and "Hello" would be treated as two different words, whereas in a case-insensitive system, they would be treated as the same word.

You can enable the case sensitivity by toggling ON or disable it by toggling OFF.

![elysium-search]({{site.baseurl}}/images/elysium-search/image17.jpg)

### Query Timeout in Minutes

This is best suitable if the query is not executed properly or is consuming too much time. By using this search option, the query in progress will be automatically stopped after the defined time limit has elapsed. 

You can define the time limit only in “minutes”.

![elysium-search]({{site.baseurl}}/images/elysium-search/image21.jpg)

### Federated Search 

This search option relies upon OpenSearch and Snowflake databases to query and retrieve the data. If the data is 7 days old or less, then the same shall be queried from OpenSearch. If the data is older than 7 days, then the same shall be queried from Snowflake. 

You can enable the Federated Search by toggling ON or disabling it by toggling OFF, by default it is disabled.

![elysium-search]({{site.baseurl}}/images/elysium-search/image24.jpg)

## Selecting Date to a Query (Date Picker)

Define 	the date range for which you want to filter the results of your executed query. 

![elysium-search]({{site.baseurl}}/images/elysium-search/image25.gif)

Additionally, you can select the ___Commonly used__ or __Recently used date ranges__ with the Refresh every time feature.

![elysium-search]({{site.baseurl}}/images/elysium-search/image4.jpg)

## Adding Filters

Elysium Search provides you the functionality to filter the records returned by your query by following this workflow:

### Adding the Filters with Fields

Select the fields from the field section at the left bar __>__ Add the filter in the query by clicking on the ( __+__ ) button or remove the filter by clicking on the ( __–__ ) button respectively as illustrated below.

![elysium-search]({{site.baseurl}}/images/elysium-search/image2.gif)

*__Note:__ By simply clicking on the search bar, a dropdown will suggest you a list of fields based on which you can perform the search for the values.*

### Adding the Filter Individually

You can set this filter based on the fields in the table/index and enter the correct value according to the record you want to get from the database.

Click on __+ Add Filter__ Button > select the __Field__ you want to search value from > select the operator based on your value > and __Save__ the filter. This will automatically execute the query and render the results as illustrated below.

![elysium-search]({{site.baseurl}}/images/elysium-search/image18.gif)

## Save the Search

You can save your recent search by simply clicking on the save button beside the search bar.

![elysium-search]({{site.baseurl}}/images/elysium-search/image12.gif)


