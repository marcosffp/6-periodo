# Aula 2 — Conceitos Básicos (Medição e Experimentação em Eng. de Software)

## 📖 Relevância da medição

**O que é / Definição para prova:** Assim como Engenharia Civil, Elétrica e Mecânica não existiriam sem medição, a Engenharia de Software também depende dela — mas na prática, muitos projetos tratam medição como um "luxo" dispensável. Os principais sintomas dessa falha de cultura são: prometer requisitos não-funcionais (ex.: "o sistema será user-friendly, confiável, sustentável") sem definir objetivamente o que isso significa e como medir; não entender nem quantificar custos de projeto (design, codificação, testes); adotar novas ferramentas só pela promessa de inovação, sem avaliação científica e criteriosa; e aceitar argumentações sem evidência clara. Além disso, é comum não questionar a procedência dos dados medidos — de onde vieram, qual o processo de coleta, a margem de erro, a qualidade, a acurácia, o universo amostral e as referências de comparação.

⚠️ **Pegadinha:** a frase "você não pode gerenciar o que não consegue medir" é constantemente atribuída a **W. Edwards Deming**, mas ele defendeu quase o oposto. Em *The New Economics*, Deming escreveu que **"é errado supor que, se você não pode medir algo, não pode gerenciá-lo"** — chamando isso de um mito custoso — e reforçou que as figuras mais importantes para a gestão muitas vezes são desconhecidas e incognoscíveis (uma das "sete doenças mortais da gestão" seria gerenciar apenas por números visíveis). A lição de Deming não é abandonar a medição, mas usá-la com humildade, sabendo que nem tudo o que importa cabe em um indicador.

🧠 **Memorizar:** medição como "luxo" na prática × essencial na teoria; mito de Deming (ele disse o oposto do que é citado); procedência/qualidade do dado; alvo da medição pode ser Projeto, Produto, Processos ou Recursos.

## 📖 Objetivos da medição de software

**O que é / Definição para prova:** A medição existe para **prover feedback** em relação a um objetivo proposto — por isso, antes de definir o que medir, é preciso definir os objetivos que se deseja alcançar. Essa ideia é ilustrada pelo clássico diagrama de **sistema com feedback** (controle): o *Measuring element* mede o *Status* do sistema, compara com um *Set point* (valor desejado) e gera um *Error* que aciona um *Controller* e um *Effector*, que corrigem o sistema — ou seja, medir só faz sentido quando serve para comparar o estado atual com uma meta e guiar uma correção.

**Como funciona / Características:** Os dois principais grupos de *stakeholders* têm perguntas bem diferentes que a medição deveria responder:

- **Managers:** custo de cada processo (dá pra otimizar/minimizar?); produtividade e estruturação da equipe (senioridade, distribuição de conhecimento, rotatividade); qualidade do código sendo desenvolvido e alternativas de arquitetura; satisfação do usuário e histórico de entregas; onde e quando é possível melhorar (aprendizado, gestão do conhecimento).
- **Developers:** os requisitos são testáveis e de qualidade? Batem com o que foi implementado? Falhas são encontradas e previstas com que proporção? Os objetivos do produto e dos processos foram cumpridos? É possível prever o futuro (tendências do código) com base em dados históricos?

🧠 **Memorizar:** medição = feedback para um objetivo; diagrama de feedback (Set point vs Status → Error → Controller/Effector); Managers = custo/produtividade/qualidade/satisfação; Developers = testabilidade/falhas/cumprimento de objetivos.

## 📖 Goal-Question-Metric (GQM)

**O que é / Definição para prova:** O **GQM (Goal-Question-Metric)**, proposto por **Victor Basili** e colegas na Universidade de Maryland/NASA-SEL no final dos anos 1980, é o framework mais influente para transformar as perguntas de managers e developers em métricas de forma sistemática (e não por tentativa e erro). A ideia central, cobrável literalmente em prova: **"nunca colete uma métrica sem antes saber qual pergunta ela responde e a que objetivo essa pergunta serve."** O processo parte de um **objetivo (Goal)** de negócio, deriva **perguntas (Questions)** que indicam se o objetivo está sendo alcançado, e só então define as **métricas (Metrics)** que respondem a cada pergunta.

**Como funciona / Características:** O template do objetivo (Basili, Caldiera & Rombach, 1994) segue a estrutura:

> **Analisar** o [objeto de estudo] **com o propósito de** [propósito, ex.: caracterizar, avaliar, prever, melhorar] **com respeito a** [foco de qualidade, ex.: custo, confiabilidade, satisfação do usuário] **do ponto de vista de** [quem usa a informação, ex.: gerente, desenvolvedor] **no contexto de** [ambiente, projeto, organização].

**Exemplo:** *Goal:* melhorar a previsibilidade das entregas do time. → *Question 1:* quanto tempo, em média, uma tarefa leva do início ao fim? → *Metric:* tempo de ciclo (cycle time) por tarefa. → *Question 2:* o time está estimando de forma consistente? → *Metric:* desvio entre esforço estimado e esforço realizado. → *Question 3:* onde as tarefas ficam mais tempo paradas? → *Metric:* tempo médio por etapa do quadro Kanban. Esse exemplo mostra que cada métrica só existe porque responde a uma pergunta específica — nunca o contrário.

⚠️ **Pegadinha:** o GQM clássico conecta objetivos e métricas dentro de **um único nível** (um time, um projeto). A evolução moderna, o **GQM+Strategies** (Basili et al., 2010), estende o modelo criando uma cadeia de objetivos e métricas que atravessa **múltiplos níveis** — do time de desenvolvimento até a diretoria — tornando explícito *por que* cada métrica de equipe importa para o negócio estratégico da organização.

