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

# FAQs
{: #faq}

The following frequently asked questions (FAQs) address issues commonly associated with using the {{site.data.keyword.personalityinsightsshort}} service. The questions are grouped by topic. Many answers include links to the documentation for more information.
{: shortdesc}

## Basic usage
{: #basic}

1.  <span style="color:#003F69">Do the words that people use in everyday communications reflect their personalities, emotional states, social connections, and thinking styles?</span>

    -   [The science behind the service](/docs/services/personality-insights/science.html#science) begins with an introduction that summarizes the research that validates that communications do indeed indicate personality characteristics. Additional sections expand upon this finding.

1.  <span style="color:#003F69">Can personality characteristics that are computed by the service predict people's behavior and preferences?</span>

    -   [The science behind the service](/docs/services/personality-insights/science.html#science) has an introduction that mentions just a few of the many studies that show how personality characteristics can predict people's behavior.
    -   [The service in action](/docs/services/personality-insights/applied.html#applied) describes numerous studies by {{site.data.keyword.IBM_notm}} and other researchers that demonstrate how personality characteristics can predict both behavior and preferences.

1.  <span style="color:#003F69">What models does the service use to describe the personality characteristics that it infers from an author's input text?</span>

    -   [Personality models](/docs/services/personality-insights/models.html) describes the Big Five, Needs, and Values models that the service uses to describe its results.

1.  <span style="color:#003F69">How does the service infer personality characteristics?</span>

    -   [How personality characteristics are inferred](/docs/services/personality-insights/science.html#researchInfer) describes how the service infers personality characteristics from input text.

1.  <span style="color:#003F69">What is the accuracy of the service's estimation of personality characteristics?</span>

    -   [Guidelines for providing sufficient input](/docs/services/personality-insights/user-overview.html#overviewGuidelines) describes the average Mean Absolute Error (MAE) and average correlation for different amounts of input text.
    -   [How precise is the service](/docs/services/personality-insights/science.html#researchPrecise) describes measurements of the accuracy of the service's results and the surveys behind those results.

## Requesting a profile
{: #input}

1.  <span style="color:#003F69">How many words are needed for the service to reliably infer personality portraits or other characteristics of individuals from their language?</span>

    -   [Guidelines for providing sufficient input](/docs/services/personality-insights/user-overview.html#overviewGuidelines) describes the amount of text the service requires to infer a person's personality characteristics and provides guidelines for providing input.

1.  <span style="color:#003F69">Can the service infer characteristics from text that is written in languages other than English?</span>

    -   Yes. [Language support](/docs/services/personality-insights/user-overview.html#overviewLanguage) states that the service supports Arabic, English, Japanese, and Spanish input text for inferring characteristics.
    -   [Inferring personality from translated text](/docs/services/personality-insights/guidance.html#translation) provides guidance about using translated text as input to the service.

## Understanding a profile
{: #output}

1.  <span style="color:#003F69">How do I interpret the scores that are returned by the service?</span>

    -   [Interpreting the numeric results](/docs/services/personality-insights/output.html#numeric) describes how to interpret the percentile that is returned by the service. It also includes information about behavior percentages and the optional raw scores and consumption preferences that the service can return.

1.  <span style="color:#003F69">Why does adding the scores for the facets of a dimension not yield the score for that dimension?</span>

    -   [Percentiles for personality characteristics](/docs/services/personality-insights/output.html#percentiles) answers this question. In summary, the service calculates the normalized percentile for each dimension and facet independently. No mathematical relationship exists between a dimension and its facets.

1.  <span style="color:#003F69">When would I use the raw score instead of the percentile score?</span>

    -   [Raw scores for personality characteristics](/docs/services/personality-insights/output.html#rawscores) provides insight into this choice. Briefly, you can use a raw score when you want to develop a custom normalization for a specific scenario or when comparison with a sample population is not required. If you need knowledge of how an author's results compare with a sample population, use the percentile scores.

1.  <span style="color:#003F69">How do I normalize a raw score to a percentile score?</span>

    -   [Raw scores for personality characteristics](/docs/services/personality-insights/output.html#rawscores) provides high-level guidance for normalizing a raw score and discusses {{site.data.keyword.IBM_notm}}'s approach to normalization.

1.  <span style="color:#003F69">How do I interpret the {{site.data.keyword.personalityinsightsshort}} visualization?</span>

    -   [Interpreting the numeric results](/docs/services/personality-insights/output.html#numeric) describes how to interpret the numerical results that are shown in the visualization.

## Consumption preferences
{: #preferences}

1.  <span style="color:#003F69">What consumption preferences does the service return and how would I use them?</span>

    -   [Consumption preferences](/docs/services/personality-insights/preferences.html) introduces how businesses can leverage the consumption preferences and describes each preference and its range of possible values.

1.  <span style="color:#003F69">How does the service determine an author's consumption preferences?</span>

    -   [How consumption preferences are inferred](/docs/services/personality-insights/science.html#researchInferPrefs) describes how the service determines the preferences based on the personality characteristics that it infers from the input text.
