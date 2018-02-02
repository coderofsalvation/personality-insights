---

copyright:
  years: 2015, 2017
lastupdated: "2017-11-28"

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

# Releaseinformationen
{: #release-notes}

In den folgenden Abschnitten sind die neuen Funktionen und Änderungen dokumentiert, die mit den einzelnen Releases des {{site.data.keyword.personalityinsightsshort}}-Service eingeführt wurden. Wenn nicht anders angegeben, sind alle Änderungen abwärtskompatibel und wurden für alle neuen und vorhandenen Anwendungen automatisch und transparent verfügbar gemacht.
{: shortdesc}

> **Anmerkung:** In den Releaseinformationen werden die *Serviceversion* und die *Schnittstellenversion* für alle letzten Aktualisierungen dokumentiert. Sie geben die *Schnittstellenversion* mit dem Abfrageparameter `version` ein, um die neuen Funktionen und die neue Funktionalität zu verwenden, die mit der jeweiligen Aktualisierung verfügbar gemacht werden. Der Service gibt beide Versionen mit dem Antwortheader `X-Service-Api-Version` zurück.

## 13. Oktober 2017
{: #October2017}

**Serviceversion:** `3.4.0`<br/> **Schnittstellenversion:** `2017-10-13`

-   Das Objekt `Trait` (Charaktermerkmal) eines Persönlichkeitsprofils enthält jetzt ein zusätzliches Feld `significant`. Ein separates Objekt `Trait` gibt die Ergebnisse für jede Big Five-Dimension, jede Big Five-Facette, jedes Bedürfnis (Need) und jeden Wert (Value) zurück. Das Feld `significant` jeder Instanz des Objekts gibt an, ob die Ergebnisse für das betreffende Merkmal für die Eingabesprache (`Content-Language`) der Anforderung aussagekräftig sind:

    -   Für Englisch, Spanisch und Japanisch enthält das Feld immer den Wert `true` für alle Persönlichkeitsmerkmale.
    -   Für Arabisch und Koreanisch hat das Feld den Wert `true` für die meisten Persönlichkeitsmerkmale. Es hat jedoch den Wert `false` für Merkmale, für die von den Modellen des Service keine aussagekräftigen Ergebnisse generiert werden können. Das Feld hat den Wert `false` für eine konstante Gruppe von Merkmalen; eine vollständige Liste finden Sie unter [Einschränkungen für arabische und koreanische Eingaben](/docs/services/personality-insights/numeric.html#limitations). Verlassen Sie sich nicht auf die Ergebnisse für ein Merkmal, für das das Feld den Wert `false` aufweist.

    Informationen zum JSON-Antwortinhalt des Service finden Sie unter [JSON-Profil verstehen](/docs/services/personality-insights/output.html).
-   Die CSV-Ausgabe enthält jetzt ebenfalls weitere Spalten, deren Überschriften das Format `*_significant` haben. Jede Spalte durch einen booleschen Wert an, ob ein Merkmal aussagekräftig ist. Informationen zu dem CSV-Antwortinhalt des Service finden Sie unter [CSV-Profil verstehen](/docs/services/personality-insights/output-csv.html).
-   Die Schnittstellenversion, die mit dem Parameter `version` zur Verwendung dieser letzten Version der Schnittstelle angegeben wird, ist `2017-10-13`.

## 18. September 2017
{: #September2017}

**Serviceversion:** `3.3.0`<br/> **Schnittstellenversion:** `2016-10-19`

Der Service unterstützt jetzt Eingabeinhalte in Koreanisch (`ko`). Informationen zum durchschnittlichen mittleren absoluter Fehler (Mean Absolute Error - MAE) und zur durchschnittlichen Korrelation für koreanische Eingaben finden Sie unter [Durchschnittlicher mittlerer absoluter Fehler und durchschnittliche Korrelation nach Sprache](/docs/services/personality-insights/science.html#precisePerLanguage).

Die Modelle des Services können für einige wenige Persönlichkeitsmerkmale koreanischer Eingaben keine aussagefähigen Perzentile und unaufbereitete Bewertungen generieren. Weitere Informationen zu den Ergebnissen für diese Merkmale finden Sie unter [Einschränkungen für arabische und koreanische Eingaben](/docs/services/personality-insights/numeric.html#limitations).

## 10. April 2017
{: #April2017}

**Serviceversion:** `3.1.7`<br/> **Schnittstellenversion:** `2016-10-19`

-   Die Art und Weise, in der der Service Anforderungen mit großen Mengen an Eingabeinhalt verarbeitet, wurde geändert. Der Service akzeptiert maximal 20 MB an Inhalt. Bei den Modellen, die auf *GloVe* basieren, wird die Genauigkeit jedoch ab etwa 3000 Eingabewörtern nicht mehr höher. Dies unterscheidet sich von den älteren Modellen, bei denen mehr Text zu Ergebnissen mit höherer Genauigkeit führte. Der Service benötigt allgemein nicht mehr so viel Inhalt, um ein präzises Profil generieren zu können. Zusätzlicher Inhalt erfordert indes zusätzliche Verarbeitungszeit, sodass es möglich ist, dass eine Anforderung das Zeitlimit überschreitet, bevor ihre Verarbeitung abgeschlossen ist.

    Daher extrahiert und verarbeitet der Service aus umfangreichen Anforderungen jetzt nur die ersten 250 KB des Inhalts (HTML- oder JSON-Markup nicht mitgezählt). Diese Anzahl entspricht keiner exakten Wortzahl, die je nach Sprache und Spezifik des Texts variiert. In der englischen Sprache liegt die durchschnittliche Wortlänge zum Beispiel zwischen vier und fünf Buchstaben, sodass diese Zahl ungefähr 50.000 Wörtern entspricht, was 15-mal mehr Wörter sind, als der Service benötigt. Im Feld `word_count` der JSON-Antwort wird die Anzahl der Wörter angegeben, die der Service tatsächlich für eine Anforderung verwendet. Diese Anzahl kann kleiner als die Anzahl der Wörter in der Eingabe sein.

    Da der Service ein Profil immer noch auf wesentlich mehr Wörter stützt, als für maximale Genauigkeit eigentlich erforderlich sind, generiert er ein Profil, das ebenso genau ist wie zuvor. Allerdings antwortet der Service wesentlich schneller als zuvor. Für Anforderungen, für die nur ein Teil des Eingabeinhalts verwendet werden, gibt der Service die folgende Warnung `CONTENT_TRUNCATED` zurück, um den Benutzer über die Tatsache zu informieren:

    `For maximum accuracy while also optimizing processing time, only the first 250KB of input text (excluding markup) was analyzed. Accuracy levels off at approximately 3K words so this did not affect the accuracy of the profile.`

    Weitere Informationen finden Sie unter [Ausreichende Eingabe bereitstellen](/docs/services/personality-insights/input.html#sufficient).
-   Der Service wurde mit kleinen Sicherheitskorrekturen aktualisiert.

## Frühere Releases
{: #older}

-   [1. März 2017](#March2017)
-   [20. Februar 2017](#February2017b)
-   [13. Februar 2017](#February2017)
-   [13. Januar 2017](#January2017)
-   [15. Dezember 2016](#December2016)
-   [15. November 2016](#November2016)
-   [20. Oktober 2016](#October2016b)
-   [12. Oktober 2016](#October2016a)
-   [31. August 2016](#August2016)
-   [14. Juli 2016](#July2016b)
-   [1. Juli 2016](#July2016a)
-   [7. Juni 2016](#June2016b)
-   [1. Juni 2016](#June2016a)
-   [17. Mai 2016](#May2016)
-   [18. März 2016](#March2016)
-   [9. Juli 2015](#July2015)
-   [23. Februar 2015](#February2015)

### 1. März 2017
{: #March2017}

**Serviceversion:** `3.1.6`<br/> **Schnittstellenversion:** `2016-10-19`

Der {{site.data.keyword.personalityinsightsshort}}-Service wurde mit kleinen Verbesserungen an der Protokollierung aktualisiert.

### 20. Februar 2017
{: #February2017b}

**Serviceversion:** `3.1.5.1`<br/> **Schnittstellenversion:** `2016-10-19`

Der Personality Insights-Service wurde mit kleinen Sicherheits- und Fehlerkorrekturen sowie zur Verbesserung der Messung von API-Aufrufen aktualisiert.

### 13. Februar 2017
{: #February2017}

**Serviceversion:** `3.1.4`<br/> **Schnittstellenversion:** `2016-10-19`

-   Die Liste der Verbraucherpräferenzen wurde neu definiert, um nur die wichtigsten für das Verständnis der dominanten Lebensgewohnheiten und Verbrauchermerkmale einzuschließen. Die Liste der Verbraucherpräferenzen wurde von 51 auf 42 gekürzt. Die verbleibenden Präferenzen drücken bündiger die Wahrscheinlichkeit aus, mit der der Autor verschiedene Produkte, Services und Aktivitäten bevorzugt, sodass es leichter wird, dem Ergebnis entsprechende Maßnahmen durchzuführen. Der Service gibt die folgenden neun Verbraucherpräferenzen nicht mehr zurück. Weitere Informationen zu den verbleibenden Präferenzen finden Sie unter [Verbraucherpräferenzen](/docs/services/personality-insights/preferences.html).

    <table>
      <caption>Tabelle 1. Änderungen an Verbraucherpräferenzen</caption>
      <tr>
        <th style="text-align:left">Kategorie</th>
        <th style="text-align:left">Entfernte Verbraucherpräferenzen</th>
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

-   *Für arabische Eingaben* sind jetzt Informationen zum durchschnittlichen mittlerer absoluter Fehler (Mean Absolute Error - MAE) und zur durchschnittlichen Korrelation unter [Durchschnittlicher mittlerer absoluter Fehler und durchschnittliche Korrelation nach Sprache](/docs/services/personality-insights/science.html#precisePerLanguage) verfügbar. Darüber hinaus können die Modelle des Service für eine Reihe von Persönlichkeitsmerkmalen keine aussagefähigen Perzentile und unaufbereitete Bewertungen generieren. Weitere Informationen zu den Ergebnissen für diese Merkmale finden Sie unter [Einschränkungen für arabische und koreanische Eingaben](/docs/services/personality-insights/numeric.html#limitations).

### 13. Januar 2017
{: #January2017}

**Serviceversion:** `3.1.2.1`<br/> **Schnittstellenversion:** `2016-10-19`

Der Personality Insights-Service wurde mit einigen Fehlerkorrekturen aktualisiert.

### 15. Dezember 2016
{: #December2016}

**Serviceversion:** `3.1.1`<br/> **Schnittstellenversion:** `2016-10-19`

Für arabischen Eingabetext verwendet der {{site.data.keyword.personalityinsightsshort}}-Service jetzt das quelloffene Worteinbettungsverfahren *GloVe*, um ein Persönlichkeitsprofil zu entwickeln. Der Service verwendet das psycholinguistische LIWC-Wörterbuch (Linguistic Inquiry and Word Count) für keine Sprache mehr. Weitere Informationen dazu, wie der Service ein Persönlichkeitsportrait entwickelt, finden Sie unter [Ableitung von Persönlichkeitsmerkmalen](/docs/services/personality-insights/science.html#researchInfer).

### 15. November 2016
{: #November2016}

**Serviceversion:** `3.1.0`<br/> **Schnittstellenversion:** `2016-10-19`

-   Für japanischen Eingabetext verwendet der {{site.data.keyword.personalityinsightsshort}}-Service jetzt das quelloffene Worteinbettungsverfahren *GloVe*, um ein Persönlichkeitsprofile zu entwickeln. Der Service verwendet das psycholinguistische LIWC-Wörterbuch (Linguistic Inquiry and Word Count) für japanische Eingaben nicht mehr. Weitere Informationen finden Sie unter [Ableitung von Persönlichkeitsmerkmalen](/docs/services/personality-insights/science.html#researchInfer).
-   Die Felder `name` der Objekte `ConsumptionPreferencesCategory` und `ConsumptionPreferences` werden jetzt mit lokalisierten Zeichenfolgen in der Sprache zurückgegeben, die im Anforderungsheader `Accept-Language` angegeben wurde.
-   Die Aktualisierung umfasst einige wenige kleine Fehlerkorrekturen.

### 20. Oktober 2016
{: #October2016b}

**Serviceversion:** `3.0.0`<br/> **Schnittstellenversion:** `2016-10-19`

Der {{site.data.keyword.personalityinsightsshort}}-Service und die zugehörige API wurden beträchtlich aktualisiert. Die API wurde von Version 2 auf Version 3 hochgestuft und stellt neue Funktionen bereit. In den übrigen Abschnitten dieser Releaseinformationen werden die Änderungen im Detail beschrieben.

Version 3 ist nicht abwärtskompatibel mit Version 2. Es wird empfohlen, auf Version 3 zu migrieren, um die Vorteile der neuen Funktionen und Änderungen zu nutzen. Die Migration auf Version 3 besteht nur in der Aktualisierung und erneuten Bereitstellung Ihrer Anwendungen, sodass sie die Änderungen verwenden, die in diesen Releaseinformationen für die neue Version beschrieben werden. Sie brauchen keine neue Instanz des Service in {{site.data.keyword.Bluemix_notm}} zu erstellen, sondern müssen lediglich die API `v3` aufrufen.

> **Anmerkung:** Version 2 der {{site.data.keyword.personalityinsightsshort}}-API wird in naher Zukunft aus dem Service entfernt. Daher wird ausdrücklich empfohlen, die Migration auf Version 3 möglichst bald durchzuführen. Zum gegenwärtigen Zeitpunkt können Sie auf Referenzliteratur für Version 2 über den Link [API-Referenz für Version 2 ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.ibm.com/watson/developercloud/personality-insights/api/v2/){: new_window} zugreifen. Darüber hinaus können Sie auch auf das interaktive Tool zum Testen von Aufrufen an Version 2 und zum Anzeigen von Live-Antworten aus dem Service über den Link [API-Explorer für Version 2 ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://watson-api-explorer.mybluemix.net/apis/personality-insights-v2){: new_window} zugreifen.

#### Weitere Informationen zu Version 3

Diese Dokumentation beschreibt jetzt Version 3 der {{site.data.keyword.personalityinsightsshort}}-API. In den folgenden Abschnitten werden die Änderungen für die neue Version der Schnittstelle zusammengefasst:

-   Informationen zum Aufrufen der Methode `/v3/profile` finden Sie unter [Profil anfordern](/docs/services/personality-insights/input.html).
-   Informationen zur Antwort der Methode `/v3/profile` finden Sie unter [JSON-Profil verstehen](/docs/services/personality-insights/output.html) und [CSV-Profil verstehen](/docs/services/personality-insights/output-csv.html).
-   Vollständige Informationen zur Schnittstelle der Version 3 finden Sie in der [API-Referenz ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}.

#### Änderungen an Parametern der Methode <code>/v3/profile</code>

Parameter der Methode `/v3/profile` wurden wie folgt geändert:

-   Die API stellt jetzt einen optionalen Abfrageparameter mit dem Namen `consumption_preferences` bereit. Der Parameter akzeptiert einen booleschen Wert, der angibt, ob die zu Verbraucherpräferenzen abgeleiteten Informationen zusammen mit den Ergebnissen zurückgegeben werden sollen. Die Informationen werden standardmäßig nicht in die Antwort eingeschlossen. Weitere Informationen finden Sie unter [Neue Funktion für Verbraucherpräferenzen](#cp).
-   Die API enthält jetzt einen erforderlichen Parameter mit dem Namen `version`. Der Parameter akzeptiert eine Zeichenfolge, die die angeforderte Version der API und das Antwortformat durch ein Datum der Form `JJJJ-MM-TT` angibt. Beispiel: Geben Sie `2016-10-19` für die Version vom 19. Oktober 2016 an. Dieser Parameter bietet dem Service die Möglichkeit, die API bzw. das Antwortformat für neue Versionen zu aktualisieren, ohne die Funktionsfähigkeit vorhandener Clients zu beeinträchtigen. Die erste Zeichenfolge für Version 3 der API ist `2016-10-19`.

    Das Datum, das Sie angeben, muss nicht exakt einer Version des Service entsprechen. Der Service verwendet die Version, die nicht später als das angegebene Datum freigegeben wurde. Wenn Sie ein Datum angeben, dass vor dem Releasedatum von Version 3 liegt, verwendet der Service Version 3 der API. Wenn Sie ein Datum angeben, das in der Zukunft liegt oder auf andere Weise nach dem Release der aktuellsten Version liegt, verwendet der Service die aktuellste Version.
-   Der Name des Abfrageparameters `include_raw` lautet jetzt `raw_scores`.
-   Der Name des Abfrageparameters `headers` lautet jetzt `csv_headers`.

#### Neue Funktion für Verbraucherpräferenzen
{: #cp}

Die Funktion für Verbraucherpräferenzen stellt einen Hinweis auf die Tendenz des Autors bereit, bestimmte Verbrauchergewohnheiten zu zeigen. Wenn Sie den Abfrageparameter `consumption_preferences` mit dem Wert `true` an die Methode `/v3/profile` übergeben, gibt der Service die folgenden zusätzlichen Ergebnisse mit dem Objekt `Profile` zurück:

-   Ein Feld `consumption_preferences`, das ein Array von Objekten `ConsumptionPreferencesCategory` enthält.
-   Jedes Objekt `ConsumptionPreferencesCategory` enthält die folgenden Felder:
    -   `consumption_preference_category_id`: Die ID einer der Kategorien von Verbraucherpräferenzen.
    -   `name`: Der für den Benutzer sichtbare Name der Kategorie.
    -   `consumption_preferences`: Ein Array von Objekten `ConsumptionPreferences`, das Ergebnisse enthält, die aus dem Eingabetext für die einzelnen Präferenzen der Kategorie abgeleitet wurden.
-   Jedes Objekt `ConsumptionPreferences` enthält die folgenden Felder:
    -   `consumption_preference_id`: Die ID einer der Verbraucherpräferenzen.
    -   `name`: Der für den Benutzer sichtbare Name der Verbraucherpräferenz.
    -   `score`: Die Bewertung für die Verbraucherpräferenz. Für viele Präferenzen bedeuten der Wert `0.0` unwahrscheinlich, der Wert `0.5` neutral und der Wert `1.0` wahrscheinlich. Die Bewertungen für einige Präferenzen sind binär und lassen keinen neutralen Wert zu. Die Bewertung ist ein Hinweis auf Präferenzen auf der Basis der Ergebnisse, die aus dem Eingabetext abgeleitet wurden, und kein normalisiertes Perzentil.

Weitere Informationen zu den Verbraucherpräferenzen finden Sie unter [Verbraucherpräferenzen](/docs/services/personality-insights/preferences.html).

> **Anmerkung:** Gegenwärtig wird das Feld `name` für beide Objekte für Verbraucherpräferenzen immer auf Englisch zurückgegeben, unabhängig von der Sprache, die im Anforderungsheader `Accept-Language` angegeben wurde.

#### Änderungen an JSON-Objekten und -Feldern

JSON-Objekte für Ein- und Ausgaben und die enthaltenen Felder wurden wie folgt einfacher und verständlicher gestaltet:

-   Die folgenden Felder wurden aus JSON-Objekten `ContentItem`, die mit einer Anforderung an die Methode `/v3/profile` übergeben werden können, entfernt:
    -   `userid`
    -   `sourceid`
    -   `charset` (zuvor veraltet)

    Sie übergeben diese Objekte im Hauptteil einer JSON-Anforderung als Elemente des Arrays `contentItems` des Objekts `Content`.
-   Die folgenden Felder des JSON-Objekts `Profile`, die von der Methode `/v3/profile` zurückgegeben werden, wurden geändert:
    -   Die folgenden Felder wurden entfernt:
        -   `id`
        -   `source`
    - Das Feld `tree` wurde entfernt. Es wurde durch vier neue Felder ersetzt:
        -   `personality` für Big Five-Persönlichkeitsmerkmale.
        -   `needs` für Bedürfnismerkmale.
        -   `values` für Wertmerkmale.
        -   `behavior` für zeitbezogene Ergebnisse zur Verteilung des Inhalts auf die Wochentage und Tagesstunden. Dieses Feld wird nur für JSON-Eingaben zurückgegeben, die Zeitmarken haben.

    Durch diese Änderung werden die Ergebnisse effektiv im JSON-Objekt `Profile` um eine Ebene höher versetzt, sodass eine Rekursionsebene entfällt.
    -   Der Name des Felds `processed_lang` lautet jetzt `processed_language`.
-   Die folgenden Felder von JSON-Objekten `Trait`, die von der Methode `/v3/profile` zurückgegeben werden, wurden umbenannt:
    -   Der Name des Felds `id` des JSON-Objekts `Trait` ist jetzt `trait_id`.
    -   Der Name des Felds `percentage` des JSON-Objekts `Trait` ist jetzt `percentile`.
-   Die folgenden Felder von JSON-Objekten `Trait`, die von der Methode `/v3/profile` zurückgegeben werden, wurden entfernt:
    -   `sampling_error`
    -   `raw_sampling_error`

    Der Service gibt jetzt einen durchschnittlichen mittleren absoluten Fehler (MAE) zurück, der die Genauigkeit der Ergebnisse qualifiziert. Weitere Informationen zum MAE für verschiedene Mengen an Eingabetext finden Sie unter [Ausreichende Eingabe bereitstellen](/docs/services/personality-insights/input.html#sufficient).
-   JSON-Objekte `Trait` werden weiterhin für die Felder `personality`, `needs` und `values` des Objekts `Profile` zurückgegeben. Jedoch gibt das Feld `behavior` ein Array von JSON-Objekten mit dem Namen `Behavior` zurück, die die folgenden Felder enthalten:
    -   `trait_id`
    -   `name`
    -   `category`
    -   `percentage`

    Außerdem werden die Verhaltensinformationen nicht mehr als Baumstruktur von Werten zurückgegeben. Die Ausgabe besteht aus einem einzelnen Array, in dem alle zeitbezogenen Merkmale (Wochentag und Tagesstunde) aufgelistet werden.
-   Der Name des Felds `id` des JSON-Objekts `Warnings`, das von der Methode `/v3/profile` zurückgegeben werden kann, ist jetzt `warnings_id`.

#### Änderungen an JSON-IDs
{: #ids}

Die JSON-IDs, die der Service für das Feld `trait_id` (früher `id`) des Objekts `Trait` und des neuen Objekts `Behavior` zurückgibt, wurden wie folgt geändert:

-   Die IDs für Big Five-Dimensionen beginnen jetzt mit der Zeichenfolge `big5_`.
-   Die IDs für Big Five-Facetten beginnen jetzt mit der Zeichenfolge `facet_`.
-   Die IDs für Bedürfnisse beginnen jetzt mit der Zeichenfolge `need_`.
-   Die IDs für Werte beginnen jetzt mit der Zeichenfolge `value_`.
-   Die IDs für alle zeitbezogenen Verhaltensmerkmale beginnen jetzt mit der Zeichenfolge `behavior_`.
-   Die IDs für zeitbezogene Verhaltensmerkmale für eine Tageszeit verwenden jetzt das 24-Stunden-Format (Beispiel: `behavior_0000`) und nicht mehr das 12-Stunden-Format (Beispiel: `0:00 am`).
-   Alle Buchstaben sind jetzt kleingeschrieben.
-   Leerzeichen und Bindestriche sind jetzt Unterstreichungszeichen.

#### Änderungen an CSV-Spaltenüberschriften
{: #headers}

Die optionalen Spaltenüberschriften, die der Service für CSV-Ausgaben zurückgeben kann, wurden wie folgt geändert:

-   Alle für das Feld `trait_id` der JSON-Ausgabe beschriebenen Änderungen gelten auch für CSV-Überschriften.
-   Die Überschriften für unaufbereitete Bewertungen für Big Five-Dimensionen beginnen jetzt mit der Zeichenfolge `big5_`.
-   Die Überschriften für unaufbereitete Bewertungen für Big Five-Facetten beginnen jetzt mit der Zeichenfolge `facet_`.
-   Die Überschriften für unaufbereitete Bewertungen für Bedürfnisse beginnen jetzt mit der Zeichenfolge `need_`.
-   Die Überschriften für unaufbereitete Bewertungen für Werte beginnen jetzt mit der Zeichenfolge `value_`.
-   Die Überschrift für die Spalte für die verarbeitete Sprache lautet jetzt `processed_language` und nicht `processed_lang`.
-   Die Spalten `user` und `source_id` werden nicht mehr zurückgegeben.
-   Alle Buchstaben sind jetzt kleingeschrieben.
-   Leerzeichen und Bindestriche sind jetzt Unterstreichungszeichen.

#### Entfernung der Methode <code>visualize</code>

Die Version 2 der API des Services enthielt eine veraltete Methode `visualize`, die in einem früheren Release zur Visualisierung der Ergebnisse eines Aufrufs der Methode `/v3/profile` verwendet wurde. Die Methode `visualize` wurde aus der API des Service entfernt. Der Service stellt weiterhin eine Gruppe von JavaScript-Dateien bereit, die eine grafische Darstellung eines Profils ermöglichen. Weitere Informationen finden Sie unter [Profil visualisieren](/docs/services/personality-insights/developer-overview.html#visualize).

### 12. Oktober 2016
{: #October2016a}

Für spanischen Eingabetext verwendet der {{site.data.keyword.personalityinsightsshort}}-Service jetzt das quelloffene Worteinbettungsverfahren *GloVe*, um ein Persönlichkeitsprofile zu entwickeln. Der Service verwendet das psycholinguistische LIWC-Wörterbuch (Linguistic Inquiry and Word Count) für spanische Eingaben nicht mehr. Der Service hat mit der Verwendung des neuen Modells für englischen Eingabetext am 31. August begonnen. Die Anwendung des Modells auf die übrigen Eingabesprachen erfolgt in naher Zukunft. Weitere Informationen zu dem neuen Modell finden Sie unter [Ableitung von Persönlichkeitsmerkmalen](/docs/services/personality-insights/science.html#researchInfer).

### 31. August 2016
{: #August2016}

Der {{site.data.keyword.personalityinsightsshort}}-Service verwendet jetzt das quelloffene Worteinbettungsverfahren *GloVe*, um ein Persönlichkeitsprofil zu entwickeln. Weitere Informationen finden Sie unter [Ableitung von Persönlichkeitsmerkmalen](/docs/services/personality-insights/science.html#researchInfer). Zum gegenwärtigen Zeitpunkt verwendet der Service das neue Verfahren nur für englischen Eingabetext. Für die anderen Sprachen verwendet der Service weiterhin das psycholinguistische LIWC-Wörterbuch (Linguistic Inquiry and Word Count). Zukünftige Versionen des Service werden das Verfahren mit dem offenen Vokabular für alle Sprachen verwenden.

Für das neue Modell, das für englische Eingaben verwendet wird, gibt der Service den durschnittlichen mittleren absoluten Fehler (Mean Absolute Error - MAE) der Ergebnisse für das zugehörige trainierte Modell zurück. Weitere Informationen dazu, wie sich der MAE mit verschiedenen Mengen an Eingabetext ändert, finden Sie unter [Ausreichende Eingabe bereitstellen](/docs/services/personality-insights/input.html#sufficient). Zukünftige Versionen des Service werden den MAE auch für Modelle anderer Sprachen (nicht Englisch) zurückgeben. Es wird empfohlen, diesen MAE und nicht die Stichprobenfehler zu verwenden, um zu bestimmen, wie sich die Genauigkeit des Service mit der Menge an Text, die Sie bereitstellen, ändert.

### 14. Juli 2016
{: #July2016b}

-   Für arabische Eingaben kann der Service jetzt die Menge an Eingabetext aus Leistungsgründen beschneiden. Ab einem bestimmten Schwellenwert verbessert sich die Genauigkeit der Ergebnisse für Arabisch mit mehr Wörtern nicht mehr. Wenn der Service arabischen Eingabetext abschneidet, wird eine Warnung `PARTIAL_TEXT_USED` mit der folgenden Nachricht zurückgegeben:

    `The text provided to compute the profile was trimmed for performance reasons. This action does not affect the accuracy of the output, as not all of the input text was required.`
-   Die Aktualisierung umfasst zusätzliche Fehlerkorrekturen und interne Verbesserungen.

### 1. Juli 2016
{: #July2016a}

-   Die Preistarife für den Service wurden geändert, um niedrigere Preise für {{site.data.keyword.personalityinsightsshort}}-Benutzer anzubieten. Weitere Informationen finden Sie unter [{{site.data.keyword.personalityinsightsshort}}-Service im {{site.data.keyword.Bluemix_short}}-Katalog ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://console.ng.bluemix.net/catalog/services/personality-insights/){: new_window}.
-   Die Liste der unterstützten Antwortsprachen, die Sie mit dem Header `Accept-Language` angeben können, enthält jetzt die folgenden Elemente:
    -   `ar` (Arabisch)
    -   `de` (Deutsch)
    -   `en` (Englisch, Standardsprache)
    -   `es` (Spanisch)
    -   `fr` (Französisch)
    -   `it` (Italienisch)
    -   `ja` (Japanisch)
    -   `ko` (Koreanisch)
    -   `pt-br` (Portugiesisch, Brasilien)
    -   `zh-cn` (vereinfachtes Chinesisch)
    -   `zh-tw` (traditionelles Chinesisch)

    Weitere Informationen finden Sie unter [Anforderungs- und Antwortsprache angeben](/docs/services/personality-insights/input.html#languages).
-   Die Methode `/v2/profile` kann jetzt die folgenden HTTP-Statuscodes zurückgeben:
    -   429 *Too Many Requests*: Der Service verarbeitet zurzeit zu viele Anforderungen für die Inhaltssprache. Warten Sie kurz und versuchen Sie die Anforderung erneut. Wenn Sie viele Anforderungen für die Sprache übergeben wollen, könnten Sie die Rate senken, mit der Sie Anforderungen übergeben.
    -   504 *Gateway Timeout*: Die Anforderung hat das Zeitlimit überschritten oder die Verarbeitung hat zu lang gedauert. Warten Sie kurz und versuchen Sie die Anforderung erneut. Wenn die Eingabe eine große Anzahl Wörter enthielt (z. B. über 20.000), ziehen Sie in Betracht, die Wortzahl unter Einhaltung der Richtlinien für sinnvolle Eingaben zu verringern.

    Die Methode gibt den Code 503 *Service Unavailable* nicht mehr zurück. Weitere Informationen zu möglichen Antwortcodes finden Sie in der [API-Referenz ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}.
-   Die Aktualisierung umfasst zusätzliche Fehlerkorrekturen und interne Verbesserungen.

### 7. Juni 2016
{: #June2016b}

-   Der Service unterstützt jetzt Cross-Origin Resource Sharing (CORS), sodass browserbasierte Clients den Service direkt aufrufen können. Weitere Informationen finden Sie unter [CORS-Unterstützung](/docs/services/personality-insights/developer-overview.html#CORS).
-   Die Leistung des Service bei der Verarbeitung von japanischem Text wurde erheblich verbessert.
-   Die Aktualisierung umfasst zusätzliche Fehlerkorrekturen und interne Verbesserungen.

### 1. Juni 2016
{: #June2016a}

Der {{site.data.keyword.personalityinsightsshort}}-Service wurde für Fehlerkorrekturen und interne Verbesserungen aktualisiert. Ein zusätzliches Feld `warnings` auf höchster Ebene wurde den JSON-Ergebnissen hinzugefügt, die von dem Service zurückgegeben werden. Weitere Informationen finden Sie in der [API-Referenz ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}.

### 17. Mai 2016
{: #May2016}

Der {{site.data.keyword.personalityinsightsshort}}-Service wurde für Fehlerkorrekturen und interne Verbesserungen aktualisiert.

### 18. März 2016
{: #March2016}

Der Service unterstützt jetzt die folgenden Sprachen:

-   Vier Sprachen für Eingabetext: Arabisch (`ar`), Englisch (`en`), Spanisch (`es`) und Japanisch (`ja`). Zur Angabe der Sprache verwenden Sie den HTTP-Header `Content-Language` für einfachen Text oder HTML-Eingabetext oder die Eigenschaft `language` des Objekts `ContentItem` für JSON-Eingaben.
-   Die gleichen vier Sprachen für die Antwort des Service. Zur Angabe der Sprache für die Antwort verwenden Sie den Header `Accept-Language`.

Sie können eine beliebige Kombination von Sprachen für die Eingabe und die Antwort verwenden. Für beide Sprachen gilt, wenn Sie keine Sprache angeben, verwendet der Service standardmäßig Englisch. Weitere Informationen finden Sie unter [ Anforderungs- und Antwortsprache angeben](/docs/services/personality-insights/input.html#languages). Weitere Informationen finden Sie außerdem im Blogbeitrag [Arabic and Japanese support is now available for {{site.data.keyword.IBM_notm}} {{site.data.keyword.watson}} {{site.data.keyword.personalityinsightsshort}} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.ibm.com/blogs/watson/2016/04/arabic-japanese-support-now-available-ibm-watson-personality-insights/){: new_window}.

> **Anmerkung:** Da die Analyse von Arabisch erheblich mehr Rechenzyklen als die anderer Sprachen, dauert die Verarbeitung von arabischem Inhalt deutlisch länger. Obwohl der Service für alle Sprachen die gleiche Beschränkung auf 20 MB für Eingabetext hat, kann das praktische Limit für arabischen Inhalt kleiner sein, um Zeitlimitüberschreitungen zu vermeiden. Die Verarbeitung von japanischem Inhalt dauert ebenfalls länger, jedoch sind die Verzögerungen im Vergleich zu Arabisch weniger signifikant.

### 9. Juli 2015
{: #July2015}

-   *Sprachunterstützung.* Der Service ermöglicht jetzt die Analyse von englischem und spanischem Inhalt. Sie geben die Sprache des Eingabetexts mit dem Header `Content-Language` der Methode `/v2/profile` an. Weitere Informationen zur Angabe einer Sprache finden Sie unter [Anforderungs- und Antwortsprache angeben](/docs/services/personality-insights/input.html#languages).
-   *Unaufbereitete Bewertungen.* Der Service ermöglicht jetzt die Anforderung von unaufbereiteten Bewertungen und unaufbereiteten Stichprobenfehlern, die aus dem Eingabetext und unter Verwendung der Modelle des Service berechnet werden. Die Werte werden nicht normalisiert und nicht mit einer Beispielpopulation verglichen. Unaufbereitete Bewertungen sind für Kunden nützlich, die eine angepasste Normalisierung für ein bestimmtes Szenario anwenden wollen oder die keinen Vergleich mit einer Beispielpopulation benötigen. Sie fordern unaufbereitete Bewertungen an, indem Sie den Abfrageparameter `include_raw` der Methode `/v2/profile` auf den Wert `true` setzen. Weitere Informationen finden Sie unter [Numerische Ergebnisse interpretieren](/docs/services/personality-insights/numeric.html).
-   *Modellverbesserungen.* Auf der Grundlage der neuesten Studien hat {{site.data.keyword.IBM_notm}} einige Verfahren zur Ableitung von Persönlichkeitsmerkmalen weiter verbessert. Die Änderungen sind für die Benutzer des Service transparent und machen frühere Ergebnisse, die durch den Service gewonnen wurden, nicht ungültig. Weitere Informationen zu den Studien und zum Ableitungsverfahren des Service finden Sie unter [Ableitung von Persönlichkeitsmerkmalen](/docs/services/personality-insights/science.html#researchInfer).

### 23. Februar 2015
{: #February2015}

Mit dem Stand vom 23. Februar 2015 ist der {{site.data.keyword.personalityinsightsshort}}-Service die allgemein verfügbare Version (GA-Version) des früheren User Modeling-Service, der als Betaversion verfügbar war. Das GA-Release setzt voraus, dass Benutzer auf eine Instanz des neues Service migrieren. Zwischen der Betaversion und der GA-Version des Service bestehen die folgenden Unterschiede.

-   Der {{site.data.keyword.personalityinsightsshort}}-Service ist abwärtskompatibel mit dem User Modeling-Service. Durch die Unterschiede, die in diesem Abschnitt beschrieben werden, verfügt der Service über mehr Flexibilität und bessere Ergebnisse, ohne aktuelle Anwendungen zu beeinträchtigen.
-   Die Parameter, mit denen Sie den Service in {{site.data.keyword.Bluemix_short}} erstellen, wurden geändert. Sie verwenden jetzt den Servicenamen `personality_insights` anstelle von `user_modeling` und den Serviceplan `"IBM Watson Personality Insights Monthly Plan"` anstelle von `user_modeling_free_plan`.
-   Die Methode `/v2/profile` akzeptiert zwei neue Eingabeformate. Der Header `Content-Type` akzeptiert jetzt das Eingabeformat für einfachen Text (`text/plain`), welches das Standardformat ist, und das HMTL-Eingabeformat (`text/html`) neben dem JSON-Format (`application/json`).
-   Die Methode `/v2/profile` gibt jetzt ein neues Ausgabeformat zurück. Der Header `Accept` akzeptiert jetzt das CSV-Ausgabeformat (`text/csv`) neben dem JSON-Ausgabeformat (`application/json`), welches das Standardformat ist.
-   Die Methode `/v2/profile` enthält jetzt das neue Ausgabeelement `sampling_error` für jedes Merkmal, für die ein Prozentwert zurückgegeben wird. Der Stichprobenfehler wird in Form eines Double-Werts zurückgegeben und gibt den Grad an Zuverlässigkeit an, den der Service für das Perzentil des Autors auf der Basis des Eingabetexts annimmt.
-   Das Modell für Bedürfnisse (Needs) nutzt eine verbesserte Zerlegung in Tokens und eine verbesserte Verarbeitung, um die Verteilung von Werten für die Merkmale besser zu normalisieren. Es wird empfohlen, alle Ergebnisse neu zu berechnen, die mit der User Modeling-API generiert wurden.
-   Die Methode `visualize` ist jetzt veraltet und wird in einem zukünftigen Release vollständig entfernt. Sie können die JavaScript-Datei `personality.js`, die mit der Beispielanwendung bereitgestellt wird, über den Client verwenden, um ähnliche Ergebnisse zu erhalten. Die JavaScript-Datei `textsummary.js` stellt zusätzliche Formatierungen für die Ergebnisse des Service bereit.
