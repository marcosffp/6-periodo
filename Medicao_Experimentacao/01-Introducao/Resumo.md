# Resumo — Aula 1: Introdução (Medição e Experimentação em Eng. de Software)

> Prof. Danilo de Quadros Maia Filho — PUC Minas. Cobre 100% do conteúdo teórico do `main.pdf` (44 slides).

---

## 📖 Medição: o que é e por que existe

**O que é / Definição para prova:** medição é o processo de coletar números (ou símbolos) que descrevem uma característica de algo — para avaliar essa característica com base em dados, e não em "achismo". Definição do slide "Primeiras Definições": **"medição é o processo pelo qual números e símbolos são atribuídos a entidades do mundo real de forma a descrevê-las de acordo com regras claramente definidas."** Termos-chave: **Entidade** (o "objeto" medido — ex.: um programa, uma equipe), **Atributo** (a característica específica medida — ex.: o tamanho do programa, não o programa inteiro), números/símbolos, unidades, qualidades abstratas (alto/baixo, bom/ruim).

**Definição alternativa (Hubbard), também cobrada:** **"medição é uma redução de incerteza quantitativamente expressa, baseada em uma ou mais observações."** Palavras-chave: observações, incerteza, quantitativo, probabilidade, redução.

A primeira definição foca em "colocar um número/rótulo em algo seguindo uma regra clara". A segunda foca em que medir não precisa eliminar 100% a dúvida — só precisa **diminuir** a incerteza que você tinha antes. Uma medição imperfeita (com margem de erro) já tem valor, porque reduziu a incerteza existente.

**Medição x Cálculo (pegadinha clássica):**

| | Medição (*Measurement*) | Cálculo (*Calculation*) |
|---|---|---|
| O que é | Quantificação **direta** de um atributo | Combinação **indireta** de medições |
| Como se obtém | Direto, com instrumento/observação | A partir de medições já existentes |
| Exemplo | Medir a altura de uma árvore | Calcular densidade populacional a partir de área+habitantes |
| Em software | Contar linhas de código de um arquivo | Calcular "produtividade" combinando linhas, tempo e nº de bugs |

🧠 **Memorizar:** 2 definições (regras+entidades/atributos; redução de incerteza-Hubbard); medição=direta, cálculo=indireto.

---

## 📖 Por que medir importa

**O que é:** o PDF abre mostrando que medição está no dia a dia de qualquer pessoa (culinária, sono, exercício) e que, em engenharia de software, sem medir não dá para saber se um processo, produto ou equipe está indo bem.

**Quantified Self:** movimento/hábito de medir constantemente a própria vida com dados (sono, passos, batimentos, gastos), usando dispositivos vestíveis e apps. Termo **cunhado em 2007 por Gary Wolf e Kevin Kelly**, editores da revista *Wired*. Exemplos: Apple Watch, Whoop, Oura Ring, Strava, apps financeiros. A mesma lógica é transportada para engenharia de software: **"sem medir, não sabemos se estamos melhorando."**

**Por que medir em engenharia de software:** sem medição, não se sabe quão bom/ruim é um processo, produto ou equipe. **Exemplo do PDF:** uma empresa trocou arquitetura monolítica por microsserviços sem medir nada antes/depois, e não percebeu que a complexidade aumentou e o tempo de entrega **triplicou** — métricas como *lead time*, número de bugs e uso de CPU teriam evitado o erro. A medição permite **melhoria contínua** (ciclo PDCA) e serve para **comunicação** clara de resultados a clientes, gerentes e equipes. Ex.: a Microsoft mede o **tempo médio de resolução de bugs** por equipe para ajustar práticas ágeis; Google, Meta e iFood usam experimentos A/B e métricas de produtividade como parte da cultura de engenharia (Google usa **MTTR** e "mudanças de código por dev/semana").

**Ciclo PDCA (Plan–Do–Check–Act):** ciclo de melhoria contínua com 4 etapas que se repetem continuamente.

