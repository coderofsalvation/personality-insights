---

copyright:
  years: 2015, 2017
lastupdated: "2017-08-08"

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

You can access the capabilities of the {{site.data.keyword.personalityinsightsshort}} service via an HTTP Representational State Transfer (REST) API. Several Software Development Kits (SDKs) are also available to simplify application development in various languages and environments. The following sections provide an overview of application development with the service.
{: shortdesc}

## Programming with the service
{: #programming}

To produce a personality portrait, you send text written by the individual of interest to the service's HTTP `POST profile` method. The service returns output that provides insight into the personality characteristics of the author in terms of personality models and optional consumption preferences. You can request that the service return JSON or CSV output.

The service reports a percentile and an optional raw score for each characteristic that it analyzes. If the input text contains timestamps, the output includes temporal information about the percentage of the input that was created on each day of the week and hour of the day. Optionally, the service can also report a score for each consumption preference that indicates the author's preferences for different products, services, and activities.

For more information about using the service's `profile` method, see [Requesting a profile](/docs/services/personality-insights/input.html) and [Understanding a profile](/docs/services/personality-insights/output.html). For detailed information about the meaning of a profile, see [Personality models](/docs/services/personality-insights/models.html) and [Consumption preferences](/docs/services/personality-insights/preferences.html).

### Visualizing a profile
{: #visualize}

The service provides a collection of JavaScript files that enable graphic visualization of a profile. The scripts facilitate use of the service with caching and content distribution networks. They rely on JavaScript, jQuery, HTML, and SVG with the Data-Driven Documents (`D3.js`) library to depict the results. For information about these client-side files, see the sample applications cited in [Using Software Development Kits](#sdks); for more information about `D3.js`, see [d3js.org ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://d3js.org/){: new_window}.

The service supports Cross-Origin Resource Sharing (CORS) to allow browser-based clients to make asynchronous requests directly to the service from front-end scripts. CORS lets clients request resources from a domain that is outside the domain from which the request originated; it lets web applications work around the same-origin security policy, which otherwise prevents such requests. For more information, see [enable-cors.org ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://enable-cors.org/){: new_window}.

## Using Software Development Kits
{: #sdks}

The {{site.data.keyword.personalityinsightsshort}} service supports a number of SDKs for simplified application development. The SDKs are available for many popular programming languages and platforms, including Node.js, Java, Python, and Apple&reg; iOS. For a complete list of SDKs and information about using them, see [{{site.data.keyword.watson}} SDKs ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/watson/developercloud/doc/common/getting-started-sdks.html){: new_window}. All SDKs are available from the [watson-developer-cloud namespace ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://github.com/watson-developer-cloud){: new_window} on GitHub.

The service also makes available the following sample applications to help you get started:

-   You can access an application that uses the Node.js SDK at the [personality-insights-nodejs repository ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window}.
-   You can access an application that uses the Java SDK at the [personality-insights-java repository ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://github.com/watson-developer-cloud/personality-insights-java){: new_window}.

All SDKs support authenticating by using either your {{site.data.keyword.Bluemix_short}} service credentials or an authentication token.

## Learning more about application development
{: #learn}

The {{site.data.keyword.personalityinsightsshort}} service supports two typical programming models: *Direct interaction*, in which the client communicates with the service directly; and *relaying via a proxy*, in which the client and service exchange all data (requests and results) through a proxy application that resides in {{site.data.keyword.Bluemix_short}}.

For more information about working with {{site.data.keyword.watson}} Developer Cloud services and {{site.data.keyword.Bluemix_notm}}, see the following:

-   For an introduction to working with {{site.data.keyword.watson}} services and {{site.data.keyword.Bluemix_notm}}, see [Getting started with {{site.data.keyword.watson}} and {{site.data.keyword.Bluemix_notm}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/watson/developercloud/doc/common/index.html){: new_window}.
-   For a language-independent introduction to developing {{site.data.keyword.watson}} services applications in {{site.data.keyword.Bluemix_notm}}, see [{{site.data.keyword.Bluemix_notm}} development approaches ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/watson/developercloud/doc/common/getting-started-bluemix.html){: new_window}.
-   For information about the two programming models available for developing {{site.data.keyword.watson}} applications, see [Programming models for {{site.data.keyword.watson}} services ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/watson/developercloud/doc/common/getting-started-develop.html){: new_window}:
    -   With relaying via a proxy, the client relies on a proxy server that resides in {{site.data.keyword.Bluemix_notm}} to communicate with the service; it passes all requests through the proxy application. Relaying requests via a proxy relies only on service credentials to authenticate with the service; see [Service credentials for {{site.data.keyword.watson}} services ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/watson/developercloud/doc/common/getting-started-credentials.html){: new_window}.
    -   With direct interaction, the client uses the proxy application in {{site.data.keyword.Bluemix_notm}} only to obtain an authentication token for the service, after which it communicates directly with the service. Direct interaction uses service credentials only to obtain a token; see [Tokens for authentication ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/watson/developercloud/doc/common/getting-started-tokens.html){: new_window}.
-   For information about controlling the default request logging that is performed for all {{site.data.keyword.watson}} services, see [Controlling request logging for {{site.data.keyword.watson}} services ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/watson/developercloud/doc/common/getting-started-logging.html){: new_window}.
