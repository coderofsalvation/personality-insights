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

# Requesting a profile
{: #input}

To analyze content, you use the HTTP `POST` request method to call the `/v3/profile` method of the {{site.data.keyword.personalityinsightsshort}} service. You can pass the service a maximum of 20 MB of content to be analyzed via the body of the request, but the service requires far less input to produce an accurate personality profile; for more information, see [Guidelines for providing sufficient input](/docs/services/personality-insights/user-overview.html#overviewGuidelines).
{: shortdesc}

The `/v3/profile` method includes parameters that let you specify the type of content to be passed to and returned by the service, as well as the language of each type of content. The service always returns a profile that provides insight into the personality characteristics of the author of the input text. You can also request that the service return raw scores not compared with a sample population and consumption preferences that indicate the types of products, services, and activities the author is likely to prefer.

The following sections describe the parameters of the `/v3/profile` method. For information about the results of a request, see [Understanding a profile](/docs/services/personality-insights/output.html). For detailed information about the `/v3/profile` method, see the [API reference ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}.

## Specifying request and response formats
{: #formats}

You can use the `Content-Type` and `Accept` header parameters to indicate the format of the content you are passing to the method and the format of the service's response. You can use any combination of supported formats for the request and response.

<table>
  <caption>Table 1. Specifying request and response formats</caption>
  <tr>
    <th style="width:10%; text-align:left; vertical-align:bottom">
      Format
    </th>
    <th style="width:26%; text-align:center; vertical-align:bottom">
      Argument
    </th>
    <th style="width:32%; text-align:center; vertical-align:bottom">
      Supported by<br/>
      <code>Content-Type</code>
    </th>
    <th style="width:32%; text-align:center; vertical-align:bottom">
      Supported by<br/>
      <code>Accept</code>
    </th>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      Plain text
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/plain</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      Yes (default)<br/><br/>
      The service processes plain text without modification.
    </td>
    <td style="text-align:center; vertical-align:top">
      No
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      HTML
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/html</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      Yes<br/><br/>
      The service strips tags from the content before processing it.
    </td>
    <td style="text-align:center; vertical-align:top">
      No
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      JSON
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>application/json</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      Yes<br/><br/>
      Content must conform to the model defined by the
      <code>Content</code> object, which is an array
      of <code>ContentItem</code> objects.
    </td>
    <td style="text-align:center; vertical-align:top">
      Yes (default)<br/><br/>
      The service returns its results as a <code>Profile</code>
      object.
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      CSV
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/csv</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      No
    </td>
    <td style="text-align:center; vertical-align:top">
      Yes<br/><br/>
      By default, the service returns a single row of numeric results.
      Set the optional <code>csv_headers</code> query parameter to
      <code>true</code> to request headers for each column of the output.
    </td>
  </tr>
</table>

### Specifying the character set
{: #charset}

By default, the service uses the following character sets for input content:

-   *For plain text and HTML content,* the service uses the International Standards Organization (ISO)-8859-1 character set (effectively the ASCII character set) per the HTTP version 1.1 specification.
-   *For JSON content,* the service effectively always uses the Unicode Transformation Format (UTF)-8 character set per Section 8.1 of the International Engineering Task Force (IETF) [Request for Comment (RFC) 7159 ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://tools.ietf.org/html/rfc7159#section-8.1){: new_window}.

When submitting plain text or HTML content, include the `charset` parameter with the `Content-Type` header to indicate the character encoding of the input text. The following example specifies UTF-8 character encoding for plain text input:

```
Content-Type: text/plain;charset=utf-8
```
{: codeblock}

By using the `charset` parameter, you can avoid potential problems associated with non-ASCII or non-printable characters. If you pass UTF-8 data without specifying the character set, special characters can result in incorrect results or in HTTP 4*nn* or 5*nn* errors.

### Using cURL
{: #charsetCurl}

To prevent errors when using cURL, always pass the content via the `--data-binary` option of the `curl` command to preserve any UTF-8 encoding for the content. If you use the `--data` option to pass the content as ASCII, the command can process the input, which can cause problems for data encoded in UTF-8.

For example, the following `curl` command correctly uses the `--data-binary` option to post the content of the specified *filename* as it exists, with no additional processing. The command also uses the `charset` parameter with the `Content-Type` header, and it explicitly requests the default JSON response format.

```bash
curl -X POST --user {username}:{password}
--header "Content-Type: text/plain;charset=utf-8"
--header "Accept: application/json"
--data-binary @{filename}
"https://gateway.watsonplatform.net/personality-insights/api/v3/profile"
```
{: pre}

For additional examples of calling the service with different request and response formats, see the [Getting started tutorial](/docs/services/personality-insights/getting-started.html).

## Specifying JSON input
{: #json}

To pass JSON input, you use the `Content` object. The object includes an array of `ContentItem` objects, each of which contains an element of the content. The only required field of the object is `content`, which provides the text to be analyzed. Other optional fields let you specify the following:

-   `id` (string) is a unique ID for the content item.
-   `created` (integer) is a UNIX timestamp that indicates when the content item was created.
-   `updated` (integer) is a UNIX timestamp that indicates when the content item was last updated.
-   `contenttype` (string) indicates the type of the content item, `text/plain` or `text/html`.
-   `language` (string) indicates the language of the content item: `ar` (Arabic), `en` (English), `es` (Spanish), or `ja` (Japanese). See [Specifying request and response languages](#languages).
-   `parentid` (string) is the `id` of the content item's parent item.
-   `reply` (boolean) indicates whether the content item is a reply to another item.
-   `forward` (boolean) indicates whether the content item is a forward or copy of another item.

JSON input is well suited for content from Twitter or other social networks that consist of multiple conversations or posts. Instead of concatenating all of the author's text into a single string, you can use JSON to submit the data as it exists. This has the further advantage of letting the service know which pieces of text are related.

### Example JSON input
{: jsonExample}

Examples in the [Getting started tutorial](/docs/services/personality-insights/getting-started.html) use the sample JSON file <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="External link icon" title="External link icon" class="style-scope doc-content"></a>. The file includes a series of Twitter messages. The following example shows the first few tweets from the file.

```javascript
{
  "contentItems": [
    {
      "content": "Wow, I liked @TheRock before, now I really SEE how special he is. The daughter story was IT for me. So great! #MasterClass",
      "contenttype": "text/plain",
      "created": 1447639154000,
      "id": "666073008692314113",
      "language": "en"
    },
    {
      "content": ".@TheRock how did you Know to listen to your gut and Not go back to football? #Masterclass",
      "contenttype": "text/plain",
      "created": 1447638226000,
      "id": "666069114889179136",
      "language": "en"
    },
    . . .
  ]
}
```
{: codeblock}

## Specifying request and response languages
{: #languages}

You can use the `Content-Language` and `Accept-Language` header parameters to indicate the language of the input content and the language of the service's response. You can use any combination of supported languages for the request and response. If you do not indicate a language, the service uses its English-trained models for its analysis and English for its results. The following table lists the supported input and output languages and identifies the arguments that you use with the language-related parameters.

<table style="width:90%">
  <caption>Table 2. Specifying request and response languages</caption>
  <tr>
    <th style="width:28%; text-align:left; vertical-align:bottom">
      Language
    </th>
    <th style="width:12%; text-align:center; vertical-align:bottom">
      Argument
    </th>
    <th style="width:30%; text-align:center; vertical-align:bottom">
      Supported by<br/>
      <code>Content-Language</code>
    </th>
    <th style="width:30%; text-align:center; vertical-align:bottom">
      Supported by<br/>
      <code>Accept-Language</code>
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      Arabic
    </td>
    <td style="text-align:center">
      <code>ar</code>
    </td>
    <td style="text-align:center">
      Yes
    </td>
    <td style="text-align:center">
      Yes
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      English
    </td>
    <td style="text-align:center">
      <code>en</code>
    </td>
    <td style="text-align:center">
      Yes
    </td>
    <td style="text-align:center">
      Yes
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Japanese
    </td>
    <td style="text-align:center">
      <code>ja</code>
    </td>
    <td style="text-align:center">
      Yes
    </td>
    <td style="text-align:center">
      Yes
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Spanish
    </td>
    <td style="text-align:center">
      <code>es</code>
    </td>
    <td style="text-align:center">
      Yes
    </td>
    <td style="text-align:center">
      Yes
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Brazilian Portuguese
    </td>
    <td style="text-align:center">
      <code>pt-br</code>
    </td>
    <td style="text-align:center">
      No
    </td>
    <td style="text-align:center">
      Yes
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      French
    </td>
    <td style="text-align:center">
      <code>fr</code>
    </td>
    <td style="text-align:center">
      No
    </td>
    <td style="text-align:center">
      Yes
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      German
    </td>
    <td style="text-align:center">
      <code>de</code>
    </td>
    <td style="text-align:center">
      No
    </td>
    <td style="text-align:center">
      Yes
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Italian
    </td>
    <td style="text-align:center">
      <code>it</code>
    </td>
    <td style="text-align:center">
      No
    </td>
    <td style="text-align:center">
      Yes
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Korean
    </td>
    <td style="text-align:center">
      <code>ko</code>
    </td>
    <td style="text-align:center">
      Yes
    </td>
    <td style="text-align:center">
      Yes
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Simplified Chinese
    </td>
    <td style="text-align:center">
      <code>zh-cn</code>
    </td>
    <td style="text-align:center">
      No
    </td>
    <td style="text-align:center">
      Yes
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Traditional Chinese
    </td>
    <td style="text-align:center">
      <code>zh-tw</code>
    </td>
    <td style="text-align:center">
      No
    </td>
    <td style="text-align:center">
      Yes
    </td>
  </tr>
</table>

Submit all text in the same language; do not mix multiple languages in the same request. For two-character language arguments, the service treats regional variants as their parent language; for example, it interprets `en-US` as `en`.

### Specifying a language for JSON content
{: #languageJSON}

For plain text and HTML input, the `Content-Language` header is the only way to specify the language. For JSON input, you can also specify the language of each individual content item by using the `language` parameter of the `ContentItem` object. However, a language specified with the `Content-Language` header overrides a language specified for a content item; the service ignores content items that specify a different language.

Omit the `Content-Type` header to base the language solely on the specification of the content items. The service uses the most prevalent language from among the content items, which yields the best possible results. It counts the number of content items for each language and selects the language with the highest frequency. If multiple languages have the same maximum frequency, the service uses the language that reaches that value first. Again, the service ignores content items that specify a different language.

### Language considerations
{: #languageNotes}

Consider the following when submitting input in English or Arabic:

-   *For English,* results are based on US cultural norms. If you analyze English text from a different culture, you might need to adjust the results accordingly.
-   *For Arabic,* the service can trim the amount of input text for performance reasons. At a certain threshold, the accuracy of the results for Arabic does not improve with more words. If the service trims Arabic input, it returns a warning message to inform you that it reduced the amount of input text that it used for the profile.

For information about using translated text, see [Inferring personality from translated text](/docs/services/personality-insights/guidance.html#translation).

## Requesting raw scores
{: #rawScores}

The service always returns normalized scores for each personality characteristic (Big Five dimension and facet, Need, and Value) as part of its response. The service can also report a `raw_score` for each characteristic if you set the `raw_scores` query parameter to `true`. Raw scores represent the scores for the characteristics based solely on the author's text and the model for that characteristic, without comparing the results to a sample population. For more information about using raw scores, see [Raw scores for personality characteristics](/docs/services/personality-insights/numeric.html#rawScores).

## Requesting consumption preferences
{: #preferences}

The service always returns results for the personality models. When you set the `consumption_preferences` query parameter to `true`, the service also returns `scores` for a variety of consumption preferences based on the personality characteristics it infers from the input text. These results indicate the author's tendency to prefer different products, services, and activities. Businesses can use the results to better understand the author's inclinations and to personalize communications and offers for the author.

For more information about the different consumption preferences, see [Consumption preferences](/docs/services/personality-insights/preferences.html). For information about interpreting the numeric results for a preference, see [Scores for consumption preferences](/docs/services/personality-insights/numeric.html#scores).

## Specifying the interface version
{: #version}

All calls to the `/v3/profile` method must include the `version` query parameter to indicate the version of the service's API and response format that you want to use. You specify the version as a date of the form `YYYY-MM-DD`; for example, specify `2016-10-20` for October 20, 2016. The parameter allows the service to update its API and response format for new versions without breaking existing clients.

The date that you specify does not need to match a version of the service exactly; the service uses the version that is no later than the date you provide. If you specify a date that is earlier than the initial release of version 3, the service uses version 3 of the API. If you specify a date that is in the future or otherwise later than the most recent version, the service uses the latest version.
