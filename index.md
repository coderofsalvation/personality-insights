---

copyright:
  years: 2015, 2018
lastupdated: "2018-11-08"

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

# About
{: #about}

> **Service update:** *The {{site.data.keyword.personalityinsightsshort}} service was updated on November 7, 2018. The service is now available in the IBM Cloud Tokyo location. For more information, see the [7 November 2018 service update](/docs/services/personality-insights/release-notes.html#November2018) in the release notes.*

The {{site.data.keyword.personalityinsightsfull}} service provides an application programming interface (API) for deriving insights from social media, enterprise data, or other digital communications. The service uses linguistic analytics to infer individuals' intrinsic personality characteristics from digital communications such as email, text messages, tweets, and forum posts.
{: shortdesc}

The service infers, from potentially noisy social media, portraits of individuals that reflect their personality characteristics. It can also determine individuals' consumption preferences, which indicate their likelihood to prefer various products, services, and activities.

## Personality characteristics
{: #models}

The {{site.data.keyword.personalityinsightsshort}} service infers personality characteristics based on three primary models:

-   **Big Five** personality characteristics represent the most widely used model for generally describing how a person engages with the world. The model includes five primary dimensions: *Agreeableness*, *Conscientiousness*, *Extraversion*, *Emotional range*, and *Openness*. Each dimension has six facets that further characterize an individual according to the dimension.
-   **Needs** describe which aspects of a product are likely to resonate with a person. The model includes twelve characteristic needs: *Excitement*, *Harmony*, *Curiosity*, *Ideal*, *Closeness*, *Self-expression*, *Liberty*, *Love*, *Practicality*, *Stability*, *Challenge*, and *Structure*.
-   **Values** describe motivating factors that influence a person's decision making. The model includes five values: *Self-transcendence / Helping others*, *Conservation / Tradition*, *Hedonism / Taking pleasure in life*, *Self-enhancement / Achieving success*, and *Open to change / Excitement*.

For more information, see [Personality models](/docs/services/personality-insights/models.html).

## Consumption preferences
{: #preferences}

Based on the personality characteristics that are inferred from the input text, the service can also return an indication of the author's consumption preferences. Consumption preferences indicate the author's likelihood to pursue different products, services, and activities. The service groups the individual preferences into eight categories: *Shopping*, *Music*, *Movies*, *Reading and learning*, *Health and activity*, *Volunteering*, *Environmental concern*, and *Entrepreneurship*. Each category contains from one to as many as a dozen individual preferences.

For more information, see [Consumption preferences](/docs/services/personality-insights/preferences.html).

## Benefits of the service
{: #benefits}

As a core service of the {{site.data.keyword.IBM_notm}} {{site.data.keyword.watson}} platform, the {{site.data.keyword.personalityinsightsshort}} service can provide insights that help businesses

-   Understand their customers at a deeper level by learning their clients' preferences, improving customer satisfaction, and strengthening client relations.
-   Improve client acquisition, retention, and engagement.
-   Guide highly personalized engagements and interactions to better tailor their products, services, campaigns, and communications for individual clients.

For more information about how you can benefit from the service, see [Use cases](/docs/services/personality-insights/usecases.html).

## Language support
{: #languages}

The service supports the following languages. You can use any combination of supported languages for the request and response, but all input text must be in the same language. For more information, see [Specifying request and response languages](/docs/services/personality-insights/input.html#languages).

<table style="width:75%">
  <caption>Table 1. Supported languages</caption>
  <tr>
    <th style="width:50%; text-align:center">
      Request languages
    </th>
    <th style="width:50%; text-align:center">
      Response languages
    </th>
  </tr>
  <tr>
    <td style="text-align:center; vertical-align:top">
      Arabic<br/>
      English<br/>
      Japanese<br/>
      Korean<br/>
      Spanish
    </td>
    <td style="text-align:center; vertical-align:top">
      Arabic<br/>
      English<br/>
      Japanese<br/>
      Korean<br/>
      Spanish<br/>
      Brazilian Portuguese<br/>
      French<br/>
      German<br/>
      Italian<br/>
      Simplified Chinese<br/>
      Traditional Chinese
    </td>
  </tr>
</table>

## Learn more about the service
{: #learn}

-   A [quick demo ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://personality-insights-demo.ng.bluemix.net/){: new_window} of the {{site.data.keyword.personalityinsightsshort}} service analyzes input text to develop a personality portrait that includes consumption preferences for the author.
-   Applications in {{site.data.keyword.watson}} Developer Cloud [Starter Kits ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://www.ibm.com/watson/developercloud/starter-kits.html){: new_window} demonstrate the service.
-   [The service in action](/docs/services/personality-insights/applied.html) and [The science behind the service](/docs/services/personality-insights/science.html) provide information about the research that underlies the service.
-   The [{{site.data.keyword.personalityinsightsshort}} service in the {{site.data.keyword.Bluemix_short}} Catalog ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://console.ng.bluemix.net/catalog/services/personality-insights/){: new_window} describes the pricing plans that are available for the service.