🧠 **Memorizar:** GQM = Basili, NASA-SEL, anos 1980; ordem Goal→Question→Metric; template "Analisar/propósito/respeito a/ponto de vista/contexto"; GQM+Strategies = multi-nível.

## 📖 Escopo das métricas de software (visão geral)

**O que é / Definição para prova:** A disciplina de medição de software cobre sete grandes frentes de atividade, cada uma com seu próprio conjunto de modelos e métricas: **estimativa de custo e esforço**, **coleta de dados**, **modelos e medidas de qualidade**, **modelos de confiabilidade**, **métricas de segurança**, **métricas estruturais e de complexidade**, **avaliação de maturidade de capacidade** e **gestão por métricas**. As seções seguintes detalham cada uma.

## 📖 Estimativa de custo e esforço

**O que é / Definição para prova:** Gerentes de projeto foram os principais motivadores do desenvolvimento de métricas de software, com o objetivo de prever custos ainda nas fases iniciais do ciclo de vida do projeto. Surgiram modelos como o **COCOMO II** (Boehm) e o modelo de **pontos de função de Albrecht**, que calculam o esforço como uma função pré-definida de variáveis como tamanho do software (linhas de código ou pontos de função), capacidade da equipe e nível de reutilização de componentes.

**Como funciona / Características (visão ágil):** Times ágeis geralmente não usam COCOMO ou pontos de função diretamente. Em vez disso:
- Estimam em unidades relativas, como **story points** (via *Planning Poker*), comparando o tamanho relativo das tarefas em vez do esforço absoluto;
- Usam a **velocidade (velocity)** do time — pontos entregues nos últimos sprints — para projetar entregas futuras;
- Reestimam continuamente, em vez de travar uma estimativa única no início do projeto.

⚠️ **Pegadinha:** o movimento minoritário porém influente **#NoEstimates** questiona a própria utilidade de estimar esforço, defendendo medir o **fluxo de trabalho real** (quantos itens terminam por semana) em vez de prever esforço antes de começar.

🧠 **Memorizar:** COCOMO II / pontos de função = modelos clássicos; story points + velocity = visão ágil; #NoEstimates = mede fluxo real, não estima.

## 📖 Coleta de dados

**O que é / Definição para prova:** A qualidade de um programa de medição depende diretamente da coleta cuidadosa de dados — desafio ainda maior em projetos diversos. Por isso, a coleta de dados virou uma disciplina própria, com especialistas focados em garantir definições claras das métricas, consistência no processo, completude e integridade dos dados. Esse processo precisa ser planejado e conduzido com atenção e sensibilidade.

**Como funciona / Características:** Existe uma cadeia de transformação — **Dados → Informações → Indicadores → Conhecimento → Inteligência** — que ocorre por meio de Organização, Relativização, Contextualização e Aprendizado, respectivamente. Uma metodologia complementar distingue dois conceitos:
- **Driver (Meio):** traduz indicadores em ações individualizadas; gerenciamento pelo **Esforço**.
- **Outcome (Fim):** depende dos drivers para se operacionalizar; gerenciamento pelo **Resultado**.

Também há uma diferença qualitativa entre Dados, Informações e Indicadores nas organizações: dados são disponíveis para manipulação no banco (abundantes, sem foco de gestão); informações são organizadas/já manipuladas em relatórios (visíveis através de softwares gerenciais); indicadores são parametrizados em fórmulas lineares e visíveis por regras de contagem, com foco no que é relevante para a gestão.

🧠 **Memorizar:** cadeia Dados→Informações→Indicadores→Conhecimento→Inteligência; Driver (esforço/meio) vs Outcome (resultado/fim).

## 📖 Modelos e medidas de qualidade

**O que é / Definição para prova:** Como a qualidade de software envolve diversos fatores, engenheiros desenvolveram modelos em **estrutura de árvore** que representam a interação entre eles: os ramos superiores contêm **fatores de qualidade de alto nível** (ex.: confiabilidade, usabilidade), cada um dividido em **critérios de nível inferior** (ex.: modularidade, compartilhamento de dados), mais fáceis de entender e medir. As **métricas** são aplicadas a esses critérios, e a árvore descreve as relações entre fatores e critérios dependentes, permitindo medir os fatores com base nas métricas dos critérios. Essa abordagem de "dividir para conquistar" tornou-se padrão na medição da qualidade de software, formalizada pela norma **IEEE 1061**.

**Como funciona / Características:** O modelo em árvore mais usado hoje não é mais o antigo ISO/IEC 9126, e sim a **ISO/IEC 25010** (parte da família **SQuaRE** — *Software Product Quality Requirements and Evaluation*). A versão **2023** trouxe uma atualização importante, ampliando de 8 para **9 características**:

| Característica | O que avalia |
|---|---|
| Adequação funcional | O software faz o que deveria fazer |
| Eficiência de desempenho | Uso de tempo e recursos (CPU, memória, rede) |
| Compatibilidade | Coexiste e troca dados com outros sistemas |
| **Capacidade de Interação** (novo nome) | Ex.: "usabilidade" — inclui agora inclusividade e autodescrição |
| Confiabilidade | Mantém o desempenho sob condições esperadas |
| Segurança | Protege dados e mantém níveis de acesso apropriados |
| Manutenibilidade | Facilidade de modificar, corrigir e testar |
| **Flexibilidade** (novo nome) | Ex.: "portabilidade" — inclui agora escalabilidade |
| **Segurança física (Safety)** (nova!) | Evita danos a pessoas, propriedade ou ambiente |

**Por que isso importa hoje:** a entrada de **Safety** como característica própria reflete a preocupação crescente com software embarcado em carros autônomos, dispositivos médicos e sistemas industriais; **Capacidade de Interação** formaliza inclusividade e acessibilidade como parte da qualidade (não mais um "extra"); **Flexibilidade** passa a considerar explicitamente escalabilidade, essencial para arquiteturas em nuvem e microsserviços.