| Etapa | O que envolve |
|---|---|
| **P**lan (Planejar) | Definição da meta, análise do problema, análise das causas, elaboração dos planos de ação |
| **D**o (Executar) | Treinamento, execução dos planos de ação |
| **C**heck (Verificar) | Verificação dos resultados |
| **A**ct (Agir) | Padronização dos resultados positivos, tratamento dos desvios |

Planeja-se com base numa meta e análise de causas → executa-se (com treinamento) → verifica-se se o resultado bateu a meta → age-se: se deu certo, padroniza-se; se não, trata-se o desvio e o ciclo recomeça.

🧠 **Memorizar:** Quantified Self = Wolf & Kelly, 2007, Wired; PDCA = Plan-Do-Check-Act, ciclo contínuo; Microsoft/Google = MTTR de bugs.

---

## 📖 Experimentação

**O que é / Definição para prova:** experimentação em software é testar hipóteses de forma controlada e segura, para saber se uma mudança realmente causa o efeito desejado, em vez de simplesmente supor. Permite responder perguntas do tipo "essa mudança X causa o efeito Y?" (ex.: "essa nova interface reduz erros do usuário?").

Enquanto a **medição** apenas observa e descreve um valor, a **experimentação** manipula alguma coisa de forma controlada para **comparar** o antes/depois ou duas versões, descobrindo uma relação de causa e efeito.

**Exemplo:** a Amazon testa alterações de interface via **experimentos A/B**, medindo conversões em tempo real — mudanças simples, como a cor de um botão, já aumentaram vendas em milhões. Isso representa bem o conceito porque não foi "achismo" de design: a Amazon formulou uma hipótese, testou com uma parte real dos usuários (grupo experimental) comparando com a versão antiga (grupo controle) e mediu o resultado antes de aplicar a mudança para todos.

⚠️ **Pegadinha:** Medição e Experimentação não são a mesma coisa, mas trabalham juntas — a experimentação **usa** medição para comparar grupo controle x grupo teste.

🧠 **Memorizar:** experimentação = testar hipótese com segurança (causa→efeito); Amazon A/B = exemplo-chave.

---

## 📖 Nem toda métrica é uma boa métrica

**O que é:** medir mal — ou medir a coisa errada — pode ser **pior** do que não medir, porque cria incentivos que distorcem o comportamento das pessoas. O PDF ilustra isso com uma lei, um efeito e uma falácia, cada um com um caso real famoso.

### Lei de Goodhart

**Definição para prova:** **"quando uma medida se torna um alvo (meta), ela deixa de ser uma boa medida."** Popularizada pela antropóloga **Marilyn Strathern (1997)**, a partir de uma ideia do economista **Charles Goodhart (1975)**.

Quando as pessoas sabem que serão avaliadas/recompensadas por um número específico, começam a otimizar **aquele número**, mesmo que isso não melhore (ou piore) o objetivo real por trás dele. **Exemplo:** uma empresa define "linhas de código por dia" como métrica de produtividade — os devs passam a escrever código mais verboso e repetitivo; a métrica sobe, mas o valor entregue não aumenta.

⚠️ **Pegadinha:** a Lei de Goodhart não diz que "métricas são ruins" — diz que a métrica **vira ruim quando é transformada em meta/alvo explícito**, abrindo espaço para ser "jogada" (manipulada).

### Efeito Cobra

**Definição para prova:** fenômeno em que a solução criada para um problema acaba **piorando** o próprio problema, porque as pessoas reagem ao incentivo de forma inesperada.

**Lenda de origem:** na Índia colonial britânica, o governo pagava recompensa por cada pele de cobra entregue, para reduzir a população de cobras venenosas em Déli. A população local passou a **criar cobras** só para vender e ganhar a recompensa; quando o governo cancelou o pagamento, os criadores soltaram as cobras — e a população selvagem **aumentou**, piorando o problema original. É, na prática, uma consequência da Lei de Goodhart: a métrica (nº de peles) virou meta, foi otimizada, mas o objetivo real (reduzir cobras) piorou.

### Falácia de McNamara

**Definição para prova:** erro de raciocínio que consiste em confiar apenas no que é facilmente mensurável, ignorando ou descartando o que não pode ser medido facilmente — mesmo que seja importante. Nome vem de **Robert McNamara**, Secretário de Defesa dos EUA na Guerra do Vietnã, cuja equipe usava a **contagem de corpos inimigos** (*body count*) como principal métrica de sucesso militar.

