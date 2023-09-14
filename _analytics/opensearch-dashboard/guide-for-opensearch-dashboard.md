---
layout: default
title: Guide for opensearch Dashboard
parent: Opensearch Dashboard
# grand_parent: Log Analytics
nav_order: 10
redirect_from: /analytics/opensearch-dasboard/opensearch-search-guide/
permalink: /analytics/opensearch-dasboard/opensearch-search-guide/index.html
---

# Guide for OpenSearch Dashboard

This quickstart guide covers the core concepts that you need to understand to get started with OpenSearch Dashboards. You’ll learn how to:

* Add sample data.
* Explore and inspect data.
* Visualize data.

    Before you get started, make sure you’ve installed OpenSearch and OpenSearch Dashboards. For information on installation and configuration, see Install and configure OpenSearch and Install and configure OpenSearch Dashboards.

## Adding sample data

Sample datasets come with visualizations, dashboards, and other tools to help you explore Dashboards before you add your own data. To add sample data, perform the following steps:

1. Verify access to OpenSearch Dashboards by connecting to [http://localhost:5601](http://localhost:5601) from a browser. The default username and password are <code>admin</code>.

2. On the OpenSearch Dashboards __Home__ page, choose __Add sample data__.

3. Choose __Add data__ to add the datasets, as shown in the following image.

![opensearch-dashboard]({{site.baseurl}}/images/opensearch-dashboard/add-sample-data.png)

## Exploring and inspecting data

In [Discover](https://opensearch.org/docs/latest/dashboards/discover/index-discover/), you can:

* Choose data to explore, set a time range for that data, search it using [Dashboards Query Language (DQL)](https://opensearch.org/docs/latest/dashboards/discover/dql/), and filter the results.
* Explore the data, view individual documents, and create tables summarizing the data’s contents.
* Visualize your findings.

### Try it: Getting familiar with Discover

1. On the OpenSearch Dashboards __Home__ page, choose __Discover__.

2. Change the [time filter](https://opensearch.org/docs/latest/dashboards/discover/time-filter/) to __Last 7 days__, as shown in the following image.

    ![opensearch-dashboard]({{site.baseurl}}/images/opensearch-dashboard/last-7--days.png)

3. Search using the DQL query <code>FlightDelay:true AND DestCountry: US AND FlightDelayMin >= 60</code> and then choose __Update__. You should see results for US-bound flights delayed by 60    minutes or more, as shown in the following image.

    ![opensearch-dashboard]({{site.baseurl}}/images/opensearch-dashboard/dql-search-field.png)

4. To filter data, choose __Add filter__ and then select an __Available field__. For example, select <code>FlightDelayType</code>, __is__, and __Weather delay__ from the __Field__, __Operator__, and __Value__ dropdown lists, as shown in the following image.

    ![opensearch-dashboard]({{site.baseurl}}/images/opensearch-dashboard/filter-data-discover.png)

## Visualizing data

Raw data can be difficult to comprehend and use. Data visualizations help you prepare and present data in a visual form. In __Dashboard__ you can:

* Display data in a single view.
* Build dynamic dashboards.
* Create and share reports.
* Embed analytics to differentiate your applications.

### Try it: Getting familiar with Dashboard

1. On the OpenSearch Dashboards __Home page__, choose Dashboard.

2. Choose __[Flights] Global Flight Data__ in the __Dashboards__ window, as shown in the following image.

    ![opensearch-dashboard]({{site.baseurl}}/images/opensearch-dashboard/dashboard-flight-quickstart.png)

3. To add panels to the dashboard, choose __Edit__ and then __Add__ from the toolbar.

4. In the __Add panels__ window, choose the existing panel __[Flights] Delay Buckets__. You’ll see a pop-up window on the lower right confirming that you’ve added the panel.

5. Select <code>x</code> to close the __Add panels__ window.

6. View the added panel __[Flights] Delay Buckets__, which is added as the last panel on the dashboard, as shown in the following image.

    ![opensearch-dashboard]({{site.baseurl}}/images/opensearch-dashboard/add-panel.png)

### Try it: Creating a visualization panel

Continuing with the preceding dashboard, you’ll create a bar chart comparing the number of canceled flights and delayed flights to delay type and then add the panel to the dashboard:

1. Change the default [time range](https://opensearch.org/docs/latest/dashboards/discover/time-filter/) from __24 hours__ to __Last 7 days__.
2. In the toolbar, choose __Edit__, then __Create new__.
3. Select __VisBuilder__ in the __New Visualizations__ window.
4. In the __Data Source__ dropdown list, choose <code>opensearch_dashboards_sample_data_flights</code>.
5. Drag the fields __Cancelled__ and __FlightDelay__ to the y-axis column.
6. Drag the field __FlightDelayType__ to the x-axis column.
7. Choose __Save__ and name the visualization in the __Title__ field.
8. Choose __Save and return__. The following bar chart is added as the last panel on the dashboard, as shown in the following image.

    ![opensearch-dashboard]({{site.baseurl}}/images/opensearch-dashboard/viz-panel-quickstart.png)

## Interacting with data

Interactive dashboards allow you analyze data in more depth and filter it in several ways. In Dashboards, you can interact directly with data on a dashboard by using dashboard-level filters. For example, continuing with the preceding dashboard, you can filter to show delays and cancellations for a specific airline.

### Try it: Interacting with the sample flight data

On the __[Flights] Airline Carrier__ panel, choose __OpenSearch-Air__. The dashboard updates automatically.

Choose __Save__ to save the customized dashboard.

Alternatively, you can apply filters using the dashboard toolbar:

1. In the dashboard toolbar, choose __Add filter__.

2. From the __Field__, __Operator__, and __Value__ dropdown lists, choose __Carrier__, __is__, and __OpenSearch-Air__, respectively, as shown in the following image.

    ![opensearch-dashboard]({{site.baseurl}}/images/opensearch-dashboard/edit-filter.png)

3. Choose __Save__. The dashboard updates automatically, and the result is the dashboard shown in the following image.

    ![opensearch-dashboard]({{site.baseurl}}/images/opensearch-dashboard/interact-filter-dashboard.png)

## Next steps

* __Visualize data__. To learn more about data visualizations in OpenSearch Dashboards, see __Building data visualizations__.
* __Create dashboards__. To learn more about creating dashboards in OpenSearch Dashboards, see __Creating dashboards__.
* __Explore data__. To learn more about exploring data in OpenSearch Dashboards, see __Exploring data__.



