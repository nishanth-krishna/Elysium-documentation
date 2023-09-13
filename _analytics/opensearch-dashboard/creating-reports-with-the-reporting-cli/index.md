---
layout: default
title: Creating reports with the Reporting CLI
nav_order: 12
parent: Opensearch Dashboard
# grand_parent: Log Analytics
has_children: true
has_toc: false
redirect_from:
  - /documentation/log-analytics/opensearch-dashboard/creating-reports-with-the-reporting-cli
--- 

# Creating reports with the Reporting CLI

You can programmatically create dashboard reports in PDF or PNG format with the Reporting CLI without using OpenSearch Dashboards or the Reporting plugin. This allows you to create reports automatically within your email workflows.

If you want to download a CSV file, you need to have the Reporting plugin installed.

For any dashboard view, you can request a report in PNG or PDF format to be sent to an email address. This can be useful for sending reports to multiple email recipients with an email alias. The only dashboard application that supports creating a CSV report is  **Discover**.

With the Reporting CLI, you can specify options for your report in the command line. The report is sent to an email address as a PDF attachment by default. You can also request a PNG image or a CSV file with the  `--formats`  argument.

You can download the report to the directory in which you are running the Reporting CLI, or you can email the report by specifying Amazon Simple Email Service (Amazon SES) or SMTP for the email transport option.

You can connect to OpenSearch with any of the following authentication types:

-   **Basic**  – Basic HTTP authentication. Use  `-a basic`.
-   **Cognito**  – Authentication through Amazon Cognito. Use  `-a cognito`.
-   **SAML**  – Authentication between an identity provider and a service provider. Use  `-a saml`. Okta provides the SAML third-party authentication.
-   **No auth**  – No authentication. Use  `-a none`. Authentication defaults to No auth if the  `-a`  flag is not specified.

To learn more about Amazon Cognito, see  [What is Amazon Cognito?](https://docs.aws.amazon.com/cognito/latest/developerguide/what-is-amazon-cognito.html).

[](https://opensearch.org/docs/latest/dashboards/reporting-cli/rep-cli-index/#top)

----------

## Related articles[](https://opensearch.org/docs/latest/dashboards/reporting-cli/rep-cli-index/#related-articles)

-   [Downloading and installing the Reporting CLI tool](https://opensearch.org/docs/latest/dashboards/reporting-cli/rep-cli-install/)
-   [Creating and requesting a visualization report](https://opensearch.org/docs/latest/dashboards/reporting-cli/rep-cli-create/)
-   [Scheduling reports with the cron utility](https://opensearch.org/docs/latest/dashboards/reporting-cli/rep-cli-cron/)
-   [Scheduling reports with AWS Lambda](https://opensearch.org/docs/latest/dashboards/reporting-cli/rep-cli-lambda/)
-   [Reporting CLI options](https://opensearch.org/docs/latest/dashboards/reporting-cli/rep-cli-options/)
-   [Using environment variables with the Reporting CLI](https://opensearch.org/docs/latest/dashboards/reporting-cli/rep-cli-env-var/)