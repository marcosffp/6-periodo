# Processo de Desenvolvimento de Software

Prof. Diego Augusto Barros — Engenharia e Tecnologia

## 📖 Processo de Engenharia (conceito geral) e Processo de Software

**O que é / Definição para prova:** Antes de falar de software, o material define processo de engenharia de forma ampla: **um processo de engenharia consiste em um conjunto de atividades inter-relacionadas que transformam um ou mais insumos em produtos, enquanto consomem recursos para realizar essa transformação**. Essa ideia vem de disciplinas tradicionais como elétrica, mecânica, civil e química, que frequentemente envolvem a transformação de energia e entidades físicas de uma forma para outra — como uma represa hidrelétrica que converte energia potencial em energia elétrica, ou uma refinaria que transforma petróleo bruto em gasolina. Os **processos de engenharia de software** seguem essa mesma lógica, mas relacionados às atividades realizadas por engenheiros de software para **desenvolver, manter e operar software** — como requisitos, design, construção, teste e gerenciamento de configuração. Para facilitar a leitura, o material chama "Processo de Engenharia de Software" simplesmente de **Processo de Software**, definido de forma direta como: **um conjunto de atividades relacionadas que levam à produção de um produto de software**.

⚠️ **Pegadinha:** **Processo de software refere-se a atividades de trabalho** (o "como se faz" o software), **não ao processo de execução do software já implementado** (ou seja, não é sobre o software rodando, e sim sobre como ele foi construído).

**Como funciona / Características:** As atividades do Processo de Software podem envolver o desenvolvimento de um sistema de três formas:
1. **A partir do zero**, em uma linguagem padrão de programação como Java ou C;
2. Através da **extensão e modificação** de sistemas existentes;
3. Por meio da **configuração e integração de softwares** de prateleira ou componentes do sistema.

🧠 **Memorizar:** Processo de engenharia = insumo → transformação (consumindo recursos) → produto · Processo de software = atividades de trabalho (não é o software rodando).

## 📖 Objetivos do Processo de Software

**O que é / Definição para prova:** O material lista os objetivos que justificam a existência formal de um processo de software: **facilitar a compreensão humana, comunicação e coordenação**; **auxiliar na gestão de projetos de software**; **medir e melhorar a qualidade dos produtos de software de maneira eficiente**; **apoiar a melhoria de processos**; e **fornecer uma base para o suporte automatizado da execução de processos**.

🧠 **Memorizar:** Comunicação · Gestão de projeto · Qualidade · Melhoria de processo · Automação.

## 📖 Elementos de um Processo de Software

**O que é / Definição para prova:** Um processo de software é formalmente descrito como **um conjunto de atividades e tarefas inter-relacionadas que transformam produtos de trabalho de entrada em produtos de trabalho de saída**. O modelo visual do material representa esse fluxo assim: uma **Entrada** passa por um **Critério de Entrada Válido?** (se falso, retorna à entrada para ajuste; se verdadeiro, segue em frente); em seguida ocorre a etapa **Transforma**, composta por várias **Atividades**, cada uma subdividida em **Tarefas**; por fim, passa por um **Critério de Saída Válido?** (se falso, volta para a transformação; se verdadeiro, produz a **Saída**).

**Como funciona / Características:** A descrição completa de um processo de software pode incluir:
- **Entradas (inputs) necessárias** — que podem ser um **evento desencadeante** ou **a saída de outro processo** (ou seja, processos se encadeiam: a saída de um processo alimenta a entrada de outro);
- **Atividades de trabalho de transformação**;
- **As saídas (outputs) produzidas**;
- **Critérios de entrada e saída** — os **critérios de entrada devem ser satisfeitos antes que um processo possa começar**, e **todas as condições especificadas devem ser atendidas antes que um processo possa ser concluído com sucesso**, incluindo os critérios de aceitação para o produto e os produtos de trabalho de saída;
- **Tarefas** — as atividades de trabalho podem ser **subdivididas em tarefas, que são as unidades mais pequenas de trabalho sujeitas à responsabilidade de gestão** (ou seja, é o nível mais granular que um gestor efetivamente acompanha);
- **Subprocessos** — um processo de software pode também incluir subprocessos, que são processos completos (com sua própria entrada, transformação e saída) aninhados dentro de um processo maior.

