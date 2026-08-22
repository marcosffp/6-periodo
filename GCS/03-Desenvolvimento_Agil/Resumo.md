# Desenvolvimento Ágil de Software

Prof. Diego Augusto Barros — Engenharia e Tecnologia

## 📖 Contexto: Por que o Desenvolvimento Rápido é Necessário

**O que é / Definição para prova:** O material abre explicando o contexto de negócio que motiva a agilidade: atualmente as empresas operam em um **ambiente global em rápida mudança**, precisando responder às novas oportunidades e mercados, às mudanças nas condições econômicas e ao surgimento de produtos e serviços concorrentes. Como os sistemas fazem parte de quase todas as operações de negócios, **novos sistemas devem ser desenvolvidos rapidamente** para obter vantagem competitiva e responder à pressão da concorrência — ou seja, **a entrega e desenvolvimento rápidos é crucial para a maioria dos sistemas de negócios**. Por isso, **as empresas podem estar dispostas a sacrificar a qualidade e comprometer requisitos para uma implantação rápida do novo software**.

🧠 **Memorizar:** Ambiente de negócios muda rápido → software precisa acompanhar → às vezes sacrifica-se qualidade/requisitos em troca de velocidade.

## 📖 Processo de Software Dirigido por Planos

**O que é / Definição para prova:** Os **processos de desenvolvimento de software dirigidos por plano** são aqueles em que as atividades são **planejadas com antecedência** e o progresso é medido em relação a esse plano — seguem um fluxo do tipo: **Engenharia de Requisitos → Especificação de Requisitos → Projeto e Implementação**, com um ciclo de retorno chamado **"Solicitação de Mudança de Requisitos"** que volta à Engenharia de Requisitos. Esses processos **especificam completamente os requisitos, depois projetam, e então constroem e testam um sistema** — as três macro-fases acontecem de forma sequencial e bem delimitada. **Mudanças ou problemas nos requisitos exigem retrabalho e testes adicionais**, o que torna esse tipo de processo **não voltado para o desenvolvimento rápido de software**. Um exemplo de processo dirigido por planos é o **Modelo em Cascata**, também chamado de **"baseado em especificações"** — como esses processos são demorados, **resultam em entregas tardias ao cliente**.

**Como funciona / Características:** Esse tipo de processo é **indicado para sistemas onde uma análise completa é essencial**, por exemplo **sistemas de controle críticos em segurança**, nos quais os riscos de um requisito mal compreendido são altos demais para se optar por um desenvolvimento mais rápido e menos formal.

🧠 **Memorizar:** Dirigido por planos = especifica tudo antes de construir · mudança = retrabalho caro · bom para sistemas críticos, ruim para entrega rápida.

## 📖 Desenvolvimento Rápido de Software (Ágil) e suas Características

**O que é / Definição para prova:** **O desenvolvimento rápido de software é conhecido como Desenvolvimento Ágil ou Métodos Ágeis** — **métodos concebidos para produzir software útil de maneira rápida**. As características centrais desse tipo de desenvolvimento são: **intercalação dos processos de especificação, projeto e implementação** (ou seja, essas atividades não ocorrem em fases estanques e sequenciais, mas se misturam continuamente); **ausência de uma especificação detalhada do sistema** logo no início; **minimização ou geração automática da documentação do projeto pelo ambiente de programação**, sendo que o **documento de requisitos do usuário contém apenas uma definição resumida com as características mais importantes do sistema**; **desenvolvimento do sistema em incrementos**; **participação de usuários finais e stakeholders na especificação e avaliação de cada incremento**; **possibilidade de propostas de novos requisitos para implementação em versões futuras do sistema**; e **ampla utilização de ferramentas para auxiliar no processo de desenvolvimento**, como testes automatizados, gerenciamento de configuração, integração de sistemas e automação da interface do usuário.

🧠 **Memorizar:** Intercalação de especificação/projeto/implementação · pouca documentação formal · incrementos · cliente participa continuamente · muita automação/ferramentas.

## 📖 Processo de Software Ágil e Comparação com o Dirigido por Planos

**O que é / Definição para prova:** No **Processo de Software Ágil**, o **Projeto e a Implementação são as atividades centrais do desenvolvimento**, sendo que outras tarefas (como elicitação de requisitos e testes) são **incorporadas a essas duas atividades**, em vez de existirem como fases separadas — o diagrama do material mostra apenas dois blocos, **Engenharia de Requisitos ↔ Projeto e Implementação**, em um ciclo direto, sem a fase intermediária formal de "Especificação de Requisitos" que existe no modelo dirigido por planos. Isso contrasta com o processo dirigido por planos, no qual **a iteração ocorre dentro das atividades** (cada bloco tem seu próprio ciclo interno) e **documentos formais são usados como comunicação entre as etapas do processo** — nesse modelo, **os requisitos evoluirão, resultando na produção de uma especificação de requisitos, que servirá como entrada para o processo de projeto e implementação**.

**Como funciona / Características (Dirigido por Planos x Ágil):** Os dois modelos não são mutuamente excludentes na prática: **os processos dirigidos por plano são utilizados frequentemente com práticas de programação ágil**, e **os métodos ágeis podem incorporar algumas atividades planejadas**, além da programação e dos testes. **É perfeitamente viável alocar requisitos e planejar a fase de projeto (design) e desenvolvimento como uma série de incrementos** — nesse caso, o processo ágil **não é inevitavelmente focado apenas no código** e **pode produzir alguma documentação de projeto (design)**. Os desenvolvedores podem até decidir que **uma iteração não produzirá código novo, mas sim modelos e documentação de sistema**.

