---
layout: default
title: Running queries in the console
parent: Opensearch Dashboard
# grand_parent: Log Analytics
nav_order: 32
redirect_from: /analytics/opensearch-dasboard/run-queries/
permalink: /analytics/opensearch-dasboard/run-queries/index.html
---

# Running queries in the console

You can use the OpenSearch Dev Tools Console to send queries to OpenSearch.

## Navigating to the console[](https://opensearch.org/docs/latest/dashboards/run-queries/#navigating-to-the-console)

To open the console, select  **Dev Tools**  on the main OpenSearch Dashboards page:

![Dev Tools Console from main page]({{site.baseurl}}/images/running-queries-in-the-console/dev-tools-main.png)

You can open the console from any other page by navigating to the main menu and selecting  **Management**  >  **Dev Tools**.

![Dev Tools Console from all pages]({{site.baseurl}}/images/running-queries-in-the-console/dev-tools-left.png)

## Writing queries[](https://opensearch.org/docs/latest/dashboards/run-queries/#writing-queries)

Write your queries in the editor pane on the left side of the console:

![Request pane]({{site.baseurl}}/images/running-queries-in-the-console/dev-tools-request.png)

You can collapse and expand parts of your query by selecting the small triangles next to the line numbers.

To learn more about writing queries in OpenSearch domain-specific language (DSL), see  [Query DSL](https://opensearch.org/docs/latest/opensearch/query-dsl).

### Comments[](https://opensearch.org/docs/latest/dashboards/run-queries/#comments)

Use  `#`  at the beginning of a line to write single-line comments.

### Autocomplete[](https://opensearch.org/docs/latest/dashboards/run-queries/#autocomplete)

OpenSearch provides autocomplete suggestions for fields, indexes and their aliases, and templates. To configure autocomplete preferences, update them in  [Console Settings](https://opensearch.org/docs/latest/dashboards/run-queries/#updating-the-console-settings).

## Sending the request[](https://opensearch.org/docs/latest/dashboards/run-queries/#sending-the-request)

To send a query to OpenSearch, select the query by placing the cursor anywhere in the query text. Then choose the triangle on the top right of the request or press  `Ctrl/Cmd+Enter`:

![Send request]({{site.baseurl}}/images/running-queries-in-the-console/dev-tools-send.png)

OpenSearch displays the response in the response pane on the right side of the console:

![Response pane]({{site.baseurl}}/images/running-queries-in-the-console/dev-tools-response.png)

## Working in the cURL and console formats[](https://opensearch.org/docs/latest/dashboards/run-queries/#working-in-the-curl-and-console-formats)

The console uses an easier syntax to format REST requests than the  `curl`  command.

For example, the following  `curl`  command runs a search query:

```
curl -XGET http://localhost:9200/shakespeare/_search?pretty -H 'Content-Type: application/json' -d'
{
  "query": {
    "match": {
      "text_entry": "To be, or not to be"
    }
  }
}'

```

The same query has a simpler syntax in the console format:

```
GET shakespeare/_search
{
  "query": {
    "match": {
      "text_entry": "To be, or not to be"
    }
  }
}

```

If you paste a  `curl`  command directly into the console, the command is automatically converted into the format the console uses.

To import a query in cURL format, select the query, then select the wrench icon and choose  **Copy as cURL**:

![Console tools]({{site.baseurl}}/images/running-queries-in-the-console/dev-tools-tools.png)

## Viewing documentation[](https://opensearch.org/docs/latest/dashboards/run-queries/#viewing-documentation)

To view the OpenSearch documentation, select the wrench icon, and choose  **Open documentation**.

## Auto indenting[](https://opensearch.org/docs/latest/dashboards/run-queries/#auto-indenting)

To use auto indent, select the queries that you want to format, select the wrench icon, and choose  **Auto indent**.

Auto indenting a collapsed query expands it.

Auto indenting a well-formatted query puts the request body on a single line. This is useful for working with  [bulk APIs](https://opensearch.org/docs/latest/api-reference/document-apis/bulk/).

## Viewing your request history[](https://opensearch.org/docs/latest/dashboards/run-queries/#viewing-your-request-history)

You can view up to the 500 most recent requests that OpenSearch ran successfully. To view request history, select  **History**  from the top menu. If you select the request you want to view from the left pane, the query is shown in the right pane.

To copy the query into the editor pane, select the query text and then select  **Apply**.

To clear the history, select  **Clear**.

## Updating the console settings[](https://opensearch.org/docs/latest/dashboards/run-queries/#updating-the-console-settings)

To update your preferences, select  **Settings**  from the top menu:

![Settings]({{site.baseurl}}/images/running-queries-in-the-console/dev-tools-settings.png)

## Using keyboard shortcuts[](https://opensearch.org/docs/latest/dashboards/run-queries/#using-keyboard-shortcuts)

To view all available keyboard shortcuts, select  **Help**  from the top menu.