**Exemplo:** o material ilustra o conceito de subprocesso com a **Validação de Requisitos**, que é um subprocesso do processo de Requisitos de Software. A validação de requisitos é o processo usado para determinar se os requisitos fornecerão uma base adequada para o desenvolvimento de software. Nesse subprocesso: as **entradas** geralmente são uma especificação de requisitos de software e os recursos necessários (pessoal, ferramentas de validação, tempo suficiente); as **tarefas da atividade** podem incluir revisões de requisitos, prototipagem e validação de modelos, envolvendo atribuições de trabalho para indivíduos e equipes; e a **saída** é tipicamente uma Especificação de Requisitos de Software Validada, que fornece entradas para os processos de design e teste de software. A validação de requisitos e outros subprocessos do processo de requisitos são frequentemente **intercalados e iterados** de várias maneiras, podendo ser **iniciados e encerrados várias vezes** durante o desenvolvimento ou modificação de software.

🧠 **Memorizar:** Entrada → critério de entrada → Transforma (Atividades → Tarefas) → critério de saída → Saída · Tarefa = menor unidade sujeita à gestão · Subprocesso = processo completo dentro de outro processo.

## 📖 Definição Completa de um Processo de Software (elementos adicionais)

**O que é / Definição para prova:** Além de entradas, atividades e saídas, a definição completa de um processo de software também pode incluir cinco outros elementos: **os papéis e competências**; **suporte de TI**; **técnicas e ferramentas de Engenharia de Software**; **ambiente de trabalho** necessário para realizar o processo; e **abordagens e medidas (Indicadores-Chave de Desempenho/KPIs)** usados para determinar a eficiência e eficácia da execução do processo. As descrições do processo também podem incluir três aspectos adicionais: **Produtos**, **Papéis** e **Pré e pós-condições**. **Produtos** são **os resultados de uma das atividades do processo** (por exemplo, o resultado da atividade de projeto de arquitetura pode ser um modelo da arquitetura de software). **Papéis** refletem **as responsabilidades das pessoas envolvidas no processo** (por exemplo, Gerente de Projeto, Gerente de Configuração, Programador). **Pré e pós-condições** são **declarações verdadeiras antes e depois de uma atividade do processo ou da produção de um produto** — por exemplo, antes do projeto de arquitetura ser iniciado, pode haver uma **pré-condição**: todos os requisitos tenham sido aprovados pelo cliente; e uma **pós-condição**: os modelos UML que descrevem a arquitetura tenham sido revisados.

🧠 **Memorizar:** Produtos = resultados · Papéis = responsabilidades das pessoas · Pré-condição = verdade antes · Pós-condição = verdade depois.

## 📖 Não Existe um Processo Ideal

**O que é / Definição para prova:** Um ponto conceitual importante reforçado no material: **não existe um melhor processo de software ou conjunto de processos de software**, nem **um processo ou conjunto de processos ideais**. Por isso, **os processos de software devem ser selecionados, adaptados e aplicados conforme apropriado para cada projeto e contexto organizacional** — ou seja, a escolha do processo depende das características específicas do projeto (tamanho, complexidade, clareza dos requisitos, equipe disponível etc.), não existindo uma receita universal.

🧠 **Memorizar:** Processo ideal não existe → selecionar, adaptar e aplicar conforme o contexto.

## 📖 As 4 Atividades Fundamentais do Processo de Software

**O que é / Definição para prova:** O material apresenta quatro atividades genéricas que, de alguma forma, **fazem parte de todos os processos de software** — são atividades fundamentais em qualquer abordagem de engenharia de software. **Especificação**: **a funcionalidade do software e as restrições a seu funcionamento devem ser definidas**. **Projeto e Implementação**: **o software deve ser produzido para atender às especificações**. **Validação**: **o software deve ser validado para garantir que atenda às demandas do cliente**. **Evolução**: **o software deve evoluir para atender às necessidades de mudança dos clientes**. Na prática, essas quatro atividades são complexas em si mesmas e incluem subatividades, como validação de requisitos, projeto de arquitetura e testes unitários (entre outras). Existem também atividades que **dão apoio ao processo**, com destaque para **documentação** e **gerenciamento de configuração de software**.

| Atividade | O que garante |
|---|---|
| Especificação | Funcionalidade e restrições definidas |
| Projeto e Implementação | Software produzido conforme especificação |
| Validação | Atende às demandas do cliente |
| Evolução | Acompanha mudanças de necessidade do cliente |

