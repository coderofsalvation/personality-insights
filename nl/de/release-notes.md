---

copyright:
  years: 2015, 2019
lastupdated: "2019-03-07"

subcollection: personality-insights

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

# Releaseinformationen
{: #release-notes}

In den folgenden Abschnitten sind die neuen Funktionen und Änderungen dokumentiert, die mit den einzelnen Releases des {{site.data.keyword.personalityinsightsshort}}-Service eingeführt wurden. Sofern nicht anders angegeben, sind alle Änderungen mit früheren (älteren) Versionen kompatibel und werden für alle neuen und vorhandenen Anwendungen automatisch und transparent verfügbar gemacht.
{: shortdesc}

In den Releaseinformationen werden die *Serviceversion* und die *Schnittstellenversion* für die letzten Aktualisierungen dokumentiert. Sie geben die *Schnittstellenversion* mit dem Abfrageparameter `version` ein, um die neuen Funktionen und die neue Funktionalität zu verwenden, die mit der jeweiligen Aktualisierung verfügbar gemacht werden. Der Service gibt beide Versionen mit dem Antwortheader `X-Service-Api-Version` zurück.
{: note}

## 21. Dezember 2018
{: #December2018}

**Serviceversion:** `3.4.5`<br/> **Schnittstellenversion:** `2017-10-13`

Version 2 der {{site.data.keyword.personalityinsightsshort}}-API wurde aus dem Service entfernt. Version 3 des Service wurde am 19. Oktober 2016 freigegeben. Zu diesem Zeitpunkt wurden die Benutzer eindringlich dazu aufgefordert, schnellstmöglich die Migration von Version 2 durchzuführen.

## 18. November 2018
{: #November2018b}

**Serviceversion:** `3.4.5`<br/> **Schnittstellenversion:** `2017-10-13`

Der {{site.data.keyword.personalityinsightsshort}}-Service ist nun am {{site.data.keyword.cloud}}-Standardort London (**eu-gb**) verfügbar. Wie alle Standorte verwendet auch London eine tokenbasierte Identitäts- und Zugriffsverwaltung (IAM). Alle neuen Serviceinstanzen, die Sie an diesem Standort erstellen, verwenden die IAM-Authentifizierung.

## 7. November 2018
{: #November2018a}

**Serviceversion:** `3.4.5`<br/> **Schnittstellenversion:** `2017-10-13`

Der {{site.data.keyword.personalityinsightsshort}}-Service ist nun am {{site.data.keyword.cloud_notm}}-Standardort Tokio (**jp-tok**) verfügbar. Wie alle Standorte verwendet auch Tokio eine tokenbasierte Identitäts- und Zugriffsverwaltung (IAM). Alle neuen Serviceinstanzen, die Sie an diesem Standort erstellen, verwenden die IAM-Authentifizierung.

## Frühere Releases
{: #older}

-   [30. Oktober 2018](#October2018)
-   [11. Juni 2018](#June2018b)
-   [4. Juni 2018](#June2018a)
-   [23. März 2018](#March2018)
-   [13. Oktober 2017](#October2017)
-   [18. September 2017](#September2017)
-   [10. April 2017](#April2017)
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

### 30. Oktober 2018
{: #October2018}

**Serviceversion:** `3.4.5`<br/> **Schnittstellenversion:** `2017-10-13`

Der {{site.data.keyword.personalityinsightsshort}}-Service wurde für alle Standorte auf tokenbasierte IAM-Authentifizierung migriert. Alle {{site.data.keyword.cloud_notm}}-Services verwenden jetzt die IAM-Authentifizierung. Der {{site.data.keyword.personalityinsightsshort}}-Service wurde an den einzelnen Standorten jeweils am folgenden Datum migriert: 

-   Dallas (**us-south**): 30. Oktober 2018
-   Frankfurt (**eu-de**): 30. Oktober 2018
-   Washington, D. C. (**us-east**): 11. Juni 2018
-   Sydney (**au-syd**): 4. Juni 2018

Die Migration zur IAM-Authentifizierung wirkt sich auf neue und auf bestehende Serviceinstanzen jeweils anders aus:

-   *Alle neuen Service-Instanzen, die Sie an einem beliebigen Standort erstellen,* verwenden nun die IAM-Authentifizierung für den Zugriff auf den Service. Sie können entweder ein Trägertoken oder einen API-Schlüssel übergeben: Token unterstützen authentifizierte Anfragen, ohne in jeden Aufruf Serviceberechtigungsnachweise einzubetten, und API-Schlüssel verwenden die HTTP-Basisauthentifizierung. Wenn Sie ein beliebiges {{site.data.keyword.watson}}-SDK verwenden, können Sie den API-Schlüssel übergeben und dem SDK die Verwaltung des Lebenszyklus der Token überlassen.
-   *Bestehende Serviceinstanzen, die Sie vor dem angegebenen Migrationsdatum an einem Standort erstellt haben,* verwenden für die Authentifizierung weiterhin die Anmeldeinformationen `{username}` und `{password}` aus ihren vorherigen Cloud Foundry-Serviceberechtigungsnachweisen, bis Sie sie so aktualisieren, dass sie die IAM-Authentifizierung verwenden. Da der {{site.data.keyword.personalityinsightsshort}}-Service statusunabhängig ist, können Sie eine vorhandene Serviceinstanz anhand der folgenden Schritte dazu bringen, dass sie die IAM-Authentifizierung verwendet:

    1.  Löschen Sie die Serviceinstanz und erstellen Sie sie erneut.
    1.  Ändern Sie Ihren Anwendungscode dergestalt, dass er IAM-Authentifizierung verwendet.

Weitere Informationen enthält die folgende Dokumentation:

-   Wenn Sie erfahren möchten, welchen Authentifizierungsmechanismus Ihre Serviceinstanz verwendet, prüfen Sie Ihre Serviceberechtigungsnachweise, indem Sie im [{{site.data.keyword.cloud_notm}}-Dashboard ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://{DomainName}/dashboard/apps){: new_window} auf die Serviceinstanz klicken.
-   Weitere Informationen zur Verwendung von IAM-Tokens mit Watson-Services enthält [Authentifizierung mit IAM-Tokens](/docs/services/watson?topic=watson-iam).
-   Weitere Informationen zur Verwendung von IAM-API-Schlüsseln mit Watson-Services enthält [API-Schlüssel des IAM-Service](/docs/services/watson?topic=watson-api-key-bp).
-   Beispiele für die Verwendung der IAM-Authentifizierung enthält die [API-Referenz ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://{DomainName}/apidocs/personality-insights){: new_window}.

### 11. Juni 2018
{: #June2018b}

**Serviceversion:** `3.4.5`<br/> **Schnittstellenversion:** `2017-10-13`

Für Serviceinstanzen und Anwendungen, die in Washington, D. C., (**us-east**) gehostet werden, unterstützt der Service nun einen neuen API-Authentifizierungsprozess. Weitere Informationen enthalten die Angaben zur [Serviceaktualisierung vom 30. Oktober 2018](#October2018).

### 4. Juni 2018
{: #June2018a}

**Serviceversion:** `3.4.5`<br/> **Schnittstellenversion:** `2017-10-13`

Für Serviceinstanzen und Anwendungen, die in Sydney (**au-syd**) gehostet werden, unterstützt der Service nun einen neuen API-Authentifizierungsprozess. Weitere Informationen enthalten die Angaben zur [Serviceaktualisierung vom 30. Oktober 2018](#October2018).

### 23. März 2018
{: #March2018}

**Serviceversion:** `3.4.4`<br/> **Schnittstellenversion:** `2017-10-13`

-   Der Service wurde mit kleinen Fehlerkorrekturen aktualisiert. Die Änderungen betrafen die arabische, die japanische und die koreanische Sprache.
-   Der Anforderungsheader `Accept` ist jetzt mit der Methode `POST /v3/profile` erforderlich. Sie müssen entweder `application/json` oder `text/csv` angeben.

### 13. Oktober 2017
{: #October2017}

**Serviceversion:** `3.4.0`<br/> **Schnittstellenversion:** `2017-10-13`

-   Das Objekt `Trait` (Charaktermerkmal) eines Persönlichkeitsprofils enthält jetzt ein Feld `significant`. Ein separates Objekt `Trait` gibt die Ergebnisse für jede Big Five-Dimension, jede Big Five-Facette, jedes Bedürfnis (Need) und jeden Wert (Value) zurück. Das Feld `significant` einer jeden Instanz des Objekts gibt an, ob die Ergebnisse für das Merkmal aussagekräftig für die Eingabesprache (`Content-Language`) der Anforderung sind:

    -   Für Englisch, Spanisch und Japanisch enthält das Feld stets den Wert `true` für alle Persönlichkeitsmerkmale.
    -   Für Arabisch und Koreanisch hat das Feld für einen Großteil der Persönlichkeitsmerkmale den Wert `true`, weist aber den Wert `false` für Merkmale auf, für die die Modelle des Service keine aussagefähigen Ergebnisse liefern können. Für eine konstante Gruppe von Merkmalen lautet der Wert für das Feld `false`. Eine vollständige Liste finden Sie unter [Einschränkungen für arabische und koreanische Eingaben](/docs/services/personality-insights?topic=personality-insights-numeric#limitations). Verlassen Sie sich nicht auf die Ergebnisse für ein Merkmal, für das das Feld den Wert `false` aufweist.

    Weitere Informationen zum JSON-Antwortinhalt des Service enthält [JSON-Profil verstehen](/docs/services/personality-insights?topic=personality-insights-output).
-   Die CSV-Ausgabe enthält jetzt ebenfalls Spalten, deren Überschriften das Format `*_significant` haben. Jede Spalte durch einen booleschen Wert an, ob ein Merkmal aussagekräftig ist. Weitere Informationen zum CSV-Antwortinhalt des Service enthält [CSV-Profil verstehen](/docs/services/personality-insights?topic=personality-insights-outputCSV).

-   Wenn Sie diese neueste Version der Schnittstelle verwenden möchten, geben Sie die Schnittstellenversion `2017-10-13` in Verbindung mit dem Parameter `version` an.

### 18. September 2017
{: #September2017}

**Serviceversion:** `3.3.0`<br/> **Schnittstellenversion:** `2016-10-19`

Der Service unterstützt jetzt Eingabeinhalte in Koreanisch (`ko`). Weitere Informationen zum durchschnittlichen mittleren absoluten Fehler (Mean Absolute Error - MAE) und zur durchschnittlichen Korrelation für koreanische Eingaben finden Sie in [Durchschnittlicher mittlerer absoluter Fehler und durchschnittliche Korrelation nach Sprache](/docs/services/personality-insights?topic=personality-insights-science#precisePerLanguage).

Die Modelle des Services können für einige wenige Persönlichkeitsmerkmale koreanischer Eingaben keine aussagefähigen Perzentile und unaufbereitete Bewertungen generieren. Weitere Informationen zu den Ergebnissen für diese Merkmale finden Sie unter [Einschränkungen für arabische und koreanische Eingaben](/docs/services/personality-insights?topic=personality-insights-numeric#limitations).

### 10. April 2017
{: #April2017}

**Serviceversion:** `3.1.7`<br/> **Schnittstellenversion:** `2016-10-19`

-   Die Art und Weise, in der der Service Anforderungen mit großen Mengen an Eingabeinhalt verarbeitet, wurde geändert. Der Service akzeptiert maximal 20 MB an Inhalt. Bei den Modellen, die auf *GloVe* basieren, stagniert die Genauigkeit ab einer Eingabe von etwa 3000 Wörtern. Dies Verhalten unterscheidet sich von den älteren Modellen, bei denen mehr Text zu Ergebnissen mit höherer Genauigkeit führte. Der Service benötigt allgemein nicht mehr so viel Inhalt, um ein präzises Profil generieren zu können. Mehr Inhalt erfordert jedoch mehr Verarbeitungszeit, was eine Anforderung für eine Zeitlimitüberschreitung bewirken kann, noch bevor die Verarbeitung abgeschlossen ist.

    Daher extrahiert und verarbeitet der Service aus umfangreichen Anforderungen jetzt nur die ersten 250 KB des Inhalts (HTML- oder JSON-Markup nicht mitgezählt). Diese Anzahl entspricht keiner exakten Wortzahl, die je nach Sprache und Spezifik des Texts variiert. In der englischen Sprache liegt die durchschnittliche Wortlänge zum Beispiel zwischen vier und fünf Buchstaben, sodass diese Zahl ungefähr 50.000 Wörtern entspricht, was 15-mal mehr Wörter sind, als der Service benötigt. Im Feld `word_count` der JSON-Antwort wird die Anzahl der Wörter angegeben, die der Service für eine Anforderung verwendet. Diese Anzahl kann kleiner als die Wortzahl in der Eingabe sein.

    Da der Service ein Profil immer noch auf wesentlich mehr Wörter stützt, als für maximale Genauigkeit eigentlich erforderlich sind, generiert er ein Profil, das so genau ist wie in der Vergangenheit. Allerdings antwortet der Service wesentlich schneller als zuvor. Für Anforderungen, für die nur ein Teil des Eingabeinhalts verwendet werden, gibt der Service die folgende Warnung `CONTENT_TRUNCATED` zurück, um den Benutzer über die Tatsache zu informieren:

    `For maximum accuracy while also optimizing processing time, only the first 250KB of input text (excluding markup) was analyzed. Accuracy levels off at approximately 3K words so this did not affect the accuracy of the profile.`

    Weitere Informationen finden Sie unter [Ausreichende Eingabe bereitstellen](/docs/services/personality-insights?topic=personality-insights-input#sufficient).
-   Der Service wurde mit kleinen Sicherheitskorrekturen aktualisiert.

### 1. März 2017
{: #March2017}

**Serviceversion:** `3.1.6`<br/> **Schnittstellenversion:** `2016-10-19`

Der Service wurde mit geringfügigen funktionalen Erweiterungen der Protokollierungsfunktion aktualisiert.

### 20. Februar 2017
{: #February2017b}

**Serviceversion:** `3.1.5.1`<br/> **Schnittstellenversion:** `2016-10-19`

Der Service wurde mit kleinen Sicherheits- und Fehlerkorrekturen sowie zur Verbesserung der Messung von API-Aufrufen aktualisiert.

### 13. Februar 2017
{: #February2017}

**Serviceversion:** `3.1.4`<br/> **Schnittstellenversion:** `2016-10-19`

-   Die Liste der Verbraucherpräferenzen wurde präzisiert. Die Liste enthält jetzt nur noch die Präferenzen, die für das Verständnis der dominierenden Lebensgewohnheiten und Verbrauchermerkmale einer Person von höchster Relevanz sind. Die Liste der Verbraucherpräferenzen wurde von 51 zu 42 gekürzt. Die übrigen Präferenzen drücken die Wahrscheinlichkeit des Autors, verschiedene Produkte, Services und Aktivitäten zu bevorzugen, noch prägnanter aus, wodurch es noch einfacher ist, auf der Grundlage der Ergebnisse tätig zu werden.

    Der Service gibt die folgenden neun Verbraucherpräferenzen nicht mehr zurück:

    -   Die Kategorie <code>consumption_preferences_shopping</code> enthält Folgendes nicht mehr:
        -   <code>consumption_preferences_automobile_resale_value</code>
    -   Die Kategorie <code>consumption_preferences_reading</code> enthält Folgendes nicht mehr:
        -   <code>consumption_preferences_read_motive_enjoyment</code><br/>
        -   <code>consumption_preferences_read_motive_information</code><br/>
        -   <code>consumption_preferences_read_motive_mandatory</code><br/>
        -   <code>consumption_preferences_read_motive_relaxation</code>
    -   Die Kategorie <code>consumption_preferences_health_and_activity</code> enthält Folgendes nicht mehr:
        -   <code>consumption_preferences_adventurous_sports</code>
        -   <code>consumption_preferences_fast_food_frequency</code>
    -   Die Kategorie <code>consumption_preferences_volunteering</code> enthält Folgendes nicht mehr:
        -   <code>consumption_preferences_volunteering_time</code>
        -   <code>consumption_preferences_volunteer_learning</code>

    Weitere Informationen zu den verbleibenden Präferenzen finden Sie unter [Verbraucherpräferenzen](/docs/services/personality-insights?topic=personality-insights-preferences).
-   *Für arabische Eingaben* sind jetzt Informationen zum durchschnittlichen mittlerer absoluter Fehler (Mean Absolute Error - MAE) und zur durchschnittlichen Korrelation unter [Durchschnittlicher mittlerer absoluter Fehler und durchschnittliche Korrelation nach Sprache](/docs/services/personality-insights?topic=personality-insights-science#precisePerLanguage) verfügbar. Darüber hinaus können die Modelle des Service für eine Reihe von Persönlichkeitsmerkmalen keine aussagefähigen Perzentile und unaufbereitete Bewertungen generieren. Weitere Informationen zu den Ergebnissen für diese Merkmale finden Sie unter [Einschränkungen für arabische und koreanische Eingaben](/docs/services/personality-insights?topic=personality-insights-numeric#limitations).

### 13. Januar 2017
{: #January2017}

**Serviceversion:** `3.1.2.1`<br/> **Schnittstellenversion:** `2016-10-19`

Der Personality Insights-Service wurde mit einigen Fehlerkorrekturen aktualisiert.

### 15. Dezember 2016
{: #December2016}

**Serviceversion:** `3.1.1`<br/> **Schnittstellenversion:** `2016-10-19`

Für arabischen Eingabetext verwendet der {{site.data.keyword.personalityinsightsshort}}-Service jetzt das quelloffene Worteinbettungsverfahren *GloVe* zum Entwickeln eines Persönlichkeitsprofils. Der Service verwendet das psycholinguistische LIWC-Wörterbuch (LIWC: Linguistic Inquiry and Word Count) für keine Sprache mehr. Weitere Informationen dazu, wie der Service ein Persönlichkeitsportrait entwickelt, finden Sie unter [Ableitung von Persönlichkeitsmerkmalen](/docs/services/personality-insights?topic=personality-insights-science#researchInfer).

### 15. November 2016
{: #November2016}

**Serviceversion:** `3.1.0`<br/> **Schnittstellenversion:** `2016-10-19`

-   Für japanischen Eingabetext verwendet der {{site.data.keyword.personalityinsightsshort}}-Service jetzt das quelloffene Worteinbettungsverfahren *GloVe* zum Entwickeln eines Persönlichkeitsprofils. Der Service verwendet das psycholinguistische LIWC-Wörterbuch (LIWC: Linguistic Inquiry and Word Count) nicht mehr Eingaben in japanischer Sprache. Weitere Informationen finden Sie unter [Ableitung von Persönlichkeitsmerkmalen](/docs/services/personality-insights?topic=personality-insights-science#researchInfer).
-   Die Felder `name` der Objekte `ConsumptionPreferencesCategory` und `ConsumptionPreferences` werden jetzt mit lokalisierten Zeichenfolgen in der Sprache zurückgegeben, die im Anforderungsheader `Accept-Language` angegeben ist.
-   Die Aktualisierung umfasst einige wenige kleine Fehlerkorrekturen.

### 20. Oktober 2016
{: #October2016b}

**Serviceversion:** `3.0.0`<br/> **Schnittstellenversion:** `2016-10-19`

Der {{site.data.keyword.personalityinsightsshort}}-Service und die zugehörige API wurden beträchtlich aktualisiert. Die API wurde von Version 2 auf Version 3 hochgestuft und stellt neue Funktionen bereit. In den übrigen Abschnitten dieser Releaseinformationen werden die Änderungen im Detail beschrieben.

Version 3 ist nicht kompatibel mit Version 2. Sie werden aufgefordert, die Migration auf Version 3 durchzuführen, um die neuen Funktionen und Änderungen voll ausschöpfen zu können. Die Migration auf Version 3 besteht nur aus der Aktualisierung und erneuten Bereitstellung Ihrer Anwendungen, sodass diese die Änderungen verwenden, die in diesen Releaseinformationen für die neue Version beschrieben werden. Sie brauchen keine neue Instanz des Service in {{site.data.keyword.cloud_notm}} zu erstellen, sondern müssen lediglich die `v3`-API aufrufen.

Version 2 der {{site.data.keyword.personalityinsightsshort}}-API wird in Kürze aus dem Service entfernt. Daher wird ausdrücklich empfohlen, die Migration auf Version 3 möglichst bald durchzuführen.
{: note}

#### Weitere Informationen zu Version 3

Diese Dokumentation beschreibt jetzt Version 3 der {{site.data.keyword.personalityinsightsshort}}-API. In den folgenden Abschnitten werden die Änderungen für die neue Version der Schnittstelle zusammengefasst:

-   Weitere Informationen zum Aufrufen der Methode `/v3/profile` finden Sie in [Profil anfordern](/docs/services/personality-insights?topic=personality-insights-input).
-   Weitere Informationen zu der Antwort der Methode `/v3/profile` finden Sie in [JSON-Profil verstehen](/docs/services/personality-insights?topic=personality-insights-output) und in [CSV-Profil verstehen](/docs/services/personality-insights?topic=personality-insights-outputCSV).
-   Weitere Informationen zur Schnittstelle von Version 3 enthält die [API-Referenz ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://{DomainName}/apidocs/personality-insights){: new_window}.

#### Änderungen an Parametern der Methode <code>/v3/profile</code>

Die Parameter der Methode `/v3/profile` haben sich wie folgt geändert:

-   Die API stellt jetzt einen optionalen Abfrageparameter mit dem Namen `consumption_preferences` bereit. Der Parameter akzeptiert einen booleschen Wert, der angibt, ob die zu Verbraucherpräferenzen erschlossenen Informationen zusammen mit den Ergebnissen zurückgegeben werden sollen. Die Informationen werden standardmäßig nicht in die Antwort eingeschlossen. Weitere Informationen finden Sie unter [Neue Funktion für Verbraucherpräferenzen](#cp).
-   Die API enthält jetzt einen erforderlichen Abfrageparameter `version`. Der Parameter akzeptiert eine Zeichenfolge, die die angeforderte Version der API und das Antwortformat durch ein Datum der Form `JJJJ-MM-TT` angibt. Beispiel: Geben Sie `2016-10-19` für die Version vom 19. Oktober 2016 an. Dieser Parameter bietet dem Service die Möglichkeit, die API bzw. das Antwortformat für neue Versionen zu aktualisieren, ohne die Funktionsfähigkeit vorhandener Clients zu beeinträchtigen. Die erste Zeichenfolge für Version 3 der API ist `2016-10-19`.

    Das Datum, das Sie angeben, muss der Version des Service nicht exakt entsprechen. Der Service verwendet die Version, die nicht später als an dem angegebenen Datum freigegeben wurde. Wenn Sie ein Datum angeben, dass vor dem Releasedatum von Version 3 liegt, verwendet der Service Version 3 der API. Wenn Sie ein Datum angeben, das in der Zukunft liegt oder auf andere Weise nach dem Release der aktuellsten Version liegt, verwendet der Service die aktuellste Version.
-   Der Name des Abfrageparameters `include_raw` lautet jetzt `raw_scores`.
-   Der Name des Abfrageparameters `headers` lautet jetzt `csv_headers`.

#### Neue Funktion für Verbraucherpräferenzen
{: #cp}

Die Funktion für Verbraucherpräferenzen stellt einen Hinweis auf die Tendenz des Autors bereit, bestimmte Verbrauchergewohnheiten zu zeigen. Wenn Sie den Abfrageparameter `consumption_preferences` mit dem Wert `true` an die Methode `/v3/profile` übergeben, gibt der Service zusätzliche Ergebnisse mit dem Objekt `Profile` zurück:

-   Ein Feld `consumption_preferences`, das ein Array von Objekten `ConsumptionPreferencesCategory` enthält.
-   Jedes Objekt `ConsumptionPreferencesCategory` enthält die folgenden Felder:
    -   `consumption_preference_category_id`: Die ID einer der Kategorien von Verbraucherpräferenzen.
    -   `name`: Der für den Benutzer sichtbare Name der Kategorie.
    -   `consumption_preferences`: Ein Array mit Objekten vom Typ `ConsumptionPreferences`, das Ergebnisse liefert, die aus dem Eingabetext für die einzelnen Präferenzen der Kategorie abgeleitet wurden.
-   Jedes Objekt `ConsumptionPreferences` enthält die folgenden Felder:
    -   `consumption_preference_id`: Die ID einer der Verbraucherpräferenzen.
    -   `name`: Der für den Benutzer sichtbare Name der Verbraucherpräferenz.
    -   `score`: Die Bewertung der Verbraucherpräferenzen:

        -   `0,0` gibt eine geringe Wahrscheinlichkeit an
        -   `0,5` gibt Neutralität an
        -   `1.0` gibt eine hohe Wahrscheinlichkeit an

        Die Bewertungen für einige Präferenzen sind binär und lassen keinen neutralen Wert zu. Die Bewertung ist ein Hinweis auf Präferenzen auf der Basis der Ergebnisse, die aus dem Eingabetext erschlossen wurden, und kein normalisiertes Perzentil.

Weitere Informationen zu den Verbraucherpräferenzen finden Sie unter [Verbraucherpräferenzen](/docs/services/personality-insights?topic=personality-insights-preferences).

Das Feld `name` wird für beide Objekte für Verbraucherpräferenzen stets auf Englisch zurückgegeben, unabhängig von der Sprache, die im Anforderungsheader `Accept-Language` angegeben wurde.
{: note}

#### Änderungen an JSON-Objekten und -Feldern

JSON-Objekte für Ein- und Ausgaben und ihre Felder wurden einfacher und verständlicher gestaltet:

-   Die folgenden Felder wurden aus JSON-Objekten vom Typ `ContentItem`, die mit einer Anforderung an die Methode `/v3/profile` übergeben werden können, entfernt:
    -   `userid`
    -   `sourceid`
    -   `charset` (zuvor veraltet)

    Sie übergeben diese Objekte im Hauptteil einer JSON-Anforderung als Elemente des Arrays `contentItems` des Objekts `Content`.
-   Die folgenden Felder des JSON-Objekts `Profile`, das von der Methode `/v3/profile` zurückgegeben wird, haben sich geändert:
    -   Die folgenden Felder wurden entfernt:
        -   `id`
        -   `source`
    -   Das Feld `tree` wurde entfernt. Es wurde durch vier neue Felder ersetzt:
        -   `personality` für Big Five-Persönlichkeitsmerkmale.
        -   `needs` für Bedürfnismerkmale.
        -   `values` für Wertmerkmale.
        -   `behavior` für zeitbezogene Ergebnisse zur Verteilung des Inhalts auf die Wochentage und Tagesstunden. Dieses Feld wird nur für JSON-Eingaben zurückgegeben, die Zeitmarken haben.

        Durch diese Änderung werden die Ergebnisse effektiv im JSON-Objekt `Profile` um eine Ebene höher versetzt, sodass eine Rekursionsebene entfällt.
    -   Der Name des Felds `processed_lang` lautet jetzt `processed_language`.
-   Die folgenden Felder von JSON-Objekten vom Typ `Trait`, die von der Methode `/v3/profile` zurückgegeben werden, wurden umbenannt:
    -   Der Name des Felds `id` des JSON-Objekts `Trait` ist jetzt `trait_id`.
    -   Der Name des Felds `percentage` des JSON-Objekts `Trait` ist jetzt `percentile`.
-   Die folgenden Felder von JSON-Objekten vom Typ `Trait`, die von der Methode `/v3/profile` zurückgegeben werden, wurden entfernt:
    -   `sampling_error`
    -   `raw_sampling_error`

    Der Service gibt jetzt einen durchschnittlichen mittleren absoluten Fehler (MAE) zurück, der die Genauigkeit der Ergebnisse qualifiziert. Weitere Informationen zum MAE für verschiedene Mengen an Eingabetext finden Sie unter [Ausreichende Eingabe bereitstellen](/docs/services/personality-insights?topic=personality-insights-input#sufficient).
-   JSON-Objekte `Trait` werden weiterhin für die Felder `personality`, `needs` und `values` des Objekts `Profile` zurückgegeben. Jedoch gibt das Feld `behavior` ein Array von JSON-Objekten mit dem Namen `Behavior` zurück, das die folgenden Felder enthält:
    -   `trait_id`
    -   `name`
    -   `category`
    -   `percentage`

    Außerdem werden die Verhaltensinformationen nicht mehr als Baumstruktur von Werten zurückgegeben. Die Ausgabe besteht aus einem einzelnen Array, in dem alle zeitbezogenen Merkmale (Wochentag und Tagesstunde) aufgelistet werden.
-   Der Name des Felds `id` des JSON-Objekts `Warnings`, das von der Methode `/v3/profile` zurückgegeben werden kann, ist jetzt `warnings_id`.

#### Änderungen an JSON-IDs
{: #ids}

Bei den JSON-IDs, die der Service für das Feld `trait_id` (früher `id`) des Objekts `Trait` und des neuen Objekts `Behavior` zurückgibt, sind die folgenden Änderungen aufgetreten:

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

Die optionalen Spaltenüberschriften, die der Service für CSV-Ausgaben zurückgeben kann, haben sich wie folgt geändert:

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

Die Version 2 der API des Services enthielt eine veraltete Methode `visualize`, die in einem früheren Release zur Visualisierung der Ergebnisse eines Aufrufs der Methode `/v3/profile` verwendet wurde. Die Methode `visualize` wurde aus der API des Service entfernt. Der Service stellt auch weiterhin eine Gruppe von JavaScript-Dateien bereit, die die grafische Darstellung eines Profils ermöglichen. Weitere Informationen enthält der Abschnitt [Profil visualisieren](/docs/services/personality-insights?topic=personality-insights-overviewDevelopers#visualize).

### 12. Oktober 2016
{: #October2016a}

Für spanischen Eingabetext verwendet der {{site.data.keyword.personalityinsightsshort}}-Service jetzt das quelloffene Worteinbettungsverfahren *GloVe* zum Entwickeln eines Persönlichkeitsprofils. Der Service verwendet das psycholinguistische LIWC-Wörterbuch (LIWC: Linguistic Inquiry and Word Count) nicht mehr für Eingaben in spanischer Sprache. Der Service hat mit der Verwendung des neuen Modells für englischen Eingabetext am 31. August begonnen. Es ist geplant, das neue Modell in Kürze auf die verbleibenden Eingabesprachen anzuwenden. Weitere Informationen zu dem neuen Modell finden Sie unter [Ableitung von Persönlichkeitsmerkmalen](/docs/services/personality-insights?topic=personality-insights-science#researchInfer).

### 31. August 2016
{: #August2016}

Der Service verwendet jetzt *GloVe* zum Entwickeln eines Persönlichkeitsprofils. *GloVe* ist ein quelloffenes Worteinbettungsverfahren. Weitere Informationen finden Sie unter [Ableitung von Persönlichkeitsmerkmalen](/docs/services/personality-insights?topic=personality-insights-science#researchInfer). Der Service verwendet den neuen Ansatz nur für englischen Eingabetext. Für andere Sprachen verwendet der Service weiterhin das LIWC-Wörterbuch (Linguistic Inquiry and Word Count) der Psycholinguistik. Es ist vorgesehen, dass der Service in Zukunft für alle Sprachen den Ansatz des offen konzipierten Wortschatzes nutzt.

Für das neue Modell, das für englische Eingaben verwendet wird, gibt der Service den durchschnittlichen mittleren absoluten Fehler (Mean Absolute Error - MAE) der Ergebnisse für das zugehörige trainierte Modell zurück. Weitere Informationen dazu, wie sich der MAE bei unterschiedlichen Mengen an Eingabetext ändert, erfahren Sie in [Ausreichende Eingabe bereitstellen](/docs/services/personality-insights?topic=personality-insights-input#sufficient).

{{site.data.keyword.IBM_notm}} beabsichtigt, künftig den MAE auch für Modelle anderer Sprachen als Englisch zurückzugeben. {{site.data.keyword.IBM_notm}} plant, an Stelle der Stichprobenfehler den MAE zu verwenden, um zu bestimmen, wie sich die Genauigkeit des Service mit der bereitgestellten Menge an Eingabetext ändert.

### 14. Juli 2016
{: #July2016b}

-   Für arabische Eingaben kann der Service jetzt die Menge an Eingabetext aus Leistungsgründen beschneiden. Ab einem bestimmten Schwellenwert verbessert sich die Genauigkeit der Ergebnisse für Arabisch mit mehr Wörtern nicht mehr. Wenn der Service arabischen Eingabetext abschneidet, wird eine Warnung `PARTIAL_TEXT_USED` mit der folgenden Nachricht zurückgegeben:

    `The text provided to compute the profile was trimmed for performance reasons. This action does not affect the accuracy of the output, as not all of the input text was required.`
-   Die Aktualisierung umfasst Fehlerkorrekturen und interne Verbesserungen.

### 1. Juli 2016
{: #July2016a}

-   Die Preistarife für den Service bieten {{site.data.keyword.personalityinsightsshort}}-Benutzern jetzt niedrigere Preise. Weitere Informationen finden Sie unter {{site.data.keyword.personalityinsightsshort}}-Service im [{{site.data.keyword.cloud_notm}}-Katalog ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://{DomainName}/catalog/services/personality-insights/){: new_window}.
-   Die Liste der unterstützten Antwortsprachen, die Sie mit dem Header `Accept-Language` angeben können, enthält jetzt folgende Sprachen:
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

Weitere Informationen finden Sie unter [Anforderungs- und Antwortsprache angeben](/docs/services/personality-insights?topic=personality-insights-input#languages-input).
-   Die Methode `/v2/profile` kann jetzt die folgenden HTTP-Statuscodes zurückgeben:
    -   429 *Too Many Requests*: Der Service verarbeitet zu viele Anforderungen für die Inhaltssprache. Warten Sie kurz und wiederholen Sie die Anforderung. Wenn Sie viele Anforderungen für die Sprache übergeben wollen, könnten Sie die Rate senken, mit der Sie Anforderungen übergeben.
    -   504 *Gateway Timeout*: Die Anforderung hat das Zeitlimit überschritten oder die Verarbeitung hat zu lang gedauert. Warten Sie kurz und versuchen Sie die Anforderung erneut. Wenn die Eingabe eine zu große Wortzahl enthielt (z. B. über 20.000), sollten Sie überlegen, die Wortzahl unter Einhaltung der Richtlinien für sinnvolle Eingaben zu reduzieren.

    Die Methode gibt den Code 503 *Service Unavailable* nicht mehr zurück. Weitere Informationen zu möglichen Antwortcodes finden Sie in der [API-Referenz ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://{DomainName}/apidocs/personality-insights){: new_window}.
-   Die Aktualisierung umfasst Fehlerkorrekturen und interne Verbesserungen.

### 7. Juni 2016
{: #June2016b}

-   Der Service unterstützt jetzt Cross-Origin Resource Sharing (CORS), sodass browserbasierte Clients den Service direkt aufrufen können. Weitere Informationen finden Sie unter [CORS-Unterstützung](/docs/services/personality-insights?topic=personality-insights-overviewDevelopers#CORS).
-   Die Leistung des Service für japanischen Text hat sich erheblich verbessert.
-   Die Aktualisierung umfasst Fehlerkorrekturen und interne Verbesserungen.

### 1. Juni 2016
{: #June2016a}

Der Service wurde mit Fehlerkorrekturen und internen Verbesserungen aktualisiert. Zu den JSON-Ergebnissen, die vom Service zurückgegeben werden, wurde ein neues Element der obersten Ebene namens `warnings` hinzugefügt. Weitere Informationen finden Sie in der the [API-Referenz ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://{DomainName}/apidocs/personality-insights){: new_window}.

### 17. Mai 2016
{: #May2016}

Der Service wurde mit Fehlerkorrekturen und internen Verbesserungen aktualisiert. 

### 18. März 2016
{: #March2016}

Der Service unterstützt jetzt die folgenden Sprachen:

-   Der Service unterstützt vier Sprachen für Eingabetext: Arabisch (`ar`), Englisch (`en`), Spanisch (`es`) und Japanisch (`ja`). Zur Angabe der Sprache verwenden Sie den HTTP-Header `Content-Language` für einfachen Text oder HTML-Eingabetext oder die Eigenschaft `language` des Objekts `ContentItem` für JSON-Eingaben.
-   Der Service unterstützt dieselben vier Sprachen für seine Antwort. Zur Angabe der Sprache für die Antwort verwenden Sie den Header `Accept-Language`.

Sie können eine beliebige Kombination von Sprachen für die Eingabe und die Antwort verwenden. Wenn Sie keine Sprache angeben, verwendet der Service standardmäßig die englische Sprache. Weitere Informationen finden Sie unter [ Anforderungs- und Antwortsprache angeben](/docs/services/personality-insights?topic=personality-insights-input#languages-input). Lesen Sie auch den Blogbeitrag [Arabic and Japanese support is now available for {{site.data.keyword.IBM_notm}} {{site.data.keyword.watson}} {{site.data.keyword.personalityinsightsshort}} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://www.ibm.com/blogs/watson/2016/04/arabic-japanese-support-now-available-ibm-watson-personality-insights/){: new_window}.

Da die Analyse von Arabisch erheblich mehr Rechenzyklen erfordert als die anderer Sprachen, dauert die Verarbeitung von arabischem Inhalt beträchtlich länger. Der Service unterstützt zwar für alle Sprachen dieselbe Beschränkung von 20 MB für Eingabetext, doch die praktische Grenze für arabische Inhalte könnte niedriger sein, um Zeitlimitüberschreitungen zu vermeiden. Die Verarbeitung von japanischem Inhalt dauert ebenfalls länger, jedoch sind die Verzögerungen im Vergleich zu Arabisch weniger signifikant.
{: note}

### 9. Juli 2015
{: #July2015}

-   *Sprachunterstützung.* Es kann sowohl englischer als auch spanischer Inhalt analysiert werden. Sie geben die Sprache des Eingabetexts mit dem Header `Content-Language` der Methode `/v2/profile` an. Weitere Informationen zur Angabe einer Sprache enthält [Anforderungs- und Antwortsprache angeben](/docs/services/personality-insights?topic=personality-insights-input#languages-input).
-   *Unaufbereitete Bewertungen.* Sie können unaufbereitete Bewertungen und unaufbereitete Stichprobenfehler anfordern, die unter Verwendung des Eingabetexts und der Modelle des Service berechnet werden. Die Werte werden nicht normalisiert und nicht mit einer Beispielpopulation verglichen. Unaufbereitete Bewertungen sind für Kunden nützlich, die eine angepasste Normalisierung für ein bestimmtes Szenario anwenden wollen oder die keinen Vergleich mit einer Beispielpopulation benötigen. Sie fordern unaufbereitete Bewertungen an, indem Sie für den Abfrageparameter `include_raw` der Methode `/v2/profile` den Wert `true` festlegen. Weitere Informationen finden Sie unter [Numerische Ergebnisse interpretieren](/docs/services/personality-insights?topic=personality-insights-numeric).
-   *Modellverbesserungen.* Auf der Grundlage der neuesten Studien hat {{site.data.keyword.IBM_notm}} einige Verfahren zur Ableitung von Persönlichkeitsmerkmalen weiter verbessert. Die Änderungen sind für die Benutzer des Service transparent; sie machen frühere Ergebnisse, die durch den Service gewonnen wurden, nicht ungültig. Weitere Informationen zu den Studien und zum Ableitungsverfahren des Service finden Sie unter [Ableitung von Persönlichkeitsmerkmalen](/docs/services/personality-insights?topic=personality-insights-science#researchInfer).

### 23. Februar 2015
{: #February2015}

Mit dem Stand vom 23. Februar 2015 ist der {{site.data.keyword.personalityinsightsshort}}-Service die allgemein verfügbare Version (GA-Version) des früheren User Modeling-Service, der als Betaversion verfügbar war. Das GA-Release setzt voraus, dass Benutzer auf eine Instanz des neues Service migrieren. Zwischen der Betaversion und der GA-Version des Service bestehen die folgenden Unterschiede.

-   Der {{site.data.keyword.personalityinsightsshort}}-Service ist mit dem User Modeling-Service kompatibel. Durch die beschriebenen Unterschiede bietet der Service mehr Flexibilität und verbesserte Ergebnisse, ohne aktuelle Anwendungen zu beeinträchtigen.
-   Die Parameter, mit denen Sie den Service in {{site.data.keyword.cloud_notm}} erstellen, haben sich geändert. Sie verwenden jetzt den Servicenamen `personality_insights` anstelle von `user_modeling` und den Serviceplan `"IBM Watson Personality Insights Monthly Plan"` anstelle von `user_modeling_free_plan`.
-   Die Methode `/v2/profile` akzeptiert zwei neue Eingabeformate. Der Header `Content-Type` akzeptiert jetzt das Eingabeformat für einfachen Text (`text/plain`), welches das Standardformat ist, und das HMTL-Eingabeformat (`text/html`) neben dem JSON-Format (`application/json`).
-   Die Methode `/v2/profile` gibt jetzt ein neues Ausgabeformat zurück. Der Header `Accept` akzeptiert jetzt das CSV-Ausgabeformat (`text/csv`) neben dem JSON-Ausgabeformat (`application/json`), welches das Standardformat ist.
-   Die Methode `/v2/profile` enthält jetzt das neue Ausgabeelement `sampling_error` für jedes Merkmal, für die ein Prozentwert zurückgegeben wird. Der Stichprobenfehler wird in Form eines Double-Werts zurückgegeben und gibt den Grad an Zuverlässigkeit an, den der Service für das Perzentil des Autors auf der Basis des Eingabetexts annimmt.
-   Das Modell für Bedürfnisse (Needs) nutzt eine verbesserte Zerlegung in Tokens und eine verbesserte Verarbeitung, um die Verteilung von Werten für die Merkmale besser zu normalisieren. Es wird empfohlen, alle Ergebnisse neu zu berechnen, die mit der User Modeling-API generiert wurden.
-   Die Methode `visualize` ist jetzt veraltet und wird in einem zukünftigen Release vollständig entfernt. Sie können die JavaScript-Datei `personality.js`, die mit der Beispielanwendung bereitgestellt wird, über den Client verwenden, um ähnliche Ergebnisse zu erhalten. Über die JavaScript-Datei `textsummary.js` werden zusätzliche Formatierungen für die Ergebnisse des Service bereitgestellt.
