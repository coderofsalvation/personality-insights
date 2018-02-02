---

Copyright: years: 2015, 2017 lastupdated: "2017-11-28"

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

# Notas sobre o Release
{: #release-notes}

As seções a seguir documentam os novos recursos e as mudanças que foram incluídas para cada liberação do serviço {{site.data.keyword.personalityinsightsshort}}. A menos que indicado de outra forma, todas as alterações foram compatíveis e foram automaticamente e de forma transparente disponível para todos os novos e aplicativos existentes.
{: shortdesc}

> **Nota:** As notas sobre a liberação do documento *versão do serviço* e *interface version* para todas as atualizações recentes. Você especifica o *interface version* com o `version` parâmetro de consulta para usar novos recursos e funcionalidade disponível com essa atualização. O serviço retorna ambos versões com o `X-Service-API-Version` cabeçalho de resposta.

## 13 de outubro de 2017
{: #October2017}

**Serviço de versão:** `3.4.0`<br/> **Versão da interface:** `2017-10-13`

-   O objeto `Trait` do perfil de personalidade agora inclui um campo `significant` adicional. Um separada `Característica` objeto relata os resultados para cada dimensão Big Five, aspecto Big Five, Necessidade, e Valor. O `significativo` campo de cada instância do objeto identifica se os resultados para essa característica são significativos para o idioma de entrada (`Content-Language`) do pedido:

    -   Para inglês, espanhol e japonês, o campo é sempre `true` para todas as características da personalidade.
    -   Para árabe e coreano, o campo é `true` para a maioria das características de personalidade, mas é `false` para aqueles para os quais os modelos do serviço são incapazes de produzir resultados significativos. O campo é `false` para um conjunto constante de características; por uma lista completa, consulte [Limitações para entrada árabe e coreano](/docs/services/personality-insights/numeric.html#limitations). Não confie nos resultados de qualquer característica para os quais o campo é `false`.

    Para obter informações sobre o conteúdo de resposta do serviço JSON, consulte [Entendendo um JSON perfil](/docs/services/personality-insights/output.html).
-   Saída CSV agora também inclui colunas adicionais cujos títulos são denominados `* _significant`. Cada coluna fornece um valor booleano para indicar se uma característica é significativo. Para obter informações sobre o serviço CSV resposta conteúdo, consulte [Entendendo um perfil CSV](/docs/services/personality-insights/output-csv.html).
-   A versão da interface especificado com o `version` parâmetro é `2017-10-13` para usar essa versão mais recente da interface.

## 18 de setembro de 2017
{: #September2017}

**Serviço de versão:** `3.3.0`<br/> **Interface versão:** `2016-10-19`

O serviço agora suporta conteúdo de entrada em Coreano (`ko`). Para obter informações sobre a média de Erro Absoluto Médio (MAE) e correlação médio para entrada coreano, consulte [por linguagem média MAE e correlação](/docs/services/personality-insights/science.html#precisePerLanguage).

Os modelos do serviço são incapazes de produzir percentis significativos e pontuações brutas para algumas características de personalidade de entrada coreana. Para obter mais informações sobre os resultados para essas características, consulte [Limitações para entrada árabe e coreano](/docs/services/personality-insights/numeric.html#limitations).

## 10 de abril de 2017
{: #April2017}

**Serviço de versão:** `3.1.7`<br/> **Interface versão:** `2016-10-19`

-   O serviço mudou assim que manipula solicitações com grandes quantidades de conteúdo de entrada. O serviço aceita um máximo de 20 MB de conteúdo. No entanto, com os modelos baseados em *GloVe*, os níveis de precisão de cerca de 3000 palavras de entrada. Isso é diferente de modelos antigos, onde mais texto produzido maior precisão. Em geral, o serviço não precisa de tanto conteúdo para produzir um perfil preciso. Mas conteúdo adicional requer tempo de processamento adicional, que pode causar uma solicitação de tempo limite antes de ser concluída.

    Portanto, o serviço agora extrai e usa apenas os primeiros 250 KB de conteúdo, sem contar qualquer HTML ou marcação JSON, de grandes pedidos. Esta figura não mapeia para um número exato de palavras, que varia com base no idioma e a natureza do texto. Em inglês, por exemplo, o comprimento da palavra média é entre quatro e cinco caracteres, então essa figura fornece cerca de 50.000 palavras, que é pelo menos 15 vezes mais palavras do que as necessidades de serviço. O `word_count` do JSON de resposta indica o número de palavras que o serviço realmente usa para um pedido, que pode ser menor que o número de palavras na entrada.

    Porque ainda bases de um perfil em palavras muito mais do que só precisa para a precisão máxima, o serviço produz um perfil que é tão preciso quanto no passado. No entanto, o serviço responde muito mais rápido que antes. Para pedidos para o qual ele usa apenas uma parte do conteúdo de entrada, o serviço retorna o seguinte `CONTENT_TRUNCATED` mensagem de aviso para tornar o usuário ciente do fato:

    `For maximum accuracy while also optimizing processing time, only the first 250KB of input text (excluding markup) was analyzed. Accuracy levels off at approximately 3K words so this did not affect the accuracy of the profile.`

    Para obter mais informações, consulte [Fornecendo suficiente entrada](/docs/services/personality-insights/input.html#sufficient).
-   O serviço foi atualizado com correções de segurança pequena.

## Liberações mais antigas
{: #older}

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

### 1 de março de 2017
{: #March2017}

**Serviço de versão:** `3.1.6`<br/> **Interface versão:** `2016-10-19`

O serviço foi atualizado com {{site.data.keyword.personalityinsightsshort}} pequenos aprimoramentos de log.

### 20 de fevereiro de 2017
{: #February2017b}

**Serviço de versão:** `3.1.5.1`<br/> **Interface versão:** `2016-10-19`

O serviço Insights de Personalidade foi atualizado com segurança pequena e correções de defeitos e melhorar a medição de chamadas API.

### 13 de fevereiro de 2017
{: #February2017}

**Serviço de versão:** `3.1.4`<br/> **Interface versão:** `2016-10-19`

-   A lista de preferências de consumo foi refinado para incluir apenas os mais importantes para entender os hábitos de vida para uma pessoa e características do consumidor. A lista de preferências de consumo foi reduzido de 51 para 42; o restante preferências expressas probabilidade do autor preferir diferentes produtos, serviços e atividades mais concisa, tornando mais fácil agir com base nos resultados. O serviço não mais retorna o seguinte nove preferências do consumo. Para obter mais informações sobre as preferências restantes, consulte [Consumo Preferências](/docs/services/personality-insights/preferences.html).

    <table>
      <caption>Tabela 1. Mudanças nas preferências de consumo</caption>
      <tr>
        <th style="text-align:left">Categoria</th>
        <th style="text-align:left">Consumo preferências removido</th>
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
            <code>consumption_preferences_read_motive_enjoyment</code> <code>consumption_preferences_read_motive_information</code> <code>consumption_preferences_read_motive_mandatory</code> <code>consumption_preferences_read_motive_relaxation</code>
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
            <code>consumption_preferences_adventurous_sports</code> <code>consumption_preferences_fast_food_frequency</code>
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
            <code>consumption_preferences_volunteering_time</code> <code>consumption_preferences_volunteer_learning</code>
          </p>
        </td>
      </tr>
    </table>

-   *Para árabe entrada*, informações sobre a média de Erro Absoluto Médio (MAE) e correlação média agora está disponível no [por linguagem média MAE e correlação](/docs/services/personality-insights/science.html#precisePerLanguage). Além disso, os modelos de serviço são incapazes de produzir percentis significativas e pontuações brutos para uma coleção de características da personalidade. Para obter mais informações sobre os resultados para essas características, consulte [Limitações para entrada árabe e coreano](/docs/services/personality-insights/numeric.html#limitations).

### 13 de janeiro de 2017
{: #January2017}

**Serviço de versão:** `3.1.2.1`<br/> **Interface versão:** `2016-10-19`

O serviço Personality Insights foi atualizado com algumas pequenas correções de defeitos.

### 15 de dezembro de 2016
{: #December2016}

**Serviço de versão:** `3.1.1`<br/> **Interface versão:** `2016-10-19`

Para texto de entrada árabe, o {{site.data.keyword.personalityinsightsshort}} serviço agora usa a palavra de software livre integração técnica chamada *GloVe* para desenvolver um perfil de personalidade. O serviço não usa mais o dicionário psicolinguístico Linguistic Inquiry and Word Count (LIWC) para nenhum idioma. Para obter mais informações sobre como o serviço desenvolve um retrato personalidade, consulte [Como as características da personalidade são inferidos](/docs/services/personality-insights/science.html#researchInfer).

### 15 de novembro de 2016
{: #November2016}

**Serviço de versão:** `3.1.0`<br/> **Interface versão:** `2016-10-19`

-   Para texto de entrada japonês, o {{site.data.keyword.personalityinsightsshort}} serviço agora usa a palavra de software livre integração técnica chamada *GloVe* para desenvolver um perfil de personalidade; o serviço não usa mais o inquérito linguística e Contagem de Palavras (LIWC) linguísticas dicionário para entrada japonês. Para obter mais informações, consulte [Como as características da personalidade são inferidos](/docs/services/personality-insights/science.html#researchInfer).
-   O `nome` campos `ConsumptionPreferencesCategory` e `ConsumptionPreferences` objetos agora são retornados com sequências localizadas no idioma especificado com o `Accept-Language` cabeçalho da solicitação.
-   A atualização inclui algumas pequenas correções de defeitos.

### 20 de outubro de 2016
{: #October2016b}

**Serviço de versão:** `3.0.0`<br/> **Interface versão:** `2016-10-19`

O serviço {{site.data.keyword.personalityinsightsshort}} e sua API foram atualizadas significativamente. A API foi incrementada a partir da versão 2 para a versão 3 e oferece novos recursos. As seções restantes deste nota release descrevem as alterações em detalhes.

Versão 3 não é compatível com a versão 2. Vocês são encorajados a migrar para a versão 3 para aproveitar os novos recursos e mudanças. A migração para a versão 3 consiste apenas em atualizar e reimplementar seus aplicativos para utilizar as mudanças descritas nestas notas sobre a liberação para a nova versão. Você não precisa criar uma nova instância do serviço no {{site.data.keyword.Bluemix_notm}}; você precisa apenas chamar o `v3` API.

> **Nota:** Versão 2 do {{site.data.keyword.personalityinsightsshort}} API será removido do serviço no futuro próximo. É altamente recomendável migrar para a versão 3 assim que possível. Por enquanto, você pode acessar a documentação de referência para a versão 2 em [Referência de API para v2 ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/watson/developercloud/personality-insights/api/v2/){: new_window}; você também pode acessar a ferramenta interativa para testar chamadas para a versão 2 e visualizar respostas ao vivo do serviço em [API Explorador para v2 ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://watson-api-explorer.mybluemix.net/apis/personality-insights-v2){: new_window}.

#### Mais informações sobre a versão 3

Esta documentação agora descreve a versão 3 {{site.data.keyword.personalityinsightsshort}} API. As seções a seguir resumem as mudanças para a nova versão da interface:

-   Para obter informações sobre como chamar o método `/v3/profile`, consulte [Solicitando um perfil](/docs/services/personality-insights/input.html).
-   Para obter informações sobre o `/v3/profile` resposta do método, consulte [Entendendo um perfil JSON](/docs/services/personality-insights/output.html) e [Entendendo um perfil CSV](/docs/services/personality-insights/output-csv.html).
-   Para obter detalhes completos sobre a interface da versão 3, consulte a [Referência da API![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}.

#### Mudanças nos parâmetros do <code>/v3/profile</code> método

Parâmetros do `/v3/profile` método mudou como segue:

-   A API agora oferece um parâmetro de consulta opcional chamado `consumption_preferences`. O parâmetro aceita um valor booleano que indica se as informações sobre preferências de consumo é inferido ser retornado com os resultados. Por padrão, as informações não são incluídos na resposta. Para obter mais informações, consulte [preferências de consumo Novo recurso](#cp).
-   A API agora inclui um parâmetro de consulta necessário chamado `version`. O parâmetro aceita uma cadeia que identifica a versão solicitada da API e o formato de resposta como uma data no formato `AAAA-MM-DD`; por exemplo, especifique `2016-10-19` para 19 de outubro de 2016. Este parâmetro permite que o serviço para atualizar sua API ou resposta formato para novas versões sem quebrar clientes existentes. A sequência inicial para a versão 3 da API é `2016-10-19`.

    A data que você especificar não precisa corresponder a uma versão do serviço exatamente; o serviço usa a versão que seja posterior à data não é fornecido. Se você especificar uma data que seja anterior à data de liberação da versão 3, o serviço usa a versão 3 da API. Se você especificar uma data que esteja no futuro ou que seja posterior à versão mais recente, o serviço usará a versão mais recente.
-   O nome do `include_raw` consulta parâmetro é agora `raw_scores`.
-   O nome do `cabeçalhos` consulta parâmetro é agora `csv_headers`.

#### Novas preferências de consumo de recurso
{: #cp}

O recurso de preferências de consumo fornece uma indicação de tendência do autor para exibir as tendências de consumo diferente. Quando você passar `consumption_preferences` consulta parâmetro com um valor de `true` para o `/v3/profile` método, o serviço retorna os seguintes resultados adicionais com o `Perfil` objeto:

-   Um campo `consumption_preferences` que fornece uma matriz de objetos `ConsumptionPreferencesCategory`.
-   Cada `ConsumptionPreferencesCategory` objeto inclui os seguintes campos:
    -   `consumption_preference_category_id`: O ID de uma das categorias de preferências de consumo
    -   `name`: O usuário visível nome da categoria.
    -   `consumption_preferences`: Uma matriz de `ConsumptionPreferences` objetos que fornece resultados inferidos do texto de entrada para as preferências individuais da categoria
-   Cada `ConsumptionPreferences` objeto inclui os seguintes campos:
    -   `consumption_preference_id`: O ID de uma das preferências de consumo.
    -   `name`: O usuário visível nome da preferência consumo.
    -   `score`: A pontuação para a preferência do consumo. Para muitos preferências, `0,0` indica improvável, `0,5` indica neutralidade, e `1,0` indica provável. As pontuações para algumas preferências são binários e não permitem um valor neutro. A pontuação é uma indicação de preferência baseada nos resultados inferidos do texto de entrada, não um percentil normalizado.

Para obter mais informações sobre as preferências de consumo, consulte [Preferências de consumo](/docs/services/personality-insights/preferences.html).

> **Nota:** Atualmente, o `nome` de campo para ambos os objetos preferências de consumo é sempre retornado em inglês, independentemente do idioma especificado com o `Accept-Language` cabeçalho da solicitação.

#### Mudanças nos objetos e campos JSON

JSON de entrada e saída objetos e seus campos foram simplificadas e esclareceu como segue:

-   Os campos a seguir foram removidos do JSON `ContentItem` objetos que você pode passar para o `/v3/profile` método com um pedido:
    -   `userid`
    -   `sourceid`
    -   `charset` (anteriormente descontinuado)

    É possível passar esses objetos no corpo de uma solicitação JSON como elementos de `contentItems` matriz de `Conteúdo` do objeto.
-   Os campos a seguir do JSON `Perfil` objeto que é retornado pelo `/v3/profile` método mudou:
    -   Os campos a seguir foram removidos:
        -   `id`
        -   `origem`
    - O `árvore` campo foi removido. Ele é substituído por quatro novos campos:
        -   `Personalidade` para as características da personalidade Big Five.
        -   `precisa` para Necessidades características.
        -   `values` para características de valores.
        -   `comportamento` para resultados temporais sobre a distribuição do conteúdo sobre os dias da semana e as horas do dia. Este campo é retornado apenas para entrada JSON que é hora.

    Essa mudança efetivamente move os resultados um nível mais alto no JSON `Perfil` objeto, eliminando um nível de recursão.
    -   O nome do `processed_lang` campo agora é `processed_language`.
-   Os campos a seguir de JSON `Peculiaridade` objetos que são retornados pelo `/v3/profile` método foram renomeados:
    -   O nome do `id` do JSON `Característica` objeto é agora `trait_id`.
    -   O nome do campo `percentage` do objeto JSON `Trait` é agora `percentile`.
-   Os seguintes campos de JSON `Peculiaridade` objetos que são retornados pelo `/v3/profile` método foram removidos:
    -   `sampling_error`
    -   `raw_sampling_error`

    O serviço agora relata uma média de Erro Absoluto Médio (MAE) que qualifica o precisão de seus resultados. Para obter mais informações sobre o MAE para diferentes quantias de texto de entrada, consulte[Fornecendo entrada suficiente](/docs/services/personality-insights/input.html#sufficient).
-   JSON `Peculiaridade` objetos continuam retornados para o `Personalidade`, `precisa`, e `valores` campos do `Perfil` objeto. O `comportamento` campo retorna uma matriz de objetos JSON chamado `Comportamento` que possuem os seguintes campos:
    -   `trait_id`
    -   `nome`
    -   `categoria`
    -   `porcentagem`

    Além disso, as informações de comportamento não é mais retornado como uma árvore de valores. A saída consiste em uma única matriz que lista todas as características temporais (dia da semana e hora do dia).
-   O nome do `id` do JSON `Avisos` objeto que pode ser retornado pelo `/v3/profile` método agora é `warnings_id`.

#### Mudanças nos IDs de JSON
{: #ids}

O JSON IDs que o serviço retorna para o `trait_id` (anteriormente `id`) do campo `Peculiaridade` e o novo `Comportamento` objetos foram alterados conforme a seguir:

-   Os IDs para as dimensões Big Five agora começam com a sequência `big5_`.
-   Os IDs para aspectos Big Five agora começam com a sequência `facet_`.
-   Os IDs para Necessidades agora começam com a sequência `need_`.
-   Os IDs para Valores agora começam com a sequência `value_`.
-   Os IDs para todas as características temporais já começam com a sequência `behavior_`.
-   Os IDs para características temporais relacionadas ao tempo do dia agora usar quatro dígitos 24 horas tempo (por exemplo, `behavior_0000`) em vez de tempo de 12 horas (por exemplo, `00:00`).
-   Todos os caracteres são minúsculos agora.
-   Espaços e hifens estão sublinhados.

#### Mudanças nos cabeçalhos CSV
{: #headers}

Os cabeçalhos de coluna opcional que o serviço pode retornar para saída CSV foram alterados conforme a seguir:

-   Todas as mudanças descritas para o `trait_id` da saída JSON também se aplicam aos cabeçalhos CSV.
-   Os cabeçalhos para pontuações brutos para as dimensões Big Five agora começam com a sequência `big5_`.
-   Os cabeçalhos para pontuações brutos para aspectos Big Five agora começam com a sequência `facet_`.
-   Os cabeçalhos para pontuações brutas para Necessidades agora começam com a sequência `need_`.
-   Os cabeçalhos para pontuações brutos para valores agora começam com a sequência `value_`.
-   O cabeçalho da coluna de idioma processado é agora `processed_language` em vez de `processed_lang`.
-   O `usuário` e `source_id` colunas não são retornados.
-   Todos os caracteres são minúsculos agora.
-   Espaços e hifens estão sublinhados.

#### A remoção do <code>visualizar</code> método

A versão 2 da API do serviço incluía um método `visualize` descontinuado que era usado em uma liberação anterior para visualizar os resultados de uma chamada para o método `/v3/profile`. O `visualizar` método foi removido da API do serviço. O serviço continua a fornecer uma coleção de arquivos JavaScript que permitem a visualização gráfica de um perfil; para obter mais informações, consulte [Visualizando um perfil](/docs/services/personality-insights/developer-overview.html#visualize).

### 12 de outubro de 2016
{: #October2016a}

Para texto de entrada espanhol, o {{site.data.keyword.personalityinsightsshort}} serviço agora usa a palavra de software livre integração técnica chamada *GloVe* para desenvolver um perfil de personalidade; o serviço não usa mais o inquérito linguística e Contagem de Palavras (LIWC) linguísticas dicionário para entrada espanhol. O serviço começou a usar o novo modelo para texto de entrada em inglês em 31 de agosto; ele será aplicado o novo modelo para os idiomas de entrada no futuro próximo. Para obter mais informações sobre o novo modelo, consulte [Como as características da personalidade são inferidos](/docs/services/personality-insights/science.html#researchInfer).

### 31 de agosto de 2016
{: #August2016}

O serviço {{site.data.keyword.personalityinsightsshort}} agora usa uma palavra de software livre de integração técnica chamada *GloVe* para desenvolver um perfil de personalidade; para obter mais informações, consulte [Como as características da personalidade são inferidos](/docs/services/personality-insights/science.html#researchInfer). Neste momento, o serviço usa a nova abordagem somente para texto de entrada em inglês. Para outros idiomas, o serviço continua a usar a Consulta linguística e dicionário linguísticas Contagem de Palavras (LIWC). As futuras versões do serviço usarão a abordagem de vocabulário aberto para todas os idiomas.

Para o novo modelo usado para entrada em inglês, o serviço informa a média de Erro Absoluto Médio (MAE) dos resultados para seu modelo treinado. Para obter informações sobre como o MAE muda com diferentes quantidades de texto de entrada, consulte [Fornecendo suficiente de entrada](/docs/services/personality-insights/input.html#sufficient). Futuras versões do serviço relatará o MAE para modelos inglês e vai recomendar que você usa, em vez de amostragem erros, para determinar como a precisão das mudanças de serviço com base na quantidade de texto de entrada que você fornece.

### 14 de julho de 2016
{: #July2016b}

-   Para entrada árabe, o serviço pode agora reduzir a quantidade de texto de entrada por motivos de desempenho. Em certo limite, a precisão dos resultados para o árabe não melhora com mais palavras. Se o texto de entrada do serviço árabe reduz, ele retorna um `PARTIAL_TEXT_USED` aviso com a seguinte mensagem:

    `O texto fornecido para calcular o perfil foi cortado por motivos de desempenho. Essa ação não afeta a precisão da saída, pois nem todo texto de entrada era necessário.`
-   A atualização inclui correções de defeitos adicionais e melhorias internas.

### 1 de julho de 2016
{: #July2016a}

-   Os planos de precificação para o serviço foram alterados para oferecer preços mais baixos para {{site.data.keyword.personalityinsightsshort}} usuários. Para obter mais informações, consulte o [{{site.data.keyword.personalityinsightsshort}} serviços no {{site.data.keyword.Bluemix_short}} Catálogo ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://console.ng.bluemix.net/catalog/services/personality-insights/){: new_window}.
-   A lista de idiomas de resposta suportados que você pode especificar com o `Accept-Language` do cabeçalho agora inclui o seguinte:
    -   `ar` (Árabe)
    -   `de` (Alemão)
    -   `en` (Inglês, o padrão)
    -   `es` (Espanhol)
    -   `fr` (Francês)
    -   `não` (Italiano)
    -   `ja` (Japonês)
    -   `ko`
(Coreano)
    -   `pt-BR` (Português do Brasil)
    -   `zh-cn` (Chinês Simplificado)
    -   `zh-tw` (Chinês Tradicional)

    Para obter mais informações, consulte [Especificando de pedido e resposta idiomas](/docs/services/personality-insights/input.html#languages).
-   O `/v2/profile` método pode agora retornar os seguintes códigos de status HTTP:
    -   429 *Muitas Solicitações*: O serviço está atualmente processando muitas solicitações para o idioma do conteúdo. Espere um pouco e tente o pedido novamente. Se você estiver enviando muitas solicitações para o idioma, considere a limitação a taxa na qual você envia pedidos.
    -   504 *Tempo Limite do Gateway*: A solicitação atingiu o tempo limite ou levou muito tempo para processar. Espere um pouco e tente o pedido novamente. Se a entrada continha um grande número de palavras (por exemplo, mais de 20.000), considere reduzir o número de palavras enquanto mantém as diretrizes para entrada significativo.

    O método não retorna 503 *Serviço Indisponível*. Para obter mais informações sobre códigos de resposta possíveis, consulte o [Referência de API ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}.
-   A atualização inclui correções de defeitos adicionais e melhorias internas.

### 7 de junho de 2016
{: #June2016b}

-   O serviço agora oferece suporte o Compartilhamento de recurso de origem cruzada (CORS) para permitir que os clientes baseados no navegador chamem o serviço diretamente. Para obter mais informações, consulte[Suporte ao CORS](/docs/services/personality-insights/developer-overview.html#CORS).
-   O desempenho do serviço quando o processamento de texto japonês melhorou significativamente.
-   A atualização inclui correções de defeitos adicionais e melhorias internas.

### 1 de junho de 2016
{: #June2016a}

O {{site.data.keyword.personalityinsightsshort}} serviço foi atualizado para correções de defeitos e melhorias internas. Um campo de nível superior adicional, `avisos`, também foi incluído no resultado JSON retornado pelo serviço; para obter mais informações, consulte a [Referência de API ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}.

### 17 de maio de 2016
{: #May2016}

O {{site.data.keyword.personalityinsightsshort}} serviço foi atualizado para correções de defeitos e melhorias internas.

### 18 de março de 2016
{: #March2016}

O serviço agora suporta os seguintes idiomas:

-   Quatro idiomas para sua entrada de texto: Árabe (`ar`), Inglês (`en`), Espanhol (`es`), e Japonês (`ja`). Para especificar o idioma, utilize o HTTP `Content-Language` do cabeçalho para texto simples e de entrada HTML ou o `idioma` propriedade do `ContentItem` objeto para entrada JSON.
-   O mesmo quatro idiomas para sua resposta. Para especificar o idioma da resposta, use o `Accept-Language` do cabeçalho.

É possível usar qualquer combinação de idiomas para a entrada e resposta. Em ambos os casos, se você não indicar um idioma, o serviço padrão será o inglês. Para obter mais informações, consulte [Especificando de pedido e resposta idiomas](/docs/services/personality-insights/input.html#languages). Além disso, consulte a postagem do blog [árabe e japonês suporte agora está disponível para {{site.data.keyword.IBM_notm}} {{site.data.keyword.watson}} {{site.data.keyword.personalityinsightsshort}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/blogs/watson/2016/04/arabic-japanese-support-now-available-ibm-watson-personality-insights/){: new_window} para obter informações adicionais.

> **Nota:** Como ele requer ciclos de computação significativamente mais para analisar que outros idiomas, o conteúdo em árabe leva significativamente mais tempo para processar. Embora o serviço suporta a mesma restrição 20 MB na quantidade de texto de entrada para todos os idiomas, o limite prático para o conteúdo em árabe pode ser inferior para evitar tempos limites. Conteúdo em japonês também leva mais tempo para processar, mas os atrasos são de importância menos significativa do que são para árabe.

### 9 de julho de 2015
{: #July2015}

-   *Idioma de suporte.* O serviço agora permite analisar ambos inglês e espanhol conteúdo. Você indica o idioma do texto de entrada com o `Content-Language` do cabeçalho do `/v2/profile` método. Para obter informações sobre como especificar um idioma, consulte [Especificando de pedido e resposta idiomas](/docs/services/personality-insights/input.html#languages).
-   *Pontuações brutas.* O serviço agora permite que você solicitar resultados brutos e erros de amostragem bruto calculado a partir do texto de entrada e modelos do serviço. Os valores não são normalizadas ou em comparação com uma população de amostra. Pontuações brutas são úteis para clientes que desejam aplicar uma normalização customizado para um cenário específico ou que não requerem uma comparação com uma população de amostra. Você solicita pontuações brutas definindo o parâmetro de consulta `include_raw` do método `/v2/profile` como `true`. Para obter mais informações, consulte [Interpretando os resultados numéricos](/docs/services/personality-insights/numeric.html).
-   *Modelo aprimoramentos.* Com base em sua última estudos, {{site.data.keyword.IBM_notm}} melhorou um pouco mais de suas abordagens para as características da personalidade deduzindo. As mudanças são transparentes para os usuários do serviço e não invalidar quaisquer resultados anteriores obtidos do serviço. Para obter mais informações sobre os estudos e a abordagem de serviço para inferência, consulte [Como as características da personalidade são inferidos](/docs/services/personality-insights/science.html#researchInfer).

### 23 de fevereiro de 2015
{: #February2015}

A partir de 23 de fevereiro de 2015, o {{site.data.keyword.personalityinsightsshort}} serviço é a versão geralmente disponível (GA) do serviço antigo User Modeling, que estava disponível como uma liberação beta. A liberação GA requer que os usuários migrem para uma instância do novo serviço. As seguintes diferenças existem entre as versões beta e GA do serviço.

-   O serviço {{site.data.keyword.personalityinsightsshort}} é compatível com o serviço User Modeling. As diferenças que são descritos nesta seção fornecem mais flexibilidade e resultados melhorados sem afetar aplicativos atuais.
-   Os parâmetros com os quais você criar o serviço no {{site.data.keyword.Bluemix_short}} mudaram. Agora, use um nome de serviço `personality_insights` em vez de `user_modeling` e um plano de serviço do `"IBM Watson Personality Insights Mensal Plano"` em vez de `user_modeling_free_plan`.
-   O método `/v2/profile` aceita dois novos formatos de entrada. O `Content-Type` cabeçalho agora aceita os formatos de entrada de texto simples (`text/plain`), que é o padrão, e HTML (`text/html`), além de JSON (`application / json`).
-   O `/v2/profile` método agora retorna um novo formato de saída. O `Aceitar` cabeçalho agora aceita o formato de saída CSV (`text/csv`) além dos JSON (`application / json`), que é o padrão.
-   O `/v2/profile` método agora inclui um novo elemento de saída, `sampling_error`, para cada característica para o qual ele relata um valor de porcentagem. O erro de amostragem é retornado como um valor duplo, que indica o nível de confiança do serviço no percentil do autor com base no texto de entrada.
-   O modelo Necessidades emprega a tokenização melhorada e o processamento para melhor normalizar a distribuição de valores para suas características. Você é avisado para recalcular quaisquer resultados que foram gerados pela API de Modelagem do Usuário.
-   O `visualizar` método agora está descontinuado e será removido completamente em uma liberação futura. É possível usar o `personality.js` JavaScript arquivo que é fornecido com o aplicativo de amostra para atingir resultados semelhantes do cliente. O `textsummary.js` arquivo JavaScript fornece formatação adicional para os resultados do serviço.
