---

copyright:
  years: 2015, 2017
lastupdated: "2018-12-03"

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

# Requesting a profile
{: #input}

1.  <span style="color:#003F69">How many words are needed for the service to reliably infer personality portraits or other characteristics of individuals from their language?</span>

    -   [Providing sufficient input](/docs/services/personality-insights/input.html#sufficient) describes the amount of text the service requires to infer a person's personality characteristics and provides guidelines for providing input.

1.  <span style="color:#003F69">Does the service validate the content before producing a profile?</span>

    -   The service validates only the number of words that you submit. If you submit enough words, the service produces a profile. The service does not check for duplicate words or sentences. Such validation is subjective and better left to the user, who might have valid reasons to submit such input. Therefore, it is possible to obtain a profile by submitting the same word or sentence many times, but the resulting profile is not necessarily meaningful.

1.  <span style="color:#003F69">Can the service infer characteristics from text that is written in languages other than English?</span>

    -   Yes. [Specifying request and response languages](/docs/services/personality-insights/input.html#languages) states that the service supports Arabic, English, Japanese, Korean, and Spanish input text for inferring characteristics.
    -   [Inferring personality from translated text](/docs/services/personality-insights/guidance.html#translation) provides guidance about using translated text as input to the service.
