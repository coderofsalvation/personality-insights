---

copyright:
  years: 2015, 2017
lastupdated: "2017-10-18"

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
{:download: .download}

# Tutorial Introdução

O serviço do {{site.data.keyword.personalityinsightsfull}} deriva insights sobre características da personalidade de mídia social, dados corporativos ou outras comunicações digitais. Este tutorial ajuda a começar a usar rapidamente o serviço do {{site.data.keyword.personalityinsightsshort}}. Os exemplos mostram como chamar o método `POST /v3/profile` do serviço com diferentes tipos de entrada e como solicitar diferentes tipos de saída e formatos de saída.
{: shortdesc}

## Antes de Começar
{: #before-you-begin}

- Crie uma instância do serviço:
    - {: download} Se você estiver vendo isso, você criou sua instância de serviço. Agora, obtenha suas credenciais.
    - Crie um projeto com base em um serviço:
        1.  Acesse a página {{site.data.keyword.watson}} Developer Console [ Serviços ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://console.{DomainName}/developer/watson/services){: new_window}. 
        1.  Selecione {{site.data.keyword.personalityinsightsshort}}, clique em **Incluir serviços** e inscreva-se para uma conta do {{site.data.keyword.Bluemix_notm}} grátis ou efetue login.
        1.  Digite `personality-tutorial` como o nome do projeto e clique em **Criar projeto**.
- Copie as credenciais para autenticação em sua instância de serviço:
    - {: download} No painel de serviço (que você está vendo):
        1.  Clique na guia **Credenciais de serviço**.
        1.  Clique em **Visualizar credenciais** em **Ações**.
        1.  Copie os valores de `username`, `password` e `url`.
        {: download}
    - Em seu projeto **personality-tutorial** no Developer Console, copie os valores de `username`, `password` e `url` para `"personality_insights"` da seção **Credenciais**.
- Certifique-se de que tenha cURL:
    - Os exemplos usam cURL para chamar métodos da interface HTTP. Instale a versão para seu sistema operacional de [curl.haxx.se ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://curl.haxx.se/){: new_window}. Instale a versão que suporta o protocolo Secure Sockets Layer (SSL). Certifique-se de incluir o arquivo binário instalado em sua variável de ambiente `PATH`.

<!-- Remove this text after dedicated instances have the Developer Console: begin -->

Se você usar o {{site.data.keyword.Bluemix_dedicated_notm}}, crie uma instância de serviço na página [{{site.data.keyword.personalityinsightsshort}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://console.{DomainName}/catalog/services/personality-insights/){: new_window} no Catálogo. Para obter detalhes sobre como localizar suas credenciais de serviço, consulte [Credenciais de serviço para serviços do Watson ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](/docs/services/watson/getting-started-credentials.html#getting-credentials-manually){: new_window}.

<!-- Remove this text after dedicated instances have the Developer Console: end -->

## Etapa 1: enviar entrada em texto sem formatação e receber saída básica em JSON
{: #example1}

O primeiro exemplo passa o arquivo de texto sem formatação `profile.txt` para o método `POST /v3/profile` e solicita implicitamente a resposta em JSON padrão.

1.  Faça download do arquivo de amostra <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.txt" download="profile.txt">profile.txt <img src="../../icons/launch-glyph.svg" alt="Ícone de link externo" title="Ícone de link externo" class="style-scope doc-content"></a>.
1.  Emita o comando a seguir para enviar o arquivo para o método `/v3/profile` e solicitar a resposta em JSON padrão. O parâmetro `charset` incluído com o cabeçalho `Content-Type` especifica a codificação de caracteres do texto de entrada.
    -   Substitua `{username}` e `{password}` com suas credenciais de serviço da etapa anterior.
    -   Modifique `{path_to_file}` para especificar o local do arquivo `profile.txt`.

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: text/plain;charset=utf-8" \
    --data-binary "@{path_to_file}profile.txt" \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13"
    ```
    {: pre}

O serviço retorna um objeto JSON `Profile` que inclui metadados básicos, como o número de palavras na entrada, o modelo de idioma com o qual a entrada foi processada e quaisquer avisos associados à entrada. Para obter mais informações, consulte [O objeto Profile](/docs/services/personality-insights/output.html#outputJSON).

O perfil inclui informações sobre as características da personalidade do Big Five, Necessidades e Valores do autor, conforme inferido do texto de entrada. O serviço relata um `percentile` ou uma pontuação normalizada para cada característica. O serviço calcula o percentil comparando os resultados do autor aos resultados de uma população de amostra. Para obter mais informações, consulte [Saída de características da personalidade](/docs/services/personality-insights/output.html#traitJSON).

## Etapa 2: enviar entrada em JSON e receber saída em JSON detalhada
{: #example2}

O segundo exemplo passa o arquivo JSON `profile.json` para o método `/v3/profile`, novamente aceitando a resposta em JSON padrão. O exemplo solicita preferências de consumo e pontuações brutas para obter uma análise mais detalhada da entrada.

1.  Faça download do arquivo de amostra <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="Ícone de link externo" title="Ícone de link externo" class="style-scope doc-content"></a>, que contém uma coleção de mensagens do Twitter.
1.  Emita o comando a seguir para enviar o arquivo para o método `/v3/profile`. O exemplo especifica `application/json` para o cabeçalho `Content-Type`; o parâmetro `charset` não é necessário para entrada em JSON. O exemplo configura os parâmetros de consulta `consumption_preferences` e `raw_scores` para `true`.

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: application/json" \
    --data-binary "@{path_to_file}profile.json" \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true"
    ```
    {: pre}

O serviço retorna um perfil JSON que inclui os metadados e as características retornados com o exemplo anterior. Para cada característica, o serviço também inclui um `raw_score`, que representa a pontuação do autor para a característica baseada unicamente no texto de entrada, sem comparar os resultados a uma população de amostra.

Como o conteúdo de entrada inclui registros de data e hora, o serviço também relata características comportamentais. Essas são características temporais que indicam `percentage` dos itens de conteúdo que foram criados em cada dia da semana e hora do dia. Para obter mais informações, consulte [Saída comportamental](/docs/services/personality-insights/output.html#behaviorJSON).

O serviço também relata pontuações para sua coleção de preferências de consumo. As pontuações indicam a probabilidade de o autor preferir diferentes produtos, serviços e atividades com base nas características inferidas. Para obter mais informações, consulte [Saída das preferências de consumo](/docs/services/personality-insights/output.html#preferenceJSON).

## Etapa 3: enviar entrada em JSON e receber saída detalhada em CSV
{: #example3}

O terceiro exemplo é semelhante ao segundo: passa o mesmo conteúdo em JSON e solicita os mesmos resultados. Mas este exemplo especifica `text/csv` para o cabeçalho `Accept` para solicitar a resposta em formato de valores separados por vírgula (CSV). Ele usa a opção `--output` do comando cURL para direcionar os resultados para um arquivo denominado `profile.csv`. O exemplo configura o parâmetro de consulta `csv_headers` para `true` para solicitar que os cabeçalhos de coluna sejam retornados com a saída.

1.  Emita o comando a seguir para enviar o arquivo JSON para o método `/v3/profile`.

    ```bash
    curl -X POST --user {username}:{password} \
    --header "Content-Type: application/json" \
    --header "Accept: text/csv" \
    --data-binary "@{path_to_file}profile.json" \
    --output profile.csv \
    "https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true&csv_headers=true"
    ```
    {: pre}

Para obter uma descrição detalhada da resposta e dos cabeçalhos em CSV, consulte [Entendendo um perfil CSV](/docs/services/personality-insights/output-csv.html).

## Etapas Seguintes

-   Saiba mais sobre [Solicitando um perfil](/docs/services/personality-insights/input.html) e sobre [Entendendo um perfil JSON](/docs/services/personality-insights/output.html) e [Entendendo um perfil CSV](/docs/services/personality-insights/output-csv.html).
-   Conheça os [Modelos de personalidade](/docs/services/personality-insights/models.html) do Big Five, Necessidades e Valores.
-   Saiba mais sobre a API na [Referência de API ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/watson/developercloud/personality-insights/api/v3/){: new_window}
-   Interaja com a API no [Explorador de API ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://watson-api-explorer.mybluemix.net/apis/personality-insights-v3){: new_window}.
-   Explore o [Aplicativo de amostra Node.js ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window} para saber mais sobre o desenvolvimento de aplicativos com o serviço.
