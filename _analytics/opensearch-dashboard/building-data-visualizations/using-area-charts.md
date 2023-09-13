---
layout: default
title: Using area charts
parent: Building data visualizations
grand_parent: Opensearch Dashboard
nav_order: 123
---

# Using area charts

An area chart is a line chart with the area between the line and the axis shaded with a color, and is a primary visualization type used to display time series data. You can create area charts in Dashboards using the Area visualization type or using the Time Series Visual Builder (TSVB), Vega, or VisBuilder visualization tools. For this tutorial, you’ll use the Area visualization type.

![Demonstration of the area chart tutorial steps]({{site.baseurl}}/images/using-area-charts/area-tutorial.gif)

# Try it: Create a simple aggregation-based area chart

In this tutorial you’ll create a simple area chart using sample data and aggregations in OpenSearch Dashboards by connecting to  [http://localhost:5601](http://localhost:5601/)  from a browser.

You have several aggregation options in Dashboards, and the choice influences your analysis. The use cases for aggregations vary from analyzing data in real time to using Dashboards to create a visualization dashboard. If you need an overview of aggregations in OpenSearch, see  [Aggregations](https://opensearch.org/docs/latest/opensearch/aggregations/)  before starting this tutorial.

Make sure you have  [installed the latest version of Dashboards](https://opensearch.org/docs/latest/install-and-configure/install-dashboards/index/)  and added the sample data before continuing with this tutorial.  _This tutorial uses Dashboards version 2.4.1_.

## Set up the area chart[](https://opensearch.org/docs/latest/dashboards/visualize/area/#set-up-the-area-chart)

1.  Access Dashboards by connecting to  [http://localhost:5601](http://localhost:5601/)  from a browser.
2.  Select  **Visualize**  from the menu and then select  **Create visualization**.
3.  Select  **Area**  from the window.
4.  Select  **opensearch_dashboards_sample_data_flights**  in the  **New Area/Choose a source**  window.
5.  Select the calendar icon and set the time filter to  **Last 7 days**.
6.  Select  **Update**.

## Add aggregations to the area chart[](https://opensearch.org/docs/latest/dashboards/visualize/area/#add-aggregations-to-the-area-chart)

Continuing with the area chart created in the preceding steps, you’ll create a visualization that displays the top five logs for flights delayed for every three hours over the last seven days:

1.  Add a  **Metrics**  aggregation.
    1.  Under  **Metrics**, select the  **Aggregation**  dropdown list and choose  **Average**  and then select the  **Field**  dropdown list and choose  **FlightDelayMin**.
    2.  Under  **Metrics**, select  **Add**  to add another Y-axis aggregation.
    3.  Select the  **Aggregation**  dropdown list and choose  **Max**  and then select the  **Field**  dropdown list and choose  **FlightDelayMin**.
2.  Add a  **Buckets**  aggregation.
    1.  Select  **Add**  to open the  **Add Bucket**  window and then select  **X-axis**.
    2.  From the  **Aggregation**  dropdown list, select  **Date Histogram**.
    3.  From the  **Field**  dropdown list, select  **timestamp**.
    4.  Select  **Update**.
3.  Add a sub-aggregation.
    1.  Select  **Add**  to open the  **Add Sub-Buckets**  window and then select  **Split series**.
    2.  From the  **Sub aggregation**  dropdown list, select  **Terms**.
    3.  From the  **Field**  dropdown list, select  **FlightDelay**.
    4.  Select  **Update**  to reflect these parameters in the graph.

You’ve now created the following aggregation-based area chart.

![Resulting aggregation-based area chart]({{site.baseurl}}/images/using-area-charts/area-aggregation-tutorial.png)

# Related links

-   [Visualize](https://opensearch.org/docs/latest/dashboards/visualize/viz-index/)
-   [Visualization types in OpenSearch Dashboards](https://opensearch.org/docs/latest/dashboards/visualize/viz-index/)
-   [Install and configure OpenSearch Dashboards](https://opensearch.org/docs/latest/install-and-configure/install-dashboards/index/)
-   [Aggregations](https://opensearch.org/docs/latest/opensearch/aggregations/)

