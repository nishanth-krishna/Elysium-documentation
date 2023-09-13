---
layout: default
title: Exploring Data
nav_order: 12
parent: Opensearch Dashboard
# grand_parent: Log Analytics
has_children: true
redirect_from:
  - /documentation/log-analytics/opensearch-dashboard/exploring-data
---


# Exploring data

**Discover**  in OpenSearch Dashboards helps you extract insights and get value out of data assets across your organization. Discover enables you to:

1.  **Explore data**. You can explore, customize, and filter data as well as search data using  [Dashboards Query Language (DQL)](https://opensearch.org/docs/latest/dashboards/dql/).
2.  **Analyze data**. You can analyze data, view individual documents, and create tables summarizing data contents.
3.  **Visualize data**. You can display findings from your saved searches in a single dashboard that combines different data visualization types.

## Try it: Exploring sample data with Discover[](https://opensearch.org/docs/latest/dashboards/discover/index-discover/#try-it-exploring-sample-data-with-discover)

This tutorial shows you how to use Discover to analyze and understand a sample dataset. At the end of this tutorial, you should be ready to use Discover with your own data.

Before starting this tutorial, make sure you’ve added the  **Sample flight data**. See  [Quickstart guide for OpenSearch Dashboards](https://opensearch.org/docs/latest/dashboards/quickstart-dashboards/)  for information about how to get started.

### Setting up data[](https://opensearch.org/docs/latest/dashboards/discover/index-discover/#setting-up-data)

Watch the following short video or start with the tutorial steps to learn how to set up a sample dataset in Discover.

![Setting up the sample data in Discover]({{site.baseurl}}/images/exploring-data/discover-setting-up-data.gif)

1.  Verify access to OpenSearch Dashboards by connecting to  [http://localhost:5601](http://localhost:5601/)  from a browser. The default username and password are  `admin`.
2.  On the  **Home**  page, choose  **Discover**  in the navigation pane.
3.  On the index pattern toolbar, select the  **opensearch_dashboards_sample_data_flights**  dataset.
4.  On the time filter toolbar, choose the calendar icon and then change the time range to  **Last 7 days**.

### Exploring the data fields[](https://opensearch.org/docs/latest/dashboards/discover/index-discover/#exploring-the-data-fields)

In the  **Discover**  panel, you’ll see a table that shows all the documents that match your search. The table includes a list of data fields that are available in the document table, as shown in the following image.

![Exploring data fields interface]({{site.baseurl}}/images/exploring-data/discover-data-fields.png)

Follow these steps to explore the data fields:

1.  View the list of  **Available fields**.
2.  Choose  **Cancelled**  to view the values (`true`  and  `false`).
3.  Choose the plus (+) sign to add the field to the document table. The field will be automatically added to  **Selected fields**  and the document table.
4.  Select  **FlightDelay**  from the  **Available fields**  list, and then choose the plus (+) sign to add the field to the document table.
5.  Optional: Rearrange the table columns by selecting the table header and then choosing  **Move left**  or  **Move right**.

## Searching data[](https://opensearch.org/docs/latest/dashboards/discover/index-discover/#searching-data)

You can use the search toolbar or enter a DQL query in the  **DevTools**  console to search data in Dashboards, as shown in the following image. The search toolbar is best for basic queries, such as searching by a field name. DQL is best for complex queries, such as searching data using a term, string, Boolean, date, range, or nested query.

![Searching data interface](https://opensearch.org/docs/latest/images/discover-search.png)

Follow these steps to search data:

1.  In the search toolbar, enter the Boolean query. For example, enter  `FlightDelay:true AND FlightDelayMin >= 60`  to search the data for flights delayed by 60 minutes or more.
2.  Choose  **Update**.
3.  Optional: Choose the arrow (`>`) in a table row to expand the row and view the document table details.

## Filtering data[](https://opensearch.org/docs/latest/dashboards/discover/index-discover/#filtering-data)

Filters allow you to refine sets of documents to subsets of those documents. For example, you can filter data to include or exclude certain fields, as shown in the following image.

![Filtering data interface]({{site.baseurl}}/images/exploring-data/discover-filter.png)

Follow these steps to filter data:

1.  In the filter bar, choose  **Add filter**.
2.  Select options from the  **Field**,  **Operator**, and  **Value**  dropdown lists. For example,  `Cancelled`,  `is`, and  `true`.
3.  Choose  **Save**.
4.  To remove the filter, choose the close icon (x) next to the filter name.
5.  Optional: Add more filters to further explore the data.

## Analyzing data in the document table[](https://opensearch.org/docs/latest/dashboards/discover/index-discover/#analyzing-data-in-the-document-table)

You can view the document table fields to better understand the data and gather insights for more informed decision-making:

1.  Choose the arrow icon (>) to expand a table row.
2.  View the fields and details.
3.  Switch between the  **Table**  and  **JSON**  tabs to view the different formats, as shown in the following image.

![Analyzing data in the document table]({{site.baseurl}}/images/exploring-data/discover-analyze.png)

## Saving the search[](https://opensearch.org/docs/latest/dashboards/discover/index-discover/#saving-the-search)

Saving a search saves the query text, filters, and current data view. To save your search to use it later, generate a report, or build visualizations and dashboards:

1.  Choose the save icon in the toolbar.
2.  Give the search a title, and then choose  **Save**.
3.  Choose the save icon to access the saved search, as shown in the following image.

![Save search interface]({{site.baseurl}}/images/exploring-data/discover-save.png)

## Visualizing the search[](https://opensearch.org/docs/latest/dashboards/discover/index-discover/#visualizing-the-search)

You can quickly visualize an aggregated field from  **Discover**:

1.  From the  **Available fields**  list, select  `FlightDelayType`  and then choose  **Visualize**, as shown in the following image.

![Visualizing search queries from Discover]({{site.baseurl}}/images/exploring-data/discover-visualize.png)

Dashboards creates a visualization for this field, which in this case is a basic bar chart, as shown in the following image.

![Bar chart created from Discover]({{site.baseurl}}/images/exploring-data/discover-visualize-2.png)

[](https://opensearch.org/docs/latest/dashboards/discover/index-discover/#top)


