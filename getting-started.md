---

copyright:
  years: 2015, 2017
lastupdated: "2017-09-10"

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

# Getting started tutorial

The {{site.data.keyword.personalityinsightsfull}} service derives insights about personality characteristics from social media, enterprise data, or other digital communications. This tutorial can help you get started quickly with the {{site.data.keyword.personalityinsightsshort}} service. The examples show you how to call the service's `POST /v3/profile` method with different types of input and how to request different types of output and output formats.
{: shortdesc}

> **Note:** The examples use cURL to call methods of the HTTP interface. You can install the version of cURL for your operating system from [curl.haxx.se ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://curl.haxx.se/){: new_window}. You must install the version that supports the Secure Sockets Layer (SSL) protocol. Make sure to include the installed binary file on your `PATH` environment variable.

## Step 1: Log in, create the service, and get your credentials

If you already know the credentials for your {{site.data.keyword.personalityinsightsshort}} service instance, skip this step.
{: tip}

1.  Go to the [{{site.data.keyword.personalityinsightsshort}} service ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://console.bluemix.net/catalog/services/personality-insights/){: new_window} and either sign up for a free {{site.data.keyword.Bluemix_notm}} account or log in.
1.  After you log in, enter `personality-tutorial` in the **Service name field** of the {{site.data.keyword.personalityinsightsshort}} page. Click **Create**.
1.  Copy your credentials:
    1.  Click **Service credentials**.
    1.  Click **View credentials** under **Actions**.
    1.  Copy the `username` and `password` values.

## Step 2: Send plain text and receive basic JSON output
{: #example1}

The first example passes the plain text file `profile.txt` to the `POST /v3/profile` method and implicitly requests the default JSON response.

1.  Download the sample file <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.txt" download="profile.txt">profile.txt <img src="../../icons/launch-glyph.svg" alt="External link icon" title="External link icon" class="style-scope doc-content"></a>.
1.  Issue the following command to send the file to the `/v3/profile` method and request the default JSON response. The `charset` parameter included with the `Content-Type` header specifies the character encoding of the input text.
    -   Replace `{username}` and `{password}` with your service credentials from the previous step.
    -   Modify `{path_to_file}` to specify the location of the `profile.txt` file.

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: text/plain;charset=utf-8" \
    --data-binary "@{path_to_file}profile.txt" \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2016-10-20"
    ```
    {: pre}

The service returns a JSON profile object that includes basic metadata such as the number of words in the input, the language model with which the input was processed, and any warnings associated with the input. For more information, see [JSON response content](/docs/services/personality-insights/output.html#outputJSON).

The profile includes information about the Big Five personality, Needs, and Values characteristics for the author as inferred from the input text. The service reports a `percentile`, or normalized score, for each characteristic. The service computes the percentile by comparing the author's results with the results from a sample population. For more information, see [Personality characteristics output](/docs/services/personality-insights/output.html#traitJSON).

## Step 3: Send JSON input and receive detailed JSON output
{: #example2}

The second example passes the JSON file `profile.json` to the `/v3/profile` method, again accepting the default JSON response. The `consumption_preferences` and `raw_scores` query parameters are set to `true` to request a more detailed analysis of the input.

1.  Download the sample file <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="External link icon" title="External link icon" class="style-scope doc-content"></a>, which contains a collection of Twitter messages.
1.  Issue the following command to send the file to the `/v3/profile` method. The example specifies `application/json` for the `Content-Type` header; the `charset` parameter is not needed for JSON input. The example sets the `consumption_preferences` and `raw_scores` query parameters to `true`.

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: application/json" \
    --data-binary "@{path_to_file}profile.json" \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2016-10-20&consumption_preferences=true&raw_scores=true"
    ```
    {: pre}

The service returns a JSON profile that includes the metadata and characteristics returned with the previous example. For each characteristic, the service also includes a `raw_score`, which represents the author's score for the characteristic based solely on the input text, without comparing the results to a sample population.

Because the input content includes timestamps, the service also reports behavioral characteristics. These are temporal characteristics that indicate the `percentage` of the content items that were created on each day of the week and hour of the day. For more information, see [Behavioral output](/docs/services/personality-insights/output.html#behaviorJSON).

The service also reports scores for the collection of consumption preferences. The scores indicate the author's likelihood to prefer different products, services, and activities based on the inferred characteristics. For more information, see [Consumption preferences output](/docs/services/personality-insights/output.html#preferenceJSON).

## Step 4: Send JSON input and receive detailed CSV output
{: #example3}

The third example is similar to the second: it passes the same JSON content and requests the same results. But this example specifies `text/csv` for the `Accept` header to request the response in comma-separated values (CSV) format, using the `--output` option of the cURL command to direct the results to a file named `profile.csv`. The example sets the `csv_headers` query parameter to `true` to request that column headers be returned with the output.

1.  Issue the following command to send the JSON file to the `/v3/profile` method.

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: application/json" \
    --header "Accept: text/csv" \
    --data-binary "@{path_to_file}profile.json" \
    --output profile.csv \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2016-10-20&consumption_preferences=true&raw_scores=true&csv_headers=true"
    ```
    {: pre}

For a detailed description of the CSV response and headers, see [CSV response content](/docs/services/personality-insights/output.html#outputCSV).

## Next steps

-   Learn more about [Requesting a profile](/docs/services/personality-insights/input.html) and about [Understanding a profile](/docs/services/personality-insights/output.html).
-   Learn about the Big Five, Needs, and Values [Personality models](/docs/services/personality-insights/models.html).
-   Learn more about the API in the [API reference ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}
-   Interact with the API in the [API explorer ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://watson-api-explorer.mybluemix.net/apis/personality-insights-v3){: new_window}.
-   Explore the [Node.js sample application ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window} to learn more about application development with the service.