🧠 **Memorizar:** modelo em árvore = fator → critério → métrica; ISO/IEC 25010 (não mais 9126); 2023 = 8→9 características; as 3 novidades: Safety, Capacidade de Interação (era usabilidade), Flexibilidade (era portabilidade, +escalabilidade).

## 📖 Modelos de confiabilidade

**O que é / Definição para prova:** A maioria dos modelos de qualidade inclui confiabilidade como um fator componente, mas a necessidade de prever e medir a confiabilidade com mais precisão levou ao surgimento de uma especialização própria em modelagem e previsão de confiabilidade.

**Como funciona / Características:** Métricas clássicas:
- **MTTF** (*Mean Time To Failure*): tempo médio até a primeira falha;
- **MTBF** (*Mean Time Between Failures*): tempo médio entre falhas consecutivas em sistemas reparáveis;
- **MTTR** (*Mean Time To Repair/Restore*): tempo médio para restaurar o serviço após uma falha;
- **Densidade de defeitos:** número de defeitos por KLOC (mil linhas de código) ou por ponto de função.

Modelos clássicos de **crescimento de confiabilidade** (*software reliability growth models*) tentam prever, a partir do histórico de falhas em teste, quantos defeitos ainda restam e quando o software estará "confiável o suficiente" para ser liberado:
- **Modelo de Musa** (*Basic Execution Time Model*, 1975): relaciona a taxa de falhas ao tempo de execução do software;
- **Modelo de Goel–Okumoto** (1979): usa um processo de Poisson não-homogêneo para modelar a chegada de falhas ao longo do tempo.

⚠️ **Pegadinha:** a tendência moderna, chamada **Engenharia do Caos**, inverte a lógica desses modelos estatísticos: em vez de só *prever* falhas, empresas como a Netflix (com o **Chaos Monkey**, 2011) passaram a **injetar falhas propositalmente em produção** para medir, empiricamente, a resiliência real do sistema antes que uma falha real aconteça.

🧠 **Memorizar:** MTTF (até a 1ª falha) × MTBF (entre falhas, sistema reparável) × MTTR (tempo de reparo); Musa (tempo de execução) × Goel-Okumoto (Poisson); Chaos Monkey = injeta falha de propósito.

## 📖 Métricas de segurança

**O que é / Definição para prova:** Com a computação integrada a quase todas as atividades humanas, aumentaram as preocupações com a segurança dos sistemas de software — o receio de que invasores roubem ou corrompam arquivos, senhas e contas. A segurança depende tanto do design interno do sistema quanto do tipo de ataque externo que ele pode sofrer.

**Como funciona / Características (panorama atual):**
- **CVSS** (*Common Vulnerability Scoring System*): padrão da indústria (mantido pelo FIRST) para pontuar a severidade de uma vulnerabilidade de 0 a 10, considerando explorabilidade e impacto;
- **OWASP Top 10**: ranking, atualizado periodicamente, das categorias de vulnerabilidade mais críticas em aplicações web — usado como referência de benchmark e checklist de avaliação;
- **SBOM** (*Software Bill of Materials*): inventário formal de todas as dependências de um software, hoje exigido em contratos governamentais dos EUA após incidentes de cadeia de suprimentos como o **Log4Shell** (2021) e o ataque à **SolarWinds** (2020);
- **Métricas de DevSecOps**: tempo médio para remediar uma vulnerabilidade (MTTR de segurança), % de dependências desatualizadas, cobertura de **SAST/DAST** (análise estática/dinâmica de segurança) no pipeline de CI/CD.

🧠 **Memorizar:** CVSS = pontua severidade 0-10; OWASP Top 10 = ranking de vulnerabilidades web; SBOM = inventário de dependências (pós Log4Shell/SolarWinds); SAST/DAST = análise estática/dinâmica.

## 📖 Métricas estruturais e de complexidade

**O que é / Definição para prova:** Atributos de qualidade desejáveis, como confiabilidade e manutenibilidade, geralmente só podem ser medidos após a existência de uma versão operacional do código. Por isso, medem-se atributos **estruturais** de representações do software disponíveis antecipadamente (sem necessidade de execução) — como gráficos de fluxo de controle e diagramas UML — para prever, ainda antes da conclusão do sistema, quais partes podem ser menos confiáveis ou mais difíceis de testar/manter.

**Como funciona / Características (métricas estruturais clássicas):**
- **Complexidade Ciclomática** (McCabe, 1976): conta os caminhos independentes em um grafo de fluxo de controle; valores altos indicam código difícil de testar e manter;
- **Métricas de Halstead** (1977): estimam esforço e volume a partir da contagem de operadores e operandos distintos no código;
- **Suíte de Chidamber e Kemerer (CK, 1994)** — para orientação a objetos: **WMC** (métodos ponderados por classe), **DIT** (profundidade da árvore de herança), **NOC** (número de filhos), **CBO** (acoplamento entre objetos), **RFC** (Response For a Class), **LCOM** (falta de coesão dos métodos);
- **Índice de Manutenibilidade** (*Maintainability Index*): combina complexidade ciclomática, volume de Halstead e linhas de código em um único indicador de 0 a 100.

**Na prática:** hoje essas métricas raramente são calculadas à mão — ferramentas de **análise estática** as coletam automaticamente a cada commit, como **SonarQube/SonarCloud** (calcula complexidade, duplicação, cobertura de testes e *Technical Debt Ratio* baseado no modelo **SQALE**, bloqueando merges que não atingem um *Quality Gate* mínimo) e **CodeClimate, ESLint, Pylint, Checkstyle** (análise específica por linguagem, integrada ao CI/CD).

