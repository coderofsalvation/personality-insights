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

# CSV-Profil verstehen
{: #outputCSV}

Der Service gibt die Ergebnisse der Analyse im CSV-Format (mit durch Kommas getrennten Werten) zurück, wenn Sie `text/csv` mit dem Header `Accept` einer Anforderung angeben. Die CSV-Ausgabe stellt Informationen bereit, die den Informationen der JSON-Ausgabe ähnlich sind. Wie bei JSON richten sich die Informationen in der CSV-Ausgabe danach, ob die Eingabedaten mit einem Zeitstempel versehen sind und ob Sie unbearbeitete Bewertungen und Verbraucherpräferenzen anfordern.
{: shortdesc}

Die CSV-Ausgabe wird im Gegensatz zur JSON-Ausgabe als feste Anzahl von Spalten zurückgegeben. Die erste Zeile der Ausgabe besteht aus optionalen Spaltenbeschriftungen, die nur enthalten sind, wenn Sie den Abfrageparameter `csv_headers` der Anforderung auf `true` setzen. Die zweite Zeile der Ausgabe, die immer vorhanden ist, enthält die Ergebnisse der Analyse.

In den folgenden Abschnitten werden alle Spalten der CSV-Ausgabe genau in der Reihenfolge, in der sie in den Ergebnissen enthalten sind, aufgelistet und kurz beschrieben. Die Tabellen beschreiben die Spalten nach logischer Gruppierung und geben auch die Anzahl der Spalten in jeder Gruppe und deren optionale Beschriftungen an. Abgesehen von der Wortzahl werden alle numerischen Daten als Werte des Typs 'Double' zurückgegeben.

Weitere Informationen zur Bedeutung der CSV-Spalten finden Sie unter [JSON-Profil verstehen](/docs/services/personality-insights?topic=personality-insights-output) und [Numerische Ergebnisse interpretieren](/docs/services/personality-insights?topic=personality-insights-numeric).

## Basismerkmale und Metadaten
{: #basicCSV}

Die folgenden Spalten sind in der CSV-Ausgabe stets für alle Anforderungen vorhanden.

<table>
  <caption>Tabelle 1. CSV-Spalten für Basismerkmale und
    Metadaten</caption>
  <tr>
    <th style="width:25%; text-align:left; vertical-align:bottom">Gruppierung<br/>(Anzahl von Spalten)</th>
    <th style="width:25%; text-align:left; vertical-align:bottom">Optionale Beschriftungen</th>
    <th style="text-align:left; vertical-align:bottom">Beschreibung</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five-Perzentile der Verträglichkeit<br/>(Sieben Spalten)
    </td>
    <td style="vertical-align:top">
      big5_agreeableness<br/>facet_altruism<br/>
      facet_cooperation<br/>facet_modesty<br/>
      facet_morality<br/>facet_sympathy<br/>
      facet_trust
    </td>
    <td style="vertical-align:top">
      Normalisierte Perzentilbewertung für den Autor des Texts hinsichtlich
      der genannten Dimension oder Facette.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five-Perzentile der Gewissenhaftigkeit<br/>(Sieben Spalten)
    </td>
    <td style="vertical-align:top">
      big5_conscientiousness<br/>facet_achievement_striving
      <br/>facet_cautiousness<br/>facet_dutifulness<br/>
      facet_orderliness<br/>facet_self_discipline<br/>
      facet_self_efficacy
    </td>
    <td style="vertical-align:top">
      Normalisierte Perzentilbewertung für den Autor des Texts hinsichtlich
      der genannten Dimension oder Facette.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five-Perzentile der Extraversion<br/>(Sieben Spalten)
    </td>
    <td style="vertical-align:top">
      big5_extraversion<br/>facet_activity_level
      <br/>facet_assertiveness<br/>facet_cheerfulness<br/>
      facet_excitement_seeking<br/>facet_friendliness<br/>
      facet_gregariousness
    </td>
    <td style="vertical-align:top">
      Normalisierte Perzentilbewertung für den Autor des Texts hinsichtlich
      der genannten Dimension oder Facette.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five-Perzentile des emotionalen Spektrums<br/>(Sieben Spalten)
    </td>
    <td style="vertical-align:top">
      big5_neuroticism<br/>facet_anger<br/>
      facet_anxiety<br/>facet_depression<br/>
      facet_immoderation<br/>facet_self_consciousness<br/>
      facet_vulnerability
    </td>
    <td style="vertical-align:top">
      Normalisierte Perzentilbewertung für den Autor des Texts hinsichtlich
      der genannten Dimension oder Facette.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five-Perzentile der Offenheit<br/>(Sieben Spalten)
    </td>
    <td style="vertical-align:top">
      big5_openness<br/>facet_adventurousness<br/>
      facet_artistic_interests<br/>facet_emotionality<br/>
      facet_imagination<br/>facet_intellect<br/>
      facet_liberalism
    </td>
    <td style="vertical-align:top">
      Normalisierte Perzentilbewertung für den Autor des Texts hinsichtlich
      der genannten Dimension oder Facette.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Perzentile: Bedürfnisse:<br/>(Zwölf Spalten)
    </td>
    <td style="vertical-align:top">
      need_liberty<br/>need_ideal<br/>
      need_love<br/>need_practicality<br/>
      need_self_expression<br/>need_stability<br/>
      need_structure<br/>need_challenge<br/>
      need_closeness<br/>need_curiosity<br/>
      need_excitement<br/>need_harmony
    </td>
    <td style="vertical-align:top">
      Normalisierte Perzentilbewertung für den Autor des Texts hinsichtlich
      des genannten Bedürfnisses.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Perzentile: Werte<br/>(Fünf Spalten)
    </td>
    <td style="vertical-align:top">
      value_conservation<br/>value_hedonism<br/>
      value_openness_to_change<br/>value_self_enhancement<br/>
      value_self_transcendence
    </td>
    <td style="vertical-align:top">
      Normalisierte Perzentilbewertung für den Autor des Texts hinsichtlich
      des genannten Werts.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Prozentsätze für Tage der Woche<br/>(Sieben Spalten)
    </td>
    <td style="vertical-align:top">
      behavior_sunday<br/>behavior_monday<br/>
      behavior_tuesday<br/>behavior_wednesday<br/>
      behavior_thursday<br/>behavior_friday<br/>
      behavior_saturday
    </td>
    <td style="vertical-align:top">
      Wenn der <em>Eingabetext mit einer Zeitmarke versehen</em> ist, der Prozentsatz der Eingabe, der jedem einzelnen Tag der Woche zugeordnet ist. Andernfalls haben alle Prozentsätze den Wert <code>0,0</code>.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Prozentsätze für Stunden des Tages<br/>(Vierundzwanzig Spalten)
    </td>
    <td style="vertical-align:top">
      behavior_0000<em> bis </em>behavior_2300
    </td>
    <td style="vertical-align:top">
      Wenn der <em>Eingabetext mit einer Zeitmarke versehen</em> ist, der Prozentsatz der
      Eingabe, der jeder einzelnen Stunde des Tages zugeordnet ist. Andernfalls haben
      alle Prozentsätze den Wert <code>0,0</code>.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Wortzahl und Sprache<br/>(Zwei Spalten)
    </td>
    <td style="vertical-align:top">
      word_count<br/>processed_language
    </td>
    <td style="vertical-align:top">
      Ein Integerwert, der die Anzahl der Wörter angibt, die im Eingabetext
      vorhanden sind, und eine Kennung aus zwei Buchstaben für das Sprachmodell,
      das der Service zur Analyse des Texts verwendet hat.
    </td>
  </tr>
</table>

## Unaufbereitete Bewertungen
{: #rawCSV}

Die folgenden Spalten sind nur vorhanden, wenn Sie unaufbereitete Bewertungen anfordern, indem Sie für den Abfrageparameter `raw_scores` den Wert `true` festlegen. In allen Fällen enthält die Spalte einen Double-Wert, der die unaufbereitete Bewertung des Autors für die Dimension, die  Facette, das Bedürfnis oder den Wert angibt.

<table>
  <caption>Tabelle 2. CSV-Spalten für unaufbereitete Bewertungen</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">Gruppierung<br/>(Anzahl von Spalten)</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">Optionale Beschriftungen</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five-Faktor der Verträglichkeit: Unaufbereitete Bewertungen<br/>(Sieben Spalten)
    </td>
    <td>
      big5_agreeableness_raw<br/>facet_altruism_raw<br/>
      facet_cooperation_raw<br/>facet_modesty_raw<br/>
      facet_morality_raw<br/>facet_sympathy_raw<br/>
      facet_trust_raw
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five-Faktor der Gewissenhaftigkeit: Unaufbereitete Bewertungen<br/>(Sieben Spalten)
    </td>
    <td>
      big5_conscientiousness_raw<br/>facet_achievement_striving_raw<br/>
      facet_cautiousness_raw<br/>facet_dutifulness_raw<br/>
      facet_orderliness_raw<br/>facet_self_discipline_raw<br/>
      facet_self_efficacy_raw
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five-Faktor der Extraversion: Unaufbereitete Bewertungen<br/>(Sieben Spalten)
    </td>
    <td>
      big5_extraversion_raw<br/>facet_activity_level_raw<br/>
      facet_assertiveness_raw<br/>facet_cheerfulness_raw<br/>
      facet_excitement_seeking_raw<br/>facet_friendliness_raw<br/>
      facet_gregariousness_raw
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five-Faktor des emotionalen Spektrums: Unaufbereitete Bewertungen<br/>(Sieben Spalten)
    </td>
    <td>
      big5_neuroticism_raw<br/>facet_anger_raw<br/>
      facet_anxiety_raw<br/>facet_depression_raw<br/>
      facet_immoderation_raw<br/>facet_self_consciousness_raw<br/>
      facet_vulnerability_raw
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five-Faktor der Offenheit: Unaufbereitete Bewertungen<br/>(Sieben Spalten)
    </td>
    <td>
      big5_openness_raw<br/>facet_adventurousness_raw<br/>
      facet_artistic_interests_raw<br/>facet_emotionality_raw<br/>
      facet_imagination_raw<br/>facet_intellect_raw<br/>
      facet_liberalism_raw
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Bedürfnisse: Unaufbereitete Bewertungen<br/>(Zwölf Spalten)
    </td>
    <td>
      need_liberty_raw<br/>need_ideal_raw<br/>
      need_love_raw<br/>need_practicality_raw<br/>
      need_self_expression_raw<br/>need_stability_raw<br/>
      need_structure_raw<br/>need_challenge_raw<br/>
      need_closeness_raw<br/>need_curiosity_raw<br/>
      need_excitement_raw<br/>need_harmony_raw
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Werte: Unaufbereitete Bewertungen<br/>(Fünf Spalten)
    </td>
    <td>
      value_conservation_raw<br/>value_hedonism_raw<br/>
      value_openness_to_change_raw<br/>value_self_enhancement_raw<br/>
      value_self_transcendence_raw
    </td>
  </tr>
</table>

## Signifikanz
{: #significantCSV}

Die folgenden Spalten sind in der CSV-Ausgabe stets für alle Anforderungen vorhanden. In allen Fällen enthält die Spalte einen booleschen Wert, der angibt, ob die Dimension, die Facette, das Bedürfnis oder der Wert für die verarbeitete Eingabesprache aussagekräftig ist.

<table>
  <caption>Tabelle 3. CSV-Spalten für Signifikanz</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">Gruppierung<br/>(Anzahl von Spalten)</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">Optionale Beschriftungen</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five-Faktor der Verträglichkeit: Signifikanz<br/>(Sieben Spalten)
    </td>
    <td>
      big5_agreeableness_significant<br/>facet_altruism_significant<br/>
      facet_cooperation_significant<br/>facet_modesty_significant<br/>
      facet_morality_significant<br/>facet_sympathy_significant<br/>
      facet_trust_significant
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five-Faktor der Gewissenhaftigkeit: Signifikanz<br/>(Sieben Spalten)
    </td>
    <td>
      big5_conscientiousness_significant<br/>
      facet_achievement_striving_significant<br/>
      facet_cautiousness_significant<br/>facet_dutifulness_significant<br/>
      facet_orderliness_significant<br/>facet_self_discipline_significant<br/>
      facet_self_efficacy_significant
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five-Faktor der Extraversion: Signifikanz<br/>(Sieben Spalten)
    </td>
    <td>
      big5_extraversion_significant<br/>facet_activity_level_significant<br/>
      facet_assertiveness_significant<br/>facet_cheerfulness_significant<br/>
      facet_excitement_seeking_significant<br/>
      facet_friendliness_significant<br/>facet_gregariousness_significant
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five-Faktor des emotionalen Spektrums: Signifikanz<br/>(Sieben Spalten)
    </td>
    <td>
      big5_neuroticism_significant<br/>facet_anger_significant<br/>
      facet_anxiety_significant<br/>facet_depression_significant<br/>
      facet_immoderation_significant<br/>
      facet_self_consciousness_significant<br/>facet_vulnerability_significant
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Big Five-Faktor der Offenheit: Signifikanz<br/>(Sieben Spalten)
    </td>
    <td>
      big5_openness_significant<br/>facet_adventurousness_significant<br/>
      facet_artistic_interests_significant<br/>
      facet_emotionality_significant<br/>facet_imagination_significant<br/>
      facet_intellect_significant<br/>facet_liberalism_significant
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Bedürfnisse: Unaufbereitete Bewertungen: Signifikanz<br/>(Zwölf Spalten)
    </td>
    <td>
      need_liberty_significant<br/>need_ideal_significant<br/>
      need_love_significant<br/>need_practicality_significant<br/>
      need_self_expression_significant<br/>need_stability_significant<br/>
      need_structure_significant<br/>need_challenge_significant<br/>
      need_closeness_significant<br/>need_curiosity_significant<br/>
      need_excitement_significant<br/>need_harmony_significant
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Werte: Signifikanz<br/>(Fünf Spalten)
    </td>
    <td>
      value_conservation_significant<br/>value_hedonism_significant<br/>
      value_openness_to_change_significant<br/>
      value_self_enhancement_significant<br/>
      value_self_transcendence_significant
    </td>
  </tr>
</table>

## Verbraucherpräferenzen
{: #preferenceCSV}

Die folgenden Spalten sind nur vorhanden, wenn Sie Verbraucherpräferenzen anfordern, indem Sie für den Abfrageparameter `consumption_preferences` den Wert `true` festlegen. In allen Fällen enthält die Spalte einen Double-Wert, der die Wahrscheinlichkeit angibt, mit der der Autor das genannte Verbraucherthema bevorzugt.

<table style="width:90%">
  <caption>Tabelle 4. CSV-Spalten für Verbraucherpräferenzen</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">Gruppierung<br/>(Anzahl von Spalten)</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">Optionale Beschriftungen</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Bewertungen in der Kategorie der Präferenzen im Bereich 'Kaufverhalten'<br/>(Zwölf Spalten)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_spur_of_moment<br/>
      consumption_preferences_credit_card_payment<br/>
      consumption_preferences_influence_brand_name<br/>
      consumption_preferences_influence_utility<br/>
      consumption_preferences_online_ads<br/>
      consumption_preferences_social_media<br/>
      consumption_preferences_family_members<br/>
      consumption_preferences_clothes_quality<br/>
      consumption_preferences_clothes_style<br/>
      consumption_preferences_clothes_comfort<br/>
      consumption_preferences_automobile_ownership_cost<br/>
      consumption_preferences_automobile_safety
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Bewertungen in der Kategorie der Präferenzen im Bereich 'Musik'<br/>(Neun Spalten)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_music_rap<br/>
      consumption_preferences_music_country<br/>
      consumption_preferences_music_r_b<br/>
      consumption_preferences_music_hip_hop<br/>
      consumption_preferences_music_live_event<br/>
      consumption_preferences_music_playing<br/>
      consumption_preferences_music_latin<br/>
      consumption_preferences_music_rock<br/>
      consumption_preferences_music_classical
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Bewertungen in der Kategorie der Präferenzen im Bereich 'Gesundheit und Aktivität'<br/>(Drei Spalten)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_gym_membership<br/>
      consumption_preferences_outdoor<br/>
      consumption_preferences_eat_out
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Bewertungen in der Kategorie der Präferenzen im Bereich 'Film'<br/>(Zehn Spalten)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_movie_romance<br/>
      consumption_preferences_movie_adventure<br/>
      consumption_preferences_movie_horror<br/>
      consumption_preferences_movie_musical<br/>
      consumption_preferences_movie_historical<br/>
      consumption_preferences_movie_science_fiction<br/>
      consumption_preferences_movie_war<br/>
      consumption_preferences_movie_drama<br/>
      consumption_preferences_movie_action<br/>
      consumption_preferences_movie_documentary
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Bewertungen in der Kategorie der Präferenzen im Bereich 'Lektüre'<br/>(Fünf Spalten)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_read_frequency<br/>
      consumption_preferences_books_entertainment_magazines<br/>
      consumption_preferences_books_non_fiction<br/>
      consumption_preferences_books_financial_investing<br/>
      consumption_preferences_books_autobiographies
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Bewertungen in der Kategorie der Präferenzen im Bereich 'Ehrenamtliche Mitarbeit'<br/>(Eine Spalte)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_volunteer
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Bewertungen in der Kategorie der Präferenzen im Bereich 'Umweltbewusstsein'<br/>(Eine Spalte)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_concerned_environment
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Bewertungen in der Kategorie der Präferenzen im Bereich 'Unternehmergeist'<br/>(Eine Spalte)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_start_business
    </td>
  </tr>
</table>
