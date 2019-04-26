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

# Solicitando um perfil
{: #input}

Para analisar o conteúdo, você usa o método de solicitação HTTP `POST` para chamar o método `/v3/profile` do serviço do {{site.data.keyword.personalityinsightsshort}}. É possível passar o serviço com um máximo de 20 MB de conteúdo a ser analisado por meio do corpo da solicitação. No entanto, o serviço requer muito menos entrada para produzir um perfil de personalidade preciso. Para obter mais informações, consulte [Fornecendo entrada suficiente](#sufficient).
{: shortdesc}

O método `/v3/profile` inclui parâmetros que especificam o tipo de conteúdo a ser passado para e retornado pelo serviço, bem como o idioma de cada tipo de conteúdo. O serviço sempre retorna um perfil que fornece insight sobre as características da personalidade do autor do texto de entrada. Também é possível solicitar pontuações brutas e preferências de consumo.

As seções a seguir descrevem os parâmetros do método `/v3/profile`. Para obter informações sobre os resultados de uma solicitação, consulte [Entendendo um perfil JSON](/docs/services/personality-insights?topic=personality-insights-output) e [Entendendo um perfil CSV](/docs/services/personality-insights?topic=personality-insights-outputCSV). Para obter informações detalhadas sobre o método `/v3/profile`, consulte a [Referência de API ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://{DomainName}/apidocs/personality-insights){: new_window}.

A criação de log de solicitação está desativada para o serviço {{site.data.keyword.personalityinsightsshort}}. Independentemente de você configurar o cabeçalho da solicitação `X-Watson-Learning-Opt-Out`, o serviço não registra nem retém dados de solicitações e respostas.
{: note}

## Especificando formatos de solicitação e resposta
{: #formats}

Você usa os parâmetros de cabeçalho `Content-Type` e `Accept` para indicar o formato do conteúdo que você está passando para o método e o formato da resposta do serviço. É possível usar qualquer combinação de formatos suportados para a solicitação e a resposta.

<table>
  <caption>Tabela 1. Especificando formatos de solicitação e resposta</caption>
  <tr>
    <th style="width:10%; text-align:left; vertical-align:bottom">
      Formato
    </th>
    <th style="width:26%; text-align:center; vertical-align:bottom">
      Argumento
    </th>
    <th style="width:32%; text-align:center; vertical-align:bottom">
      Suportado por<br/>
      <code>Content-Type</code>
    </th>
    <th style="width:32%; text-align:center; vertical-align:bottom">
      Suportado por<br/>
      <code>Accept</code>
    </th>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      Texto sem formatação
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/plain</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      Sim (padrão)<br/><br/>
      O serviço processa o texto sem formatação sem modificação.
    </td>
    <td style="text-align:center; vertical-align:top">
      no
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      HTML
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/html</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      Sim<br/><br/>
      O serviço retira as tags do conteúdo antes de processar o texto.
    </td>
    <td style="text-align:center; vertical-align:top">
      no
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      JSON
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>application/json</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      Sim<br/><br/>
      O conteúdo deve estar em conformidade com o modelo definido pelo objeto <code>Content</code>, que é uma matriz de objetos <code>ContentItem</code>.
    </td>
    <td style="text-align:center; vertical-align:top">
      Sim<br/><br/>
      O serviço retorna seus resultados como um objeto <code>Profile</code>.
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      CSV
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/csv</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      no
    </td>
    <td style="text-align:center; vertical-align:top">
      Sim<br/><br/>
      Por padrão, o serviço retorna uma única linha de resultados numéricos.
      Configure o parâmetro de consulta <code>csv_headers</code> opcional para
      <code>true</code> para solicitar cabeçalhos para cada coluna da saída.
    </td>
  </tr>
</table>

### Especificando o conjunto de caracteres
{: #charset}

Por padrão, o serviço usa os conjuntos de caracteres a seguir para conteúdo de entrada:

-   *Para conteúdo em texto sem formatação e HTML,* o serviço usa o conjunto de caracteres Organização de Normas Internacionais (ISO)-8859-1 (efetivamente o conjunto de caracteres ASCII) de acordo com a especificação HTTP versão 1.1.
-   *Para conteúdo em JSON,* o serviço efetivamente sempre usa o conjunto de caracteres Unicode Transformation Format (UTF)-8 de acordo com a Seção 8.1 da International Engineering Task Force (IETF) [Solicitação de Comentários (RFC) 7159 ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://tools.ietf.org/html/rfc7159#section-8.1){: new_window}.

Ao enviar conteúdo em texto sem formatação ou HTML, inclua o parâmetro `charset` com o cabeçalho `Content-Type` para indicar a codificação de caracteres do texto de entrada. O exemplo a seguir especifica codificação de caracteres UTF-8 para entrada de texto sem formatação:

```
Content-Type: text/plain;charset=utf-8
```
{: codeblock}

Usando o parâmetro `charset`, é possível evitar problemas em potencial que estão associados a caracteres não ASCII ou não imprimíveis. Se você passar dados UTF-8 sem especificar o conjunto de caracteres, os caracteres especiais poderão resultar em resultados incorretos ou em erros de nível de HTTP 400 ou 500.

### Usando o comando curl
{: #charsetCurl}

Para evitar erros ao usar o comando `curl`, sempre transmita o conteúdo por meio da opção `--data-binary`do comando `curl`para preservar qualquer codificação UTF-8 do conteúdo. Se você usar a opção `--data` para passar o conteúdo como ASCII, o comando poderá processar a entrada, o que poderá causar problemas para dados codificados em UTF-8.

Por exemplo, o comando `curl` a seguir usa a opção `--data-binary` corretamente para postar os conteúdos do *filename* especificado sem processamento adicional. O comando especifica o parâmetro `charset` com o cabeçalho `Content-Type` e ele solicita o formato de resposta de JSON com o cabeçalho `Accept`.

```bash
curl -X POST -u "apikey: { apikey }"
--header "Content-Type: text/plain;charset=utf-8"
--header "Accept: application/json"
--data-binary @{filename}
"https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13"
```
{: pre}

Para obter mais exemplos de como chamar o serviço com diferentes formatos de solicitação e resposta, consulte o [Tutorial de introdução](/docs/services/personality-insights?topic=personality-insights-gettingStarted).

## Especificando entrada em JSON
{: #json}

Para passar entrada em JSON, você usa o objeto `Content`. O objeto inclui uma matriz de objetos `ContentItem`, cada um dos quais contém um elemento do conteúdo. O único campo obrigatório do objeto é `content`, que fornece o texto a ser analisado. Outros campos opcionais são

-   `id` (sequência) é um ID exclusivo para o item de conteúdo.
-   `created` (número inteiro) é um registro de data e hora UNIX que indica quando o item de conteúdo foi criado.
-   `updated` (número inteiro) é um registro de data e hora UNIX que indica quando o item de conteúdo foi atualizado pela última vez.
-   `contenttype` (sequência) indica o tipo do item de conteúdo: `text/plain` ou `text/html`.
-   `language` (sequência) indica o idioma do item de conteúdo: `ar` (árabe), `en` (inglês), `es` (espanhol), `ja` (japonês) ou `ko` (coreano). Consulte [Especificando idiomas de solicitação e resposta](#languages-input).
-   `parentid` (sequência) é o `id` do item pai do item de conteúdo.
-   `reply` (booleano) indica se o item de conteúdo é uma resposta a outro item.
-   `forward` (booleano) indica se o item de conteúdo é um encaminhamento ou cópia de outro item.

Entrada em JSON é bem adequada para conteúdo do Twitter ou de outras redes sociais que consistem em várias conversas ou posts. Em vez de concatenar todo o texto do autor em uma única sequência, é possível usar JSON para enviar os dados como existem. Essa abordagem tem a vantagem adicional de permitir que o serviço saiba quais partes do texto estão relacionadas.

### Entrada em JSON de exemplo
{: jsonExample}

Exemplos no [Tutorial de introdução](/docs/services/personality-insights?topic=personality-insights-gettingStarted) usam o arquivo JSON de amostra <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="Ícone de link externo" title="Ícone de link externo"></a>. O arquivo inclui uma série de mensagens do Twitter. O exemplo a seguir mostra os primeiros tweets do arquivo.

```javascript
{
  "contentItems": [
    {
      "content": "Wow, I liked @TheRock before, now I really SEE how special he is. The daughter story was IT for me. So great! #MasterClass",
      "contenttype": "text/plain",
      "created": 1447639154000,
      "id": "666073008692314113",
      "language": "en"
    },
    {
      "content": ".@TheRock how did you Know to listen to your gut and Not go back to football? #MasterClass",
      "contenttype": "text/plain",
      "created": 1447638226000,
      "id": "666069114889179136",
      "language": "en"
    },
    . . .
  ]
}
```
{: codeblock}

## Especificando idiomas de solicitação e resposta
{: #languages-input}

É possível usar os parâmetros de cabeçalho `Content-Language` e `Accept-Language` para indicar o idioma do conteúdo de entrada e o idioma da resposta do serviço. É possível usar qualquer combinação de idiomas suportados para a solicitação e a resposta. Se você não indicar um idioma, o serviço usará seus modelos treinados de inglês para a análise e inglês para os resultados. A tabela a seguir lista os idiomas de entrada e de saída suportados e identifica os argumentos que você usa com os parâmetros relacionados ao idioma.

<table style="width:90%">
  <caption>Tabela 2. Especificando idiomas de solicitação e resposta</caption>
  <tr>
    <th style="width:28%; text-align:left; vertical-align:bottom">
      Idioma
    </th>
    <th style="width:12%; text-align:center; vertical-align:bottom">
      Argumento
    </th>
    <th style="width:30%; text-align:center; vertical-align:bottom">
      Suportado por<br/>
      <code>Content-Language</code>
    </th>
    <th style="width:30%; text-align:center; vertical-align:bottom">
      Suportado por<br/>
      <code>Accept-Language</code>
    </th>
  </tr>
  <tr>
    <td style="text-align:left">
      Árabe
    </td>
    <td style="text-align:center">
      <code>ar</code>
    </td>
    <td style="text-align:center">
      Sim
    </td>
    <td style="text-align:center">
      Sim
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Inglês
    </td>
    <td style="text-align:center">
      <code>en</code>
    </td>
    <td style="text-align:center">
      Sim
    </td>
    <td style="text-align:center">
      Sim
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Japonês
    </td>
    <td style="text-align:center">
      <code>ja</code>
    </td>
    <td style="text-align:center">
      Sim
    </td>
    <td style="text-align:center">
      Sim
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Coreano
    </td>
    <td style="text-align:center">
      <code>ko</code>
    </td>
    <td style="text-align:center">
      Sim
    </td>
    <td style="text-align:center">
      Sim
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Espanhol
    </td>
    <td style="text-align:center">
      <code>es</code>
    </td>
    <td style="text-align:center">
      Sim
    </td>
    <td style="text-align:center">
      Sim
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Português do Brasil
    </td>
    <td style="text-align:center">
      <code>pt-br</code>
    </td>
    <td style="text-align:center">
      no
    </td>
    <td style="text-align:center">
      Sim
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Francês
    </td>
    <td style="text-align:center">
      <code>fr</code>
    </td>
    <td style="text-align:center">
      no
    </td>
    <td style="text-align:center">
      Sim
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Alemão
    </td>
    <td style="text-align:center">
      <code>de</code>
    </td>
    <td style="text-align:center">
      no
    </td>
    <td style="text-align:center">
      Sim
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Italiano
    </td>
    <td style="text-align:center">
      <code>it</code>
    </td>
    <td style="text-align:center">
      no
    </td>
    <td style="text-align:center">
      Sim
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Chinês Simplificado
    </td>
    <td style="text-align:center">
      <code>zh-cn</code>
    </td>
    <td style="text-align:center">
      no
    </td>
    <td style="text-align:center">
      Sim
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Chinês Tradicional
    </td>
    <td style="text-align:center">
      <code>zh-tw</code>
    </td>
    <td style="text-align:center">
      no
    </td>
    <td style="text-align:center">
      Sim
    </td>
  </tr>
</table>

Envie todo o texto no mesmo idioma; não misture vários idiomas na mesma solicitação. Para argumentos de idioma de dois caracteres, o serviço tratará variantes regionais como seu idioma pai; por exemplo, interpretará `en-US` como `en`.

### Especificar um idioma para conteúdo em JSON
{: #languageJSON}

Para entrada em texto sem formatação e HTML, o cabeçalho `Content-Language` é a única maneira para especificar o idioma. Para entrada em JSON, também é possível especificar o idioma de cada item de conteúdo individual usando o parâmetro `language` do objeto `ContentItem`. Para JSON, um idioma especificado com o cabeçalho `Content-Language` substitui um idioma especificado para um item de conteúdo; o serviço ignora os itens de conteúdo que especificam um idioma diferente.

Omita o cabeçalho `Content-Type` para basear o idioma apenas na especificação dos itens de conteúdo. O serviço usa o idioma mais predominante entre os itens de conteúdo, o que mostra como resultado os melhores resultados possíveis. Ele conta o número de itens de conteúdo para cada idioma e seleciona o idioma com maior frequência. Se vários idiomas tiverem a mesma frequência máxima, o serviço usará o idioma que atingir o valor primeiro. Novamente, o serviço ignora itens de conteúdo que especificam um idioma diferente.

### Considerações sobre o idioma
{: #languageNotes}

Considere os detalhes a seguir ao enviar texto de entrada:

-   *Para inglês,* as bases de serviço resultam em normas culturais dos EUA. Se você analisar texto em inglês de uma cultura diferente, talvez seja necessário ajustar os resultados.
-   *Para árabe,* o serviço pode cortar a quantia de texto de entrada por motivos de desempenho. Em um determinado limite, a precisão dos resultados em árabe não melhora com mais palavras. Se o serviço cortar entrada em árabe, ele retornará uma mensagem de aviso para informar que reduziu a quantia de texto de entrada usado para o perfil.
-   *Para árabe e coreano,* o serviço não pode retornar resultados significativos para um subconjunto de características. Para obter mais informações, veja [Limitações para entrada em árabe e coreano](/docs/services/personality-insights?topic=personality-insights-numeric#limitations).

Para obter informações gerais sobre o uso de texto traduzido, consulte [Inferindo personalidade de texto traduzido](/docs/services/personality-insights?topic=personality-insights-guidance#translation).

## Fornecendo entrada suficiente
{: #sufficient}

Um perfil de personalidade significativo poderá ser criado apenas quando dados suficientes de quantia e qualidade adequadas forem fornecidos. Como o uso do idioma varia naturalmente de um documento para outro e ocasionalmente, uma pequena amostra de texto pode não ser representativa dos padrões de linguagem em geral de um indivíduo. Além disso, diferentes características e mídia diferente convergem em diferentes taxas.

É possível enviar o serviço com até 20 MB de conteúdo de entrada. Até certo ponto, mais palavras provavelmente produzirão melhores resultados, melhorando a precisão do serviço ao reduzir o desvio entre os resultados previstos e pontuação real do autor. Mas a precisão se estabiliza em aproximadamente 3000 palavras de entrada e adicionar mais conteúdo não contribui para a precisão do perfil. Portanto, o serviço extrai e usa apenas os primeiros 250 KB de conteúdo, sem contar qualquer marcação de HTML ou JSON, de solicitações grandes.

Esta figura não é mapeada para um número exato de palavras, que varia com base na linguagem e natureza do texto. Em inglês, por exemplo, o comprimento médio da palavra é entre quatro e cinco caracteres; portanto, essa figura fornece cerca de 50.000 palavras. Esse número é de pelo menos 15 vezes mais palavras do que o serviço precisa para produzir um perfil preciso. Ao truncar a entrada longa, o serviço melhora o tempo de resposta sem sacrificar precisão. O campo `word_count`do JSON de resposta indica o número de palavras que o serviço usa para um pedido, que pode ser menor que o número de palavras enviadas.

O serviço valida apenas o número de palavras que você enviar. Se você enviar palavras suficientes, o serviço produzirá um perfil. O serviço não verifica se há palavras ou sentenças duplicadas. Essa validação é subjetiva e melhor deixada para o usuário, que pode ter razões válidas para enviar essa entrada. Portanto, é possível obter um perfil enviando a mesma palavra ou sentença muitas vezes, mas o perfil resultante não é necessariamente significativo.
{: note}

### Diretrizes e recomendações
{: #sufficientGuidelines}

A tabela a seguir relata dois valores para diferentes quantidades de texto de entrada:

-   O *Erro médio absoluto (MAE)* em todas as características com base no número de palavras que são fornecidas como entrada. Quanto menor o MAE, mais próximos os resultados do serviço são das pontuações que o autor receberia ao fazer um teste de personalidade.
-   A *Correlação média* entre as pontuações inferidas e reais entre todas as características. Quanto mais próxima a correlação estiver de 1, melhores serão as previsões. As correlações maiores que 0,2 são consideradas aceitáveis; a correlação mais alta que 0,4 é rara.

As informações são baseadas em dados no idioma inglês, mas as diretrizes gerais se aplicam a todos os idiomas. Para obter mais informações sobre MAE e correlação médios, incluindo estatísticas específicas do idioma, consulte [Qual é a precisão do serviço](/docs/services/personality-insights?topic=personality-insights-science#researchPrecise).

<table style="width:80%">
  <caption>Tabela 3. MAE e correlação médios</caption>
  <tr>
    <th style="text-align:center; vertical-align:bottom; width:24%">Número de palavras</th>
    <th style="text-align:center; width:38%">Média de MAE<br/>em todas as características</th>
    <th style="text-align:center; width:38%">Correção média<br/>em todas as características</th>
  </tr>
  <tr>
    <td style="text-align:center">3000</td>
    <td style="text-align:center">12,1%</td>
    <td style="text-align:center">0,257</td>
  </tr>
  <tr>
    <td style="text-align:center">1200</td>
    <td style="text-align:center">12,2%</td>
    <td style="text-align:center">0,237</td>
  </tr>
  <tr>
    <td style="text-align:center">600</td>
    <td style="text-align:center">12,3%</td>
    <td style="text-align:center">0,212</td>
  </tr>
  <tr>
    <td style="text-align:center">300</td>
    <td style="text-align:center">12,5%</td>
    <td style="text-align:center">0,175</td>
  </tr>
  <tr>
    <td style="text-align:center">100</td>
    <td style="text-align:center">12,7%</td>
    <td style="text-align:center">0,095</td>
  </tr>
</table>

Conforme as diretrizes a seguir indicam, a {{site.data.keyword.IBM_notm}} recomenda que você forneça pelo menos 1200 palavras, mas fornecer pelo menos 600 palavras produz resultados aceitáveis:

-   3000 palavras são suficientes para alcançar a precisão máxima do serviço.
-   Pelo menos 1200 palavras resulta em um MAE que está na margem de dois por cento do melhor MAE que o serviço pode retornar.
-   Entre 600 e 1.200 palavras resulta em um MAE que está na margem de três por cento do melhor MAE que o serviço pode retornar.
-   Menos de 600 palavras gera um aviso, mas o serviço ainda analisa a entrada.
-   Menos de 100 palavras gera um erro.

Essas diretrizes podem ajudá-lo a acomodar a confiabilidade dos resultados para seu aplicativo. Por exemplo, para um aplicativo casual que recomenda filmes, você pode estar confortável com menos precisão. Para um aplicativo que faz recomendações mais críticas, é provável que você precise de resultados mais precisos. Para obter mais informações sobre como o serviço infere características da personalidade, consulte [Como características da personalidade são inferidas](/docs/services/personality-insights?topic=personality-insights-science#researchInfer).

## Solicitando pontuações brutas
{: #rawScores-input}

O serviço sempre retorna pontuações normalizadas para cada característica de personalidade (dimensão e aspecto do Big Five, Necessidade e Valor) como parte de sua resposta. O serviço também poderá relatar um `raw_score` para cada característica se você configurar o parâmetro de consulta `raw_scores` para `true`. Pontuações brutas representam resultados para as características que são baseadas exclusivamente no texto do autor e no modelo para essa característica, sem comparar os resultados com uma população de amostra. Para obter mais informações sobre como usar as pontuações brutas, consulte [Pontuações brutas para características da personalidade](/docs/services/personality-insights?topic=personality-insights-numeric#rawScores-numeric).

## Solicitando preferências de consumo
{: #preferences-input}

O serviço sempre retorna resultados para os modelos de personalidade. Quando você configurar o parâmetro de consulta `consumption_preferences` como `true`, o serviço também retornará `scores` para várias preferências de consumo. O serviço baseia as preferências nas características de personalidade que ele infere por meio do texto de entrada. Esses resultados indicam a tendência do autor em preferir diferentes produtos, serviços e atividades. Os negócios podem usar os resultados para entender melhor as inclinações do autor e para personalizar comunicações e ofertas para o autor.

Para obter mais informações sobre as diferentes preferências de consumo, consulte [Preferências de consumo](/docs/services/personality-insights?topic=personality-insights-preferences). Para obter informações sobre como interpretar os resultados numéricos de uma preferência, consulte [Pontuações para preferências de consumo](/docs/services/personality-insights?topic=personality-insights-numeric#scores).

## Especificando a versão da interface
{: #version}

Todas as chamadas para o método `/v3/profile` devem incluir o parâmetro de consulta `version` para indicar a versão da API do serviço e o formato de resposta que você deseja usar. Você especifica a versão como uma data no formato `YYYY-MM-DD`; por exemplo, especifique `2017-10-13` para 13 de outubro de 2017 (a versão mais recente). O parâmetro permite que o serviço atualize sua API e seu formato de resposta para novas versões sem interromper clientes existentes. Para obter informações sobre todas as versões disponíveis, consulte as [Notas sobre a liberação](/docs/services/personality-insights?topic=personality-insights-release-notes).

A data que você especificar não precisará corresponder a uma versão do serviço exatamente; o serviço usará a versão que não seja posterior à data fornecida. Se você especificar uma data que seja anterior à liberação inicial da versão 3 (`2016-10-19`), o serviço usará essa versão da API. Se você especificar uma data que esteja no futuro ou que seja posterior à versão mais recente, o serviço usará a versão mais recente.
