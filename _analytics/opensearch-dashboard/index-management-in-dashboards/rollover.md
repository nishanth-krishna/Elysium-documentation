---
layout: default
title: Rollover
parent: Index management in Dashboards
grand_parent: Opensearch Dashboard
nav_order: 28
redirect_from: /analytics/opensearch-dashboard/index-management-in-dashboards/rollover/
permalink: /analytics/opensearch-dashboard/index-management-in-dashboards/rollover/index.html
---

# Rollover

INTRODUCED 2.6

OpenSearch Dashboards allows you to perform an  [index rollover](https://opensearch.org/docs/latest/im-plugin/ism/error-prevention/index/#rollover)  operation with  **Index Management**.

## Data streams[](https://opensearch.org/docs/latest/dashboards/im-dashboards/rollover/#data-streams)

To perform a rollover operation on a data stream, perform the following steps:

1.  Under  **Index Management**, choose  **Data streams**.
    
2.  Choose  **Actions**, and then choose  **Roll over**, as shown in the following image.
    
    ![Roll over]({{site.baseurl}}/images/index-management-in-dashboards/rollover1.png)
    
3.  Under  **Configure source**, select the source data stream on which you want to perform the rollover operation.
    
4.  Choose  **Roll over**, as shown in the following image.
    
    ![Roll over]({{site.baseurl}}/images/index-management-in-dashboards/rollover3.png)
    

## Aliases[](https://opensearch.org/docs/latest/dashboards/im-dashboards/rollover/#aliases)

To perform a rollover operation on an alias, perform the following steps:

1.  Under  **Index Management**, choose  **Aliases**.
    
2.  Choose  **Actions**, and then choose  **Roll over**, as shown in the following image.
    
    ![Roll over]({{site.baseurl}}/images/index-management-in-dashboards/rollover2.png)
    
3.  Under  **Configure source**, select the source alias on which you want to perform the rollover operation.
    
4.  If the alias does not contain a write index, you are prompted to assign a write index, as shown in the following image.
    
    ![Roll over]({{site.baseurl}}/images/index-management-in-dashboards/rollover4.png)
    
5.  Under  **Configure a new rollover index**  and on the  **Define index**  pane, specify an index name and an optional index alias.
    
6.  Under  **Index settings**, specify the number of primary shards, the number of replicas, and the refresh interval, as shown in the following image.
    
    ![Roll over]({{site.baseurl}}/images/index-management-in-dashboards/rollover5.png)
    
7.  Choose  **Roll over**.