---
layout: default
title: Downloading and installing the Reporting CLI tool
parent: Creating reports with the Reporting CLI
grand_parent: Opensearch Dashboard
nav_order: 19
redirect_from: /analytics/opensearch-dashboard/creating-reports-with-the-reporting-cli/download-cli/
permalink: /analytics/opensearch-dashboard/creating-reports-with-the-reporting-cli/download-cli/index.html
---

# Downloading and installing the Reporting CLI tool

You can download and install the Reporting CLI tool from either the npm software registry or the OpenSearch.org  [Artifacts](https://opensearch.org/artifacts)  hub. Refer to the following sections for instructions.

To learn more about the npm software registry, see the  [npm](https://docs.npmjs.com/about-npm)  documentation.

## Downloading and installing the Reporting CLI from npm[](https://opensearch.org/docs/latest/dashboards/reporting-cli/rep-cli-install/#downloading-and-installing-the-reporting-cli-from-npm)

To download and install the Reporting CLI from npm, run the following command to initiate installation:

```
npm i @opensearch-project/reporting-cli

```

## Downloading and installing the Reporting CLI from OpenSearch.org[](https://opensearch.org/docs/latest/dashboards/reporting-cli/rep-cli-install/#downloading-and-installing-the-reporting-cli-from-opensearchorg)

You can download the  `opensearch-reporting-cli`  tool from the OpenSearch.org  [Artifacts](https://artifacts.opensearch.org/reporting-cli/opensearch-reporting-cli-1.0.0.tgz)  hub.

Next, run the following command to install the .tar archive:

```
npm install -g opensearch-reporting-cli-1.0.0.tgz

```

To provide better security for artifacts, we recommend that you verify signatures by downloading the  [Reporting CLI signature file](https://artifacts.opensearch.org/reporting-cli/opensearch-reporting-cli-1.0.0.tgz.sig).

To learn more about verifying signatures, see  [How to verify signatures for downloadable artifacts](https://opensearch.org/verify-signatures.html).