🧠 **Memorizar:** Especificação → Projeto/Implementação → Validação → Evolução (as 4 atividades fundamentais, presentes em qualquer processo).

## 📖 Atividades de Apoio ao Processo de Software

**O que é / Definição para prova:** Além das quatro atividades fundamentais, o material lista oito **atividades de apoio**, que sustentam a execução do processo principal mas não produzem diretamente o software em si: **Controle e Acompanhamento do Projeto de Software** — **permite à equipe de software avaliar o progresso em relação ao plano do projeto e tomar as medidas necessárias para manter o cronograma**; **Gerência de Riscos** — **avalia os riscos que podem afetar o resultado do projeto ou a qualidade do produto**; **Garantia de Qualidade de Software** — **define e realiza atividades necessárias para garantir a qualidade do software**; **Revisões Técnicas** — **avaliam os produtos de trabalho de engenharia de software para descobrir e corrigir erros antes que se propaguem para a próxima atividade**; **Medição** — **define e coleta medidas de processo, projeto e produto que ajudam a equipe a fornecer software que atenda às necessidades dos interessados**, podendo ser usada em conjunto com todas as outras atividades do framework; **Gerência de Configuração de Software** — **gerencia os efeitos da mudança ao longo do processo de software**; **Gestão de Reutilização** — **define critérios para a reutilização de produtos de trabalho (incluindo componentes de software) e estabelece mecanismos para alcançar componentes reutilizáveis**; e **Preparação e Produção de Artefatos de Software** — **engloba as atividades necessárias para criar produtos de trabalho, como modelos, documentos, registros, formulários e listas**.

🧠 **Memorizar:** Controle/Acompanhamento (cronograma) · Riscos · Qualidade · Revisões Técnicas (achar erro cedo) · Medição · Configuração (gerenciar mudança) · Reutilização · Produção de Artefatos.

## 📖 O Framework de Processo

**O que é / Definição para prova:** O Framework de Processo é definido como um **arcabouço (Framework) genérico que estabelece a base para o processo completo de engenharia de software**. Ele **identifica um conjunto limitado de atividades estruturais aplicáveis a todos os projetos de software, independentemente do tamanho ou complexidade**, abordando aspectos comuns a diferentes projetos. Engloba **cinco atividades principais**: **Comunicação** — antes do início do trabalho técnico, é essencial comunicar e colaborar com o cliente e outros interessados; o objetivo é compreender os objetivos do projeto e reunir requisitos para definir as características e funções do software. **Planejamento** — a atividade de planejamento cria um "mapa" para orientar a equipe durante a jornada do projeto de software; o plano do projeto define tarefas técnicas, riscos, recursos necessários, produtos de trabalho e cronograma. **Modelagem** — assim como em outras áreas profissionais, os engenheiros de software utilizam modelos (semelhantes a esboços) para compreender os requisitos e o design do software, ajudando a entender arquitetura, partes constituintes e detalhes do problema. **Construção** — envolve a geração de código (manual ou automatizada) e os testes necessários para identificar erros no código; é a etapa em que o que foi projetado é efetivamente construído, dando vida ao software. **Implantação** — a entrega do software, seja como uma entidade completa ou como um incremento parcial, é realizada ao cliente, que avalia o produto entregue e fornece feedback com base na avaliação.

**Como funciona / Características:** Em muitos projetos de software, as atividades do framework **são aplicadas iterativamente durante o progresso do projeto**, ou seja, se repetem ao longo de várias iterações. **Cada iteração gera um incremento de software**, oferecendo aos interessados um subconjunto das características e funcionalidades globais do software. **À medida que cada incremento é produzido, o software se torna mais completo**.

🧠 **Memorizar:** Comunicação → Planejamento → Modelagem → Construção → Implantação (as 5 atividades do framework, aplicadas de forma iterativa e incremental).

## 📖 Modelo de Processo de Software

**O que é / Definição para prova:** **Um modelo de processo de software é uma representação simplificada de um processo de software.** Cada modelo representa uma **perspectiva particular** de um processo e, portanto, fornece **informações parciais** sobre ele — por exemplo, um modelo de atividade do processo pode mostrar as atividades e sua sequência, mas não mostrar os papéis das pessoas envolvidas. Os modelos de processo foram originalmente propostos para **trazer ordem ao caos** do desenvolvimento de software. A história indicou que esses modelos **trouxeram uma quantidade útil de estrutura para o trabalho de engenharia de software** e **forneceram um mapa eficaz para equipes de software**.