**Os 4 passos (Charles Handy), na ordem:**
1. Medir o que é facilmente mensurável.
2. Desconsiderar o que não pode ser medido facilmente, ou atribuir-lhe um valor arbitrário.
3. Presumir que o que não pode ser medido facilmente não é importante.
4. Dizer que o que não pode ser medido facilmente, na verdade, não existe.

| | Lei de Goodhart | Falácia de McNamara |
|---|---|---|
| Problema central | A métrica vira alvo e é manipulada | Só se dá valor ao que é fácil de medir |
| Mecanismo | Pessoas "jogam" para melhorar o número | Ignora/descarta o que não é mensurável facilmente |
| Exemplo | Linhas de código/dia vira meta → código inflado | Contagem de corpos no Vietnã → ignora progresso real |
| Frase-resumo | "A medida deixa de ser boa quando vira meta" | "Só existe o que é fácil de medir" |

🧠 **Memorizar:** Goodhart (Strathern 1997/Goodhart 1975) = métrica vira meta e é manipulada; Efeito Cobra = solução piora o problema (lenda das cobras na Índia); McNamara = 4 passos, ignora o difícil de medir (Vietnã, body count).

---

## 📖 Estudos de caso reais de métricas ruins

**O que é:** dois casos reais que mostram a **Lei de Goodhart em ação** no mundo corporativo.

**Caso Wells Fargo (2016):** o banco definiu **metas agressivas de venda cruzada** (*cross-selling*) por funcionário. Para bater a meta, funcionários abriram **milhões de contas e cartões de crédito falsos**, sem consentimento dos clientes — a métrica "produtos vendidos por cliente" subia, mas o valor real não. Consequência: multa de **US$ 3 bilhões**, demissão do CEO, dano à reputação.

**Caso Volkswagen — Dieselgate (2015):** a VW instalou um **software** nos motores a diesel capaz de **detectar** quando o carro estava em teste oficial de emissões, reduzindo artificialmente a emissão de poluentes **durante o teste** — fora dele, a emissão real chegava a ser dezenas de vezes maior que o permitido. A métrica de "conformidade no teste" foi otimizada diretamente, não a poluição real. Consequência: dezenas de bilhões de dólares em multas/acordos, executivos processados criminalmente.

⚠️ **Pegadinha:** se a prova pedir "qual princípio esses dois casos ilustram", a resposta é a **Lei de Goodhart** (métrica virou alvo manipulado) — não a Falácia de McNamara (que é sobre ignorar o difícil de medir, não sobre manipular o fácil de medir).

🧠 **Memorizar:** Wells Fargo = metas de cross-selling → contas falsas → multa US$3bi + CEO demitido; VW = software detecta teste → reduz poluição só no teste → bilhões em multas. Ambos = Lei de Goodhart.

---

## 📖 Como medir bem: métricas multidimensionais (DORA e SPACE)

**O que é:** depois de mostrar os problemas de métricas únicas e "jogáveis", o PDF explica que a resposta da engenharia moderna **não é abandonar métricas** — é usar **conjuntos de métricas multidimensionais**, difíceis de manipular isoladamente, porque otimizar só uma delas prejudica outra.

### DORA Metrics

**O que é / Definição para prova:** conjunto de 4 métricas-chave da pesquisa **DORA** (*DevOps Research and Assessment*, hoje parte do Google), popularizadas pelo livro **Accelerate** (Forsgren, Humble & Kim, 2018).

1. **Deployment Frequency** — com que frequência a equipe entrega em produção.
2. **Lead Time for Changes** — tempo entre um commit e ele estar em produção.
3. **Change Failure Rate** — % de mudanças que causam falha em produção.
4. **Mean Time to Restore (MTTR)** — tempo médio para recuperar de uma falha.

Juntas, classificam times em **Elite / High / Medium / Low performers**. **Por que 4 e não 1:** elas se balanceiam entre si — otimizar só velocidade (deployment frequency, lead time) sem cuidado aumenta falhas; otimizar só estabilidade tende a travar a velocidade de entrega. Isso é uma **defesa direta contra a Lei de Goodhart**: um time não consegue "jogar" as 4 ao mesmo tempo sem realmente melhorar o processo.