| Dirigido por Planos | Ágil |
|---|---|
| Requisitos especificados completamente antes de projetar | Requisitos evoluem junto com o projeto/implementação |
| Iteração ocorre dentro de cada atividade isolada | Requisitos e Projeto/Implementação em ciclo direto e contínuo |
| Documentos formais comunicam as etapas | Documentação mínima, comunicação mais informal |
| Bom para sistemas críticos/análise completa | Bom para requisitos que mudam rapidamente |

🧠 **Memorizar:** Ágil = Requisitos e Projeto/Implementação praticamente fundidos num único ciclo · os dois modelos podem se combinar na prática (não são opostos rígidos).

## 📖 História do Desenvolvimento Ágil

**O que é / Definição para prova:** **Nos anos de 1980 e início dos anos 1990, havia uma visão generalizada de que a melhor maneira para conseguir o melhor software era por meio de**: **planejamento cuidadoso do projeto**; **garantia de qualidade formalizada**; **uso de métodos de análise e projeto apoiado por ferramentas de software CASE** (*Computer-Aided Software Engineering*); e **processo de desenvolvimento de software rigorosos e controlados**. Essa percepção veio da comunidade de engenharia de software responsável por desenvolver **sistemas grandes e duradouros**, como os destinados aos setores **aeroespacial e governamental**. Quando essa **abordagem pesada de desenvolvimento** é aplicada para **sistemas de negócio de pequeno ou médio porte**, **a sobrecarga de trabalho é tão grande que domina o processo de desenvolvimento de software** — **mais tempo é dedicado à decisão de como o sistema deve ser desenvolvido do que na programação ou nos testes**, e **mudanças nos requisitos exigem retrabalho, levando a alterações na especificação e no design inicial do projeto**. **A insatisfação com essas abordagens levou ao surgimento dos métodos ágeis no final da década de 1990**, que **permitiram que o time de desenvolvimento se concentrasse no próprio software, em vez de no projeto (design) ou na documentação**.

🧠 **Memorizar:** Anos 80-90 = processos pesados (CASE, planejamento rígido) para sistemas grandes (aeroespacial/governo) · aplicado a projetos pequenos, virou sobrecarga · insatisfação → métodos ágeis (fim dos anos 90).

## 📖 Aliança Ágil e Manifesto Ágil

**O que é / Definição para prova:** **Em 2001, Kent Beck e 16 outros notáveis desenvolvedores de software, escritores e consultores (referidos como "Agile Alliance") assinaram o "Manifesto para o Desenvolvimento Ágil de Software"**. O texto do manifesto declara: *"Estamos descobrindo maneiras melhores de desenvolver software, fazendo-o nós mesmos e ajudando outros a fazerem o mesmo. Através deste trabalho, passamos a valorizar"*: **Indivíduos e interações mais que processos e ferramentas**; **Software em funcionamento mais que documentação abrangente**; **Colaboração com o cliente mais que negociação de contratos**; **Responder a mudanças mais que seguir um plano**. **Ou seja, mesmo havendo valor nos itens à direita, valorizamos mais os itens à esquerda** — essa ressalva final é importante: o manifesto não descarta processos, documentação, contratos ou planos, apenas prioriza o item da esquerda quando há conflito entre os dois.

⚠️ **Pegadinha:** É comum errar a estrutura da frase do manifesto — não é "só o da esquerda importa", e sim **"valorizamos mais os itens à esquerda, mesmo reconhecendo valor nos itens à direita"**.

🧠 **Memorizar:** 2001, Kent Beck + 16, Agile Alliance · 4 valores: Indivíduos/interações > processos/ferramentas; Software funcionando > documentação; Colaboração com cliente > negociação de contrato; Responder a mudanças > seguir plano.

## 📖 Os 12 Princípios do Desenvolvimento Ágil

**O que é / Definição para prova:** A partir do Manifesto, a Aliança Ágil detalhou **12 princípios** que operacionalizam esses valores na prática do dia a dia:
1. **Nossa maior prioridade é satisfazer o cliente através da entrega contínua e adiantada de software com valor agregado.**
2. **Mudanças nos requisitos são bem-vindas, mesmo tardiamente no desenvolvimento.** Processos ágeis tiram vantagem das mudanças visando vantagem competitiva para o cliente.
3. **Entregar frequentemente software funcionando, de poucas semanas a poucos meses, com preferência à menor escala de tempo.**
4. **Pessoas de negócio e desenvolvedores devem trabalhar diariamente em conjunto por todo o projeto.**
5. **Construa projetos em torno de indivíduos motivados.** Dê a eles o ambiente e o suporte necessário e confie neles para fazer o trabalho.
6. **O método mais eficiente e eficaz de transmitir informações para e entre uma equipe de desenvolvimento é através de conversa face a face.**
7. **Software funcionando é a medida primária de progresso.**
8. **Os processos ágeis promovem desenvolvimento sustentável.** Os patrocinadores, desenvolvedores e usuários devem ser capazes de manter um ritmo constante indefinidamente.
9. **Contínua atenção à excelência técnica e bom design aumenta a agilidade.**
10. **Simplicidade: a arte de maximizar a quantidade de trabalho não realizado; é essencial.**
11. **As melhores arquiteturas, requisitos e designs emergem de equipes auto-organizáveis.**
12. **Em intervalos regulares, a equipe reflete sobre como se tornar mais eficaz e então refina e ajusta seu comportamento de acordo.**

