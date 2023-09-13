---
layout: default
title: Force merge
parent: Index management in Dashboards
grand_parent: Opensearch Dashboard
nav_order: 26
---

# Force merge

INTRODUCED 2.6

OpenSearch Dashboards allows you to perform a  [force merge](https://opensearch.org/docs/latest/im-plugin/ism/error-prevention/index#force_merge)  operation on two or more indexes with  **Index Management**.

## Force merging indexes[](https://opensearch.org/docs/latest/dashboards/im-dashboards/forcemerge/#force-merging-indexes)

To perform a force merge operation on two or more indexes, perform the following steps:

1.  Under  **Index Management**, choose  **Indices**.
    
2.  Select the indexes you want to force merge.
    
3.  Choose  **Actions**, and then choose  **Force merge**, as shown in the following image.
    
    ![Force Merge]({{site.baseurl}}/images/index-management-in-dashboards/forcemerge1.png)
    
4.  Under  **Configure source index**, specify the indexes you want to force merge.
    
5.  Optionally, under  **Advanced settings**  you can to choose to  **Flush indices**  or  **Only expunge delete**  and then specify the  **Max number of segments**  to merge to as shown in the following image.
    
    ![Force Merge]({{site.baseurl}}/images/index-management-in-dashboards/forcemerge2.png)
    

## Force merging data streams[](https://opensearch.org/docs/latest/dashboards/im-dashboards/forcemerge/#force-merging-data-streams)

To perform a force merge operation on two or more indexes, perform the following steps:

1.  Under  **Index Management**, choose  **Data streams**.
    
2.  Select the data streams you want to force merge.
    
3.  Choose  **Actions**, and then choose  **Force merge**.
    
4.  Under  **Configure source index**, specify the data streams you want to force merge.
    
5.  Optionally, under  **Advanced settings**  you can to choose to  **Flush indices**  or  **Only expunge delete**  and then specify the  **Max number of segments**  to merge to as shown in the following image.
    
    ![Force Merge]({{site.baseurl}}/images/index-management-in-dashboards/forcemerge2.png)