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

# Entendendo um perfil JSON
{: #output}

Quando você usa o método `POST /v3/profile` para analisar conteúdo, o serviço retorna os resultados de sua análise como um objeto de JSON `Profile` quando você especifica `application/json` com o cabeçalho `Accept` de uma solicitação. O escopo da saída de JSON depende dos parâmetros que você especifica com a solicitação. Ele também depende de o texto de entrada representar dados com registro de data e hora, como o texto associado a um feed do Twitter.
{: shortdesc}

As seções a seguir descrevem os conteúdos de uma resposta em formato JSON. Toda a saída de exemplo é produzida pelo arquivo JSON de amostra <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="Ícone de link externo" title="Ícone de link externo"></a> que é usado no [Tutorial de introdução](/docs/services/personality-insights?topic=personality-insights-gettingStarted). Para obter informações sobre a saída em CSV, consulte [Entendendo um perfil CSV](/docs/services/personality-insights?topic=personality-insights-outputCSV).

## O objeto Profile
{: #outputJSON}

O objeto `Profile` é o objeto de JSON de nível superior que é retornado pelo serviço. O objeto tem os campos a seguir:

-   `word_count` (número inteiro) fornece o número de palavras do conteúdo de entrada que foram usadas para gerar o perfil. Esse valor poderá ser menor que o número de palavras na entrada se a solicitação enviou uma grande quantia de conteúdo. Se o número de palavras falhar em atender a um limite mínimo, a saída incluirá um campo `word_count_message` que fornecerá orientação adicional.
-   `processed language` (sequência) descreve o modelo de idioma que o serviço usou para processar a entrada: `ar` (árabe), `en` (inglês), `es` (espanhol), `ja` (japonês) ou `ko` (coreano).
-   `personality` é uma matriz recursiva de objetos `Trait` que descreve as dimensões e os aspectos do Big Five que são inferidos por meio do texto de entrada.
-   `needs` é uma matriz de objetos `Trait` que descreve as Necessidades que são inferidas por meio do texto de entrada.
-   `values` é uma matriz de objetos `Trait` que descreve os Valores que são inferidos por meio do texto de entrada.
-   `behavior` é uma matriz de objetos `Behavior` que descreve a distribuição do conteúdo pelos dias da semana e as horas do dia. O serviço retorna o campo apenas para entrada JSON com registro de data e hora.
-   `consumption_preferences` é uma matriz de objetos `ConsumptionPreferencesCategory` que fornece resultados para cada categoria de preferências de consumo. Os elementos da matriz fornecem informações para as preferências individuais dessa categoria. O serviço retornará o campo apenas se o parâmetro de consulta `consumption_preferences` da solicitação for configurado para `true`.
-   `warnings` é uma matriz de objetos `Warning` que fornece mensagens sobre o texto de entrada. A matriz estará vazia se a entrada não tiver gerado avisos.

### Resposta de exemplo
{: #JSONExample}

A saída de exemplo a seguir mostra a estrutura de alto nível de um objeto `Profile`. A saída sempre inclui os campos `personality`, `needs` e `values`. Se a entrada tiver registro de data e hora JSON, a resposta incluirá o campo `behavior`. E se a solicitação também solicitar preferências de consumo, a resposta incluirá o campo `consumption_preferences`. Neste exemplo, a entrada não gera avisos.

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

## Saída de características da personalidade
{: #traitJSON}

O objeto `Profile` sempre inclui os campos `personality`, `needs` e `values` para todos os tipos de entrada. Cada um desses campos contém uma matriz de objetos `Trait` que descreve as características da personalidade para os atributos desse tipo de característica. Para as características de Necessidades e Valores, a matriz tem um único nível que descreve as características. Para características do Big Five, uma matriz de nível superior descreve as dimensões e as matrizes de segundo nível descrevem os aspectos de cada dimensão.

-   `trait_id` (sequência) é o ID exclusivo da característica à qual os resultados pertencem:
    -   `big5_{characteristic}` para as dimensões de personalidade do Big Five
    -   `facet_{characteristic}` para os aspectos de personalidade do Big Five
    -   `need_{characteristic}` para as Necessidades
    -   `value_{characteristic}` para os Valores
-   `name` (sequência) é o nome visível pelo usuário da característica.
-   `category` (sequência) é a categoria da característica:
    -   `personality` para as características da personalidade do Big Five
    -   `needs` para Necessidades
    -   `values` para Valores
-   `percentile` (duplo) é a pontuação em percentil normalizada para a característica. Para obter mais informações, consulte [Percentis para características da personalidade](/docs/services/personality-insights?topic=personality-insights-numeric#percentiles).
-   `raw_score` (duplo) é a pontuação bruta para a característica. O campo é retornado apenas se você solicitar pontuações brutas configurando o parâmetro de consulta `raw_scores` para `true`. Para obter mais informações, consulte [Pontuações brutas para características da personalidade](/docs/services/personality-insights?topic=personality-insights-numeric#rawScores-numeric).
-   `significant` (booleano) indica se a característica é significativa para o idioma de entrada. O campo é sempre `true` para todas as características de entrada em inglês, espanhol e japonês. O campo é `false` para o subconjunto de características de entrada em árabe e coreano para o qual os modelos do serviço são incapazes de gerar resultados significativos. Para obter mais informações, veja [Limitações para entrada em árabe e coreano](/docs/services/personality-insights?topic=personality-insights-numeric#limitations).
-   `children` é uma matriz de objetos `Trait` que fornece resultados mais detalhados para os aspectos de cada dimensão do Big Five conforme inferido do texto de entrada. A matriz é retornada apenas para dimensões do Big Five.

### Resposta de exemplo
{: #traitExample}

A saída de exemplo a seguir mostra fragmentos da saída para as características do Big Five, Necessidades e Valores. Conforme descrito, apenas as características do Big Five têm uma matriz de `children` para seus respectivos aspectos.

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

## Saída comportamental
{: #behaviorJSON}

Se a entrada para o serviço for em JSON com registros de data e hora para os itens de conteúdo individuais, o objeto `Profile` incluirá um campo `behavior`. O campo inclui um objeto `Behavior` para cada dia da semana e hora do dia.

-   `trait_id` (sequência) é o ID exclusivo da característica à qual os resultados pertencem:
    -   `behavior_{day}` para dias da semana (por exemplo, `behavior_sunday`).
    -   `behavior_{hour}` para horas do dia (por exemplo, `behavior_0000`).
-   `name` (sequência) é o nome visível pelo usuário da característica.
-   `category` (sequência) é a categoria da característica, que sempre é `behavior`.
-   `percentage` (duplo) é a porcentagem de itens de conteúdo que ocorreram durante esse dia da semana ou hora do dia. Para obter mais informações, consulte [Porcentagens para características comportamentais](/docs/services/personality-insights?topic=personality-insights-numeric#percentages).

### Resposta de exemplo
{: #behaviorExample}

A saída a seguir mostra fragmentos da saída comportamental para características temporais.

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

## Saída de preferências de consumo
{: #preferenceJSON}

Se o parâmetro de consulta `consumption_preferences` for configurado para `true`, o objeto `Profile` incluirá um campo `consumption_preferences`. O campo inclui um objeto `ConsumptionPreferencesCategory` para cada categoria de preferências.

-   `consumption_preference_category_id` (sequência) é o ID exclusivo da categoria de preferências de consumo à qual os resultados pertencem no formato `consumption_preferences_{category}`.
-   `name` (sequência) é o nome da categoria de preferências de consumo visível para o usuário.
-   `consumption_preferences` é uma matriz de objetos `ConsumptionPreferences` que fornece resultados para as preferências individuais da categoria.

Cada preferência individual de uma categoria é descrita por meio do objeto `ConsumptionPreferences`. Algumas categorias têm somente uma preferência única; outras categorias têm muito mais.

-   `consumption_preference_id` (sequência) é o ID exclusivo da preferência de consumo à qual os resultados pertencem no formato `consumption_preferences_{preference}`.
-   `name` (sequência) é o nome da preferência consumo visível para o usuário.
-   `score` (duplo) é uma pontuação que indica a probabilidade de o autor preferir o item. Para obter mais informações, consulte [Pontuações para preferências de consumo](/docs/services/personality-insights?topic=personality-insights-numeric#scores).

### Resposta de exemplo
{: #preferenceExample}

A saída a seguir mostra fragmentos da saída para as preferências de consumo.

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
