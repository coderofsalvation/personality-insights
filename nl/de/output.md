---

copyright:
  years: 2015, 2017
lastupdated: "2017-10-28"

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

# JSON-Profil verstehen
{: #output}

Wenn Sie die Methode `POST /v3/profile` zur Analyse von Inhalten verwenden oder wenn Sie `application/json` mit dem Header `Accept` in einer Anforderung angeben, gibt der Service die Ergebnisse der Analyse standardmäßig als JSON-Objekt `Profile` zurück. Der Umfang der JSON-Ausgabe hängt davon ab, welche Parameter Sie mit der Anforderung angegeben haben, sowie davon, ob der Eingabetext Daten mit Zeitmarke darstellt, wie zum Beispiel ein Text, der einem Twitter-Feed zugeordnet ist.
{: shortdesc}

In den folgenden Abschnitten werden die Inhalte einer Antwort im JSON-Format beschrieben. Alle Beispielausgaben werden von der JSON-Beispieldatei <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="Symbol für externen Link" title="Symbol für externen Link" class="style-scope doc-content"></a> generiert, die im [Lernprogramm zur Einführung](/docs/services/personality-insights/getting-started.html) verwendet wird. Informationen zur CSV-Ausgabe finden Sie unter [CSV-Profil verstehen](/docs/services/personality-insights/output-csv.html).

## Objekt 'Profile'
{: #outputJSON}

Das Objekt `Profile` ist das JSON-Objekt der höchsten Ebene, das vom Service zurückgegeben wird. Das Objekt enthält die folgenden Felder:

-   `word_count` (Integer) gibt die Anzahl Wörter aus dem Eingabeinhalt an, die zum Generieren des Profils verwendet wurden. Diese kann kleiner als die Anzahl Wörter in der Eingabe sein, wenn die Anforderung einen sehr umfangreichen Inhalt übergeben hat. Wenn die Anzahl Wörter den Mindestschwellenwert nicht erfüllt, enthält die Ausgabe auch ein Feld `word_count_message` mit weiteren Anleitungen.
-   `processed language` (Zeichenfolge) beschreibt das Sprachmodell, mit dem der Service die Eingabe verarbeitet hat: `ar` (Arabisch), `en` (Englisch), `es` (Spanisch), `ja` (Japanisch) oder `ko` (Koreanisch).
-   `personality` ist ein rekursives Array mit Objekten `Trait`, das die Big Five-Dimensionen und -Facetten beschreibt, die aus dem Eingabetext abgeleitet wurden.
-   `needs` ist ein Array mit Objekten `Trait`, das die Bedürfnisse beschreibt, die aus dem Eingabetext abgeleitet wurden.
-   `values` ist ein Array mit Objekten `Trait`, das die Werte beschreibt, die aus dem Eingabetext abgeleitet wurden.
-   `behavior` ist ein Array mit Objekten `Behavior`, das die Verteilung des Inhalts über die Tage der Woche und die Stunden des Tages beschreibt. Der Service gibt das Feld nur für JSON-Eingaben zurück, die mit Zeitmarken versehen sind.
-   `consumption_preferences` ist ein Array mit Objekten `ConsumptionPreferencesCategory`, das Ergebnisse für jede Kategorie von Verbraucherpräferenzen bereitstellt. Die Elemente des Arrays enthalten Informationen für die einzelnen Präferenzen der jeweiligen Kategorie. Der Service gibt das Feld nur dann zurück, wenn der Abfrageparameter `consumption_preferences` der Anforderung auf `true` gesetzt wurde.
-   `warnings` ist ein Array mit Objekten `Warning`, das Nachrichten zum Eingabetext enthält. Das Array ist leer, wenn die Eingabe keine Warnungen verursacht hat.

### Beispielantwort
{: #JSONExample}

Die folgende Beispielausgabe zeigt die übergeordnete Struktur eines Objekts `Profile`. Die Ausgabe schließt immer die Felder `personality`, `needs` und `values` ein. Wenn die Eingabe aus Daten im JSON-Format mit Zeitmarke besteht, enthält die Antwort das Feld `behavior`. Wenn die Anforderung außerdem Verbraucherpräferenzen abfragt, enthält die Antwort das Feld `consumption_preferences`. In diesem Beispiel generiert die Eingabe keine Warnungen.

```javascript
{
  "word_count": 15223,
  "processed_language": "en",
  "personality": [
     . . .
  ],
  "needs": [
     . . .
  ],
  "values": [
     . . .
  ],
  "behavior": [
     . . .
  ],
  "consumption_preferences": [
     . . .
   ],
  "warnings": []
}
```
{: codeblock}

## Ausgabe von Persönlichkeitsmerkmalen
{: #traitJSON}

Das Objekt `Profile` enthält immer die Felder `personality`, `needs` und `values` für alle Typen von Eingaben. Jedes dieser Felder enthält ein Array von Objekten `Trait`, das die Persönlichkeitsmerkmale für die Attribute des betreffenden Merkmalstyps beschreibt. Für die Merkmale Bedürfnisse (Needs) und Werte (Values) hat das Array eine einzige Ebene, die die Merkmale beschreibt. Für die Big Five-Merkmale beschreibt ein Array auf der höchsten Ebene die Dimensionen und Arrays auf der zweiten Ebene beschreiben die Facetten der einzelnen Dimensionen.

-   `trait_id` (Zeichenfolge) ist die eindeutige ID des Merkmals, zu dem die Ergebnisse gehören:
    -   `big5_characteristic` für Big Five-Persönlichkeitsdimensionen
    -   `facet_characteristic` für Big Five-Persönlichkeitsfacetten
    -   `need_characteristic` für Bedürfnisse
    -   `value_characteristic` für Werte
-   `name` (Zeichenfolge) ist der für Benutzer sichtbare Name des Merkmals.
-   `category` (Zeichenfolge) ist die Kategorie des Merkmals:
    -   `personality` für Big Five-Persönlichkeitsmerkmale
    -   `needs` für Bedürfnisse
    -   `values` für Werte
-   `percentile` (Double) ist die Bewertung als normalisiertes Perzentil für das Merkmal. Weitere Informationen finden Sie unter [Perzentile für Persönlichkeitsmerkmale](/docs/services/personality-insights/numeric.html#percentiles).
-   `raw_score` (Double) ist die unaufbereitete Bewertung für das Merkmal. Das Feld wird nur zurückgegeben, wenn Sie unaufbereitete Bewertungen anfordern, indem Sie den Abfrageparameter `raw_scores` auf den Wert `true` setzen. Weitere Informationen finden Sie unter [Unaufbereitete Bewertungen für Persönlichkeitsmerkmale](/docs/services/personality-insights/numeric.html#rawScores).
-   `significant` (Boolesch) gibt an, ob das Merkmal für die Eingabesprache aussagefähig ist. Das Feld hat für alle Merkmale für Eingaben in Englisch, Spanisch und Japanisch immer den Wert `true`. Das Feld hat den Wert `false` für einen Teil der Merkmale für Eingaben in Arabisch und Koreanisch, für die die Modelle des Service keine aussagefähigen Ergebnisse generieren können. Weitere Informationen finden Sie unter [Einschränkungen für arabische und koreanische Eingaben](/docs/services/personality-insights/numeric.html#limitations).
-   `children` ist ein Array mit Objekten `Trait`, das weitere Detailergebnisse für die Facetten jeder Big Five-Dimension bereitstellt, wie sie aus dem Eingabetext abgeleitet werden. Das Array wird nur für Big Five-Dimensionen zurückgegeben.

### Beispielantwort
{: #traitExample}

Die folgende Beispielausgabe zeigt Ausschnitte der Ausgabe für Merkmale der Kategorien Big Five, Bedürfnisse und Werte. Wie beschrieben haben nur die Big Five-Merkmale ein Array `children` für die jeweils zugehörigen Facetten.

```javascript
{
  . . .
  "personality": [
    {
      "trait_id": "big5_openness",
      "name": "Openness",
      "category": "personality",
      "percentile": 0.8011555009553,
      "raw_score": 0.77565404255038,
      "significant": true,
      "children": [
        {
          "trait_id": "facet_adventurousness",
          "name": "Adventurousness",
          "category": "personality",
          "percentile": 0.89755869047319,
          "raw_score": 0.54990704031219,
          "significant": true
        },
        . . .
      ]
    },
    {
      "trait_id": "big5_conscientiousness",
      "name": "Conscientiousness",
      "category": "personality",
      "percentile": 0.81001753184176,
      "raw_score": 0.66899984888815,
      "significant": true,
      "children": [
        {
          "trait_id": "facet_achievement_striving",
          "name": "Achievement striving",
          "category": "personality",
          "percentile": 0.84613299226628,
          "raw_score": 0.74240118454888,
          "significant": true
        },
        . . .
      ]
    },
    {
      "trait_id": "big5_extraversion",
      "name": "Extraversion",
      "category": "personality",
      "percentile": 0.64980796071382,
      "raw_score": 0.56817738781166,
      "significant": true,
      "children": [
        {
          "trait_id": "facet_activity_level",
          "name": "Activity level",
          "category": "personality",
          "percentile": 0.88220584913965,
          "raw_score": 0.60106995926143,
          "significant": true
        },
      ]
    },
    {
      "trait_id": "big5_agreeableness",
      "name": "Agreeableness",
      "category": "personality",
      "percentile": 0.94786124793821,
      "raw_score": 0.80677815631809,
      "significant": true,
      "children": [
        {
          "trait_id": "facet_altruism",
          "name": "Altruism",
          "category": "personality",
          "percentile": 0.99241983824205,
          "raw_score": 0.79028406290747,
          "significant": true
        },
        . . .
      ]
    },
    {
      "trait_id": "big5_neuroticism",
      "name": "Emotional range",
      "category": "personality",
      "percentile": 0.5008224041628,
      "raw_score": 0.46748200007024,
      "significant": true,
      "children": [
        {
          "trait_id": "facet_anger",
          "name": "Fiery",
          "category": "personality",
          "percentile": 0.17640022058508,
          "raw_score": 0.48490315691802,
          "significant": true
        },
        . . .
      ]
    }
  ],
  "needs": [
    {
      "trait_id": "need_challenge",
      "name": "Challenge",
      "category": "needs",
      "percentile": 0.67362332054511,
      "raw_score": 0.75196348037675,
      "significant": true
    },
    . . .
  ],
  "values": [
    {
      "trait_id": "value_conservation",
      "name": "Conservation",
      "category": "values",
      "percentile": 0.89268222856139,
      "raw_score": 0.72135308187423,
      "significant": true
    },
    . . .
  ],
  . . .
}
```
{: codeblock}

## Ausgaben von Verhaltensmerkmalen
{: #behaviorJSON}

Wenn die Eingabe an den Service in Form von JSON-Daten erfolgt, die Zeitmarken für einzelne Inhaltselemente haben, enthält das Objekt `Profile` ein Feld `behavior`. Das Feld enthält ein Objekt `Behavior` für jeden Wochentag und jede Tageszeit.

-   `trait_id` (Zeichenfolge) ist die eindeutige ID des Merkmals, zu dem die Ergebnisse gehören:
    -   `behavior_day` für Wochentage (Beispiel: `behavior_sunday`).
    -   `behavior_hour` für Tagesstunden (Beispiel: `behavior_0000`).
-   `name` (Zeichenfolge) ist der für Benutzer sichtbare Name des Merkmals.
-   `category` (Zeichenfolge) ist die Kategorie des Merkmals. Hat immer den Wert `behavior`.
-   `percentage` (Double) ist der Prozentsatz der Inhaltselemente, die während dieses Wochentags bzw. dieser Tagesstunde aufgetreten sind. Weitere Informationen finden Sie unter [Prozentsätze für Verhaltensmerkmale](/docs/services/personality-insights/numeric.html#percentages).

### Beispielantwort
{: #behaviorExample}

Die folgende Ausgabe zeigt Ausschnitte der Ausgabe von Verhaltensmerkmalen für zeitlich zugeordnete Merkmale.

```javascript
{
  . . .
  "behavior": [
    {
      "trait_id": "behavior_sunday",
      "name": "Sunday",
      "category": "behavior",
      "percentage": 0.21392532795156
    },
    {
      "trait_id": "behavior_monday",
      "name": "Monday",
      "category": "behavior",
      "percentage": 0.42583249243189
    },
    . . .
    {
      "trait_id": "behavior_saturday",
      "name": "Saturday",
      "category": "behavior",
      "percentage": 0.077699293642785
    },
    {
      "trait_id": "behavior_0000",
      "name": "0:00 am",
      "category": "behavior",
      "percentage": 0.4561049445005
    },
    {
      "trait_id": "behavior_0100",
      "name": "1:00 am",
      "category": "behavior",
      "percentage": 0.12209889001009
    },
    . . .
    {
      "trait_id": "behavior_2300",
      "name": "11:00 pm",
      "category": "behavior",
      "percentage": 0.12310797174571
    }
  ],
  . . .
}
```
{: codeblock}

## Ausgabe für Verbraucherpräferenzen
{: #preferenceJSON}

Wenn der Abfrageparameter `consumption_preferences` auf den Wert `true` gesetzt wird, enthält das Objekt `Profile` ein Feld `consumption_preferences`. Das Feld enthält ein Objekt `ConsumptionPreferencesCategory` für jede Kategorie von Präferenzen.

-   `consumption_preference_category_id` (Zeichenfolge) ist die eindeutige ID der Kategorie von Verbraucherpräferenzen, zu der die Ergebnisse gehören, in der Form `consumption_preferences_{category}`.
-   `name` (Zeichenfolge) ist der für Benutzer sichtbare Name der Kategorie von Verbraucherpräferenzen.
-   `consumption_preferences` ist ein Array mit Objekten `ConsumptionPreferences`, das Ergebnisse für die einzelnen Präferenzen der Kategorie bereitstellt.

Jede einzelne Präferenz für eine Kategorie wird durch ein Objekt `ConsumptionPreferences` beschrieben. Einige Kategorien haben nur eine Präferenz, während andere mehrere Präferenzen enthalten.

-   `consumption_preference_id` (Zeichenfolge) ist die eindeutige ID der Verbraucherpräferenz, zu der die Ergebnisse gehören, in der Form `consumption_preferences_preference`.
-   `name` (Zeichenfolge) ist der für Benutzer sichtbare Name der Verbraucherpräferenz.
-   `score` (Double) ist eine Bewertung, die die Wahrscheinlichkeit angibt, mit der der Autor das Element bevorzugt. Weitere Informationen finden Sie unter [Bewertungen für Verbraucherpräferenzen](/docs/services/personality-insights/numeric.html#scores).

### Beispielantwort
{: #preferenceExample}

Die folgende Ausgabe zeigt Ausschnitte der Ausgabe für Verbraucherpräferenzen.

```javascript
{
  . . .
  "consumption_preferences": [
    {
      "consumption_preference_category_id": "consumption_preferences_shopping",
      "name": "Purchasing Preferences",
      "consumption_preferences": [
        {
          "consumption_preference_id": "consumption_preferences_automobile_ownership_cost",
          "name": "Likely to be sensitive to ownership cost when buying automobiles",
          "score": 0
        },
        . . .
      ]
    },
    {
      "consumption_preference_category_id": "consumption_preferences_health_and_activity",
      "name": "Health & Activity Preferences",
      "consumption_preferences": [
        {
          "consumption_preference_id": "consumption_preferences_eat_out",
          "name": "Likely to eat out frequently",
          "score": 1
        },
        . . .
      ]
    },
    . . .
    {
      "consumption_preference_category_id": "consumption_preferences_volunteering",
      "name": "Volunteering Preferences",
      "consumption_preferences": [
        {
          "consumption_preference_id": "consumption_preferences_volunteer",
          "name": "Likely to volunteer for social causes",
          "score": 0
        }
      ]
    }
  ],
  . . .
}
```
{: codeblock}
