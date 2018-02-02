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

# O serviço em ação
{: #applied}

{{site.data.keyword.IBM_notm}} e outros pesquisadores têm validado muitas hipóteses que estão relacionados aos aplicativos do mundo real das características da personalidade. Estes estudos ajudaram a levar o desenvolvimento do {{site.data.keyword.personalityinsightsshort}} serviço. Suas descobertas fornecem informações sobre algumas das várias maneiras pelas quais é possível aplicar o serviço aos seus objetivos de negócios e de comunicação. Para obter mais informações sobre a pesquisa que suporta o {{site.data.keyword.personalityinsightsshort}} serviço, consulte [A ciência por trás do serviço](/docs/services/personality-insights/science.html).
{: shortdesc}

## Estudos por pesquisadores da IBM
{: #appliedIBM}

Os seguintes estudos conduzidos pelo {{site.data.keyword.IBM_notm}} os pesquisadores indicam que aplicar os resultados do serviço pode produzir resultados tangíveis em vários domínios. Os estudos contribuiu diretamente para o desenvolvimento do serviço. A tabela inclui links para seções com mais informações sobre cada estudo.

<table>
  <caption>Tabela 3. Estudos pela IBM</caption>
  <tr>
    <th style="text-align:left; width:25%">Estudo</th>
    <th style="text-align:center; width:25%">Assuntos</th>
    <th style="text-align:left; width:50%">Efeito de características de personalidade</th>
  </tr>
  <tr>
    <td>
      <a href="#IBMrespond"><strong>Respondendo a tweets</strong></a>
      <br/>(Coleta de informações)
    </td>
    <td style="text-align:center">2000 usuários do Twitter</td>
    <td>
      <strong>Mais probabilidade de responder:</strong> Pontuação alta em dimensões e aspectos Big Five entusiasmo e buscando amizade, nível de atividade, sociabilidade, confiança, moralidade, extroversão, e agradam<br/><br/>
      <strong>Menos deve responder:</strong> Pontuação alta no Big Five aspectos cautela e ansiedade
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMretweet"><strong>Re-tweeting</strong></a>
      <br/>(difundir informações)
    </td>
    <td style="text-align:center">3500 usuários do Twitter</td>
    <td>
      <strong>Mais provável retuitarei:</strong> Pontuação alta em dimensões e aspectos Big Five modéstia, abertura, e amizade
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMtarget"><strong>Publicidade</strong></a>
      <br/>(publicidade não solicitada)
    </td>
    <td style="text-align:center">Mais de 6000 usuários do Twitter
    </td>
    <td>
      <strong>Responder mais favorável:</strong> Pontuação alta na abertura dimensão Big Five, e baixa pontuação no intervalo emocional dimensão Big Five
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMcampaign"><strong>Campanhas de marketing</strong></a>
      <br/>(resgate do cupom)
    </td>
    <td style="text-align:center">Milhares de clientes de varejo</td>
    <td>
      <strong>Mais probabilidade de responder:</strong> Pontuação alta na ordem aspectos Big Five, auto-disciplina, e a prudência, e baixa pontuação em uma imoderação aspecto Big Five
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMbrand"><strong>Marca preferências</strong></a>
      <br/>(afinidade de marca)
    </td>
    <td style="text-align:center">600 usuários do Twitter</td>
    <td>
      <strong>Preditores de preferência marca:</strong> Big Five dimensões e aspectos inteligênica, conservação, auto-aprimoramento, e agradam; precisa de amor e ideal; e o hedonismo Valor
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMmember"><strong>Membro satisfação</strong></a>
      <br/>(Preenchimento da comunidade)
    </td>
    <td style="text-align:center">Mais de 3.000 membros da comunidade</td>
    <td>
      <strong>Preditores de satisfação membro:</strong> Características como raiva, ansiedade, trabalho, lazer, inibição, favorável, e o uso do pronome pessoal
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMreading"><strong>Lendo preferências</strong></a>
      <br/>(de conteúdo)
    </td>
    <td style="text-align:center">Mais de 200 participantes</td>
    <td>
      <strong>Interesse em artigos ambientais:</strong> Pontuação alta na Valor auto-transcendência<br/><br/>
      <strong>Interesse em artigos de trabalho:</strong> Pontuação alta de auto aperfeiçoamento Valor
    </td>
  </tr>
  <tr>
    <td>
      <a href="#IBMpreferences"><strong>Prever o consumo de preferências</strong></a><br/>(de compra do consumidor)
    </td>
    <td style="text-align:center">Centenas de milhares de registros de dados</td>
    <td>
      <strong>Prever preferências do consumidor:</strong> dados demográficos e características de personalidade
    </td>
  </tr>
</table>

### Respondendo a tweets
{: #IBMrespond}

{{site.data.keyword.IBM_notm}} descobriu que pessoas com características da personalidade específica responder mais rapidamente a coleção de informações de tarefas. A {{site.data.keyword.IBM_notm}} realizou recentemente um estudo com mais de 2.000 usuários do Twitter para entender os fatores que influenciam a probabilidade de responder a tais tarefas e de desenvolver modelos para prever respostas a perguntas ([Mahmud et al., 2013](/docs/services/personality-insights/references.html#mahmud2013) e [Mahmud et al., 2014](/docs/services/personality-insights/references.html#mahmud2014)).

{{site.data.keyword.IBM_notm}} para o modelo que foi usado no estudo de dois conjuntos de dados de perguntas e respostas em que os usuários do Twitter foram feitas ou perguntas relacionadas ao local. As perguntas depende se os usuários relataram estar presente em um local ou ter um produto. Como os recursos no modelo de previsão, {{site.data.keyword.IBM_notm}} incluído comportamento social (por exemplo, taxa de resposta passado e atividade no Twitter), disponibilidade (por exemplo, quanto tempo o usuário está inativo), recursos de categoria da consulta lingüística e Contagem de Palavras (LIWC) o mistério dicionário, e dimensões e aspectos Big Five.

{{site.data.keyword.IBM_notm}} encontrou um conjunto de características da personalidade Big Five que são significativos no prever a probabilidade de responder. Especificamente, o {{site.data.keyword.IBM_notm}} descobriu que quem recorde nas dimensões e aspectos entusiasmo e buscando amizade, nível de atividade, sociabilidade, confiança, moralidade, extroversão, e agradam são mais propensos a responder a tweets. Como alternativa, quem recorde nos aspectos cautela e ansiedade são menos propensos a responder. Estes resultados foram considerados estatisticamente significativo (p-valor &lt; 0,05).

### Re-tweeting
{: #IBMretweet}

Da mesma forma, {{site.data.keyword.IBM_notm}} também descobriu que pessoas com características da personalidade específica responder em maior número para espalhar informações tarefas. {{site.data.keyword.IBM_notm}} recentemente realizou outro estudo entre mais de 3500 usuários do Twitter para entender os fatores que aumentam a probabilidade de retuitarei informações e desenvolver modelos para prever o comportamento retuites ([Lee et al., 2014](/docs/services/personality-insights/references.html#lee2014)).

Como os recursos no modelo que foi usado no estudo, {{site.data.keyword.IBM_notm}} incluído passado a atividade de mídia social, informações de perfil de mídia social, prontidão, o dicionário LIWC, e dimensões e aspectos Big Five. O estudo descobriu que um conjunto de características do Big Five é significativo para prever a tendência de retweetar. Por exemplo, os resultados indicam que as pessoas que pontuação alta nas dimensões e aspectos modéstia, abertura e amizade são mais prováveis de espalhar informações. As descobertas foram estatisticamente significativo (p-valor &lt; 0,05).

### Publicidade de Destino
{: #IBMtarget}

{{site.data.keyword.IBM_notm}} descobriu que pessoas com características da personalidade específica respondem mais favoravelmente a publicidade direcionada. Recentemente, {{site.data.keyword.IBM_notm}} criou um serviço de informações de viagens Twitter baseados em testar a hipótese de que os usuários do Twitter determinados responderia mais favorável para propagandas não solicitadas do serviço. A hipótese que tais usuários seriam mais propensas a clicar em um link para um anúncio ou seguir uma conta. {{site.data.keyword.IBM_notm}} dois estudos realizados com base nesse caso de uso e os efeitos hipotetizados de personalidade ([Chen et al., 2015](/docs/services/personality-insights/references.html#chen2015)).

Em um estudo de pesquisa, {{site.data.keyword.IBM_notm}} pediu 133 usuários do Twitter para relatar seus provável resposta a uma mensagem que informa um serviço de informações de viagem. A {{site.data.keyword.IBM_notm}}, então, usou questionários tradicionais para medir as personalidades dos usuários. Em um estudo campo, {{site.data.keyword.IBM_notm}} enviou tweets de publicidade o serviço para mais de 5900 viajando usuários do Twitter. {{site.data.keyword.IBM_notm}} então usado o {{site.data.keyword.personalityinsightsshort}} serviço para indicar características da personalidade dos usuários de seus últimos tuítes.

Os dois estudos rendeu resultados consistentes: Pessoas que pontuação alta na abertura dimensão e baixo no intervalo emocional dimensão (neuroticism) certamente responder mais favorável ao anúncio. Essas provas são verdadeiras apesar das abordagens diferentes que eram utilizadas pelos estudos para obter as características da personalidade dos usuários. A segmentação dos principais 10 por cento dos usuários com alta abertura e baixo intervalo emocional aumentou a taxa de cliques de 6,8 para 11,3 por cento e a taxa de acompanhamento de 4,7 para 8,8 por cento Os resultados foram estatisticamente significativo (p-valor &lt; 0,05).

### Campanhas de Marketing
{: #IBMcampaign}

{{site.data.keyword.IBM_notm}} recentemente trabalhou com um grande varejista para indicar características por milhares de seus clientes que estão envolvidos em campanhas de marketing. O varejista enviou cupons para seus clientes. Uma resposta positiva foi definido como redenção qualquer cupom. De acordo com a teoria psicologia, quem recorde na ordem aspectos Big Five, auto-disciplina, e prudência e baixa no aspecto de um excesso são mais propensos a resgatar cupons.

{{site.data.keyword.IBM_notm}} validado a hipótese usando dados do cliente e as características da personalidade inferida. {{site.data.keyword.IBM_notm}} primeiro segmentado a população cliente em quartis com base em características de personalidade individual. Usando as pontuações normalizadas para as características de percentil (com uma escala de 1 100), {{site.data.keyword.IBM_notm}} usado combinação linear para calcular uma pontuação total para cada cliente:

*Orderliness + Auto-Disciplina + prudência + (100-Immoderation)*

{{site.data.keyword.IBM_notm}} então comparado resultados para os clientes na maior quartil com aqueles no quartil inferior, ignorando o meio meio da população. O estudo descobriu que pessoas com as características hipotetizadas são 40 mais propensos a responder os cupons que são pessoas da população aleatória.

### Marca de preferência
{: #IBMbrand}

{{site.data.keyword.IBM_notm}} realizou um estudo sobre mais de 600 usuários do Twitter para entender se Big Five, Valores e Necessidades características de personalidade pode prever as preferências dos usuários para diferentes marcas (se eles gostam ou não de uma marca). O estudo avaliou 22 marcas de seis categorias: carros de luxo, bebidas, fast food, varejo, xampus, e smartphones. {{site.data.keyword.IBM_notm}} estabelecido verdade solo de preferência da marca ao realizar uma pesquisa entre os usuários.

O estudo descobriu que as características de personalidade pode prever preferência marca com precisão de 65. Especificamente, o estudo descobriu que o Big Five dimensões e aspectos inteligênica, conservação, auto-aprimoramento, e agradam, o amor Necessária e ideal, e o hedonismo Valor estão entre as características mais prováveis para prever preferências marca.

### Membro satisfação
{: #IBMmember}

{{site.data.keyword.IBM_notm}} realizou um estudo entre seus funcionários que são membros de comunidades de trabalho online para investigar se o idioma que eles usam nas comunidades está relacionado ao seu nível de satisfação com as comunidades ([Matthews et al., 2015](/docs/services/personality-insights/references.html#matthews2015)). {{site.data.keyword.IBM_notm}} medido comunidade satisfação por pesquisas relatados. A {{site.data.keyword.IBM_notm}} examinou 142 comunidades de local de trabalho; dependendo do tamanho da comunidade, a {{site.data.keyword.IBM_notm}} pesquisou de 20 a 26 membros de cada comunidade.

O estudo descobriu que usam o idioma em comunidades, conforme medido pelo dicionário LIWC, se correlaciona com satisfação membro. Especificamente, o estudo descobriu que as categorias LIWC, como raiva, ansiedade, trabalho, lazer, inibição, aprovação e pessoa pronome são preditores boa satisfação do membro. {{site.data.keyword.IBM_notm}} espera características que são computados do texto em uma comunidade para correlacionar bem com satisfação membro para a comunidade.

### Lendo preferência
{: #IBMreading}

{{site.data.keyword.IBM_notm}} realizou um estudo para entender o relacionamento entre valores e interesses de leitura ([Hsieh et al., 2014](/docs/services/personality-insights/references.html#hsieh2014)). {{site.data.keyword.IBM_notm}} hipotetizada que

1.  Pessoas com um maior auto-transcendência valor irá demonstrar um interesse em ler artigos sobre o ambiente.
1.  Pessoas com maior valor de autoaprimoramento mostrarão interesse em ler artigos sobre o trabalho.
1.  Pessoas com um valor maior terá hedonismo evidenciam um forte interesse em conteúdo sobre lazer.

{{site.data.keyword.IBM_notm}} recrutou mais de 200 participantes para o estudo do mercado Amazon Mechanical Turk. Os participantes concluiu uma pesquisa Valores e respondeu perguntas sobre seu nível de interesse em ler artigos diferentes.

O estudo validado os dois primeiros hipóteses: Participantes com uma pontuação maior no Valor auto-transcendência demonstrou interesse em ler artigos sobre o ambiente, e os participantes com uma pontuação maior no Valor auto-aprimoramento mostrou um interesse em ler artigos sobre o trabalho. Esses resultados foram estatisticamente significativo (p-valor &lt; 0,05).

No entanto, o estudo observou uma correlação fraca entre o hedonismo Valor e um interesse em ler os artigos de lazer. Essa ligação fraca pode indicar que as pessoas não consideram ler uma atividade hedonista, não importando o tema do artigo.

### Previsão de preferências de consumo
{: #IBMpreferences}

{{site.data.keyword.IBM_notm}} colaborou com [TAP ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://www.acxiom.com/){: new_window} para investigar se o retrato da personalidade de um indivíduo pode melhorar a precisão de previsão de preferências de consumo dos indivíduos comparado com previsões com base apenas em atributos demográficos. O estudo examinou 133 preferências de consumo por cerca de 785.000 pessoas nos EUA. Incluindo personalidade insights características para dados demográficos melhorou a precisão prevista para 115 preferências (86,5), e por 23 das preferências, usando insights de personalidade só fornece melhor precisão do que usar dados demográficos apenas.

O estudo foi baseado em duas tecnologias: Os resultados da {{site.data.keyword.IBM_notm}} {{site.data.keyword.personalityinsightsshort}} serviço e o produto Acxiom InfoBase, especificamente InfoBase &trade; Aprimoramento de dados do cliente elementos. TAP é um provedor líder de dados demográficos para as necessidades de marketing dos clientes. Dados demográficos de juristas, como idade, sexo, renda, residência tamanho, faixa de renda, e assim por diante, podem ajudar a analisar e melhorar os dados do cliente para identificar oportunidades de vendas e retenção, preencha as lacunas em informações de contato do cliente, auxiliar na análise de informações do cliente, e identificar as perspectivas, entre outras coisas.

O estudo analisou 133 atributos comportamentais de consumo baseado em 22 {{site.data.keyword.personalityinsightsshort}} características e quatro categorias dados demográficos (de gênero, educação, renda familiar e idade). Os resultados mostram que 115 dos 133 preferências de consumo mostrou precisão melhor preditiva quando dados demográficos foram aumentados com características de personalidade. Além disso, a falta de melhoria em 18 preferências restantes pode ser devido à natureza da comparação e como os dados foram calculados. Experiências futuras tentará comparações mais complexas para ver se uma abordagem diferente mais melhora a precisão.

Os resultados gerais revelam que {{site.data.keyword.personalityinsightsshort}} características são úteis para prever preferências de consumo diferentes. Usando a demografia e as características da personalidade juntos geralmente produz precisão melhor preditiva. O {{site.data.keyword.personalityinsightsshort}} sozinho é uma boa alternativa quando dados pessoais não estão disponíveis.

Para obter mais informações sobre o estudo, consulte <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Improving-Consumption-Preferences-Accuracy.pdf" download="Improving-Consumption-Preferences-Accuracy.pdf">Melhorando-Consumo-Preferências-Accuracy.pdf <img src="../../icons/launch-glyph.svg" alt="External link icon" title="External link icon" class="style-scope doc-content"></a>. Para obter mais informações sobre o modelo de preferências de consumo usado no estudo, consulte[Liu et al. (2016)](/docs/services/personality-insights/references.html#liu2016).

## Estudos por outros pesquisadores
{: #appliedOthers}

Muitos estudos conduzidos por pesquisadores fora do {{site.data.keyword.IBM_notm}} indicam que correlaciona personalidade com e pode prever resultados diferentes. As seções a seguir descrevem esses estudos, que corrobora e aumentar a pesquisa descrita na seção anterior.

### Preferências do consumidor
{: #otherConsumer}

-   [Hirsh et al. (2012)](/docs/services/personality-insights/references.html#hirsh2012) entrevistou pessoas sobre mensagens de marketing diferentes. Eles descobriram que as pessoas respondem mais positiva para as mensagens customizadas para sua personalidade.
-   [Chen (2011)](/docs/services/personality-insights/references.html#chen2011) localizado que no contexto de marketing online, as pessoas com a abertura de alta são mais intelectualmente curioso e aberto a novas ideias. Tais pessoas são, portanto, mais propensas a experimentar coisas novas.
-   [Westfll (1962)](/docs/services/personality-insights/references.html#westfall1962) descobriu que as diferenças de personalidade existir entre os proprietários de carros conversíveis e os proprietários de padrão ou carros compactos. Consumidores que recorde na dimensão agradam e no aspecto a ordem da dimensão consciência prefere os carros tradicionais. Consumidores que recorde na dimensão abertura, por outro, pode fazer um carro conversível sua primeira escolha.
-   [Choo e Mokhtarian (2002)](/docs/services/personality-insights/references.html#choo2002) examinou o relacionamento entre escolha de veículo e fatores como personalidade, estilo de vida, uma atitude, e a demografia. Eles descobriram que indivíduos que recorde na ousadia aspectos, excitação, buscando, e desafiando a autoridade pode preferir carros desempenho poderosos. Quem recorde na dimensão agradam, no entanto, não gostaria carros poderosos.
-   [Kassarjian (1971)](/docs/services/personality-insights/references.html#kassarjian1971) descobriu que os proprietários de carros geralmente tendem a perceber os tipos de carros que eles compra como extensões de sua personalidade. [consciência ambiental](#otherEnvironment) descreve como a personalidade de um indivíduo podem influenciar sua preferência para veículos de emissões.
-   [Myszkowski e Storme (2012)](/docs/services/personality-insights/references.html#myszkowski2012) descobriram que a abertura prevê significativamente a tendência dos indivíduos de preferir e responder a produtos bem projetados. O estudo sugere que indivíduos com *baixo* abertura tendem a reagir mais intensamente para a aparência de um produto, ampliando as opções de produto design-driven. Por outro lado, indivíduos com abertura *high* tendem a focar mais em outros aspectos do produto, levando eles para desconsiderar as características estéticas.
-   [Lin (2002)](/docs/services/personality-insights/references.html#lin2002) e [Sarli e Tat (2011)](/docs/services/personality-insights/references.html#sarli2011) relatou que as características de personalidade afetam as preferências marca ninguém.

### Preferências pessoais
{: #otherPersonal}

-   [Hu e Pu (2011)](/docs/services/personality-insights/references.html#hu2011) descobriu que no domínio da música, as recomendações são mais bem-sucedidas quando eles alavancar as correlações entre a personalidade das pessoas e sua música preferências.
-   [Chamorro-Premuzic e Furnham (2007)](/docs/services/personality-insights/references.html#chamorro2007) também relatou que diferenças individuais em personalidade e capacidade cognitiva pode determinar como as pessoas experimentar música. [Rentfrow e Gosling (2003)](/docs/services/personality-insights/references.html#rentfrow2003) relatou resultados semelhantes em um estudo anterior.
-   [Golbeck e Norris (2013)](/docs/services/personality-insights/references.html#golbeck2013) encontrou correlações entre as preferências personalidade e cinema entre Netflix &trade; usuários.

### Hábitos de gastos
{: #otherSpending}

-   [Pirog e Roberts (2007)](/docs/services/personality-insights/references.html#pirog2007) revelou o relacionamento entre os hábitos de gastos e personalidade. Eles focado no "uso" (ou "abuso") de cartões de crédito entre estudantes. Eles descobriram que os estudantes que se recorde em consciência tendem a usar cartões de débito ou dinheiro e tendem não cartões de crédito abuso. Por outro lado, neuroticism alto (intervalo emocional) deve ser associado com uso excessivo de cartões de crédito.

### Perfis de Risco
{: #otherRisk}

-   [Lauriola e Levin (2001)](/docs/services/personality-insights/references.html#lauriola2001) mostraram que personalidade influencia indivíduos ' risco de decisão em investimentos financeiros. Eles concluíram que as pessoas que pontuação alta na abertura a experiências tendem a fazer investimentos arriscados. Enquanto isso, neuroticism (intervalo emocional) pode fazer as pessoas menos dispostos a assumir riscos como.
-   [Nicholson et al. (2001)](/docs/services/personality-insights/references.html#nicholson2001) mais desenvolveu a correlação entre as características Big Five e perfis de risco. Suas descobertas revelam que a sensibilidade e o estado consciente diminuem a vontade das pessoas de assumir riscos em geral. Em contraste, indivíduos que recorde em extroversão são mais propensos a tomar decisões arriscadas.
-   [Tok (2011)](/docs/services/personality-insights/references.html#tok2011) identificou o relacionamento entre as características da personalidade Big Five e participação em esportes de aventura arriscada, como esqui, ciclismo mountain, voando, deslizando, parapente, e mergulho. Quatro das características do Big Five influenciam diretamente a participação em esportes de risco: as altas pontuações em extroversão, abertura e neuroticismo (faixa emocional) aumentam a probabilidade de participação nesses esportes; uma alta pontuação em estado consciente reduz a vontade de participar.
-   [Hymbaugh e Garrett (1974)](/docs/services/personality-insights/references.html#hymbaugh1974) estudou as características da personalidade dos paraquedistas. Eles descobriram que paraquedistas geralmente têm maior emoção e aventura em busca do que a população em geral.

### Profissional de desempenho
{: #otherProfessional}

-  [Representantes e Montagem (1991)](/docs/services/personality-insights/references.html#barrick1991) explorou a relação entre as dimensões da personalidade Big Five para desempenho da tarefa. Eles descobriram que as dimensões da personalidade, como consciência estão relacionados ao desempenho da tarefa para todos os grupos de trabalho que eles estudaram (profissionais, gerentes, vendas, polícia, qualificados e semi-qualificados).
-   [Hurtz e Donovan (2000)](/docs/services/personality-insights/references.html#hurtz2000) relatou que consciência é a característica personalidade que é mais preditiva de desempenho da tarefa.
-   [Lim e Ployhart (2004)](/docs/services/personality-insights/references.html#lim2004) descobriu que extroversão está positivamente correlacionado com habilidades de liderança.
-   [Judge et al. (2002)](/docs/services/personality-insights/references.html#judge2002) relatou que os indivíduos extraverted são mais satisfeitos no trabalho; trabalho dá a eles uma oportunidade de experimentar um nível ideal de excitação. Por outro lado, indivíduos introvertidos estão menos satisfeitos no trabalho devido a estímulo demais.
-   [van Vianen et al. (2012)](/docs/services/personality-insights/references.html#vanvianen2012) relatou diferenças individuais na adaptabilidade e suas causas, correlaciona e consequências. Eles descobriram que consciência, extroversão e abertura correlação positiva com adaptabilidade carreira.

### Desempenho acadêmico
{: #otherAcademic}

-   [Chamorro-Premuzic e Furnham (2003)](/docs/services/personality-insights/references.html#chamorro2003) relatou um estudo longitudinal no qual eles descobriram que as características de personalidade impactar o desempenho acadêmico. Especificamente, eles descobriram que neuroticism (intervalo emocional) pode prejudicar desempenho acadêmico e que apele pode levar a maior conquista acadêmica.
-   [Komarraju e Karau (2005)](/docs/services/personality-insights/references.html#komarraju2005) descobriu que algumas características da personalidade impactar o comportamento de um indivíduo com relação ao aprendizado de melhorias. O estudo revela que a abertura alta e muitas vezes levam a uma consciência maior interesse em aprender melhorias e que neuroticism alto (intervalo emocional) diminui a motivação para aprender como.

### Os relacionamentos profissionais
{: #otherProRelations}

-   [Flynn e Smith (2007)](/docs/services/personality-insights/references.html#flynn2007) descobriu que as preferências de interação influencia personalidade entre profissionais e clientes. Por exemplo, pacientes com um alto grau de consciência e abertura preferem ficar ativamente envolvido em decidir o curso de tratamento. Pacientes com altos níveis de afabilidade ou escala emocional (neuroticismo) preferem que os médicos tomem a liderança na tomada de importantes decisões de saúde.
-   [Duberstein et al. (2007)](/docs/services/personality-insights/references.html#duberstein2007) da mesma forma, relatou que a personalidade dos médicos afetou o nível de satisfação de seus pacientes. Por exemplo, os pacientes relataram estar mais satisfeitos com médicos que pontuação relativamente alta na abertura e médio em consciência.

### Os relacionamentos pessoais
{: #otherPerRelations}

-   [Botwin et al. (1997)](/docs/services/personality-insights/references.html#botwin1997) descobriu que a personalidade afeta relacionamentos românticos. As características da personalidade do parceiro um significativamente prever a insatisfação conjugal, principalmente quando os resultados de parceiros menores em agradam, intervalo emocional, e a abertura do desejado.

### Saúde
{: #otherHealth}

-   [Turiano et al. (2012)](/docs/services/personality-insights/references.html#turiano2012) relatou um estudo longitudinal sobre um período de tempo de 10 anos em que eles descobriram que as características Big Five previu resultados de saúde. Por exemplo, todas as características, exceto a abertura prevista saúde física auto-classificada, e todas as características, exceto agradam previsto número de dias de trabalho limitado devido à saúde física.
-   [Masui et al. (2006)](/docs/services/personality-insights/references.html#masui2006) descobriu que pontuações altas nos características da personalidade específica consciência, extroversão e abertura estão associados a longevidade. Outros pesquisadores também descobriram uma relação entre as características da personalidade Big Five e expectativa de vida.
-   [Roberts et al. (2007)](/docs/services/personality-insights/references.html#roberts2007) relatou que as características da personalidade específica prever resultados de vida importante, como mortalidade, divórcio, e sucesso no trabalho.

### Dieta e exercício
{: #otherDiet}

-   [Shepherd e Sparks (1994)](/docs/services/personality-insights/references.html#shepherd1994) desenvolveu o relacionamento entre escolha personalidade e comida. O estudo revela que as pessoas com notas altas no intervalo emocional (neuroticism), especialmente no aspecto de um excesso, tendem a consumir alimentos em gordura.
-   [Elfhag e Morey (2008)](/docs/services/personality-insights/references.html#elfhag2008) revelou que consciência é positivamente relacionado a uma preferência para alimentos light. Especificamente, a disciplina e os aspectos dutifulness da dimensão inteligênica influenciar positivamente o consumo de comida light e (porque o gerenciamento de peso está intimamente relacionado com opções de comida) de controle de peso regular.
-   [Céu na al. (2001)](/docs/services/personality-insights/references.html#heaven2001) relatou que o consumo de comida saudável está relacionada a duas dimensões Big Five. As pessoas com alto neuroticismo (escala emocional) geralmente são menos propensas a escolher alimentos saudáveis, enquanto as pessoas com alto estado consciente preferem alimentos saudáveis. O jornal também cita vários aspectos que se relacionam com um pouco de comida escolha: interesses artísticos (da dimensão de abertura) e de autodisciplina (da dimensão consciência) correlacionar positivamente a maior consumo de alimentos saúde; pelo contrário, sendo suscetível a estresse tem uma correlação negativa com um consumo saudável.
-   [Lusk (2012)](/docs/services/personality-insights/references.html#lusk2012) descobriu que os amantes de alta pontuação em abertura a experiência. Abertura pode motivar as pessoas tentar diferentes alimentos e ajudá-los a se tornarem apreciadores de comida.
-   [Courneya e Hellsten (1998)](/docs/services/personality-insights/references.html#courneya1998) descobriu que influencia personalidade a tendência de um indivíduo seguir hábitos associados a um estilo de vida saudável, incluindo exercícios físicos. Extroversão e inteligênica correlacionados positivamente com mais frequentes exercícios físicos, enquanto neuroticism (intervalo emocional) pode influenciar negativamente a frequência de exercício.

### Jantar fora
{: #otherDining}

-   [Kim et al. (2010)](/docs/services/personality-insights/references.html#kim2010) provaram que abertura vivenciar correlaciona positivamente com mais frequentes jantar fora. Quem pontuação baixa na abertura geralmente jantar fora com menos frequência.
-   [Van Trijp e Steenkamp (1992)](/docs/services/personality-insights/references.html#vantrijp1992) descobriu que o jantar se correlaciona com o entusiasmo, buscando (mediático) aspecto da dimensão extroversão.

### A consciência ambiental
{: #otherEnvironment}

-   [Griskevicius et al. (2010)](/docs/services/personality-insights/references.html#griskevicius2010) descobriu que uma pessoa influencia seu interesse em personalidade preocupações ambientais. Eles estudaram a relação entre personalidade e o comportamento ambiental como usar veículos de emissões e buscando viver verde, jardinagem, reciclagem, e assim por diante. Para a maioria das pessoas, níveis mais altos de agradam, transparência e rigor estão associados a uma inclinação maior para o comportamento ambiental.
-   [Fraj e Martinez (2006)](/docs/services/personality-insights/references.html#fraj2006) descobriu que influencia personalidade a decisão de comprar produtos ambientalmente consciente. As pessoas caracterizadas por recursos de personalidade, como extroversão, agradam, e consciência são mais propensos a comprar esses produtos.

### Comunidade de serviço
{: #otherCommunity}

-   [Penner et al. (2005)](/docs/services/personality-insights/references.html#penner2005) relatou que a personalidade de um indivíduo afeta seu envolvimento no serviço de comunidade. Em um estudo revisão, os autores resumidos personalidade vários fatores que influenciam o comportamento prosocial. Eles descobriram que extroversão e agradam têm influências positivas sobre envolvimento em serviço comunitário. Em particular, o altruísmo e aspectos de cooperação da dimensão agradam pode ter o impacto mais, enquanto o aspecto de sociabilidade da dimensão extroversão tem uma correlação positiva mais sutil ao serviço comunitário.

### A religião e espiritualidade
{: #otherReligion}

-   [Adorno et al. (1950)](/docs/services/personality-insights/references.html#adorno1950), em seu livro clássico *The Authoritarian Personality*, relata uma possível correlação entre as características de personalidade e a religião. Eles sugerem que as pessoas que recorde em agradam são mais religiosos, enquanto aqueles que recorde na autoridade desafiador são menos motivados a participar de práticas religiosas e espirituais.
