---
layout: default
title: Creating reports with the Dashboards interface
parent: Opensearch Dashboard
# grand_parent: Log Analytics
nav_order: 17
redirect_from: /analytics/opensearch-dasboard/create-reports-dashboard/
permalink: /analytics/opensearch-dasboard/create-reports-dashboard/index.html
---

# Creating reports with the Dashboards interface

You can use OpenSearch Dashboards to create PNG, PDF, and CSV reports. To create reports, you must have the correct permissions. For a summary of the predefined roles and the permissions they grant, see the  [security plugin](https://opensearch.org/docs/latest/security/access-control/users-roles#predefined-roles).

CSV reports have a non-configurable 10,000 row limit. They have no explicit size limit (for example, MB), but extremely large documents could cause report generation to fail with an out of memory error from the V8 JavaScript engine.

## Generating reports with the interface[](https://opensearch.org/docs/latest/dashboards/reporting/#generating-reports-with-the-interface)

To generate a report from the interface:

1.  From the navigation panel, choose  **Reporting**.
2.  For dashboards, visualizations, or notebooks, choose  **Download PDF**  or  **Download PNG**. If you’re creating a report from the Discover page, choose  **Generate CSV**.
    
    REPORTS GENERATE ASYNCHRONOUSLY IN THE BACKGROUND AND MIGHT TAKE A FEW MINUTES, DEPENDING ON THE SIZE OF THE REPORT. A NOTIFICATION APPEARS WHEN YOUR REPORT IS READY TO DOWNLOAD.
    
3.  To create a schedule-based report, choose  **Create report definition**. Then proceed to  [Create reports using a definition](https://opensearch.org/docs/latest/dashboards/reporting/#creating-reports-using-a-definition). This option pre-fills many of the fields for you based on the visualization, dashboard, or data you were viewing.

## Creating reports using a definition[](https://opensearch.org/docs/latest/dashboards/reporting/#creating-reports-using-a-definition)

Definitions let you generate reports on a periodic schedule.

1.  From the navigation panel, choose  **Reporting**.
2.  Choose  **Create**.
3.  Under  **Report settings**, enter a name and optional description for your report.
4.  Choose the  **Report source**  (i.e. the page from which the report is generated). You can generate reports from the  **Dashboard**,  **Visualize**,  **Discover**  (saved search), or  **Notebooks**  pages.
5.  Select your dashboard, visualization, saved search, or notebook. Then choose a time range for the report.
6.  Choose an appropriate file format for the report.
7.  (Optional) Add a header or footer to the report. Headers and footers are only available for dashboard, visualization, and notebook reports.
8.  Under  **Report trigger**, choose either  **On demand**  or  **Schedule**.
    
    For scheduled reports, select either  **Recurring**  or  **Cron based**. You can receive reports daily or at some other time interval, and Cron expressions give you more flexibility. See  [Cron expression reference](https://opensearch.org/docs/latest/monitoring-plugins/alerting/cron/)  for more information.
    
9.  Choose  **Create**.

## Troubleshooting[](https://opensearch.org/docs/latest/dashboards/reporting/#troubleshooting)

### Chromium fails to launch with OpenSearch Dashboards[](https://opensearch.org/docs/latest/dashboards/reporting/#chromium-fails-to-launch-with-opensearch-dashboards)

While creating a report for dashboards or visualizations, you might see a the following error:

![OpenSearch Dashboards reporting pop-up error message]({{site.baseurl}}/images/creating-reports-with-the-dashboards-interface/reporting-error.png)

This problem can occur for two reasons:

-   You don’t have the correct version of  `headless-chrome`  to match the operating system on which OpenSearch Dashboards is running. Download the  [correct version](https://github.com/opensearch-project/reporting/releases/tag/chromium-1.12.0.0).
    
-   You’re missing additional dependencies. Install the required dependencies for your operating system from the  [additional libraries](https://github.com/opensearch-project/dashboards-reports/blob/main/dashboards-reports/rendering-engine/headless-chrome/README.md#additional-libaries)  section.
    

### Characters not loading in reports[](https://opensearch.org/docs/latest/dashboards/reporting/#characters-not-loading-in-reports)

You might encounter an issue where UTF-8 encoded characters look fine in your browser, but they don’t load in your generated reports because you’re missing the required font dependencies. Install the  [font dependencies](https://github.com/opensearch-project/dashboards-reports#missing-font-dependencies), and then generate your reports again.