Os **modelos de software prescritivos (tradicionais)** apresentados são quatro: **Modelo Cascata**, **Modelo de Processo de Prototipação**, **Modelo de Processo Evolucionário (Espiral)** e **Modelo de Processo Unificado**.

🧠 **Memorizar:** Modelo de processo = representação simplificada e parcial (uma perspectiva) do processo real.

## 📖 O Modelo em Cascata

**O que é / Definição para prova:** O Modelo em Cascata foi **proposto por Winston Royce em 1970** e foi **o primeiro modelo do processo de desenvolvimento de software a ser publicado**, derivado de processos mais gerais da engenharia de sistemas. É um exemplo de **processo dirigido a planos**: em princípio, é preciso **planejar e programar todas as atividades do processo antes de começar a trabalhar nelas**. O modelo segue as cinco atividades do framework em sequência linear: **1. Comunicação** (início do projeto, levantamento de requisitos) → **2. Planejamento** (estimativas, cronogramas, acompanhamento) → **3. Modelagem** (análise, projeto) → **4. Construção** (código, testes) → **5. Implantação** (entrega, suporte, feedback). Por causa do **encadeamento entre uma fase e outra** (cada fase "cai" na próxima, como uma cascata), esse modelo é conhecido como Modelo em Cascata, ou **ciclo de vida de software**. É considerado **o paradigma mais antigo para engenharia de software**. O modelo original em cascata **previa "ciclos de feedback"** entre as fases, mas, na prática, **a grande maioria das organizações que aplicam esse modelo o tratam como se fosse estritamente linear** (sem retorno entre fases).

**Como funciona / Características (problemas do modelo):**
- **Projetos reais raramente seguem o fluxo de trabalho sequencial** proposto pelo modelo.
- Muitas vezes, é **difícil para o cliente declarar todas as exigências explicitamente** no início da maioria dos projetos.
- O cliente deve ter **paciência**, pois uma versão funcional do(s) programa(s) **não estará disponível até mais tarde** no período do projeto.
- **Grandes equívocos podem não ser detectados** até que o programa funcional seja revisado (ou seja, erros de entendimento só aparecem tarde, quando já é caro corrigir).

⚠️ **Pegadinha:** As críticas a este modelo incomodaram até mesmo aos defensores mais fervorosos, gerando questionamentos sobre sua eficácia. Hoje, o trabalho com software tem um **ritmo acelerado** e está sujeito a um **fluxo contínuo de mudanças** em características, funções e conteúdo de informações — por isso, **o Modelo em Cascata frequentemente é inadequado** para esse tipo de trabalho (não lida bem com mudanças, pois exige planejamento completo antecipado).

🧠 **Memorizar:** Royce, 1970, primeiro modelo publicado · Sequencial/linear (dirigido a planos) · 5 fases em cascata · Problema central: não se adapta a mudanças, testa só no final.

## 📖 Modelo de Processo de Prototipação

**O que é / Definição para prova:** Neste modelo, as cinco atividades do framework (Comunicação, Planejamento, Modelagem, Construção, Implantação) são organizadas em um **ciclo** centrado na produção de protótipos, em vez de uma sequência linear única. **A prototipagem fornece uma manifestação concreta de uma ideia**, seja um produto novo ou uma modificação de um já existente, e **permite que os designers comuniquem suas ideias e que os usuários as experimentem**. Um **protótipo** é definido como **uma manifestação de um design que permite às partes interessadas (Stakeholders) interagir com ele e explorar sua adequação**.

**Como funciona / Características:** Nos **estágios iniciais** do desenvolvimento, os protótipos podem ser feitos de **papel, papelão ou componentes prontos** reunidos apenas para permitir a avaliação. **À medida que o projeto avança**, eles se tornam **mais polidos, adaptados e robustos** para se parecerem com o produto final. Um protótipo de software pode ser usado no processo de desenvolvimento para ajudar a **antecipar as mudanças que podem ser requisitadas**, sendo aplicado principalmente em dois contextos: **1. Engenharia de Requisitos** — ajudar na elicitação e validação de requisitos de sistema; **2. Projeto de Sistema** — estudar soluções específicas do software e apoiar o projeto de interface de usuário.

