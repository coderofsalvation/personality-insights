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

# Orientação de uso
{: #guidance}

Usuários estão aplicando o serviço do {{site.data.keyword.personalityinsightsshort}} a um número crescente de casos de uso. Eles aplicam o serviço para oferecer recomendações personalizadas do produto para os clientes por meio de quiosques dentro da loja. Eles exploram e analisam as diferenças nas personalidades dos presidentes dos EUA, conforme inferido por meio de seu Estado dos Endereços da União. E eles integram o serviço com outro produto no portfólio da {{site.data.keyword.IBM_notm}} {{site.data.keyword.watson}}, o {{site.data.keyword.watson}} Explorer, para demonstrar como um consultor de investimento pode oferecer opções adequadas com base em perfis de personalidade dos investidores. (Para obter mais informações, consulte [Casos de uso](/docs/services/personality-insights?topic=personality-insights-usecases).)
{: shortdesc}

Ao longo do desenvolvimento desses e de outros casos de uso prospectivo, a {{site.data.keyword.IBM_notm}} conversou com bancos, provedores de assistência médica, empresas de gerenciamento de experiência do cliente e agências federais. Essas conversas frequentemente geram dúvidas sobre cenários de uso aplicáveis.

-   Que tipo de texto é melhor para inferir a personalidade de um indivíduo? O texto precisar ser de natureza reflexiva? Em caso afirmativo, qual seria o nível de reflexão e como a reflexão pode ser medida? Consulte [Que tipo de texto é o ideal para inferir personalidade?](#optimal)
-   Como interpretar um texto escrito por uma pessoa sobre outra pessoa? A personalidade de um autor pode ser inferida de trabalhos de ficção do autor? Texto escrito por vários indivíduos pode ser combinado para obter um perfil de personalidade? Consulte [Interpretando resultados de diferentes tipos de texto](#interpreting).
-   Perfis de personalidade podem ser inferidos de texto gerado por serviço de transcrição ou tradução? Consulte [Inferindo personalidade de texto gerado](#inferring).
-   Perfis de personalidade podem ser usados para combinação de indivíduos, monitoramento e previsão de saúde mental e monitoramento de elementos radicais e suspeitos por meio de mídia social? Consulte [Usando perfis de personalidade para usos específicos](#applying).
-   A personalidade de um indivíduo se desenvolve à medida que ele envelhece? Consulte [A personalidade de uma pessoa muda ao longo do tempo?](#evolve)

## Que tipo de texto é ideal para inferir personalidade?
{: #optimal}

Que tipo de texto é mais adequado para inferir personalidade? O texto precisa ser reflexivo, autorreflexivo, formal ou informal? Como se mede as palavras que são usadas na vida diária? Essas palavras são de natureza reflexiva? As respostas para essas perguntas pode ajudá-lo a selecionar a entrada mais apropriada para aplicar o serviço de forma mais eficiente.

O trabalho da {{site.data.keyword.IBM_notm}} no serviço {{site.data.keyword.personalityinsightsshort}} é baseado na premissa fundamental de que as palavras que uma pessoa usa na vida diária revela a personalidade de uma pessoa ([Pennebaker e outros, 2001](/docs/services/personality-insights?topic=personality-insights-references#pennebaker2001) e [Pennebaker e outros, 2007](/docs/services/personality-insights?topic=personality-insights-references#pennebaker2007)). O serviço pode analisar palavras que são gravadas por indivíduos sobre eles mesmos ou sobre qualquer tópico. Para que o serviço gere um retrato de personalidade preciso, os indivíduos deverão escolher e escrever as palavras.

A {{site.data.keyword.IBM_notm}} acredita que o texto que é usado para inferir a personalidade de um indivíduo precisa ser reflexivo. A composição reflexiva expõe as experiências e as respostas pessoais do autor. Exige que o autor ponha uma certa dose de pensamento nas palavras que são escolhidas. Por exemplo, o texto pode incluir opiniões, atitudes, sentimentos e observações do escritor sobre alguém ou algo. Ele também pode expressar os gostos e os desgostos do escritor. Mas deve refletir a seleção de palavras do escritor.

A {{site.data.keyword.IBM_notm}} não identificou referências explícitas na literatura de psicolinguística sobre a necessidade de reflexão no texto que é usado para inferir personalidade. No entanto, {{site.data.keyword.IBM_notm}}observou que alguns estudos usam palavras do texto que foi coletado em uma configuração de laboratório em que as pessoas foram convidadas a escrever redações curtas sobre tópicos específicos. Esse tipo de composição demanda implicitamente um certo esforço de reflexão. Outros estudos utilizavam o texto de amostras naturais, como blogs sobre vários tópicos, tuítes, e-mail ou até mesmo comunicação extraída do jogo *World of Warcraft*. Todos esses estudos pressupõem que as palavras usadas na vida diária revelam personalidade porque tendem a refletir os pensamentos do escritor.

Outros estudos mostram que composição emocional, composição de controle, blogs e transcrições de fala são bem adequados para inferir personalidade. Artigos científicos são inversamente apenas marginalmente adequados para inferir personalidade. Além disso, a literatura indica que chegar a uma medida precisa de personalidade é mais complicado por texto que

-   Não tenha autenticidade, como sarcasmo, ironia, edição intensa ou vários autores
-   Inclua erros ortográficos, palavras técnicas, significados alternativos para palavras, negação e frases em vez de palavras únicas
-   Inclua grupos de comparação inadequados, como composição profissional versus pessoal e técnica versus emocional

## Interpretando resultados de diferentes tipos de texto
{: #interpreting}

O tipo de texto a ser analisado pode ter um efeito significativo na qualidade dos resultados do serviço do {{site.data.keyword.personalityinsightsshort}}. As seções a seguir discutem como interpretar resultados que são obtidos de diferentes fontes:

-   [Interpretando resultados do texto sobre outros](#writingaboutothers)
-   [Interpretando resultados de trabalhos de ficção](#fictionalworks)
-   [Interpretando resultados do texto por múltiplos indivíduos](#multipleindividuals)

### Interpretando resultados do texto sobre outros
{: #writingaboutothers}

Para inferir de forma confiável a personalidade de um indivíduo, o texto precisa ser escrito *pelo* indivíduo ou pode ser escrito *sobre* o indivíduo por outra pessoa? Quando uma pessoa escreve sobre outra pessoa, a personalidade de quem é inferida do texto?

A intuição da {{site.data.keyword.IBM_notm}} é que a composição sempre reflete a personalidade do autor, independentemente do assunto. Por exemplo, se um indivíduo A escreve texto sobre o indivíduo B, uma análise do texto inferna a personalidade do indivíduo A. Embora o indivíduo A esteja escrevendo sobre o indivíduo B, é individual Um que está escolhendo as palavras para expressar as coisas sobre o indivíduo B. No entanto, {{site.data.keyword.IBM_notm}}não testou explicitamente este cenário.

### Interpretando resultados de trabalhos de ficção
{: #fictionalworks}

A {{site.data.keyword.IBM_notm}} não recomenda inferir a personalidade de um autor de seu trabalho de ficção. Ao escrever ficção, os autores intencionalmente retratam cada personagem de forma diferente, eles constroem diálogos para refletir a personalidade dos personagens e predefinem a personalidade de cada personagem em suas mentes.

Usar texto destinado a refletir a personalidade de um personagem fictício personificado para inferir a personalidade do criador desse personagem é questionável. Embora cada autor tenha um estilo exclusivo, os personagens foram propositadamente pré-configurados. No entanto, a personalidade de um autor pode ser inferida por meio dos ensaios de não ficção do autor, transcrições de entrevista ou outros trechos de trabalho, como introduções, prólogos, agradecimentos ou dedicatórias.

### Interpretando resultados do texto por múltiplos indivíduos
{: #multipleindividuals}

Um caso de uso comum do serviço do {{site.data.keyword.personalityinsightsshort}} é analisar os seguidores de uma marca ou de uma empresa. Seguidores são definidos como pessoas que seguem uma empresa no Twitter ou em uma página pública no Facebook. Nesse cenário, o objetivo é derivar a personalidade geral de seguidores de uma empresa. Um método preferencial é coletar texto suficiente que é gravado por membros de um grupo para calcular a personalidade de cada membro individual. As personalidades são, então, colocadas em grupos distintos. Esses grupos representam personas com características de personalidade distintas que seguem a empresa.

Se texto insuficiente estiver disponível por meio de membros de um grupo, o texto que é gravado por muitos membros poderá ser combinado e analisado para produzir um retrato de personalidade médio ou composto para o grupo. Essa abordagem pode mostrar como resultado uma indicação de qualidades dominantes do grupo, mas a precisão desse método diminui com a diversidade da população. Tenha cuidado ao interpretar retratos que são obtidos da agregação do texto de múltiplos indivíduos. O trabalho da {{site.data.keyword.IBM_notm}} nessa área ainda está em seus estágios iniciais; a {{site.data.keyword.IBM_notm}} relatará suas descobertas à medida que desvendar resultados convincentes.

## Inferindo personalidade de texto gerado
{: #inferring}

Analisar texto gerado por serviços de transcrição ou tradução pode impactar a confiabilidade dos resultados do serviço do {{site.data.keyword.personalityinsightsshort}}. As seções a seguir discutem os efeitos de inferir personalidade de texto gerado:

-   [Inferindo personalidade de transcrições de fala](#transcription)
-   [Inferindo personalidade de texto traduzido](#translation)

### Inferindo personalidade de transcrições de fala
{: #transcription}

Mecanismos de transcrição de fala, como o serviço do {{site.data.keyword.IBM_notm}} {{site.data.keyword.speechtotextshort}}, geram texto escrito de palavras faladas. Diferentes motores de transcrição têm diferentes variações de precisão. Os clientes que transcrever o discurso para o texto para uso como entrada para o serviço {{site.data.keyword.personalityinsightsshort}}precisam estar cientes de que os resultados podem variar muito dependendo do desempenho do mecanismo. Especificamente, a {{site.data.keyword.IBM_notm}} aconselha clientes e parceiros de negócios a determinar a qualidade da transcrição em relação a dois tipos de erros:

-   *Eliminação:* uma palavra falada é omitida da transcrição.
-   *Substituição:* uma palavra falada é transcrita incorretamente.

A substituição pode ser um problema mais sério porque pode introduzir palavras que não foram faladas, mas que correspondem a palavras usadas para determinar a personalidade. Antes de usar texto transcrito, considere corrigir manualmente o texto de um corpus de teste e contar os erros encontrados. Em seguida, compare os resultados do texto gerado automaticamente à versão corrigida manualmente para determinar a variação nos resultados devido a erros de transcrição.

### Inferindo personalidade de texto traduzido
{: #translation}

Serviços de tradução de idioma traduzem texto escrito de um idioma para outro idioma. Assim como a transcrição de fala, a questão surge se o texto traduzido pode ser usado como entrada para o serviço do {{site.data.keyword.personalityinsightsshort}}. A {{site.data.keyword.IBM_notm}} não recomenda usar texto obtido de serviços de tradução como entrada para o serviço do {{site.data.keyword.personalityinsightsshort}}. Dependendo do serviço de tradução, os resultados da tradução e da inferência de personalidade podem variar muito. Palavras, seus sentidos e sensibilidades culturais tendem a se perder tradução, produzindo resultados inválidos.

A {{site.data.keyword.IBM_notm}} recomenda que você use como entrada somente texto escritos nos idiomas para os quais o serviço do {{site.data.keyword.personalityinsightsshort}} está ativado. Versões ativadas para idioma do serviço

-   Analise o texto de entrada em seu idioma nativo.
-   Use dicionários de idioma nativo para identificar características de personalidade.
-   Use modelos que são calibrados para o idioma nativo para produzir resultados estatísticos.

Se você precisa analisar texto traduzido, a {{site.data.keyword.IBM_notm}} recomenda que você primeiro traduza manualmente algum texto de amostra usando os serviços de um especialista em linguagem humana. Você poderá então comparar os resultados que o serviço do {{site.data.keyword.personalityinsightsshort}} obtiver do texto traduzido manualmente e automaticamente para entender a variação nos resultados.

O{{site.data.keyword.IBM_notm}}continua a incluir mais idiomas à medida que a demanda de negócios aumenta. A {{site.data.keyword.IBM_notm}} entende que o serviço do {{site.data.keyword.personalityinsightsshort}} poderá não suportar seu idioma nativo rápido o suficiente para seus propósitos. {{site.data.keyword.IBM_notm}}está realizando testes para comparar resultados de ativação de idioma nativo com resultados de serviços de tradução de idioma e relatará suas descobertas à medida que elas se tornam disponíveis.

## Usando perfis de personalidade para usos específicos
{: #applying}

O serviço do {{site.data.keyword.personalityinsightsshort}} pode ser aplicado a inúmeros casos de uso. As seções a seguir descrevem o uso de perfis de personalidades para alguns propósitos específicos:

-   [Combinação de indivíduos](#matching)
-   [Monitorando e prevendo saúde mental](#mentalhealth)
-   [Monitorando elementos radicais e suspeitos por meio de mídia social](#monitoring)

### Combinação de indivíduos
{: #matching}

Uma boa combinação entre as pessoas pode melhorar a interação e os resultados nos relacionamentos. Essa noção também se aplica ao prédio da equipe dentro de uma empresa e à interação com os clientes em uma ampla gama de segmentos de mercado. Em um estudo de combinação médico-paciente, os pesquisadores descobriram que os pacientes preferem médicos que são semelhantes a eles. Combinar médicos e pacientes de forma efetiva cria confiança e incentiva a comunicação, o que pode melhorar o consentimento e resultar em tratamento mais bem-sucedido ([Godager, 2012](/docs/services/personality-insights?topic=personality-insights-references#godager2012)).

A personalidade também influencia as preferências de interação entre profissionais e clientes. Por exemplo, pacientes com um alto grau de estado consciente e abertura preferem estar ativamente envolvidos na decisão do curso de seu tratamento. Pacientes com altos níveis de acetabilidade ou neuroticismo preferem que os médicos tomem a liderança em decisões de saúde importantes ([Flynn e Smith, 2007](/docs/services/personality-insights?topic=personality-insights-references#flynn2007)).

### Monitorando e prevendo saúde mental
{: #mentalhealth}

A {{site.data.keyword.IBM_notm}} acredita que o diagnóstico da doença é mais bem executado por um profissional médico treinado. Pode ser possível detectar alguns sinais do estado mental dos indivíduos com base em seu uso de palavras. Mas o {{site.data.keyword.IBM_notm}}não realizou estudos de verdade em solo ou explorou a possibilidade de estabelecer uma base científica para esse tipo de trabalho.

Clientes e parceiros de negócios que estão interessados em usar o serviço {{site.data.keyword.personalityinsightsshort}}para diagnóstico de funcionamento mental são bem-vindas para projetar e conduzir experimentos de verdade de solo para esses casos de uso. A pesquisa ativa nesta área inclui trabalho que relaciona a personalidade aos resultados de saúde ([Israel e outros, 2014](/docs/services/personality-insights?topic=personality-insights-references#israel2014)). Ele também inclui trabalho que visa a prever pós-parto e outras formas de depressão da mídia social ([De Choudhury e outros, 2013a](/docs/services/personality-insights?topic=personality-insights-references#dechoudhury2013a), e [De Choudhury e outros, 2013b](/docs/services/personality-insights?topic=personality-insights-references#dechoudhury2013b)).

### Monitorando elementos radicais e suspeitos por meio de mídia social
{: #monitoring}

Agências governamentais em todo o mundo estão constantemente procurando maneiras para detectar sinais iniciais da radicalização de indivíduos ou grupos de indivíduos por meio de canais de mídia social. Inferir personalidade da composição de indivíduos é um uso tradicional do serviço do {{site.data.keyword.personalityinsightsshort}}. Portanto, não surpreende que usar o serviço para inferir elementos radicais e suspeitos por meio de mídia social seja um caso de uso viável. Inferências confiáveis requerem não apenas características da personalidade, mas uma série de outros atributos, como gênero, idade e geografia. {{site.data.keyword.IBM_notm}}não possui estudos para validar ou invalidar este caso de uso. Clientes e parceiros de negócios são bem-vindos para realizar estudos para explorar esse caso de uso com base em seus objetivos e requisitos específicos.

## A personalidade de uma pessoa muda ao longo do tempo?
{: #evolve}

A personalidade de uma pessoa se desenvolve ao longo do tempo? Em caso afirmativo, com que frequência o serviço do {{site.data.keyword.personalityinsightsshort}} deve ser usado para inferir a personalidade de uma pessoa? Diferentes estudos relatam evidência pró e contra a teoria de que a personalidade de uma pessoa se estabiliza na idade adulta. No seu trabalho seminal 1890 sobre a medição da estabilidade da personalidade, *Os Princípios da Psicologia*, o psicólogo de Harvard William James observou, "Na maioria de nós, aos trinta anos, o personagem se parece com gesso, e nunca mais amolecerá novamente." Mas estudos mais recentes relatam que a personalidade que se desenvolve ao longo do tempo.

-   [Helson e outros (2002)](/docs/services/personality-insights?topic=personality-insights-references#helson2002)relatais que "a ideia de que a mudança de personalidade é mais pronunciada antes dos 30 anos e, em seguida, atingir um platô não recebeu apoio". Os autores realizaram um estudo longitudinal em duas coortes em um período de 40 anos. Eles observaram que o período de vida e o ambiente social são fatores significativos na mudança de personalidade durante os anos da idade adulta. Eles comentam que "pontuações de Dominância e Independência atingiram o pico na meia idade de ambas as coortes e as pontuações de Responsabilidade foram mais baixas durante os anos de pico da cultura do individualismo".
-   [Scollon e Diener (2006)](/docs/services/personality-insights?topic=personality-insights-references#scollon2006) se propuseram a examinar as diferenças individuais em mudança em extroversão, neuroticismo e satisfação no trabalho e no relacionamento ao longo do tempo. Os autores observaram que o aumento da satisfação no trabalho e no relacionamento estava associado a reduções em neuroticismo e aumentos em extroversão ao longo do tempo.
-   [Roberts e Mroczek (2008)](/docs/services/personality-insights?topic=personality-insights-references#roberts2008) comentam que há evidência de "mudança no nível médio em traços de personalidade, assim como para diferenças individuais em mudança ao longo da vida". Os autores observam que as pessoas mostram um aumento de autoconfiança, cordialidade, autocontrole e estabilidade emocional com a idade. Essas mudanças são predominantes na idade adulta jovem (com idades entre 20 e 40). Além disso, mudança no nível médio das características da personalidade ocorre na meia idade e na velhice, mostrando que as características da personalidade podem mudar em qualquer idade.

Com base nesses estudos, a {{site.data.keyword.IBM_notm}} recomenda que os usuários do serviço do {{site.data.keyword.personalityinsightsshort}} sempre trabalhem com os dados mais recentes e com o máximo de dados disponíveis possível. A {{site.data.keyword.IBM_notm}} ainda recomenda que os usuários atualizem perfis de personalidade em intervalos regulares para capturar as personalidades em evolução dos indivíduos. Embora a {{site.data.keyword.IBM_notm}} tenda a acreditar que a personalidade se desenvolve dentro de determinados limites, não realizou estudos para examinar os limites superior e inferior dessa evolução.

Alguém pode questionar como que frequência os perfis de personalidade dos indivíduos devem ser atualizados. A orientação da {{site.data.keyword.IBM_notm}} é buscar a disponibilidade de novos dados e texto por meio de um indivíduo. Se um indivíduo tiver criado uma quantia substancial de texto novo desde que seu perfil de personalidade foi obtido, pode valer a pena atualizar o perfil. Esta abordagem capta a natureza evolutiva da personalidade, se alguém escolher aceitar que a personalidade evolui. Ela também dá ao serviço {{site.data.keyword.personalityinsightsshort}} o benefício de trabalhar com mais palavras, o que, por sua vez, pode aumentar a precisão dos resultados do serviço.
