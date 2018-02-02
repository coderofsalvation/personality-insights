---

copyright:
  years: 2015, 2017
lastupdated: "2017-10-12"

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

# Verbraucherpräferenzen
{: #preferences}

Der {{site.data.keyword.personalityinsightsshort}}-Service leitet Persönlichkeitsmerkmale eines Autors nach drei Modellen ab: Big Five, Bedürfnisse (Needs) und Werte (Values). Auf der Basis der Ergebnisse für diese Modelle kann der Service außerdem Verbraucherpräferenzen für den Autor des Eingabetexts generieren. Setzen Sie den Abfrageparameter `consumption_preferences` für eine Anforderung auf `true`, um Verbraucherpräferenzen abzurufen.
{: shortdesc}

Die über 40 Verbraucherpräferenzen in acht übergeordneten Gruppen geben die Wahrscheinlichkeit des Autors an, mit der er verschiedene Produkte, Services und Aktivitäten bevorzugt. Der Service kann zum Beispiel die Neigungen des Autors, wenn er sich im Geschäft Kleidung (bequem oder modisch) oder Automobile (kostengünstig oder sicherheitsorientiert) ansieht, seine Neigungen zu verschiedenen Genres in den Bereichen Musik, Film und Literatur sowie seine Haltung zu Umwelt und ehrenamtlicher Tätigkeit unter anderem erschließen.

Unternehmen verwenden die Persönlichkeitsmodelle des Service, um ihre Kunden besser zu verstehen und personalisiertere und zielorientiertere Kampagnen, Produkte und Services zu entwerfen und zu entwickeln. Verbraucherpräferenzen vereinfachen die Aufgabe, Maßnahmen auf der Grundlage der Ergebnisse des Services zu ergreifen. Unternehmen können ohne großen Aufwand eine Liste von Präferenzen abrufen, die den dominanten Merkmalen einer Person zugeordnet sind, und entsprechend reagieren. Weitere Informationen zu möglichen Anwendungen der Verbraucherpräferenzen finden Sie unter [Anwendungsfälle](/docs/services/personality-insights/usecases.html) und [Service in Aktion](/docs/services/personality-insights/applied.html).

In den folgenden Abschnitten werden die Verbraucherpräferenzen aufgeführt und beschrieben, die der Service zurückgeben kann. Weitere Informationen zur Interpretation der numerischen Werte für Präferenzen finden Sie unter [Bewertungen für Verbraucherpräferenzen](/docs/services/personality-insights/numeric.html#scores). Informationen dazu, wie die Präferenzen von {{site.data.keyword.IBM_notm}} entwickelt wurden, finden Sie unter [Wissenschaftliche Grundlagen des Service](/docs/services/personality-insights/science.html).

## Einkaufspräferenzen
{: #shopping}

Einkaufspräferenzen geben das Interesse des Autors an verschiedenen Typen von Einkäufen, das Ausmaß, in dem die Einkaufsgewohnheiten des Autors durch verschiedene externe Quellen beeinflusst werden, sowie das Geldausgabeverhalten des Autors an. Die Kategorie-ID und der Name sind `consumption_preferences_shopping` und `Präferenzen im Bereich Kaufverhalten`. Die Kategorie besitzt 12 Präferenzen.

<table>
  <caption>Tabelle 1. Einkaufspräferenzen</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID der Verbraucherpräferenz
    </th>
    <th style="width:30%; text-align:left">
      Name
    </th>
    <th style="text-align:center">
      Bewertungen
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_automobile_ownership_cost</code>
    </td>
    <td style="text-align:left">
      Achtet beim Autokauf auf die Betriebskosten
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_automobile_safety</code>
    </td>
    <td style="text-align:left">
      Achtet beim Autokauf auf Sicherheitsaspekte
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_quality</code>
    </td>
    <td style="text-align:left">
      Legt beim Kauf von Bekleidung Wert auf Qualität
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_style</code>
    </td>
    <td style="text-align:left">
      Legt beim Kauf von Bekleidung Wert auf Stil
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_clothes_comfort</code>
    </td>
    <td style="text-align:left">
      Legt beim Kauf von Bekleidung Wert auf Tragekomfort
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_brand_name</code>
    </td>
    <td style="text-align:left">
      Lässt sich beim Kauf von Produkten vom Markennamen beeinflussen
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_utility</code>
    </td>
    <td style="text-align:left">
      Lässt sich beim Kauf von Produkten vom praktischen Nutzen
      beeinflussen
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_online_ads</code>
    </td>
    <td style="text-align:left">
      Lässt sich beim Kauf von Produkten von Onlinewerbung beeinflussen
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_social_media</code>
    </td>
    <td style="text-align:left">
      Lässt sich beim Kauf von Produkten von sozialen Medien
      beeinflussen
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_influence_family_members</code>
    </td>
    <td style="text-align:left">
      Lässt sich beim Kauf von Produkten von der Familie beeinflussen
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_spur_of_moment</code>
    </td>
    <td style="text-align:left">
      Neigt zu Spontankäufen
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_credit_card_payment</code>
    </td>
    <td style="text-align:left">
      Nutzt beim Einkauf häufig die Kreditkarte
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
</table>

## Filmpräferenzen
{: #movie}

Filmpräferenzen geben Aufschluss über das Interesse des Autors an verschiedenen Arten von Filmen. Die Kategorie-ID und der Name sind `consumption_preferences_movie` und `Präferenzen im Bereich Film`. Die Kategorie besitzt 10 Präferenzen.

<table>
  <caption>Tabelle 2. Filmpräferenzen</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID der Verbraucherpräferenz
    </th>
    <th style="width:30%; text-align:left">
      Name
    </th>
    <th style="text-align:center">
      Bewertungen
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_romance</code>
    </td>
    <td style="text-align:left">
      Mag Liebesfilme
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_adventure</code>
    </td>
    <td style="text-align:left">
      Mag Abenteuerfilme
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_horror</code>
    </td>
    <td style="text-align:left">
      Mag Horrorfilme
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_musical</code>
    </td>
    <td style="text-align:left">
      Mag Musikfilme
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_historical</code>
    </td>
    <td style="text-align:left">
      Mag Historienfilme
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_science_fiction</code>
    </td>
    <td style="text-align:left">
      Mag Science-Fiction-Filme
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_war</code>
    </td>
    <td style="text-align:left">
      Mag Kriegsfilme
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_drama</code>
    </td>
    <td style="text-align:left">
      Mag Dramen
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_action</code>
    </td>
    <td style="text-align:left">
      Mag Actionfilme
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_movie_documentary</code>
    </td>
    <td style="text-align:left">
      Mag Dokumentarfilme
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
</table>

## Musikpräferenzen
{: #music}

Musikpräferenzen geben das Interesse des Autors an verschiedenen Typen von Musik an und zeigen, ob der Autor gerne Musik macht. Die Kategorie-ID und der Name sind `consumption_preferences_music` und `Präferenzen im Bereich Musik`. Die Kategorie besitzt neun Präferenzen.

<table>
  <caption>Tabelle 3. Musikpräferenzen</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID der Verbraucherpräferenz
    </th>
    <th style="width:30%; text-align:left">
      Name
    </th>
    <th style="text-align:center">
      Bewertungen
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_rap</code>
    </td>
    <td style="text-align:left">
      Mag Mag Rap-Musik
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_country</code>
    </td>
    <td style="text-align:left">
      Mag Country-Musik
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_r_b</code>
    </td>
    <td style="text-align:left">
      Mag R&amp;B-Musik
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_hip_hop</code>
    </td>
    <td style="text-align:left">
      Mag Hip Hop-Musik
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_live_event</code>
    </td>
    <td style="text-align:left">
      Besucht Livemusikveranstaltungen
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_playing</code>
    </td>
    <td style="text-align:left">
      Hat Erfahrung mit eigenem Musizieren
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_latin</code>
    </td>
    <td style="text-align:left">
      Mag lateinamerikanische Musik
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_rock</code>
    </td>
    <td style="text-align:left">
      Mag Rockmusik
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_music_classical</code>
    </td>
    <td style="text-align:left">
      Mag klassische Musik
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
</table>

## Lektüre- und Bildungspräferenzen
{: #reading}

Lektüre- und Bildungspräferenzen geben die Wahrscheinlichkeit, mit der der Autor liest, die Lesemotivation des Autors sowie die Typen von Inhalten, die der Autor gerne liest, an. Die Kategorie-ID und der Name sind `consumption_preferences_reading` und `Präferenzen im Bereich Literatur`. Die Kategorie besitzt fünf Präferenzen.

<table>
  <caption>Tabelle 4. Lektüre- und Bildungspräferenzen</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID der Verbraucherpräferenz
    </th>
    <th style="width:30%; text-align:left">
      Name
    </th>
    <th style="text-align:center">
      Bewertungen
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_read_frequency</code>
    </td>
    <td style="text-align:left">
      Liest häufig
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_entertainment_magazines</code>
    </td>
    <td style="text-align:left">
      Liest Unterhaltungsmagazine
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_non_fiction</code>
    </td>
    <td style="text-align:left">
      Liest Sachbücher
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_financial_investing</code>
    </td>
    <td style="text-align:left">
      Liest Bücher zu Finanzinvestitionen
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_books_autobiographies</code>
    </td>
    <td style="text-align:left">
      Liest autobiografische Bücher
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
</table>

## Gesundheits- und Aktivitätspräferenzen
{: #health}

Gesundheits- und Aktivitätspräferenzen geben das Interesse des Autors an gesunden Nahrungsmitteln und körperlichen Aktivitäten an. Die Kategorie-ID und der Name sind `consumption_preferences_health_and_activity` und `Präferenzen im Bereich Gesundheit und Aktivitäten`. Die Kategorie besitzt drei Präferenzen.

<table>
  <caption>Tabelle 5. Gesundheits- und Aktivitätspräferenzen</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID der Verbraucherpräferenz
    </th>
    <th style="width:30%; text-align:left">
      Name
    </th>
    <th style="text-align:center">
      Bewertungen
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_eat_out</code>
    </td>
    <td style="text-align:left">
      Isst häufig außer Haus
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_gym_membership</code>
    </td>
    <td style="text-align:left">
      Ist wahrscheinlich Mitglied in einem Fitnessstudio
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_outdoor</code>
    </td>
    <td style="text-align:left">
      Mag Outdoor-Aktivitäten
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
</table>

## Unternehmerische Präferenzen
{: #entrepreneur}

Unternehmerische Präferenzen geben das Interesse des Autors an, ein Geschäft zu gründen. Die Kategorie-ID und der Name sind `consumption_preferences_entrepreneurship` und `Unternehmerische Präferenzen`. Die Kategorie besitzt eine Präferenz.

<table>
  <caption>Tabelle 6. Unternehmerische Präferenzen</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID der Verbraucherpräferenz
    </th>
    <th style="width:30%; text-align:left">
      Name
    </th>
    <th style="text-align:center">
      Bewertungen
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_start_business</code>
    </td>
    <td style="text-align:left">
      Könnte in den nächsten Jahren ein Unternehmen gründen
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
</table>

## Umweltbewusste Präferenzen
{: #environment}

Umweltbewusste Präferenzen geben das Interesse des Autors an der Umwelt an. Die Kategorie-ID und der Name sind `consumption_preferences_environmental_concern` und `Präferenzen im Bereich Umwelt`. Die Kategorie besitzt eine Präferenz.

<table>
  <caption>Tabelle 7. Umweltbewusste Präferenzen</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID der Verbraucherpräferenz
    </th>
    <th style="width:30%; text-align:left">
      Name
    </th>
    <th style="text-align:center">
      Bewertungen
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_concerned_environment</code>
    </td>
    <td style="text-align:left">
      Macht sich Gedanken über die Umwelt
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>0.5</code> (neutral)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
</table>

## Ehrenamtliche Präferenzen
{: #volunteer}

Ehrenamtliche Präferenzen geben das Interesse des Autors an ehrenamtlicher Tätigkeit im Sozialbereich an. Die Kategorie-ID und der Name sind `consumption_preferences_volunteering` und `Präferenzen im Bereich der ehrenamtlichen Arbeit`. Die Kategorie besitzt eine Präferenz.

<table>
  <caption>Tabelle 8. Ehrenamtliche Präferenzen</caption>
  <tr>
    <th style="width:45%; text-align:left">
      ID der Verbraucherpräferenz
    </th>
    <th style="width:30%; text-align:left">
      Name
    </th>
    <th style="text-align:center">
      Bewertungen
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      <code>consumption_preferences_volunteer</code>
    </td>
    <td style="text-align:left">
      Möchte ehrenamtlich für soziale Projekte arbeiten
    </td>
    <td style="text-align:center">
      <code>0.0</code> (unwahrscheinlich)<br/>
      <code>1.0</code> (wahrscheinlich)
    </td>
  </tr>
</table>
