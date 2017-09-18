---

copyright:
  years: 2015, 2017
lastupdated: "2017-09-13"

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

# Release notes
{: #release-notes}

The following sections document the new features and changes that were included for each release of the {{site.data.keyword.personalityinsightsshort}} service. Unless otherwise noted, all changes were backward-compatible and were automatically and transparently available to all new and existing applications.
{: shortdesc}

> **Note:** The release notes document the *service version* and *interface version* for all recent updates. You specify the *interface version* with the `version` query parameter to use new features and functionality made available with that update. The service returns both versions with the `X-Service-Api-Version` response header.

## 18 September 2017
{: #September2017}

**Service version:** `3.3.0`<br/> **Interface version:** `2016-10-20`

The service now supports input content in Korean (`ko`). For information about the average Mean Absolute Error (MAE) and average correlation for Korean input, see [Per-language average MAE and correlation](/docs/services/personality-insights/science.html#precisePerLanguage).

The service's models are unable to produce meaningful percentiles and raw scores for a few personality characteristics of Korean input. For more information about the results for these characteristics, see [Limitations for Arabic and Korean input](/docs/services/personality-insights/numeric.html#limitations).

## 10 April 2017
{: #April2017}

**Service version:** `3.1.7`<br/> **Interface version:** `2016-10-20`

-   The service changed how it handles requests with large amounts of input content. The service accepts a maximum of 20 MB of content. However, with the models based on *GloVe*, accuracy levels off at around 3000 words of input. This is different from the older models, where more text produced greater accuracy. In general, the service no longer needs as much content to produce an accurate profile. But additional content requires additional processing time, which can cause a request to time out before it completes.

    Therefore, the service now extracts and uses only the first 250 KB of content, not counting any HTML or JSON markup, from large requests. This figure does not map to an exact number of words, which varies based on the language and nature of the text. In English, for example, average word length is between four and five characters, so this figure provides around 50,000 words, which is at least 15 times more words than the service needs. The `word_count` field of the response JSON indicates the number of words that the service actually uses for a request, which can be less than the number of words in the input.

    Because it still bases a profile on many more words than it strictly needs for maximum accuracy, the service produces a profile that is just as accurate as in the past. However, the service responds much faster than before. For requests for which it uses only a portion of the input content, the service returns the following `CONTENT_TRUNCATED` warning message to make the user aware of the fact:

    `For maximum accuracy while also optimizing processing time, only the first 250KB of input text (excluding markup) was analyzed. Accuracy levels off at approximately 3K words so this did not affect the accuracy of the profile.`

    For more information, see [Guidelines for providing sufficient input](/docs/services/personality-insights/user-overview.html#overviewGuidelines).
-   The service was updated with small security fixes.

## 1 March 2017
{: #March2017}

**Service version:** `3.1.6`<br/> **Interface version:** `2016-10-20`

The {{site.data.keyword.personalityinsightsshort}} service was updated with small enhancements to logging.

## Older releases
{: #older}

-   [20 February 2017](#February2017b)
-   [13 February 2017](#February2017)
-   [13 January 2017](#January2017)
-   [15 December 2016](#December2016)
-   [15 November 2016](#November2016)
-   [20 October 2016](#October2016b)
-   [12 October 2016](#October2016a)
-   [31 August 2016](#August2016)
-   [14 July 2016](#July2016b)
-   [1 July 2016](#July2016a)
-   [7 June 2016](#June2016b)
-   [1 June 2016](#June2016a)
-   [17 May 2016](#May2016)
-   [18 March 2016](#March2016)
-   [9 July 2015](#July2015)
-   [23 February 2015](#February2015)

### 20 February 2017
{: #February2017b}

**Service version:** `3.1.5.1`<br/> **Interface version:** `2016-10-20`

The Personality insights service was updated with small security and defect fixes, and to improve metering of API calls.

### 13 February 2017
{: #February2017}

**Service version:** `3.1.4`<br/> **Interface version:** `2016-10-20`

-   The list of consumption preferences has been refined to include only those most important to understanding an individual's dominant lifestyle habits and consumer characteristics. The list of consumption preferences was shortened from 51 to 42; the remaining preferences express the author's likelihood to prefer different products, services, and activities more concisely, making it even easier to take action based on the results. The service no longer returns the following nine consumption preferences. For more information about the remaining preferences, see [Consumption preferences](/docs/services/personality-insights/preferences.html).

    <table>
      <caption>Table 1. Changes to consumption preferences</caption>
      <tr>
        <th style="text-align:left">Category</th>
        <th style="text-align:left">Consumption preferences removed</th>
      </tr>
      <tr>
        <td style="vertical-align: top">
          <p>
            <code>consumption_preferences_shopping</code>
          </p>
        </td>
        <td>
          <p>
            <code>consumption_preferences_automobile_resale_value</code>
          </p>
        </td>
      </tr>
      <tr>
        <td style="vertical-align: top">
          <p>
            <code>consumption_preferences_reading</code>
          </p>
        </td>
        <td>
          <p>
            <code>consumption_preferences_read_motive_enjoyment</code>
            <code>consumption_preferences_read_motive_information</code>
            <code>consumption_preferences_read_motive_mandatory</code>
            <code>consumption_preferences_read_motive_relaxation</code>
          </p>
        </td>
      </tr>
      <tr>
        <td style="vertical-align: top">
          <p>
            <code>consumption_preferences_health_and_activity</code>
          </p>
        </td>
        <td>
          <p>
            <code>consumption_preferences_adventurous_sports</code>
            <code>consumption_preferences_fast_food_frequency</code>
          </p>
        </td>
      </tr>
      <tr>
        <td style="vertical-align: top">
          <p>
            <code>consumption_preferences_volunteering</code>
          </p>
        </td>
        <td>
          <p>
            <code>consumption_preferences_volunteering_time</code>
            <code>consumption_preferences_volunteer_learning</code>
          </p>
        </td>
      </tr>
    </table>

-   *For Arabic input*, information about the average Mean Absolute Error (MAE) and average correlation is now available in [Per-language average MAE and correlation[(/docs/services/personality-insights/science.html#precisePerLanguage). In addition, the service's models are unable to produce meaningful percentiles and raw scores for a collection of personality characteristics. For more information about the results for these characteristics, see [Limitations for Arabic and Korean input](/docs/services/personality-insights/numeric.html#limitations).

### 13 January 2017
{: #January2017}

**Service version:** `3.1.2.1`<br/> **Interface version:** `2016-10-20`

The Personality insights service was updated with a few small defect fixes.

### 15 December 2016
{: #December2016}

**Service version:** `3.1.1`<br/> **Interface version:** `2016-10-20`

For Arabic input text, the {{site.data.keyword.personalityinsightsshort}} service now uses the open-source word-embedding technique called *GloVe* to develop a personality profile. The service no longer uses the Linguistic Inquiry and Word Count (LIWC) psycholinguistic dictionary for any language. For more information about how the service develops a personality portrait, see [How personality characteristics are inferred](/docs/services/personality-insights/science.html#researchInfer).

### 15 November 2016
{: #November2016}

**Service version:** `3.1.0`<br/> **Interface version:** `2016-10-20`

-   For Japanese input text, the {{site.data.keyword.personalityinsightsshort}} service now uses the open-source word-embedding technique called *GloVe* to develop a personality profile; the service no longer uses the Linguistic Inquiry and Word Count (LIWC) psycholinguistic dictionary for Japanese input. For more information, see [How personality characteristics are inferred](/docs/services/personality-insights/science.html#researchInfer).
-   The `name` fields of the `ConsumptionPreferencesCategory` and `ConsumptionPreferences` objects are now returned with localized strings in the language specified with the `Accept-Language` request header.
-   The update includes a few small defect fixes.

### 20 October 2016
{: #October2016b}

**Service version:** `3.0.0`<br/> **Interface version:** `2016-10-20`

The {{site.data.keyword.personalityinsightsshort}} service and its API were updated significantly. The API was incremented from version 2 to version 3 and offers new features. The remaining sections of this release note describe the changes in detail.

Version 3 is not backward-compatible with version 2. You are encouraged to migrate to version 3 to take advantage of the new features and changes. Migration to version 3 consists only of updating and redeploying your applications to use the changes described in these release notes for the new version. You do not need to create a new instance of the service in {{site.data.keyword.Bluemix_notm}}; you need only call the `v3` API.

> **Note:** Version 2 of the {{site.data.keyword.personalityinsightsshort}} API will be removed from service in the near future. You are strongly encouraged to migrate to version 3 as soon as possible. For now, you can access reference documentation for version 2 at [API reference for v2 ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/watson/developercloud/personality-insights/api/v2/){: new_window} {: new_window}; you can also access the interactive tool for testing calls to version 2 and viewing live responses from the service at [API explorer for v2 ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://watson-api-explorer.mybluemix.net/apis/personality-insights-v2){: new_window}.

#### More information about version 3

This documentation now describes version 3 of the {{site.data.keyword.personalityinsightsshort}} API. The following sections summarize the changes for the new version of the interface:

-   For information about calling the `profile` method, see [Requesting a profile](/docs/services/personality-insights/input.html).
-   For information about the `profile` method's response, see [Understanding a profile](/docs/services/personality-insights/output.html).
-   For complete details about the version 3 interface, see the [API reference ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}.

#### Changes to parameters of the <code>profile</code> method

Parameters of the `profile` method have changed as follows:

-   The API now offers an optional query parameter named `consumption_preferences`. The parameter accepts a boolean value that indicates whether information inferred about consumption preferences is to be returned with the results. By default, the information is not included in the response. For more information, see [New consumption preferences feature](#cp).
-   The API now includes a required query parameter named `version`. The parameter accepts a string that identifies the requested version of the API and the response format as a date in the form `YYYY-MM-DD`; for example, specify `2016-10-20` for October 20, 2016. This parameter allows the service to update its API or response format for new versions without breaking existing clients. The initial string for version 3 of the API is `2016-10-20`.

    The date that you specify does not need to match a version of the service exactly; the service uses the version that is no later than the date you provide. If you specify a date that is earlier than the release date of version 3, the service uses version 3 of the API. If you specify a date that is in the future or otherwise later than the most recent version, the service uses the latest version.
-   The name of the `include_raw` query parameter is now `raw_scores`.
-   The name of the `headers` query parameter is now `csv_headers`.

#### New consumption preferences feature
{: #cp}

The consumption preferences feature provides an indication of the author's tendency to exhibit different consumer tendencies. When you pass the `consumption_preferences` query parameter with a value of `true` to the `profile` method, the service returns the following additional results with the `Profile` object:

-   A `consumption_preferences` field that provides an array of `ConsumptionPreferencesCategory` objects.
-   Each `ConsumptionPreferencesCategory` object includes the following fields:
    -   `consumption_preference_category_id`: The ID of one of the consumption preferences categories
    -   `name`: The user-visible name of the category.
    -   `consumption_preferences`: An array of `ConsumptionPreferences` objects that provides results inferred from the input text for the individual preferences of the category
-   Each `ConsumptionPreferences` object includes the following fields:
    -   `consumption_preference_id`: The ID of one of the consumption preferences.
    -   `name`: The user-visible name of the consumption preference.
    -   `score`: The score for the consumption preference. For many preferences, `0.0` indicates unlikely, `0.5` indicates neutrality, and `1.0` indicates likely. The scores for some preferences are binary and do not allow a neutral value. The score is an indication of preference based on the results inferred from the input text, not a normalized percentile.

For more information about the consumption preferences, see [Consumption preferences](/docs/services/personality-insights/preferences.html).

> **Note:** Currently, the `name` field for both consumption preferences objects is always returned in English, regardless of the language specified with the `Accept-Language` request header.

#### Changes to JSON objects and fields

JSON input and output objects and their fields have been simplified and clarified as follows:

-   The following fields have been removed from JSON `ContentItem` objects that you can pass to the `profile` method with a request:
    -   `userid`
    -   `sourceid`
    -   `charset` (previously deprecated)

    You pass these objects in the body of a JSON request as elements of the `contentItems` array of the `Content` object.
-   The following fields of the JSON `Profile` object that is returned by the `profile` method have changed:
    -   The following fields have been removed:
        -   `id`
        -   `source`
    - The   `tree` field has been removed. It is replaced by four new fields:
        -   `personality` for Big Five personality characteristics.
        -   `needs` for Needs characteristics.
        -   `values` for Values characteristics.
        -   `behavior` for temporal results about the distribution of the content over the days of the week and the hours of the day. This field is returned only for JSON input that is timestamped.

    This change effectively moves the results one level higher in the JSON `Profile` object, eliminating a level of recursion.
    -   The name of the `processed_lang` field is now `processed_language`.
-   The following fields of JSON `Trait` objects that are returned by the `profile` method have been renamed:
    -   The name of the `id` field of the JSON `Trait` object is now `trait_id`.
    -   The name of the `percentage` field of the JSON `Trait` object is now `percentile`.
-   The following fields of JSON `Trait` objects that are returned by the `profile` method have been removed:
    -   `sampling_error`
    -   `raw_sampling_error`

    The service now reports an average Mean Absolute Error (MAE) that qualifies the precision of its results. For more information about the MAE for different amounts of input text, see [Guidelines for providing sufficient input](/docs/services/personality-insights/user-overview.html#overviewGuidelines).
-   JSON `Trait` objects are still returned for the `personality`, `needs`, and `values` fields of the `Profile` object. But the `behavior` field returns an array of JSON objects named `Behavior` that have the following fields:
    -   `trait_id`
    -   `name`
    -   `category`
    -   `percentage`

    In addition, behavioral information is no longer returned as a tree of values. The output consists of a single array that lists all temporal characteristics (day of week and time of day).
-   The name of the `id` field of the JSON `Warnings` object that can be returned by the `profile` method is now `warnings_id`.

#### Changes to JSON IDs
{: #ids}

The JSON IDs that the service returns for the `trait_id` (formerly `id`) field of the `Trait` and the new `Behavior` object have changed as follows:

-   The IDs for Big Five dimensions now begin with the string `big5_`.
-   The IDs for Big Five facets now begin with the string `facet_`.
-   The IDs for Needs now begin with the string `need_`.
-   The IDs for Values now begin with the string `value_`.
-   The IDs for all temporal characteristics now begin with the string `behavior_`.
-   The IDs for temporal characteristics related to time of day now use four-digit 24-hour time (for example, `behavior_0000`) rather than 12-hour time (for example, `0:00 am`).
-   All characters are now lowercase.
-   Spaces and hyphens are now underscores.

#### Changes to CSV headers
{: #headers}

The optional column headers that the service can return for CSV output have changed as follows:

-   All of the changes described for the `trait_id` of the JSON output also apply to the CSV headers.
-   The headers for raw scores for Big Five dimensions now begin with the string `big5_`.
-   The headers for raw scores for Big Five facets now begin with the string `facet_`.
-   The headers for raw scores for Needs now begin with the string `need_`.
-   The headers for raw scores for Values now begin with the string `value_`.
-   The header for the processed language column is now `processed_language` rather than `processed_lang`.
-   The `user` and `source_id` columns are no longer returned.
-   All characters are now lowercase.
-   Spaces and hyphens are now underscores.

#### Removal of the <code>visualize</code> method

Version 2 of the service's API included a deprecated `visualize` method that was used in an earlier release to visualize the results of a call to the `profile` method. The `visualize` method has been removed from the service's API. The service continues to provide a collection of JavaScript files that enable graphic visualization of a profile; for more information, see [Visualizing a profile](/docs/services/personality-insights/developer-overview.html#visualize).

### 12 October 2016
{: #October2016a}

For Spanish input text, the {{site.data.keyword.personalityinsightsshort}} service now uses the open-source word-embedding technique called *GloVe* to develop a personality profile; the service no longer uses the Linguistic Inquiry and Word Count (LIWC) psycholinguistic dictionary for Spanish input. The service began using the new model for English input text on August 31; it will apply the new model to the remaining input languages in the near future. For more information about the new model, see [How personality characteristics are inferred](/docs/services/personality-insights/science.html#researchInfer).

### 31 August 2016
{: #August2016}

The {{site.data.keyword.personalityinsightsshort}} service now uses an open-source word-embedding technique called *GloVe* to develop a personality profile; for more information, see [How personality characteristics are inferred](/docs/services/personality-insights/science.html#researchInfer). At this time, the service uses the new approach only for English input text. For other languages, the service continues to use the Linguistic Inquiry and Word Count (LIWC) psycholinguistic dictionary. Future versions of the service will use the open-vocabulary approach for all languages.

For the new model used for English input, the service reports the average Mean Absolute Error (MAE) of the results for its trained model. For information about how the MAE changes with different amounts of input text, see [Guidelines for providing sufficient input](/docs/services/personality-insights/user-overview.html#overviewGuidelines). Future versions of the service will report the MAE for non-English models and will recommend that you use it, as opposed to sampling errors, to determine how the precision of the service changes based on the amount of input text that you provide.

### 14 July 2016
{: #July2016b}

-   For Arabic input, the service can now trim the amount of input text for performance reasons. At a certain threshold, the accuracy of the results for Arabic does not improve with more words. If the service trims Arabic input text, it returns a `PARTIAL_TEXT_USED` warning with the following message:

    `The text provided to compute the profile was trimmed for performance reasons. This action does not affect the accuracy of the output, as not all of the input text was required.`
-   The update includes additional defect fixes and internal improvements.

### 1 July 2016
{: #July2016a}

-   The pricing plans for the service have changed to offer lower prices for {{site.data.keyword.personalityinsightsshort}} users. For more information, see the [{{site.data.keyword.personalityinsightsshort}} service in the {{site.data.keyword.Bluemix_short}} Catalog ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://console.ng.bluemix.net/catalog/services/personality-insights/){: new_window}.
-   The list of supported response languages that you can specify with the `Accept-Language` header now includes the following:
    -   `ar` (Arabic)
    -   `de` (German)
    -   `en` (English, the default)
    -   `es` (Spanish)
    -   `fr` (French)
    -   `it` (Italian)
    -   `ja` (Japanese)
    -   `ko` (Korean)
    -   `pt-br` (Brazilian Portuguese)
    -   `zh-cn` (Simplified Chinese)
    -   `zh-tw` (Traditional Chinese)

    For more information, see [Language support](/docs/services/personality-insights/user-overview.html#overviewLanguage).
-   The `profile` method can now return the following HTTP status codes:
    -   429 *Too Many Requests*: The service is currently processing too many requests for the content language. Wait a short time and try the request again. If you are submitting many requests for the language, consider throttling the rate at which you submit requests.
    -   504 *Gateway Timeout*: The request timed out or took too long to process. Wait a short time and try the request again. If the input contained a large number of words (for example, more than 20,000), consider reducing the number of words while maintaining the guidelines for meaningful input.

    The method no longer returns 503 *Service Unavailable*. For more information about possible response codes, see the [API reference ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}.
-   The update includes additional defect fixes and internal improvements.

### 7 June 2016
{: #June2016b}

-   The service now supports Cross-Origin Resource Sharing (CORS) to allow browser-based clients to call the service directly. For more information, see [Visualizing a profile](/docs/services/personality-insights/developer-overview.html#visualize).
-   The service's performance when processing Japanese text has improved significantly.
-   The update includes additional defect fixes and internal improvements.

### 1 June 2016
{: #June2016a}

The {{site.data.keyword.personalityinsightsshort}} service was updated for defect fixes and internal improvements. An additional top-level field, `warnings`, was also added to the JSON results returned by the service; for more information, see the [API reference ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}.

### 17 May 2016
{: #May2016}

The {{site.data.keyword.personalityinsightsshort}} service was updated for defect fixes and internal improvements.

### 18 March 2016
{: #March2016}

The service now supports the following languages:

-   Four languages for its input text: Arabic (`ar`), English (`en`), Spanish (`es`), and Japanese (`ja`). To specify the language, use the HTTP `Content-Language` header for plain text and HTML input or the `language` property of the `ContentItem` object for JSON input.
-   The same four languages for its response. To specify the language of the response, use the `Accept-Language` header.

You can use any combination of languages for the input and response. In both cases, if you do not indicate a language, the service defaults to English. For more information, see [Language support](/docs/services/personality-insights/user-overview.html#overviewLanguage). Also refer to the blog post [Arabic and Japanese support is now available for {{site.data.keyword.IBM_notm}} {{site.data.keyword.watson}} {{site.data.keyword.personalityinsightsshort}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/blogs/watson/2016/04/arabic-japanese-support-now-available-ibm-watson-personality-insights/){: new_window} for additional information.

> **Note:** Because it requires significantly more computing cycles to analyze than other languages, Arabic content takes markedly longer to process. Although the service supports the same 20 MB restriction on the amount of input text for all languages, the practical limit for Arabic content may be lower to avoid timeouts. Japanese content also takes longer to process, but the delays are of less meaningful significance than they are for Arabic.

### 9 July 2015
{: #July2015}

-   *Language support.* The service now lets you analyze both English and Spanish content. You indicate the language of the input text with the `Content-Language` header of the `profile` method. For information about specifying a language, see [Specifying request and response languages](/docs/services/personality-insights/input.html#languages).
-   *Raw scores.* The service now lets you request raw scores and raw sampling errors computed from the input text and the service's models. The values are not normalized or compared with a sample population. Raw scores are useful for customers who want to apply a custom normalization for a specific scenario or who do not require a comparison with a sample population. You request raw scores by setting the `include_raw` query parameter of the `profile` method to `true`. For more information, see [Interpreting the numeric results](/docs/services/personality-insights/numeric.html).
-   *Model enhancements.* Based on its latest studies, {{site.data.keyword.IBM_notm}} has further improved some of its approaches to inferring personality characteristics. The changes are transparent to the service's users and do not invalidate any previous results obtained from the service. For more information about the studies and the service's approach to inference, see [How personality characteristics are inferred](/docs/services/personality-insights/science.html#researchInfer) and [How media influence inferred characteristics](/docs/services/personality-insights/science.html#researchMedia).

### 23 February 2015
{: #February2015}

As of February 23, 2015, the {{site.data.keyword.personalityinsightsshort}} service is the generally available (GA) version of the former User Modeling service, which was available as a beta release. The GA release requires that users migrate to an instance of the new service. The following differences exist between the beta and GA versions of the service.

-   The {{site.data.keyword.personalityinsightsshort}} service is backward-compatible with the User Modeling service. The differences that are described in this section provide more flexibility and improved results without affecting current applications.
-   The parameters with which you create the service in {{site.data.keyword.Bluemix_short}} have changed. You now use a service name of `personality_insights` instead of `user_modeling` and a service plan of `"IBM Watson Personality Insights Monthly Plan"` instead of `user_modeling_free_plan`.
-   The `profile` method accepts two new input formats. The `Content-Type` header now accepts the input formats plain text (`text/plain`), which is the default, and HTML (`text/html`), in addition to JSON (`application/json`).
-   The `profile` method now returns a new output format. The `Accept` header now accepts the output format CSV (`text/csv`) in addition to JSON (`application/json`), which is the default.
-   The `profile` method now includes a new output element, `sampling_error`, for each characteristic for which it reports a percentage value. The sampling error is returned as a double value that indicates the service's level of confidence in the author's percentile based on the input text.
-   The Needs model employs improved tokenization and processing to better normalize the distribution of values for its characteristics. You are advised to recompute any results that were generated by the User Modeling API.
-   The `visualize` method is now deprecated and will be removed entirely in a future release. You can use the `personality.js` JavaScript file that is provided with the sample application to achieve similar results from the client. The `textsummary.js` JavaScript file provides additional formatting for the results of the service.
