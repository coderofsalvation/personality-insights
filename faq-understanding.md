---

copyright:
  years: 2015, 2017
lastupdated: "2018-09-13"

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

# Understanding a profile
{: #output}

1.  <span style="color:#003F69">How do I interpret the scores that are returned by the service?</span>

    -   [Interpreting the numeric results](/docs/services/personality-insights/numeric.html) describes how to interpret the percentile that is returned by the service. It also includes information about behavior percentages and the optional raw scores and consumption preferences that the service can return.

1.  <span style="color:#003F69">Why does adding the scores for the facets of a dimension not yield the score for that dimension?</span>

    -   [Percentiles for personality characteristics](/docs/services/personality-insights/numeric.html#percentiles) answers this question. In summary, the service calculates the normalized percentile for each dimension and facet independently. No mathematical relationship exists between a dimension and its facets.

1.  <span style="color:#003F69">When would I use the raw score instead of the percentile score?</span>

    -   [Raw scores for personality characteristics](/docs/services/personality-insights/numeric.html#rawScores) provides insight into this choice. Briefly, you can use a raw score when you want to develop a custom normalization for a specific scenario or when comparison with a sample population is not required. If you need knowledge of how an author's results compare with a sample population, use the percentile scores.

1.  <span style="color:#003F69">How do I normalize a raw score to a percentile score?</span>

    -   [Raw scores for personality characteristics](/docs/services/personality-insights/numeric.html#rawScores) provides high-level guidance for normalizing a raw score and discusses {{site.data.keyword.IBM_notm}}'s approach to normalization.

1.  <span style="color:#003F69">How do I interpret the {{site.data.keyword.personalityinsightsshort}} visualization?</span>

    -   [Interpreting the numeric results](/docs/services/personality-insights/numeric.html) describes how to interpret the numerical results that are shown in the visualization.
