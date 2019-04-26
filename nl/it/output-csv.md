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

# Descrizione di un profilo CSV
{: #outputCSV}

Il servizio restituisce la sua analisi in formato CSV (comma-separated value) se specifichi `text/csv` con l'intestazione `Accept` di una richiesta. L'output CSV fornisce informazioni simili a quelle fornite dall'output JSON. Come con JSON, le informazioni nell'output CSV dipendono dal fatto che i dati di input vengano rappresentati con data e ora e se si richiedono punteggi non elaborati e preferenze di consumo.
{: shortdesc}

L'output CSV, a differenza di JSON, viene restituito come un numero fisso di colonne. La prima riga dell'output è composta da etichette di colonna facoltative, che vengono incluse solo se imposti il parametro di query `csv_headers` della richiesta su `true`. La seconda riga dell'output, che è sempre presente, contiene i risultati dell'analisi.

Le seguenti sezioni elencano e descrivono brevemente tutte le colonne dell'output CSV nell'ordine esatto in cui vengono visualizzate nei risultati. Le tabelle descrivono le colonne per raggruppamento logico, incluso il numero di colonne in ciascun gruppo e le relative etichette facoltative. A parte il conteggio delle parole, tutti i dati numerici vengono restituiti come valori doppi. 

Per ulteriori informazioni sul significato delle colonne CSV, vedi [Descrizione di un profilo JSON](/docs/services/personality-insights?topic=personality-insights-output) e [Interpretazione dei risultati numerici](/docs/services/personality-insights?topic=personality-insights-numeric).

## Caratteristiche di base e metadati
{: #basicCSV}

Le seguenti colonne sono sempre presenti nell'output CSV per tutte le richieste.

<table>
  <caption>Tabella 1. Colonne CSV per le caratteristiche di base e i
    metadati</caption>
  <tr>
    <th style="width:25%; text-align:left; vertical-align:bottom">Raggruppamento<br/>(Numero di colonne)</th>
    <th style="width:25%; text-align:left; vertical-align:bottom">Etichette facoltative</th>
    <th style="text-align:left; vertical-align:bottom">Descrizione</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Percentili di Gradevolezza Big Five<br/>(Sette colonne)
    </td>
    <td style="vertical-align:top">
      big5_agreeableness<br/>facet_altruism<br/>
      facet_cooperation<br/>facet_modesty<br/>
      facet_morality<br/>facet_sympathy<br/>
      facet_trust
    </td>
    <td style="vertical-align:top">
      Punteggio percentile normalizzato per l'autore del testo per la
      dimensione o l'aspetto denominato.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Percentili di Coscienziosità Big Five<br/>(Sette colonne)
    </td>
    <td style="vertical-align:top">
      big5_conscientiousness<br/>facet_achievement_striving
      <br/>facet_cautiousness<br/>facet_dutifulness<br/>
      facet_orderliness<br/>facet_self_discipline<br/>
      facet_self_efficacy
    </td>
    <td style="vertical-align:top">
      Punteggio percentile normalizzato per l'autore del testo per la
      dimensione o l'aspetto denominato.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Percentili di Estroversione Big Five<br/>(Sette colonne)
    </td>
    <td style="vertical-align:top">
      big5_extraversion<br/>facet_activity_level
      <br/>facet_assertiveness<br/>facet_cheerfulness<br/>
      facet_excitement_seeking<br/>facet_friendliness<br/>
      facet_gregariousness
    </td>
    <td style="vertical-align:top">
      Punteggio percentile normalizzato per l'autore del testo per la
      dimensione o l'aspetto denominato.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Percentili di Stabilità emotiva Big Five<br/>(Sette colonne)
    </td>
    <td style="vertical-align:top">
      big5_neuroticism<br/>facet_anger<br/>
      facet_anxiety<br/>facet_depression<br/>
      facet_immoderation<br/>facet_self_consciousness<br/>
      facet_vulnerability
    </td>
    <td style="vertical-align:top">
      Punteggio percentile normalizzato per l'autore del testo per la
      dimensione o l'aspetto denominato.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Percentili di Apertura mentale Big Five<br/>(Sette colonne)
    </td>
    <td style="vertical-align:top">
      big5_openness<br/>facet_adventurousness<br/>
      facet_artistic_interests<br/>facet_emotionality<br/>
      facet_imagination<br/>facet_intellect<br/>
      facet_liberalism
    </td>
    <td style="vertical-align:top">
      Punteggio percentile normalizzato per l'autore del testo per la
      dimensione o l'aspetto denominato.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Percentili di Esigenze<br/>(Dodici colonne)
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
      Punteggio percentile normalizzato per l'autore del testo per
      l'esigenza denominata.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Percentili di Valori<br/>(Cinque colonne)
    </td>
    <td style="vertical-align:top">
      value_conservation<br/>value_hedonism<br/>
      value_openness_to_change<br/>value_self_enhancement<br/>
      value_self_transcendence
    </td>
    <td style="vertical-align:top">
      Punteggio percentile normalizzato per l'autore del testo per
      il valore denominato.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Percentuali dei giorni della settimana<br/>(Sette colonne)
    </td>
    <td style="vertical-align:top">
      behavior_sunday<br/>behavior_monday<br/>
      behavior_tuesday<br/>behavior_wednesday<br/>
      behavior_thursday<br/>behavior_friday<br/>
      behavior_saturday
    </td>
    <td style="vertical-align:top">
      <em>Se il testo di input ha un indicatore di data e ora,</em> la percentuale dell'input
      associato a ciascun giorno della settimana. Diversamente, le
      percentuali sono tutte <code>0.0</code>.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Percentuali delle ore del giorno<br/>(Ventiquattro colonne)
    </td>
    <td style="vertical-align:top">
      da behavior_0000 <em>a</em> behavior_2300
    </td>
    <td style="vertical-align:top">
      <em>Se il testo di input ha un indicatore di data e ora,</em> la percentuale
      dell'input associato a ciascuna ora del giorno. Diversamente, le
      percentuali sono tutte <code>0.0</code>.
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Conteggio delle parole e lingua<br/>(Due colonne)
    </td>
    <td style="vertical-align:top">
      word_count<br/>processed_language
    </td>
    <td style="vertical-align:top">
      Un numero intero che indica il numero di parole presenti nel testo di input
      e un identificativo di due lettere per il modello di lingua utilizzato dal
      servizio per analizzare il testo.
    </td>
  </tr>
</table>

## Punteggi non elaborati
{: #rawCSV}

Le seguenti colonne sono presenti solo se richiedi i punteggi non elaborati impostando il parametro di query `raw_scores` su `true`. In tutti i casi, la colonna è un valore doppio che fornisce il punteggio non elaborato dell'autore per la dimensione, l'aspetto, l'esigenza o il valore.

<table>
  <caption>Tabella 2. Colonne CSV per i punteggi non elaborati</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">Raggruppamento<br/>(Numero di colonne)</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">Etichette facoltative</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Punteggi non elaborati di Gradevolezza Big Five<br/>(Sette colonne)
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
      Punteggi non elaborati di Coscienziosità Big Five<br/>(Sette colonne)
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
      Punteggi non elaborati di Estroversione Big Five<br/>(Sette colonne)
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
      Punteggi non elaborati di Stabilità emotiva Big Five<br/>(Sette colonne)
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
      Punteggi non elaborati di Apertura mentale Big Five<br/>(Sette colonne)
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
      Punteggi non elaborati di Esigenze<br/>(Dodici colonne)
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
      Punteggi non elaborati di Valori<br/>(Cinque colonne)
    </td>
    <td>
      value_conservation_raw<br/>value_hedonism_raw<br/>
      value_openness_to_change_raw<br/>value_self_enhancement_raw<br/>
      value_self_transcendence_raw
    </td>
  </tr>
</table>

## Significatività
{: #significantCSV}

Le seguenti colonne sono sempre presenti nell'output CSV per tutte le richieste. In tutti i casi, la colonna è un valore booleano che indica se la dimensione, l'aspetto, l'esigenza o il valore è significativo per la lingua di input elaborata.

<table>
  <caption>Tabella 3. Colonne CSV per significatività</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">Raggruppamento<br/>(Numero di colonne)</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">Etichette facoltative</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Significatività di Gradevolezza Big Five<br/>(Sette colonne)
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
      Significatività di Coscienziosità Big Five<br/>(Sette colonne)
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
      Significatività di Estroversione Big Five<br/>(Sette colonne)
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
      Significatività di Stabilità emotiva Big Five<br/>(Sette colonne)
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
      Significatività di Apertura mentale Big Five<br/>(Sette colonne)
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
      Significatività di Esigenze<br/>(Dodici colonne)
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
      Significatività di Valori<br/>(Cinque colonne)
    </td>
    <td>
      value_conservation_significant<br/>value_hedonism_significant<br/>
      value_openness_to_change_significant<br/>
      value_self_enhancement_significant<br/>
      value_self_transcendence_significant
    </td>
  </tr>
</table>

## Preferenze di consumo
{: #preferenceCSV}

Le seguenti colonne sono presenti solo se richiedi le preferenze di consumo impostando il parametro di query `consumption_preferences` su `true`. In tutti i casi, la colonna è un valore doppio che riporta la probabilità che l'autore preferisca l'argomento di consumo denominato.

<table style="width:90%">
  <caption>Tabella 4. Colonne CSV per le preferenze di consumo</caption>
  <tr>
    <th style="width:40%; text-align:left; vertical-align:bottom">Raggruppamento<br/>(Numero di colonne)</th>
    <th style="width:60%; text-align:left; vertical-align:bottom">Etichette facoltative</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Punteggi per la categoria preferenze di acquisto<br/>(Dodici colonne)
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
      Punteggi per la categoria preferenze musicali<br/>(Nove colonne)
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
      Punteggi per la categoria preferenze di salute e attività<br/>(Tre colonne)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_gym_membership<br/>
      consumption_preferences_outdoor<br/>
      consumption_preferences_eat_out
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Punteggi per la categoria preferenze di film<br/>(Dieci colonne)
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
      Punteggi per la categoria preferenze di lettura<br/>(Cinque colonne)
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
      Punteggi per la categoria preferenze di volontariato<br/>(Una colonna)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_volunteer
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Punteggi per la categoria preferenze di interesse ambientale<br/>(Una colonna)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_concerned_environment
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      Punteggi per la categoria preferenze di imprenditorialità<br/>(Una colonna)
    </td>
    <td style="vertical-align:top">
      consumption_preferences_start_business
    </td>
  </tr>
</table>