💡 Fontes complementares citadas: DORA State of DevOps Report (anual, desde 2014); GitHub Octoverse; Stack Overflow Developer Survey; canal DavesGarage (Dave Plummer, autor do Task Manager do Windows).

### SPACE Framework

**O que é / Definição para prova:** framework proposto por pesquisadores da **Microsoft e GitHub** (Forsgren, Storey, Nagappan et al., 2021), criado para responder: *"como medir produtividade de um desenvolvedor sem cair em armadilhas como linhas de código ou nº de commits?"*

**5 dimensões (sigla SPACE):** **S**atisfaction and well-being (satisfação e bem-estar); **P**erformance (resultado do trabalho, não só volume); **A**ctivity (ações realizadas — commits, PRs, deploys); **C**ommunication and collaboration (qualidade da colaboração); **E**fficiency and flow (fluxo de trabalho sem interrupções).

**Ideia central:** produtividade de desenvolvedor **não é um número único**; nenhuma dimensão isolada deve ser usada como meta — mesma lógica de defesa contra Goodhart. Regra prática do slide: sempre que alguém propuser avaliar produtividade com **1 métrica só**, desconfie.

⚠️ **Pegadinha:** DORA e SPACE não competem nem medem a mesma coisa — DORA foca no **processo de entrega** (deploy, falhas, recuperação); SPACE foca na **produtividade do desenvolvedor** de forma ampla (inclui bem-estar e colaboração, que DORA não mede).

| | DORA Metrics | SPACE Framework |
|---|---|---|
| Origem | Pesquisa DORA (Google); livro *Accelerate* (2018) | Microsoft/GitHub (2021) |
| Foco | Desempenho do processo de entrega (DevOps) | Produtividade do desenvolvedor, de forma ampla |
| Itens | Deployment frequency, lead time, change failure rate, MTTR | Satisfaction, Performance, Activity, Communication, Efficiency |

🧠 **Memorizar:** DORA = 4 métricas de entrega (deploy freq., lead time, change failure rate, MTTR), classifica Elite/High/Medium/Low; SPACE = 5 dimensões de produtividade do dev (Satisfaction, Performance, Activity, Communication, Efficiency); ambos = múltiplas métricas contra Goodhart.

---

## 📖 Medição de produtividade na era da IA Generativa

**O que é:** ferramentas de IA generativa (GitHub Copilot, ChatGPT, Claude) tornam ainda mais difícil e arriscado medir produtividade com métricas ingênuas, já que parte relevante do código hoje é sugerida por IA, não digitada do zero. Isso quebra métricas como "linhas de código por dia" (a IA gera linhas em segundos, sem relação com esforço/qualidade) e "número de commits" — a **Lei de Goodhart fica ainda mais perigosa** na era da IA (mais fácil "inflar" uma métrica ingênua).

**Achados de pesquisa citados:**

| Fonte | Achado |
|---|---|
| **GitHub (2022)** | Estudo controlado: devs usando Copilot completaram uma tarefa **~55% mais rápido** que o grupo sem a ferramenta |
| **DORA State of DevOps Report (2024)** | Primeira vez com perguntas sobre adoção de IA: efeito **positivo, porém pequeno** na produtividade individual — e pode até **piorar a estabilidade de entrega** se a revisão de código não for adaptada |

Frase-síntese do slide: **"Eu codifico mais rápido" ≠ "a organização entrega mais valor."**

**Controvérsia — proposta da McKinsey (2023):** a consultoria publicou um framework para medir "produtividade de desenvolvedor", incluindo métricas como **% de código gerado por IA** e **contagem de PRs**. Gerou forte reação negativa da comunidade, incluindo crítica pública conjunta de **Kent Beck** (criador do Extreme Programming) e **Gergely Orosz** (*The Pragmatic Engineer*): o framework reduzia um trabalho de engenharia complexo a métricas individuais simplistas e facilmente "jogáveis" — o mesmo erro descrito pela **Lei de Goodhart**.