🧠 **Memorizar:** Protótipo = manifestação concreta de uma ideia (papel → digital, cada vez mais próximo do produto final) · Usos: elicitar/validar requisitos e apoiar projeto de interface.

## 📖 Modelo de Processo Evolucionário e Modelo Espiral

**O que é / Definição para prova:** O Modelo de Processo Evolucionário organiza as cinco atividades do framework em uma estrutura **espiral**, partindo de um ponto de **início** central e expandindo-se em ciclos concêntricos. O **Modelo Espiral** é a implementação mais conhecida dessa ideia, **originalmente proposto por Barry Boehm em 1988**. **O modelo espiral é um modelo evolutivo de processo de software que combina: 1) a natureza iterativa da prototipagem; 2) com os aspectos controlados e sistemáticos do modelo em cascata.** Ele **oferece o potencial para o desenvolvimento rápido de versões cada vez mais completas do software**.

**Como funciona / Características:** Usando o modelo espiral, **o software é desenvolvido em uma série de lançamentos evolutivos**. **Durante as iterações iniciais**, o lançamento pode ser um **modelo ou protótipo**; **durante iterações posteriores, versões cada vez mais completas do sistema desenvolvido são produzidas**. **Um modelo espiral é dividido em um conjunto de atividades de estrutura definidas pela equipe de engenharia de software** — cada "volta" da espiral passa por etapas como determinar objetivos/alternativas/restrições, análise de risco, desenvolvimento de protótipos/simulações e planejamento da próxima fase, revisitando essas etapas em um nível cada vez mais detalhado a cada iteração.

🧠 **Memorizar:** Boehm, 1988 · Combina prototipagem (iterativo) + cascata (controlado/sistemático) · Cada volta da espiral = versão mais completa (lançamentos evolutivos).

## 📖 O Processo Unificado

**O que é / Definição para prova:** O Processo Unificado organiza as cinco atividades do framework em um **ciclo contínuo** (Comunicação → Planejamento → Modelagem → Construção → Implantação), produzindo a cada volta um **incremento do software** que evolui em direção a uma **versão de produção**. Ele foi criado para **aproveitar as melhores características e elementos dos modelos tradicionais de processo de software**, mas **caracterizá-los de uma maneira que implementa muitos dos melhores princípios do desenvolvimento ágil de software**. O Processo Unificado reconhece **a importância da comunicação com o cliente** e utiliza **métodos simplificados para descrever a visão do cliente sobre um sistema** (por exemplo, Casos de Uso). Ele também **enfatiza o papel crucial da arquitetura de software**, ajudando o arquiteto a focar em objetivos como **compreensibilidade** e **confiabilidade** para futuras alterações e reutilização. A **Linguagem de Modelagem Unificada (UML)** foi desenvolvida para apoiar o trabalho do Processo Unificado.

**Como funciona / Características:** Sugere um fluxo de processo **iterativo e incremental**, proporcionando uma **sensação evolutiva**, sendo considerado essencial no desenvolvimento moderno de software. Ele se organiza em quatro **fases** (diferentes das cinco atividades do framework, embora relacionadas a elas): **1. Concepção** — atingir o consenso entre todos os investidores sobre os objetivos do ciclo de vida do projeto; **2. Elaboração** — estabelecer a estrutura fundamental da arquitetura do sistema, visando proporcionar uma base sólida para a execução da fase de construção; **3. Construção** — esclarecer os requisitos restantes e concluir o desenvolvimento do sistema com base na arquitetura definida; **4. Transição** — assegurar que o software esteja disponível a seus usuários.

⚠️ **Pegadinha:** Não confundir as **fases do Processo Unificado** (Concepção, Elaboração, Construção, Transição) com as **cinco atividades do Framework de Processo** (Comunicação, Planejamento, Modelagem, Construção, Implantação) — são organizações diferentes, embora a fase "Construção" apareça em ambas com sentidos próximos.

🧠 **Memorizar:** UP = melhor dos modelos tradicionais + princípios ágeis · UML apoia o UP · Fases: Concepção → Elaboração → Construção → Transição · Iterativo e incremental.

## 📖 Comparação entre os Modelos de Processo

