---

copyright:
  years: 2015, 2017
lastupdated: "2017-08-11"

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

# Personality models
{: #models}

As described in [Overview for users](/docs/services/personality-insights/user-overview.html), {{site.data.keyword.personalityinsightsshort}} analytics are developed based on the psychology of language in combination with data analytics algorithms. The characteristics are described in terms of three models:
{: shortdesc}

-   [Big Five](#outputBigFive)
-   [Needs](#outputNeeds)
-   [Values](#outputValues)

For more information about the models, how they were developed, and how the service uses them, see [The science behind the service](/docs/services/personality-insights/science.html).

## Big Five
{: #outputBigFive}

The first personality model, *Big Five*, was developed by Costa and Norman and is the most widely used model to generally describe how a person engages with the world. The model includes five primary categories, or *dimensions*:

-   [Agreeableness](#agreeableness)
-   [Conscientiousness](#conscientiousness)
-   [Extraversion](#extraversion)
-   [Emotional range](#emotionalRange)
-   [Openness](#openness)

Each top-level dimension has six subdimensions, or *facets*, that further characterize an individual according to the dimension. The following sections introduce the dimensions and provide detailed information about their facets. Each section includes three tables that provide the following information:

-   The first table, *Facets*, lists the dimension's facets and provides a brief description of individuals who score highly in each facet.
-   The second table, *Range of characteristics*, presents general descriptions that might apply to individuals whose scores evidence more of less of each facet of the dimension, as well as terms that might describe such individuals.

    > **Note:** The document <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Personality-Insights-Facet-Characteristics.pdf" download="Personality-Insights-Facet-Characteristics.pdf">Personality-Insights-Facet-Characteristics.pdf <img src="../../icons/launch-glyph.svg" alt="External link icon" title="External link icon" class="style-scope doc-content"></a> provides a convenient single-page table that includes the *Range of characteristics* tables for the facets of all five dimensions.
-   The third table, *Primary and secondary dimensions*, presents information that relates the dimension to other dimensions, describing combinations of personality characteristics. In this table, the rows represent the dimension that is identified as the individual's primary characteristic, and the columns provide terms that might describe people whose scores on the remaining secondary dimensions are higher or lower. The table provides interesting insight into how primary and secondary characteristics might interrelate to represent an individual's composite personality.

    > **Note:** The document <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Personality-Insights-Dimension-Characteristics.pdf" download="Personality-Insights-Dimension-Characteristics.pdf">Personality-Insights-Dimension-Characteristics.pdf <img src="../../icons/launch-glyph.svg" alt="External link icon" title="External link icon" class="style-scope doc-content"></a> provides a convenient single-page table that includes the *Primary and secondary characteristics* tables for all five dimensions.

### Agreeableness
{: #agreeableness}

**Agreeableness** is a person's tendency to be compassionate and cooperative toward others.

<table>
  <caption>Table 1. Agreeableness - Facets</caption>
  <tr>
    <th style="text-align:left">Facet</th>
    <th style="text-align:left">People who score high...</th>
  </tr>
  <tr>
    <td><strong>Altruism / Altruistic</strong></td>
    <td>Find that helping others is genuinely rewarding, that doing
    things for others is a form of self-fulfillment rather than
    self-sacrifice.</td>
  </tr>
  <tr>
    <td><strong>Cooperation / Accommodating / Compliance</strong></td>
    <td>Dislike confrontation. They are perfectly willing to compromise
    or to deny their own needs to get along with others.</td>
  </tr>
  <tr>
    <td><strong>Modesty / Modest</strong></td>
    <td>Are unassuming, rather self-effacing, and humble. However, they
    do not necessarily lack self-confidence or self-esteem.</td>
  </tr>
  <tr>
    <td><strong>Morality / Uncompromising / Sincerity</strong></td>
    <td>See no need for pretense or manipulation when dealing with
    others and are therefore candid, frank, and genuine.</td>
  </tr>
  <tr>
    <td><strong>Sympathy / Empathetic</strong></td>
    <td>Are tender-hearted and compassionate.</td>
  </tr>
  <tr>
    <td><strong>Trust / Trusting of others</strong></td>
    <td>Assume that most people are fundamentally fair, honest, and
    have good intentions. They take people at face value and are willing
    to forgive and forget.</td>
  </tr>
</table>

<table>
  <caption>Table 2. Agreeableness - Range of characteristics</caption>
  <tr>
    <th colspan="2" style="text-align:center">Description of LOW value</th>
    <th></th>
    <th colspan="2" style="text-align:center">Description of HIGH value</th>
  </tr>
  <tr>
    <th style="text-align:left; width:23%">Description</th>
    <th style="text-align:center; width:16%">Term</th>
    <th style="text-align:center; width:16%">Facet</th>
    <th style="text-align:center; width:16%">Term</th>
    <th style="text-align:right">Description</th>
  </tr>
  <tr>
    <td style="text-align:left">You are more concerned with taking care of yourself than taking time for others.</td>
    <td style="text-align:center">Self-focused</td>
    <td style="text-align:center"><strong>Altruism</strong></td>
    <td style="text-align:center">Altruistic</td>
    <td style="text-align:right">You feel fulfilled when helping others and will go out of your way to do so.</td>
  </tr>
  <tr>
    <td style="text-align:left">You do not shy away from contradicting others.</td>
    <td style="text-align:center">Contrary</td>
    <td style="text-align:center"><strong>Cooperation</strong></td>
    <td style="text-align:center">Accommodating</td>
    <td style="text-align:right">You are easy to please and try to avoid confrontation.</td>
  </tr>
  <tr>
    <td style="text-align:left">You hold yourself in high regard and are satisfied with who you are.</td>
    <td style="text-align:center">Proud</td>
    <td style="text-align:center"><strong>Modesty</strong></td>
    <td style="text-align:center">Modest</td>
    <td style="text-align:right">You are uncomfortable being the center of attention.</td>
  </tr>
  <tr>
    <td style="text-align:left">You are comfortable using every trick in the book to get what you want.</td>
    <td style="text-align:center">Compromising</td>
    <td style="text-align:center"><strong>Morality</strong></td>
    <td style="text-align:center">Uncompromising</td>
    <td style="text-align:right">You think it is wrong to take advantage of others to get ahead.</td>
  </tr>
  <tr>
    <td style="text-align:left">You think people should generally rely more on themselves than on others.</td>
    <td style="text-align:center">Hard-hearted</td>
    <td style="text-align:center"><strong>Sympathy</strong></td>
    <td style="text-align:center">Empathetic</td>
    <td style="text-align:right">You feel what others feel and are compassionate toward them.</td>
  </tr>
  <tr>
    <td style="text-align:left">You are wary of other people's intentions and do not trust easily.</td>
    <td style="text-align:center">Cautious of others</td>
    <td style="text-align:center"><strong>Trust</strong></td>
    <td style="text-align:center">Trusting of others</td>
    <td style="text-align:right">You believe the best of others and trust people easily.</td>
  </tr>
</table>

<table>
  <caption>Table 3. Agreeableness - Primary and secondary dimensions</caption>
  <tr>
    <th colspan="2"></th>
    <th colspan="2" style="text-align:center">Agreeableness value</th>
  </tr>
  <tr>
    <th colspan="2" style="width:30%">Dimension</th>
    <th style="width:35%"><em>High</em></th>
    <th style="width:35%"><em>Low</em></th>
  </tr>
  <tr>
    <td style="text-align:left"><strong>Conscientiousness</strong></td>
    <td style="text-align:center"><em>High</em></td>
    <td>Helpful, cooperative, considerate, respectful, polite</td>
    <td>Strict, rigid, stern</td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center"><em>Low</em></td>
    <td>Unpretentious, self-effacing</td>
    <td>Inconsiderate, impolite, distrustful, uncooperative, thoughtless</td>
  </tr>
  <tr>
    <td style="text-align:left"><strong>Extraversion</strong></td>
    <td style="text-align:center"><em>High</em></td>
    <td>Effervescent, happy, friendly, merry, jovial</td>
    <td>Bullheaded, abrupt, crude, combative, rough</td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center"><em>Low</em></td>
    <td>Soft-hearted, agreeable, obliging, humble, lenient</td>
    <td>Cynical, wary of others, reclusive, detached, impersonal</td>
  </tr>
  <tr>
    <td style="text-align:left"><strong>Emotional range</strong></td>
    <td style="text-align:center"><em>High</em></td>
    <td>Sentimental, affectionate, sensitive, soft, passionate</td>
    <td>Critical, selfish, ill-tempered, antagonistic, grumpy</td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center"><em>Low</em></td>
    <td>Generous, pleasant, tolerant, peaceful, flexible</td>
    <td>Insensitive, unaffectionate, passionless, unemotional</td>
  </tr>
  <tr>
    <td style="text-align:left"><strong>Openness</strong></td>
    <td style="text-align:center"><em>High</em></td>
    <td>Genial, tactful, diplomatic, deep, idealistic</td>
    <td>Shrewd, eccentric, individualistic</td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center"><em>Low</em></td>
    <td>Dependent, simple</td>
    <td>Coarse, tactless, curt, narrow-minded, callous</td>
  </tr>
</table>

### Conscientiousness
{: #conscientiousness}

**Conscientiousness** is a person's tendency to act in an organized or thoughtful way.

<table>
  <caption>Table 4. Conscientiousness - Facets</caption>
  <tr>
    <th style="text-align:left">Facet</th>
    <th style="text-align:left">People who score high...</th>
  </tr>
  <tr>
    <td><strong>Achievement striving / Driven</strong></td>
    <td>Try hard to achieve excellence. Their drive to be recognized
    as successful keeps them on track as they work hard to accomplish
    their goals.</td>
  </tr>
  <tr>
    <td><strong>Cautiousness / Deliberate / Deliberateness</strong></td>
    <td>Are disposed to think through possibilities carefully before
    acting.</td>
  </tr>
  <tr>
    <td><strong>Dutifulness / Dutiful / Sense of responsibility</strong></td>
    <td>Have a strong sense of duty and obligation.</td>
  </tr>
  <tr>
    <td><strong>Orderliness / Organized</strong></td>
    <td>Are well-organized, tidy, and neat.</td>
  </tr>
  <tr>
    <td><strong>Self-discipline / Persistent</strong></td>
    <td>Have the self-discipline, or "will-power," to persist at difficult
    or unpleasant tasks until they are completed.</td>
  </tr>
  <tr>
    <td><strong>Self-efficacy / Self-assured / Sense of competence</strong></td>
    <td>Are confident in their ability to accomplish things.</td>
  </tr>
</table>

<table>
  <caption>Table 5. Conscientiousness - Range of characteristics</caption>
  <tr>
    <th colspan="2" style="text-align:center">Description of LOW value</th>
    <th></th>
    <th colspan="2" style="text-align:center">Description of HIGH value</th>
  </tr>
  <tr>
    <th style="text-align:left; width:23%">Description</th>
    <th style="text-align:center; width:16%">Term</th>
    <th style="text-align:center; width:16%">Facet</th>
    <th style="text-align:center; width:16%">Term</th>
    <th style="text-align:right">Description</th>
  </tr>
  <tr>
    <td style="text-align:left">You are content with your level of
      accomplishment and do not feel the need to set ambitious goals.</td>
    <td style="text-align:center">Content</td>
    <td style="text-align:center"><strong>Achievement-striving</strong></td>
    <td style="text-align:center">Driven</td>
    <td style="text-align:right">You set high goals for yourself and work
      hard to achieve them.</td>
  </tr>
  <tr>
    <td style="text-align:left">You would rather take action immediately
      than spend time deliberating making a decision.</td>
    <td style="text-align:center">Bold</td>
    <td style="text-align:center"><strong>Cautiousness</strong></td>
    <td style="text-align:center">Deliberate</td>
    <td style="text-align:right">You carefully think through decisions before making them.</td>
  </tr>
  <tr>
    <td style="text-align:left">You do what you want, disregarding rules and obligations.</td>
    <td style="text-align:center">Carefree</td>
    <td style="text-align:center"><strong>Dutifulness</strong></td>
    <td style="text-align:center">Dutiful</td>
    <td style="text-align:right">You take rules and obligations seriously, even when they are inconvenient.</td>
  </tr>
  <tr>
    <td style="text-align:left">You do not make a lot of time for organization in your daily life.</td>
    <td style="text-align:center">Unstructured</td>
    <td style="text-align:center"><strong>Orderliness</strong></td>
    <td style="text-align:center">Organized</td>
    <td style="text-align:right">You feel a strong need for structure in your life.</td>
  </tr>
  <tr>
    <td style="text-align:left">You have a hard time sticking with difficult tasks for a long period of time.</td>
    <td style="text-align:center">Intermittent</td>
    <td style="text-align:center"><strong>Self-discipline</strong></td>
    <td style="text-align:center">Persistent</td>
    <td style="text-align:right">You can tackle and stick with tough tasks.</td>
  </tr>
  <tr>
    <td style="text-align:left">You frequently doubt your ability to achieve your goals.</td>
    <td style="text-align:center">Self-doubting</td>
    <td style="text-align:center"><strong>Self-efficacy</strong></td>
    <td style="text-align:center">Self-assured</td>
    <td style="text-align:right">You feel you have the ability to succeed in the tasks you set out to do.</td>
  </tr>
</table>

<table>
  <caption>Table 6. Conscientiousness - Primary and secondary dimensions</caption>
  <tr>
    <th colspan="2"></th>
    <th colspan="2" style="text-align:center">Conscientiousness value</th>
  </tr>
  <tr>
    <th colspan="2" style="width:30%">Dimension</th>
    <th style="width:35%"><em>High</em></th>
    <th style="width:35%"><em>Low</em></th>
  </tr>
  <tr>
    <td style="text-align:left"><strong>Agreeableness</strong></td>
    <td style="text-align:center"><em>High</em></td>
    <td>Dependable, responsible, reliable, mannerly, considerate</td>
    <td>Unpretentious, self-effacing</td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center"><em>Low</em></td>
    <td>Stern, strict, rigid</td>
    <td>Rash, uncooperative, unreliable, distrustful, thoughtless</td>
  </tr>
  <tr>
    <td style="text-align:left"><strong>Extraversion</strong></td>
    <td style="text-align:center"><em>High</em></td>
    <td>Ambitious, alert, firm, purposeful, competitive</td>
    <td>Unruly, boisterous, reckless, devil-may-care, demonstrative</td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center"><em>Low</em></td>
    <td>Cautious, confident, punctual, formal, thrifty</td>
    <td>Indecisive, aimless, wishy-washy, noncommittal, unambitious</td>
  </tr>
  <tr>
    <td style="text-align:left"><strong>Emotional range</strong></td>
    <td style="text-align:center"><em>High</em></td>
    <td>Particular, high-strung</td>
    <td>Scatterbrained, inconsistent, erratic, forgetful, impulsive</td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center"><em>Low</em></td>
    <td>Thorough, steady, consistent, self-disciplined, logical</td>
    <td>Informal, low-key</td>
  </tr>
  <tr>
    <td style="text-align:left"><strong>Openness</strong></td>
    <td style="text-align:center"><em>High</em></td>
    <td>Sophisticated, perfectionistic, industrious, dignified, refined</td>
    <td>Unconventional, quirky</td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center"><em>Low</em></td>
    <td>Traditional, conventional</td>
    <td>Foolhardy, illogical, immature, haphazard, lax</td>
  </tr>
</table>

### Extraversion
{: #extraversion}

**Extraversion** is a person's tendency to seek stimulation in the company of others.

<table>
  <caption>Table 7. Extraversion - Facets</caption>
  <tr>
    <th style="text-align:left">Facet</th>
    <th style="text-align:left">People who score high...</th>
  </tr>
  <tr>
    <td><strong>Activity level / Energetic</strong></td>
    <td>Lead fast-paced and busy lives. They do things and move about quickly,
    energetically, and vigorously, and they are involved in many activities.</td>
  </tr>
  <tr>
    <td><strong>Assertiveness / Assertive</strong></td>
    <td>Like to take charge and direct the activities of others. They tend to be
    leaders in groups.</td>
  </tr>
  <tr>
    <td><strong>Cheerfulness / Cheerful / Positive emotions</strong></td>
    <td>Experience a range of positive feelings, including happiness, enthusiasm,
    optimism, and joy.</td>
  </tr>
  <tr>
    <td><strong>Excitement-seeking</strong></td>
    <td>Are easily bored without high levels of stimulation.</td>
  </tr>
  <tr>
    <td><strong>Friendliness / Outgoing / Warmth</strong></td>
    <td>Genuinely like other people and openly demonstrate positive feelings
    toward others.</td>
  </tr>
  <tr>
    <td><strong>Gregariousness / Sociable</strong></td>
    <td>Find the company of others pleasantly stimulating and rewarding.
    They enjoy the excitement of crowds.</td>
  </tr>
</table>

<table>
  <caption>Table 8. Extraversion - Range of characteristics</caption>
  <tr>
    <th colspan="2" style="text-align:center">Description of LOW value</th>
    <th></th>
    <th colspan="2" style="text-align:center">Description of HIGH value</th>
  </tr>
  <tr>
    <th style="text-align:left; width:23%">Description</th>
    <th style="text-align:center; width:16%">Term</th>
    <th style="text-align:center; width:16%">Facet</th>
    <th style="text-align:center; width:16%">Term</th>
    <th style="text-align:right">Description</th>
  </tr>
  <tr>
    <td style="text-align:left">You appreciate a relaxed pace in life.</td>
    <td style="text-align:center">Laid-back</td>
    <td style="text-align:center"><strong>Activity level</strong></td>
    <td style="text-align:center">Energetic</td>
    <td style="text-align:right">You enjoy a fast-paced, busy schedule with many activities.</td>
  </tr>
  <tr>
    <td style="text-align:left">You prefer to listen than to talk, especially in group settings.</td>
    <td style="text-align:center">Demure</td>
    <td style="text-align:center"><strong>Assertiveness</strong></td>
    <td style="text-align:center">Assertive</td>
    <td style="text-align:right">You tend to speak up and take charge of situations, and you are comfortable leading groups.</td>
  </tr>
  <tr>
    <td style="text-align:left">You are generally serious and do not joke much.</td>
    <td style="text-align:center">Solemn</td>
    <td style="text-align:center"><strong>Cheerfulness</strong></td>
    <td style="text-align:center">Cheerful</td>
    <td style="text-align:right">You are a joyful person and share that joy with the world.</td>
  </tr>
  <tr>
    <td style="text-align:left">You prefer activities that are quiet, calm, and safe.</td>
    <td style="text-align:center">Calm-seeking</td>
    <td style="text-align:center"><strong>Excitement-seeking</strong></td>
    <td style="text-align:center">Excitement-seeking</td>
    <td style="text-align:right">You are excited by taking risks and feel bored without lots of action going on.</td>
  </tr>
  <tr>
    <td style="text-align:left">You are a private person and do not let many people in.</td>
    <td style="text-align:center">Reserved</td>
    <td style="text-align:center"><strong>Friendliness</strong></td>
    <td style="text-align:center">Outgoing</td>
    <td style="text-align:right">You make friends easily and feel comfortable around other people.</td>
  </tr>
  <tr>
    <td style="text-align:left">You have a strong desire to have time to yourself.</td>
    <td style="text-align:center">Independent</td>
    <td style="text-align:center"><strong>Gregariousness</strong></td>
    <td style="text-align:center">Sociable</td>
    <td style="text-align:right">You enjoy being in the company of others.</td>
  </tr>
</table>

<table>
  <caption>Table 9. Extraversion - Primary and secondary dimensions</caption>
  <tr>
    <th colspan="2"></th>
    <th colspan="2" style="text-align:center">Extraversion value</th>
  </tr>
  <tr>
    <th colspan="2" style="width:30%">Dimension</th>
    <th style="width:35%"><em>High</em></th>
    <th style="width:35%"><em>Low</em></th>
  </tr>
  <tr>
    <td style="text-align:left"><strong>Agreeableness</strong></td>
    <td style="text-align:center"><em>High</em></td>
    <td>Social, energetic, enthusiastic, communicative, vibrant</td>
    <td>Unaggressive, humble, submissive, timid, compliant</td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center"><em>Low</em></td>
    <td>Opinionated, forceful, domineering, boastful, bossy</td>
    <td>Skeptical, wary of others, seclusive, uncommunicative, unsociable</td>
  </tr>
  <tr>
    <td style="text-align:left"><strong>Conscientiousness</strong></td>
    <td style="text-align:center"><em>High</em></td>
    <td>Active, competitive, persistent, ambitious, purposeful</td>
    <td>Restrained, serious, discreet, cautious, principled</td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center"><em>Low</em></td>
    <td>Boisterous, mischievous, exhibitionistic, gregarious, demonstrative</td>
    <td>Indirect, unenergetic, sluggish, non-persistent, vague</td>
  </tr>
  <tr>
    <td style="text-align:left"><strong>Emotional range</strong></td>
    <td style="text-align:center"><em>High</em></td>
    <td>Explosive, wordy, extravagant, volatile, flirtatious</td>
    <td>Guarded, pessimistic, secretive, cowardly</td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center"><em>Low</em></td>
    <td>Confident, bold, assured, uninhibited, courageous</td>
    <td>Tranquil, sedate, placid, impartial, unassuming</td>
  </tr>
  <tr>
    <td style="text-align:left"><strong>Openness</strong></td>
    <td style="text-align:center"><em>High</em></td>
    <td>Expressive, candid, dramatic, spontaneous, witty</td>
    <td>Inner-directed, introspective, meditative, contemplating, self-examining</td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center"><em>Low</em></td>
    <td>Verbose, unscrupulous, pompous</td>
    <td>Somber, meek, unadventurous, passive, apathetic</td>
  </tr>
</table>

### Emotional range
{: #emotionalRange}

**Emotional range**, also referred to as *Neuroticism* or *Natural reactions*, is the extent to which a person's emotions are sensitive to the individual's environment.

<table>
  <caption>Table 10. Emotional range - Facets</caption>
  <tr>
    <th style="text-align:left">Facet</th>
    <th style="text-align:left">People who score high...</th>
  </tr>
  <tr>
    <td><strong>Anger / Fiery</strong></td>
    <td>Have a tendency to feel angry.</td>
  </tr>
  <tr>
    <td><strong>Anxiety / Prone to worry</strong></td>
    <td>Often feel like something unpleasant, threatening, or dangerous is
    about to happen. The "fight-or-flight" system of their brains is too
    easily and too often engaged.</td>
  </tr>
  <tr>
    <td><strong>Depression / Melancholy / Moodiness</strong></td>
    <td>Tend to react more readily to life's ups and downs.</td>
  </tr>
  <tr>
    <td><strong>Immoderation / Self-indulgence</strong></td>
    <td>Feel strong cravings and urges that they have difficulty resisting,
    even though they know that they are likely to regret them later. They tend
    to be oriented toward short-term pleasures and rewards rather than long-term
    consequences.</td>
  </tr>
  <tr>
    <td><strong>Self-consciousness</strong></td>
    <td>Are sensitive about what others think of them. Their concerns about
    rejection and ridicule cause them to feel shy and uncomfortable around
    others; they are easily embarrassed.</td>
  </tr>
  <tr>
    <td><strong>Vulnerability / Susceptible to stress / Sensitivity to stress</strong></td>
    <td>Have difficulty coping with stress. They experience panic, confusion,
    and helplessness when under pressure or when facing emergency situations.</td>
  </tr>
</table>

<table>
  <caption>Table 11. Emotional range - Range of characteristics</caption>
  <tr>
    <th colspan="2" style="text-align:center">Description of LOW value</th>
    <th></th>
    <th colspan="2" style="text-align:center">Description of HIGH value</th>
  </tr>
  <tr>
    <th style="text-align:left; width: 23%">Description</th>
    <th style="text-align:center; width: 16%">Term</th>
    <th style="text-align:center; width: 16%">Facet</th>
    <th style="text-align:center; width: 16%">Term</th>
    <th style="text-align:right">Description</th>
  </tr>
  <tr>
    <td style="text-align:left">It takes a lot to get you angry.</td>
    <td style="text-align:center">Mild-tempered</td>
    <td style="text-align:center"><strong>Anger</strong></td>
    <td style="text-align:center">Fiery</td>
    <td style="text-align:right">You have a fiery temper, especially when things do not go your way.</td>
  </tr>
  <tr>
    <td style="text-align:left">You tend to feel calm and self-assured.</td>
    <td style="text-align:center">Self-assured</td>
    <td style="text-align:center"><strong>Anxiety</strong></td>
    <td style="text-align:center">Prone to worry</td>
    <td style="text-align:right">You tend to worry about things that might happen.</td>
  </tr>
  <tr>
    <td style="text-align:left">You are generally comfortable with yourself as you are.</td>
    <td style="text-align:center">Content</td>
    <td style="text-align:center"><strong>Depression</strong></td>
    <td style="text-align:center">Melancholy</td>
    <td style="text-align:right">You think quite often about the things you are unhappy about.</td>
  </tr>
  <tr>
    <td style="text-align:left">You have control over your desires, which are not particularly intense.</td>
    <td style="text-align:center">Self-controlled</td>
    <td style="text-align:center"><strong>Immoderation</strong></td>
    <td style="text-align:center">Hedonistic</td>
    <td style="text-align:right">You feel your desires strongly and are easily tempted by them.</td>
  </tr>
  <tr>
    <td style="text-align:left">You are hard to embarrass and are self-confident most of the time.</td>
    <td style="text-align:center">Confident</td>
    <td style="text-align:center"><strong>Self-consciousness</strong></td>
    <td style="text-align:center">Self-conscious</td>
    <td style="text-align:right">You are sensitive about what others might be thinking of you.</td>
  </tr>
  <tr>
    <td style="text-align:left">You handle unexpected events calmly and effectively.</td>
    <td style="text-align:center">Calm under pressure</td>
    <td style="text-align:center"><strong>Vulnerability</strong></td>
    <td style="text-align:center">Susceptible to stress</td>
    <td style="text-align:right">You are easily overwhelmed in stressful situations.</td>
  </tr>
</table>

<table>
  <caption>Table 12. Emotional range - Primary and secondary dimensions</caption>
  <tr>
    <th colspan="2"></th>
    <th colspan="2" style="text-align:center">Emotional range value</th>
  </tr>
  <tr>
    <th colspan="2" style="width:30%">Dimension</th>
    <th style="width:35%"><em>High</em></th>
    <th style="width:35%"><em>Low</em></th>
  </tr>
  <tr>
    <td style="text-align:left"><strong>Agreeableness</strong></td>
    <td style="text-align:center"><em>High</em></td>
    <td>Emotional, gullible, affectionate, sensitive, soft</td>
    <td>Patient, relaxed, undemanding, down-to-earth</td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center"><em>Low</em></td>
    <td>Temperamental, irritable, quarrelsome, impatient, grumpy</td>
    <td>Unemotional, insensitive, unaffectionate, passionless</td>
  </tr>
  <tr>
    <td style="text-align:left"><strong>Conscientiousness</strong></td>
    <td style="text-align:center"><em>High</em></td>
    <td>Particular, high-strung</td>
    <td>Rational, objective, steady, logical, decisive</td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center"><em>Low</em></td>
    <td>Compulsive, nosy, self-indulgent, forgetful, impulsive</td>
    <td>Informal, low-key</td>
  </tr>
  <tr>
    <td style="text-align:left"><strong>Extraversion</strong></td>
    <td style="text-align:center"><em>High</em></td>
    <td>Excitable, wordy, flirtatious, explosive, extravagant</td>
    <td>Unself-conscious, weariless, indefatigible</td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center"><em>Low</em></td>
    <td>Guarded, fretful, insecure, pessimistic, secretive</td>
    <td>Unassuming, unexcitable, placid, tranquil</td>
  </tr>
  <tr>
    <td style="text-align:left"><strong>Openness</strong></td>
    <td style="text-align:center"><em>High</em></td>
    <td>Excitable, passionate, sensual</td>
    <td>Heartfelt, versatile, creative, intellectual, insightful</td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center"><em>Low</em></td>
    <td>Easily rattled, easily irked, apprehensive</td>
    <td>Imperturbable, insensitive</td>
  </tr>
</table>

### Openness
{: #openness}

**Openness**, or *Open to Experience*, is the extent to which a person is open to experiencing a variety of activities.

<table>
  <caption>Table 13. Openness - Facets</caption>
  <tr>
    <th style="text-align:left">Facet</th>
    <th style="text-align:left">People who score high...</th>
  </tr>
  <tr>
    <td><strong>Adventurousness / Willingness to experiment</strong></td>
    <td>Are eager to try new activities and experience different things.
    They find familiarity and routine boring.</td>
  </tr>
  <tr>
    <td><strong>Artistic interests</strong></td>
    <td>Love beauty, both in art and in nature. They become easily involved
    and absorbed in artistic and natural events. With intellect, this facet
    is one of the two most important, central aspects of this
    characteristic.</td>
  </tr>
  <tr>
    <td><strong>Emotionality / Emotionally aware / Depth of emotions</strong></td>
    <td>Have good access to and awareness of their own feelings.</td>
  </tr>
  <tr>
    <td><strong>Imagination</strong></td>
    <td>View the real world as often too plain and ordinary. They use
    fantasy not as an escape but as a way of creating for themselves a
    richer and more interesting inner-world.</td>
  </tr>
  <tr>
    <td><strong>Intellect / Intellectual curiosity</strong></td>
    <td>Are intellectually curious and tend to think in symbols and
    abstractions. With artistic interests, this facet is one of the two
    most important, central aspects of this characteristic.</td>
  </tr>
  <tr>
    <td><strong>Liberalism / Authority challenging / Tolerance for diversity</strong></td>
    <td>Have a readiness to challenge authority, convention, and traditional
    values.</td>
  </tr>
</table>

<table>
  <caption>Table 14. Openness - Range of characteristics</caption>
  <tr>
    <th colspan="2" style="text-align:center">Description of LOW value</th>
    <th></th>
    <th colspan="2" style="text-align:center">Description of HIGH value</th>
  </tr>
  <tr>
    <th style="text-align:left; width: 23%">Description</th>
    <th style="text-align:center; width: 16%">Term</th>
    <th style="text-align:center; width: 16%">Facet</th>
    <th style="text-align:center; width: 16%">Term</th>
    <th style="text-align:right">Description</th>
  </tr>
    <tr>
    <td style="text-align:left">You enjoy familiar routines and prefer not to deviate from them.</td>
    <td style="text-align:center">Consistent</td>
    <td style="text-align:center"><strong>Adventurousness</strong></td>
    <td style="text-align:center">Adventurous</td>
    <td style="text-align:right">You are eager to experience new things.</td>
  </tr>
  <tr>
    <td style="text-align:left">You are less concerned with artistic or creative activities than most people.</td>
    <td style="text-align:center">Unconcerned with art</td>
    <td style="text-align:center"><strong>Artistic interests</strong></td>
    <td style="text-align:center">Appreciative of art</td>
    <td style="text-align:right">You enjoy beauty and seek out creative experiences.</td>
  </tr>
  <tr>
    <td style="text-align:left">You do not frequently think about or openly express your emotions.</td>
    <td style="text-align:center">Dispassionate</td>
    <td style="text-align:center"><strong>Emotionality</strong></td>
    <td style="text-align:center">Emotionally aware</td>
    <td style="text-align:right">You are aware of your feelings and how to express them.</td>
  </tr>
  <tr>
    <td style="text-align:left">You prefer facts over fantasy.</td>
    <td style="text-align:center">Down-to-earth</td>
    <td style="text-align:center"><strong>Imagination</strong></td>
    <td style="text-align:center">Imaginative</td>
    <td style="text-align:right">You have a wild imagination.</td>
  </tr>
  <tr>
    <td style="text-align:left">You prefer dealing with the world as it is, rarely considering
    abstract ideas.</td>
    <td style="text-align:center">Concrete</td>
    <td style="text-align:center"><strong>Intellect</strong></td>
    <td style="text-align:center">Philosophical</td>
    <td style="text-align:right">You are open to and intrigued by new ideas and love to explore them.</td>
  </tr>
  <tr>
    <td style="text-align:left">You prefer following with tradition to maintain a sense of stability.</td>
    <td style="text-align:center">Respectful of authority</td>
    <td style="text-align:center"><strong>Liberalism</strong></td>
    <td style="text-align:center">Authority-challenging</td>
    <td style="text-align:right">You prefer to challenge authority and traditional values to help bring about change.</td>
  </tr>
</table>

<table>
  <caption>Table 15. Openness - Primary and secondary dimensions</caption>
  <tr>
    <th colspan="2"></th>
    <th colspan="2" style="text-align:center">Openness value</th>
  </tr>
  <tr>
    <th colspan="2" style="width:30%">Dimension</th>
    <th style="width:35%"><em>High</em></th>
    <th style="width:35%"><em>Low</em></th>
  </tr>
  <tr>
    <td style="text-align:left"><strong>Agreeableness</strong></td>
    <td style="text-align:center"><em>High</em></td>
    <td>Idealistic, diplomatic, deep, tactful, genial</td>
    <td>Simple, dependent</td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center"><em>Low</em></td>
    <td>Shrewd, eccentric, individualistic</td>
    <td>Coarse, tactless, curt, narrow-minded, callous</td>
  </tr>
  <tr>
    <td style="text-align:left"><strong>Conscientiousness</strong></td>
    <td style="text-align:center"><em>High</em></td>
    <td>Analytical, perceptive, informative, articulate, dignified</td>
    <td>Conventional, traditional</td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center"><em>Low</em></td>
    <td>Unconventional, quirky</td>
    <td>Shortsighted, foolhardy, illogical, immature, haphazard</td>
  </tr>
  <tr>
    <td style="text-align:left"><strong>Extraversion</strong></td>
    <td style="text-align:center"><em>High</em></td>
    <td>Worldly, theatrical, eloquent, inquisitive, intense</td>
    <td>Verbose, unscrupulous, pompous</td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center"><em>Low</em></td>
    <td>Introspective, meditative, contemplating, self-examining, inner-directed</td>
    <td>Predictable, unimaginative, somber, apathetic, unadventurous</td>
  </tr>
  <tr>
    <td style="text-align:left"><strong>Emotional range</strong></td>
    <td style="text-align:center"><em>High</em></td>
    <td>Passionate, excitable, sensual</td>
    <td>Creative, intellectual, insightful, versatile, inventive</td>
  </tr>
  <tr>
    <td></td>
    <td style="text-align:center"><em>Low</em></td>
    <td>Easily rattled, easily irked, apprehensive</td>
    <td>Imperturbable, insensitive</td>
  </tr>
</table>

## Needs
{: #outputNeeds}

The second model, *Needs*, describes at a high level which aspects of a product are likely to resonate with the author of the text. The model includes twelve categories of needs based on Kotler's and Ford's work in marketing. The following table describes the twelve needs that are evaluated by the {{site.data.keyword.personalityinsightsshort}} service.

<table>
  <caption>Table 16. Needs</caption>
  <tr>
    <th style="text-align:left">Need</th>
    <th style="text-align:left">People who score high...</th>
  </tr>
  <tr>
    <td><strong>Excitement</strong></td>
    <td>Want to get out there and live life, have upbeat emotions, and want
      to have fun.</td>
  </tr>
  <tr>
    <td><strong>Harmony</strong></td>
    <td>Appreciate other people, their viewpoints, and their feelings.</td>
  </tr>
  <tr>
    <td><strong>Curiosity</strong></td>
    <td>Have a desire to discover, find out, and grow.</td>
  </tr>
  <tr>
    <td><strong>Ideal</strong></td>
    <td>Desire perfection and a sense of community.</td>
  </tr>
  <tr>
    <td><strong>Closeness</strong></td>
    <td>Relish being connected to family and setting up a home.</td>
  </tr>
  <tr>
    <td><strong>Self-expression</strong></td>
    <td>Enjoy discovering and asserting their own identities.</td>
  </tr>
  <tr>
    <td><strong>Liberty</strong></td>
    <td>Have a desire for fashion and new things, as well as the need for
      escape.</td>
  </tr>
  <tr>
    <td><strong>Love</strong></td>
    <td>Enjoy social contact, whether one-to-one or one-to-many. Any brand
      that is involved in bringing people together taps this need.</td>
  </tr>
  <tr>
    <td><strong>Practicality</strong></td>
    <td>Have a desire to get the job done, a desire for skill and efficiency,
      which can include physical expression and experience.</td>
  </tr>
  <tr>
    <td><strong>Stability</strong></td>
    <td>Seek equivalence in the physical world. They favor the sensible,
      the tried and tested.</td>
  </tr>
  <tr>
    <td><strong>Challenge</strong></td>
    <td>Have an urge to achieve, to succeed, and to take on challenges.</td>
  </tr>
  <tr>
    <td><strong>Structure</strong></td>
    <td>Exhibit groundedness and a desire to hold things together. They
      need things to be well organized and under control.</td>
  </tr>
</table>

## Values
{: #outputValues}

The third model, *Values*, describes motivating factors that influence the author's decision-making. The model includes five dimensions of human values based on Schwartz's work in psychology. The following table describes the five values that are inferred by the {{site.data.keyword.personalityinsightsshort}} service.

<table>
  <caption>Table 17. Values</caption>
  <tr>
    <th style="text-align:left">Value</th>
    <th style="text-align:left">People who score high...</th>
  </tr>
  <tr>
    <td><strong>Self-transcendence / Helping others</strong></td>
    <td>Show concern for the welfare and interests of others.</td>
  </tr>
  <tr>
    <td><strong>Conservation / Tradition</strong></td>
    <td>Emphasize self-restriction, order, and resistance to change.</td>
  </tr>
  <tr>
    <td><strong>Hedonism / Taking pleasure in life</strong></td>
    <td>Seek pleasure and sensuous gratification for themselves.</td>
  </tr>
  <tr>
    <td><strong>Self-enhancement / Achieving success</strong></td>
    <td>Seek personal success for themselves.</td>
  </tr>
  <tr>
    <td><strong>Open to change / Excitement</strong></td>
    <td>Emphasize independent action, thought, and feeling, as well as
      a readiness for new experiences.</td>
  </tr>
</table>
