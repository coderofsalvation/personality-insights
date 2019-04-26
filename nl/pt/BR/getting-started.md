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
{:go: .ph data-hd-programlang='go'}
{:java: .ph data-hd-programlang='java'}
{:python: .ph data-hd-programlang='python'}
{:swift: .ph data-hd-programlang='swift'}
{:download: .download}
{:apikey: data-credential-placeholder='apikey'}
{:url: data-credential-placeholder='url'}
{:hide-dashboard: .hide-dashboard}

# Tutorial Introdução
{: #gettingStarted}

O serviço do {{site.data.keyword.personalityinsightsfull}} deriva insights sobre características da personalidade de mídia social, dados corporativos ou outras comunicações digitais. Este tutorial ajuda a começar a usar rapidamente o serviço do {{site.data.keyword.personalityinsightsshort}}. Os exemplos mostram como chamar o método `POST /v3/profile` do serviço com diferentes tipos de entrada e como solicitar diferentes tipos de saída e formatos de saída.
{: shortdesc}

O tutorial usa as chaves de API do {{site.data.keyword.cloud}} Identity and Access Management (IAM) para autenticação. As instâncias de serviço mais antigas podem continuar a usar o `{username}` e a `{password}` por meio de suas credenciais de serviço do Cloud Foundry existentes para autenticação. Autentique usando a abordagem que está correta para sua instância de serviço. Para obter mais informações sobre o uso do serviço de autenticação do IAM, consulte a [atualização de serviço de 30 de outubro de 2018](/docs/services/personality-insights?topic=personality-insights-release-notes#October2018) nas notas sobre a liberação.
{: important}

## Antes de Começar
{: #before-you-begin}

-   {: hide-dashboard} Crie uma instância do serviço:
    1.  {: hide-dashboard} Acesse a página [{{site.data.keyword.personalityinsightsshort}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://{DomainName}/catalog/services/personality-insights){: new_window} no {{site.data.keyword.cloud_notm}} Catalog.
    1.  {: hide-dashboard} Inscreva-se para obter uma conta gratuita do {{site.data.keyword.cloud_notm}} ou efetue login.
    1.  {: hide-dashboard} Clique em  ** Criar **.
-   Copie as credenciais para autenticação em sua instância de serviço:
    1.  {: hide-dashboard} No [painel do {{site.data.keyword.cloud_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://{DomainName}/dashboard/apps){: new_window}, clique em sua instância do serviço {{site.data.keyword.personalityinsightsshort}} para acessar a página do painel do serviço {{site.data.keyword.personalityinsightsshort}}.
    1.  Na página **Gerenciar**, clique em **Mostrar** para visualizar as suas credenciais.
    1.  Copie os valores `API Key` e `URL`.
-   Certifique-se de que você tenha o comando `curl`.
    -   Os exemplos usam o comando `curl` para chamar métodos da interface de HTTP. Instale a versão para seu sistema operacional de [curl.haxx.se ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://curl.haxx.se/){: new_window}. Instale a versão que suporta o protocolo Secure Sockets Layer (SSL). Certifique-se de incluir o arquivo binário instalado em sua variável de ambiente `PATH`.

Quando você inserir um comando, substitua `{apikey}` e `{url}` por sua chave de API real e URL. Omita as chaves, que indicam um valor de variável, por meio do comando. Um valor real é semelhante ao exemplo a seguir:
{: hide-dashboard}

```bash
curl -X POST -u "apikey:L_HALhLVIksh1b73l97LSs6R_3gLo4xkujAaxm7i-b9x"
. . .
"https://gateway.watsonplatform.net/personality-insights/api/v3/profile?version=2017-10-13"
```
{:pre}
{: hide-dashboard}

## Etapa 1: enviar entrada em texto sem formatação e receber saída básica em JSON
{: #example1}

O primeiro exemplo passa o arquivo de texto simples `profile.txt` para o método `POST /v3/profile` e solicita uma resposta de JSON.

1.  Faça download do arquivo de amostra <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.txt" download="profile.txt">profile.txt <img src="../../icons/launch-glyph.svg" alt="Ícone de link externo" title="Ícone de link externo"></a>.
1.  Emita o comando a seguir para enviar o arquivo para o método `/v3/profile` e solicitar uma resposta de JSON.
    -   O cabeçalho `Content-Type` especifica que a entrada é texto simples, `text/plain`. O parâmetro `charset` incluído com o cabeçalho identifica a codificação de caracteres do texto de entrada.
    -   O cabeçalho `Accept` especifica `application/json` para indicar que a saída de JSON é solicitada.
    -   {: hide-dashboard}Substitua `{apikey}` e `{url}` por suas informações.
    -   Modifique `{path_to_file}` para especificar o local do arquivo `profile.txt`.

    ```bash
    curl -X POST -u "apikey: { apikey }"{: apikey} \
    --header "Content-Type: text/plain;charset=utf-8" \
    --header "Accept: application/json" \
    --data-binary @{path_to_file}profile.txt \
    "{url}/v3/profile?version=2017-10-13"{: url}
    ```
    {: pre}

O serviço retorna um objeto JSON `Profile` que inclui metadados básicos, como o número de palavras na entrada, o modelo de idioma com o qual a entrada foi processada e quaisquer avisos associados à entrada. Para obter mais informações, consulte [O objeto Profile](/docs/services/personality-insights?topic=personality-insights-output#outputJSON).

O perfil inclui informações sobre as características da personalidade do Big Five, Necessidades e Valores do autor, conforme inferido do texto de entrada. O serviço relata um `percentile` ou uma pontuação normalizada para cada característica. O serviço calcula o percentil comparando os resultados do autor aos resultados de uma população de amostra. Para obter mais informações, consulte [Saída de características da personalidade](/docs/services/personality-insights?topic=personality-insights-output#traitJSON).

## Etapa 2: enviar entrada em JSON e receber saída em JSON detalhada
{: #example2}

O segundo exemplo passa o arquivo de JSON `profile.json` para o método `/v3/profile`, solicitando novamente uma resposta de JSON. O exemplo solicita preferências de consumo e pontuações brutas para obter uma análise mais detalhada da entrada.

1.  Faça download do arquivo de amostra <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/profile.json" download="profile.json">profile.json <img src="../../icons/launch-glyph.svg" alt="Ícone de link externo" title="Ícone de link externo"></a>, que contém uma coleção de mensagens do Twitter.
1.  Emita o comando a seguir para enviar o arquivo para o método `/v3/profile`. O exemplo especifica `application/json` para os cabeçalhos `Content-Type` e `Accept`; o parâmetro `charset` não é necessário para a entrada de JSON. O exemplo configura os parâmetros de consulta `consumption_preferences` e `raw_scores` para `true`.

    ```bash
    curl -X POST -u "apikey: { apikey }"{: apikey} \
    --header "Content-Type: application/json" \
    --header "Accept: application/json" \
    --data-binary @{path_to_file}profile.json \
    "{url}/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true"{: url}
    ```
    {: pre}

O serviço retorna um perfil JSON que inclui os metadados e as características retornados com o exemplo anterior. Para cada característica, o serviço também inclui um `raw_score`, que representa a pontuação do autor para a característica baseada unicamente no texto de entrada, sem comparar os resultados a uma população de amostra.

Como o conteúdo de entrada inclui registros de data e hora, o serviço também relata características comportamentais. Essas são características temporais que indicam `percentage` dos itens de conteúdo que foram criados em cada dia da semana e hora do dia. Para obter mais informações, consulte [Saída comportamental](/docs/services/personality-insights?topic=personality-insights-output#behaviorJSON).

O serviço também relata pontuações para sua coleção de preferências de consumo. As pontuações indicam a probabilidade de o autor preferir diferentes produtos, serviços e atividades com base nas características inferidas. Para obter mais informações, consulte [Saída das preferências de consumo](/docs/services/personality-insights?topic=personality-insights-output#preferenceJSON).

## Etapa 3: enviar entrada em JSON e receber saída detalhada em CSV
{: #example3}

O terceiro exemplo é semelhante ao segundo: passa o mesmo conteúdo em JSON e solicita os mesmos resultados. Mas este exemplo especifica `text/csv` para o cabeçalho `Accept` para solicitar a resposta em formato de valores separados por vírgula (CSV). Ele usa a opção `-- output`do comando `curl`para direcionar os resultados para um arquivo denominado `profile.csv`. O exemplo configura o parâmetro de consulta `csv_headers` para `true` para solicitar que os cabeçalhos de coluna sejam retornados com a saída.

1.  Emita o comando a seguir para enviar o arquivo JSON para o método `/v3/profile`. O cabeçalho `Content-Type` identifica o conteúdo de entrada como `application/json` e o cabeçalho `Accept` solicita a saída de CSV, `text/csv`.

    ```bash
    curl -X POST -u "apikey: { apikey }"{: apikey} \
    --header "Content-Type: application/json" \
    --header "Accept: text/csv" \
    --data-binary @{path_to_file}profile.json \
    --output profile.csv \
    "{url}/v3/profile?version=2017-10-13&consumption_preferences=true&raw_scores=true&csv_headers=true"{: url}
    ```
    {: pre}

Para obter uma descrição detalhada da resposta e dos cabeçalhos em CSV, consulte [Entendendo um perfil CSV](/docs/services/personality-insights?topic=personality-insights-outputCSV).

## Etapas Seguintes
{: #gsns}

-   Saiba mais sobre [Solicitando um perfil](/docs/services/personality-insights?topic=personality-insights-input) e sobre [Entendendo um perfil JSON](/docs/services/personality-insights?topic=personality-insights-output) e [Entendendo um perfil CSV](/docs/services/personality-insights?topic=personality-insights-outputCSV).
-   Conheça os [Modelos de personalidade](/docs/services/personality-insights?topic=personality-insights-models) do Big Five, Necessidades e Valores.
-   Saiba mais sobre a API na [Referência de API ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://{DomainName}/apidocs/personality-insights){: new_window}
-   Explore o [Aplicativo de amostra Node.js ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://github.com/watson-developer-cloud/personality-insights-nodejs){: new_window} para saber mais sobre o desenvolvimento de aplicativos com o serviço.
