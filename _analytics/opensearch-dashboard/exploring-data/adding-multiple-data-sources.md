---
layout: default
title: Adding multiple data sources
parent: Exploring Data
grand_parent: Opensearch Dashboard
nav_order: 12
redirect_from: /analytics/opensearch-dashboard/exploring-data/add-datasources/
permalink: /analytics/opensearch-dashboard/exploring-data/add-datasources/index.html
---

# Adding multiple data sources.

    The multiple data sources feature is an experimental feature released in OpenSearch 2.4. It can’t be used in a production environment. For updates on the feature’s progress or to leave feedback on improving the feature, see the [OpenSearch Forum discussion](https://forum.opensearch.org/t/feedback-experimental-feature-connect-to-external-data-sources/11144).

You can add multiple data sources to a single dashboard. OpenSearch Dashboards allows you to dynamically manage data sources, create index patterns based on those data sources, and execute queries against a specific data source and then combine visualizations in one dashboard.

In this tutorial we provide the steps for enabling the <code>data_source</code> setting in Dashboards; adding credentials, data source connections, and index patterns; and combining visualizations in a single dashboard.

## Try it: Exploring the multiple data sources feature in your local environment

<pre>This tutorial uses a preconfigured data source and index pattern, and you aren’t required to configure settings. However, you’ll need to enable the <code>data_source</code> setting in the configuration file before before getting started with exploring this feature.</pre>

The multiple data sources feature is experimental and can’t be deployed into production. You can try it out with a sample data source and a sample index pattern. Before getting started, you must first edit the YAML configuration. The following section provides the steps for enabling the feature.

## Modifying the multiple data sources settings

Dashboards is configured in the cluster settings, and the multiple data sources feature is disabled by default. To enable it, you need to edit the configuration in <code>opensearch_dashboards.yml</code> and then restart the cluster.

To enable the feature:

1. Navigate to your Dashboards home directory; for example, in Docker, <code>/usr/share/opensearch-dashboards</code>.

2. Open your local copy of the Dashboards configuration file, <code>opensearch_dashboards.yml</code>. If you don’t have a copy, get one from GitHub: <code>opensearch_dashboards.yml.</code>

3. Set <code>data_source.enabled: false</code> to <code>data_source.enabled: true</code> and save the configuration.

4. Restart the Dashboards container.

5. Verify the feature configuration settings were created and configured properly by connecting to Dashboards through [http://localhost:5601](http://localhost:5601/) and viewing the __Stack Management__ console. __Data Sources__ Experimental will appear in the sidebar. Alternatively, you can open on [http://localhost:5601/app/management/opensearch-dashboards/dataSources](http://localhost:5601/app/management/opensearch-dashboards/dataSource).

## Creating a data source connection

A data source connection specifies the parameters needed to connect to a data source. These parameters form a connection string for the data source. In Dashboards, you can add new data source connections or edit existing connections.

To create a new data source connection:

1. Open Dashboards. If you’re not running the security plugin, go to <code>http://localhost:5601</code>. If you’re running the security plugin, go to <code>https://localhost:5601</code> and log in with the username <code>admin</code> and password <code>admin</code>.

2. Under __Management__ in the OpenSearch Dashboards main menu, choose __Stack Management__, ___Data Sources__ <code>Experimental</code>, __Data Sources__, and then choose __Create data source connection__, as shown in the following image.

    ![exploring-data]({{site.baseurl}}/images/exploring-data/multi-data-sources-1.png)

3. Add information to each field to configure __Connection Details__, __Endpoint URL__, and __Authentication Method__, as shown in the following image. For this tutorial, the __Endpoint URL__ is <code>http://localhost:5601/app/management/opensearch-dashboards/dataSources</code>.

    ![exploring-data]({{site.baseurl}}/images/exploring-data/multi-data-sources-2.png)

In <code>Connection Details</code>, enter a title for the connection and the endpoint URL used to connect to the data source. A description of the connection is optional.

For __Authentication Method__, first select the type of authentication:

* __No authentication:__ No authentication is used to connect to the data source.
* __Username & Password:__ A basic username and password are used to connect to the data source.
* __AWS SigV4:__ An AWS Signature Version 4 authenticating request is used to connect to the data source. AWS SigV4 requires an access key ID and a secret access key. First specify the ___Region__, and then enter the __Access Key__ and __Secret Key__ for authorization. For information on available Regions for AWS accounts, see [Available Regions](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-regions-availability-zones.html#concepts-available-regions). For more on SigV4 authentication requests, see [Authenticating Requests (AWS Signature Version 4)](https://docs.aws.amazon.com/AmazonS3/latest/API/sig-v4-authenticating-requests.html).

When you select the authentication method, the applicable fields appear for the selected method. Enter the required details.

After you have entered the appropriate details in all of the required fields, the __Test connection__ and __Create data source connection__ buttons become active. You can choose __Test connection__ to confirm that the connection is valid.

4. Choose __Create data source connection__ to save your settings. The connection is created. The active window returns to the __Data Sources__ main page, and the new connection appears in the list of data sources.

    ![exploring-data]({{site.baseurl}}/images/exploring-data/multi-data-sources-3.png)

    You can also delete the data source connection from this page by selecting the check box to the left of the title and then choosing __Delete 1 connection__ to the right of the search bar. Selecting multiple check boxes for multiple connections is also supported.

### Editing and updating a data source connection

To make changes to the data source connection, select a connection in the list on the __Data Sources__ main page. The connection details window opens, as shown in the following image.

![exploring-data]({{site.baseurl}}/images/exploring-data/multi-data-sources-3-5.png)

To make changes to  **Connection Details**, edit one or both of the  **Title**  and  **Description**  fields and choose  **Save changes**  in the lower-right corner of the screen. You can also cancel changes here. To change the  **Authentication Method**, choose a different authentication method, enter your credentials if applicable, and then choose  **Save changes**  in the lower-right corner of the screen. The changes are saved.

When  **Username & Password**  is the selected authentication method, you can update the password by choosing  **Update stored password**  next to the  **Password**  field. In the pop-up window, enter a a new password in the first field and then enter it again in the second field to confirm. Choose  **Update stored password**  in the pop-up window. The new password is saved. Choose  **Test connection**  in the upper-right corner of the screen to confirm that the connection is valid.

When  **AWS SigV4**  is the selected authentication method, you can update the credentials by choosing  **Update stored AWS credential**. In the pop-up window, enter a new access key in the first field and a new secret key in the second field. Choose  **Update stored AWS credential**  in the pop-up window. The new credentials are saved. Choose  **Test connection**  in the upper-right corner of the screen to confirm that the connection is valid.

To delete the data source connection, choose the red trash can icon in the upper-right corner of the screen.

## Creating an index pattern[](https://opensearch.org/docs/latest/dashboards/discover/multi-data-sources/#creating-an-index-pattern)

Index patterns allow you to access the OpenSearch data that you want to explore. An index pattern selects the data to use and allows you to define the field properties. Learn how to load your own data and create an index pattern following these steps. This tutorial uses the preconfigured index pattern  `opensearch_dashboards_sample_data_ecommerce Default`.

1. In the Dashboards console, choose **Index Patterns** > **Create index pattern**, as shown in the following image.

    ![exploring-data]({{site.baseurl}}/images/exploring-data/multi-data-sources-5.png)

2. Choose __Use external data source connection__.

3. Start typing in the  **Search data sources**  field to search for the data source you created earlier and then select the data source and  **Next step**, as shown in the following image.

    ![Index pattern search user interface]({{site.baseurl}}/images/exploring-data/multi-data-sources-6.png)

4.  Add an  **Index pattern name**  to define the index pattern and then choose  **Next step**, as shown in the following image.

    ![Index pattern define user interface]({{site.baseurl}}/images/exploring-data/multi-data-sources-7.png)
    
5.  Select an option for the  **Time field**  and then choose  **Create index pattern**, as shown in the following image.

    ![Index pattern time field user interface]({{site.baseurl}}/images/exploring-data/multi-data-sources-8.png)

## Searching data[](https://opensearch.org/docs/latest/dashboards/discover/multi-data-sources/#searching-data)

Before you start searching for data, set up the time filter. The sample index pattern used for this tutorial contains time-based data. You can set a time filter that displays only the data within a specified time range, and you can choose the time filter to change the time range or select a specific time range in the histogram.

### Adjusting the time filter[](https://opensearch.org/docs/latest/dashboards/discover/multi-data-sources/#adjusting-the-time-filter)

To adjust the time filter:

1.  In the Dashboards console, choose  **Discover**  and confirm that the index pattern being used is  `opensearch_dashboards_sample_data_ecommerce`.

2.  Choose the calendar icon to change the time field. The default is  **Last 15 minutes**.

3.  Change the time field to  **Last 7 days**  and choose  **Refresh**, as shown in the following image.

    ![Time filter user interface]({{site.baseurl}}/images/exploring-data/multi-data-sources-9.png)
    
4.  To set the start and end times, choose the bar next to the time filter. In the popup, select  **Absolute**,  **Relative**, or  **Now**  and then specify the required options, as shown in the following image.

    ![Start and end times user interface]({{site.baseurl}}/images/exploring-data/multi-data-sources-10.png)


### Selecting a time range from the histogram[](https://opensearch.org/docs/latest/dashboards/discover/multi-data-sources/#selecting-a-time-range-from-the-histogram)

To select a time range for the histogram, you can do one of the following:

-   Select the bar that represents the time range you want to zoom in on.
-   Select the bar and drag to view a specific time range. You must start the selection with the cursor over the background of the chart (the cursor changes to a plus sign when you hover over a valid start point).
-   Select the dropdown and then select an interval.

The following image shows a date histogram with an interval dropdown list.

![Histogram user interface]({{site.baseurl}}/images/exploring-data/multi-data-sources-11.jpg)


## Creating data visualizations for a dashboard[](https://opensearch.org/docs/latest/dashboards/discover/multi-data-sources/#creating-data-visualizations-for-a-dashboard)

Follow these steps to learn how to create data visualizations for a dashboard:

1.  In the Dashboards console, choose  **Visualize**  >  **Create visualization**.
2.  Select the visualization type. For this tutorial, choose  **Line**.
3.  Select a source. For this tutorial, choose the index pattern  `opensearch_dashboards_sample_data_ecommerce`.
4.  Under  **Buckets**, choose  **Add**  >  **X-axis**.
5.  In the  **Aggregation**  field, choose  **Date Histogram**  and then choose  **Update**.
6.  Optional: Choose  **Save**  and add the file name. This tutorial uses preconfigured data visualizations, so you can’t save the file for this tutorial.

## Connecting visualizations in a single dashboard[](https://opensearch.org/docs/latest/dashboards/discover/multi-data-sources/#connecting-visualizations-in-a-single-dashboard)

Follow these steps to connect your visualizations in a single dashboard:

1.  In the Dashboards console, choose  **Dashboard**  >  **Create dashboard**.

2.  Choose  **Add an existing**  and then select the data you want to add.

3.  Choose  **Save**  and add the dashboard name in the  **Title field**. This tutorial uses preconfigured dashboards, so you won’t be able to save your dashboard.

4.  Click on the white space left of  **Add panels**  to view the visualizations in a single dashboard.

Your dashboard might look like the one in the following image.

![Example dashboard using data visualizations from many data sources]({{site.baseurl}}/images/exploring-data/multi-data-sources-12.jpg)

You have now explored the data sources experimental feature. To provide feedback on how this feature can be improved ahead of its release for production use, comment in the  [OpenSearch forum](https://forum.opensearch.org/).

## Understanding feature limitations[](https://opensearch.org/docs/latest/dashboards/discover/multi-data-sources/#understanding-feature-limitations)

The following limitations apply to this experimental feature:

-   The multiple data sources feature is supported for index-pattern-based visualizations only.
-   The visualization types Time Series Visual Builder (TSVB), Vega and Vega-Lite, and timeline are not supported.
-   External plugins, such as Gantt chart, and non-visualization plugins, such as the developer console, are not supported.

## Related topics[](https://opensearch.org/docs/latest/dashboards/discover/multi-data-sources/#related-topics)

-   [OpenSearch Forum](https://forum.opensearch.org/)