⚠️ **Pegadinha:** Na prática, **os princípios básicos dos métodos ágeis são, por vezes, difíceis de se concretizar** — o material lista quatro desafios concretos: **o envolvimento do cliente depende da disponibilidade e representação efetiva de todos os stakeholders** (princípio 1 e 4 dependem disso); **algumas pessoas na equipe podem não se adaptar bem ao intenso envolvimento exigido pelos métodos ágeis** (contraria a ideia de "confiar nos indivíduos" do princípio 5); **priorizar mudanças é desafiador em sistemas com múltiplos stakeholders**, cada um com suas próprias prioridades (dificulta aplicar o princípio 2); e **manter a simplicidade requer esforço adicional, especialmente sob pressão de prazos de entrega** (tensiona o princípio 10); além disso, **grandes empresas podem enfrentar dificuldades ao mudar de uma cultura de processos informais para processos definidos** (ou o inverso — de processos rígidos para uma cultura ágil mais informal).

🧠 **Memorizar:** 12 princípios = detalhamento prático dos 4 valores do manifesto · desafios reais: disponibilidade do cliente, adaptação da equipe, múltiplos stakeholders, pressão de prazo x simplicidade, mudança cultural.

## 📖 Métodos Ágeis: Objetivos e Onde São Mais Eficazes

**O que é / Definição para prova:** Os **objetivos dos Métodos Ágeis** são: **reduzir a burocracia do processo**; **evitar trabalho de longo prazo de valor duvidoso**; e **minimizar a criação de documentação pouco utilizada**. **Métodos ágeis são altamente eficazes no desenvolvimento de**: **produtos pequenos ou médios feitos por empresas de software para venda**; e **sistemas personalizados dentro das empresas**, desde que haja **compromisso claro do cliente** e **pouca interferência externa de regras e regulamentos**. Eles **são mais adequados ao desenvolvimento de aplicativos nos quais os requisitos de sistema mudam rapidamente durante o processo de desenvolvimento**, pois **visam entregar rapidamente o software funcional aos clientes**, possibilitando que eles **proponham alterações e novos requisitos para iterações posteriores do sistema**.

**Como funciona / Características:** As práticas centrais dos métodos ágeis incluem: **desenvolvimento incremental**, com **pequenos incrementos e lançamentos frequentes para os clientes**, geralmente **a cada duas ou três semanas**; **envolvimento dos clientes**, para **feedback rápido sobre requisitos**; e **minimização da documentação**, em favor de **comunicação informal**. Já as **características gerais dos métodos ágeis** (nível mais operacional) são: **ciclos de desenvolvimento curtos e iterativos** (também chamados de **Métodos Leves**); **equipes auto-organizadas**; **designs mais simples**; **refatoração de código**; **desenvolvimento orientado por testes**; **envolvimento frequente do cliente**; e **ênfase na criação de um produto de trabalho demonstrável a cada ciclo de desenvolvimento**.

🧠 **Memorizar:** Objetivos = menos burocracia, menos trabalho de valor duvidoso, menos documentação inútil · Eficazes para: produtos pequenos/médios ou sistemas personalizados com cliente comprometido e requisitos que mudam rápido.

## 📖 Principais Frameworks/Métodos Ágeis (visão geral)

**O que é / Definição para prova:** O material apresenta uma tabela com os principais frameworks ágeis e seus contribuidores principais, entre eles: **Adaptive Software Development (ASD)** — Jim Highsmith, Sam Bayer; **Agile Modeling** — Scott Ambler, Robert Cecil Martin; **Agile Unified Process (AUP)** — Scott Ambler; **Disciplined Agile delivery** — Scott Ambler; **Dynamic Systems Development Method (DSDM)** — Jennifer Stapleton; **Extreme Programming (XP)** — Kent Beck, Robert Cecil Martin; **Feature-Driven Development (FDD)** — Jeff De Luca; **Lean Software Development** — Mary Poppendieck, Tom Poppendieck; **Lean Startup** — Eric Ries; **Kanban** — Taiichi Ohno; **Rapid Application Development (RAD)** — James Martin; **Scrum** — Ken Schwaber, Jeff Sutherland; e **Scaled Agile Framework (SAFe)** — Scaled Agile, Inc. O material aprofunda três desses métodos: **Extreme Programming (XP)**, **Scrum**, **Rapid Application Development (RAD)** e **Kanban**.

🧠 **Memorizar:** Vários frameworks existem (ASD, XP, FDD, Lean, Kanban, RAD, Scrum, SAFe...) — cada um com autores/contribuidores próprios; os quatro detalhados no material são XP, Scrum, RAD e Kanban.

## 📖 Extreme Programming (XP)

**O que é / Definição para prova:** **Extreme Programming (XP) é um framework ágil de desenvolvimento de software que visa produzir software de maior qualidade e maior qualidade de vida para a equipe de desenvolvimento**. **O nome foi cunhado por Beck (2000)**, e **a abordagem foi desenvolvida para impulsionar práticas reconhecidamente boas** — por exemplo, o desenvolvimento iterativo — **a níveis "extremos"** (daí o nome "extremo"). O ciclo do XP é composto por quatro atividades centrais: **1. Planejamento** (histórias de usuários, valores, critérios de teste de aceitação, plano de iteração) → **2. Projeto** (design simples, cartões CRC, protótipos) → **3. Codificação** (programação em pares) → **4. Teste** (teste unitário, integração contínua, teste de aceitação) — com um ciclo interno de **Refatoração** dentro da Codificação, gerando a cada volta um **incremento do software**.

