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

# Overview for users
{: #userOverview}

The {{site.data.keyword.personalityinsightsshort}} service offers a set of core analytics for discovering actionable insights about people and entities. The following sections provide basic information about using the service.
{: shortdesc}

## The personality models
{: #overviewModels}

The {{site.data.keyword.personalityinsightsshort}} service is based on the psychology of language in combination with data analytics algorithms. The service analyzes the content that you send and returns a personality profile for the author of the input. The service infers personality characteristics based on three models:

-   **Big Five** personality characteristics represent the most widely used model for generally describing how a person engages with the world. The model includes five primary dimensions:
    -   *Agreeableness* is a person's tendency to be compassionate and cooperative toward others.
    -   *Conscientiousness* is a person's tendency to act in an organized or thoughtful way.
    -   *Extraversion* is a person's tendency to seek stimulation in the company of others.
    -   *Emotional range*, also referred to as *Neuroticism* or *Natural reactions*, is the extent to which a person's emotions are sensitive to the person's environment.
    -   *Openness* is the extent to which a person is open to experiencing a variety of activities.

    Each of these top-level dimensions has six facets that further characterize an individual according to the dimension.
-   **Needs** describe which aspects of a product will resonate with a person. The model includes twelve characteristic needs: *Excitement*, *Harmony*, *Curiosity*, *Ideal*, *Closeness*, *Self-expression*, *Liberty*, *Love*, *Practicality*, *Stability*, *Challenge*, and *Structure*.
-   **Values** describe motivating factors that influence a person's decision making. The model includes five values: *Self-transcendence / Helping others*, *Conservation / Tradition*, *Hedonism / Taking pleasure in life*, *Self-enhancement / Achieving success*, and *Open to change / Excitement*.

For detailed information about the personality models and their characteristics, see [Personality models](/docs/services/personality-insights/models.html).

## Consumption preferences
{: #overviewPreferences}

The service can also return an indication of the consumption preferences for the author of the input text. Based on the personality characteristics inferred from the input, consumption preferences indicate the author's likelihood to pursue different products, services, and activities. The service assigns a binary or ternary indication of the author's inclination for each preference.

The service groups the individual preferences into eight categories: *Shopping*, *Music*, *Movies*, *Reading and learning*, *Health and activity*, *Volunteering*, *Environmental concern*, and *Entrepreneurship*. Each category contains from one to as many as 13 individual preferences.

For more information about the consumption preferences, their meaning, and their range of possible values, see [Consumption preferences](/docs/services/personality-insights/preferences.html).

## Submitting a request
{: #overviewRequest}

You can submit input as plain text, HTML, or JSON content, and the service can return its analysis in JSON or CSV format. For each personality characteristic, the service reports a *percentile*, which is a normalized score that describes the extent to which the author's writing exhibits a characteristic within a sample population. If requested, the service also returns a *raw score*, which is an absolute value that is not normalized for a sample population.

If the input is timestamped, the service provides a summary of the author's writing habits with respect to day of week and time of day. If requested, the service also returns a likelihood score for each of its available consumption preferences. For more information about submitting a request and about the meaning of the different results, see [Requesting a profile](/docs/services/personality-insights/input.html) and [Interpreting the numeric results](/docs/services/personality-insights/output.html#numeric).

## Guidelines for providing sufficient input
{: #overviewGuidelines}

A meaningful personality profile can be created only where sufficient data of suitable quantity and quality is provided. Because language use varies naturally from document to document and from time to time, a small sample of text might not be representative of an individual's overall language patterns. Moreover, different characteristics and different media converge at somewhat different rates.

Up to a point, more words are likely to produce better results, improving the service's precision by reducing the deviation between the predicted results and the author's actual score. You can send the service up to 20 MB of input content, but accuracy levels off at around 3000 words of input; additional content does not contribute further to the accuracy of the profile. Therefore, the service extracts and uses only the first 250 KB of content, not counting any HTML or JSON markup, from large requests.

This figure does not map to an exact number of words, which varies based on the language and nature of the text. In English, for example, average word length is between four and five characters, so this figure provides around 50,000 words, which is at least 15 times more words than the service needs to produce an accurate profile. By truncating long input, the service improves response time without sacrificing precision. The `word_count` field of the response JSON indicates the number of words that the service actually uses for a request, which can be less than the number of words submitted.

The following table documents the average Mean Absolute Error (MAE) across all characteristics based on the number of words provided as input. The smaller the MAE, the closer the service's results are to the scores the author would receive by taking an actual personality test. The final column reports the average correlation between inferred and actual scores across all characteristics. The information is based on English-language data, but the general guidelines for the number of words to provide apply to all languages. For more information about average MAE and correlation, along with statistics for specific languages, see [How precise is the service](/docs/services/personality-insights/science.html#researchPrecise).

<table style="width:80%">
  <caption>Table 1. Average MAE and correlation</caption>
  <tr>
    <th style="text-align:center; vertical-align:bottom; width:24%">Number of words</th>
    <th style="text-align:center; width:38%">Average MAE<br/>across all
      characteristics</th>
    <th style="text-align:center; width:38%">Average correlation<br/>across
      all characteristics</th>
  </tr>
  <tr>
    <td style="text-align:center">100</td>
    <td style="text-align:center">12.7%</td>
    <td style="text-align:center">0.095</td>
  </tr>
  <tr>
    <td style="text-align:center">300</td>
    <td style="text-align:center">12.5%</td>
    <td style="text-align:center">0.175</td>
  </tr>
  <tr>
    <td style="text-align:center">600</td>
    <td style="text-align:center">12.3%</td>
    <td style="text-align:center">0.212</td>
  </tr>
  <tr>
    <td style="text-align:center">1200</td>
    <td style="text-align:center">12.2%</td>
    <td style="text-align:center">0.237</td>
  </tr>
  <tr>
    <td style="text-align:center">3000</td>
    <td style="text-align:center">12.1%</td>
    <td style="text-align:center">0.257</td>
  </tr>
</table>

{{site.data.keyword.IBM_notm}} recommends that you provide at least 1200 words of input text, which results in an MAE that is within two percent of the best MAE the service can return. Submitting between 600 and 1200 words results in an MAE that is within three percent of the best MAE that {{site.data.keyword.IBM_notm}} still considers acceptable. Providing 3000 words is sufficient to achieve the service's maximum precision. You must submit at least 100 words; otherwise, the service reports an error. If you submit fewer than 600 words, the service reports a warning but still analyzes the input text.

These guidelines can help you accommodate the reliability of the results to your application. For example, for a casual application that recommends movies, you might be comfortable with less precision; for an application that makes more critical recommendations, you likely require more precise results. For more information about how the service infers personality characteristics, see [How personality characteristics are inferred](/docs/services/personality-insights/science.html#researchInfer).

## Language support
{: #overviewLanguage}

The {{site.data.keyword.personalityinsightsshort}} service can infer characteristics and return its response in the following languages.

<table style="width:80%">
  <caption>Table 2. Supported languages</caption>
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
      Spanish
    </td>
    <td style="text-align:center; vertical-align:top">
      Arabic<br/>
      English<br/>
      Japanese<br/>
      Spanish<br/>
      Brazilian Portuguese<br/>
      French<br/>
      German<br/>
      Italian<br/>
      Korean<br/>
      Simplified Chinese<br/>
      Traditional Chinese
    </td>
  </tr>
</table>

You can use any combination of supported languages for the request and response, but all input text must be in the same language. For more information, see [Specifying request and response languages](/docs/services/personality-insights/input.html#languages).

## Applying the service
{: #overviewApply}

{{site.data.keyword.IBM_notm}} researchers and others have validated the hypotheses behind the {{site.data.keyword.personalityinsightsshort}} service via studies in multiple domains. In addition to influencing the direction of the service and ensuring the validity of its results, these studies offer ideas for applying the service in your applications. For information about use cases that suggest additional applications of the service, see [Use cases](/docs/services/personality-insights/usecases.html).

### Studies by IBM

The following table lists studies performed by {{site.data.keyword.IBM_notm}} researchers and briefly summarizes their findings. These studies contributed directly to the development of the service. For more information about these {{site.data.keyword.IBM_notm}} studies, see [Studies by {{site.data.keyword.IBM_notm}} researchers](/docs/services/personality-insights/applied.html#appliedIBM).

<table>
  <caption>Table 3. Studies by IBM</caption>
  <tr>
    <th style="text-align:left; width:25%">Study</th>
    <th style="text-align:center; width:25%">Subjects</th>
    <th style="text-align:left; width:50%">Effect of Personality Characteristics</th>
  </tr>
  <tr>
    <td>
      <a href="applied.html#IBMrespond"><strong>Responding to tweets</strong></a>
      <br/>(information collection)
    </td>
    <td style="text-align:center">2000 Twitter users</td>
    <td>
      <strong>More likely to respond:</strong> Score high on Big Five dimensions
      and facets excitement-seeking, friendliness, activity level,
      gregariousness, trust, morality, extraversion, and
      agreeableness<br/><br/>
      <strong>Less likely to respond:</strong> Score high on Big Five facets
      cautiousness and anxiety
    </td>
  </tr>
  <tr>
    <td>
      <a href="applied.html#IBMretweet"><strong>Re-tweeting</strong></a>
      <br/>(information spreading)
    </td>
    <td style="text-align:center">3500 Twitter users</td>
    <td>
      <strong>More likely to re-tweet:</strong> Score high on Big Five dimensions
      and facets modesty, openness, and friendliness
    </td>
  </tr>
  <tr>
    <td>
      <a href="applied.html#IBMtarget"><strong>Targeted advertising</strong></a>
      <br/>(unsolicited advertising)
    </td>
    <td style="text-align:center">More than 6000 Twitter users
    </td>
    <td>
      <strong>Respond more favorably:</strong> Score high on Big Five dimension
      openness, and score low on Big Five dimension emotional range
    </td>
  </tr>
  <tr>
    <td>
      <a href="applied.html#IBMcampaign"><strong>Marketing campaigns</strong></a>
      <br/>(coupon redemption)
    </td>
    <td style="text-align:center">Thousands of retail customers</td>
    <td>
      <strong>More likely to respond:</strong> Score high on Big Five facets
      orderliness, self-discipline, and cautiousness, and score low
      on Big Five facet immoderation
    </td>
  </tr>
  <tr>
    <td>
      <a href="applied.html#IBMbrand"><strong>Brand preference</strong></a>
      <br/>(brand affinity)
    </td>
    <td style="text-align:center">600 Twitter users</td>
    <td>
      <strong>Predictors of brand preference:</strong> Big Five dimensions
      and facets conscientiousness, conservation, self-enhancement,
      and agreeableness; Needs love and ideal; and Value hedonism
    </td>
  </tr>
  <tr>
    <td>
      <a href="applied.html#IBMmember"><strong>Member satisfaction</strong></a>
      <br/>(community fulfillment)
    </td>
    <td style="text-align:center">More than 3000 community members</td>
    <td>
      <strong>Predictors of member satisfaction:</strong> Characteristics such as
      anger, anxiety, work, leisure, inhibition, assent, and use of the
      first-person pronoun
    </td>
  </tr>
  <tr>
    <td>
      <a href="applied.html#IBMreading"><strong>Reading preference</strong></a>
      <br/>(content interest)
    </td>
    <td style="text-align:center">More than 200 participants</td>
    <td>
      <strong>Interest in environmental articles:</strong> Score high on Value
      self-transcendence<br/><br/>
      <strong>Interest in work-related articles:</strong> Score high on Value
      self-enhancement
    </td>
  </tr>
  <tr>
    <td>
      <a href="applied.html#IBMpreferences"><strong>Consumption
          preferences</strong></a>
      <br/>(consumer purchasing)
    </td>
    <td style="text-align:center">Hundreds of thousands of data records</td>
    <td>
      <strong>Predicting consumer preferences:</strong> Demographic data and
      personality characteristics
    </td>
  </tr>
</table>

### Studies by others

The following table lists and briefly describes studies by researchers outside of {{site.data.keyword.IBM_notm}}. These studies influenced the direction of the service, and they validate the hypotheses on which it is based. For more information about these external studies, see [Studies by other researchers](/docs/services/personality-insights/applied.html#appliedOthers).

<table>
  <caption>Table 4. Studies by others</caption>
  <tr>
    <th style="text-align:left; width:25%">Topic Area</th>
    <th style="text-align:center; width:25%">Study</th>
    <th style="text-align:left; width:50%">Findings</th>
  </tr>
  <tr>
    <td>
      <a href="applied.html#otherConsumer">Consumer preferences</a>
    </td>
    <td style="text-align:center">
      Marketing messages
    </td>
    <td>
      People respond more favorably to marketing messages tailored to their
      personality.
    </td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center">
      Online marketing
    </td>
    <td>
      People with high openness are more likely to try new things.
    </td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center">
      Car ownership
    </td>
    <td>
      People who own convertibles differ in personality from the owners
      of standard or compact cars.
    </td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center">
      Car ownership
    </td>
    <td>
      People who own powerful cars differ in personality from those who
      prefer not to own powerful cars.
    </td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center">
      Car ownership
    </td>
    <td>
      Car owners tend to perceive the types of cars they buy as an extension
      of their personality.
    </td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center">
      Product design
    </td>
    <td>
      People with high openness respond to product design, while people
      with low openness value other product traits.
    </td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center">
      Brand preference
    </td>
    <td>
      Personality characteristics affect brand preference.
    </td>
  </tr>
  <tr>
    <td>
      <a href="applied.html#otherPersonal">Personal preferences</a>
    </td>
    <td style="text-align:center">
      Music preference
    </td>
    <td>
      People respond more positively to music recommendations tailored
      to their personality.
    </td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center">
      Music appreciation
    </td>
    <td>
      Individual differences in personality and cognition might determine
      how music is experienced.
    </td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center">
      Movie preference
    </td>
    <td>
      Movie preference correlates with personality.
    </td>
  </tr>
  <tr>
    <td>
      <a href="applied.html#otherSpending">Spending habits</a>
    </td>
    <td style="text-align:center">
      Credit card use
    </td>
    <td>
      Individuals with high conscientiousness tend not to abuse credits
      cards, while those with high emotional range do.
    </td>
  </tr>
  <tr>
    <td>
      <a href="applied.html#otherRisk">Risk profiles</a>
    </td>
    <td style="text-align:center">
      Financial investment
    </td>
    <td>
      Personality influences risky decision-making in financial
      investments.
    </td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center">
      Taking risks
    </td>
    <td>
      Agreeableness and conscientiousness lower people's willingness
      to take risks, while extraversion increases it.
    </td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center">
      Adventure sports
    </td>
    <td>
      Personality characteristics directly influence the probability
      of participating in risky sports.
    </td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center">
      Skydiving
    </td>
    <td>
      Skydivers typically have higher excitement-seeking and adventurousness
      than the general population.
    </td>
  </tr>
  <tr>
    <td>
      <a href="applied.html#otherProfessional">Professional performance</a>
    </td>
    <td style="text-align:center">
      Job performance
    </td>
    <td>
      Conscientiousness and other Big Five dimensions affect job
      performance.
    </td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center">
      Job performance
    </td>
    <td>
      Conscientiousness is the characteristic that best predicts job
      performance.
    </td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center">
      Leadership
    </td>
    <td>
      Extraversion correlates with leadership abilities.
    </td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center">
      Job satisfaction
    </td>
    <td>
      Personality characteristics such as extraversion and introversion
      positively and negatively indicate job satisfaction.
    </td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center">
      Adaptability
    </td>
    <td>
      Conscientiousness, extraversion, and openness correlate with
      career adaptability.
    </td>
  </tr>
  <tr>
    <td>
      <a href="applied.html#otherAcademic">Academic performance</a>
    </td>
    <td style="text-align:center">
      Academic achievement
    </td>
    <td>
      Personality characteristics such as neuroticism and
      conscientiousness can negatively and positively indicate academic
      performance.
    </td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center">
      Self-improvement
    </td>
    <td>
      Openness and conscientiousness often lead to more self-improvement
      learning, while neuroticism decreases such motivation.
    </td>
  </tr>
  <tr>
    <td>
      <a href="applied.html#otherProRelations">Professional
        relationships</a>
    </td>
    <td style="text-align:center">
      Interaction preferences
    </td>
    <td>
      Conscientiousness, openness, and other Big Five dimensions affect
      patients' interaction preferences with medical professionals.
    </td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center">
      Patient satisfaction
    </td>
    <td>
      Openness and conscientiousness affect physicians' patient
      satisfaction.
    </td>
  </tr>
  <tr>
    <td>
      <a href="applied.html#otherPerRelations">Personal relationships</a>
    </td>
    <td style="text-align:center">
      Romantic relationships
    </td>
    <td>
      Differences in personality characteristics such as agreeableness,
      emotional range, and openness predict marital dissatisfaction.
    </td>
  </tr>
  <tr>
    <td>
      <a href="applied.html#otherHealth">Health</a>
    </td>
    <td style="text-align:center">
      Health-related outcomes
    </td>
    <td>
      Personality characteristics predict health-related outcomes such
      as self-rated physical health and absenteeism from work.
    </td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center">
      Longevity
    </td>
    <td>
      High scores in conscientiousness, extraversion, and openness are
      associated with greater life expectancy.
    </td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center">
      Life outcomes
    </td>
    <td>
      Personality characteristics predict life outcomes such as mortality,
      divorce, and professional success.
    </td>
  </tr>
  <tr>
    <td>
      <a href="applied.html#otherDiet">Diet and exercise</a>
    </td>
    <td style="text-align:center">
      High-fat food
    </td>
    <td>
      People with high scores in emotional range and especially in
      immoderation tend to consume high-fat food.
    </td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center">
      Low-fat food
    </td>
    <td>
      Conscientiousness and especially self-discipline and dutifulness
      influence the consumption of low-fat food and regular weight
      control.
    </td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center">
      Healthy food
    </td>
    <td>
      The choice to consume healthy food is related to personality
      characteristics.
    </td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center">
      Varied diet
    </td>
    <td>
      Food lovers score high in openness to experience, which might
      motivate them to try different foods.
    </td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center">
      Healthy lifestyle
    </td>
    <td>
      Personality influences the decision to pursue a healthy lifestyle,
      including physical exercise.
    </td>
  </tr>
  <tr>
    <td>
      <a href="applied.html#otherDining">Dining out</a>
    </td>
    <td style="text-align:center">
      Dining choices
    </td>
    <td>
      Openness to experience correlates positively with more frequent
      dining out.
    </td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center">
      Dining choices
    </td>
    <td>
      Excitement-seeking also correlates with the decision to dine out.
    </td>
  </tr>
  <tr>
    <td>
      <a href="applied.html#otherEnvironment">Environmental
        consciousness</a>
    </td>
    <td style="text-align:center">
      Environmental concerns
    </td>
    <td>
      Personality influences people's level of interest in environmental
      concerns and pro-environmental behavior.
    </td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center">
      Product decisions
    </td>
    <td>
      Personality influences the decision to buy environmentally
      conscious products such as low-emission vehicles.
    </td>
  </tr>
  <tr>
    <td>
      <a href="applied.html#otherCommunity">Community service</a>
    </td>
    <td style="text-align:center">
      Community engagement
    </td>
    <td>
      Personality affects the tendency for prosocial behavior such
      as community service.
    </td>
  </tr>
  <tr>
    <td>
      <a href="applied.html#otherReligion">Religion and spirituality</a>
    </td>
    <td style="text-align:center">
      Religious tendencies
    </td>
    <td>
      Agreeableness suggests greater religious tendencies, while
      authority-challenging indicates less motivation to participate
      in religious and spiritual practices.
    </td>
  </tr>
</table>