💡 **Pergunta de reflexão do professor (para o semestre):** "Se seu time usa Copilot/ChatGPT no dia a dia, qual seria uma métrica capaz de capturar valor real entregue, sem cair na Lei de Goodhart?" — será retomada quando a disciplina tratar de experimentos controlados.

⚠️ **Pegadinha:** "IA aumenta produtividade" não é a conclusão simples dos estudos — o efeito é **pequeno** e pode ter **efeito colateral negativo** na estabilidade. Não confunda "codificar mais rápido" (métrica individual ingênua) com "entregar mais valor" (objetivo real da organização).

🧠 **Memorizar:** GitHub 2022 = Copilot ~55% mais rápido; DORA 2024 = efeito pequeno, pode piorar estabilidade; McKinsey 2023 = criticada (Beck e Orosz) por repetir erro de Goodhart.

---

## 📖 Informações administrativas da disciplina

*(Contexto do curso — baixa prioridade para prova teórica, resumido apenas para referência.)*

- **Professor:** Danilo de Quadros Maia Filho — Eng. Elétrica (UFMG), Executive MBA em Gerenciamento de Projetos (FGV), Mestre em Otimização (UFMG), 17 anos de carreira.
- **Avaliações:** Avaliação 1 (25 pts), Avaliação 2 (25 pts), Avaliação 3 (25 pts), Trabalho Final (5 pts), Participações/tarefas (15 pts), ADAS (5 pts).
- **Mini-seminários:** a cada aula, 2 alunos apresentam um artigo (até 10 anos) relacionado ao tema da aula anterior, 5 min, individual.
- **Regras gerais:** frequência mínima de 75%, sem arredondamento de notas, chamada só 1x por horário.
- **Cronograma:** nivelamento → conceitos de medição/experimentação → entidades/atributos → métricas de produto/processo/projeto → estatística (tendência central, dispersão, distribuições, testes de hipótese, erros tipo I/II) → experimentação (variáveis, etapas, análise, decisão) — 3 provas ao longo do semestre.
- **Bibliografia básica:** Fenton & Bieman (*Software Metrics*), Wohlin et al. (*Experimentation in Software Engineering*), Juristo & Moreno, periódico *Empirical Software Engineering*, Pressman & Maxim.

---

## 📚 Resumão Final

- **Medição** = atribuir números/símbolos segundo regras claras (def. 1) **ou** reduzir incerteza com base em observações (def. 2, Hubbard); medição é **direta**, cálculo é **indireto** (ver tópico Medição).
- **Experimentação** = testar hipóteses de forma controlada (ex.: A/B), diferente de medição, que só observa.
- Medir é essencial para melhoria contínua (**PDCA**) e comunicação clara de resultados (ver tópico Por que medir importa).
- **Métrica única, fácil de otimizar e fácil de enganar = perigosa**: Lei de Goodhart (métrica vira meta), Efeito Cobra (solução piora o problema), Falácia de McNamara (ignora o difícil de medir) — ver tópico próprio.
- **Wells Fargo** e **Volkswagen** são casos reais que ilustram a Lei de Goodhart em ação.
- A solução da engenharia moderna é usar **métricas multidimensionais**: **DORA** (4 métricas de entrega) e **SPACE** (5 dimensões de produtividade do dev).
- A **IA generativa** torna a Lei de Goodhart ainda mais perigosa; estudos mostram ganho real mas pequeno de produtividade, e a proposta da McKinsey (2023) repetiu o erro de métricas simplistas.

## ⚠️ Pontos que podem cair na prova

- As 4 métricas DORA e as 5 dimensões do SPACE, de cor — as listas mais "decoráveis" do material.
- Os 4 passos da Falácia de McNamara, na ordem certa.
- Diferenciar Goodhart x Efeito Cobra x Falácia de McNamara (mecanismos diferentes).
- Relacionar os casos reais (Wells Fargo, Volkswagen) com a Lei de Goodhart.
- As duas definições formais de Medição, e a diferença entre medição e cálculo.
- Por que usar múltiplas métricas é a defesa contra a Lei de Goodhart.

## 📝 Perguntas para revisão

