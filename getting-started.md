---

copyright:
  years: 2015, 2018
lastupdated: "2018-09-26"

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
{:download: .download}

# Getting started tutorial
{: #gettingStarted}

The {{site.data.keyword.personalityinsightsfull}} service derives insights about personality characteristics from social media, enterprise data, or other digital communications. This tutorial can help you get started quickly with the {{site.data.keyword.personalityinsightsshort}} service. The examples show you how to call the service's `POST /v3/profile` method with different types of input and how to request different types of output and output formats.
{: shortdesc}

> **Important:** The tutorial uses {{site.data.keyword.Bluemix}} Identity and Access Management (IAM) API keys for authentication. Some service instances continue to use service credentials (`{username}:{password}`) for authentication. Authenticate by using the approach that is right for your region and service instance. For more information about where and how the service uses IAM authentication, see the [Release notes](/docs/services/personality-insights/release-notes.html).

## Before you begin
{: #before-you-begin}

-   {: download} If you're seeing this, you created your service instance. Now get your credentials.
-   Create an instance of the service:
    1.  Go to the [{{site.data.keyword.personalityinsightsshort}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://console.{DomainName}/catalog/services/personality-insights){: new_window} page in the {{site.data.keyword.Bluemix_notm}} Catalog.
    1.  Sign up for a free {{site.data.keyword.Bluemix_notm}} account or log in.
    1.  Click **Create**.
-   Copy the credentials to authenticate to your service instance:
    1.  From the [{{site.data.keyword.Bluemix_notm}} dashboard ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://console.{DomainName}/dashboard/apps){: new_window}, click on your {{site.data.keyword.personalityinsightsshort}} service instance to go to the {{site.data.keyword.personalityinsightsshort}} service dashboard page.
    1.  On the **Manage** page, click **Show** to view your credentials.
    1.  Copy the `apikey` and `url` values.
-   Make sure that you have cURL.
    -   The examples use cURL to call methods of the HTTP interface. Install the version for your operating system from [curl.haxx.se ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://curl.haxx.se/){: new_window}. Install the version that supports the Secure Sockets Layer (SSL) protocol. Make sure to include the installed binary file on your `PATH` environment variable.

**Note:** When you enter a command, replace `{api_key}` with your actual API key. Omit the braces, which indicate a variable value, from the command. An actual value resembles the following example:

```bash
curl -X POST --user "apikey:L_HALhLVIksh1b73l97LSs6R_3gLo4xkujAaxm7i-b9x"
. . .
```
{:pre}

## Step 1: Send plain text input and receive basic JSON output
{: #example1}

The first example passes the plain text file `profile.txt` to the `POST /v3/profile` method and requests a JSON response.

1.  Download the sample file <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.txt" download="profile.txt">profile.txt <img src="../../icons/launch-glyph.svg" alt="External link icon" title="External link icon" class="style-scope doc-content"></a>.
1.  Issue the following command to send the file to the `/v3/profile` method and request a JSON response.
    -   The `Content-Type` header specifies that the input is plain text, `text/plain`. The `charset` parameter included with the header identifies the character encoding of the input text.
    -   The `Accept` header specifies `application/json` to indicate that JSON output is requested.
    -   Replace `{api_key}` with your IAM API key from the previous step.
    -   Modify `{path_to_file}` to specify the location of the `profile.txt` file.

    ```bash
    curl -X POST --user "apikey:{api_key}" \
    --header "Content-Type: text/plain;charset=utf-8" \
    --header "Accept: application/json" \
    --data-binary @{path_to_file}profile.txt \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13"
    ```
    {: pre}

The service returns a JSON `Profile` object that includes basic metadata such as the number of words in the input, the language model with which the input was processed, and any warnings associated with the input. For more information, see [The Profile object](/docs/services/personality-insights/output.html#outputJSON).

The profile includes information about the Big Five personality, Needs, and Values characteristics for the author as inferred from the input text. The service reports a `percentile`, or normalized score, for each characteristic. The service computes the percentile by comparing the author's results with the results from a sample population. For more information, see [Personality characteristics output](/docs/services/personality-insights/output.html#traitJSON).

## Step 2: Send JSON input and receive detailed JSON output
{: #example2}

The second example passes the JSON file `profile.json` to the `/v3/profile` method, again requesting a JSON response. The example requests consumption preferences and raw scores for a more detailed analysis of the input.

1.  Download the sample file <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="External link icon" title="External link icon" class="style-scope doc-content"></a>, which contains a collection of Twitter messages.
1.  Issue the following command to send the file to the `/v3/profile` method. The example specifies `application/json` for the `Content-Type` and `Accept` headers; the `charset` parameter is not needed for JSON input. The example sets the `consumption_preferences` and `raw_scores` query parameters to `true`.

    ```bash
    curl -X POST --user "apikey:{api_key}" \
    --header "Content-Type: application/json" \
    --header "Accept: application/json" \
    --data-binary @{path_to_file}profile.json \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true"
    ```
    {: pre}

The service returns a JSON profile that includes the metadata and characteristics returned with the previous example. For each characteristic, the service also includes a `raw_score`, which represents the author's score for the characteristic based solely on the input text, without comparing the results to a sample population.

Because the input content includes timestamps, the service also reports behavioral characteristics. These are temporal characteristics that indicate the `percentage` of the content items that were created on each day of the week and hour of the day. For more information, see [Behavioral output](/docs/services/personality-insights/output.html#behaviorJSON).

The service also reports scores for its collection of consumption preferences. The scores indicate the author's likelihood to prefer different products, services, and activities based on the inferred characteristics. For more information, see [Consumption preferences output](/docs/services/personality-insights/output.html#preferenceJSON).

## Step 3: Send JSON input and receive detailed CSV output
{: #example3}

The third example is similar to the second: it passes the same JSON content and requests the same results. But this example specifies `text/csv` for the `Accept` header to request the response in comma-separated values (CSV) format. It uses the `--output` option of the cURL command to direct the results to a file named `profile.csv`. The example sets the `csv_headers` query parameter to `true` to request that column headers be returned with the output.

1.  Issue the following command to send the JSON file to the `/v3/profile` method. The `Content-Type` header identifies the input content as `application/json`, and the `Accept` header requests CSV output, `text/csv`.

    ```bash
    curl -X POST --user "apikey:{api_key}" \
    --header "Content-Type: application/json" \
    --header "Accept: text/csv" \
    --data-binary @{path_to_file}profile.json \
    --output profile.csv \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true&csv_headers=true"
    ```
    {: pre}

For a detailed description of the CSV response and headers, see [Understanding a CSV profile](/docs/services/personality-insights/output-csv.html).

## Next steps

-   Learn more about [Requesting a profile](/docs/services/personality-insights/input.html) and about [Understanding a JSON profile](/docs/services/personality-insights/output.html) and [Understanding a CSV profile](/docs/services/personality-insights/output-csv.html).
-   Learn about the Big Five, Needs, and Values [Personality models](/docs/services/personality-insights/models.html).
-   Learn more about the API in the [API reference ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}
-   Explore the [Node.js sample application ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window} to learn more about application development with the service.