⚠️ **Pegadinha:** se uma ferramenta bloqueia o merge quando a complexidade ciclomática ultrapassa 10, o time pode passar a otimizar só para "ficar abaixo de 10" — e não necessariamente para escrever o código mais simples possível. É um exemplo concreto da **Lei de Goodhart** (ver seção Métricas Modernas).

🧠 **Memorizar:** McCabe = complexidade ciclomática (caminhos independentes); Halstead = operadores/operandos; CK = WMC/DIT/NOC/CBO/RFC/LCOM (orientação a objetos); SonarQube = Quality Gate/SQALE.

## 📖 Avaliação de maturidade de capacidade (CMMI)

**O que é / Definição para prova:** O **Capability Maturity Model Integration (CMMI®) for Development** é uma técnica de avaliação de processos de desenvolvimento de software, originalmente criada pelo **Software Engineering Institute (SEI)** da Universidade Carnegie Mellon para medir a capacidade de contratados do governo dos EUA. Hoje é utilizado por diversas organizações ao redor do mundo, considerando uso de ferramentas, práticas padronizadas e outros fatores de desenvolvimento. A avaliação resulta em uma classificação em uma escala de **cinco níveis**, do Nível 1 (Inicial — dependente de indivíduos) ao Nível 5 (Otimizado — processos otimizados com base em dados quantitativos). Empresas frequentemente exigem certificações CMMI em níveis específicos para contratar fornecedores.

**Como funciona / Características:** Os **Maturity Levels** (nível organizacional) são:

| Nível | Nome | Característica |
|---|---|---|
| 0 | Incomplete | Ad hoc, trabalho pode não ser concluído |
| 1 | Initial | Imprevisível e reativo; atrasos e estouro de orçamento |
| 2 | Managed | Gerenciado no nível do projeto: planejado, medido, controlado |
| 3 | Defined | Proativo; padrões em toda a organização |
| 4 | Quantitatively Managed | Medido e controlado com objetivos quantitativos |
| 5 | Optimizing | Estável e flexível; melhoria contínua |

Já os **Capability Levels** (nível de área de prática individual, escala 0 a 3) medem o quanto uma prática específica atingiu maturidade: 0 (*Incomplete*), 1 (*Initial* — aborda problemas de desempenho), 2 (*Managed* — conjunto completo mas simples de práticas, monitora progresso do projeto) e 3 (*Defined* — usa padrões organizacionais, foca em objetivos de projeto e organizacionais).

⚠️ **Pegadinha:** não confundir **Maturity Levels** (avaliam a organização como um todo, 0 a 5) com **Capability Levels** (avaliam uma área de prática específica, 0 a 3).

**Governança atual:** o SEI transferiu a gestão comercial do CMMI para o **CMMI Institute** em 2012, que foi **adquirido pela ISACA em 2016** — hoje é a ISACA quem desenvolve o modelo e certifica os *Lead Appraisers*, não mais o SEI. Em **abril de 2023**, a ISACA lançou o **CMMI V3.0**, que mantém os 5 níveis de maturidade mas simplifica a estrutura de práticas, amplia o escopo para além de desenvolvimento de software (segurança, gestão de dados, gestão de pessoas, trabalho remoto) e se integra mais diretamente a frameworks ágeis, em vez de ser percebido como "anti-ágil".

🧠 **Memorizar:** CMMI = SEI (Carnegie Mellon) → hoje ISACA (desde 2016); Maturity Levels 0-5 (organização) × Capability Levels 0-3 (área de prática); CMMI V3.0 (abril 2023) = mais integrado a ágil.

## 📖 Gestão por métricas

**O que é / Definição para prova:** A medição é uma parte fundamental da gestão de projetos de software. Tanto clientes quanto desenvolvedores dependem de gráficos e relatórios baseados em métricas para avaliar se o projeto está no caminho certo. Muitas organizações definem conjuntos padronizados de medições e formas de apresentação dos dados para permitir comparações entre projetos — padronização especialmente importante quando o software é parte de um produto cujo foco principal está fora da área de TI (o cliente final geralmente não domina a terminologia técnica), permitindo que as métricas comuniquem o progresso de forma clara e acessível mesmo para quem não programa nem testa.

**Como funciona / Características:** Exemplos de métricas usadas para medir o sucesso de um projeto: *Schedule Variance*, *Cost Variance*, *Schedule Performance Index*, *Cost Performance Index*, métricas de qualidade, escopo, risco e de *stakeholders*.

## 📖 Métricas ágeis e DevOps

**O que é / Definição para prova:** Times ágeis que trabalham em **Scrum** ou **Kanban** usam métricas próprias, focadas em **fluxo de trabalho** mais do que em previsão de custo total:

- **Velocity**: pontos de história entregues por sprint;
- **Lead time vs. Cycle time**: tempo desde a solicitação até a entrega vs. tempo desde o início do trabalho até a entrega;
- **Cumulative Flow Diagram (CFD)**: visualiza gargalos mostrando o volume de itens em cada coluna do quadro ao longo do tempo;
- **WIP (Work In Progress)**: itens em andamento simultaneamente — limitar o WIP é um princípio central do Kanban;
- **Burndown / Burnup charts**: trabalho restante (ou concluído) ao longo do sprint/release.

⚠️ **Pegadinha:** Lead time e Cycle time não são a mesma coisa — Lead time conta a partir da **solicitação** (inclui espera na fila), enquanto Cycle time conta a partir do **início do trabalho de fato**.

🧠 **Memorizar:** Velocity = pontos/sprint; Lead time (solicitação→entrega) × Cycle time (início→entrega); CFD = gargalos; WIP = princípio do Kanban.

## 📖 DORA Metrics

**O que é / Definição para prova:** A pesquisa **DevOps Research and Assessment (DORA)**, do Google, consolidada no livro *Accelerate* (Forsgren, Humble & Kim, 2018) e no *State of DevOps Report* anual, identificou **quatro métricas-chave** que distinguem times de alta performance:

| Métrica | O que mede |
|---|---|
| Deployment Frequency | Com que frequência o time coloca código em produção |
| Lead Time for Changes | Tempo do commit até estar rodando em produção |
| Change Failure Rate | % de deploys que causam falha em produção |
| Time to Restore Service (MTTR) | Tempo para recuperar o serviço após um incidente |

O achado central do estudo, altamente cobrável em prova: **velocidade e estabilidade não são um trade-off** — os times que fazem deploy com mais frequência também têm menos falhas e se recuperam mais rápido.

🧠 **Memorizar:** DORA = 4 métricas (Deployment Frequency, Lead Time for Changes, Change Failure Rate, MTTR); achado central = velocidade e estabilidade andam juntas, não competem.

## 📖 SLI, SLO, SLA e Error Budget (SRE)

**O que é / Definição para prova:** A prática de **Site Reliability Engineering (SRE)**, criada no Google e formalizada no *Site Reliability Engineering Book* (Beyer et al., 2016), trouxe seu próprio vocabulário de métricas para medir confiabilidade **em produção**, não apenas em teste:

- **SLI** (*Service Level Indicator*): a métrica medida de fato (ex.: % de requisições respondidas em menos de 200ms);
- **SLO** (*Service Level Objective*): a meta interna para o SLI (ex.: 99,9% das requisições em menos de 200ms, por mês);
- **SLA** (*Service Level Agreement*): o compromisso contratual com o cliente, geralmente mais frouxo que o SLO, com penalidades se descumprido;
- **Error Budget**: quanto de "falha" é tolerável antes de violar o SLO (ex.: 0,1% de erro/mês) — usado para decidir, com dados, se o time deve priorizar novas features ou estabilidade.

⚠️ **Pegadinha:** a ordem de "rigor" é **SLI (medida) → SLO (meta interna, mais rígida) → SLA (compromisso contratual, mais frouxo)**. Não confundir qual é interno e qual é o compromisso com o cliente.

🧠 **Memorizar:** SLI = mede; SLO = meta interna; SLA = contrato com cliente; Error Budget = "quanto posso falhar antes de estourar o SLO".

## 📖 A Lei de Goodhart

**O que é / Definição para prova:** **"Quando uma medida se torna um alvo, ela deixa de ser uma boa medida"** — atribuída ao economista **Charles Goodhart** (1975), popularizada pela antropóloga Marilyn Strathern (1997). Toda métrica é uma **proxy** — uma aproximação do que realmente se quer saber. Quando pessoas são avaliadas ou recompensadas diretamente por uma proxy, elas otimizam a proxy, não necessariamente o objetivo real por trás dela.

**Como funciona / Características:** Conceitos relacionados: **Lei de Campbell** (avaliação por indicadores tende a corromper o próprio processo que deveriam medir) e **Falácia de McNamara** (confiar só no que é facilmente quantificável, ignorando o resto).

**Exemplo:** exemplos de métricas "jogadas" em software:
- **Linhas de código como produtividade**: incentiva código verboso (Bill Gates: *"medir o progresso da programação em linhas de código é como medir o progresso na construção de um avião pelo peso"*);
- **Cobertura de testes de 100%**: times escrevem testes sem *asserts* relevantes, só para bater a métrica, sem checar comportamento de fato;
- **Contagem de bugs fechados como meta**: incentiva fechar como "não é bug" ou "duplicado" em vez de corrigir;
- **Story points como "produtividade"**: incentiva inflação de estimativas ao longo do tempo (o mesmo trabalho "vale" cada vez mais pontos).

🧠 **Memorizar:** Goodhart = "medida vira alvo, deixa de ser boa medida"; Campbell = indicador corrompe o processo; McNamara = só confiar no quantificável.

## 📖 Avaliação de métodos e ferramentas

**O que é / Definição para prova:** A literatura é repleta de descrições de novas ferramentas e métodos que prometem aumentar produtividade e melhorar qualidade/custo — mas é difícil distinguir promessa de realidade. Por isso, organizações realizam experimentos, estudos de caso ou pesquisas para avaliar se uma abordagem trará benefícios reais para seu contexto específico. Essas avaliações só são eficazes quando há medições e análises cuidadosas e controladas.

**Como funciona / Características (diferença Métrica × Indicador × KPI):**
- **Métrica**: valores brutos usados para mensurar algo; apenas quantificam o que aconteceu, sem operação implícita (ex.: faturamento, usuários, cliques);
- **Indicador**: tem maior significado e "corrige" a análise — são valores calculados que relacionam métricas com outras métricas, comparados com curvas ou metas (ex.: Turnover, ROI, taxa de conversão);
- **KPI (indicador-chave)**: o mais importante e estratégico, ligado diretamente às metas e objetivos organizacionais, refletindo o objetivo principal daquele departamento (ex.: NPS, margem de lucro).

🧠 **Memorizar:** Métrica (bruto) → Indicador (calculado, comparado) → KPI (estratégico, ligado a metas).

## 📖 Medir a IA em vez de confiar nela

**O que é / Definição para prova:** A IA generativa é hoje o exemplo mais atual de "ferramenta disruptiva aceita pela promessa" — exatamente o tipo de situação em que a avaliação de métodos e ferramentas se torna urgente: assistentes de código realmente aumentam a produtividade?

**Exemplo:** o estudo **METR (Model Evaluation & Threat Research, 2025)** conduziu um **experimento controlado randomizado** com 16 desenvolvedores experientes (em média 5 anos no próprio repositório), resolvendo 246 tarefas reais em projetos open-source maduros, usando ferramentas como Cursor Pro e Claude 3.5/3.7 Sonnet:

| Medida | Resultado |
|---|---|
| Previsão dos devs antes da tarefa | +24% mais rápido (esperado) |
| Percepção dos devs depois da tarefa | +20% mais rápido (percebido) |
| Tempo real medido | **−19% (mais lento)** |

