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

# O serviço em ação
{: #applied}

A {{site.data.keyword.IBM_notm}} e outros pesquisadores validaram muitas hipóteses que estão relacionadas a aplicações reais de características de personalidade. Esses estudos ajudaram a impulsionar o desenvolvimento do serviço {{site.data.keyword.personalityinsightsshort}}. Suas descobertas fornecem insight sobre algumas das várias maneiras pelas quais é possível aplicar o serviço aos seus objetivos de negócios e de comunicação. Para obter mais informações sobre a pesquisa que apoia o serviço do {{site.data.keyword.personalityinsightsshort}}, consulte [A ciência por trás do serviço](/docs/services/personality-insights?topic=personality-insights-science).
{: shortdesc}

## Estudos de pesquisadores da IBM
{: #appliedIBM}

Os estudos a seguir feitos por pesquisadores da {{site.data.keyword.IBM_notm}} indicam que a aplicação dos resultados do serviço pode produzir resultados tangíveis em múltiplos domínios. Os estudos contribuíram diretamente para o desenvolvimento do serviço. A tabela inclui links para seções com mais informações sobre cada estudo.

<table>
  <caption>Tabela 3. Estudos da IBM</caption>
  <tr>
    <th style="text-align:left; width:25%">Estudo</th>
    <th style="text-align:center; width:25%">Sujeitos</th>
    <th style="text-align:left; width:50%">Efeito de características da personalidade</th>
  </tr>
  <tr>
    <td style="vertical-align:top">
      [Respondendo a tweets](#IBMrespond)
      <br/>(coleta de informações)
    </td>
    <td style="text-align:center; vertical-align:top">2000 usuários do Twitter</td>
    <td style="vertical-align:top">
      <strong>Mais propenso a responder:</strong> pontuação alta em dimensões e aspectos do Big Five: busca por entusiasmo, simpatia, nível de atividade, amistosidade, confiança, moralidade, extroversão e afabilidade<br/><br/>
      <strong>Menos propenso a responder:</strong> pontuação alta em aspectos do Big Five: cautela e ansiedade
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      [Retweeting](#IBMretweet)
      <br/>(difusão de informações)
    </td>
    <td style="text-align:center; vertical-align:top">3500 usuários do Twitter</td>
    <td style="vertical-align:top">
      <strong>Mais propenso a retweet:</strong> pontuação alta nas dimensões e nos aspectos Modéstia, Abertura e Simpatia do Big Five
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      [Publicidade direcionada](#IBMtarget)
      <br/>(publicidade não solicitada)
    </td>
    <td style="text-align:center; vertical-align:top">Mais de 6000 usuários do Twitter
    </td>
    <td style="vertical-align:top">
      <strong>Responder de forma mais favorável:</strong> pontuação alta em dimensão do Big Five: abertura; e pontuação baixa em dimensão do Big Five: escala emocional
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      [Campanhas de marketing](#IBMcampaign)
      <br/>(resgate de cupom)
    </td>
    <td style="text-align:center; vertical-align:top">Milhares de clientes de varejo</td>
    <td style="vertical-align:top">
      <strong>Mais propenso a responder:</strong> pontuação alta em aspectos do Big Five: ordenação, autodisciplina e cautela; e pontuação baixa em aspecto do Big Five: sem moderação
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      [Preferência de marca](#IBMbrand)
      <br/>(afinidade por marca)
    </td>
    <td style="text-align:center; vertical-align:top">600 usuários do Twitter</td>
    <td style="vertical-align:top">
      <strong>Preditores de preferência de marca:</strong> dimensões e aspectos do Big Five: estado consciente, conservação, autoaprimoramento e afabilidade; Necessidades: amor e ideal; e Valor: hedonismo
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      [Satisfação de membro](#IBMmember)
      <br/>(realização da comunidade)
    </td>
    <td style="text-align:center; vertical-align:top">Mais de 3.000 membros da comunidade</td>
    <td style="vertical-align:top">
      <strong>Preditores de satisfação de membro:</strong> características como raiva, ansiedade, trabalho, lazer, inibição, aprovação e uso de pronome na primeira pessoa
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      [Preferência de leitura](#IBMreading)
      <br/>(interesse no conteúdo)
    </td>
    <td style="text-align:center; vertical-align:top">Mais de 200 participantes</td>
    <td style="vertical-align:top">
      <strong>Interesse em artigos ambientais:</strong> pontuação alta em Valor: autotranscendência<br/><br/>
      <strong>Interesse em artigos relacionados a trabalho:</strong> pontuação alta em Valor: autoaprimoramento
    </td>
  </tr>
  <tr>
    <td style="vertical-align:top">
      [Prevendo preferências de consumo](#IBMpreferences)<br/>
      (compras de consumidor)
    </td>
    <td style="text-align:center; vertical-align:top">Centenas de milhares de registros de dados</td>
    <td style="vertical-align:top">
      <strong>Prevendo preferências do consumidor:</strong> dados demográficos e características da personalidade
    </td>
  </tr>
</table>

### Respondendo a tweets
{: #IBMrespond}

A {{site.data.keyword.IBM_notm}} identificou que pessoas com características da personalidade específicas respondem mais prontamente a tarefas de coleta de informações. A {{site.data.keyword.IBM_notm}} realizou recentemente um estudo de mais de 2.000 usuários do Twitter. Os estudos ajudaram a {{site.data.keyword.IBM_notm}} a entender os fatores que influenciam a probabilidade de responder a essas tarefas e a desenvolver modelos para prever respostas a perguntas ([Mahmud e outros, 2013](/docs/services/personality-insights?topic=personality-insights-references#mahmud2013) e [Mahmud e outros, 2014](/docs/services/personality-insights?topic=personality-insights-references#mahmud2014)).

A {{site.data.keyword.IBM_notm}} treinou o modelo que foi usado no estudo de dois conjuntos de dados de perguntas e respostas em que foram feitas perguntas os usuários do Twitter com base em local ou relacionadas a produtos. As perguntas dependem de se os usuários relataram estar presentes em um local ou possuir um produto. Como recursos no modelo de predição, {{site.data.keyword.IBM_notm}}incluído

-   Comportamento social (por exemplo, taxa de resposta passada e atividade de tweeting)
-   Readiness (por exemplo, por quanto tempo o usuário está inativo)
-   Recursos de categoria do dicionário de psicolinguística do Linguistic Inquiry and Word Count (LIWC)
-   Grandes dimensões e máscaras de cinco dimensões

{{site.data.keyword.IBM_notm}}localizou um conjunto de características de personalidade do Big Five que é significante na previsão da probabilidade de resposta. {{site.data.keyword.IBM_notm}}descobriu que as pessoas que pontuam alto nas dimensões e facetas excitam a busca, a amizade, o nível de atividade, a gregação, a confiança, a moralidade, a exversão e a serenidade são mais propensos a responder aos tweets. Como alternativa, pessoas que pontuam alto nos aspectos de cautela e ansiedade são menos propensas a responder. Esses resultados foram considerados estatisticamente significativos (p-valor &lt; 0,05).

### Retweeting
{: #IBMretweet}

De forma semelhante, a {{site.data.keyword.IBM_notm}} também identificou que pessoas com características da personalidade específicas respondem em maior número a tarefas de difusão de informações. {{site.data.keyword.IBM_notm}}recentemente realizou outro estudo entre mais de 3500 usuários do Twitter para entender os fatores que aumentam a probabilidade de informações retweet. Os estudos ajudaram a {{site.data.keyword.IBM_notm}}desenvolver modelos para prever o comportamento de retweeting ([Lee e outros, 2014](/docs/services/personality-insights?topic=personality-insights-references#lee2014)).

Como recursos no modelo que foi usado no estudo, a {{site.data.keyword.IBM_notm}} incluiu atividade anterior em mídia social, informações de perfil de mídia social, prontidão, o dicionário LIWC e dimensões e aspectos do Big Five. O estudo descobriu que um conjunto de características do Big Five é significante na previsão da tendência para o retweet. Por exemplo, os resultados indicam que as pessoas com pontuação alta nas dimensões e aspectos de modéstia, abertura e simpatia são mais propensas a difundir informações. As descobertas foram estatisticamente significativas (p-valor &lt; 0,05).

### Publicidade direcionada
{: #IBMtarget}

A {{site.data.keyword.IBM_notm}} identificou que pessoas com características da personalidade específicas respondem mais favoravelmente à publicidade direcionada. Recentemente, a {{site.data.keyword.IBM_notm}} criou um serviço de informações de viagens baseado no Twitter para testar a hipótese de que determinados usuários do Twitter responderiam de forma mais favorável a propagandas não solicitadas do serviço. A hipótese previu que esses usuários seriam mais propensos a clicar em um link de uma propaganda ou seguir uma conta. {{site.data.keyword.IBM_notm}}conduziu dois estudos com base neste caso de uso e os efeitos hipotetizados de personalidade ([Chen e outros, 2015](/docs/services/personality-insights?topic=personality-insights-references#chen2015)).

Em um estudo de pesquisa, a {{site.data.keyword.IBM_notm}} pediu a 133 usuários do Twitter para relatar sua provável resposta a um tweet de propaganda de um serviço de informações de viagem. Em seguida, a {{site.data.keyword.IBM_notm}} usou questionários tradicionais para medir as personalidades dos usuários. Em um estudo de campo, a {{site.data.keyword.IBM_notm}} enviou tweets que anunciam o serviço para mais de 5.900 usuários do Twitter que estão viajando. A {{site.data.keyword.IBM_notm}} usou então o serviço do {{site.data.keyword.personalityinsightsshort}} para inferir características da personalidade dos usuários com base em seus tweets anteriores.

Os dois estudos renderam resultados consistentes: pessoas com pontuação alta na dimensão de abertura e baixa na dimensão de escala emocional (neuroticismo) realmente respondem de forma mais favorável à propaganda. Essas descobertas são verdadeiras apesar das abordagens diferentes que foram usadas pelos estudos para obter as características da personalidade dos usuários. Fazer o direcionamento o 10% de usuários com a maior abertura e a menor escala emocional aumentou a taxa de 6,8% para 11,3% e a taxa de acompanhamento de 4,7% para 8,8%. Os resultados foram estatisticamente significativos (p-valor &lt; 0,05).

### Campanhas de marketing
{: #IBMcampaign}

A {{site.data.keyword.IBM_notm}} recentemente trabalhou com um grande varejista para inferir características de milhares de seus clientes que estão envolvidos em campanhas de marketing. O varejista enviou cupons a seus clientes. Uma resposta positiva foi definida como resgate de qualquer cupom. De acordo com teoria da psicologia, pessoas que pontuam alto nos aspectos do Big Five de ordenação, autodisciplina e cautela e baixo no aspecto de sem moderação são mais propensas a resgatar cupons.

A {{site.data.keyword.IBM_notm}} validou a hipótese usando dados do cliente e inferiu características da personalidade. A {{site.data.keyword.IBM_notm}} primeiro segmentou a população do cliente em quartis com base em características da personalidade individuais. Usando pontuações em percentil normalizadas para as características (com uma escala de 1 a 100), a {{site.data.keyword.IBM_notm}} usou combinação linear para calcular uma pontuação combinada para cada cliente:

*Ordenação + Autodisciplina + Cautela + (100 - Sem moderação)*

A {{site.data.keyword.IBM_notm}} então comparou os resultados para os clientes no quartil mais alto com esses clientes no quartil mais baixo, ignorando a metade média da população. O estudo identificou que pessoas com as características hipotéticas são 40 por cento mais propensas a responder a cupons do que as pessoas da população aleatória.

### Preferência de marca
{: #IBMbrand}

A {{site.data.keyword.IBM_notm}} realizou um estudo de mais de 600 usuários do Twitter para saber se as características de personalidade do Big Five, Valores e Necessidades, podem prever preferências dos usuários para diferentes marcas. Por exemplo, essas características podem prever se os usuários gostam ou não de uma marca. O estudo avaliou 22 marcas de seis categorias: carros de luxo, bebidas, fast food, varejo, xampus e smartphones. A {{site.data.keyword.IBM_notm}} estabeleceu verdade absoluta para preferência de marca ao realizar uma pesquisa entre os usuários.

O estudo identificou que as características da personalidade podem prever preferência de marca com precisão de 65 por cento. Especificamente, as características a seguir estão entre aquelas que são mais propensas a prever a preferência de marca:

-   As dimensões e os aspectos Estado consciente, Conservação, Autoaprimoramento e Amabilidade do Big Five
-   As necessidades Amor e Ideal 
-   O valor Hedonismo 

### Satisfação de membro
{: #IBMmember}

A {{site.data.keyword.IBM_notm}} realizou um estudo entre os seus funcionários que são membros de comunidades de local de trabalho on-line. Os estudos investigaram se o idioma que os funcionários usam nas comunidades está relacionada ao seu nível de satisfação com as comunidades ([Matthews e outros, 2015](/docs/services/personality-insights?topic=personality-insights-references#matthews2015)). A {{site.data.keyword.IBM_notm}} mediu a satisfação da comunidade por meio de pesquisas de relatório automático. A {{site.data.keyword.IBM_notm}} examinou 142 comunidades do local de trabalho; dependendo do tamanho da comunidade, a {{site.data.keyword.IBM_notm}} pesquisou de 20 a 26 membros de cada comunidade.

O estudo identificou que o uso da linguagem nas comunidades, conforme medido pelo dicionário LIWC, está correlacionado à satisfação dos membros. Especificamente, o estudo identificou que as categorias do LIWC, como raiva, ansiedade, trabalho, lazer, inibição, aprovação e uso de pronome na primeira pessoa são bons preditores de satisfação dos membros. A {{site.data.keyword.IBM_notm}} espera que as características que são calculadas do texto em uma comunidade estejam bem correlacionadas com a satisfação dos membros da comunidade.

### Preferência de leitura
{: #IBMreading}

A {{site.data.keyword.IBM_notm}} realizou um estudo para entender o relacionamento entre Valores e interesses de leitura ([Hsieh e outros, 2014](/docs/services/personality-insights?topic=personality-insights-references#hsieh2014)). A hipótese da {{site.data.keyword.IBM_notm}} foi que

1.  Pessoas com um valor Autotranscendência mais alto demonstram um interesse em ler artigos sobre o meio ambiente.
1.  Pessoas com um valor Autoaprimoramento mais alto mostram um interesse em ler artigos sobre trabalho.
1.  Pessoas com um valor Hedonismo mais alto demonstram um interesse mais forte em conteúdo sobre lazer.

A {{site.data.keyword.IBM_notm}} recrutou mais de 200 participantes para o estudo do mercado de trabalho Amazon Mechanical Turk. Os participantes preencheram uma pesquisa sobre Valores e responderam perguntas sobre seu nível de interesse em ler diferentes artigos.

O estudo validou as duas primeiras hipóteses. Os participantes com uma pontuação mais elevada na auto-transcendência do Valor demonstraram um interesse em ler artigos sobre o ambiente. Os participantes com uma pontuação mais alta no valor Autoaprimoramento mostraram interesse em ler artigos sobre trabalho. Esses resultados foram estatisticamente significativos (p-valor &lt; 0,05).

No entanto, o estudo observou uma correlação fraca entre o Valor de hedonismo e um interesse em ler os artigos sobre lazer. Essa ligação fraca pode indicar que as pessoas não consideram a leitura uma atividade hedonista, não importando o tema do artigo.

### Prevendo preferências de consumo
{: #IBMpreferences}

A {{site.data.keyword.IBM_notm}} colaborou com a [Acxiom ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](http://www.acxiom.com/){: new_window} para investigar se os retratos de personalidade dos indivíduos podem melhorar a precisão preditiva de suas preferências de consumo em comparação com as predições baseadas exclusivamente em atributos demográficos. O estudo examinou 133 preferências de consumo de cerca de 785.000 indivíduos nos EUA. A inclusão de características de insights de personalidade na demografia melhorou a precisão preditiva para 115 preferências (86,5%). Para 23 das preferências, o uso de insights de personalidade sozinho fornece melhor precisão do que o uso apenas da demografia.

O estudo foi baseado em duas tecnologias: os resultados do serviço do {{site.data.keyword.IBM_notm}} {{site.data.keyword.personalityinsightsshort}} e do produto Acxiom InfoBase, especificamente os elementos de dados do InfoBase Customer Enhancement&trade;. A Acxiom é um provedor líder de mercado de dados demográficos para as necessidades de marketing dos clientes. Os dados demográficos da Acxiom incluem atributos como idade, gênero, renda, tamanho da família e faixa de renda. Os dados demográficos podem ser usados para analisar e aprimorar os dados do cliente. Eles podem ajudar a identificar oportunidades de vendas e de retenção, preencher lacunas nas informações de contato do cliente, ajudar na análise de informações do cliente e identificar perspectivas, entre outras coisas.

O estudo analisou 133 atributos de consumo comportamentais com base em 22 características do {{site.data.keyword.personalityinsightsshort}} e quatro categorias demográficas (gênero, educação, renda familiar e idade). Os resultados mostraram que 115 das 133 preferências de consumo mostraram melhor precisão de previsão quando os dados demográficos foram ampliados com características da personalidade. Além disso, a falta de melhoria nas 18 preferências restantes pode ser devido à natureza da comparação e como os dados foram calculados. Experimentos futuros tentarão comparações mais complexas para ver se uma abordagem diferente melhora ainda mais a precisão.

Os resultados gerais revelam que as características do {{site.data.keyword.personalityinsightsshort}} são úteis para prever diferentes preferências de consumo. Usar dados demográficos e características da personalidade juntos geralmente mostra como resultado melhor precisão de previsão. Mas o {{site.data.keyword.personalityinsightsshort}} sozinho é uma boa alternativa quando dados demográficos não estão disponíveis.

Para obter mais informações sobre o estudo, consulte <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Improving-Consumption-Preferences-Accuracy.pdf" download="Improving-Consumption-Preferences-Accuracy.pdf">Improving-Consumption-Preferences-Accuracy.pdf <img src="../../icons/launch-glyph.svg" alt="Ícone de link externo" title="Ícone de link externo"></a>. Para obter mais informações sobre o modelo de preferências de consumo que foi usado no estudo, consulte [Liu e outros (2016)](/docs/services/personality-insights?topic=personality-insights-references#liu2016).

## Estudos de outros pesquisadores
{: #appliedOthers}

Muitos estudos que foram conduzidos por pesquisadores fora da {{site.data.keyword.IBM_notm}} indicam que a personalidade está correlacionada a vários resultados e pode prevê-las. As seções a seguir descrevem esses estudos, que corroboram e aumentam a pesquisa que é descrita na seção prévia.

### Preferências do consumidor
{: #otherConsumer}

-   [Hirsh e outros (2012)](/docs/services/personality-insights?topic=personality-insights-references#hirsh2012) fizeram pesquisas com pessoas sobre várias mensagens de marketing. Eles descobriram que as pessoas respondem mais positivamente a mensagens customizadas para sua personalidade.
-   [Chen (2011)](/docs/services/personality-insights?topic=personality-insights-references#chen2011) identificou que no contexto de marketing on-line, as pessoas com a abertura alta são mais intelectualmente curiosas e abertas a novas ideias. Portanto, essas pessoas são mais propensas a experimentar coisas novas.
-   [Westfall (1962)](/docs/services/personality-insights?topic=personality-insights-references#westfall1962) identificou que existem diferenças de personalidade entre os proprietários de carros conversíveis e os proprietários de carros padrão ou compactos. Consumidores que pontuam alto na dimensão de afabilidade e no aspecto de ordenação da dimensão de estado consciente preferem carros tradicionais. Por outro lado, os consumidores que têm alta pontuação na dimensão de "abertura" podem fazer com que um carro conversível seja a sua primeira opção.
-   [Choo e Mokhtarian (2002)](/docs/services/personality-insights?topic=personality-insights-references#choo2002) examinaram o relacionamento entre escolha de tipo de veículo e fatores como personalidade, estilo de vida, atitude e dados demográficos. Eles descobriram que indivíduos que pontuam alto nos aspectos de aventura, busca por entusiasmo e desafiador de autoridade podem preferir carros de desempenho poderosos. No entanto, as pessoas que têm alta pontuação na dimensão de "afabilidade" podem não gostar de carros poderosos.
-   [Kassarjian (1971)](/docs/services/personality-insights?topic=personality-insights-references#kassarjian1971) identificou que proprietários de carros geralmente tendem a perceber os tipos de carros que compram como extensões de sua personalidade. [Consciência ambiental](#otherEnvironment) descreve como a personalidade de um indivíduo pode influenciar sua preferência por veículos com baixa emissão de gases.
-   [Myszkowski e Storme (2012)](/docs/services/personality-insights?topic=personality-insights-references#myszkowski2012) identificaram que abertura prevê significativamente a tendência dos indivíduos de preferir e responder a produtos bem projetados. O estudo sugere que indivíduos com *baixa* abertura tendem a reagir mais intensamente à aparência de um produto, amplificando as opções de produtos voltados ao design. Por outro lado, indivíduos com abertura *alta* tendem a focar mais em outros aspectos do produto, levando-os a desconsiderar as características estéticas.
-   [Lin (2002)](/docs/services/personality-insights?topic=personality-insights-references#lin2002) e [Sarli e Tat (2011)](/docs/services/personality-insights?topic=personality-insights-references#sarli2011) relataram que as características da personalidade afetam as preferências de marca do indivíduo.

### Preferências pessoais
{: #otherPersonal}

-   [Hu e Pu (2011)](/docs/services/personality-insights?topic=personality-insights-references#hu2011) descobriram que no domínio da música, as recomendações são mais bem-sucedidas quando elas utilizam as correlações entre a personalidade das pessoas e suas preferências de música.
-   [Chamorro-Premuzic e Furnham (2007)](/docs/services/personality-insights?topic=personality-insights-references#chamorro2007) também relataram que diferenças individuais em personalidade e capacidade cognitiva podem determinar como as pessoas experimentam música. [Rentfrow e Gosling (2003)](/docs/services/personality-insights?topic=personality-insights-references#rentfrow2003) relataram resultados semelhantes em um estudo anterior.
-   [Golbeck e Norris (2013)](/docs/services/personality-insights?topic=personality-insights-references#golbeck2013) encontraram correlações entre personalidade e preferências de filmes entre usuários da Netflix&trade;.

### Hábitos de gastos
{: #otherSpending}

-   [Pirog e Roberts (2007)](/docs/services/personality-insights?topic=personality-insights-references#pirog2007) revelaram o relacionamento entre hábitos de gastos e personalidade. Eles focaram no "uso indevido" (ou "abuso") de cartões de crédito entre estudantes de faculdade. Eles identificaram que os estudantes que pontuam alto em estado consciente tendem a usar cartões de débito ou dinheiro e tendem a não abusar de cartões de crédito. Por outro lado, neuroticismo alto (escala emocional) deve ser associado ao uso excessivo de cartões de crédito.

### Perfis de risco
{: #otherRisk}

-   [Lauriola e Levin (2001)](/docs/services/personality-insights?topic=personality-insights-references#lauriola2001) mostraram que a personalidade influencia a tomada de decisão arriscada de indivíduos em investimentos financeiros. Eles concluíram que as pessoas que pontuam alto em abertura para experiências tendem a fazer investimentos arriscados. Enquanto isso, neuroticismo (escala emocional) pode fazer as pessoas menos dispostas a assumir tais riscos.
-   [Nicholson e outros (2001)](/docs/services/personality-insights?topic=personality-insights-references#nicholson2001) desenvolveram ainda mais a correlação entre as características do Big Five e os perfis de risco. As suas descobertas revelam que a afabilidade e o estado consciente diminuem a disposição das pessoas de assumir riscos em geral. Em contraste, indivíduos que pontuam alto em extroversão são mais propensos a tomar decisões arriscadas.
-   [Tok (2011)](/docs/services/personality-insights?topic=personality-insights-references#tok2011) identificou o relacionamento entre as características da personalidade do Big Five e participação em esportes de aventura arriscados, como esqui, mountain bike, voo, voo livre, parapente e mergulho. Quatro das cinco características do Big Five influenciam diretamente a participação em esportes de risco: notas altas em extraversão, abertura e neuroticismo (escala emocional) aumentam a probabilidade de participação em tais esportes; uma pontuação elevada na consciência reduz a disposição de participar.
-   [Hymbaugh e Garrett (1974)](/docs/services/personality-insights?topic=personality-insights-references#hymbaugh1974) estudaram características da personalidade dos paraquedistas. Eles descobriram que paraquedistas geralmente têm busca por entusiasmo e aventura mais altos do que a população em geral.

### Desempenho profissional
{: #otherProfessional}

-   [Barrick e Mount (1991)](/docs/services/personality-insights?topic=personality-insights-references#barrick1991) exploraram a relação entre dimensões de personalidade do Big Five e desempenho no emprego. Eles descobriram que as dimensões de personalidade, como o estado consciente, estão relacionadas ao desempenho no emprego para todos os grupos de tarefas que eles estudaram (profissionais liberais, gerentes, vendas, polícia, qualificados e semiqualificados).
-   [Hurtz e Donovan (2000)](/docs/services/personality-insights?topic=personality-insights-references#hurtz2000) relataram que estado consciente é a característica da personalidade que é mais preditiva de desempenho no emprego.
-   [Lim e Ployhart (2004)](/docs/services/personality-insights?topic=personality-insights-references#lim2004) descobriram que extroversão está positivamente correlacionada às habilidades de liderança.
-   [Judge e outros (2002)](/docs/services/personality-insights?topic=personality-insights-references#judge2002) relataram que os indivíduos extrovertidos são mais satisfeitos no local de trabalho; o trabalho dá a eles uma oportunidade de experimentar um nível ideal de excitação. Por outro lado, indivíduos introvertidos estão menos satisfeitos no local de trabalho devido a estímulo demasiado.
-   [van Vianen e outros (2012)](/docs/services/personality-insights?topic=personality-insights-references#vanvianen2012) relataram diferenças individuais na adaptabilidade e suas causas, correlações e consequências. Eles descobriram que estado consciente, extroversão e abertura estão correlacionados de forma positiva com adaptabilidade da carreira.

### Desempenho acadêmico
{: #otherAcademic}

-   [Chamorro-Premuzic e Furnham (2003)](/docs/services/personality-insights?topic=personality-insights-references#chamorro2003) relataram um estudo longitudinal no qual descobriram que características da personalidade impactam o desempenho acadêmico. Especificamente, identificaram que neuroticismo (escala emocional) pode prejudicar o desempenho acadêmico e que estado consciente pode levar a maior sucesso acadêmico.
-   [Komarraju e Karau (2005)](/docs/services/personality-insights?topic=personality-insights-references#komarraju2005) descobriram que algumas características de personalidade afetam o comportamento de um indivíduo em relação ao aprendizado de autoaperfeiçoamento. O estudo revela que abertura e estado consciente altos frequentemente levam a um maior interesse no aprendizado de autoaprimoramento e que neuroticismo alto (escala emocional) diminui a motivação desse tipo de aprendizado.

### Relações profissionais
{: #otherProRelations}

-   [Flynn e Smith (2007)](/docs/services/personality-insights?topic=personality-insights-references#flynn2007) descobriram que a personalidade influencia as preferências de interação entre profissionais e clientes. Por exemplo, pacientes com um alto grau de estado consciente e abertura preferem estar ativamente envolvidos na decisão do curso de tratamento. Pacientes com altos níveis de afabilidade ou escala emocional (neuroticismo) preferem que os médicos tomem a liderança na tomada de importantes decisões sobre a saúde.
-   [Duberstein e outros (2007)](/docs/services/personality-insights?topic=personality-insights-references#duberstein2007) de forma semelhante relataram que as personalidades dos médicos afetaram o nível de satisfação de seus pacientes. Por exemplo, os pacientes relataram estar mais satisfeitos com médicos que pontuam relativamente alto em abertura e médio em estado consciente.

### Relações pessoais
{: #otherPerRelations}

-   [Botwin e outros (1997)](/docs/services/personality-insights?topic=personality-insights-references#botwin1997) descobriram que a personalidade afeta os relacionamentos românticos. As características de personalidade do parceiro de alguém preveem de forma significativa a insatisfação marital, mais notavelmente quando o parceiro tem pontuações mais baixas em afabilidade, escala emocional e abertura do que o desejado.

### Funcionamento
{: #otherHealth}

-   [Turiano e outros (2012)](/docs/services/personality-insights?topic=personality-insights-references#turiano2012) relataram um estudo longitudinal sobre um período de tempo de 10 anos em que eles descobriram que as características do Big Five previam resultados relacionados à saúde. Por exemplo, todas as características, exceto abertura, previam a saúde física autoclassificada e todas as características, exceto afabilidade, previam o número de dias de trabalho limitado devido à saúde física.
-   [Masui e outros (2006)](/docs/services/personality-insights?topic=personality-insights-references#masui2006) descobriram que pontuações altas nas características de personalidade específicas de estado consciente, extroversão e abertura estão associadas à longevidade. Outros pesquisadores também descobriram um relacionamento entre as características de personalidade do Big Five e a expectativa de vida.
-   [Roberts e outros (2007)](/docs/services/personality-insights?topic=personality-insights-references#roberts2007) relataram que características de personalidade específicas preveem resultados de vida importantes, como a mortalidade, o divórcio e o sucesso no trabalho.

### Dieta e exercício
{: #otherDiet}

-   [Shepherd e Sparks (1994)](/docs/services/personality-insights?topic=personality-insights-references#shepherd1994) desenvolveram a relação entre personalidade e opção de alimentos. O estudo revela que as pessoas com pontuações altas na escala emocional (neuroticismo), principalmente no aspecto de falta de moderação, tendem a consumir alimentos com alto nível de gordura.
-   [Elfhag e Morey (2008)](/docs/services/personality-insights?topic=personality-insights-references#elfhag2008) revelaram que estado consciente está positivamente relacionado a uma preferência por alimentos de baixo nível de gordura. Especificamente, os aspectos de autodisciplina e obediência da dimensão de estado consciente influenciam positivamente o consumo de alimentos de baixo nível de gordura e (como o gerenciamento de peso está intimamente relacionado às opções de alimentos) o controle de peso regular.
-   [Heaven e outros (2001)](/docs/services/personality-insights?topic=personality-insights-references#heaven2001) relataram que o consumo de comida saudável está relacionado a duas dimensões do Big Five. As pessoas com neuroticismo (escala emocional) alto geralmente são menos propensas a escolher alimentos saudáveis, enquanto as pessoas com estado consciente alto preferem alimentos saudáveis. O papel também cita vários aspectos que se relacionam sutilmente com a escolha de alimentos. Os interesses artísticos (da dimensão da abertura) e a autodisciplina (desde a dimensão da consciência) correlacionam-se positivamente com o aumento do consumo de alimentos para a saúde. Por outro lado, a suscetibilidade ao estresse tem uma correlação ligeiramente negativa com o consumo de comida saudável.
-   [Lusk (2012)](/docs/services/personality-insights?topic=personality-insights-references#lusk2012) descobriu que amantes de comida pontuam alto em abertura para experiência. Abertura pode motivar as pessoas a experimentar diferentes alimentos e ajudá-los a se tornarem especialistas em comida.
-   [Courneya e Hellsten (1998)](/docs/services/personality-insights?topic=personality-insights-references#courneya1998) descobriram que a personalidade influencia a tendência de um indivíduo a perseguir hábitos que estão associados a um estilo de vida saudável, incluindo exercício físico. Extroversão e estado consciente estão correlacionados positivamente com exercícios físicos mais frequentes, enquanto neuroticismo (escala emocional) pode influenciar negativamente a frequência de exercícios.

### Jantar fora
{: #otherDining}

-   [Kim e outros (2010)](/docs/services/personality-insights?topic=personality-insights-references#kim2010) provaram que a abertura para a experiência se correlaciona positivamente com o jantar fora mais frequente. As pessoas que pontuam baixo em abertura geralmente jantam fora com menos frequência.
-   [Van Trijp e Steenkamp (1992)](/docs/services/personality-insights?topic=personality-insights-references#vantrijp1992) descobriram que o jantar fora está correlacionado ao aspecto de busca por entusiasmo (busca por sensações) da dimensão de extroversão.

### Consciência ambiental
{: #otherEnvironment}

-   [Griskevicius e outros (2010)](/docs/services/personality-insights?topic=personality-insights-references#griskevicius2010) descobriram que a personalidade de uma pessoa influencia o seu interesse em preocupações ambientais. Eles estudaram o relacionamento entre personalidade e comportamento pró-ambiental, como o uso de veículos de baixa emissão e a busca de vida verde, jardinagem e reciclagem. Para a maioria das pessoas, níveis mais altos de afabilidade, abertura e estado consciente estão associados a uma inclinação maior para o comportamento pró-ambiental.
-   [Fraj e Martinez (2006)](/docs/services/personality-insights?topic=personality-insights-references#fraj2006) descobriram que personalidade influencia a decisão de comprar produtos ambientalmente conscientes. As pessoas que são caracterizadas por recursos de personalidade como a extroversão, a afabilidade e estado consciente são mais propensas a comprar esses produtos.

### Serviço comunitário
{: #otherCommunity}

-   [Penner e outros (2005)](/docs/services/personality-insights?topic=personality-insights-references#penner2005) relataram que a personalidade de um indivíduo afeta o seu engajamento no serviço da comunidade. Em um estudo de revisão, os autores resumiram vários fatores de personalidade que influenciam o comportamento pró-social. Eles identificaram que extroversão e afabilidade têm influências positivas no engajamento em serviço comunitário. Em particular, o altruísmo e os aspectos de cooperação da dimensão de afabilidade podem ter o maior impacto. A faceta de gregariosidade da dimensão extraversão tem uma correlação positiva mais sutil para o serviço comunitário.

### Religião e espiritualidade
{: #otherReligion}

-   [Adorno e outros (1950)](/docs/services/personality-insights?topic=personality-insights-references#adorno1950), em seu livro clássico *A personalidade autoritária*, relataque uma possível correlação entre as características de personalidade e a religião. Eles sugerem que as pessoas que pontuam alto em acordo são mais religiosas, enquanto as pessoas que pontuam alto na autoridade-desafiando são menos motivadas a participar de práticas religiosas e espirituais.
