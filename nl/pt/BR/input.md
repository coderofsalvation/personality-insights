---

Copyright: years: 2015, 2017 lastupdated: "2017-10-12"

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

# Solicitando um perfil
{: #input}

Para analisar o conteúdo, você usa o HTTP `POST` pedido de método para chamar o `/v3/profile` método do {{site.data.keyword.personalityinsightsshort}} serviço. É possível passar pelo serviço com um máximo de 20 MB de conteúdo a ser analisado por meio do corpo da solicitação, mas o serviço requer muito menos entradas para produzir um perfil de personalidade preciso; para obter mais informações, consulte [Fornecendo entrada suficiente](#sufficient).
{: shortdesc}

O `/v3/profile` método inclui parâmetros que permitem especificar o tipo de conteúdo ser transmitido para e retornadas pelo serviço, bem como o idioma de cada tipo de conteúdo. O serviço sempre retorna um perfil que fornece insight sobre as características da personalidade do autor do texto de entrada. Você também pode solicitar que o serviço retorne resultados brutos e preferências de consumo.

As seções a seguir descrevem os parâmetros do método `/v3/profile`. Para obter informações sobre os resultados de uma solicitação, consulte [Entendendo um perfil JSON](/docs/services/personality-insights/output.html) e [Entendendo um perfil CSV](/docs/services/personality-insights/output-csv.html). Para obter informações detalhadas sobre o `/v3/profile` método, consulte a [Referência de API ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}.

## Especificar formatos de solicitação e resposta
{: #formats}

É possível usar o `Content-Type` e `Aceitar` cabeçalho parâmetros para indicar o formato do conteúdo que você está transmitindo para o método e o formato de resposta do serviço. É possível usar qualquer combinação de formatos suportados para o pedido e resposta.

<table>
  <caption>Tabela 1. Especificar formatos de solicitação e resposta</caption>
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
      <code>Aceitar</code>
    </th>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      Texto Simples
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>text/plain</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      Sim (padrão)<br/><br/>
      O texto sem formatação do serviço sem modificação.
    </td>
    <td style="text-align:center; vertical-align:top">
      Não
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
      As tags faixas de serviço do conteúdo antes de processar isso.
    </td>
    <td style="text-align:center; vertical-align:top">
      Não
    </td>
  </tr>
  <tr>
    <td style="text-align:left; vertical-align:top">
      JSON
    </td>
    <td style="text-align:center; vertical-align:top">
      <code>application / json</code>
    </td>
    <td style="text-align:center; vertical-align:top">
      Sim<br/><br/>
      O conteúdo deve estar em conformidade com o modelo definido pelo <code>Conteúdo</code> objeto, que é uma matriz de <code>ContentItem</code> objetos.
    </td>
    <td style="text-align:center; vertical-align:top">
      Sim (padrão)<br/><br/>
      O serviço retorna seus resultados como um <code>Perfil</code> objeto.
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
      Não
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

Por padrão, o serviço usa o seguinte conjuntos de caracteres para conteúdo de entrada:

-   *Para texto simples e conteúdo HTML,* o serviço usa o International Standards Organization (ISO) -8859-1 conjunto de caracteres (efetivamente o conjunto de caracteres ASCII) por a especificação HTTP version 1.1.
-   *Para conteúdo JSON,* o serviço efetivamente sempre usa o Formato de Transformação Unicode (UTF) -8 caracteres configurado por Seção 8,1 da International Engineering Task Force (IETF) [Pedido de Comentário (RFC) 7159 ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://tools.ietf.org/html/rfc7159#section-8.1){: new_window}.

Ao enviar texto simples ou conteúdo HTML, inclua o parâmetro `charset` com o `Content-Type` cabeçalho para indicar a codificação de caracteres do texto de entrada. O exemplo a seguir especifica UTF-8 codificação de caracteres para entrada de texto simples:

```
Content-Type: text/plain;charset=utf-8
```
{: codeblock}

Usando o `charset` parâmetro, você pode evitar problemas em potencial associados a não ASCII ou caracteres não imprimíveis. Se você passar UTF-8 dados sem especificar o conjunto de caracteres, caracteres especiais podem resultar em resultados incorretos ou em HTTP 4*nn* ou 5*nn* erros.

### Usando cURL
{: #charsetCurl}

Para evitar erros ao usar cURL, sempre passar o conteúdo por meio do `--data-binary` opção do `curl` comando para preservar qualquer codificação UTF-8 para o conteúdo. Se você usar o `--data` opção para passar o conteúdo como ASCII, o comando pode processar a entrada, que pode causar problemas para dados codificados em UTF-8.

Por exemplo, o seguinte `curl` comando corretamente usa o `--data-binary` opção para postar o conteúdo do especificado *filename* sem processamento adicional. O comando também usa o `charset` parâmetro com o `Content-Type` cabeçalho, e isso solicita explicitamente o formato de resposta JSON padrão.

```bash
Curl -X POST -- usuário {: {
-- header "Content-Type: text/plain;charset=utf-8"
-- header "Accept: application / json"
--data-binary @ {3}/profile?version=2017-10-13"
```
{: pre}

Para obter exemplos adicionais de como chamar o serviço com formatos diferentes de solicitação e de resposta, consulte o [Tutorial de introdução](/docs/services/personality-insights/getting-started.html).

## Especificando entrada JSON
{: #json}

Para transmitir entrada JSON, você usa o `Conteúdo` objeto. O objeto inclui uma matriz de `ContentItem` objetos, cada um dos quais contém um elemento do conteúdo. O único campo obrigatório do objeto é `conteúdo`, que fornece o texto a ser analisado. Outros campos opcionais permitem especificar o seguinte:

-   `id` (sequência) é um ID exclusivo para o item de conteúdo.
-   `criado` (inteiro) é um registro de UNIX que indica quando o item de conteúdo foi criado.
-   `atualizado` (inteiro) é um registro de UNIX que indica quando o item de conteúdo foi atualizado pela última vez.
-   `contenttype` (cadeia) indica o tipo do item de conteúdo, `text/plain` ou `text/html`.
-   `idioma` (sequência) indica o idioma do item de conteúdo: `ar` (Árabe), `en` (inglês), `es` (Espanhol), `ja` (Japonês), ou `ko` (Coreano). Consulte [Especificando idiomas de solicitação e de resposta](#languages).
-   `parentid` (sequência) é o `id` do item pai do item de conteúdo.
-   `resposta` (boolean) indica se o item de conteúdo é uma resposta a outro item.
-   `avançar` (boolean) indica se o item de conteúdo é um encaminhamento ou cópia de outro item.

Entrada JSON é bem adequado para o conteúdo do Twitter ou outras redes sociais que consistem em várias conversas ou posts. Em vez de concatenar todos texto do autor em uma única cadeia, você pode utilizar JSON para enviar os dados como ela existe. Isso tem a vantagem adicional de permitir que o serviço saiba quais partes de texto são relacionados.

### Exemplo de JSON de entrada
{: jsonExample}

Exemplos no [Introdução ao tutorial](/docs/services/personality-insights/getting-started.html) usam a amostra JSON no arquivo <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="External link icon" title="External link icon" class="style-scope doc-content"></a>. O arquivo inclui uma série de mensagens no Twitter. O exemplo a seguir mostra os primeiros tweets do arquivo.

```javascript
{
  "ContentItems": [ {
      "Content": " Uau, gostei @TheRock antes, agora eu realmente ver o quanto ele é especial. A história filha era de TI para mim. Tão bom! #MasterClass "," contenttype ":" text/plain ", "created": 1447639154000, "id": "666073008692314113", "language": "en"
    },
    {
      "Content": ". @TheRock como você sabe para ouvir sua intuição e não voltar para o futebol? #Masterclass",
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

## Especificando linguagens de solicitação e resposta
{: #languages}

É possível usar o `Content-Language` e `Accept-Language` do cabeçalho parâmetros para indicar o idioma do conteúdo de entrada e o idioma da resposta do serviço. É possível usar qualquer combinação de idiomas suportados para a solicitação e a resposta. Se você não indicar um idioma, o serviço usa seus modelos English-trained para sua análise e inglês para seus resultados. A tabela a seguir lista os idiomas suportados de entrada e saída e identifica os argumentos que você usa com os parâmetros relacionados ao idioma.

<table style="width:90%">
  <caption>Tabela 2. Especificando linguagens de solicitação e resposta</caption>
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
      <code>pt-BR</code>
    </td>
    <td style="text-align:center">
      Não
    </td>
    <td style="text-align:center">
      Sim
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      França
    </td>
    <td style="text-align:center">
      <code>fr</code>
    </td>
    <td style="text-align:center">
      Não
    </td>
    <td style="text-align:center">
      Sim
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Alemanha
    </td>
    <td style="text-align:center">
      <code>de</code>
    </td>
    <td style="text-align:center">
      Não
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
      Não
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
      Não
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
      Não
    </td>
    <td style="text-align:center">
      Sim
    </td>
  </tr>
</table>

Enviar todos texto no mesmo idioma; não misture vários idiomas no mesmo pedido. Para argumentos de idioma de dois caracteres, o serviço tratará variantes regionais como seu pai idioma; por exemplo, ele interpretará `en-US` como `en`.

### Especificar um idioma para o conteúdo JSON
{: #languageJSON}

Para texto simples e entrada HTML, o `Content-Language` do cabeçalho é o único caminho para especificar o idioma. Para entrada JSON, você também pode especificar o idioma de cada item de conteúdo individuais usando o `idioma` do parâmetro `ContentItem` objeto. No entanto, um idioma especificado com o `Content-Language` do cabeçalho substitui um idioma especificado para um item de conteúdo; o serviço ignora itens de conteúdo que especificam um idioma diferente.

Omita o `Content-Type` cabeçalho para basear o idioma apenas na especificação dos itens de conteúdo. O serviço usa a linguagem mais prevalente entre os itens de conteúdo, o que produz os melhores resultados possíveis. Ele conta o número de itens de conteúdo para cada idioma e seleciona o idioma com maior frequência. Se vários idiomas têm a mesma frequência máxima, o serviço usa o idioma que atinge o primeiro valor. Novamente, o serviço ignora itens de conteúdo que especificam um idioma diferente.

### Considerações de Idioma
{: #languageNotes}

Considere o seguinte ao enviar texto de entrada:

-   *Para inglês,* resultados são baseados em normas culturais dos EUA. Se você analisar texto em inglês de uma cultura diferente, você pode precisar ajustar os resultados de acordo.
-   *Para árabe,* o serviço pode reduzir a quantidade de texto de entrada por motivos de desempenho. Em um determinado limite, a precisão dos resultados árabe não melhorar com mais palavras. Se o serviço de entrada reduz árabe, ele retornará uma mensagem de aviso para informar que ele reduziu a quantidade de texto de entrada que é usado para o perfil.
-   *Para árabe e coreano,* o serviço não pode retornar resultados significativos para um subconjunto de características. Para obter mais informações, consulte [Limitações para entrada árabe e coreano](/docs/services/personality-insights/numeric.html#limitations).

Para obter informações gerais sobre o uso texto traduzido, consulte [Inferindo a personalidade de tradução de texto](/docs/services/personality-insights/guidance.html#translation).

## Fornecer entrada suficiente
{: #sufficient}

Um perfil de personalidade significativas podem ser criados apenas onde os dados suficientes de quantidade adequada e de qualidade é fornecido. Como usar o idioma natural do documento varia para documentar e de vez em quando, uma pequena amostra de texto não pode ser representante de padrões de idioma geral de um indivíduo. Além disso, características diferentes e mídias diferentes convergem em taxas um pouco diferente.

Até um ponto, mais palavras são deve produzir melhores resultados, melhorando a precisão do serviço reduzindo o desvio entre os resultados previstos e pontuação real do autor. Você pode enviar o serviço até 20 MB de conteúdo de entrada, mas níveis de precisão de cerca de 3000 palavras de entrada; conteúdo adicional não contribui mais para a precisão do perfil. Portanto, o serviço extrai e usa apenas os primeiros 250 KB de conteúdo, sem contar qualquer marcação HTML ou JSON, de solicitações grandes.

Esta figura não mapeia para um número exato de palavras, que varia com base no idioma e a natureza do texto. Em inglês, por exemplo, o comprimento da palavra média é entre quatro e cinco caracteres, então essa figura fornece cerca de 50.000 palavras, que é pelo menos 15 vezes mais palavras do que o serviço precisa produzir um perfil preciso. Ao truncar a entrada tempo, o serviço melhora o tempo de resposta sem sacrificar precisão. O `word_count` do JSON de resposta indica o número de palavras que o serviço realmente usa para um pedido, que pode ser menor que o número de palavras enviadas.

### Diretrizes e recomendações
{: #sufficientGuidelines}

A tabela a seguir relata dois valores para diferentes quantidades de texto de entrada:

-   *Média Erro Absoluto Médio (MAE)* em todas as características com base no número de palavras fornecido como entrada. Quanto menor o MAE, mais perto os resultados do serviço são as contas a autora receberia tomando um teste de personalidade real.
-   A *Correlação média* entre as pontuações inferidas e as reais entre todas as características. Quanto mais a correlação é 1, melhor as previsões, embora correlações acima de 0,2 são considerados aceitáveis e aqueles acima de 0,4 são raros.

As informações são baseadas em dados em inglês, mas as orientações gerais se aplicam a todos os idiomas. Para obter mais informações sobre média de MAE e correlação, incluindo estatísticas específicas do idioma, consulte [Como exato é o serviço](/docs/services/personality-insights/science.html#researchPrecise).

<table style="width:80%">
  <caption>Tabela 3. Média MAE e correlação</caption>
  <tr>
    <th style="text-align:center; vertical-align:bottom; width:24%">Número de palavras</th>
    <th style="text-align:center; width:38%">Média MAE<br/>Em todas as características</th>
    <th style="text-align:center; width:38%">Média de correlação<br/>Em todas as características</th>
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

Como as diretrizes a seguir indicam, {{site.data.keyword.IBM_notm}} recomenda que você fornecer pelo menos 1200 palavras, mas fornecendo pelo menos 600 palavras produz resultados aceitáveis:

-   3000 palavras são suficientes para alcançar precisão máxima do serviço.
-   Pelo menos 1200 palavras resultam em um MAE que está dentro de dois por cento dos melhores MAE que o serviço pode retornar.
-   Entre 600 e 1.200 palavras resultam em um MAE que está dentro de três por cento do melhor MAE que o serviço pode retornar.
-   Menos de 600 palavras gerar um aviso, mas o serviço ainda analisa a entrada.
-   Menos de 100 palavras gerar um erro.

Essas diretrizes podem ajudar você acomodar a confiabilidade dos resultados para seu aplicativo. Por exemplo, para um aplicativo casual que recomenda filmes, você pode estar confortável com menos precisão; para um aplicativo que faz recomendações mais críticas, você provavelmente requer resultados mais precisos. Para obter mais informações sobre como o serviço infere características de personalidade, consulte [Como as características da personalidade são inferidos](/docs/services/personality-insights/science.html#researchInfer).

## Solicitando resultados brutos
{: #rawScores}

O serviço sempre retorna as pontuações normalizadas para cada característica de personalidade (Big Five dimensão e aspecto, Necessidade, e Valor) como parte de sua resposta. O serviço também pode relatar um `raw_score` para cada característica se você configurar o `raw_scores` parâmetro de consulta para `true`. Pontuações brutos representam as pontuações para as características baseado exclusivamente em texto do autor e o modelo para essa característica, sem comparar os resultados para uma população de amostra. Para obter mais informações sobre como usar as pontuações brutos, consulte [pontuações para características da personalidade bruta](/docs/services/personality-insights/numeric.html#rawScores).

## Solicitando preferências de consumo
{: #preferences}

O serviço sempre retorna resultados para os modelos de personalidade. Quando você configurar o `consumption_preferences` parâmetro de consulta para `true`, o serviço também retorna `pontuações` para uma variedade de preferências de consumo com base nas características de personalidade que infere do texto de entrada. Esses resultados indicam tendência do autor preferir diferentes produtos, serviços e atividades. As empresas podem usar os resultados para entender melhor os desejos do autor e personalizar comunicações e ofertas para o autor.

Para obter mais informações sobre as preferências de consumo diferentes, consulte [Consumo Preferências](/docs/services/personality-insights/preferences.html). Para obter informações sobre como interpretar os resultados numéricos para uma preferência, consulte [Escores para consumo preferências](/docs/services/personality-insights/numeric.html#scores).

## Especificando a versão da interface
{: #version}

Todas as chamadas para o `/v3/profile` método deve incluir o `version` consulta parâmetro para indicar a versão do API do serviço e formato de resposta que você deseja usar. Você especifica a versão como uma data no formato `YYYY-MM-DD`; por exemplo, especifique `2017-10-13` para 13 de outubro de 2017. O parâmetro permite que o serviço para atualizar seu formato API e resposta para novas versões sem quebrar clientes existentes.

A data que você especificar não precisa corresponder a uma versão do serviço exatamente; o serviço usa a versão que seja posterior à data não é fornecido. Se você especificar uma data que seja anterior à liberação inicial do versão 3, o serviço usa a versão 3 da API. Se você especificar uma data que está no futuro ou seja mais recente que a versão mais recente, o serviço usa a versão mais recente.
