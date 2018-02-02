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

# A ciência por trás do serviço
{: #science}

Uma teoria testada de psicologia, marketing e outros campos é que linguagem humana reflete a personalidade, pensando estilo, conexões sociais e estados emocionais. A frequência com a qual usamos certas categorias de palavras podem fornecer pistas para essas características. Alguns pesquisadores descobriram que as variações no uso da palavra em textos como blogs, ensaios, e tweets pode prever os aspectos da personalidade ([Fast &amp; Funder, 2008](/docs/services/personality-insights/references.html#fast2008); [Gill et al., 2009](/docs/services/personality-insights/references.html#gill2009); [Golbeck et al., 2011](/docs/services/personality-insights/references.html#golbeck2011); [ Hirsch &amp; Peterson, 2009](/docs/services/personality-insights/references.html#golbeck2011)); e [Yarkoni, 2010](/docs/services/personality-insights/references.html#yarkoni2010)).
{: shortdesc}

{{site.data.keyword.IBM_notm}} realizou um conjunto de estudos para entender se as características de personalidade inferido a partir dos dados de mídia social pode prever o comportamento e as pessoas preferências. {{site.data.keyword.IBM_notm}} descobriu que pessoas com características da personalidade específica respondeu e retuitou em números mais altos de coleta de informações e tarefas repartição. Por exemplo, as pessoas que pontuação alta na excitação que buscam mais propensas a responder, enquanto aqueles que recorde na prudência são menos propensos a fazer isso ([Mahmud et al., 2013](/docs/services/personality-insights/references.html#mahmud2013)). Da mesma forma, quem recorde na modéstia, abertura e amizade são mais propensos a se espalhar informações ([Lee et al., 2014](/docs/services/personality-insights/references.html#lee2014)).

{{site.data.keyword.IBM_notm}} também descobriu que as pessoas com alta abertura e baixa escala emocional (neuroticismo) como inferidas da linguagem das mídias sociais responderam de forma mais favorável (por exemplo, clicando em um link de propaganda ou seguindo uma conta), resultados que foram corroborados com verificação baseada em pesquisas e verdades absolutas. Por exemplo, contra 10 principais dos usuários por cento em termos de abertura de alta e baixa intervalo emocional resultou em aumentos na taxa clique de 6,8 para 11,3 e a taxa de 4,7 em 8,8.

Vários estudos recentes divulgados resultados semelhantes para características que foram calculados a partir dos dados de mídia social. Um estudo recente com os dados da loja de varejo descobriram que quem recorde em ordem, auto-disciplina, e prudência e baixa em uma imoderação são 40 mais propensos a responder aos cupons que a população aleatória. Um segundo estudo constatou que pessoas com valores específicos mostraram interesse leitura específico ([Hsieh et al. 2014](/docs/services/personality-insights/references.html#hsieh2014)). Por exemplo, as pessoas com um alto auto-transcendência valor demonstrou interesse em ler artigos sobre o ambiente, e as pessoas com um alto auto-aprimoramento valor mostrou um interesse em ler artigos sobre o trabalho. Um terceiro estudo de mais de 600 usuários do Twitter que as características da personalidade de uma pessoa pode prever sua marca preferência com precisão de 65.

As seções a seguir expandem a essas descobertas de alto nível para descrever a pesquisa e desenvolvimento por trás do serviço. {{site.data.keyword.personalityinsightsshort}} Para obter mais informações sobre estudos que se aplicam o serviço para cenários concretos, consulte [O serviço em ação](/docs/services/personality-insights/applied.html).

## Entendendo os modelos de personalidade
{: #researchModels}

Para o {{site.data.keyword.personalityinsightsshort}} serviço, {{site.data.keyword.IBM_notm}} desenvolveu modelos para inferir pontuações para dimensões Big Five e aspectos, Necessidades, e Valores de informações textuais. Os modelos relatados pelo serviço são baseados em pesquisas nos campos da psicologia, mistério, e marketing:

-   [Big Five](/docs/services/personality-insights/models.html) é um dos melhores modelos de estudos de personalidade desenvolvidos por psicólogos ([Costa &amp; McCrae, 1992](/docs/services/personality-insights/references.html#costa1992) e [Norman, 1963](/docs/services/personality-insights/references.html#norman1963)). É o modelo personalidade mais amplamente usado para descrever como uma pessoa geralmente se envolve com o mundo. O serviço calcula os cinco dimensões e trinta aspectos do modelo. As dimensões são geralmente chamados pelo mnemônico *OCEANO*, em que *O* representa Abertura, *C* para consciente, *E* para Extroversão, *A* para Afabilidade, e *N* para Neuroticismo. (Como o termo Neuroticismo pode ter um significado clínico específico, o serviço apresenta tais insights sob o mais geralmente aplicável de Faixa emocional.)
-   [Necessária](/docs/services/personality-insights/needs.html) são um aspecto importante do comportamento humano. Pesquisa sugere que literatura vários tipos de necessidades humanas são universais e influenciam diretamente o comportamento do consumidor ([KotIer &amp; Armstrong, 2013](/docs/services/personality-insights/references.html#kotler2013), e [Ford, 2005](/docs/services/personality-insights/references.html#ford2005)). Os doze categorias de necessidades que são relatados pelo serviço são descritas na literatura de marketing como desejos que uma pessoa espera cumprir quando considerar um produto ou serviço.
-   [Valores](/docs/services/personality-insights/values.html) transmitem o que é mais importante para um indivíduo. Eles são "desejáveis, trans-objetivos situacionais, variando em importância, que servem como princípios de orientação na vida das pessoas" ([Schwartz, 2006](/docs/services/personality-insights/references.html#schwartz2006)). Schwartz resume cinco recursos que são comuns a todos os valores: (1) valores são crenças; (2) valores são uma construção motivacional; (3) valores ultrapassam específicos ações e situações; (4) valores orientar a seleção ou avaliação de ações, políticas, pessoas e eventos; e (5) valores variam por importância relativa e podem ser classificados de acordo. O serviço calcula os cinco valores humanos básicos propostos por Schwartz e validado em mais de vinte países ([Schwartz, 1992](/docs/services/personality-insights/references.html#schwartz1992)).

## Como as características da personalidade são inferidas
{: #researchInfer}

O serviço {{site.data.keyword.personalityinsightsshort}} infere personalidade características de informações textuais com base em uma abordagem aberta-vocabulário. Este método reflete a tendência mais recente na pesquisa sobre a personalidade inferência ([Arnoux et al., 2017](/docs/services/personality-insights/references.html#arnoux2017), [Schwartz et al., 2013](/docs/services/personality-insights/references.html#schwartz2013), e [PlanK &amp; Hovy, 2015](/docs/services/personality-insights/references.html#plank2015)).

O serviço primeiro converte o texto de entrada para desenvolver uma representação no espaço dimensões um *n*. O serviço usa uma técnica de software livre integrada por palavras chamada [GloVe ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](http://nlp.stanford.edu/projects/glove/){: new_window} para obter uma representação vetorial para as palavras no texto de entrada ([Pennington et al., 2014](/docs/services/personality-insights/references.html#pennington2014)). Em seguida, alimenta essa representação para um algoritmo de aprendizado por máquina que infere um perfil de personalidade com Big Five, Necessidades, e Valores características. Para treinar o algoritmo, o serviço usa as pontuações obtidas a partir de pesquisas realizadas entre milhares de usuários juntamente com dados de seus feeds do Twitter.

{{site.data.keyword.IBM_notm}} desenvolveu os modelos para todos os idiomas suportados em uma forma idêntica. Os modelos foram desenvolvidos independentes demográficos do usuário como idade, sexo, ou cultura. No futuro, {{site.data.keyword.IBM_notm}} pode desenvolver modelos que são específicas para diferentes categorias demográficas.

Versões anteriores do serviço usado na consulta lingüística e Contagem de Palavras (LIWC) linguísticas dicionário com seu modelo de aprendizado por máquina. No entanto, a abordagem aberta vocabulário descreveu supera o modelo LIWC baseado. Para obter mais informações sobre a precisão do serviço para cada idioma em termos de média Erro Absoluto Médio (MAE) e de correlação, consulte [Como exato é o serviço](#researchPrecise). Para obter orientação sobre fornecer texto de entrada para alcançar os resultados mais precisos, consulte [Fornecendo suficiente de entrada](/docs/services/personality-insights/input.html#sufficient).

## Como precisa é o serviço
{: #researchPrecise}

{{site.data.keyword.IBM_notm}} realizou um estudo de validação para entender a precisão de aproximação do serviço para concluir um perfil de personalidade. {{site.data.keyword.IBM_notm}} coletados pesquisa respostas e Twitter feeds de entre 1500 e 2000 participantes para todas as características e idiomas. Para estabelecer *terreno verdade*, os participantes levou quatro conjuntos de testes psicométricos padrão:

-   50 itens do Big Five derivados do International Personality Item Pool (IPIP)
-   Aspecto 120-item derivado da Neuroticismo IPIP, Extroversão &amp; Openness (IPIP-NEO)
-   Necessidades fundamentais de 52 itens desenvolvido pela {{site.data.keyword.IBM_notm}}
-   Valores de 26 itens básicos desenvolvidos por Schwartz

{{site.data.keyword.IBM_notm}} então comparou as pontuações que foram derivados por seus modelos com as pontuações, e para os usuários do Twitter. Com base nestes resultados, {{site.data.keyword.IBM_notm}} determinou o [média Médio Absoluto Erro](#preciseMAE) e [média de correlação](#preciseCorrelation) entre os resultados inferidos e reais para diferentes categorias de características da personalidade. [Por linguagem média MAE e correlação](#precisePerLanguage) fornece os valores estatísticos para cada idioma suportado.

### Média de Erro Absoluto Médio
{: #preciseMAE}

*Mean Absolute Error (MAE)* é uma métrica que é usada para medir a diferença entre os valores reais e os previstos. Para o {{site.data.keyword.personalityinsightsshort}} serviço, o valor real, ou verdade solo, é a pontuação personalidade que foi obtida pela administração de uma pesquisa personalidade. O valor previsto é a pontuação que os modelos do serviço produz.

{{site.data.keyword.IBM_notm}} computado o MAE levando a média do valor absoluto da diferença entre o real e resultados previstos. {{site.data.keyword.IBM_notm}} usou o valor absoluto porque prever mais ou menos do valor real é irrelevante; enquanto houver uma diferença, o modelo é penalizado pela magnitude do erro. Quanto menor o MAE, melhor o desempenho do modelo. {{site.data.keyword.IBM_notm}} usa uma escala de 0 1 para MAE, em que 0 significa nenhum erro (o valor previsto é o mesmo que o valor real), e 1 significa erro máximo.

### Média de correlação
{: #preciseCorrelation}

*Média de correlação* é um termo estatístico que mede a interdependência das duas variáveis. Com esta métrica, {{site.data.keyword.IBM_notm}} medido a correlação entre resultados inferidos e reais para diferentes categorias de características da personalidade. Se o resultado previsto estreitamente controla os resultados reais, a pontuação de correlação é alto; caso contrário, a pontuação é baixa.

{{site.data.keyword.IBM_notm}} medidas de correlação na escala de -1 1: 1 indica uma perfeita direta (crescente) relacionamento linear, e -1 indica uma inversão perfeita (decrescente) relacionamento linear. Em todos os outros casos, o valor fica entre esses extremos. Se as variáveis são independentes (eles não têm relacionamento em todos), a correlação é 0.

{{site.data.keyword.IBM_notm}} procura números mais próximos de 1 para as melhores previsões. Mas as personalidades são difíceis de prever com base exclusivamente em texto, e é raro ver correlações exceder 0,4 para esses tipos de modelos psicológicos. Na literatura de pesquisa para este domínio, correlações acima de 0,2 são considerados aceitáveis.

### Por linguagem média MAE e correlação
{: #precisePerLanguage}

A tabela a seguir mostra cada idioma média MAE e os resultados de correlação para o {{site.data.keyword.personalityinsightsshort}} serviço. Os resultados colocar o serviço na vanguarda da personalidade inferência de dados textuais, conforme indicado por [Schwartz et al. (2013)](/docs/services/personality-insights/references.html#schwartz2013) e [PlanK. e Hovy (2015)](/docs/services/personality-insights/references.html#plank2015).

<table>
  <caption>Tabela 1. MAE Médio e correlação por idioma</caption>
  <tr>
    <th style="text-align:left; vertical-align:bottom">
      Idioma
    </th>
    <th style="text-align:center; vertical-align:bottom">
      Grande cinco dimensões
    </th>
    <th style="text-align:center; vertical-align:bottom">
      Big Five Aspectos
    </th>
    <th style="text-align:center; vertical-align:bottom">
      Necessidades
    </th>
    <th style="text-align:center; vertical-align:bottom">
      Valores
    </th>
  </tr>
  <tr>
    <td colspan="5" style="text-align:left">
      **Inglês**
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Média MAE
    </td>
    <td style="text-align:center">
      0,12
    </td>
    <td style="text-align:center">
      0,12
    </td>
    <td style="text-align:center">
      0,11
    </td>
    <td style="text-align:center">
      0,11
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Média de correlação
    </td>
    <td style="text-align:center">
      0,33
    </td>
    <td style="text-align:center">
      0,28
    </td>
    <td style="text-align:center">
      0,22
    </td>
    <td style="text-align:center">
      0,24
    </td>
  </tr>
  <tr>
    <td colspan="5" style="text-align:left">
      **Espanhol**
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Média MAE
    </td>
    <td style="text-align:center">
      0,10
    </td>
    <td style="text-align:center">
      0,12
    </td>
    <td style="text-align:center">
      0,12
    </td>
    <td style="text-align:center">
      0,11
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Média de correlação
    </td>
    <td style="text-align:center">
      0,35
    </td>
    <td style="text-align:center">
      0,21
    </td>
    <td style="text-align:center">
      0,24
    </td>
    <td style="text-align:center">
      0,19
    </td>
  </tr>
  <tr>
    <td colspan="5" style="text-align:left">
      **Japonês**
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Média MAE
    </td>
    <td style="text-align:center">
      0,11
    </td>
    <td style="text-align:center">
      0,12
    </td>
    <td style="text-align:center">
      0,11
    </td>
    <td style="text-align:center">
      0,11
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Média de correlação
    </td>
    <td style="text-align:center">
      0,27
    </td>
    <td style="text-align:center">
      0,22
    </td>
    <td style="text-align:center">
      0,25
    </td>
    <td style="text-align:center">
      0,19
    </td>
  </tr>
  <tr>
    <td colspan="5" style="text-align:left">
      **Árabe**
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Média MAE
    </td>
    <td style="text-align:center">
      0,09
    </td>
    <td style="text-align:center">
      0,12
    </td>
    <td style="text-align:center">
      0,11
    </td>
    <td style="text-align:center">
      0,10
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Média de correlação
    </td>
    <td style="text-align:center">
      0,17
    </td>
    <td style="text-align:center">
      0,14
    </td>
    <td style="text-align:center">
      0,13
    </td>
    <td style="text-align:center">
      0,14
    </td>
  </tr>
  <tr>
    <td colspan="5" style="text-align:left">
      **Coreano**
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Média MAE
    </td>
    <td style="text-align:center">
      0,11
    </td>
    <td style="text-align:center">
      0,12
    </td>
    <td style="text-align:center">
      0,11
    </td>
    <td style="text-align:center">
      0,11
    </td>
  </tr>
  <tr>
    <td style="text-align:left">
      Média de correlação
    </td>
    <td style="text-align:center">
      0,21
    </td>
    <td style="text-align:center">
      0,21
    </td>
    <td style="text-align:center">
      0,13
    </td>
    <td style="text-align:center">
      0,12
    </td>
  </tr>
</table>

Para calcular as pontuações percentis, a {{site.data.keyword.IBM_notm}} coletou um conjunto de dados muito grande de usuários do Twitter (um milhão de usuários para inglês, 200.000 usuários para coreano, 100.000 usuários para árabe e 100.000 para japonês e 80.000 usuários para espanhol) e calculou seus retratos de personalidade. {{site.data.keyword.IBM_notm}} em seguida, comparou os resultados brutos de cada perfil calculado para a distribuição de perfis a partir desses conjuntos de dados para determinar o percentual.

> **Nota:** Para entrada árabe e coreano, o serviço é incapaz de produzir percentis significativas e pontuações brutos para algumas características da personalidade. Para obter mais informações, consulte [Limitações para entrada árabe e coreano](/docs/services/personality-insights/numeric.html#limitations).

## Entendendo as preferências de consumo
{: #researchPrefs}

O relacionamento entre personalidade e comportamento de compra foi estudado em uma variedade de produtos e serviços:

-   [Chen (2007)](/docs/services/personality-insights/references.html#chen2007), enquanto o teste preferências sobre alimentos orgânicos, indicou que as características da personalidade de um indivíduo jogar um papel importante no estabelecimento de critérios de escolha pessoal.
-   [Schlegelmilch na al. (1996)](/docs/services/personality-insights/references.html#schlegelmilch1996) explorou o relacionamento entre as variáveis personalidade e comportamento de compra pró-ambiental. Os autores mostram que a consciência ambiental geral dos consumidores tem um impacto positivo nas decisões de compra verde.
-   [Hymbaugh e Garrett (2007)](/docs/services/personality-insights/references.html#hymbaugh1974) investigou o relacionamento entre personalidade e paraquedas e descobriram que quem recorde na aventura e excitação em busca geralmente satisfazer em paraquedismo. (Para obter mais informações, consulte [Perfil de Risco](/docs/services/personality-insights/applied.html#otherRisk).)

Aplicando essas relações conhecidas entre os comportamentos de consumo e personalidade é um desafio: A maioria desses trabalhos usou dados de personalidade derivado de pesquisas, e seus modelos não estão disponíveis publicamente. {{site.data.keyword.IBM_notm}} portanto decidi aprender esses modelos de preferência consumo diretamente. Ao treinar os modelos, {{site.data.keyword.IBM_notm}} pontuações personalidade usados retornados do {{site.data.keyword.personalityinsightsshort}} serviço como recursos. Como resultado, quando você aplica esses modelos para calcular as características de personalidade um usuário com o serviço, as previsões devem ser mais precisos.

## Como as preferências de consumo são inferidas
{: #researchInferPrefs}

O serviço {{site.data.keyword.personalityinsightsshort}} infere preferências de consumo com base nos resultados do seu perfil de personalidade para o autor do texto de entrada. A literatura existente, {{site.data.keyword.IBM_notm}} identificou 104 preferências de consumo que provaram ser correlacionado com personalidade. Eles incluem as preferências relacionadas a compras, filmes, música, e outras categorias. {{site.data.keyword.IBM_notm}} então criou uma pesquisa psicométricos para avaliar inclinação um indivíduo para cada comportamento de consumo.

{{site.data.keyword.IBM_notm}} obtido respostas para sua pesquisa de cerca de 600 indivíduos para os quais ela também tinha dados do Twitter (mais de 200 tuítes autoassinados criados para cada usuário). {{site.data.keyword.IBM_notm}} enviou os tweets ao serviço para reunir um perfil de personalidade para cada indivíduo. Em seguida, construiu uma classificador para cada preferência consumo, onde o conjunto de recursos de entrada estava informações personalidade.

Para inclusão com o serviço, {{site.data.keyword.IBM_notm}} selecionado apenas aqueles preferências de consumo para o qual a classificação personality-based executada pelo menos 9 melhor do que a classificação aleatória. Dos 104 preferências originais, 42 satisfeito este critério e são expostos como preferências consumo pelo serviço.

<!--
COMMENTED FOR REMOVAL OF LIWC AND SAMPLING ERROR 08/10/2016

## How media influence inferred characteristics

{{site.data.keyword.IBM_notm}} conducted a validation study to understand the effect of media on inferred characteristics. To determine the accuracy of the service's approach to estimating characteristics, {{site.data.keyword.IBM_notm}} compared scores that were derived by its models with survey-based scores for Twitter users (for instance, approximately 500 users for English and more than 600 for Spanish).

To establish ground truth, participants took three sets of standard psychometric tests: 50-item Big Five (derived from the International Personality Item Pool, or IPIP), 52-item fundamental Needs (developed by {{site.data.keyword.IBM_notm}}), and 26-item basic Values (developed by Schwartz). {{site.data.keyword.IBM_notm}} conducted the study in two phases:

-   For the first study, conducted in 2013, {{site.data.keyword.IBM_notm}} recruited 256 Twitter users ([Gou et al., 2014](/docs/services/personality-insights/references.html#gou2014)). Although the models were learned from different sources, {{site.data.keyword.IBM_notm}} found that for more than 80 percent of the Twitter users, scores for characteristics that were inferred for all three models correlated significantly with survey-based scores (p-value &lt; 0.05 and correlation coefficient between 0.05 and 0.80). Specifically, scores that were derived by the service correlated with survey-based scores as follows:
    -   For 80.8 percent of participants' Big Five scores (p-value &lt; 0.05 and correlation coefficients between 0.05 and 0.75)
    -   For 86.6 percent of participants' Needs scores (p-value &lt; 0.05 and correlation coefficient between 0.05 and 0.80)
    -   For 98.21 percent of participants' Values scores (p-value &lt; 0.05 and correlation coefficients between 0.05 and 0.55)
-   For the second study, conducted in 2015, {{site.data.keyword.IBM_notm}} recruited another set of 237 Twitter users. The study found that for Big Five and Values, scores for inferred characteristics correlated significantly with survey-based scores (p-value &lt; 0.05 and correlation coefficient between 0.07 and 0.21) for every Twitter user. For needs, such significant correlation was observed for 90 percent of the users (p value &lt; 0.05 and correlation coefficient between 0.01 and 0.20).

In both studies, participants also rated on a five-point scale how well each derived characteristic matched their perceptions of themselves. Their ratings suggest that the inferred characteristics largely matched their self-perceptions. Specifically, means of all ratings were above 3 ("somewhat") out of 5 ("perfect").

-   For the 256 Twitter users of the first study, means were 3.4 (with a standard deviation of 1.14) for Big Five, 3.39 (with a standard deviation of 1.34) for Needs, and 3.13 (with a standard deviation of 1.17) for Values.
-   For the 237 Twitter users of the second study, means were 3.31 (with a standard deviation of 1.18) for Big Five, 3.37 (with a standard deviation of 1.22) for Needs, and 3.36 (with a standard deviation of 1.18) for Values.

COMMENTED FOR REMOVAL OF LIWC AND SAMPLING ERROR 08/10/2016
-->

## Notas sobre as pesquisas de personalidade
{: #researchSurveys}

Ao desenvolver o serviço {{site.data.keyword.personalityinsightsshort}} , {{site.data.keyword.IBM_notm}} confiar em pesquisas personalidade para estabelecer dados terreno verdade para inferência personalidade. Terra refere-se à verdade dados factuais obtidas através da observação direta ao invés de através de inferência. Uma medida típica de precisão para qualquer máquina-modelo de aprendizado é comparar os resultados inferidos pelo modelo com dados terreno verdade; as seções anteriores descrevem como o {{site.data.keyword.IBM_notm}} usou pesquisas para validar a exatidão do serviço.

As notas a seguir esclarecer o uso de pesquisas personalidade e estimativa de personalidade, e:

-   Pesquisas Personalidade são longos e demorados para concluir. Os resultados são, portanto, limitados pelo número de usuários do Twitter que estavam dispostos e disponíveis para participar do estudo da {{site.data.keyword.IBM_notm}}. {{site.data.keyword.IBM_notm}} planeja realizar estudos de validação com mais usuários, bem como com usuários de outros meios online como e-mail, blogs e fóruns.
-   Pesquisa de estimativa de personalidade baseada em é baseado em auto-relatório, que nem sempre podem ser um reflexo verdadeiro da personalidade de um: Alguns usuários podem dar respostas ruidosas para essas pesquisas. Para reduzir o ruído, {{site.data.keyword.IBM_notm}} filtrou as respostas da pesquisa de incluindo perguntas atenção e verificar por descartar pesquisas que foram concluídas muito rapidamente.
-   Embora a correlação entre resultados inferidos e levantamentos é tanto positivo e significativo, os resultados indicam que pontuações inferidos podem nem sempre se correlacionam com resultados baseados. Pesquisadores de fora do {{site.data.keyword.IBM_notm}} também têm feito experiências para comparar como as pontuações inferidas correspondem às obtidas pesquisas, e nenhuma registrou um jogo totalmente consistente:
    -   [Golbeck et al. (2011)](/docs/services/personality-insights/references.html#golbeck2011) relatou uma taxa de erro de 10 para 18 quando pontuações inferidas correspondentes com pontuação sobre.
    -   [Sumner et al. (2012)](/docs/services/personality-insights/references.html#sumner2012) relatou aproximadamente 65 por cento de precisão para a previsão de personalidade.
    -   [Mairesse e Walker (2006)](/docs/services/personality-insights/references.html#mairesse2006) relatou precisão 60 70 por cento para predição de personalidade Big Five.

Em geral, é amplamente aceito na literatura de pesquisa que declaram dezenas de pesquisas personalidade nem sempre correspondem totalmente pontuações que são inferidos a partir de texto. O que é mais importante, porém, é que o {{site.data.keyword.IBM_notm}} descobriu que características inferido a partir de texto podem confiavelmente prever uma variedade de comportamento real.
