---
layout: default
title: Data streams
parent: Index management in Dashboards
grand_parent: Opensearch Dashboard
nav_order: 26
redirect_from: /analytics/opensearch-dashboard/index-management-in-dashboards/data-streams/
permalink: /analytics/opensearch-dashboard/index-management-in-dashboards/data-streams/index.html
---

# Data streams

INTRODUCED 2.6

In OpenSearch Dashboards, the  **Index Management**  application allows you to view and manage  [data streams](https://opensearch.org/docs/latest/im-plugin/data-streams/)  as shown in the following image.

![Data Streams]({{site.baseurl}}/images/index-management-in-dashboards/datastreams1.png)

## Viewing a data stream[](https://opensearch.org/docs/latest/dashboards/im-dashboards/datastream/#viewing-a-data-stream)

To view a data stream and its health status, choose  **Data streams**  under  **Index management**  as shown in the following image.

![Data Streams]({{site.baseurl}}/images/index-management-in-dashboards/datastreams5.png)

The following are the three data stream health statuses:

-   Green: All primary and replica shards are assigned.
-   Yellow: At least one replica shard is not assigned.
-   Red: At least one primary shard is not assigned.

## Creating a data stream[](https://opensearch.org/docs/latest/dashboards/im-dashboards/datastream/#creating-a-data-stream)

To create a data stream, perform the following steps:

1.  Under  **Index Management**, choose  **Data streams**.
    
2.  Choose  **Create data stream**.
    
3.  Enter a name for the data stream under  **Data stream name**.
    
4.  Ensure that you have a matching index template. This will be populated under  **Matching index template**, as shown in the following image.
    
    ![Data Streams]({{site.baseurl}}/images/index-management-in-dashboards/datastreams3.png)
    
5.  The  **Inherited settings from template**  and  **Index alias**  sections are read-only, and display the backing indexes that are contained in the data stream.
    
6.  The number of primary shards, number of replicas, and the refresh interval are inherited from the template, as shown in the following image.
    
    ![Data Streams]({{site.baseurl}}/images/index-management-in-dashboards/datastreams4.png)
    
7.  Choose  **Create data stream**.
    

## Deleting a data stream[](https://opensearch.org/docs/latest/dashboards/im-dashboards/datastream/#deleting-a-data-stream)

To delete a data stream, perform the following steps:

1.  Under  **Index Management**, choose  **Data streams**.
    
2.  Select the data stream that you want to delete.
    
3.  Choose  **Actions**, and then choose  **Delete**.
    

## Rolling over a data stream[](https://opensearch.org/docs/latest/dashboards/im-dashboards/datastream/#rolling-over-a-data-stream)

To perform a rollover operation on a data stream, perform the following steps:

1.  Under  **Index Management**, choose  **Data streams**.
    
2.  Choose  **Actions**, and then choose  **Roll over**, as shown in the following image.
    
    ![Rollover]({{site.baseurl}}/images/index-management-in-dashboards/rollover1.png)
    
3.  Under  **Configure source**, select the source data stream on which you want to perform the rollover operation.
    
4.  Choose  **Roll over**, as shown in the following image.
    
    ![Rollover]({{site.baseurl}}/images/index-management-in-dashboards/rollover3.png)
    

## Force merging data streams[](https://opensearch.org/docs/latest/dashboards/im-dashboards/datastream/#force-merging-data-streams)

To perform a force merge operation on two or more indexes, perform the following steps:

1.  Under  **Index Management**, choose  **Data streams**.
    
2.  Select the data streams on which you want to perform the force merge operation.
    
3.  Choose  **Actions**, and then choose  **Force merge**.
    
4.  Under  **Configure source index**, specify the data streams you want to force merge.
    
5.  Optionally, under  **Advanced settings**  you can to choose to  **Flush indices**  or  **Only expunge delete**  and then specify the  **Max number of segments**  to merge to as shown in the following image.
    
    ![Force Merge]({{site.baseurl}}/images/index-management-in-dashboards/forcemerge2.png)