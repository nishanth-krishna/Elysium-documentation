---
layout: default
title: Creating and requesting a visualization report
parent: Creating reports with the Reporting CLI
grand_parent: Opensearch Dashboard
nav_order: 19
---

# Creating and requesting a visualization report

First, you need to get the URL for the visualization that you want to download as an image file or PDF.

To generate a visualization report, you need to specify the Dashboards URL.

Open the visualization for which you want to generate a report, and select  **Share > Permalinks > Generate link as Shapshot > Short URL > Copy link**, as shown in the following image.

![Copy link]({{site.baseurl}}/images/creating-reports-with-the-reporting-cli/dash-url.png)

You will need to add the URL with the  `-u`  argument when you request the report in the CLI.

#### EXAMPLE: REQUESTING A PNG FILE[](https://opensearch.org/docs/latest/dashboards/reporting-cli/rep-cli-create/#example-requesting-a-png-file)

The following command requests a report in PNG format with basic authentication and sends the report to an email address using Amazon SES:

```
opensearch-reporting-cli -u https://localhost:5601/app/dashboards#/view/7adfa750-4c81-11e8-b3d7-01146121b73d -a basic -c admin:Test@1234 -e ses -s <email address>  -r <email address> -f png

```

#### EXAMPLE: REQUESTING A PDF FILE[](https://opensearch.org/docs/latest/dashboards/reporting-cli/rep-cli-create/#example-requesting-a-pdf-file)

The following command requests a PDF file and specifies the recipient’s email address:

```
opensearch-reporting-cli -u https://localhost:5601/app/dashboards#/view/7adfa750-4c81-11e8-b3d7-01146121b73d -a basic -c admin:Test@1234 -e ses -s <email address> -r <email address> -f pdf

```

Upon success, the file will be sent to the specified email address. The following image shows an example PDF report.

![PDF example]({{site.baseurl}}/images/creating-reports-with-the-reporting-cli/cli-pdf-report.png)

#### EXAMPLE: REQUESTING A CSV FILE[](https://opensearch.org/docs/latest/dashboards/reporting-cli/rep-cli-create/#example-requesting-a-csv-file)

The following command generates a report that contains all table content in CSV format and sends the report to an email address using Amazon SES transport:

```
opensearch-reporting-cli -u https://localhost:5601/app/dashboards#/view/7adfa750-4c81-11e8-b3d7-01146121b73d -f csv -a basic -c admin:Test@1234 -e ses -s <email address> -r <email address>

```

Upon success, the email will be sent to the specified email address with the CSV file attached.
