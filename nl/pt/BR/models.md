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

# Modelos de personalidade
{: #models}

O serviço do {{site.data.keyword.personalityinsightsshort}} baseia-se na psicologia da linguagem em combinação com algoritmos de análise de dados. O serviço analisa o conteúdo que você envia e retorna um perfil de personalidade para o autor da entrada. O serviço infere características da personalidade com base em três modelos:
{: shortdesc}

-   As características da personalidade *Big Five* representam o modelo mais amplamente usado para descrever de forma geral como uma pessoa se envolve com o mundo. O modelo inclui cinco dimensões principais:
    -   [*Afabilidade*](/docs/services/personality-insights?topic=personality-insights-agreeableness) é uma tendência da pessoa que a leva a ser compassiva e cooperativa em relação aos outros.
    -   [*Estado consciente*](/docs/services/personality-insights?topic=personality-insights-conscientiousness) é uma tendência da pessoa que a leva a agir de forma organizada e cuidadosa.
    -   [*Extroversão*](/docs/services/personality-insights?topic=personality-insights-extraversion) é uma tendência da pessoa que a leva a buscar estímulos na companhia de outros.
    -   [*Escala emocional*](/docs/services/personality-insights?topic=personality-insights-emotionalRange), também referida como *Neuroticismo* ou *Reações naturais*, é até que ponto as emoções de uma pessoa são sensíveis ao ambiente da pessoa.
    -   [*Abertura*](/docs/services/personality-insights?topic=personality-insights-openness) é a extensão em que uma pessoa está aberta a experimentar atividades diferentes.

    Cada uma dessas dimensões de nível superior tem seis aspectos que caracterizam ainda mais um indivíduo de acordo com a dimensão.
-   [Necessidades](/docs/services/personality-insights?topic=personality-insights-needs) descrevem quais aspectos de um produto ressoam com uma pessoa. O modelo inclui doze necessidades características.
-   [Valores](/docs/services/personality-insights?topic=personality-insights-values) descrevem os fatores de motivação que influenciam a tomada de decisão de uma pessoa. O modelo inclui cinco valores.

Para obter mais informações sobre como os modelos foram desenvolvidos e como o serviço os usa, consulte [A ciência por trás do serviço](/docs/services/personality-insights?topic=personality-insights-science).

## Descrições de características da personalidade do Big Five
{: #bigFive}

Cada dimensão do Big Five é descrita por três tabelas:

-   A tabela *Aspectos* apresenta os aspectos da dimensão e descreve os indivíduos que pontuam alto em cada aspecto.
-   A tabela *Intervalo de características* apresenta descrições gerais que podem se aplicar a indivíduos cujas pontuações evidenciam mais ou menos de cada aspecto da dimensão, junto com termos que podem descrever tais indivíduos. Para obter uma tabela conveniente em uma única página que resume as tabelas *Intervalo de características* dos aspectos de todas as cinco dimensões, consulte <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Personality-Insights-Facet-Characteristics.pdf" download="Personality-Insights-Facet-Characteristics.pdf">Personality-Insights-Facet-Characteristics.pdf <img src="../../icons/launch-glyph.svg" alt="Ícone de link externo" title="Ícone de link externo"></a>.
-   A tabela *Dimensões primárias e secundárias* apresenta informações que relacionam a dimensão a outras dimensões, descrevendo combinações de características de personalidade. A tabela fornece insight interessante sobre como características primárias e secundárias podem se relacionar para representar a personalidade composta de um indivíduo. Para obter uma tabela conveniente em uma única página que resume as tabelas *Características primárias e secundárias* para todas as cinco dimensões, consulte <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/personality-insights/Personality-Insights-Dimension-Characteristics.pdf" download="Personality-Insights-Dimension-Characteristics.pdf">Personality-Insights-Dimension-Characteristics.pdf <img src="../../icons/launch-glyph.svg" alt="Ícone de link externo" title="Ícone de link externo"></a>.
