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

# Notas sobre a liberação
{: #release-notes}

As seções a seguir documentam os novos recursos e as mudanças que foram incluídas em cada liberação do serviço do {{site.data.keyword.personalityinsightsshort}}. A menos que seja observado de outra forma, todas as alterações são compatíveis com liberações anteriores e são disponibilizadas de forma automática e transparente para todos os aplicativos novos e existentes.
{: shortdesc}

As notas sobre a liberação documentam a *versão do serviço* e a *versão da interface* para todas as atualizações recentes. Você especifica a *versão da interface* com o parâmetro de consulta `version` para usar novos recursos e funcionalidades disponibilizados com esta atualização. O serviço retorna ambas as versões com o cabeçalho de resposta `X-Service-Api-Version`.
{: note}

## 21 de dezembro de 2018
{: #December2018}

**Versão do serviço** - `3.4.5`<br/> **Versão da interface** - `2017-10-13`

A versão 2 da API do {{site.data.keyword.personalityinsightsshort}} foi removida do serviço. A versão 3 do serviço foi liberada em 19 de outubro de 2016. Naquele momento, os usuários foram fortemente encorajados a migrar da versão 2 o mais rápido possível.

## 18 de novembro de 2018
{: #November2018b}

**Versão do serviço** - `3.4.5`<br/> **Versão da interface** - `2017-10-13`

O serviço {{site.data.keyword.personalityinsightsshort}} agora está disponível no local de Londres do {{site.data.keyword.cloud}} (**eu-gb**). Como todos os locais, Londres usa a autenticação de Identidade e Gerenciamento de Acesso (IAM) baseada em token. Todas as novas instâncias de serviço que você cria nessa localização usam a autenticação do IAM.

## 7 de novembro de 2018
{: #November2018a}

**Versão do serviço** - `3.4.5`<br/> **Versão da interface** - `2017-10-13`

O serviço {{site.data.keyword.personalityinsightsshort}} agora está disponível no local de Tóquio do {{site.data.keyword.cloud_notm}} (**jp-tok**). Como todos os locais, Tóquio usa a autenticação do Identity and Access Management (IAM) baseada em token. Todas as novas instâncias de serviço que você cria nessa localização usam a autenticação do IAM.

## Liberações mais antigas
{: #older}

-   [30 de outubro de 2018](#October2018)
-   [11 de junho de 2018](#June2018b)
-   [4 de junho de 2018](#June2018a)
-   [23 de março de 2018](#March2018)
-   [13 de outubro de 2017](#October2017)
-   [18 de setembro de 2017](#September2017)
-   [10 de abril de 2017](#April2017)
-   [1 de março de 2017](#March2017)
-   [20 de fevereiro de 2017](#February2017b)
-   [13 de fevereiro de 2017](#February2017)
-   [13 de janeiro de 2017](#January2017)
-   [15 de dezembro de 2016](#December2016)
-   [15 de novembro de 2016](#November2016)
-   [20 de outubro de 2016](#October2016b)
-   [12 de outubro de 2016](#October2016a)
-   [31 de agosto de 2016](#August2016)
-   [14 de julho de 2016](#July2016b)
-   [1 de julho de 2016](#July2016a)
-   [7 de junho de 2016](#June2016b)
-   [1 de junho de 2016](#June2016a)
-   [17 de maio de 2016](#May2016)
-   [18 de março de 2016](#March2016)
-   [9 de julho de 2015](#July2015)
-   [23 de fevereiro de 2015](#February2015)

### 30 de outubro de 2018
{: #October2018}

**Versão do serviço** - `3.4.5`<br/> **Versão da interface** - `2017-10-13`

O serviço {{site.data.keyword.personalityinsightsshort}} migrou para a autenticação do Identity and Access Management (IAM) baseada em token para todos os locais. Todos os serviços do {{site.data.keyword.cloud_notm}} agora usam a autenticação do IAM. O serviço {{site.data.keyword.personalityinsightsshort}} migrou em cada local nas datas a seguir:

-   Dallas (**us-south**): 30 de outubro de 2018
-   Frankfurt (**eu-de**): 30 de outubro de 2018
-   Washington, DC (**us-east**): 11 de junho de 2018
-   Sydney (**au-syd**): 4 de junho de 2018

A migração para a autenticação do IAM afeta as instâncias de serviço novas e existentes de forma diferente:

-   *Todas as novas instâncias de serviço que você cria em qualquer local* agora usam a autenticação do IAM para acessar o serviço. É possível passar um token de acesso ou uma chave de API: os tokens suportam solicitações autenticadas sem incorporar as credenciais de serviço em cada chamada; as chaves de API usam a autenticação básica de HTTP. Quando você usa qualquer um dos SDKs do {{site.data.keyword.watson}}, é possível passar a chave de API e deixar que o SDK gerencie o ciclo de vida dos tokens.
-   *Instâncias de serviço existentes que você criou em um local antes da data de migração indicada* continuam a usar o `{username}` e a `{password}` por meio de suas credenciais de serviço do Cloud Foundry anteriores para autenticação até que você os atualize para usar a autenticação do IAM. Como o serviço {{site.data.keyword.personalityinsightsshort}} é sem estado, será possível executar as etapas a seguir para converter uma instância de serviço existente para usar a autenticação do IAM:

    1.  Exclua e recrie a instância de serviço.
    1.  Modifique o código do aplicativo para usar a autenticação do IAM.

Para obter mais informações, consulte a documentação a seguir:

-   Para saber qual mecanismo de autenticação a sua instância de serviço usa, visualize as suas credenciais de serviço clicando na instância no painel do [{{site.data.keyword.cloud_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://{DomainName}/dashboard/apps){: new_window}.
-   Para obter mais informações sobre como usar tokens do IAM com serviços do Watson, consulte [Autenticando com tokens do IAM](/docs/services/watson?topic=watson-iam).
-   Para obter mais informações sobre como usar as chaves de API do IAM com serviços do Watson, consulte [Chaves de API de serviço do IAM](/docs/services/watson?topic=watson-api-key-bp).
-   Para obter exemplos que usam a autenticação do IAM, consulte a [Referência da API ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://{DomainName}/apidocs/personality-insights){: new_window}.

### 11 de junho de 2018
{: #June2018b}

**Versão do serviço** - `3.4.5`<br/> **Versão da interface** - `2017-10-13`

Para instâncias de serviço e aplicativos que são hospedados em Washington, DC (**us-east**), o serviço agora suporta um novo processo de autenticação de API. Para obter mais informações, consulte a [atualização de serviço de 30 de outubro de 2018](#October2018).

### 4 de junho de 2018
{: #June2018a}

**Versão do serviço** - `3.4.5`<br/> **Versão da interface** - `2017-10-13`

Para instâncias de serviço e aplicativos que estão hospedados em Sydney (**au-syd**), o serviço agora suporta um novo processo de autenticação de API. Para obter mais informações, consulte a [atualização de serviço de 30 de outubro de 2018](#October2018).

### 23 de março de 2018
{: #March2018}

**Versão do serviço** - `3.4.4`<br/> **Versão da interface** - `2017-10-13`

-   O serviço foi atualizado com pequenas correções de defeito. As mudanças foram específicas para os idiomas árabe, japonês e coreano.
-   O cabeçalho da solicitação `Accept` é agora necessário com o método `POST /v3/profile`. Deve-se especificar `application/json` ou `text/csv`.

### 13 de outubro de 2017
{: #October2017}

**Versão do serviço** - `3.4.0`<br/> **Versão da interface** - `2017-10-13`

-   O objeto `Trait` de um perfil de personalidade agora inclui um campo `significant`. Um objeto `Trait` separado relata os resultados para cada dimensão do Big Five, aspecto do Big Five, Necessidade e Valor. O campo `significativo` de cada instância do objeto identifica se os resultados para a característica são significativos para o idioma de entrada (`Content-Language`) da solicitação:

    -   Para inglês, espanhol e japonês, o campo é sempre `true` para todas as características da personalidade.
    -   Para árabe e coreano, o campo é `true` para a maioria das características de personalidade, mas é `false` para características para as quais os modelos do serviço são incapazes de produzir resultados significativos. O campo é `false` para um conjunto constante de características. Para obter uma lista completa, consulte [Limitações para entrada em árabe e coreano](/docs/services/personality-insights?topic=personality-insights-numeric#limitations). Não confie nos resultados de qualquer característica para a qual o campo é `false`.

    Para obter mais informações sobre o conteúdo de resposta de JSON do serviço, consulte [Entendendo um perfil de JSON](/docs/services/personality-insights?topic=personality-insights-output).
-   A saída CSV também inclui agora colunas cujos títulos são denominados `* _significante`. Cada coluna fornece um valor booleano para indicar se uma característica é significativa. Para obter mais informações sobre o conteúdo de resposta do CSV do serviço, consulte [Entendendo um perfil do CSV](/docs/services/personality-insights?topic=personality-insights-outputCSV).
-   Para usar essa versão mais recente da interface, especifique a versão da interface `2017-10-13` com o parâmetro `version`.

### 18 de setembro de 2017
{: #September2017}

**Versão do serviço**- `3.3.0`<br/> **Versão da interface** - `2016-10-19`

O serviço agora suporta conteúdo de entrada em coreano (`ko`). Para obter mais informações sobre o Erro médio absoluto (MAE) médio e a correlação média para a entrada em coreano, consulte [MAE e correlação médios por idioma](/docs/services/personality-insights?topic=personality-insights-science#precisePerLanguage).

Os modelos do serviço são incapazes de produzir percentis significativos e pontuações brutas para algumas características de personalidade de entrada em coreano. Para obter mais informações sobre os resultados para essas características, veja [Limitações para entrada em árabe e coreano](/docs/services/personality-insights?topic=personality-insights-numeric#limitations).

### 10 de abril de 2017
{: #April2017}

**Versão do serviço** - `3.1.7`<br/> **Versão da interface** - `2016-10-19`

-   O serviço mudou como manipula solicitações com grandes quantias de conteúdo de entrada. O serviço aceita no máximo 20 MB de conteúdo. No entanto, para os modelos que são baseados em *GloVe*, os níveis de precisão são desligados em torno de 3000 palavras de entrada. Esse comportamento é diferente dos modelos mais antigos, em que mais texto produziu maior precisão. Em geral, o serviço não precisa mais de tanto conteúdo para produzir um perfil preciso. Mas mais conteúdo requer mais tempo de processamento, o que pode fazer com que uma solicitação atinja o tempo limite antes de ser concluída.

    Portanto, o serviço agora extrai e usa apenas os primeiros 250 KB de conteúdo, sem contar qualquer marcação de HTML ou JSON, de solicitações grandes. Esta figura não é mapeada para um número exato de palavras, que varia com base na linguagem e natureza do texto. Em inglês, por exemplo, o comprimento médio de palavra fica entre quatro e cinco caracteres, portanto, esse número fornece cerca de 50.000 palavras, que é pelo menos 15 vezes mais palavras do que o serviço precisa. O campo `word_count` do JSON de resposta indica o número de palavras que o serviço usa para uma solicitação, que pode ser menor que o número de palavras na entrada.

    Como ele ainda baseia um perfil em muito mais palavras do que estritamente precisa para máxima precisão, o serviço produz um perfil que é tão preciso quanto no passado. No entanto, o serviço responde muito mais rapidamente do que antes. Para solicitações para as quais usa apenas uma parte do conteúdo de entrada, o serviço retorna a mensagem de aviso `CONTENT_TRUNCATED` a seguir para tornar o usuário ciente do fato:

    `For maximum accuracy while also optimizing processing time, only the first 250KB of input text (excluding markup) was analyzed. Accuracy levels off at approximately 3K words so this did not affect the accuracy of the profile.`

    Para obter mais informações, consulte [Fornecendo entrada suficiente](/docs/services/personality-insights?topic=personality-insights-input#sufficient).
-   O serviço foi atualizado com pequenas correções de segurança.

### 1 de março de 2017
{: #March2017}

**Versão do serviço** - `3.1.6`<br/> **Versão da interface** - `2016-10-19`

O serviço foi atualizado com pequenos aprimoramentos para criação de log.

### 20 de fevereiro de 2017
{: #February2017b}

**Versão do serviço** - `3.1.5.1`<br/> **Versão da interface** - `2016-10-19`

O serviço foi atualizado com pequenas correções de segurança e defeitos e para melhorar a medição de chamadas de API.

### 13 de fevereiro de 2017
{: #February2017}

**Versão do serviço** - `3.1.4`<br/> **Versão da interface** - `2016-10-19`

-   A lista de preferências de consumo foi refinada. A lista agora inclui apenas as preferências que são mais importantes para entender os hábitos de estilo de vida e as características do consumidor dominantes do indivíduo. A lista de preferências de consumo foi abreviada de 51 para 42. As preferências restantes expressam mais concisamente a probabilidade do autor de preferir diferentes produtos, serviços e atividades, tornando ainda mais fácil agir sobre os resultados.

    O serviço não retorna mais as nove preferências de consumo a seguir:

    -   A categoria <code>consumption_preferences_shopping</code> não inclui mais
        -   <code>consumption_preferences_automobile_resale_value</code>
    -   A categoria <code>consumption_preferences_reading</code> não inclui mais
        -   <code>consumption_preferences_read_motive_enjoyment</code><br/>
        -   <code>consumption_preferences_read_motive_information</code><br/>
        -   <code>consumption_preferences_read_motive_mandatory</code><br/>
        -   <code>consumption_preferences_read_motive_relaxation</code>
    -   A categoria <code>consumption_preferences_health_and_activity</code> não inclui mais
        -   <code>consumption_preferences_aventurous_sports</code>
        -   <code>consumption_preferences_fast_food_frequency</code>
    -   A categoria <code>consumption_preferences_voluntariering</code>não inclui mais
        -   <code>consumption_preferences_volunteering_time</code>
        -   <code>consumption_preferences_volunteer_learning</code>

    Para obter mais informações sobre as preferências restantes, consulte [Preferências de consumo](/docs/services/personality-insights?topic=personality-insights-preferences).
-   *Para entrada em árabe*, informações sobre o Erro Médio Absoluto (MAE) médio e a correlação média agora estão disponíveis em [MAE e correlação médios por idioma](/docs/services/personality-insights?topic=personality-insights-science#precisePerLanguage). Além disso, os modelos do serviço são incapazes de produzir percentis significativas e pontuações brutas para uma coleção de características da personalidade. Para obter mais informações sobre os resultados para essas características, veja [Limitações para entrada em árabe e coreano](/docs/services/personality-insights?topic=personality-insights-numeric#limitations).

### 13 de janeiro de 2017
{: #January2017}

**Versão do serviço** - `3.1.2.1`<br/> **Versão da interface** - `2016-10-19`

O serviço do Personality Insights foi atualizado com algumas pequenas correções de defeitos.

### 15 de dezembro de 2016
{: #December2016}

**Versão do serviço** - `3.1.1`<br/> **Versão da interface** - `2016-10-19`

Para o texto de entrada em árabe, o serviço {{site.data.keyword.personalityinsightsshort}} agora usa *GloVe* para desenvolver um perfil de personalidade. O serviço não usa mais o dicionário de psicolinguística Linguistic Inquiry and Word Count (LIWC) para qualquer idioma. Para obter mais informações sobre como o serviço desenvolve um perfil de personalidade, consulte [Como características da personalidade são inferidas](/docs/services/personality-insights?topic=personality-insights-science#researchInfer).

### 15 de novembro de 2016
{: #November2016}

**Versão do serviço** - `3.1.0`<br/> **Versão da interface** - `2016-10-19`

-   Para o texto de entrada em japonês, o serviço {{site.data.keyword.personalityinsightsshort}} agora usa o *GloVe* para desenvolver um perfil de personalidade. O serviço não usa mais o dicionário de psicolinguística Linguistic Inquiry and Word Count (LIWC) para entrada em japonês. Para obter mais informações, consulte [Como características da personalidade são inferidas](/docs/services/personality-insights?topic=personality-insights-science#researchInfer).
-   Os campos `name` dos objetos `ConsumptionPreferencesCategory` e `ConsumptionPreferences` agora são retornados com sequências localizadas no idioma que é especificado com o cabeçalho da solicitação `Accept-Language`.
-   A atualização inclui algumas pequenas correções de defeitos.

### 20 de outubro de 2016
{: #October2016b}

**Versão do serviço** - `3.0.0`<br/> **Versão da interface** - `2016-10-19`

O serviço do {{site.data.keyword.personalityinsightsshort}} e sua API foram atualizados de forma significativa. A API foi incrementada da versão 2 para a versão 3 e oferece novos recursos. As seções restantes desta nota sobre a liberação descrevem as mudanças em detalhes.

A Versão 3 não é compatível com a versão 2. Você é encorajado a migrar para a versão 3 para tirar proveito dos novos recursos e mudanças. A migração para a versão 3 consiste apenas em atualizar e reimplementar os seus aplicativos para usarem as mudanças que são descritas nestas notas sobre a liberação para a nova versão. Não é necessário criar uma nova instância do serviço no {{site.data.keyword.cloud_notm}}; você precisa apenas chamar a API `v3`.

A versão 2 da API do {{site.data.keyword.personalityinsightsshort}} deve ser removida do serviço em breve. É altamente recomendável migrar para a versão 3 assim que possível.
{: note}

#### Mais informações sobre a versão 3

Esta documentação agora descreve a versão 3 da API do {{site.data.keyword.personalityinsightsshort}}. As seções a seguir resumem as mudanças para a nova versão da interface:

-   Para obter mais informações sobre como chamar o método `/v3/profile`, consulte [Solicitando um perfil](/docs/services/personality-insights?topic=personality-insights-input).
-   Para obter mais informações sobre a resposta do método `/v3/profile`, consulte [Entendendo um perfil de JSON](/docs/services/personality-insights?topic=personality-insights-output) e [Entendendo um perfil do CSV](/docs/services/personality-insights?topic=personality-insights-outputCSV).
-   Para obter mais informações sobre a interface da versão 3, consulte a [Referência da API ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://{DomainName}/apidocs/personality-insights){: new_window}.

#### Mudanças nos parâmetros do método <code>/v3/profile</code>

Os parâmetros do método `/v3/profile` mudaram:

-   A API agora oferece um parâmetro de consulta opcional denominado `consumption_preferences`. O parâmetro aceita um valor booleano que indica se as informações que são inferidas sobre preferências de consumo devem ser retornadas com os resultados. Por padrão, as informações não são incluídas na resposta. Para obter mais informações, consulte [Novo recurso de preferências de consumo](#cp).
-   A API agora inclui um parâmetro de consulta `version` necessário. O parâmetro aceita uma sequência que identifica a versão solicitada da API e o formato de resposta como uma data no formato `YYYY-MM-DD`; por exemplo, especifique `2016-10-19` para 19 de outubro de 2016. Esse parâmetro permite que o serviço atualize sua API ou formato de resposta para novas versões sem interromper clientes existentes. A sequência inicial para a versão 3 da API é `2016-10-19`.

    A data que você especifica não precisa corresponder exatamente a uma versão do serviço. O serviço usa a versão que não é posterior à data que você fornece. Se você especificar uma data que seja anterior à data de liberação da versão 3, o serviço usará a versão 3 da API. Se você especificar uma data que esteja no futuro ou que seja posterior à versão mais recente, o serviço usará a versão mais recente.
-   O nome do parâmetro de consulta `include_raw` agora é `raw_scores`.
-   O nome do parâmetro de consulta `headers` agora é `csv_headers`.

#### Novo recurso de preferências de consumo
{: #cp}

O recurso de preferências de consumo fornece uma indicação de tendência do autor para exibir diferentes tendências de consumo. Quando você passar o parâmetro de consulta `consumption_preferences` com um valor `true` para o método `/v3/profile`, o serviço retornará resultados extras com o objeto `Profile`:

-   Um campo `consumption_preferences` que fornece uma matriz de objetos `ConsumptionPreferencesCategory`.
-   Cada objeto `ConsumptionPreferencesCategory` inclui os campos a seguir:
    -   `consumption_preference_category_id`: o ID de uma das categorias de preferências de consumo
    -   `name`: o nome da categoria visível pelo usuário.
    -   `consumption_preferences`: uma matriz de objetos `ConsumptionPreferences` que fornece resultados inferidos por meio do texto de entrada para as preferências individuais da categoria
-   Cada objeto `ConsumptionPreferences` inclui os campos a seguir:
    -   `consumption_preference_id`: o ID de uma das preferências de consumo.
    -   `name`: o nome da preferência consumo visível para o usuário.
    -   `score`: a pontuação para a preferência de consumo:

        -   `0.0` indica improvável
        -   `0.5` indica neutralidade
        -   `1.0`indica provável

        As pontuações para algumas preferências são binárias e não permitem um valor neutro. A pontuação é uma indicação de preferência com base nos resultados que são inferidos por meio do texto de entrada, não em um percentil normalizado.

Para obter mais informações sobre as preferências de consumo, consulte [Preferências de consumo](/docs/services/personality-insights?topic=personality-insights-preferences).

O campo `name` para ambos os objetos de preferências de consumo é sempre retornado em inglês, independentemente do idioma especificado com o cabeçalho da solicitação `Accept-Language`.
{: note}

#### Mudanças nos objetos e campos JSON

Objetos de JSON de entrada e saída e os seus campos foram simplificados e esclarecidos:

-   Os campos a seguir foram removidos dos objetos de JSON `ContentItem` que você pode passar para o método `/v3/profile` com uma solicitação:
    -   `userid`
    -   `sourceid`
    -   `charset` (anteriormente descontinuado)

    Você passa esses objetos no corpo de uma solicitação em JSON como elementos da matriz `contentItems` do objeto `Content`.
-   Os campos a seguir do objeto `Profile`JSON que é retornado pelo método `/v3/profile`foram alterados:
    -   Os campos a seguir foram removidos:
        -   `id`
        -   `source`
    -   O campo `tree` foi removido. Ele foi substituído por quatro novos campos:
        -   `personality` para as características da personalidade do Big Five
        -   `needs` para características de Necessidades.
        -   `values` para características de Valores.
        -   `behavior` para resultados temporais sobre a distribuição do conteúdo pelos dias da semana e as horas do dia. Esse campo é retornado apenas para entrada em JSON com registro de data e hora.

        Essa mudança efetivamente move os resultados para um nível mais alto no objeto JSON `Profile`, eliminando um nível de recursão.
    -   O nome do campo `processed_lang` agora é `processed_language`.
-   Os campos a seguir de objetos de JSON `Trait` que são retornados pelo método `/v3/profile` foram renomeados:
    -   O nome do campo `id` do objeto JSON `Trait` agora é `trait_id`.
    -   O nome do campo `percentage` do objeto JSON `Trait` agora é `percentile`.
-   Os campos a seguir de objetos de JSON `Trait` que são retornados pelo método `/v3/profile` foram removidos:
    -   `sampling_error`
    -   `raw_sampling_error`

    O serviço agora relata um Erro Médio Absoluto (MAE) médio que qualifica a precisão de seus resultados. Para obter mais informações sobre o MAE para diferentes quantias de texto de entrada, consulte [Fornecendo entrada suficiente](/docs/services/personality-insights?topic=personality-insights-input#sufficient).
-   Objetos JSON `Trait` ainda são retornados para os campos `personality`, `needs` e `values` do objeto `Profile`. Mas o campo `behavior` retorna uma matriz de objetos de JSON denominados `Behavior` que tem os campos a seguir:
    -   `trait_id`
    -   `name`
    -   `category`
    -   `percentage`

    Além disso, as informações comportamentais não são mais retornadas como uma árvore de valores. A saída consiste em uma única matriz que lista todas as características temporais (dia da semana e hora do dia).
-   O nome do campo `id` do objeto JSON `Warnings` que pode ser retornado pelo método `/v3/profile` agora é `warnings_id`.

#### Mudanças nos IDs de JSON
{: #ids}

Os IDs de JSON que o serviço retorna para o campo `trait_id` (anteriormente `id`) do `Trait` e o novo objeto `Behavior` mudaram:

-   Os IDs para as dimensões do Big Five agora começam com a sequência `big5_`.
-   Os IDs para aspectos do Big Five agora começam com a sequência `facet_`.
-   Os IDs para Necessidades agora começam com a sequência `need_`.
-   Os IDs para Valores agora começam com a sequência `value_`.
-   Os IDs para todas as características temporais agora começam com a sequência `behavior_`.
-   Os IDs para as características temporais que estão relacionados ao horário do dia do dia agora usam horário de quatro dígitos de 24 horas (por exemplo, `behavior_0000`) em vez de horário de 12 horas (por exemplo, `0:00 am`).
-   Todos os caracteres estão agora em minúsculas.
-   Os espaços e hifens são agora sublinhados.

#### Mudanças nos cabeçalhos de CSV
{: #headers}

Os cabeçalhos de coluna opcionais que o serviço pode retornar para a saída CSV foram alterados:

-   Todas as mudanças que são descritas para o `trait_id` da saída de JSON também se aplicam aos cabeçalhos do CSV.
-   Os cabeçalhos para pontuações brutas das dimensões do Big Five agora começam com a sequência `big5_`.
-   Os cabeçalhos para pontuações brutas dos aspectos do Big Five agora começam com a sequência `facet_`.
-   Os cabeçalhos para pontuações brutas de Necessidades agora começam com a sequência `need_`.
-   Os cabeçalhos para pontuações brutas de valores agora começam com a sequência `value_`.
-   O cabeçalho da coluna de idioma processado agora é `processed_language`, em vez de `processed_lang`.
-   As colunas `user` e `source_id` não são mais retornadas.
-   Todos os caracteres estão agora em minúsculas.
-   Os espaços e hifens são agora sublinhados.

#### Remoção do método <code>visualize</code>

A versão 2 da API do serviço incluía um método `visualize` descontinuado que era usado em uma liberação anterior para visualizar os resultados de uma chamada do método `/v3/profile`. O método `visualize` foi removido da API do serviço. O serviço continua a fornecer uma coleção de arquivos JavaScript que ativam a visualização gráfica de um perfil. Para obter mais informações, consulte [Visualizando um perfil](/docs/services/personality-insights?topic=personality-insights-overviewDevelopers#visualize).

### 12 de outubro de 2016
{: #October2016a}

Para o texto de entrada em espanhol, o serviço {{site.data.keyword.personalityinsightsshort}} agora usa *GloVe* para desenvolver um perfil de personalidade. O serviço não usa mais o dicionário de psicolinguística Linguistic Inquiry and Word Count (LIWC) para entrada em espanhol. O serviço começou a usar o novo modelo para texto de entrada em inglês em 31 de agosto. Ele planeja aplicar o novo modelo para os idiomas de entrada restantes em breve. Para obter mais informações sobre o novo modelo, consulte [Como características da personalidade são inferidas](/docs/services/personality-insights?topic=personality-insights-science#researchInfer).

### 31 de agosto de 2016
{: #August2016}

O serviço agora usa *GloVe* para desenvolver um perfil de personalidade. *GloVe* é uma técnica de integração de palavra de software livre. Para obter mais informações, consulte [Como características da personalidade são inferidas](/docs/services/personality-insights?topic=personality-insights-science#researchInfer). O serviço usa a nova abordagem apenas para o texto de entrada em inglês. Para outros idiomas, o serviço continua a usar o dicionário de psicolinguística do Linguistic Inquiry and Word Count (LIWC). O serviço planeja usar a abordagem de vocabulário aberto para todos os idiomas no futuro.

Para o novo modelo usado para entrada em inglês, o serviço relata o Erro Médio Absoluto (MAE) médio dos resultados para seu modelo treinado. Para obter mais informações sobre como o MAE é mudado com diferentes quantias de texto de entrada, consulte [Fornecendo entrada suficiente](/docs/services/personality-insights?topic=personality-insights-input#sufficient).

A {{site.data.keyword.IBM_notm}} planeja relatar o MAE para modelos que não estão em inglês no futuro. A {{site.data.keyword.IBM_notm}} planeja usar o MAE em vez de erros de amostragem para determinar como a precisão do serviço muda com base na quantia de texto de entrada que você fornece.

### 14 de julho de 2016
{: #July2016b}

-   Para entrada em árabe, o serviço agora pode cortar a quantia de texto de entrada por motivos de desempenho. Em um determinado limite, a precisão dos resultados para árabe não melhora com mais palavras. Se o serviço cortar o texto de entrada em árabe, ele retornará um aviso `PARTIAL_TEXT_USED` com a mensagem a seguir:

    `The text provided to compute the profile was trimmed for performance reasons. This action does not affect the accuracy of the output, as not all of the input text was required.`
-   A atualização inclui correções de defeito e melhorias internas.

### 1 de julho de 2016
{: #July2016a}

-   Os planos de precificação para o serviço agora oferecem preços mais baixos para os usuários do {{site.data.keyword.personalityinsightsshort}}. Para obter mais informações, consulte o serviço {{site.data.keyword.personalityinsightsshort}} no [Catálogo do {{site.data.keyword.cloud_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://{DomainName}/catalog/services/personality-insights/){: new_window}.
-   A lista de idiomas de resposta suportados que é possível especificar com o cabeçalho `Accept-Language` agora inclui
    -   `ar` (árabe)
    -   `de`
(Alemão)
    -   `en` (Inglês, o padrão)
    -   `es`
(Espanhol)
    -   `fr` (Francês)
    -   `it`
(Italiano)
    -   `ja` (Japonês)
    -   `ko`
(Coreano)
    -   `pt-br` (português do Brasil)
    -   `zh-cn` (chinês simplificado)
    -   `zh-tw` (chinês tradicional)

    Para obter mais informações, veja [Especificando linguagens de solicitação e resposta](/docs/services/personality-insights?topic=personality-insights-input#languages-input).
-   O método `/v2/profile` agora pode retornar os códigos de status HTTP a seguir:
    -   429 *Muitas solicitações*: o serviço está processando muitas solicitações para o idioma do conteúdo. Aguarde um curto tempo e tente a solicitação novamente. Se você estiver enviando muitas solicitações para o idioma, considere regular a taxa pela qual você envia solicitações.
    -   504 *Tempo limite do gateway*: a solicitação atingiu o tempo limite ou levou muito tempo para processar. Aguarde um curto tempo e tente a solicitação novamente. Se a entrada continha muitas palavras (por exemplo, mais de 20.000), considere reduzir o número de palavras, mas manter as diretrizes para entrada significativa.

    O método não retorna mais 503 *Serviço indisponível*. Para obter mais informações sobre possíveis códigos de resposta, consulte a [Referência de API ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://{DomainName}/apidocs/personality-insights){: new_window}.
-   A atualização inclui correções de defeito e melhorias internas.

### 7 de junho de 2016
{: #June2016b}

-   O serviço agora suporta o Compartilhamento de Recurso de Origem Cruzada (CORS) para permitir que os clientes baseados no navegador chamem o serviço diretamente. Para obter mais informações, consulte [Suporte ao CORS](/docs/services/personality-insights?topic=personality-insights-overviewDevelopers#CORS).
-   O desempenho do serviço para o texto em japonês melhorou significativamente.
-   A atualização inclui correções de defeito e melhorias internas.

### 1 de junho de 2016
{: #June2016a}

O serviço foi atualizado para correções de defeito e melhorias internas. Um novo campo de nível superior, `warnings`, também foi incluído nos resultados de JSON que são retornados pelo serviço. Para obter mais informações, veja a [Referência de API ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://{DomainName}/apidocs/personality-insights){: new_window}.

### 17 de maio de 2016
{: #May2016}

O serviço foi atualizado para correções de defeito e melhorias internas. 

### 18 de março de 2016
{: #March2016}

O serviço agora suporta os idiomas a seguir:

-   O serviço suporta quatro idiomas para o seu texto de entrada: árabe (`ar`), inglês (`en`), espanhol (`es`) e japonês (`ja`). Para especificar o idioma, use o cabeçalho HTTP `Content-Language` para entrada em texto sem formatação e HTML ou a propriedade `language` do objeto `ContentItem` para entrada em JSON.
-   O serviço suporta os mesmos quatro idiomas para a sua resposta. Para especificar o idioma da resposta, use o cabeçalho `Accept-Language`.

É possível usar qualquer combinação de idiomas para a entrada e a resposta. Se você não indicar um idioma, o serviço usará inglês como padrão. Para obter mais informações, veja [Especificando linguagens de solicitação e resposta](/docs/services/personality-insights?topic=personality-insights-input#languages-input). Também é possível consultar a postagem do blog [Suporte árabe e japonês agora está disponível para o {{site.data.keyword.IBM_notm}} {{site.data.keyword.watson}} {{site.data.keyword.personalityinsightsshort}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/blogs/watson/2016/04/arabic-japanese-support-now-available-ibm-watson-personality-insights/){: new_window}.

Como ele requer significativamente mais ciclos de computação para analisar do que outros idiomas, o conteúdo em árabe leva marcadamente mais tempo para processar. Embora o serviço suporte a mesma restrição de 20 MB sobre a quantidade de texto de entrada para todos os idiomas, o limite prático para o conteúdo árabe pode ser inferior para evitar tempos limites. O conteúdo em japonês também leva mais tempo para processar, mas os atrasos são de importância menos significativa do que para o árabe.
{: note}

### 9 de julho de 2015
{: #July2015}

-   *Suporte ao idioma.* É possível analisar o conteúdo inglês e espanhol. Você indica o idioma do texto de entrada com o cabeçalho `Content-Language` do método `/v2/profile`. Para obter mais informações sobre como especificar um idioma, consulte [Especificando idiomas de solicitação e resposta](/docs/services/personality-insights?topic=personality-insights-input#languages-input).
-   *Pontuações brutas.* É possível solicitar pontuações brutas e erros de amostragem bruta que são calculados por meio do texto de entrada e dos modelos do serviço. Os valores não são normalizados ou comparados a uma população de amostra. Pontuações brutas são úteis para clientes que desejam aplicar uma normalização customizada para um cenário específico ou que não requerem uma comparação com uma população de amostra. Você solicita pontuações brutas configurando o parâmetro de consulta `include_raw` do método `/v2/profile` para `true`. Para obter mais informações, consulte [Interpretando os resultados numéricos](/docs/services/personality-insights?topic=personality-insights-numeric).
-   *Aprimoramentos do modelo.* Com base em seus estudos mais recentes, a {{site.data.keyword.IBM_notm}} melhorou ainda mais algumas de suas abordagens para inferir características de personalidade. As mudanças são transparentes para os usuários do serviço; elas não invalidam nenhum resultado anterior obtido por meio do serviço. Para obter mais informações sobre os estudos e a abordagem do serviço para inferência, consulte [Como características da personalidade são inferidas](/docs/services/personality-insights?topic=personality-insights-science#researchInfer).

### 23 de fevereiro de 2015
{: #February2015}

A partir de 23 de fevereiro de 2015, o serviço do {{site.data.keyword.personalityinsightsshort}} é a versão generally available (GA) do antigo serviço de Modelagem de usuário, que estava disponível como uma liberação beta. A liberação GA requer que os usuários migrem para uma instância do novo serviço. As diferenças a seguir existem entre as versões beta e GA do serviço.

-   O serviço {{site.data.keyword.personalityinsightsshort}} é compatível com o serviço User Modeling. As diferenças que são descritas fornecem mais flexibilidade e resultados melhorados sem afetar os aplicativos atuais.
-   Os parâmetros com os quais você cria o serviço em {{site.data.keyword.cloud_notm}}foram alterados. Agora, você usa um nome de serviço `personality_insights` em vez de `user_modeling` e um plano de serviço do `"IBM Watson Personality Insights Monthly Plan"` em vez de `user_modeling_free_plan`.
-   O método `/v2/profile` aceita dois novos formatos de entrada. O cabeçalho `Content-Type` agora aceita os formatos de entrada de texto sem formatação (`text/plain`), que é o padrão, e HTML (`text/html`), além de JSON (`application/json`).
-   O método `/v2/profile` agora retorna um novo formato de saída. O cabeçalho `Accept` agora aceita o formato de saída CSV (`text/csv`) além de JSON (`application/json`), que é o padrão.
-   O método `/v2/profile` agora inclui um novo elemento de saída, `sampling_error`, para cada característica para a qual ele relata um valor de porcentagem. O erro de amostragem é retornado como um valor duplo que indica o nível de confiança do serviço em percentil do autor com base no texto de entrada.
-   O modelo Necessidades emprega tokenização melhorada e processamento para melhor normalizar a distribuição de valores para suas características. Você é aconselhado a recalcular quaisquer resultados que foram gerados pela API de Modelagem de usuário.
-   O método `visualize` foi descontinuado e será removido completamente em uma liberação futura. É possível usar o arquivo JavaScript `personality.js` que é fornecido com o aplicativo de amostra para atingir resultados semelhantes do cliente. O arquivo JavaScript `textsummary.js` fornece formatação extra para os resultados do serviço.