O próprio METR classifica o resultado como específico daquele contexto — pode não se repetir com modelos mais novos.

⚠️ **Pegadinha:** o achado central não é "IA piora produtividade" de forma geral, mas sim a **divergência entre percepção e medição real**: os desenvolvedores *acharam* que estavam sendo mais rápidos com IA quando, medido de fato, estavam mais lentos. Isso reforça por que experimentos controlados (tema central da disciplina) são necessários mesmo quando "todo mundo sabe" que uma ferramenta funciona — e por que resultados empíricos em software envelhecem rápido.

**Como funciona / Características (métricas para modelos de IA em si):** além de medir se a IA ajuda quem programa, também se mede a qualidade do modelo como componente de software: **Precision, Recall e F1-score** (acerto/cobertura de um classificador); **Taxa de alucinação** (frequência de informação falsa apresentada como fato); **Benchmarks de código** (ex.: HumanEval, SWE-bench — % de tarefas resolvidas corretamente); **Custo e latência por requisição**. Essas métricas seguem exatamente a mesma lógica do GQM: nenhuma delas faz sentido fora de um objetivo e uma pergunta bem definidos.

🧠 **Memorizar:** METR 2025 = RCT com 16 devs, 246 tarefas; percepção +20% × realidade −19%; Precision/Recall/F1, taxa de alucinação, HumanEval/SWE-bench = métricas de modelos de IA.

## 📖 Normas Internacionais

Para comparar as três normas centrais desta seção, veja a tabela abaixo — em vez de repetir a explicação de cada uma:

| | IEEE 1061 | ISO/IEC/IEEE 15939 | ISO/IEC 25012 |
|---|---|---|---|
| **Nome** | Standard for a Software Quality Metrics Methodology | Software Measurement Process | Modelo de Qualidade de Dados |
| **Propósito** | Metodologia para identificar, definir e aplicar métricas de **qualidade** de software (não define métricas fixas, descreve como criá-las) | Processo padronizado para **qualquer tipo de medição** no ciclo de vida do software (custo, esforço, desempenho, defeitos etc.) | Definir a **qualidade dos próprios dados** usados na medição |
| **Enfoque** | Liga atributos de qualidade (confiabilidade, manutenibilidade, eficiência, usabilidade) a métricas mensuráveis | Mais amplo que a IEEE 1061 — garante que a medição seja sistemática, repetível e ligada a objetivos estratégicos | 15 características em 2 dimensões: inerentes aos dados (acurácia, completude, consistência, credibilidade, atualidade) e dependentes do sistema (acessibilidade, conformidade, confidencialidade, eficiência, precisão, rastreabilidade, compreensibilidade, disponibilidade, portabilidade, recuperabilidade) |
| **Relação com outras normas** | Complementa a IEEE 730 (Software Quality Assurance Plans); relacionada à família ISO/IEC 9126, hoje substituída pela ISO/IEC 25010 | Ainda ativa (edição 2017); apoia modelos como CMMI, SPICE e ISO/IEC 12207 | Parte da família SQuaRE (assim como a ISO/IEC 25010) |

**Estrutura básica da IEEE 1061:** (1) identificar atributos de qualidade a medir; (2) escolher métricas para medi-los; (3) validar se as métricas realmente medem o que se propõem; (4) interpretar e usar os resultados em decisões de gestão de qualidade.

**Estrutura básica da ISO/IEC/IEEE 15939:** (1) planejar a medição (objetivos, contexto, stakeholders); (2) especificar métricas (quais dados, como coletar); (3) coletar dados (mecanismos confiáveis e consistentes); (4) analisar e interpretar (gerar informação útil para decisão); (5) armazenar e manter (preservar dados e resultados para uso futuro). Essa cadeia é representada no **modelo de medição ISO 15939**: uma Entidade tem um Atributo, medido por um Método de Medição, gerando uma Base Measure; Base Measures combinadas por uma Measurement Function geram Derived Measures; um Analysis Model interpreta essas medidas derivadas em um Indicator, que por sua vez é interpretado (com base nas Information Needs) em um Information Product final.

⚠️ **Pegadinha (nota sobre versão):** a versão vigente da IEEE 1061 é a **IEEE 1061-1998** (revisão de 1992, reafirmada em 2009) — daí a confusão comum com uma suposta "versão 2009". Desde 2020, a norma está classificada como *Inactive-Reserved* pelo IEEE: não é mais atualizada, mas segue como referência histórica, tendo influenciado metodologias modernas de métricas em frameworks ágeis e em modelos de maturidade (CMMI, ISO/IEC 15939).

🧠 **Memorizar:** IEEE 1061 = metodologia de métricas de qualidade (Inactive-Reserved desde 2020); ISO/IEC/IEEE 15939 = processo de medição geral, ainda ativa (2017); ISO/IEC 25012 = qualidade dos dados (15 características, 2 dimensões); modelo 15939: Entidade→Atributo→Base Measure→Derived Measure→Indicator→Information Product.

---

## 📚 Resumão final