**O que é / Definição para prova:** O material fecha a comparação dos quatro modelos prescritivos com uma tabela de prós e contras, útil para decidir qual modelo se encaixa em cada contexto de projeto:

| Modelo | Prós | Contras |
|---|---|---|
| **Cascata** | Fácil de entender e planejar; funciona para projetos pequenos e bem compreendidos; a análise e o teste são simples e diretos | Não se adapta a mudanças; o teste ocorre nas fases finais do processo; a aprovação do cliente vem no final |
| **Prototipação** | O impacto das alterações aos requisitos é reduzido; o cliente se envolve bastante e desde o início; funciona bem para projetos pequenos; a probabilidade de rejeição do produto é reduzida | O envolvimento do cliente pode causar atrasos; pode haver a tentação de "embalar" o protótipo (entregar o protótipo como se fosse o produto final); desperdiça-se trabalho em um protótipo descartável; é difícil de planejar e gerenciar |
| **Espiral** | Há envolvimento contínuo dos clientes; os riscos de desenvolvimento são gerenciados; é apropriado para modelos grandes e complexos; funciona bem para artefatos extensíveis | Falhas de análise de risco podem fadar o projeto ao fracasso; o projeto pode ser difícil de gerenciar; exige uma equipe de desenvolvimento especializada |
| **Unificado** | A documentação de alta qualidade é enfatizada; há envolvimento contínuo dos clientes; adapta-se a alterações aos requisitos; funciona bem para projetos de manutenção | Os casos de uso nem sempre são precisos; a integração de incrementos de software é complicada; a sobreposição das fases pode causar problemas; exige uma equipe de desenvolvimento especializada |

🧠 **Memorizar:** Cascata = simples mas rígido · Prototipação = envolve cliente cedo mas pode virar retrabalho/tentação de "embalar" o protótipo · Espiral = gerencia risco mas exige especialistas · Unificado = documentação boa + ágil, mas integração complicada.

---

## 📚 Resumão final

- **Processo de engenharia/software**: atividades relacionadas que transformam insumos em produtos, consumindo recursos; processo de software = atividades de trabalho, não o software rodando.
- **Objetivos do processo**: comunicação, gestão de projeto, qualidade, melhoria de processo, suporte automatizado.
- **Elementos do processo**: entrada → critério de entrada → atividades/tarefas (transformação) → critério de saída → saída; pode ter subprocessos (ex.: validação de requisitos).
- **Definição completa**: além de entrada/atividade/saída, inclui papéis, suporte de TI, técnicas/ferramentas, ambiente, KPIs, produtos, papéis e pré/pós-condições.
- **Não existe processo ideal**: deve ser selecionado, adaptado e aplicado ao contexto de cada projeto.
- **4 atividades fundamentais** (presentes em todo processo): Especificação, Projeto e Implementação, Validação, Evolução.
- **8 atividades de apoio**: Controle/Acompanhamento, Gerência de Riscos, Garantia de Qualidade, Revisões Técnicas, Medição, Gerência de Configuração, Gestão de Reutilização, Preparação e Produção de Artefatos.
- **Framework de processo**: 5 atividades genéricas e iterativas — Comunicação, Planejamento, Modelagem, Construção, Implantação — geram incrementos de software.
- **Modelo de processo**: representação simplificada/parcial de um processo real.
- **Cascata** (Royce, 1970): sequencial, dirigido a planos, não se adapta a mudanças.
- **Prototipação**: constrói protótipos (papel → digital) para antecipar mudanças e validar requisitos/interface.
- **Espiral** (Boehm, 1988): combina prototipagem + cascata, iterativo com foco em análise de risco.
- **Unificado**: usa UML, fases Concepção/Elaboração/Construção/Transição, iterativo, incremental, alinhado a princípios ágeis.
- **Comparação**: cada modelo tem prós/contras específicos (ver tabela) — não há um "melhor" universal.

## ⚠️ Pontos que podem cair na prova

