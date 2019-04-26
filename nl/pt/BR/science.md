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

# A ciência por trás do serviço
{: #science}

Uma teoria bem aceita de psicologia, marketing e outros campos é que a linguagem humana reflete personalidade, estilo de pensamento, ligações sociais e estados emocionais. A frequência com que as pessoas usam determinadas categorias de palavras pode fornecer pistas para essas características. Vários pesquisadores descobriram que variações de uso de palavra em escritos como blogs, ensaios e tweets podem prever aspectos de personalidade ([Fast e Funder, 2008](/docs/services/personality-insights?topic=personality-insights-references#fast2008); [Gill e outros, 2009](/docs/services/personality-insights?topic=personality-insights-references#gill2009); [Golbeck e outros, 2011](/docs/services/personality-insights?topic=personality-insights-references#golbeck2011); [Hirsh e Peterson, 2009](/docs/services/personality-insights?topic=personality-insights-references#hirsh2009) e [Yarkoni, 2010](/docs/services/personality-insights?topic=personality-insights-references#yarkoni2010)).
{: shortdesc}

A {{site.data.keyword.IBM_notm}} conduziu um conjunto de estudos para entender se as características de personalidade que são inferidas por meio de dados de mídia social podem prever o comportamento e as preferências das pessoas. A {{site.data.keyword.IBM_notm}} descobriu que pessoas com características de personalidade específicas responderam e efetuaram retweet em números mais altos em tarefas de coleção de informações e de difusão. Por exemplo, as pessoas que pontuam alto em busca de excitação são mais propensas a responder, enquanto as pessoas que pontuam alto na cautela são menos propensas a fazer isso ([Mahmud e outros, 2013](/docs/services/personality-insights?topic=personality-insights-references#mahmud2013)). Da mesma forma, as pessoas que pontuam alto em modéstia, abertura e simpatia são mais propensas a difundir informações ([Lee e outros, 2014](/docs/services/personality-insights?topic=personality-insights-references#lee2014)).

{{site.data.keyword.IBM_notm}}também descobriu que pessoas com alta abertura e baixo alcance emocional (neuroticismo), como inferido da linguagem de mídia social, responderam de forma mais favorável (por exemplo, clicando em um link de propaganda ou em uma conta). Esses resultados são corroborados por verificação baseada em pesquisa de opinião, baseada em verdade. Por exemplo, fazer o direcionamento para os 10% de usuários em termos de maior abertura e menor escala emocional resultou em aumentos na taxa de clique de 6,8% para 11,3% e na taxa de acompanhamento de 4,7% para 8,8%.

Vários estudos recentes divulgaram resultados semelhantes para características que foram calculadas de dados de mídia social. Um estudo recente com os dados de armazenamento de varejo descobriu que as pessoas que pontuam alto em ordem, autodisciplina e cautela e baixa na imoderação são 40% mais propensas do que a população aleatória a responder aos cupons. Um segundo estudo descobriu que pessoas com valores específicos mostraram interesses de leitura específicos ([Hsieh e outros 2014](/docs/services/personality-insights?topic=personality-insights-references#hsieh2014)). Por exemplo, pessoas com um valor mais alto de autotranscendência demonstraram interesse em ler artigos sobre o ambiente e pessoas com um valor mais alto em autoaprimoramento mostraram interesse em ler artigos sobre o trabalho. Um terceiro estudo de mais de 600 usuários do Twitter identificou que as características da personalidade de uma pessoa podem prever sua preferência de marca com precisão de 65 por cento.

As seções a seguir se aprofundam nessas descobertas de alto nível para descrever a pesquisa e o desenvolvimento por trás do serviço do {{site.data.keyword.personalityinsightsshort}}. Para obter mais informações sobre estudos que aplicam o serviço a cenários tangíveis, consulte [O serviço em ação](/docs/services/personality-insights?topic=personality-insights-applied).

## Entendendo os modelos de personalidade
{: #researchModels}

Para o serviço do {{site.data.keyword.personalityinsightsshort}}, a {{site.data.keyword.IBM_notm}} desenvolveu modelos para inferir pontuações para dimensões e aspectos do Big Five, Necessidades e Valores de informações textuais. Os modelos relatados pelo serviço são baseados em pesquisas nos campos da psicologia, psicolinguística e marketing:

-   [Big Five](/docs/services/personality-insights?topic=personality-insights-models) é um dos mais estudados dos modelos de personalidade que foram desenvolvidos por psicólogos ([Costa e McCrae, 1992](/docs/services/personality-insights?topic=personality-insights-references#costa1992) e [Norman, 1963](/docs/services/personality-insights?topic=personality-insights-references#norman1963)). É o modelo de personalidade mais amplamente usado para descrever como uma pessoa geralmente se envolve com o mundo. O serviço calcula as cinco dimensões e os trinta aspectos do modelo. As dimensões são geralmente chamadas pelo mnemônico *OCEAN*, em que *O* representa Abertura, *C* Estado consciente, *E* Extroversão, *A* Afabilidade e *N* Neuroticismo. (Como o termo Neuroticismo pode ter um significado clínico específico, o serviço apresenta esses insights sob o título aplicável de Escala emocional.)
-   [Necessidades](/docs/services/personality-insights?topic=personality-insights-needs) é um aspecto importante do comportamento humano. A literatura de pesquisa sugere que vários tipos de necessidades humanas são universais e influenciam diretamente o comportamento do consumidor ([Kotler e Armstrong, 2013](/docs/services/personality-insights?topic=personality-insights-references#kotler2013) e [Ford, 2005](/docs/services/personality-insights?topic=personality-insights-references#ford2005)). As doze categorias de necessidades que são relatadas pelo serviço são descritas na literatura de marketing como desejos que as pessoas esperam atender quando consideram um produto ou um serviço.
-   [Valores](/docs/services/personality-insights?topic=personality-insights-values) transmitem o que é mais importante para um indivíduo. Eles são "objetivos desejáveis e de transição situacional, variando em importância, que servem como princípios de orientação na vida das pessoas" ([Schwartz, 2006](/docs/services/personality-insights?topic=personality-insights-references#schwartz2006)). Schwartz resume cinco recursos que são comuns a todos os valores:

    1.  Valores são crenças.
    1.  Os valores são uma construção motivacional.
    1.  Os valores transcendem ações e situações específicas.
    1.  Os valores orientam a seleção ou avaliação de ações, políticas, pessoas e eventos.
    1.  Os valores variam por importância relativa e podem ser classificados por importância.

    O serviço calcula os cinco valores humanos básicos que foram propostos por Schwartz e que foram validados em mais de vinte países ([Schwartz, 1992](/docs/services/personality-insights?topic=personality-insights-references#schwartz1992)).

## Como características da personalidade são inferidas
{: #researchInfer}

O serviço do {{site.data.keyword.personalityinsightsshort}} infere características da personalidade de informações textuais com base em uma abordagem de vocabulário aberto. Esse método reflete a tendência mais recente na pesquisa sobre inferência de personalidade ([Arnoux e outros, 2017](/docs/services/personality-insights?topic=personality-insights-references#arnoux2017), [Schwartz e outros, 2013](/docs/services/personality-insights?topic=personality-insights-references#schwartz2013) e [Plank e Hovy, 2015](/docs/services/personality-insights?topic=personality-insights-references#plank2015)).

O serviço primeiro converte o texto de entrada em tokens para desenvolver uma representação em um espaço *n*-dimensional. O serviço usa uma técnica de integração de palavras de software livre, [GloVe ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](http://nlp.stanford.edu/projects/glove/){: new_window}, para obter uma representação de vetor para as palavras no texto de entrada ([Pennington e outros, 2014](/docs/services/personality-insights?topic=personality-insights-references#pennington2014)). Em seguida, alimenta essa representação em um algoritmo de aprendizado de máquina que infere um perfil de personalidade com característica do Big Five, Necessidades e Valores. Para treinar o algoritmo, o serviço usa pontuações de pesquisas que foram conduzidas entre milhares de usuários juntamente com dados de suas alimentações do Twitter.

A {{site.data.keyword.IBM_notm}} desenvolveu os modelos para todos os idiomas suportados de maneira idêntica. Os modelos foram desenvolvidos independentemente de dados demográficos do usuário como idade, sexo ou cultura. No futuro, a {{site.data.keyword.IBM_notm}} poderá desenvolver modelos que sejam específicas para diferentes categorias demográficas.

Versões anteriores do serviço usavam o dicionário psicolinguístico Linguistic Inquiry and Word Count (LIWC) com seu modelo de aprendizado de máquina. No entanto, a abordagem de vocabulário aberto supera o modelo baseado em LIWC. Para obter mais informações sobre a precisão do serviço para cada idioma em termos de Erro Médio Absoluto (MAE) e correlação médios, consulte [Qual é a precisão do serviço](#researchPrecise). Para obter orientação sobre como fornecer texto de entrada para obter os resultados mais precisos, consulte [Fornecendo entrada suficiente](/docs/services/personality-insights?topic=personality-insights-input#sufficient).

## Qual é a precisão do serviço
{: #researchPrecise}

A {{site.data.keyword.IBM_notm}} realizou um estudo de validação para entender a precisão abordagem do serviço para inferir um perfil de personalidade. A {{site.data.keyword.IBM_notm}} coletou respostas à pesquisa e feeds do Twitter de 1500 a 2000 participantes para todas as características e idiomas. Para estabelecer *verdade absoluta*, os participantes fizerem quatro conjuntos de testes psicométricos padrão:

-   Um Big Five de 50 itens derivado do International Personality Item Pool (IPIP)
-   Um Facet de 120 itens derivado do Neuroticismo IPIP, Extraversão e Abertura (IPIP-NEO)
-   Necessidades fundamentais de 52 itens desenvolvidos pela {{site.data.keyword.IBM_notm}}
-   Valores Básicos de 26 itens desenvolvidos por Schwartz

A {{site.data.keyword.IBM_notm}} então comparou as pontuações que foram derivadas por seus modelos com as pontuações baseadas em pesquisas para os usuários do Twitter. Com base nesses resultados, a {{site.data.keyword.IBM_notm}} determinou o [Erro Médio Absoluto médio](#preciseMAE) e a [correlação média](#preciseCorrelation) entre as pontuações inferidas e reais para as diferentes categorias de características da personalidade. [
MAE e correlação médios por idioma](#precisePerLanguage) fornecem os valores estatísticos para cada idioma suportado.

### Erro Médio Absoluto médio
{: #preciseMAE}

*Erro Médio Absoluto (MAE)* é uma métrica que é usada para medir a diferença entre os valores reais e os previstos. Para o serviço do {{site.data.keyword.personalityinsightsshort}}, o valor real ou a verdade absoluta é a pontuação de personalidade que foi obtida realizando uma pesquisa de personalidade. O valor previsto é a pontuação que os modelos do serviço produzem.

A {{site.data.keyword.IBM_notm}} calculou o MAE fazendo a média do valor absoluto da diferença entre as pontuações reais e as previstas. A {{site.data.keyword.IBM_notm}} usou o valor absoluto porque prever mais ou menos de valor real é irrelevante. Contanto que exista uma diferença, o modelo é penalizado pela magnitude do erro. Quanto menor o MAE, melhor o desempenho do modelo. A {{site.data.keyword.IBM_notm}} usa uma escala de 0 a 1 para o MAE, em que 0 significa nenhum erro (o valor previsto é exatamente o mesmo que o valor real) e 1 significa erro máximo.

### Correção média
{: #preciseCorrelation}

*Correlação média* é um termo estatístico que mede a interdependência das duas variáveis. Com essa métrica, a {{site.data.keyword.IBM_notm}} mediu a correlação entre pontuações inferidas e reais para as diferentes categorias de características da personalidade. Se a pontuação prevista estiver muito próxima dos resultados reais, a pontuação de correlação é alta; caso contrário, a pontuação é baixa.

A {{site.data.keyword.IBM_notm}} mede a correlação em uma escala de -1 para 1:

-   1 indica um relacionamento linear perfeito direto (crescente).
-   -1 indica um relacionamento linear perfeito inverso (decrescente).

Em todos os outros casos, o valor fica entre esses extremos. Se as variáveis forem independentes (elas não terão qualquer relação), a correlação será 0.

A {{site.data.keyword.IBM_notm}} procura números mais próximos de 1 para melhores previsões. Mas as personalidades são difíceis de prever com base exclusivamente em texto e é raro ver correlações que excedem 0,4 para esses tipos de modelos psicológicos. Na literatura de pesquisa para esse domínio, as correlações maiores que 0,2 são consideradas aceitáveis.

### MAE e correlação médios por idioma
{: #precisePerLanguage}

A tabela a seguir mostra os resultados de MAE e correlação médios por idioma para o serviço do {{site.data.keyword.personalityinsightsshort}}. Os resultados colocam o serviço na vanguarda da inferência de personalidade de dados textuais conforme indicado por [Schwartz e outros (2013)](/docs/services/personality-insights?topic=personality-insights-references#schwartz2013) e [Plank e Hovy (2015)](/docs/services/personality-insights?topic=personality-insights-references#plank2015).

<table summary="Para cada linha que identifica um idioma na primeira coluna, as duas linhas a seguir fornecem o MAE médio e a correlação média para as dimensões do Big Five, os aspectos do Big Five, as Necessidades e os Valores.">
  <caption>Tabela 1. MAE e correlação médios por idioma</caption>
  <tr>
    <th id="language" style="text-align:left; vertical-align:bottom">
      Idioma
    </th>
    <th id="dimensions" style="text-align:center; vertical-align:bottom">
      Cinco principais dimensões
    </th>
    <th id="facets" style="text-align:center; vertical-align:bottom">
      Cinco principais aspectos
    </th>
    <th id="needs" style="text-align:center; vertical-align:bottom">
      Necessidades
    </th>
    <th id="values" style="text-align:center; vertical-align:bottom">
      Valores
    </th>
  </tr>
  <tr>
    <th id="arabic" headers="language" colspan="5" style="text-align:left">
      **Árabe**
    </th>
  </tr>
  <tr>
    <td headers="language arabic" style="text-align:left">
      Média de MAE
    </td>
    <td headers="dimensions arabic" style="text-align:center">
      0,09
    </td>
    <td headers="facets arabic" style="text-align:center">
      0,12
    </td>
    <td headers="needs arabic" style="text-align:center">
      0,11
    </td>
    <td headers="values arabic" style="text-align:center">
      0,10
    </td>
  </tr>
  <tr>
    <td headers="language arabic" style="text-align:left">
      Correção média
    </td>
    <td headers="dimensions arabic" style="text-align:center">
      0,17
    </td>
    <td headers="facets arabic" style="text-align:center">
      0,14
    </td>
    <td headers="needs arabic" style="text-align:center">
      0,13
    </td>
    <td headers="values arabic" style="text-align:center">
      0,14
    </td>
  </tr>
  <tr>
    <th id="english" headers="language" colspan="5" style="text-align:left">
      **Inglês**
    </th>
  </tr>
  <tr>
    <td headers="language english" style="text-align:left">
      Média de MAE
    </td>
    <td headers="dimensions english" style="text-align:center">
      0,12
    </td>
    <td headers="facets english" style="text-align:center">
      0,12
    </td>
    <td headers="needs english" style="text-align:center">
      0,11
    </td>
    <td headers="values english" style="text-align:center">
      0,11
    </td>
  </tr>
  <tr>
    <td headers="language english" style="text-align:left">
      Correção média
    </td>
    <td headers="dimensions english" style="text-align:center">
      0,33
    </td>
    <td headers="facets english" style="text-align:center">
      0,28
    </td>
    <td headers="needs english" style="text-align:center">
      0,22
    </td>
    <td headers="values english" style="text-align:center">
      0,24
    </td>
  </tr>
  <tr>
    <th id="japanese" headers="language" colspan="5" style="text-align:left">
      **Japonês**
    </th>
  </tr>
  <tr>
    <td headers="language japanese" style="text-align:left">
      Média de MAE
    </td>
    <td headers="dimensions japanese" style="text-align:center">
      0,11
    </td>
    <td headers="facets japanese" style="text-align:center">
      0,12
    </td>
    <td headers="needs japanese" style="text-align:center">
      0,11
    </td>
    <td headers="values japanese" style="text-align:center">
      0,11
    </td>
  </tr>
  <tr>
    <td headers="language japanese" style="text-align:left">
      Correção média
    </td>
    <td headers="dimensions japanese" style="text-align:center">
      0,27
    </td>
    <td headers="facets japanese" style="text-align:center">
      0,22
    </td>
    <td headers="needs japanese" style="text-align:center">
      0,25
    </td>
    <td headers="values japanese" style="text-align:center">
      0,19
    </td>
  </tr>
  <tr>
    <th id="korean" headers="language" colspan="5" style="text-align:left">
      **Coreano**
    </th>
  </tr>
  <tr>
    <td headers="language korean" style="text-align:left">
      Média de MAE
    </td>
    <td headers="dimensions korean" style="text-align:center">
      0,11
    </td>
    <td headers="facets korean" style="text-align:center">
      0,12
    </td>
    <td headers="needs korean" style="text-align:center">
      0,11
    </td>
    <td headers="values korean" style="text-align:center">
      0,11
    </td>
  </tr>
  <tr>
    <td headers="language korean" style="text-align:left">
      Correção média
    </td>
    <td headers="dimensions korean" style="text-align:center">
      0,21
    </td>
    <td headers="facets korean" style="text-align:center">
      0,21
    </td>
    <td headers="needs korean" style="text-align:center">
      0,13
    </td>
    <td headers="values korean" style="text-align:center">
      0,12
    </td>
  </tr>
  <tr>
    <th id="spanish" headers="language" colspan="5" style="text-align:left">
      **Espanhol**
    </th>
  </tr>
  <tr>
    <td headers="language spanish" style="text-align:left">
      Média de MAE
    </td>
    <td headers="dimensions spanish" style="text-align:center">
      0,10
    </td>
    <td headers="facets spanish" style="text-align:center">
      0,12
    </td>
    <td headers="needs spanish" style="text-align:center">
      0,12
    </td>
    <td headers="values spanish" style="text-align:center">
      0,11
    </td>
  </tr>
  <tr>
    <td headers="language spanish" style="text-align:left">
      Correção média
    </td>
    <td headers="dimensions spanish" style="text-align:center">
      0,35
    </td>
    <td headers="facets spanish" style="text-align:center">
      0,21
    </td>
    <td headers="needs spanish" style="text-align:center">
      0,24
    </td>
    <td headers="values spanish" style="text-align:center">
      0,19
    </td>
  </tr>
</table>

Para calcular as pontuações de percentil, a {{site.data.keyword.IBM_notm}} coletou um conjunto de dados muito grande de usuários do Twitter e calculou os seus retratos de personalidade:

-   Um milhão de usuários para inglês
-   Duzentos mil usuários para coreano
-   Cem mil usuários para cada um de árabes e japoneses
-   Oitenta mil usuários para espanhol

A {{site.data.keyword.IBM_notm}}, então, comparou as pontuações brutas de cada perfil calculado com a distribuição de perfis dos conjuntos de dados para determinar os percentis.

Para entrada em árabe e coreano, o serviço é incapaz de produzir percentis significativos e pontuações brutas para algumas características de personalidade. Para obter mais informações, veja [Limitações para entrada em árabe e coreano](/docs/services/personality-insights?topic=personality-insights-numeric#limitations).
{: note}

## Entendendo as preferências de consumo
{: #researchPrefs}

O relacionamento entre personalidade e comportamento de compra foi estudado em vários produtos e serviços:

-   [Chen (2007)](/docs/services/personality-insights?topic=personality-insights-references#chen2007), ao testar as preferências por alimentos orgânicos, indicou que as características da personalidade de um indivíduo desempenham um papel importante no estabelecimento de critérios pessoais de escolha de alimentos.
-   [Schlegelmilch e outros (1996)](/docs/services/personality-insights?topic=personality-insights-references#schlegelmilch1996) exploraram o relacionamento entre as variáveis de personalidade e o comportamento de compra pró-ambiental. Os autores mostram que a consciência ambiental geral dos consumidores tem um impacto positivo nas decisões de compras ecológicas.
-   [Hymbaugh e Garrett (2007)](/docs/services/personality-insights?topic=personality-insights-references#hymbaugh1974) investigaram a relação entre personalidade e paraquedismo e descobriram que pessoas que pontuam alto em aventura e busca por entusiasmo geralmente se satisfazem em paraquedismo. (Para obter mais informações, consulte [Criação de perfil de risco](/docs/services/personality-insights?topic=personality-insights-applied#otherRisk).)

A aplicação dessas relações conhecidas entre comportamentos de consumo e personalidade é um desafio. A maioria das obras usou dados de personalidade derivados de pesquisas, e seus modelos não estão publicamente disponíveis. Portanto, a {{site.data.keyword.IBM_notm}} decidiu aprender esses modelos de preferência de consumo diretamente. Quando ela estava treinando os modelos, a {{site.data.keyword.IBM_notm}} usou pontuações de personalidade que foram retornadas do serviço {{site.data.keyword.personalityinsightsshort}} como recursos. Como resultado, ao aplicar esses modelos para calcular as características da personalidade de um usuário com o serviço, as previsões provavelmente serão mais precisas.

## Como preferências de consumo são inferidas
{: #researchInferPrefs}

O serviço do {{site.data.keyword.personalityinsightsshort}} infere preferências de consumo com base nos resultados do seu perfil de personalidade para o autor do texto de entrada. Na literatura existente, a {{site.data.keyword.IBM_notm}} identificou 104 preferências de consumo que provaram estar correlacionadas à personalidade. Estas incluem preferências que estão relacionadas a compras, filmes, música e outras categorias. A {{site.data.keyword.IBM_notm}} criou então uma pesquisa psicométrica para avaliar a inclinação de um indivíduo para cada comportamento de consumo.

A {{site.data.keyword.IBM_notm}} obteve respostas para sua pesquisa de cerca de 600 indivíduos para os quais ela também tinha dados do Twitter (mais de 200 tweets de autoria própria para cada usuário). A {{site.data.keyword.IBM_notm}} enviou os tweets ao serviço para reunir um perfil de personalidade para cada indivíduo. Em seguida, construiu um classificador para cada preferência de consumo, em que o conjunto de recursos de entrada era as informações de personalidade.

Para inclusão no serviço, a {{site.data.keyword.IBM_notm}} selecionou apenas aquelas preferências de consumo para as quais a classificação baseada em personalidade teve um desempenho pelo menos de 9 por cento melhor do que a classificação aleatória. Das 104 preferências originais, 42 satisfizeram esse critério e são expostas como preferências de consumo pelo serviço.

<!--
COMMENTED FOR REMOVAL OF LIWC AND SAMPLING ERROR 08/10/2016

## How media influence inferred characteristics

{{site.data.keyword.IBM_notm}} conducted a validation study to understand the effect of media on inferred characteristics. To determine the accuracy of the service's approach to estimating characteristics, {{site.data.keyword.IBM_notm}} compared scores that were derived by its models with survey-based scores for Twitter users (for instance, approximately 500 users for English and more than 600 for Spanish).

To establish ground truth, participants took three sets of standard psychometric tests: 50-item Big Five (derived from the International Personality Item Pool, or IPIP), 52-item fundamental Needs (developed by {{site.data.keyword.IBM_notm}}), and 26-item basic Values (developed by Schwartz). {{site.data.keyword.IBM_notm}} conducted the study in two phases:

-   For the first study, conducted in 2013, {{site.data.keyword.IBM_notm}} recruited 256 Twitter users ([Gou and others, 2014](/docs/services/personality-insights?topic=personality-insights-references#gou2014)). Although the models were learned from different sources, {{site.data.keyword.IBM_notm}} found that for more than 80 percent of the Twitter users, scores for characteristics that were inferred for all three models correlated significantly with survey-based scores (p-value &lt; 0.05 and correlation coefficient between 0.05 and 0.80). Specifically, scores that were derived by the service correlated with survey-based scores as follows:
    -   For 80.8 percent of participants' Big Five scores (p-value &lt; 0.05 and correlation coefficients between 0.05 and 0.75)
    -   For 86.6 percent of participants' Needs scores (p-value &lt; 0.05 and correlation coefficient between 0.05 and 0.80)
    -   For 98.21 percent of participants' Values scores (p-value &lt; 0.05 and correlation coefficients between 0.05 and 0.55)
-   For the second study, conducted in 2015, {{site.data.keyword.IBM_notm}} recruited another set of 237 Twitter users. The study found that for Big Five and Values, scores for inferred characteristics correlated significantly with survey-based scores (p-value &lt; 0.05 and correlation coefficient between 0.07 and 0.21) for every Twitter user. For needs, such significant correlation was observed for 90 percent of the users (p value &lt; 0.05 and correlation coefficient between 0.01 and 0.20).

In both studies, participants also rated on a five-point scale how well each derived characteristic matched their perceptions of themselves. Their ratings suggest that the inferred characteristics largely matched their self-perceptions. Specifically, means of all ratings were above 3 ("somewhat") out of 5 ("perfect").

-   For the 256 Twitter users of the first study, means were 3.4 (with a standard deviation of 1.14) for Big Five, 3.39 (with a standard deviation of 1.34) for Needs, and 3.13 (with a standard deviation of 1.17) for Values.
-   For the 237 Twitter users of the second study, means were 3.31 (with a standard deviation of 1.18) for Big Five, 3.37 (with a standard deviation of 1.22) for Needs, and 3.36 (with a standard deviation of 1.18) for Values.

COMMENTED FOR REMOVAL OF LIWC AND SAMPLING ERROR 08/10/2016
-->

## Notas sobre pesquisas de personalidade
{: #researchSurveys}

Quando ela desenvolveu o serviço {{site.data.keyword.personalityinsightsshort}}, a {{site.data.keyword.IBM_notm}} confiou em pesquisas de opinião de personalidade para estabelecer dados de verdade básica para inferência de personalidade. Verdade absoluta refere-se aos dados factuais obtidos por meio de observação direta em vez de por meio de inferência. Uma medida típica de precisão para qualquer modelo de aprendizado de máquina é comparar as pontuações que são inferidas pelo modelo com dados de verdade básica. As seções prévias descrevem como a {{site.data.keyword.IBM_notm}} usou pesquisas de opinião para validar a precisão do serviço.

As notas a seguir esclarecem o uso de pesquisas de personalidade e a estimação de personalidade baseada em pesquisa:

-   Pesquisas de personalidade são longas e demoradas para concluir. Os resultados da pesquisa de opinião são restritos pelo número de usuários do Twitter que estavam disponíveis para participar do estudo da {{site.data.keyword.IBM_notm}}. A {{site.data.keyword.IBM_notm}} planeja realizar estudos de validação com mais usuários, assim como com usuários de outras mídias on-line, como e-mail, blogs e fóruns.
-   A estimação de personalidade baseada em pesquisa é baseada em relatório automático, o que pode nem sempre ser um reflexo verdadeiro da personalidade de alguém: alguns usuários podem dar respostas ruidosas a essas pesquisas. Para reduzir o ruído, a {{site.data.keyword.IBM_notm}} filtrou as respostas da pesquisa incluindo perguntas de verificação de atenção e descartando pesquisas que foram concluídas muito rapidamente.
-   Embora a correlação entre pontuações inferidas e baseadas em pesquisa seja positiva e significativa, os resultados sugerem que pontuações inferidas podem nem sempre se correlacionar com resultados baseados em pesquisa. Pesquisadores de fora da {{site.data.keyword.IBM_notm}} também realizaram experimentos para comparar quão bem inferidas as pontuações combinam com pontuações obtidas de pesquisas de opinião e nenhum relatou uma correspondência totalmente consistente:
    -   [Golbeck e outros (2011)](/docs/services/personality-insights?topic=personality-insights-references#golbeck2011) relataram uma taxa de erro de 10% a 18% para pontuações inferidas correspondidas com pontuações baseadas em pesquisa de opinião.
    -   [Sumner e outros (2012)](/docs/services/personality-insights?topic=personality-insights-references#sumner2012) relataram aproximadamente 65% de precisão para a predição de personalidade.
    -   [Mairesse e Walker (2006)](/docs/services/personality-insights?topic=personality-insights-references#mairesse2006) relataram precisão de 60 a 70 por cento para predição de personalidade do Big Five.

Em geral, é amplamente aceito na literatura de pesquisa que pontuações de relatório automático de pesquisas de personalidade nem sempre correspondem totalmente a pontuações que são inferidas de texto. O que é mais importante, no entanto, é que a {{site.data.keyword.IBM_notm}} descobriu que as características que são inferidas do texto geralmente podem prever com segurança o comportamento real.
