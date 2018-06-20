---

copyright:
  years: 2015, 2018
lastupdated: "2018-06-20"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}
{:pre: .pre}
{:codeblock: .codeblock}
{:screen: .screen}
{:javascript: .ph data-hd-programlang='javascript'}
{:java: .ph data-hd-programlang='java'}
{:python: .ph data-hd-programlang='python'}
{:swift: .ph data-hd-programlang='swift'}

# Overview for developers
{: #overviewDevelopers}

You can use the {{site.data.keyword.personalityinsightsshort}} service via an HTTP Representational State Transfer (REST) API. Several Software Development Kits (SDKs) are also available to simplify application development in various languages and environments.
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

The {{site.data.keyword.personalityinsightsshort}} service supports a number of SDKs for simplified application development. The SDKs are available for many popular programming languages and platforms, including Node.js, Java, and Python. For a complete list of SDKs and information about using them, see [{{site.data.keyword.watson}} SDKs](/docs/services/watson/getting-started-sdks.html). All SDKs are available from the [watson-developer-cloud namespace ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://github.com/watson-developer-cloud){: new_window} on GitHub.

## Learning more about application development
{: #learn}

For more information about working with {{site.data.keyword.watson}} Developer Cloud services and {{site.data.keyword.Bluemix_notm}}, see the following sections:

-   For an introduction to working with {{site.data.keyword.watson}} services and {{site.data.keyword.Bluemix_notm}}, see [Getting started with {{site.data.keyword.watson}} and {{site.data.keyword.Bluemix_notm}}](/docs/services/watson/index.html).
-   For a language-independent introduction to developing {{site.data.keyword.watson}} services applications in {{site.data.keyword.Bluemix_notm}}, see [{{site.data.keyword.Bluemix_notm}} development approaches](/docs/services/watson/getting-started-bluemix.html).
-   Some service instances use {{site.data.keyword.Bluemix}} Identity and Access Management (IAM) for authentication. Other service instances continue to use service credentials for authentication.
    -   For more information about where and how the service uses IAM authentication, see the [Release notes](/docs/services/personality-insights/release-notes.html).
    -   For more information about using IAM tokens with {{site.data.keyword.watson}} services, see [Authenticating with IAM tokens](/docs/services/watson/getting-started-iam.html).
    -   For more information about using service credentials with {{site.data.keyword.watson}} services, see [Service credentials for {{site.data.keyword.watson}} services](/docs/services/watson/getting-started-credentials.html).
-   Request logging is disabled for the {{site.data.keyword.personalityinsightsshort}} service. The service does not log or retain data from requests and responses, regardless of whether the `X-Watson-Learning-Opt-Out` request header is set.

<!--
The {{site.data.keyword.personalityinsightsshort}} service supports two typical programming models. With *direct interaction*, the client communicates with the service directly. With *relaying via a proxy*, the client and service exchange all data (requests and results) through a proxy application that resides in {{site.data.keyword.Bluemix_short}}.

-   For information about the two programming models available for developing {{site.data.keyword.watson}} applications, see [Programming models for {{site.data.keyword.watson}} services](/docs/services/watson/getting-started-develop.html):
    -   With relaying via a proxy, the client relies on a proxy server that resides in {{site.data.keyword.Bluemix_notm}} to communicate with the service. The client passes all requests through the proxy application. Relaying requests via a proxy relies only on service credentials to authenticate with the service; see [Service credentials for {{site.data.keyword.watson}} services](/docs/services/watson/getting-started-credentials.html).
    -   With direct interaction, the client uses the proxy application in {{site.data.keyword.Bluemix_notm}} only to obtain an authentication token for the service. It then communicates directly with the service. Direct interaction uses service credentials only to obtain a token; see [Tokens for authentication](/docs/services/watson/getting-started-tokens.html).
-->