- Definição exata de processo de software e a distinção "atividades de trabalho" vs. "execução do software" — ver tópico Processo de Engenharia.
- Elementos do processo (entrada, critérios de entrada/saída, atividade, tarefa, subprocesso) e o exemplo de validação de requisitos como subprocesso — ver tópico Elementos de um Processo de Software.
- As 4 atividades fundamentais (Especificação, Projeto e Implementação, Validação, Evolução) — memorizar nomes e definições exatas.
- As 8 atividades de apoio e suas definições — especialmente Gerência de Configuração e Gestão de Reutilização, que costumam ser confundidas.
- As 5 atividades do Framework de Processo (Comunicação, Planejamento, Modelagem, Construção, Implantação) e o caráter iterativo/incremental.
- Autor e ano do Modelo em Cascata (Winston Royce, 1970) e do Modelo Espiral (Barry Boehm, 1988).
- Problemas específicos do Modelo em Cascata (sequencial, difícil mudar requisitos, versão só ao final).
- O que o Modelo Espiral combina (prototipagem + cascata) e sua ênfase em análise de risco.
- Fases do Processo Unificado (Concepção, Elaboração, Construção, Transição) — não confundir com as atividades do framework.
- Tabela de prós e contras dos quatro modelos (Cascata, Prototipação, Espiral, Unificado).

## 📝 Perguntas para revisão

1. O que é um processo de engenharia de forma geral, e como isso se aplica ao processo de software?
2. Qual é a definição de "processo de software" dada no material, e qual é a pegadinha comum sobre esse termo?
3. Quais são os cinco objetivos do processo de software?
4. Descreva os elementos básicos de um processo de software usando o diagrama Entrada → Transforma → Saída.
5. O que são tarefas, dentro de uma atividade de um processo de software?
6. O que é um subprocesso? Use o exemplo de validação de requisitos para explicar.
7. Além de entradas, atividades e saídas, que outros cinco elementos podem compor a definição completa de um processo de software?
8. O que são Produtos, Papéis e Pré/Pós-condições na descrição de um processo?
9. Por que não existe um "melhor" processo de software?
10. Quais são as quatro atividades fundamentais presentes em todo processo de software? Defina cada uma.
11. Cite pelo menos quatro atividades de apoio ao processo de software e explique brevemente cada uma.
12. Quais são as cinco atividades do Framework de Processo, e por que elas são aplicadas iterativamente?
13. O que é um modelo de processo de software, e por que ele fornece apenas informações "parciais"?
14. Quem propôs o Modelo em Cascata e em que ano? Por que ele é chamado assim?
15. Quais são os principais problemas do Modelo em Cascata?
16. O que é um protótipo, segundo o material, e em quais dois contextos ele é usado no processo de software?
17. O que é o Modelo Espiral e o que ele combina? Quem o propôs e em que ano?
18. Quais são as quatro fases do Processo Unificado, e qual é o objetivo de cada uma?
19. Cite um prós e um contra de cada um dos quatro modelos de processo prescritivos (Cascata, Prototipação, Espiral, Unificado).

### Gabarito