**Como funciona / Características (práticas do XP):**
- **Desenvolvimento incremental**, sustentado por meio de **pequenos e frequentes releases** do sistema.
- **Requisitos** baseados em **cenários ou histórias de usuários**, usadas como base para decidir a funcionalidade que deve ser incluída em um incremento do sistema. Essas histórias seguem tipicamente o formato: *"Como um `<papel>`, eu quero `<meta/desejo>` para que `<benefício>`"*.
- **Envolvimento do cliente**, sustentado pelo **engajamento contínuo do cliente** com a equipe de desenvolvimento; um **representante do cliente** participa do desenvolvimento e é responsável por definir os **testes de aceitação** para o sistema.
- **Pessoas, não processos**: sustentado por meio de **programação em pares**, **propriedade coletiva do código do sistema** e um **processo de desenvolvimento sustentável** que não envolve horas de trabalho excessivamente longas.
- **Mudança** é aceita por meio de **releases contínuos para os clientes**, do **desenvolvimento *test-first*** e da **Refatoração** (para evitar a degeneração do código), e da **integração contínua** de nova funcionalidade.
- **Manutenção da simplicidade**, feita por meio de **Refatoração constante** (que melhora a qualidade do código) e de **projetos simples** que **não antecipam desnecessariamente futuras mudanças no sistema** — o design do XP segue rigorosamente o princípio **KIS (*Keep It Simple* — Mantenha-o simples)**, sendo sempre preferido um **design simples** em vez de uma representação mais complexa.
- **Escuta ativa**: usada para entender o contexto de negócios do software e ter uma visão ampla da saída necessária e dos principais recursos e funcionalidades; leva à criação das histórias de usuário.
- **Cartões CRC** (*class-responsibility-collaborator*): usados como mecanismo eficaz para pensar sobre o software em um contexto orientado a objetos, **identificando e organizando as classes orientadas a objetos** relevantes para o atual incremento de software; **são o único produto de trabalho de design produzido como parte do processo XP**.
- **Testes unitários**: antes de codificar, a equipe **desenvolve uma série de testes unitários para cada história** a ser incluída na versão atual do software; esses testes **ajudam a equipe a se concentrar no que precisa ser implementado** para passar nos testes, e devem ser implementados usando uma estrutura que **permita sua automatização**, para que possam ser executados de forma fácil e repetida. **Uma vez que o código esteja completo, é testado imediatamente**, proporcionando **feedback instantâneo** aos desenvolvedores.
- **Programação em pares**: um **conceito-chave** durante a codificação (um dos aspectos mais comentados do XP) — **o XP recomenda que duas pessoas trabalhem juntas em uma estação de trabalho de computador para criar código para uma história**.

🧠 **Memorizar:** Beck, 2000 · Ciclo: Planejamento → Projeto → Codificação (com Refatoração) → Teste · Práticas-chave: histórias de usuário, programação em pares, cartões CRC, TDD/testes automatizados, KIS (design simples), integração contínua, propriedade coletiva do código.

## 📖 Scrum

**O que é / Definição para prova:** **Scrum é um método popular de desenvolvimento ágil de software.** **O nome é derivado de uma atividade em partidas de Rugby** (a formação tática na qual os jogadores se juntam em uma disputa física pela posse da bola — a analogia remete ao trabalho coeso e coordenado da equipe). **O framework Scrum foi concebido por Jeff Sutherland e sua equipe no início dos anos 1990.** **Os princípios do Scrum estão alinhados com o manifesto ágil**, e **guiam as atividades de desenvolvimento dentro de um processo que inclui as seguintes atividades: 1. Requisitos, 2. Análise, 3. Projeto, 4. Evolução, 5. Entrega.** **As tarefas de trabalho ocorrem em períodos curtos e limitados no tempo, chamados de sprints** — o trabalho dentro de cada sprint **é adaptado ao problema em questão** e é **definido e frequentemente modificado em tempo real pela equipe Scrum**. **Cada sprint dura de 2 a 4 semanas.**

🧠 **Memorizar:** Sutherland, início anos 1990 · nome vem do Rugby (formação tática coesa) · trabalho organizado em sprints de 2 a 4 semanas.

### Equipe Scrum

**A equipe Scrum é uma equipe interdisciplinar auto organizável** composta por três papéis: **um Proprietário de Produto (*Product Owner* — PO)**, **um Scrum Master (Mestre Scrum — SM)** e **uma pequena equipe de desenvolvimento (3 a 6 pessoas — *Development Team*)**.

| Papel | Responsabilidades |
|---|---|
| **Product Owner (PO)** | Responsável por definir e priorizar os requisitos do produto; representa os interesses do cliente e dos stakeholders; define a visão do produto e toma decisões sobre o que deve ser desenvolvido |
| **Scrum Master (SM)** | Facilita o processo Scrum, removendo impedimentos e garantindo que a equipe siga as práticas e valores do Scrum; ajuda a equipe a entender e implementar os princípios e práticas do Scrum; protege a equipe contra influências externas; ajuda a resolver conflitos internos |
| **Development Team** | Equipe multifuncional e auto-organizada que trabalha para entregar o produto; responsável por transformar os itens do backlog da sprint em incrementos potencialmente entregáveis do produto; colabora diretamente com o PO para entender os requisitos e com o SM para garantir um ambiente de trabalho eficaz |

🧠 **Memorizar:** PO = "o quê" (prioriza requisitos, visão do produto) · SM = facilitador/protetor do processo · Dev Team = "como" (constrói o incremento).

### Artefatos do Scrum

