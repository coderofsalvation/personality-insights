---

copyright:
  years: 2015, 2019
lastupdated: "2019-02-01"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}
{:important: .important}
{:note: .note}
{:deprecated: .deprecated}
{:pre: .pre}
{:codeblock: .codeblock}
{:screen: .screen}
{:javascript: .ph data-hd-programlang='javascript'}
{:java: .ph data-hd-programlang='java'}
{:python: .ph data-hd-programlang='python'}
{:swift: .ph data-hd-programlang='swift'}

# Overview for developers
{: #overviewDevelopers}

You can use the {{site.data.keyword.personalityinsightsshort}} service via an HTTP Representational State Transfer (REST) API. Several Software Development Kits (SDKs) are also available to simplify application development in various languages.
{: shortdesc}

## Programming with the service
{: #programming}

To produce a personality profile, you send text to the service's HTTP `POST /v3/profile` method. You can submit plain text, HTML, or JSON content. The service can return its analysis in JSON or CSV format

For each personality characteristic, the service reports a *percentile*. The percentile is a normalized score that describes the extent to which the author's writing exhibits a characteristic within a sample population. If requested, the service also returns a *raw score*, which is an absolute value that is not normalized for a sample population. If the input is timestamped, the service provides a summary of the author's writing habits by day of week and time of day. And if requested, the service also returns a likelihood score for each of its available consumption preferences.

For more information about using the service, see

-   [Requesting a profile](/docs/services/personality-insights/input.html)
-   [Understanding a JSON profile](/docs/services/personality-insights/output.html)
-   [Understanding a CSV profile](/docs/services/personality-insights/output-csv.html)

### Visualizing a profile
{: #visualize}

The service provides a collection of JavaScript files that enable graphic visualization of a profile. The scripts facilitate use of the service with caching and content distribution networks. They rely on JavaScript, jQuery, HTML, and SVG with the Data-Driven Documents (`D3.js`) library to depict the results. For more information about `D3.js`, see [d3js.org ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://d3js.org/){: new_window}.

### CORS support
{: #CORS}

The service supports Cross-Origin Resource Sharing (CORS). CORS allows browser-based clients to make asynchronous requests directly to the service from front-end scripts. CORS circumvents the same-origin security policy, which otherwise prevents such requests.

By using CORS, web pages can request resources from a foreign domain, one that is outside the domain from which the request originated. For more information, see [enable-cors.org ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://enable-cors.org/){: new_window}.

## Using Software Development Kits
{: #sdks}

SDKs are available for the {{site.data.keyword.personalityinsightsshort}} service to simplify application development. {{site.data.keyword.ibmwatson}} SDKs are available for many popular programming languages and platforms.

-   For a complete list of SDKs and links to the SDKs on GitHub, see [Using SDKs](/docs/services/watson/getting-started-sdks.html).
-   For detailed information about all methods of the Node, Java, Python, Ruby, and Go SDKs for the {{site.data.keyword.personalityinsightsshort}} service, see the [API reference ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://{DomainName}/apidocs/personality-insights){: new_window}.

## Learning more about application development
{: #learn-overview}

For more information about working with {{site.data.keyword.watson}} services and {{site.data.keyword.cloud}}, see the following sections:

-   For an introduction to working with {{site.data.keyword.watson}} services and {{site.data.keyword.cloud_notm}}, see [Getting started with {{site.data.keyword.watson}} and {{site.data.keyword.cloud_notm}}](/docs/services/watson/index.html).
-   All new service instances use {{site.data.keyword.cloud_notm}} Identity and Access Management (IAM) for authentication. Older service instances might continue to use the `{username}` and `{password}` from their existing Cloud Foundry service credentials for authentication. For more information about authenticating to the service, see the [30 October 2018 service update](/docs/services/personality-insights/release-notes.html#October2018) in the release notes.
-   Request logging is disabled for the {{site.data.keyword.personalityinsightsshort}} service. The service does not log or retain data from requests and responses, regardless of whether the `X-Watson-Learning-Opt-Out` request header is set.
