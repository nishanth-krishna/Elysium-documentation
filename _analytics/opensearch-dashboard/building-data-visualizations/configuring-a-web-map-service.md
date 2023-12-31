---
layout: default
title: Configuring a Web Map Service (WMS)
parent: Building data visualizations
grand_parent: Opensearch Dashboard
nav_order: 14
redirect_from: /analytics/opensearch-dashboard/building-data-visualizations/conf-wms/
permalink: /analytics/opensearch-dashboard/building-data-visualizations/conf-wms/index.html
---

# Configuring a Web Map Service (WMS)

The Open Geospatial Consortium (OGC) Web Map Service (WMS) specification is an international specification for requesting dynamic maps on the web. OpenSearch Dashboards includes default map tiles. For specialized maps, you can configure a WMS on OpenSearch Dashboards following these steps:

1.  Log in to OpenSearch Dashboards at  `https://<host>:<port>`. For example, you can connect to OpenSearch Dashboards by connecting to  [https://localhost:5601](https://localhost:5601/). The default username and password are  `admin`.
2.  Choose  **Management**  >  **Advanced Settings**.
3.  Locate  `visualization:tileMap:WMSdefaults`.
4.  Change  `enabled`  to  `true`  and add the URL of a valid WMS server, as shown in the following example:
    
    ```
    {
      "enabled": true,
      "url": "<wms-map-server-url>",
      "options": {
        "format": "image/png",
        "transparent": true
      }
    }
    
    ```
    

Web map services may have licensing fees or restrictions, and you are responsible for complying with any such fees or restrictions.