**Os principais artefatos do Scrum são: o backlog do produto, o backlog da sprint e o incremento do código.** **O backlog do produto é uma lista priorizada de todas as funcionalidades, requisitos, melhorias e correções que precisam ser feitas no produto.** **É de responsabilidade do Product Owner gerenciar o backlog do produto**, priorizando os itens com base no valor para o cliente e nas necessidades do negócio; **o backlog do produto é dinâmico e está sempre sujeito a alterações**, com novos itens sendo adicionados, removidos ou reordenados conforme necessário. **O backlog da sprint é a seleção do backlog do produto que a equipe de desenvolvimento concorda em trabalhar durante uma sprint específica** — é composto por uma lista de itens do backlog do produto que foram priorizados para aquela sprint, com base na capacidade da equipe e nos objetivos definidos; **o backlog da sprint é congelado no início da sprint e só pode ser alterado em circunstâncias excepcionais** (por exemplo, a descoberta de novas informações que afetam a sprint). **O incremento do código é o resultado tangível do trabalho realizado durante uma sprint**, consistindo em todas as funcionalidades desenvolvidas e testadas durante a sprint que atendem aos critérios de conclusão definidos (**Definição de Concluído**); **cada incremento do código é uma versão potencialmente entregável do produto**, que adiciona valor ao produto e pode ser lançada ou demonstrada ao cliente no final da sprint.

| Artefato | O que é | Quem gerencia |
|---|---|---|
| Backlog do Produto | Lista priorizada de tudo que falta fazer no produto | Product Owner |
| Backlog da Sprint | Subconjunto do backlog do produto escolhido para a sprint atual | Equipe de Desenvolvimento (congelado no início da sprint) |
| Incremento | Resultado tangível/testado da sprint, potencialmente entregável | Equipe de Desenvolvimento |

🧠 **Memorizar:** Backlog do Produto = tudo · Backlog da Sprint = fatia dessa sprint (congelada) · Incremento = o que foi de fato construído e testado.

### Eventos do Scrum

**O desenvolvimento prossegue ao dividir o projeto em uma série de períodos de desenvolvimento incremental, chamados de sprints; cada sprint dura de 2 a 4 semanas.** Os eventos que estruturam cada sprint são:

- **Reunião de Planejamento da Sprint (*Sprint Planning*)**: **é um evento do framework Scrum que marca o início de uma nova sprint no ciclo de desenvolvimento ágil de software**. Aborda três tópicos: **1. Por que esta Sprint é valiosa? 2. O que pode ser feito nesta Sprint? 3. Como o trabalho escolhido será realizado?** É essencial para **alinhar as expectativas da equipe**, **definir metas claras** e **selecionar o trabalho a ser realizado durante a sprint**, garantindo uma execução eficiente e focada nas necessidades do cliente.
- **Reunião Diária do Scrum (*Daily Scrum*)**: **é um evento de 15 minutos agendado no início de cada dia de trabalho**, que permite que os membros da equipe **sincronizem suas atividades** e **façam planos para as próximas 24 horas**. Três perguntas-chave são feitas e respondidas por todos os membros da equipe: **1. O que você fez desde a última reunião da equipe? 2. Quais obstáculos você está enfrentando? 3. O que você planeja realizar até a próxima reunião da equipe?** **O Scrum Master lidera a reunião e resolve obstáculos quando possível**, promovendo a identificação precoce de problemas. Algumas equipes utilizam a reunião para declarar a conclusão de itens do backlog da sprint, o que pode resultar no agendamento de uma demonstração do incremento concluído com o Product Owner.
- **Reunião de Revisão da Sprint (*Sprint Review*)**: **ocorre ao final da sprint, quando o time de desenvolvimento considera o incremento completo**. Geralmente tem **duração máxima de 4 horas para uma sprint de 4 semanas**. Participam o **Scrum Master**, o **Time de desenvolvimento**, o **Product Owner** e **stakeholders selecionados**. Durante a revisão, **o Product Owner pode aceitar ou não o incremento**, e o **feedback fornecido pode influenciar o planejamento da próxima sprint**.
- **Retrospectiva da Sprint (*Sprint Retrospective*)**: **ocorre ao final de cada sprint no Scrum**. Durante essa reunião, **o time revisa o trabalho realizado na sprint anterior**, discutindo os **pontos positivos e negativos da sprint**, bem como **oportunidades de melhoria**. **O objetivo é aprender com as experiências da sprint anterior e fazer ajustes para aumentar a eficiência e a qualidade do trabalho na próxima sprint. O Scrum Master lidera a reunião, incentivando a participação de todos os membros do time.**

⚠️ **Pegadinha:** Não confundir **Sprint Review** (foco no **produto/incremento**, com o cliente/stakeholders, decide se aceita o incremento) com **Sprint Retrospective** (foco no **processo/equipe**, interno ao time, sem stakeholders externos, discute como melhorar o próprio trabalho).

🧠 **Memorizar:** Sprint Planning (início, o que/como fazer) → Daily Scrum (diário, 15 min, 3 perguntas) → Sprint Review (fim, mostra o incremento ao PO/stakeholders) → Sprint Retrospective (fim, o time reflete sobre o próprio processo).

### O Framework Scrum Completo (visão integrada)

O ciclo completo do Scrum integra os elementos acima: o **Objetivo do Produto** orienta o **Refinamento do Backlog do Produto**, que alimenta o **Backlog do Produto**; a partir dele ocorre o **Planejamento da Sprint**, que define o **Objetivo da Sprint** e o **Backlog da Sprint**; a equipe (PO, SM, Devs) trabalha durante a sprint (com a **Daily Scrum** ocorrendo a cada 24h ao longo de até 30 dias), produzindo, conforme a **Definição de Concluído**, um **Incremento**; esse incremento passa pela **Revisão da Sprint**; e o ciclo se fecha com a **Retrospectiva da Sprint**, cujo aprendizado retroalimenta o Objetivo do Produto para a próxima sprint.