- **Relevância:** medição é essencial mesmo quando tratada como luxo; cuidado com o mito de Deming (ele defendeu o oposto da frase famosa) e sempre questione a procedência dos dados.
- **Objetivos da medição:** medir é dar feedback para um objetivo — managers e developers têm perguntas diferentes que a medição precisa responder.
- **GQM:** transforma objetivo (Goal) em pergunta (Question) só então em métrica (Metric); nunca o caminho inverso; GQM+Strategies estende isso para múltiplos níveis organizacionais.
- **Estimativa de custo/esforço:** de COCOMO/pontos de função (clássico) a story points/velocity (ágil) até #NoEstimates (medir fluxo real).
- **Coleta de dados:** cadeia Dados→Informações→Indicadores→Conhecimento→Inteligência; Driver (esforço) vs Outcome (resultado).
- **Modelos de qualidade:** estrutura em árvore fator→critério→métrica, hoje formalizada pela ISO/IEC 25010:2023 (9 características, incluindo a nova Safety).
- **Confiabilidade:** MTTF/MTBF/MTTR e modelos preditivos (Musa, Goel-Okumoto) vs. a tendência moderna de injetar falhas de propósito (Chaos Monkey).
- **Segurança:** CVSS, OWASP Top 10, SBOM e métricas de DevSecOps.
- **Estruturais/complexidade:** McCabe, Halstead, suíte CK, Índice de Manutenibilidade — hoje automatizadas via SonarQube e ferramentas de análise estática.
- **CMMI:** avalia maturidade organizacional (5 níveis) e capacidade por prática (4 níveis); hoje sob gestão da ISACA (CMMI V3.0, 2023).
- **Gestão por métricas:** padronização de indicadores permite comparar projetos e comunicar progresso a stakeholders não-técnicos.
- **Métricas ágeis/DevOps:** velocity, lead/cycle time, CFD, WIP, burndown — e as 4 DORA Metrics, cujo achado central é que velocidade e estabilidade não competem.
- **SRE:** SLI (mede) → SLO (meta interna) → SLA (contrato) → Error Budget (margem tolerável de falha).
- **Lei de Goodhart:** métrica vira alvo, deixa de medir bem — veja os exemplos de métricas "jogadas" em software.
- **Avaliação de métodos/ferramentas:** distinguir Métrica (bruta) de Indicador (calculado) de KPI (estratégico); o estudo METR (2025) mostra divergência entre percepção e medição real do uso de IA em programação.
- **Normas internacionais:** IEEE 1061 (metodologia de qualidade, hoje histórica) vs. ISO/IEC/IEEE 15939 (processo geral de medição, ainda ativa) vs. ISO/IEC 25012 (qualidade dos dados).

## ⚠️ Pontos que podem cair na prova

- O mito de Deming invertido (seção Relevância) — pegadinha clássica de prova.
- A ordem correta do GQM (Goal→Question→Metric) e o template completo do objetivo.
- As 9 características da ISO/IEC 25010:2023, especialmente as 3 que mudaram/entraram (Safety, Capacidade de Interação, Flexibilidade).
- Diferença entre MTTF, MTBF e MTTR (seção Modelos de confiabilidade).
- As 4 DORA Metrics e o achado de que velocidade/estabilidade não são trade-off.
- Diferença entre SLI, SLO e SLA (ordem de rigor/quem define).
- Enunciado exato da Lei de Goodhart e exemplos de métricas "jogadas".
- Diferença entre Maturity Levels (0-5, organização) e Capability Levels (0-3, prática) do CMMI.
- Diferença de escopo entre IEEE 1061, ISO/IEC/IEEE 15939 e ISO/IEC 25012 (tabela comparativa).
- O resultado do estudo METR (percepção de +20% mais rápido vs. realidade de −19% mais lento).

## 📝 Perguntas para revisão

1. Por que a frase "você não pode gerenciar o que não consegue medir" costuma ser atribuída erroneamente a Deming, e o que ele disse de fato?
2. Explique o processo GQM e por que "nunca colete uma métrica sem saber qual pergunta ela responde" é o princípio central.
3. Qual a diferença entre o GQM clássico e o GQM+Strategies?
4. Cite três abordagens de estimativa de esforço em times ágeis e como elas diferem do COCOMO/pontos de função.
5. Descreva a cadeia Dados→Informações→Indicadores→Conhecimento→Inteligência e a diferença entre Driver e Outcome.
6. Quais são as 9 características da ISO/IEC 25010:2023? Quais 3 mudaram ou surgiram na versão 2023, e por quê?
7. Diferencie MTTF, MTBF e MTTR. O que é a "Engenharia do Caos" e como ela se contrapõe aos modelos clássicos de confiabilidade?
8. O que são CVSS, OWASP Top 10 e SBOM, e por que o SBOM ganhou importância recente?
9. Quais são as métricas estruturais clássicas (McCabe, Halstead, CK) e o que cada uma mede?
10. Qual a diferença entre Maturity Levels e Capability Levels no CMMI? Quem gerencia o CMMI hoje?
11. Explique as quatro DORA Metrics e o achado central do estudo Accelerate.
12. Defina SLI, SLO, SLA e Error Budget, e explique a relação de rigor entre eles.
13. Enuncie a Lei de Goodhart e dê dois exemplos de métricas de software que podem ser "jogadas".
14. Diferencie Métrica, Indicador e KPI.
15. O que o estudo METR (2025) descobriu sobre produtividade de desenvolvedores usando IA, e por que esse resultado é relevante para a disciplina de Medição e Experimentação?
16. Compare o propósito e o escopo da IEEE 1061, da ISO/IEC/IEEE 15939 e da ISO/IEC 25012.

### Gabarito

