---

Copyright: years: 2015, 2017 lastupdated: "2017-10-28"

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

# Entendendo um perfil JSON
{: #output}

Quando você usa o `POST /v3/profile` método para analisar o conteúdo, o serviço retorna os resultados de sua análise como um JSON `Perfil` objeto por padrão ou quando você especificar `application / json` com o `Aceitar` cabeçalho de uma solicitação. O escopo da saída JSON depende dos parâmetros que você especificou com a solicitação e se o texto de entrada representa dados com registro de data e hora, como o texto associado a um feed do Twitter.
{: shortdesc}

As seções a seguir descrevem o conteúdo de uma resposta em formato JSON. Toda saída de exemplo é produzido pela amostra JSON no arquivo <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="External link icon" title="External link icon" class="style-scope doc-content"></a> que é usado no [Introdução ao tutorial](/docs/services/personality-insights/getting-started.html). Para obter informações sobre a saída CSV, consulte [Entendendo um perfil CSV](/docs/services/personality-insights/output-csv.html).

## O objeto Perfil
{: #outputJSON}

O `Perfil` objeto é o objeto JSON de nível superior retornado pelo serviço. O objeto possui os seguintes campos:

-   `word_count` (inteiro) fornece o número de palavras do conteúdo de entrada que foram usados para gerar o perfil. Isso pode ser menor que o número de palavras na entrada se a solicitação enviada uma grande quantidade de conteúdo. Se o número de palavras não atender um limite mínimo, a saída também inclui um `word_count_message` campo que fornece orientação adicional.
-   `processados idioma` (sequência) descreve o modelo de linguagem que o serviço utilizado para processar a entrada: `عندما` (Árabe), `en` (inglês), `es` (Espanhol), `ja` (Japonês), ou `ko` (Coreano).
-   `Personalidade` é uma matriz recursiva de `Característica` objetos que descreve o Big Five dimensões e aspectos inferido a partir do texto de entrada.
-   `precisa` é uma matriz de `Peculiaridade` objetos que descreve as Necessidades inferido do texto de entrada.
-   `valores` é uma matriz de `Peculiaridade` objetos que descreve os valores inferidos do texto de entrada.
-   `comportamento` é uma matriz de `Comportamento` objetos que descreve a distribuição do conteúdo sobre os dias da semana e as horas do dia. O serviço retorna o campo apenas para entrada JSON que é hora.
-   `consumption_preferences` é uma matriz de objetos `ConsumptionPreferencesCategory` que fornece resultados para cada categoria de preferências de consumo. Os elementos da matriz fornecem informações para as preferências individuais dessa categoria. O serviço retorna o campo apenas se o `consumption_preferences` parâmetro de consulta da solicitação é configurado como `true`.
-   `avisos` é uma matriz de `Aviso` objetos que fornece mensagens associadas com o texto de entrada. A matriz está vazia se a entrada gerada não tem avisos.

### Exemplo de resposta
{: #JSONExample}

A saída de exemplo a seguir mostra a estrutura de alto nível de um `Perfil` objeto. A saída sempre inclui o `pessoa`, `precisa`, e `valores` campos. Se a entrada for data JSON, a resposta inclui o `comportamento` campo. E se a solicitação também pede preferências de consumo, a resposta inclui o `consumption_preferences` campo. Neste exemplo, a entrada não gera avisos.

```javascript
{
  "Word_count": 15223, "processed_language": "en", "personalidade": [
     . . .
  ], "precisa": [
     . . .
  ], "valores": [
     . . .
  ], "comportamento": [
     . . .
  ],
  "consumption_preferences": [
     . . .
   ], "warnings": [ ]
}
```
{: codeblock}

## Saída características de personalidade
{: #traitJSON}

O `Perfil` objeto sempre inclui `Personalidade`, `precisa`, e `valores` campos para todos os tipos de entrada. Cada um desses campos contém uma matriz de `Peculiaridade` objetos que descreve as características da personalidade para os atributos desse tipo de característica. Para Necessidades e Valores características, a matriz possui um único nível que descreve as características. Para características Big Five, uma matriz de nível superior descreve as dimensões e as matrizes de segundo descrevem os aspectos de cada dimensão.

-   `trait_id` (sequência) é o ID exclusivo do característica para o qual o resultado pertencem:
    -   `big5_characteristic` para as dimensões da personalidade Big Five
    -   `facet_characteristic` para Big Five aspectos da personalidade
    -   `need_characteristic` para Necessária
    -   `value_characteristic` para Valores
-   `name` (sequência) é o usuário visível nome da característica.
-   `categoria` (sequência) é a categoria da característica:
    -   `Personalidade` para as características da personalidade Big Five
    -   `precisa` para Necessária
    -   `valores` para Valores
-   `percentile` (dobro) é o escore percentil normalizado para a característica. Para obter mais informações, consulte [percentis para características da personalidade](/docs/services/personality-insights/numeric.html#percentiles).
-   `raw_score` (duplo) é o resultado bruto para a característica. O campo é retornado apenas se você solicitar notas brutas configurando o `raw_scores` parâmetro de consulta para `true`. Para obter mais informações, consulte [pontuações para características da personalidade bruta](/docs/services/personality-insights/numeric.html#rawScores).
-   `significativo` (boolean) indica se a característica é significativo para o idioma de entrada. O campo é sempre `true` para todas as características de inglês, espanhol, e a entrada do Japão. O campo é `false` para o subconjunto de características de entrada árabe e coreano para o qual os modelos do serviço são incapazes de gerar resultados significativos. Para obter mais informações, consulte [Limitações para entrada árabe e coreano](/docs/services/personality-insights/numeric.html#limitations).
-   `filhos` é uma matriz de `Peculiaridade` objetos que fornece resultados mais detalhados para os aspectos de cada dimensão Big Five como inferido a partir do texto de entrada. A matriz é retornado apenas para dimensões Big Five.

### Exemplo de resposta
{: #traitExample}

A saída de exemplo a seguir mostra fragmentos da saída para o Big Five, Necessidades, e Valores características. Conforme descrito, apenas o Big Five características ter uma matriz de `filhos` para seus respectivos aspectos.

```javascript
{
  . . .
  "Personalidade": [ {
      "Trait_id": "big5_openness", "name": "Openness", "category": "personalidade", "percentil": 0,8011555009553, "raw_score": 0,77565404255038, "significativa": true, "crianças": [ {
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
      "Trait_id": "big5_conscientiousness", "name": "consciente", "category": "personalidade", "percentil": 0,81001753184176, "raw_score": 0,66899984888815, "significativa": true, "crianças": [ {
          "Trait_id": "facet_achievement_striving", "name": "Melhor esforço", "category": "personalidade", "percentil": 0,84613299226628, "raw_score": 0,74240118454888, "significativa": true },
        . . .
      ]
    },
    {
      "Trait_id": "big5_extraversion", "name": "Extroversão", "category": "personalidade", "percentil": 0,64980796071382, "raw_score": 0,56817738781166, "significativa": true, "crianças": [ {
          "Trait_id": "facet_activity_level", "name": "nível de atividade", "category": "personalidade", "percentil": 0,88220584913965, "raw_score": 0,60106995926143, "significativa": true }, ]
    },
    {
      "Trait_id": "big5_agreeableness", "name": "Afabilidade", "category": "personalidade", "percentil": 0,94786124793821, "raw_score": 0,80677815631809, "significativa": true, "crianças": [ {
          "Trait_id": "facet_altruism", "name": "Altruísmo", "category": "personalidade", "percentil": 0,99241983824205, "raw_score": 0,79028406290747, "significativa": true },
        . . .
      ]
    },
    {
      "Trait_id": "big5_neuroticism", "name": "Emotivas intervalo", "category": "personalidade", "percentil": 0,5008224041628, "raw_score": 0,46748200007024, "significativa": true, "crianças": [ {
          "Trait_id": "facet_anger", "name": "Furioso", "category": "personalidade", "percentil": 0,17640022058508, "raw_score": 0,48490315691802, "significativa": true },
        . . .
      ]
    }
  ], "precisa": [ {
      "Trait_id": "need_challenge", "name": "Challenge", "categoria": "necessidades", "percentil": 0,67362332054511, "raw_score": 0,75196348037675, "significativa": true },
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

## Comportamento de saída
{: #behaviorJSON}

Se a entrada para o serviço é JSON que tem os registros para os itens de conteúdo individuais, o `Perfil` objeto inclui um `comportamento` campo. O campo inclui um `Comportamento` do objeto para cada dia da semana e hora do dia.

-   `trait_id` (sequência) é o ID exclusivo do característica para o qual o resultado pertencem:
    -   `behavior_day` para dias da semana (por exemplo, `behavior_sunday`).
    -   `behavior_hour` para horas do dia (por exemplo, `behavior_0000`).
-   `name` (sequência) é o usuário visível nome da característica.
-   `categoria` (sequência) é a categoria do característica, que é sempre `comportamento`.
-   `porcentagem` (duplo) é a porcentagem de itens de conteúdo que ocorreram durante esse dia da semana ou hora do dia. Para obter mais informações, consulte [Classificações para características comportamentais](/docs/services/personality-insights/numeric.html#percentages).

### Exemplo de resposta
{: #behaviorExample}

A saída a seguir mostra fragmentos da saída comportamental para características temporais.

```javascript
{
  . . .
  "Comportamento": [ {
      "Trait_id": "behavior_sunday", "name": "Sunday", "category": "comportamento", "porcentagem": 0,21392532795156
    },
    {
      "Trait_id": "behavior_monday", "name": "Segunda-feira", "category": "comportamento", "porcentagem": 0,42583249243189
    },
    . . .
    {
      "Trait_id": "behavior_saturday", "name": "sábado", "category": "comportamento", "porcentagem": 0,077699293642785
    },
    {
      "Trait_id": "behavior_0000", "name": "00:00", "category": "comportamento", "porcentagem": 0,4561049445005
    },
    {
      "Trait_id": "behavior_0100", "name": "01:00", "category": "comportamento", "porcentagem": 0,12209889001009
    },
    . . .
    {
      "Trait_id": "behavior_2300", "name": "23:00", "category": "comportamento", "porcentagem": 0,12310797174571 }
  ],
  . . .
}
```
{: codeblock}

## Saída de preferências de consumo
{: #preferenceJSON}

Se o parâmetro de consulta `consumption_preferences` está configurado como `true`, o objeto `Profile` inclui um campo `consumption_preferences`. O campo inclui um `ConsumptionPreferencesCategory` do objeto para cada categoria de preferências.

-   `consumption_preference_category_id` (sequência) é o ID exclusivo da categoria preferências de consumo ao qual o pertence resultados no formato `consumption_preferences_ {`.
-   `name` (sequência) é o nome visível do usuário da categoria de preferências de consumo.
-   `consumption_preferences` é uma matriz de `ConsumptionPreferences` objetos que fornece resultados para as preferências individuais da categoria.

Cada preferência individual para uma categoria é descrito através de um `ConsumptionPreferences` objeto. Algumas categorias têm apenas uma única preferência, outros têm muitos mais.

-   `consumption_preference_id` (sequência) é o ID exclusivo da preferência consumo na qual o pertencem resultados na forma `consumption_preferences_preference`.
-   `name` (sequência) é o usuário visível nome da preferência consumo.
-   `score` (duplo) é uma pontuação que indica a probabilidade do autor de preferir o item. Para obter mais informações, consulte [Escores para consumo preferências](/docs/services/personality-insights/numeric.html#scores).

### Exemplo de resposta
{: #preferenceExample}

A saída a seguir mostra fragmentos da saída para as preferências de consumo.

```javascript
{
  . . .
  "Consumption_preferences": [ {
      "Consumption_preference_category_id": "consumption_preferences_shopping", "name": "Preferências de Compras", "consumption_preferences": [ {
          "Consumption_preference_id": "consumption_preferences_automobile_ownership_cost", "name": "a ser sensível ao custo de propriedade ao comprar automóveis", "placar": 0
        },
        . . .
      ]
    },
    {
      "Consumption_preference_category_id": "consumption_preferences_health_and_activity", "name": "Preferências Health & Activity", "consumption_preferences": [ {
          "Consumption_preference_id": "consumption_preferences_eat_out", "name": "Propenso a comer fora frequentemente", "placar": 1
        },
        . . .
      ]
    },
    . . .
    {
      "Consumption_preference_category_id": "consumption_preferences_volunteering", "name": "Voluntariando Preferências", "consumption_preferences": [ {
          "Consumption_preference_id": "consumption_preferences_volunteer", "name": "a trabalhar como voluntário por causas sociais", "pontuação": 0 }
      ]
    }
  ],
  . . .
}
```
{: codeblock}