1. Um processo de engenharia consiste em um conjunto de atividades inter-relacionadas que transformam um ou mais insumos em produtos, consumindo recursos para isso — como ocorre em disciplinas tradicionais (elétrica, mecânica, civil, química). O processo de software segue a mesma lógica, mas relacionado às atividades de engenheiros de software para desenvolver, manter e operar software (requisitos, design, construção, teste, gerenciamento de configuração etc.).
2. Processo de software é um conjunto de atividades relacionadas que levam à produção de um produto de software. A pegadinha é que ele se refere às atividades de trabalho (o processo de construir o software), não ao processo de execução do software já implementado.
3. Facilitar a compreensão humana, comunicação e coordenação; auxiliar na gestão de projetos de software; medir e melhorar a qualidade dos produtos de software; apoiar a melhoria de processos; e fornecer uma base para o suporte automatizado da execução de processos.
4. A Entrada passa por um critério de entrada válido (se não for válida, retorna para ajuste); em seguida ocorre a Transformação, composta por atividades (cada uma com suas tarefas); depois passa por um critério de saída válido (se não for válido, volta para a transformação); se válido, gera a Saída.
5. Tarefas são subdivisões das atividades de trabalho — são as unidades mais pequenas de trabalho sujeitas à responsabilidade de gestão, ou seja, o nível mais granular acompanhado por um gestor.
6. Subprocesso é um processo completo (com entrada, transformação e saída próprias) contido dentro de um processo maior. A validação de requisitos é um subprocesso do processo de requisitos de software: recebe como entrada a especificação de requisitos e recursos necessários, executa tarefas como revisões, prototipagem e validação de modelos, e produz como saída uma especificação de requisitos validada.
7. Os papéis e competências das pessoas envolvidas; suporte de TI; técnicas e ferramentas de Engenharia de Software; ambiente de trabalho necessário; e abordagens/medidas (KPIs) para determinar eficiência e eficácia da execução do processo.
8. Produtos são os resultados de uma das atividades do processo (ex.: um modelo de arquitetura gerado pela atividade de projeto de arquitetura). Papéis refletem as responsabilidades das pessoas envolvidas no processo (ex.: Gerente de Projeto, Programador). Pré-condições são declarações que devem ser verdadeiras antes de uma atividade começar, e pós-condições são declarações que devem ser verdadeiras depois que ela termina.
9. Porque diferentes projetos têm características e contextos organizacionais diferentes; por isso, os processos devem ser selecionados, adaptados e aplicados conforme apropriado para cada situação, e não existe uma solução universal.
10. Especificação (definir a funcionalidade do software e as restrições ao seu funcionamento), Projeto e Implementação (produzir o software para atender às especificações), Validação (validar o software para garantir que atenda às demandas do cliente) e Evolução (fazer o software evoluir para atender às necessidades de mudança dos clientes).
11. Exemplos: Controle e Acompanhamento do Projeto (avaliar progresso frente ao plano e manter o cronograma), Gerência de Riscos (avaliar riscos que podem afetar o projeto ou a qualidade), Garantia de Qualidade de Software (definir e realizar atividades que garantam a qualidade) e Revisões Técnicas (avaliar produtos de trabalho para descobrir e corrigir erros antes que se propaguem). Outras: Medição, Gerência de Configuração, Gestão de Reutilização, Preparação e Produção de Artefatos.
12. Comunicação, Planejamento, Modelagem, Construção e Implantação. Elas são aplicadas iterativamente porque, em muitos projetos, se repetem ao longo do progresso do projeto, cada iteração gerando um incremento de software que torna o produto cada vez mais completo.
13. É uma representação simplificada de um processo de software real. Fornece apenas informações parciais porque cada modelo representa uma perspectiva particular do processo — por exemplo, um modelo de atividade pode mostrar as atividades e sua sequência, mas não os papéis das pessoas envolvidas.
14. Foi proposto por Winston Royce em 1970, sendo o primeiro modelo de processo de desenvolvimento de software publicado. É chamado de "Cascata" por causa do encadeamento entre uma fase e outra, como uma cascata de água caindo de um nível para o próximo.
15. Projetos reais raramente seguem o fluxo sequencial proposto; é difícil para o cliente declarar todas as exigências explicitamente no início; o cliente precisa ter paciência, pois uma versão funcional só fica disponível mais tarde no projeto; e grandes equívocos podem não ser detectados até que o programa funcional seja revisado.
16. Um protótipo é uma manifestação de um design que permite às partes interessadas (stakeholders) interagir com ele e explorar sua adequação. É usado em dois contextos principais: na Engenharia de Requisitos, para ajudar na elicitação e validação de requisitos de sistema, e no Projeto de Sistema, para estudar soluções específicas do software e apoiar o projeto de interface de usuário.
17. O Modelo Espiral é um modelo evolutivo de processo de software que combina a natureza iterativa da prototipagem com os aspectos controlados e sistemáticos do modelo em cascata, oferecendo potencial para desenvolvimento rápido de versões cada vez mais completas do software. Foi originalmente proposto por Barry Boehm em 1988.
18. Concepção (atingir consenso entre todos os investidores sobre os objetivos do ciclo de vida do projeto), Elaboração (estabelecer a estrutura fundamental da arquitetura do sistema, dando base sólida à construção), Construção (esclarecer requisitos restantes e concluir o desenvolvimento com base na arquitetura definida) e Transição (assegurar que o software esteja disponível a seus usuários).
19. Cascata: prós — fácil de entender e planejar; contras — não se adapta a mudanças. Prototipação: prós — reduz o impacto de alterações aos requisitos; contras — pode haver tentação de "embalar" o protótipo em vez de refazer o desenvolvimento corretamente. Espiral: prós — gerencia os riscos de desenvolvimento; contras — falhas na análise de risco podem levar o projeto ao fracasso. Unificado: prós — enfatiza documentação de alta qualidade; contras — a integração de incrementos de software é complicada.