## 📖 Rapid Application Development (RAD)

**O que é / Definição para prova:** O **RAD** é **aplicado principalmente em sistemas de negócios intensivos em dados**. **O método RAD utiliza ferramentas especializadas de desenvolvimento de banco de dados**, que **permitem que engenheiros de software desenvolvam, testem e implantem rapidamente novas ou modificadas aplicações de negócios**. Seu ciclo é composto pelas etapas: **Requirements Planning** (planejamento de requisitos) → **User Design** (projeto do usuário, com um ciclo interno de refinamento/*Refine* + *Prototype*) → **Test** → **Construction** (construção) → **Cutover** (entrada em operação).

🧠 **Memorizar:** RAD = focado em sistemas intensivos em dados · usa ferramentas especializadas de banco de dados · ciclo com prototipagem/refinamento no meio.

## 📖 Kanban

**O que é / Definição para prova:** **Kanban é uma abordagem para gerenciar o trabalho de forma mais eficiente, originária do sistema de produção da Toyota.** **É um método visual para mapear, controlar e melhorar o fluxo de trabalho.** Ele **utiliza um quadro Kanban, que é dividido em colunas que representam diferentes estágios do processo de trabalho** (por exemplo: *To Do*, *Doing*, *Done*), com **cartões que representam itens de trabalho individuais**. **Os objetivos do Kanban são: limitar a quantidade de trabalho em progresso (WIP — *Work In Progress*) em cada etapa do processo; identificar gargalos e impedimentos; e promover a colaboração e a melhoria contínua.**

🧠 **Memorizar:** Kanban = origem na Toyota · quadro visual (colunas = estágios, cartões = tarefas) · objetivo central: limitar WIP e visualizar gargalos.

---

## 📚 Resumão final

- **Contexto**: ambiente de negócios muda rápido, exigindo entrega ágil de software, mesmo com risco de sacrificar qualidade/requisitos.
- **Dirigido por planos**: especifica tudo antes, sequencial (ex.: Cascata); bom para sistemas críticos, ruim para velocidade.
- **Ágil**: intercalação de especificação/projeto/implementação, incrementos, documentação mínima, cliente envolvido continuamente.
- **Dirigido por Planos x Ágil**: não são excludentes — podem se combinar (ágil pode ter planejamento parcial, plano pode usar práticas ágeis).
- **História**: dos processos pesados dos anos 80/90 (CASE, sistemas grandes) à insatisfação que gerou os métodos ágeis no fim dos anos 1990.
- **Manifesto Ágil (2001, Kent Beck + 16)**: 4 valores — indivíduos/interações, software funcionando, colaboração com cliente, responder a mudanças — cada um "mais que" seu par tradicional.
- **12 princípios**: detalham os valores em prática (entrega contínua, mudanças bem-vindas, entregas frequentes, trabalho conjunto diário, equipes motivadas, conversa face a face, software funcionando como métrica, ritmo sustentável, excelência técnica, simplicidade, equipes auto-organizáveis, reflexão periódica) — com desafios reais de aplicação.
- **Métodos ágeis**: objetivos de reduzir burocracia/documentação/trabalho de valor duvidoso; eficazes em produtos pequenos/médios e sistemas personalizados com cliente comprometido.
- **Frameworks**: XP, Scrum, RAD e Kanban são detalhados; outros (FDD, Lean, DSDM, SAFe etc.) são citados na tabela.
- **XP** (Beck, 2000): ciclo Planejamento → Projeto → Codificação → Teste; práticas extremas: pares, cartões CRC, TDD, KIS, integração contínua.
- **Scrum** (Sutherland, anos 1990): sprints de 2-4 semanas; papéis PO/SM/Dev Team; artefatos Backlog do Produto/Sprint/Incremento; eventos Planning/Daily/Review/Retrospective.
- **RAD**: foco em sistemas intensivos em dados, ferramentas especializadas de BD, ciclo com prototipagem.
- **Kanban**: origem Toyota, quadro visual, foco em limitar WIP e identificar gargalos.

## ⚠️ Pontos que podem cair na prova

- Diferença entre processo dirigido por planos e processo ágil, e por que o primeiro não é voltado ao desenvolvimento rápido — ver tópicos correspondentes.
- Os quatro valores exatos do Manifesto Ágil (2001) e a ressalva "mesmo havendo valor nos itens à direita, valorizamos mais os da esquerda".
- Os 12 princípios do desenvolvimento ágil — decorar pelo menos os primeiros (entrega contínua, mudanças bem-vindas, entregas frequentes) e os desafios de aplicá-los na prática.
- Autor e origem do XP (Kent Beck, 2000) e do Scrum (Jeff Sutherland, início dos anos 1990; nome vem do Rugby).
- As quatro atividades do ciclo XP (Planejamento, Projeto, Codificação, Teste) e práticas associadas (programação em pares, cartões CRC, testes unitários automatizados, KIS).
- Os três papéis da equipe Scrum (PO, SM, Dev Team) e suas responsabilidades específicas.
- Os três artefatos do Scrum (Backlog do Produto, Backlog da Sprint, Incremento) e quem é responsável por cada um.
- Diferença entre Sprint Review (produto, com stakeholders) e Sprint Retrospective (processo, interno à equipe) — muito propensa a confusão.
- Duração típica de uma sprint (2 a 4 semanas) e da Daily Scrum (15 minutos) e da Sprint Review (até 4h para sprint de 4 semanas).
- Objetivo do Kanban (limitar WIP, identificar gargalos) e sua origem (sistema de produção da Toyota).
- Foco específico do RAD (sistemas intensivos em dados, ferramentas de banco de dados).

## 📝 Perguntas para revisão

1. Por que a entrega e o desenvolvimento rápidos de software são cruciais para a maioria dos sistemas de negócios atualmente?
2. O que caracteriza um processo de software dirigido por planos, e por que ele não é voltado para o desenvolvimento rápido?
3. Para que tipo de sistema um processo dirigido por planos ainda é indicado, e por quê?
4. Quais são as principais características do Desenvolvimento Ágil de Software?
5. Como o Processo de Software Ágil organiza as atividades de Engenharia de Requisitos e Projeto/Implementação, comparado ao processo dirigido por planos?
6. É verdade que processos dirigidos por planos e métodos ágeis são sempre mutuamente excludentes? Explique.
7. Qual foi a visão predominante sobre desenvolvimento de software nos anos 1980 e início dos 1990, e para que tipo de sistemas ela funcionava bem?
8. O que aconteceu quando essa abordagem pesada foi aplicada a sistemas de negócio pequenos ou médios, e o que isso motivou?
9. Quando e por quem foi assinado o Manifesto Ágil? Cite os quatro valores que ele estabelece.
10. Qual é a ressalva importante sobre a forma como os quatro valores do Manifesto Ágil devem ser interpretados?
11. Cite pelo menos quatro dos 12 princípios do desenvolvimento ágil.
12. Quais são os principais desafios de se aplicar os princípios ágeis na prática, segundo o material?
13. Quais são os três objetivos dos Métodos Ágeis?
14. Em que tipos de projeto os métodos ágeis são mais eficazes?
15. O que é o Extreme Programming (XP), quem cunhou o nome e em que ano?
16. Quais são as quatro atividades do ciclo do XP?
17. O que são histórias de usuário no XP, e qual formato elas costumam seguir?
18. O que são cartões CRC no XP, e qual sua importância no processo?
19. O que é a programação em pares no XP?
20. O que significa o princípio KIS no design do XP?
21. Qual é a origem do nome "Scrum", e quem concebeu esse framework?
22. Quais são os três papéis da equipe Scrum, e qual a responsabilidade principal de cada um?
23. Quais são os três principais artefatos do Scrum, e o que cada um representa?
24. Quanto tempo dura tipicamente uma sprint no Scrum?
25. Qual é a diferença entre a Reunião de Revisão da Sprint (Sprint Review) e a Retrospectiva da Sprint (Sprint Retrospective)?
26. Quais são as três perguntas-chave respondidas na Reunião Diária do Scrum (Daily Scrum)?
27. Para que tipo de sistema o Rapid Application Development (RAD) é mais indicado?
28. O que é o Kanban, qual sua origem, e quais são seus principais objetivos?

### Gabarito

1. Porque as empresas operam em um ambiente global de rápida mudança e precisam responder a novas oportunidades, mudanças econômicas e à concorrência; sistemas novos precisam ser desenvolvidos rapidamente para se obter vantagem competitiva e responder à pressão da concorrência.
2. É um processo em que os requisitos são especificados completamente antes de se projetar, construir e testar o sistema, seguindo um fluxo sequencial (Engenharia de Requisitos → Especificação de Requisitos → Projeto e Implementação). Não é voltado para o desenvolvimento rápido porque mudanças ou problemas nos requisitos exigem retrabalho e testes adicionais, tornando o processo demorado e resultando em entregas tardias ao cliente.
3. É indicado para sistemas onde uma análise completa é essencial, como sistemas de controle críticos em segurança, nos quais entender e especificar corretamente os requisitos desde o início é fundamental para evitar riscos graves.
4. Intercalação dos processos de especificação, projeto e implementação; ausência de especificação detalhada inicial; minimização/geração automática de documentação; desenvolvimento em incrementos; participação de usuários finais e stakeholders na especificação e avaliação de cada incremento; possibilidade de propor novos requisitos para versões futuras; e ampla utilização de ferramentas de apoio ao desenvolvimento.
5. No processo ágil, o Projeto e a Implementação são as atividades centrais, com outras tarefas (como elicitação de requisitos e testes) incorporadas a elas em um ciclo direto entre Engenharia de Requisitos e Projeto/Implementação — sem uma fase formal e separada de "Especificação de Requisitos" como no processo dirigido por planos, no qual a iteração ocorre dentro de cada atividade e documentos formais comunicam as etapas.
6. Não. Processos dirigidos por planos são frequentemente utilizados com práticas de programação ágil, e métodos ágeis podem incorporar atividades planejadas além da programação e dos testes — é viável alocar requisitos e planejar o projeto/desenvolvimento como uma série de incrementos, podendo até gerar alguma documentação de design.
7. A visão era de que o melhor software vinha de planejamento cuidadoso, garantia de qualidade formalizada, uso de ferramentas CASE e processos rigorosos e controlados. Essa abordagem funcionava bem para sistemas grandes e duradouros, como os dos setores aeroespacial e governamental.
8. A sobrecarga de trabalho dominava o processo de desenvolvimento: mais tempo era gasto decidindo como desenvolver o sistema do que programando ou testando, e mudanças nos requisitos exigiam retrabalho na especificação e no design. Isso motivou a insatisfação que levou ao surgimento dos métodos ágeis no final da década de 1990.
9. Foi assinado em 2001 por Kent Beck e mais 16 desenvolvedores, escritores e consultores (a "Agile Alliance"). Os quatro valores são: Indivíduos e interações mais que processos e ferramentas; Software em funcionamento mais que documentação abrangente; Colaboração com o cliente mais que negociação de contratos; Responder a mudanças mais que seguir um plano.
10. Mesmo havendo valor nos itens à direita (processos/ferramentas, documentação, negociação de contratos, seguir um plano), o manifesto declara que se valoriza mais os itens à esquerda — ou seja, os itens da direita não são descartados, apenas priorizados abaixo dos da esquerda quando há conflito.
11. Exemplos: satisfazer o cliente com entrega contínua e adiantada de valor; aceitar mudanças de requisitos mesmo tardiamente; entregar frequentemente software funcionando; ter pessoas de negócio e desenvolvedores trabalhando diariamente juntos; construir projetos em torno de indivíduos motivados e confiar neles; comunicação por conversa face a face; software funcionando como medida de progresso; desenvolvimento sustentável; atenção à excelência técnica; simplicidade; equipes auto-organizáveis; reflexão e ajuste periódicos.
12. O envolvimento do cliente depende da disponibilidade e representação efetiva de todos os stakeholders; algumas pessoas da equipe podem não se adaptar bem ao intenso envolvimento exigido; priorizar mudanças é desafiador quando há múltiplos stakeholders com prioridades diferentes; manter a simplicidade requer esforço extra sob pressão de prazos; e grandes empresas podem ter dificuldade em mudar sua cultura de processos.
13. Reduzir a burocracia do processo; evitar trabalho de longo prazo de valor duvidoso; e minimizar a criação de documentação pouco utilizada.
14. Em produtos pequenos ou médios feitos por empresas de software para venda, e em sistemas personalizados dentro de empresas, desde que haja compromisso claro do cliente e pouca interferência externa de regras e regulamentos — especialmente quando os requisitos do sistema mudam rapidamente durante o desenvolvimento.
15. É um framework ágil de desenvolvimento de software que visa produzir software de maior qualidade e maior qualidade de vida para a equipe de desenvolvimento. O nome foi cunhado por Kent Beck em 2000.
16. Planejamento, Projeto, Codificação (com refatoração contínua) e Teste, formando um ciclo que gera incrementos do software.
17. São requisitos baseados em cenários que descrevem a saída, os recursos e a funcionalidade necessários para o software, usadas para decidir a funcionalidade a incluir em um incremento. Costumam seguir o formato: "Como um <papel>, eu quero <meta/desejo> para que <benefício>".
18. Cartões CRC (class-responsibility-collaborator) identificam e organizam as classes orientadas a objetos relevantes para o incremento atual de software; são o único produto de trabalho de design produzido como parte do processo XP, servindo como mecanismo eficaz para pensar sobre o software em um contexto orientado a objetos.
19. É a prática, recomendada pelo XP, em que duas pessoas trabalham juntas em uma mesma estação de trabalho de computador para criar o código de uma história de usuário — é um dos aspectos mais comentados e um conceito-chave da atividade de codificação no XP.
20. Significa "Keep It Simple" (Mantenha-o simples): o design do XP segue rigorosamente esse princípio, sendo sempre preferido um design simples em vez de uma representação mais complexa.
21. O nome vem de uma formação tática usada em partidas de Rugby, na qual os jogadores se juntam em disputa física pela posse da bola — remetendo ao trabalho coeso da equipe. O framework foi concebido por Jeff Sutherland e sua equipe no início dos anos 1990.
22. Product Owner (PO) — define e prioriza os requisitos do produto, representa cliente/stakeholders e define a visão do produto; Scrum Master (SM) — facilita o processo Scrum, remove impedimentos, protege a equipe e ajuda a resolver conflitos; Development Team — equipe multifuncional auto-organizada que transforma os itens do backlog da sprint em incrementos entregáveis.
23. Backlog do Produto — lista priorizada de todas as funcionalidades, requisitos, melhorias e correções do produto, gerenciada pelo Product Owner. Backlog da Sprint — subconjunto do backlog do produto escolhido pela equipe para trabalhar durante a sprint atual, congelado no início dela. Incremento — resultado tangível e testado do trabalho realizado na sprint, uma versão potencialmente entregável do produto.
24. Tipicamente entre 2 e 4 semanas.
25. A Sprint Review ocorre ao final da sprint com foco no produto/incremento, envolvendo Scrum Master, Time de desenvolvimento, Product Owner e stakeholders selecionados, e o PO pode aceitar ou não o incremento. Já a Sprint Retrospective também ocorre ao final da sprint, mas é interna à equipe, com foco no processo de trabalho (pontos positivos, negativos e oportunidades de melhoria), sem a presença de stakeholders externos.
26. O que você fez desde a última reunião da equipe? Quais obstáculos você está enfrentando? O que você planeja realizar até a próxima reunião da equipe?
27. É mais indicado para sistemas de negócios intensivos em dados, utilizando ferramentas especializadas de desenvolvimento de banco de dados que permitem desenvolver, testar e implantar rapidamente aplicações de negócios novas ou modificadas.
28. Kanban é uma abordagem para gerenciar o trabalho de forma mais eficiente, originária do sistema de produção da Toyota; é um método visual (quadro dividido em colunas representando estágios do processo, com cartões representando itens de trabalho) para mapear, controlar e melhorar o fluxo de trabalho. Seus objetivos são limitar o trabalho em progresso (WIP) em cada etapa, identificar gargalos e impedimentos, e promover colaboração e melhoria contínua.