1. Defina Medição segundo as duas definições vistas em aula, e diferencie medição de cálculo.
2. O que é experimentação, e como ela se diferencia de medição?
3. Enuncie a Lei de Goodhart e explique com um exemplo de software.
4. O que é o Efeito Cobra? Conte a lenda de origem.
5. Quais são os 4 passos da Falácia de McNamara, na ordem, e qual sua origem histórica?
6. Explique os casos Wells Fargo e Volkswagen (Dieselgate) e a qual princípio eles se relacionam.
7. Cite e explique as 4 métricas DORA, e por que são usadas em conjunto (não isoladas).
8. Quais são as 5 dimensões do SPACE Framework e quem o propôs?
9. O que os estudos do GitHub (2022) e do DORA Report (2024) mostraram sobre IA e produtividade?
10. Por que a proposta da McKinsey (2023) sobre medir produtividade foi criticada?
11. O que é o ciclo PDCA e o que cada etapa envolve?
12. O que é o movimento Quantified Self e quem cunhou o termo?

### Gabarito

1. Def. 1: processo pelo qual números/símbolos são atribuídos a entidades do mundo real segundo regras claramente definidas. Def. 2 (Hubbard): redução de incerteza quantitativamente expressa, baseada em uma ou mais observações. Medição é quantificação direta de um atributo; cálculo é indireto, combina medições já existentes.
2. Experimentação testa hipóteses de forma controlada (ex.: A/B) para checar se uma mudança causa um efeito; medição apenas observa/descreve um valor existente, sem manipular nada.
3. "Quando uma medida se torna um alvo, ela deixa de ser uma boa medida" (Goodhart/Strathern). Ex.: "linhas de código/dia" como meta faz devs inflarem código sem aumentar valor entregue.
4. É quando a solução de um problema o piora, pela reação das pessoas ao incentivo. Lenda: governo colonial britânico pagava por peles de cobra na Índia; pessoas passaram a criar cobras para vender; quando o pagamento acabou, soltaram as cobras e a população selvagem aumentou.
5. (1) Medir o fácil; (2) desconsiderar/atribuir valor arbitrário ao difícil de medir; (3) presumir que o difícil de medir não é importante; (4) dizer que não existe. Origem: contagem de corpos (*body count*) na Guerra do Vietnã, por Robert McNamara.
6. Wells Fargo definiu metas agressivas de venda cruzada; funcionários abriram contas/cartões falsos para bater a meta. Volkswagen usou software para detectar testes de emissão e reduzir poluição só durante o teste. Ambos ilustram a Lei de Goodhart — a métrica virou alvo manipulado, enquanto o objetivo real piorou ou não mudou.
7. Deployment Frequency (frequência de entregas), Lead Time for Changes (tempo commit→produção), Change Failure Rate (% de mudanças que causam falha), Mean Time to Restore/MTTR (tempo médio de recuperação). São usadas juntas porque se balanceiam (velocidade x estabilidade), tornando difícil manipular todas sem melhorar de fato — defesa contra Goodhart.
8. Satisfaction and well-being, Performance, Activity, Communication and collaboration, Efficiency and flow — proposto por pesquisadores da Microsoft e GitHub (2021).
9. GitHub (2022): Copilot deixou devs ~55% mais rápidos numa tarefa controlada. DORA (2024): efeito da IA é positivo mas pequeno na produtividade, podendo piorar a estabilidade se a revisão de código não for adaptada.
10. Porque reduzia um trabalho de engenharia complexo a métricas simplistas e facilmente manipuláveis (% código gerado por IA, nº de PRs), repetindo o erro descrito pela Lei de Goodhart; recebeu críticas públicas de Kent Beck e Gergely Orosz.
11. PDCA = Plan (definir meta, analisar problema/causas, planejar ação), Do (treinar e executar), Check (verificar resultado), Act (padronizar acerto ou tratar desvio) — ciclo contínuo de melhoria.
12. Hábito de medir constantemente a própria vida com dados (sono, passos, gastos etc.), usando wearables e apps; termo cunhado em 2007 por Gary Wolf e Kevin Kelly, editores da revista Wired.