1. A frase é atribuída a Deming, mas em *The New Economics* ele escreveu o oposto: "é errado supor que, se você não pode medir algo, não pode gerenciá-lo" — chamando isso de mito custoso, e reforçando que as figuras mais importantes para a gestão são frequentemente desconhecidas e incognoscíveis.
2. O GQM parte de um objetivo de negócio (Goal), deriva perguntas (Questions) que indicam se esse objetivo está sendo alcançado, e só então define métricas (Metrics) que respondem a cada pergunta. O princípio evita coletar dados "porque são fáceis de medir" sem propósito claro — cada métrica deve ter uma razão de existir ligada a uma pergunta e um objetivo.
3. O GQM clássico conecta objetivos e métricas dentro de um único nível (um time, um projeto). O GQM+Strategies estende o modelo criando uma cadeia de objetivos e métricas que atravessa múltiplos níveis organizacionais — do time de desenvolvimento até a diretoria — deixando explícito por que cada métrica de equipe importa para o negócio.
4. Story points (via Planning Poker, comparação relativa de tamanho), velocity (pontos entregues nos últimos sprints, usada para projetar entregas futuras) e reestimativa contínua (em vez de travar uma estimativa única no início). Diferem por não calcularem esforço absoluto via fórmula fixa (como COCOMO/pontos de função), e sim por comparação relativa e ajuste contínuo.
5. Dados são organizados (Organização) em Informações; Informações são relativizadas (Relativização) em Indicadores; Indicadores são contextualizados (Contextualização) em Conhecimento; Conhecimento vira Aprendizado, gerando Inteligência. Driver (Meio) traduz indicadores em ações individualizadas, gerenciado pelo esforço; Outcome (Fim) depende dos drivers para se operacionalizar, gerenciado pelo resultado.
6. As 9: Adequação funcional, Eficiência de desempenho, Compatibilidade, Capacidade de Interação, Confiabilidade, Segurança, Manutenibilidade, Flexibilidade, Segurança física (Safety). As 3 que mudaram: Capacidade de Interação (antiga usabilidade, agora inclui inclusividade/autodescrição), Flexibilidade (antiga portabilidade, agora inclui escalabilidade) e Segurança física/Safety (nova, refletindo preocupação com carros autônomos, dispositivos médicos e sistemas industriais).
7. MTTF = tempo médio até a primeira falha; MTBF = tempo médio entre falhas consecutivas em sistemas reparáveis; MTTR = tempo médio para restaurar o serviço após uma falha. A Engenharia do Caos (ex.: Chaos Monkey da Netflix) inverte a lógica dos modelos preditivos (que só estimam falhas estatisticamente): em vez disso, injeta falhas propositalmente em produção para medir empiricamente a resiliência real do sistema antes que uma falha real aconteça.
8. CVSS pontua a severidade de uma vulnerabilidade de 0 a 10 (padrão do FIRST); OWASP Top 10 é um ranking atualizado das vulnerabilidades mais críticas em aplicações web, usado como checklist/benchmark; SBOM é um inventário formal de todas as dependências de um software. O SBOM ganhou importância após incidentes de cadeia de suprimentos como o Log4Shell (2021) e o ataque à SolarWinds (2020), sendo hoje exigido em contratos governamentais dos EUA.
9. Complexidade Ciclomática (McCabe) conta caminhos independentes em um grafo de fluxo de controle, indicando dificuldade de testar/manter; Métricas de Halstead estimam esforço/volume a partir da contagem de operadores e operandos distintos; a suíte CK (WMC, DIT, NOC, CBO, RFC, LCOM) mede aspectos de orientação a objetos como herança, acoplamento e coesão.
10. Maturity Levels (0 a 5) avaliam a organização como um todo (do Inicial ao Otimizado); Capability Levels (0 a 3) avaliam uma área de prática específica. Hoje quem gerencia o CMMI é a ISACA, que adquiriu o CMMI Institute em 2016 (o SEI transferiu a gestão comercial em 2012).
11. Deployment Frequency (frequência de deploys), Lead Time for Changes (tempo do commit até produção), Change Failure Rate (% de deploys que causam falha) e Time to Restore Service/MTTR (tempo de recuperação após incidente). O achado central: velocidade e estabilidade não são um trade-off — times com deploy mais frequente também têm menos falhas e se recuperam mais rápido.
12. SLI é a métrica medida de fato; SLO é a meta interna para o SLI (geralmente mais rígida); SLA é o compromisso contratual com o cliente (geralmente mais frouxo que o SLO, com penalidades); Error Budget é quanto de "falha" é tolerável antes de violar o SLO, usado para decidir se o time prioriza novas features ou estabilidade. A ordem de rigor é SLI (medido) → SLO (meta interna, mais apertada) → SLA (contrato, mais frouxo).
13. "Quando uma medida se torna um alvo, ela deixa de ser uma boa medida" (Goodhart, popularizada por Strathern). Exemplos: linhas de código como produtividade (incentiva verbosidade); cobertura de testes de 100% (testes sem asserts relevantes); contagem de bugs fechados como meta (incentiva fechar como "não é bug" em vez de corrigir); story points como produtividade (inflação de estimativas).
14. Métrica é um valor bruto que apenas quantifica algo (ex.: número de cliques); Indicador é um valor calculado que relaciona métricas entre si e é comparado com metas/curvas (ex.: taxa de conversão); KPI é o indicador mais importante e estratégico, ligado diretamente aos objetivos organizacionais (ex.: NPS).
15. O METR conduziu um experimento controlado randomizado com 16 devs experientes resolvendo 246 tarefas reais: antes da tarefa, os devs previram +24% mais rápido com IA; depois, perceberam +20% mais rápido; mas o tempo real medido foi 19% MAIS LENTO. Isso é relevante porque mostra divergência entre percepção e medição real, reforçando por que experimentos controlados são necessários mesmo quando "todo mundo sabe" que uma ferramenta funciona, e que resultados empíricos em software envelhecem rápido.
16. IEEE 1061 é uma metodologia para identificar, definir e aplicar métricas especificamente de qualidade de software (hoje classificada como Inactive-Reserved, mas ainda referência histórica). ISO/IEC/IEEE 15939 define um processo padronizado para qualquer tipo de medição no ciclo de vida do software (não só qualidade), ainda ativa (2017), apoiando CMMI, SPICE e ISO/IEC 12207. ISO/IEC 25012 define a qualidade dos próprios dados usados na medição, com 15 características em duas dimensões (inerentes aos dados e dependentes do sistema) — relevante inclusive para avaliar dados usados em treinamento de IA.
