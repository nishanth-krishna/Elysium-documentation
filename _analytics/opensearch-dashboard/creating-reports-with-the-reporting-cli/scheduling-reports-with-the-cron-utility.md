---
layout: default
title: Scheduling reports with the cron utility
parent: Creating reports with the Reporting CLI
grand_parent: Opensearch Dashboard
nav_order: 20
---

# Scheduling reports with the cron utility

You can use the cron command-line utility to initiate a report request with the Reporting CLI that runs periodically at any date or time interval. Follow the cron expression syntax to specify the date and time that precedes the command that you want to initiate.

To learn about the cron expression syntax, see  [Cron expression reference](https://opensearch.org/docs/latest/observing-your-data/alerting/cron/). To get help with cron, open the man page by running the following command:

```
man cron

```

### Prerequisites[](https://opensearch.org/docs/latest/dashboards/reporting-cli/rep-cli-cron/#prerequisites)

-   You need a machine with cron installed.
-   You need to install the Reporting CLI. See  [Downloading and installing the Reporting CLI tool](https://opensearch.org/docs/latest/dashboards/reporting-cli/rep-cli-install/)

## Specifying the report details[](https://opensearch.org/docs/latest/dashboards/reporting-cli/rep-cli-cron/#specifying-the-report-details)

Open the crontab editor by running the following command:

```
crontab -e

```

In the crontab editor, enter the report request. The following example shows a cron report that runs every day at 8:00 AM:

```
0 8 * * * opensearch-reporting-cli -u https://playground.opensearch.org/app/dashboards#/view/084aed50-6f48-11ed-a3d5-1ddbf0afc873 -e ses -s <
```
