---
layout: default
title: Index management in Dashboards
nav_order: 24
parent: Opensearch Dashboard
# grand_parent: Log Analytics
has_children: true
has_toc: false
redirect_from: /analytics/opensearch-dashboard/index-management-in-dashboards/
permalink: /analytics/opensearch-dashboard/index-management-in-dashboards/index.html
--- 

# Index management in Dashboards

INTRODUCED 2.5

Previously, users relied on REST APIs or YAML configurations for basic administrative operations and interventions. This release takes the first step toward a unified administration panel in OpenSearch Dashboards with the launch of several index management UI enhancements. The new interface provides a more user-friendly way to run common indexing and data stream operations. Now you can perform create, read, update, and delete (CRUD) and mapping operations for indexes, index templates, and aliases through the UI. Additionally, you can open, close, reindex, shrink, and split indexes. The UI runs index status and data validation before submitting requests and lets you compare changes with previously saved settings before making updates.

![Index management demo gif]({{site.baseurl}}/images/index-management-in-dashboards/admin-UI-preview.gif)

[](https://opensearch.org/docs/latest/dashboards/im-dashboards/index/#top)

----------

## Related articles[](https://opensearch.org/docs/latest/dashboards/im-dashboards/index/#related-articles)

-   [Indexes](https://opensearch.org/docs/latest/dashboards/im-dashboards/index-management/)
-   [Data streams](https://opensearch.org/docs/latest/dashboards/im-dashboards/datastream/)
-   [Force merge](https://opensearch.org/docs/latest/dashboards/im-dashboards/forcemerge/)
-   [Rollover](https://opensearch.org/docs/latest/dashboards/im-dashboards/rollover/)