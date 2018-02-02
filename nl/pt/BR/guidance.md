---

copyright: years: 2015, 2017 lastupdated: "2017-08-13"

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

# Uso de orientação
{: #guidance}

Os usuários são aplicando o {{site.data.keyword.personalityinsightsshort}} serviço para um número crescente de casos de uso. Eles têm aplicado o serviço para oferecer recomendações de produto personalizadas para clientes através de quiosques na loja. Eles têm exploradas e analisadas diferenças na personalidade de presidentes americanos como inferida do seu Estado da União Endereços. E eles têm integrado o serviço com outro produto no {{site.data.keyword.IBM_notm}} {{site.data.keyword.watson}} portfólio, {{site.data.keyword.watson}} Explorer, para demonstrar como um consultor de investimentos pode oferecer opções apropriadas com base em fotos personalidade dos investidores. (Para obter mais informações, consulte [Usar casos](/docs/services/personality-insights/usecases.html).)
{: shortdesc}

Durante o desenvolvimento desses e outros possíveis casos de uso, {{site.data.keyword.IBM_notm}} teve conversas com bancos, provedores de saúde, empresas de experiência de cliente, e agências federais. Essas conversas sempre geram dúvidas sobre os cenários de uso aplicável. Algumas dessas perguntas e links para suas respostas estão disponíveis como FAQs. {{site.data.keyword.IBM_notm}}perspectiva em um número de perguntas adicionais a seguir:

-   Que tipo de texto é melhor para concluir a personalidade de um indivíduo? O texto tem que ser reflexiva na natureza? Se sim, como reflexo e como uma medida de reflexão. Consulte [Qual tipo de texto é o ideal para inferir personalidade?](#optimal)
-   Como interpretar um texto que é gravado por uma pessoa por outra pessoa? Você personalidade um autor ser inferido a partir de ficção do autor? Posso texto que é gravado por vários indivíduos sejam combinados para obter um retrato personalidade? Consulte [Interpretando resultados de diferentes tipos de texto](#interpreting).
-   Você retratos de personalidade ser inferido a partir de texto que é gerado pelo serviço de transcrição ou tradução? Consulte [Inferindo personalidade de texto gerado](#inferring).
-   Podem ser aplicados retratos de personalidade a aplicações, como a correspondência de indivíduos, o monitoramento e a previsão de saúde mental e o monitoramento de elementos radicais e suspeitos via mídia social? Consulte [Usando retratos de personalidades para aplicativos específicos](#applying).
-   A personalidade de um indivíduo desenvolver como eles idade? Consulte [A mudança de personalidade de uma pessoa ao longo do tempo.](#evolve)

## Qual tipo de texto é o ideal para inferir personalidade?
{: #optimal}

Que tipo de texto é mais adequado para personalidade deduzindo? O texto precisa ser reflexivo, auto-reflexiva, formal ou informal. Como uma medida as palavras que são usados na vida diária? Essas palavras estão reflexivas na natureza? As respostas a essas perguntas pode ajudá-lo a selecionar a entrada mais apropriada para aplicar o serviço mais eficiente.

{{site.data.keyword.IBM_notm}}trabalhar no {{site.data.keyword.personalityinsightsshort}} serviço é baseado na premissa fundamental que as palavras que usa na vida diária revela a personalidade deles é ([Pennebaker et al., 2001](/docs/services/personality-insights/references.html#pennebaker2001), e [Pennebaker et al., 2007](/docs/services/personality-insights/references.html#pennebaker2007)). O serviço pode analisar palavras que são gravados por pessoas sobre si ou sobre qualquer tópico, mas o indivíduo deve escolher e escrever as palavras para o serviço para gerar um retrato da personalidade exata.

{{site.data.keyword.IBM_notm}} acredita que, idealmente, o texto que é utilizado para indicar a personalidade de um indivíduo precisa ser reflexiva. Refletivo expõe a escrita do autor pessoal experiências e respostas; ela requer que o autor colocou uma certa quantidade de pensamento em palavras que são escolhidos. Por exemplo, o texto pode incluir opiniões do escritor, atitudes, sentimentos, e observações sobre alguém ou algo, ou pode expressar o escritor gostos e desgostos, mas deve refletir a seleção do escritor de palavras.

{{site.data.keyword.IBM_notm}} não localizar referências explícitas na literatura o mistério sobre a necessidade de reflexão no texto que é utilizado para indicar personalidade. No entanto, {{site.data.keyword.IBM_notm}} não observar que alguns estudos usam palavras de texto coletados em uma configuração de laboratório em que as pessoas foram convidados a escrever textos curtos em tópicos específicos. Esse tipo de escrita implicitamente exige uma certa quantidade de reflexão. Outros estudos usou texto de amostras naturais como blogs em vários tópicos, tweets no Twitter, e-mail, ou mesmo de comunicação que é extraída do jogo *World of Warcraft*. Todos esses estudos assumem que as palavras usadas na vida diária revelam personalidade porque tendem a refletir os pensamentos do escritor.

Outros estudos mostram que escrever emocional, a gravação de controle, blogs e transcrições do discurso são bem adequado para uma personalidade deduzindo. Artigos científicos, inversamente, são apenas marginalmente adequado para personalidade deduzindo. Além disso, a literatura indica que chegam em uma medida exata da personalidade é mais complicado pelo texto que

-   Falta de autenticidade, como sarcasmo, ironia, edição intensa, ou vários autores
-   Inclui erros ortográficos, palavras técnicas, significados alternativos para palavras, negação, e frases em vez de palavras simples
-   Inclui grupos de comparação inadequado, como profissional versus pessoal e técnico em gravação emocional

## Interpretando resultados de tipos diferentes de texto
{: #interpreting}

O tipo de texto a ser analisado pode ter um efeito significativo no qualidade dos resultados do serviço. {{site.data.keyword.personalityinsightsshort}} As seções a seguir discutem como interpretar resultados que são obtidos a partir de origens diferentes:

-   [Interpretando resultados do texto escrito sobre outros](#writingaboutothers)
-   [Interpretando resultados de ficção funciona](#fictionalworks)
-   [Interpretando resultados do texto escrito por vários indivíduos](#multipleindividuals)

### Interpretando resultados do texto escrito sobre os outros
{: #writingaboutothers}

Para concluir de forma confiável de personalidade de um indivíduo, o texto tem que ser gravados *por* o indivíduo ou pode ser gravados *sobre* o indivíduo por outra pessoa? Quando uma pessoa escreve sobre outra pessoa, cuja personalidade é inferida a partir do texto?

{{site.data.keyword.IBM_notm}}de intuição é que escrever sempre reflete a personalidade do autor, independentemente do assunto. Por exemplo, se uma pessoa grava texto sobre B individual, uma análise do texto infere a personalidade de cada A. Embora Um indivíduo está escrevendo sobre B individuais, é um indivíduo que está escolhendo as palavras para expressar coisas sobre individuais B. No entanto, {{site.data.keyword.IBM_notm}} não tem feito estudos para testar explicitamente este cenário.

### Interpretando os resultados de trabalhos de ficção
{: #fictionalworks}

{{site.data.keyword.IBM_notm}} não recomenda deduzindo personalidade um autor do seu trabalho de ficção. Quando eles escrever ficção, os autores intencionalmente retratar cada caractere de forma diferente, eles constroem diálogo para refletir a personalidade dos personagens, e eles predefinem a personalidade de cada personagem em suas mentes.

Usando o texto que deve refletir a personalidade de um personagem fictício personificada para inferir o personalidade do criador dessa personagem é questionável. Enquanto cada autor tem um estilo único, os caracteres são ainda propositadamente pré-configurado. Uma personalidade autor pode, no entanto, ser inferido a partir textos de não-ficção do autor, transcrições de entrevistas, ou outras partes de trabalho, como apresentações, prólogos, confirmações, ou dedicações.

### Interpretando resultados de texto gravado por vários indivíduos
{: #multipleindividuals}

Um uso comum do serviço {{site.data.keyword.personalityinsightsshort}} é analisar os seguidores de uma marca ou de uma empresa. Seguidores são definidos como pessoas que seguem uma empresa no Twitter ou em uma página no Facebook público. Neste cenário, o objetivo é derivar a personalidade geral de seguidores de uma empresa. Um método preferencial é coletar texto suficiente que é gravado por membros de um grupo para calcular a personalidade de cada membro individual, e depois o cluster personalidades em grupos distintos. Esses grupos representam personagens com características de personalidade distintos que seguem o empresa.

Se o texto insuficiente está disponível a partir dos membros de um grupo, o texto que é escrito por muitos membros podem ser combinados e analisados para produzir um retrato da personalidade média ou composto para o grupo como um todo. Essa abordagem pode produzir uma indicação de qualidades dominante do grupo, mas a precisão desse método diminui com a diversidade da população. Tome cuidado ao interpretar retratos que são obtidos a partir agregar o texto de vários indivíduos. {{site.data.keyword.IBM_notm}}de trabalho nesta área ainda está em seus estágios iniciais; {{site.data.keyword.IBM_notm}} relatarão suas descobertas como ele descobre resultados convincentes.

## Inferindo personalidade do texto gerado
{: #inferring}

Analisando o texto que é gerado pelo serviço de transcrição ou de tradução pode impactar a confiabilidade dos resultados do serviço. {{site.data.keyword.personalityinsightsshort}} As seções a seguir discutem os efeitos da personalidade deduzindo do texto gerado:

-   [Inferindo personalidade do discurso transcrições](#transcription)
-   [Inferindo personalidade de tradução de texto](#translation)

### Inferindo a personalidade de transcrições do discurso
{: #transcription}

Mecanismos de transcrição Discurso, como o {{site.data.keyword.IBM_notm}} {{site.data.keyword.speechtotextshort}} serviço, gerar texto escrito de palavras faladas. Porque mecanismos de transcrição diferentes têm diferentes intervalos de precisão, os clientes que transcrever discurso texto para uso como entrada para o {{site.data.keyword.personalityinsightsshort}} serviço precisam estar ciente de que os resultados variam amplamente dependendo do desempenho do motor. Especificamente, o {{site.data.keyword.IBM_notm}} avisa clientes e parceiros de negócios para determinar a qualidade da transcrição contra dois tipos de erros:

-   *Desmatricular:* Uma palavra falada é omitido da transcrição.
-   *Substituição:* uma palavra falada é transcrita incorretamente.

A substituição pode ser uma questão mais séria porque pode introduzir palavras que não foram faladas, mas que combinam com palavras usadas para determinar a personalidade. Antes de usar o texto transcrito, considere manualmente corrigir o texto de um corpus de teste e contando os erros que você encontra. Em seguida, compare os resultados do texto gerado automaticamente com a versão corrigido manualmente para determinar a variação nos resultados devido a erros de transcrição.

### Inferindo personalidade do texto traduzido
{: #translation}

Os serviços de tradução de idioma traduzir texto que é gravado em um idioma para outro idioma. Assim como transcrição discurso, a questão surge se o texto traduzido pode ser usado como entrada para o serviço {{site.data.keyword.personalityinsightsshort}} . {{site.data.keyword.IBM_notm}} não recomenda que você usa texto que é obtido de serviços de tradução como entrada para o serviço {{site.data.keyword.personalityinsightsshort}} . Dependendo do serviço de tradução, os resultados da conversão e a inferência personalidade podem variar amplamente. Palavras, seus sentidos, e sensibilidades culturais tendem a ficar perdido na tradução, produzindo resultados inválidos.

{{site.data.keyword.IBM_notm}} recomenda que você usa como entrada somente texto que é gravado em idiomas nos quais o {{site.data.keyword.personalityinsightsshort}} serviço está ativado. Versões do Idioma ativado para o serviço de análise do texto de entrada em seu idioma nativo, use dicionários de idioma nativo para identificar características de personalidade, e modelos de uso que são calibradas para o idioma nativo para produzir resultados estatísticos. Se você deve analisar texto traduzido, {{site.data.keyword.IBM_notm}} recomenda que você primeiro converter manualmente algumas amostras de texto usando os serviços de um especialista em linguagem humana. Você pode então comparar os resultados que o {{site.data.keyword.personalityinsightsshort}} serviço obtém de ambos manualmente e automaticamente o texto traduzido para entender a variação nos resultados.

{{site.data.keyword.IBM_notm}} continuará a incluir mais idiomas como aumentos de demanda de negócios. A {{site.data.keyword.IBM_notm}} entende que o serviço{{site.data.keyword.personalityinsightsshort}} pode não suportar seu idioma nativo rápido o suficiente para seus propósitos. {{site.data.keyword.IBM_notm}} é conduzir testes para comparar resultados que são obtidos a partir de ativação de idioma nativo com resultados obtidos de serviços de tradução de idioma e relatará suas conclusões à medida que eles se tornam disponíveis.

## Usando retratos de personalidade para aplicativos específicos
{: #applying}

O {{site.data.keyword.personalityinsightsshort}} serviço pode ser aplicado a inúmeros casos de uso. As seções a seguir descrevem o uso de retratos de personalidades para alguns propósitos específicos:

-   [Correspondência indivíduos](#matching)
-   [Monitoramento e prever saúde mental](#mentalhealth)
-   [Monitorando radicais e desonestos elementos através de mídia social](#monitoring)

### Correspondendo pessoas
{: #matching}

Fazer uma boa correspondência entre as pessoas pode melhorar a interação e os resultados nos relacionamentos. Isso é verdadeiro para construção de equipe dentro de uma empresa e de interação com os clientes em uma ampla variedade de indústrias. Em um estudo de correspondência médico-paciente, os pesquisadores descobriram que os pacientes preferem médicos que são semelhantes a si. Efetivamente correspondentes médicos e pacientes constrói confiança e incentiva comunicação, que pode melhorar a conformidade e resultar em mais tratamento bem-sucedido ([Godager, 2012](/docs/services/personality-insights/references.html#godager2012)).

Personalidade também influencia as preferências interação entre profissionais e clientes. Por exemplo, pacientes com um alto grau de consciência e abertura preferem estar ativamente envolvido na decisão de seu curso de tratamento. Pacientes com altos níveis de agradam ou neuroticism prefiro que os médicos a liderança em tomar decisões importantes de saúde ([Flynn &amp; Smith, 2007](/docs/services/personality-insights/references.html#flynn2007)).

### Monitorando e prever saúde mental
{: #mentalhealth}

{{site.data.keyword.IBM_notm}} acredita que o diagnóstico da doença é melhor executada por um profissional médico treinado. Pode ser possível detectar alguns sinais de status mental dos indivíduos de sua palavra de uso. O {{site.data.keyword.IBM_notm}} fez nenhuma investigação neste espaço para realizar estudos verdade solo ou para explorar a possibilidade de estabelecer uma base científica para esse trabalho.

Os clientes e parceiros de negócios que estão interessados em buscar uso do {{site.data.keyword.personalityinsightsshort}} serviço para diagnóstico de saúde mental são bem-vindos para projetar e conduzir experimentos verdade solo para casos de uso como. A pesquisa ativa e contínua nesta área inclui um trabalho que relaciona a personalidade com os resultados de saúde ([Israel et al., 2014](/docs/services/personality-insights/references.html#israel2014)) e que visa prever o pós-parto e outras formas de depressão por meio das mídias sociais ([De Choudhury et al., 2013a](/docs/services/personality-insights/references.html#dechoudhury2013a) e [De Choudhury et al., 2013b](/docs/services/personality-insights/references.html#dechoudhury2013b)).

### Monitorando radical e elementos suspeitos através de redes sociais
{: #monitoring}

As agências governamentais em todo o mundo estão constantemente procurando por maneiras de detectar sinais iniciais da radicalização de indivíduos ou grupos de indivíduos via canais de mídia social. Inferindo personalidade de escrever " indivíduos é um aplicativo tradicional do {{site.data.keyword.personalityinsightsshort}} serviço. Então vem como nenhuma surpresa que usar o serviço para inferir elementos radicais e desonestos por meio de mídia social é um caso de uso viável. Inferências Confiável requerem não apenas características da personalidade, mas uma série de outros atributos, como sexo, idade, e geografia. {{site.data.keyword.IBM_notm}} não fez quaisquer estudos para validar ou invalidar este caso de uso. Clientes e parceiros de negócios são bem-vindos para realizar estudos para explorar esse caso de uso com base em seus objetivos e requisitos específicos.

## Não uma pessoa de personalidade mudar ao longo do tempo?
{: #evolve}

A personalidade de uma pessoa se desenvolvem ao longo do tempo? Se sim, como muitas vezes se o {{site.data.keyword.personalityinsightsshort}} serviço seja usado para indicar a personalidade de uma pessoa? Diferentes estudos relatar provas para e contra a teoria de que a personalidade de uma pessoa estabilizar em idade adulta. Em seu trabalho sobre 1890 seminal medindo a estabilidade da personalidade, *The Principles of Psychology*, psicólogo de Harvard William James observou que "Na maioria de nós, pelo aos trinta, o personagem tem configurado como gesso, e nunca vai amolecer novamente." Mas estudos mais recente relatório que personalidade não evoluem com o tempo.

-   [Helson et al. (2002)](/docs/services/personality-insights/references.html#helson2002) relatório que "a ideia de que mudanças de personalidade é mais pronunciada antes de 30 anos e depois atinge um platô não recebeu apoio." Os autores realizaram um estudo longitudinal em duas coortes em um período de 40 anos. Eles observe que período de vida e clima social são fatores importantes na mudança de personalidade nos últimos anos adultos. Eles comentam que "As pontuações de dominância e de independência atingiram um pico na meia idade de ambas as coortes, e as pontuações em Responsabilidade foram mais baixas durante os anos de pico da cultura do individualismo."
-   [Scollon e seinen (2006)](/docs/services/personality-insights/references.html#scollon2006) estabelecido para examinar as diferenças individuais em troca de extroversão, neuroticism e trabalho e satisfação relacionamento ao longo do tempo. Os autores observe que o aumento de trabalho e satisfação relacionamento foi associado com reduções no neuroticism e aumenta em extroversão ao longo do tempo.
-   [Roberts e Mroczek (2008)](/docs/services/personality-insights/references.html#roberts2008) comentário que a evidência existe para "mudança significa nível em traços de personalidade, bem como para diferenças individuais em troca pela vida." Os autores observe que as pessoas mostram um aumento auto-confiança, calor, auto-controle, e estabilidade emocional com a idade. Essas mudanças predominantes na idade adulta jovem (com idades entre 20 e 40). Além disso, altere que nível em características de personalidade ocorre na idade média e velhos, mostrando que as características de personalidade pode mudar em qualquer idade.

Com base nestes estudos, {{site.data.keyword.IBM_notm}} recomenda que os usuários do {{site.data.keyword.personalityinsightsshort}} serviço sempre trabalhar com os dados mais recentes e com dados disponíveis tanto quanto possível. {{site.data.keyword.IBM_notm}} ainda recomenda que os usuários atualizar retratos personalidade em intervalos regulares para capturar " indivíduos evoluindo personalidades. Embora o {{site.data.keyword.IBM_notm}} tende a acreditar que a personalidade se desenvolve dentro dos limites determinados, não realizou estudos para examinar os superior e inferior fronteiras desta evolução.

Pode-se perguntar como regularmente para atualizar os retratos personalidade de indivíduos. {{site.data.keyword.IBM_notm}}orientação é procurar a disponibilidade de novos dados e texto de um indivíduo específico. Se um indivíduo criado uma quantidade substancial de texto novo desde sua personalidade retrato foi obtido, ele pode valer atualizar o retrato. Essa abordagem captura a natureza evolutiva da personalidade, quando alguém escolhe aceitar que a personalidade evolui e concede ao serviço {{site.data.keyword.personalityinsightsshort}} o benefício de trabalhar com mais palavras, o que, por sua vez, pode aumentar a precisão dos resultados do serviço.
