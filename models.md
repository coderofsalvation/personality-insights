---

copyright:
  years: 2015, 2018
lastupdated: "2018-12-10"

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

# Personality models
{: #models}

The {{site.data.keyword.personalityinsightsshort}} service is based on the psychology of language in combination with data analytics algorithms. The service analyzes the content that you send and returns a personality profile for the author of the input. The service infers personality characteristics based on three models:
{: shortdesc}

-   *Big Five* personality characteristics represent the most widely used model for generally describing how a person engages with the world. The model includes five primary dimensions:
    -   [*Agreeableness*](/docs/services/personality-insights/agreeableness.html) is a person's tendency to be compassionate and cooperative toward others.
    -   [*Conscientiousness*](/docs/services/personality-insights/conscientiousness.html) is a person's tendency to act in an organized or thoughtful way.
    -   [*Extraversion*](/docs/services/personality-insights/extraversion.html) is a person's tendency to seek stimulation in the company of others.
    -   [*Emotional range*](/docs/services/personality-insights/emotional-range.html), also referred to as *Neuroticism* or *Natural reactions*, is the extent to which a person's emotions are sensitive to the person's environment.
    -   [*Openness*](/docs/services/personality-insights/openness.html) is the extent to which a person is open to experiencing different activities.

    Each of these top-level dimensions has six facets that further characterize an individual according to the dimension.
-   [Needs](/docs/services/personality-insights/needs.html) describe which aspects of a product resonate with a person. The model includes twelve characteristic needs.
-   [Values](/docs/services/personality-insights/values.html) describe motivating factors that influence a person's decision making. The model includes five values.

For more information about how the models were developed and how the service uses them, see [The science behind the service](/docs/services/personality-insights/science.html).

## Descriptions of Big Five personality characteristics
{: #bigFive}

Each Big Five dimension is described by three tables:

-   The *Facets* table introduces the dimension's facets and describes individuals who score high on each facet.
-   The *Range of characteristics* table presents general descriptions that might apply to individuals whose scores evidence more or less of each facet of the dimension, along with terms that might describe such individuals. For a convenient single-page table that summarizes the *Range of characteristics* tables for the facets of all five dimensions, see <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Personality-Insights-Facet-Characteristics.pdf" download="Personality-Insights-Facet-Characteristics.pdf">Personality-Insights-Facet-Characteristics.pdf <img src="../../icons/launch-glyph.svg" alt="External link icon" title="External link icon"></a>.
-   The *Primary and secondary dimensions* table presents information that relates the dimension to other dimensions, describing combinations of personality characteristics. The table provides interesting insight into how primary and secondary characteristics might interrelate to represent an individual's composite personality. For a convenient single-page table that summarizes the *Primary and secondary characteristics* tables for all five dimensions, see <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Personality-Insights-Dimension-Characteristics.pdf" download="Personality-Insights-Dimension-Characteristics.pdf">Personality-Insights-Dimension-Characteristics.pdf <img src="../../icons/launch-glyph.svg" alt="External link icon" title="External link icon"></a>.
