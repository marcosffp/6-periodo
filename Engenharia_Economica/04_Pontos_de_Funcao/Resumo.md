# Resumo — Pontos de Função (Análise de Pontos de Função - APF)

*Baseado em: Aula 5 (Planejamento e Precificação + introdução a Pontos de Função), Aula 6 (exemplos de contagem) e Apostila_APF (material de referência completo do IFPUG).*

## 📖 Planejamento de projetos e precificação de software

**O que é / Definição para prova:** Ao disputar um contrato, é preciso definir o preço que será proposto ao cliente para desenvolver o software. O **ponto de partida para calcular esse preço é a estimativa dos custos** para concluir o trabalho do projeto — o que envolve estabelecer a quantidade de esforço necessária para cada atividade e calcular o custo total. Só depois de se ter uma estimativa razoável dos prováveis custos é que há condições de calcular o preço a ser proposto ao cliente. ⚠️ **Pegadinha:** ao estimar o custo do esforço, **não se deve simplesmente multiplicar os salários das pessoas envolvidas pelo tempo gasto** — é preciso levar em conta também todos os **custos gerais da organização** que devem ser cobertos pela receita do projeto (espaço de escritório, administração etc.), somando-os proporcionalmente ao custo de cada engenheiro envolvido.

**Parâmetros principais para calcular os custos de um projeto:**
- **Custos de esforço** — salários dos engenheiros de software e gerentes (na maioria dos projetos, esse é o **maior custo**);
- **Custos de hardware e software** — inclui manutenção de hardware e suporte de software;
- **Custos de viagem e treinamento.**

Deve-se **estimar o esforço total (em pessoas-mês)** provavelmente necessário para realizar o trabalho e, depois de fazer a melhor estimativa possível, **adicionar uma contingência** (tempo e esforço extras) para o caso de a estimativa inicial ter sido otimista.

**Precificação de software:** a princípio, o preço de um sistema é uma soma simples do custo de desenvolvimento com o lucro do desenvolvedor. Na prática, porém, essa relação normalmente não é tão simples — é preciso considerar preocupações organizacionais, riscos do projeto e o tipo de contrato utilizado. Vários **fatores** podem levar uma organização a cobrar mais ou menos do que o custo + lucro "puro":

| Fator | O que influencia |
|---|---|
| **Termos contratuais** | Se o cliente deixa o desenvolvedor manter a propriedade do código-fonte (para reuso futuro), o preço pode ser reduzido para refletir esse valor. |
| **Incerteza da estimativa de custos** | Se a organização não tem certeza da estimativa, pode aumentar o preço com uma contingência além do lucro normal. |
| **Saúde financeira** | Empresas com problemas financeiros podem baixar o preço para garantir o contrato — o fluxo de caixa importa mais que o lucro em momentos difíceis. |
| **Oportunidade de mercado** | Cotar um preço baixo para entrar em um novo segmento pode trazer lucro maior no futuro e experiência para novos projetos. |
| **Volatilidade de requisitos** | Se os requisitos tendem a mudar, o preço inicial pode ser reduzido para ganhar o contrato, cobrando-se mais depois pelas mudanças. |

🧠 **Memorizar:** maior custo = esforço (salários); preço ≠ custo+lucro simples; 5 fatores de precificação (contratuais, incerteza, saúde financeira, oportunidade, volatilidade).

## 📖 A crise do software (motivação para medir e estimar melhor)

**O que é / Definição para prova:** Em 2006, Pressman apresentou os principais sintomas da **crise do software**: **a produtividade não acompanha a demanda por serviços**; **a qualidade do software, em alguns sistemas, não é adequada**; e **as estimativas de prazo e custo são frequentemente imprecisas**. Esse último sintoma está associado a um dos principais problemas enfrentados pela indústria: a **falta de previsibilidade de custo e prazo de projetos de software**.

**Consequências dessa falta de previsibilidade:** conflitos entre o gerente do projeto e a equipe; baixa estima da equipe; entrega de software de baixa qualidade; perda de imagem da organização; e cancelamento do projeto.

🧠 **Memorizar:** 3 sintomas de Pressman (produtividade, qualidade, estimativas imprecisas); problema central = falta de previsibilidade de custo/prazo.

## 📖 Processo de estimativas de projetos de software

**O que é / Definição para prova:** É importante investir na implantação de um **processo de estimativas efetivo**, visando à melhoria da previsibilidade de custo, prazo e esforço. O fluxo típico desse processo (aderente à área de Planejamento de Projeto do nível 2 do CMMI) parte da coleta e análise dos requisitos iniciais e segue estimando, em sequência: **tamanho → esforço → cronograma → custo → recursos computacionais críticos**; depois as estimativas são **analisadas e aprovadas**, **acompanhadas** durante o projeto, e ao final o processo é **calibrado e melhorado** com base em um **banco de dados histórico de projetos da organização** — que tanto alimenta quanto é realimentado por essas estimativas. Sempre que necessário, é possível **reestimar** em qualquer ponto do fluxo.

**Distribuição típica de esforço por fase do projeto** (segundo o Roteiro de Métricas SERPRO, 2015): Engenharia de Requisitos 25%, Design/Arquitetura 10%, Implementação 40%, Testes 15%, Homologação 5%, Implantação 5%.

🧠 **Memorizar:** fluxo = tamanho → esforço → cronograma → custo → recursos críticos → aprovar → acompanhar → calibrar; banco de dados histórico alimenta e é realimentado pelo processo; maior fatia de esforço = Implementação (40%).

## 📖 Análise de Pontos de Função (APF): o que é e para que serve

**O que é / Definição para prova:** A Análise de Pontos de Função (APF), **proposta por Allan Albrecht em 1979**, é um método para a **medição de projetos de desenvolvimento e de manutenção evolutiva de software**, que visa **estabelecer o tamanho funcional do software em Pontos de Função (PF)**, considerando as funcionalidades implementadas **sob o ponto de vista do usuário** — ou seja, ela mede o tamanho do software olhando para o que ele *faz* pelo usuário, e não para como ele foi construído tecnicamente (por isso é independente de linguagem de programação ou tecnologia).

**Objetivos principais:**
- determinar o tamanho do produto a partir de suas funcionalidades, de modo a servir como medida consistente entre diversos projetos e organizações;
- medir o tamanho do produto para avaliar o desenvolvimento quanto à **produtividade** e à **qualidade**;
- determinar o tamanho do produto para **estimar custo e recursos** necessários ao desenvolvimento, à melhoria e à manutenção de software;
- obter informações que tornem possível **normalizar dados para comparação** entre softwares;
- determinar o tamanho de um produto (sistema ou subsistema) por meio da **quantificação de suas funcionalidades**.

**Benefícios da APF:** para o **comprador** de software, possibilita determinar o tamanho da ferramenta adquirida por meio da contagem de PF de todas as funcionalidades incluídas; para o **gestor**, serve de apoio à análise de qualidade e produtividade do desenvolvimento, além de ser mecanismo eficaz para estimar esforço, custos e recursos em projetos de manutenção. A APF é hoje a métrica mais utilizada pelo mercado e é reconhecida pela norma internacional **ISO/IEC 20926**.

🧠 **Memorizar:** Albrecht, 1979; mede tamanho pela visão do usuário (funcionalidades), não pela tecnologia; padrão ISO/IEC 20926.

## 📖 Conceitos-base: Fronteira, Escopo, Visão do Usuário e Processo Elementar

**Fronteira da aplicação:** é a **interface conceitual** entre a aplicação sendo medida e seus usuários — define o que é externo à aplicação, atua como uma "membrana" pela qual os dados processados pelas transações (EE, SE, CE) passam para dentro e para fora, envolve os dados mantidos pela aplicação (ALIs) e ajuda a identificar os dados apenas referenciados (AIEs). A fronteira depende da **visão externa do negócio do usuário**, sendo independente de considerações técnicas ou de implementação.

**Escopo de contagem:** delimita **tudo aquilo que não faz parte do sistema a ser desenvolvido** (o que fica de fora da contagem). ⚠️ **Exemplo (do material):** se o propósito é delimitar o escopo de um sistema de RH separando-o do Financeiro, o foco da contagem recai sobre o sistema de RH, mesmo que ele referencie informações do Financeiro (que fica fora do escopo daquela contagem) — pois, na visão do usuário, RH e Financeiro são áreas com funcionalidades distintas.

**Visão do usuário:** é uma descrição formal das necessidades de negócio do usuário, na linguagem do usuário (não técnica) — pode ser materializada por artefatos como histórias de usuário, propostas de projeto, especificação de requisitos, casos de uso ou protótipos. Os desenvolvedores traduzem essa visão para linguagem técnica. Um **usuário**, no contexto da APF, é qualquer pessoa ou coisa que se comunica ou interage com o software (pode ser uma pessoa, um hardware, ou outra aplicação/sistema).

**Processo elementar:** é a **menor unidade de atividade significativa para o usuário final** — constitui uma transação completa, autocontida, que ao final de sua execução deixa o negócio da aplicação em um estado consistente. Inclusão, alteração, consulta e exclusão são os processos elementares mais comuns.

🧠 **Memorizar:** fronteira = interface conceitual usuário-aplicação; escopo = o que fica de fora; usuário = pessoa OU sistema/hardware que interage; processo elementar = menor unidade significativa e autocontida.

## 📖 O processo de contagem de Pontos de Função: visão geral (7 passos)

**O que é / Definição para prova:** O Manual de Práticas de Contagem de Pontos de Função (CPM) do IFPUG define um fluxo de **7 passos** para a contagem:

1. Determinar o **tipo de contagem**;
2. Identificar o **escopo de contagem e a fronteira da aplicação**;
3. Contagem das **funções de dados** (ALI/AIE);
4. Contagem das **funções transacionais** (EE/SE/CE);
5. Determinar os **PFs não ajustados** (soma das etapas 3 e 4);
6. Determinar o **fator de ajuste**;
7. Calcular os **PFs ajustados**.

Os passos 3 e 4 ocorrem em paralelo (ambos partem da fronteira definida no passo 2) e alimentam o passo 5; o passo 6 (fator de ajuste) é independente e se junta ao passo 5 apenas no cálculo final do passo 7. Cada um desses passos é detalhado nos tópicos a seguir.

## 📖 Passo 1: Determinar o tipo de contagem

**Como funciona / As três situações possíveis:**
1. **Projeto a ser desenvolvido** — ocorre quando um novo produto (software) precisa ser desenvolvido e há necessidade de estimar o tamanho do projeto.
2. **Manutenção em sistema já existente** — ocorre quando o sistema já existe e é necessário adicionar novas funcionalidades, modificar ou excluir funcionalidades existentes, precisando-se estimar o tamanho da manutenção.
3. **Determinação do tamanho de sistemas já existentes** — ocorre quando é preciso determinar o tamanho de um sistema já instalado, para o qual essa contagem ainda não havia sido feita.

Essas três situações também são chamadas, no manual do IFPUG, de: contagem de **Projetos de Desenvolvimento**, de **Projetos de Manutenção** e de **Aplicações Instaladas**.

🧠 **Memorizar:** 3 tipos = desenvolvimento (novo) / manutenção (sistema existente, alterando) / aplicação instalada (sistema existente, ainda não contado).

## 📖 Passo 2: Identificar o escopo de contagem e a fronteira da aplicação

**Como funciona:** deve-se identificar todos os relacionamentos do sistema/funcionalidade que está sendo contada com o seu exterior (o que está fora da fronteira), e identificar as pertinências dos dados e processos suportados pelo sistema/funcionalidade. O escopo deve **considerar as funções de dados e controle existentes, sob a perspectiva do usuário**.

**Cinco informações identificadas e contadas nesse passo:**
- **ALI** — Arquivo Lógico Interno;
- **AIE** — Arquivo de Interface Externa;
- **EE** — Entrada Externa;
- **SE** — Saída Externa;
- **CE** — Consulta Externa.

As duas primeiras (ALI, AIE) são **funções de dados**; as três últimas (EE, SE, CE) são **funções de transação** (ou transacionais). Essas cinco categorias são detalhadas em profundidade nos dois próximos tópicos (Passos 3 e 4).

## 📖 Passo 3: Contagem das funções de dados (ALI e AIE)

**O que é / Definição para prova:** As funções de dados representam a funcionalidade fornecida ao usuário relativa aos requisitos de **dados** internos e externos à aplicação. São compostas por:
- **ALI (Arquivo Lógico Interno):** grupo de dados **logicamente relacionados**, ou informações de controle, identificado pelo usuário e **mantido dentro da fronteira da aplicação**. Sua principal função é armazenar dados mantidos por um ou mais processos elementares da própria aplicação.
- **AIE (Arquivo de Interface Externa):** grupo de dados logicamente relacionados, ou informações de controle, identificado pelo usuário, **referenciado** pela aplicação, mas **mantido dentro da fronteira de outra aplicação**. Sua função é armazenar dados apenas referenciados (não mantidos) pela aplicação sendo contada.

⚠️ **Pegadinha:** por definição, um **AIE contado para uma aplicação deve obrigatoriamente ser um ALI em outra aplicação** — ou seja, todo dado tem que "pertencer" (ser mantido) por alguma aplicação.

**Como funciona / Contagem em 3 passos:**

**a) Identificar as funções de dados** — cada ALI/AIE contém um ou mais subconjuntos de dados chamados **RLR (Registro Lógico Referenciado)** ou simplesmente **RL (Registro Lógico)**; por padrão, todo ALI/AIE contém pelo menos 1 RL. Dentro de cada RL, os campos/atributos únicos (reconhecidos pelo usuário, não repetidos, incluindo chaves estrangeiras) são chamados de **ID (Item de Dados)** ou **DER (Dado Elementar Referenciado)**. **Exemplo:** a Aplicação X mantém/referencia CPF, Nome, Rua, Caixa Postal, Cidade, Estado e CEP → 7 DERs; a Aplicação Z mantém/referencia apenas Nome, Cidade e Estado → 3 DERs. ⚠️ Não se conta cada ocorrência de um dado — um conjunto de Telefones, mesmo com vários registros, conta como 1 único tipo de dado (1 DER).

**b) Classificar a função e determinar sua complexidade** — combinando o número de RLRs (RL) com o número de DERs (ID), segundo a tabela:

| RLRs \ DERs | 1–19 | 20–50 | 51 ou mais |
|---|---|---|---|
| **1 RL** | Simples | Simples | Média |
| **2 a 5 RLs** | Simples | Média | Complexa |
| **6 ou mais RLs** | Média | Complexa | Complexa |

**c) Determinar o tamanho (peso em PF)** de cada ALI/AIE, multiplicando a **quantidade** de cada um pelo **peso** correspondente à sua complexidade:

| Complexidade | ALI | AIE |
|---|---|---|
| Baixa (Simples) | 7 | 5 |
| Média | 10 | 7 |
| Alta (Complexa) | 15 | 10 |

**Exemplo (Controle de Ponto — Apostila, pág. 96):**

| Descrição | Tipo | TD (DERs) | TR (RLRs) | Complexidade |
|---|---|---|---|---|
| Pessoa (matrícula, nome, senha, tipo) | AIE | 4 | 1 | Baixa |
| Apontamento (matrícula, data, hora entrada, hora saída) | ALI | 4 | 1 | Baixa |
| Justificativa (matrícula, data, texto) | ALI | 3 | 1 | Baixa |

Aplicando os pesos: ALI = 2 (baixa) × 7 = **14 PF**; AIE = 1 (baixa) × 5 = **5 PF**.

🧠 **Memorizar:** ALI = mantido dentro; AIE = referenciado, mantido fora (é ALI em outra aplicação); RLR/RL = subgrupo de dados; DER/ID = atributo único; tabela de complexidade (RLR × DER); pesos ALI 7/10/15, AIE 5/7/10.

## 📖 Passo 4: Contagem das funções transacionais (EE, SE, CE)

**O que é / Definição para prova:** As funções transacionais representam a funcionalidade de **processamento de dados** oferecida ao usuário. São três tipos, todos definidos como **processos elementares**:

| | Entrada Externa (EE) | Saída Externa (SE) | Consulta Externa (CE) |
|---|---|---|---|
| **Direção do dado** | Recebe dados/controle de fora da fronteira | Envia dados/controle para fora da fronteira | Envia dados/controle para fora da fronteira |
| **Intenção primária** | Manter um ou mais ALI e/ou alterar o comportamento do sistema | Apresentar informação ao usuário através de processamento lógico | Apresentar informação ao usuário através de recuperação de dados |
| **Processamento lógico exigido** | — | Deve ter ao menos: fórmula/cálculo, OU gerar dados derivados, OU manter um ALI, OU alterar comportamento do sistema | Não pode ter fórmula/cálculo nem gerar dados derivados; nenhum ALI é alterado |
| **Termos típicos** | incluir, alterar, excluir, editar, registrar, gravar, carregar | relatórios com totalização, relatórios que também atualizam arquivos, consultas com cálculo/dados derivados | ajuda on-line, consulta a dados de cliente/paciente/aluno, autenticação/login |
| **Exemplo do material** | Janela que permite adicionar/excluir/alterar registros (complexidade baixa = 3 PF) | Relatório de saldo por cartão de crédito (complexidade baixa = 4 PF) | Consulta de restituição de IR por CPF (complexidade baixa = 3 PF) |

⚠️ **Pegadinha:** informações de **ajuda on-line (help)** contam como **CE**, nunca como SE. Da mesma forma, se uma funcionalidade permite gerar **múltiplas formas de relatório a partir do mesmo processamento**, conta-se apenas **1 SE**. Já **Drop-Downs estáticos não são contados como CE** — só contam se recuperarem dados de arquivos lógicos dinamicamente.

**Como funciona / Passos para contar (6 passos):**
1. Identificar cada processo elementar único requerido pelo usuário;
2. Classificar cada processo elementar como EE, SE ou CE;
3. Determinar quantos **ALRs** (Arquivos Lógicos Referenciados) e **DERs/IDs** existem em cada função de transação;
4. Determinar a **complexidade funcional** de cada função, cruzando ALRs × DERs nas tabelas abaixo;
5. Determinar o **tamanho funcional** (peso em PF) de cada função;
6. Obter o total de PF das funções de transação.

**Complexidade da EE** (cruzando ALRs × DERs):

| ALRs \ DERs | 1–4 | 5–15 | 16 ou mais |
|---|---|---|---|
| 0–1 | Simples | Simples | Média |
| 2 | Simples | Média | Complexa |
| 3 ou mais | Média | Complexa | Complexa |

**Complexidade da SE e CE** (cruzando ALRs × DERs — nota: uma CE tem no mínimo 1 ALR):

| ALRs \ DERs | 1–5 | 6–19 | 20 ou mais |
|---|---|---|---|
| 0–1 | Simples | Simples | Média |
| 2–3 | Simples | Média | Complexa |
| 4 ou mais | Média | Complexa | Complexa |

**Pesos (tamanho em PF) das funções de transação:**

| Complexidade | EE | SE | CE |
|---|---|---|---|
| Baixa | 3 | 4 | 3 |
| Média | 4 | 5 | 4 |
| Alta | 6 | 7 | 6 |

**Sobre a lógica de processamento (usada para classificar/justificar EE, SE, CE):** existem 13 tipos possíveis de lógica de processamento (ex.: realizar validações, realizar cálculos/fórmulas, converter equivalência entre montantes, filtrar/comparar dados, analisar condições, atualizar um ou mais ALI, referenciar um ou mais ALI/AIE, recuperar dados, criar dados derivados, alterar comportamento do sistema, preparar/apresentar informação para fora da fronteira, aceitar dados/controle que entra na fronteira, ordenar/organizar dados). Cada tipo de função de transação **pode**, **deve** (ao menos uma dessas lógicas precisa estar presente) ou **não pode (N/A)** executar cada tipo de lógica — por exemplo, realizar cálculos e fórmulas matemáticas é algo que a SE **deve** poder fazer (ou gerar dados derivados, ou manter um ALI), enquanto a CE **não pode** ter esse tipo de lógica.

🧠 **Memorizar:** EE mantém dado / SE e CE enviam dado para fora; SE precisa de processamento lógico (fórmula/derivado/mantém ALI/altera comportamento), CE não pode ter isso; help = sempre CE; pesos EE 3/4/6, SE 4/5/7, CE 3/4/6.

## 📖 Passo 5: Determinar os Pontos de Função não ajustados (PFNA / ADD)

**O que é / Definição para prova:** Os Pontos de Função **não ajustados** refletem as funcionalidades fornecidas pela aplicação (ou projeto) para o usuário, avaliadas em termos de **O QUE É** entregue. É simplesmente a **soma dos tamanhos (pesos)** obtidos nos Passos 3 (funções de dados) e 4 (funções de transação).

**Exemplo (contagem completa, do material):**

| Função | Tipo | Complexidade | PF (não ajustado) |
|---|---|---|---|
| Cliente | ALI | Média | 10 |
| Produto | ALI | Baixa | 7 |
| Fornecedor | AIE | Baixa | 5 |
| Incluir/Alterar/Excluir/Consultar Cliente + 4 relatórios | EE/CE/SE | variada | 6+4+3+3+4+5+4+7 |
| Incluir/Alterar/Excluir/Consultar Produto + relatório | EE/CE/SE | variada | 4+3+3+4+5 |
| Consulta e relatório de Fornecedor | CE/SE | variada | 3+5 |
| **Tamanho Funcional total** | | | **85 PF (não ajustados)** |

🧠 **Memorizar:** PF não ajustado = soma simples (funções de dados + funções de transação); representa "o que é" entregue.

## 📖 Passo 6: Determinar o Fator de Ajuste (VFA/VAF)

**O que é / Definição para prova:** O sexto passo é o cálculo do **Fator de Ajuste**, responsável por corrigir eventuais distorções do cálculo anterior. Ele se baseia nas **14 Características Gerais do Sistema (CGS)**, que avaliam a funcionalidade *geral* da aplicação (seus requisitos **não funcionais**):

Comunicação de Dados; Processamento de Dados Distribuído; Performance (Desempenho); Configuração do Equipamento (Utilizada); Volume de Transações; Entrada de Dados On-line; Interface/Eficiência do Usuário Final; Atualização On-line; Processamento Complexo; Reusabilidade; Facilidade de Implantação; Facilidade Operacional; Múltiplos Locais; Facilidade de Mudanças (Flexibilidade).

**Como funciona:** cada uma das 14 CGS recebe um **peso (Nível de Influência - NI) de 0 (nenhuma influência) a 5 (forte/grande influência)**. A soma de todos os NIs resulta no **TDI (Nível/Grau Total de Influência)**. A partir do TDI, calcula-se o Fator de Ajuste com a fórmula:

**VFA (ou VAF) = (TDI × 0,01) + 0,65**

Como o TDI varia de 0 (todas as CGS = 0) a 70 (todas as CGS = 5), o Fator de Ajuste varia entre **0,65 e 1,35** — por isso se diz que ele corrige o PF não ajustado em **até ±35%**. ⚠️ Para se adequar à norma ISO 14143 (medição do tamanho funcional), o IFPUG tornou o fator de ajuste **opcional** — contratualmente, costuma-se fixar o fator de ajuste = 1 (neutro) quando não se deseja que ele influencie o resultado.

**Exemplo:** em um sistema, apurou-se TDI = 34 → VFA = (34 × 0,01) + 0,65 = **0,99**.

🧠 **Memorizar:** 14 CGS, escala 0-5 cada; TDI = soma; VFA = (TDI×0,01)+0,65; faixa 0,65 a 1,35 (±35%); fator de ajuste é opcional pela ISO 14143.

## 📖 Passo 7: Calcular os Pontos de Função Ajustados

**O que é / Definição para prova:** É o sétimo e último passo, no qual se corrige o PF não ajustado usando o Fator de Ajuste calculado no passo anterior, aproximando a medida da situação real. A **fórmula usada varia conforme o tipo de contagem** (definido no Passo 1):

| Situação | Fórmula | Variáveis |
|---|---|---|
| **Aplicação (após 1ª instalação, a qualquer momento do ciclo de vida)** | AFP = ADD | AFP: PF da aplicação; ADD: tamanho das funções entregues |
| **Projeto de Desenvolvimento** | DFP = ADD + CFP | DFP: PF do projeto; ADD: funções a entregar; CFP: tamanho das funções de conversão |
| **Projeto de Melhoria** | EFP = ADD + CHGA + CFP + DEL | EFP: PF do projeto de melhoria; ADD: funções incluídas; CHGA: funções alteradas (como ficarão); CFP: funções de conversão; DEL: funções excluídas |
| **Aplicação, após melhoria** | AFPA = (AFPB + ADD + CHGA) − (CHGB + DEL) | AFPA: tamanho depois da melhoria; AFPB: tamanho antes; CHGB: tamanho das funções alteradas, antes da melhoria |
| **Contagem inicial com fator de ajuste** | AFP = ADD × VAF | AFP: PF ajustados; ADD: PF não ajustados; VAF: fator de ajuste |

**Sobre as funções de conversão (CFP):** não são funcionalidades técnicas — são funções construídas e entregues pelo projeto (de desenvolvimento ou melhoria), usadas apenas no momento da instalação para converter dados ou atender requisitos de conversão especificados pelo usuário (ex.: relatórios de verificação da conversão). São descartadas após o uso, não fazendo parte da aplicação depois de instalada. **Exemplo:** ao instalar uma nova aplicação de RH, o usuário precisa que dados sejam migrados de uma aplicação legada e inseridos na nova aplicação — essa migração é uma função de conversão. ⚠️ A migração de plataforma tecnológica, por si só, **não** é contada como função de conversão (pois não é vista pelo usuário como uma funcionalidade de negócio).

**Exemplo completo (Cadastro de Clientes com listagem alfabética e exportação em arquivo texto — todos os tipos com complexidade baixa):**
- ALI = 1, AIE = 0, EE = 1 (inclusão), SE = 1 (listagem), CE = 1 (exportação)
- **ADD = ALI×7 + AIE×5 + EE×3 + SE×4 + CE×3 = 1×7 + 0×5 + 1×3 + 1×4 + 1×3 = 17 PF (não ajustados)**
- Considerando TDI = 45 → **VAF = 0,65 + (0,01×45) = 1,1**
- **AFP = ADD × VAF = 17 × 1,1 = 18,7 PF (ajustados)**

🧠 **Memorizar:** fórmula muda por tipo de contagem (aplicação: AFP=ADD; desenvolvimento: DFP=ADD+CFP; melhoria: EFP=ADD+CHGA+CFP+DEL); CFP = função de conversão, descartada após uso.

## 📖 Aplicações da APF: estimando esforço, prazo e custo

**O que é / Definição para prova:** Uma vez obtido o tamanho em Pontos de Função (PF), a APF é usada como base para estimar esforço, prazo e custo de desenvolvimento — sendo uma das principais vantagens do método o fato de permitir gerar estimativas **já nas fases iniciais** do desenvolvimento, e apoiar reestimativas ao longo do projeto.

**Fórmulas principais:**
- **Produtividade no desenvolvimento = Horas por PF (H/PF)**
- **Esforço de desenvolvimento = Produtividade (H/PF) × Tamanho (PF)**
- **Custo de software = Tamanho (PF) × Custo (R$/PF)**
- Outras aplicações: **Taxa de produção de software** = PF/mês ou PF/ano; **Taxa de manutenção de software** = PF de manutenção / PF do aplicativo.

**Continuação do exemplo (Cadastro de Clientes, AFP = 18,7 PF):** considerando produtividade média de 10 h/PF, jornada de trabalho de 6 horas, 4 pessoas alocadas ao desenvolvimento e valor da hora de trabalho de R$ 25,00:
- **Esforço = 10 h/PF × 18,7 PF = 187 horas**
- **Prazo = 187 h ÷ (4 pessoas × 6 h) = 7,8 dias**
- **Custo = 187 h × R$ 25,00 = R$ 4.675,00**

**Fórmula específica para estimar o prazo (Capers Jones, 2007):**

**Td = Vᵗ**

onde **Td** é o prazo de desenvolvimento em meses, **V** é o tamanho do projeto em Pontos de Função, e **t** é um expoente que varia conforme o tipo de sistema:

| Tipo de Sistema | Expoente t |
|---|---|
| Sistema Comum – Mainframe (alto reuso/manutenção evolutiva) | 0,32 a 0,33 |
| Sistema Comum – Web ou Cliente-Servidor | 0,34 a 0,35 |
| Sistema Orientado a Objetos (não é novidade para a equipe) | 0,36 |
| Sistema Cliente/Servidor (alta complexidade arquitetural) | 0,37 |
| Sistemas gerenciais complexos (data warehousing, geoprocessamento, workflow) | 0,39 |
| Software básico, frameworks, sistemas comerciais | 0,40 |

⚠️ **Pegadinha:** essa fórmula de Capers Jones **só é válida para projetos a partir de 100 Pontos de Função** — para projetos menores (como o exemplo de 18,7 PF acima) não se aplica. O prazo calculado por ela considera todo o ciclo de vida do projeto.

🧠 **Memorizar:** Esforço = Produtividade(H/PF) × Tamanho(PF); Custo = Tamanho(PF) × Custo(R$/PF); Td=Vᵗ (Capers Jones), válido só a partir de 100 PF.

## 📖 Requisitos não funcionais: contagem SNAP

**O que é / Definição para prova:** O **SNAP** (Software Non-functional Assessment Process) é um framework do IFPUG (2008) criado para complementar a APF, permitindo medir o tamanho dos **requisitos não funcionais** (técnicos e de qualidade) — coisas que a APF, por focar em funcionalidades visíveis ao usuário, não captura. Os requisitos funcionais (medidos em Pontos de Função) e os não funcionais (medidos em pontos SNAP) podem ser vistos como duas dimensões complementares de um mesmo "bloco" de requisitos do sistema (junto com requisitos técnicos e de qualidade).

**Como funciona / Categorias e subcategorias SNAP** (4 categorias):
1. **Operações de Dados** — validações na entrada, operações lógicas/matemáticas, formatação de dados, movimentações de dados internos, entrega de valor agregado por configuração de dados;
2. **Projeto de Interface** — interfaces do usuário, métodos de ajuda, múltiplos métodos de entrada, múltiplos métodos de saída;
3. **Ambiente Técnico** — múltiplas plataformas, tecnologia de banco de dados, processos batch;
4. **Arquitetura** — software baseado em componentes, múltiplas interfaces de entrada/saída.

**Unidade de medida:** cada subcategoria tem sua própria **UCS (Unidade de Contagem SNAP)**, determinada pela natureza daquela subcategoria — a medição é feita separadamente para cada UCS. A complexidade de uma subcategoria é avaliada, por exemplo, pelo **número de dados elementares** e pelo **número de níveis de aninhamento** (quantidade de validações condicionais — IF-Else, While, For — na cadeia de validação mais longa). Por exemplo, para o parâmetro de nível de aninhamento: complexidade Baixa (1-5 níveis) = 2×#DERs; Média (6-14) = 3×#DERs; Alta (15+) = 4×#DERs. ⚠️ Um mesmo requisito pode ter aspectos funcionais e não funcionais ao mesmo tempo — nesse caso, ele terá um tamanho medido em Pontos de Função **e** um tamanho medido em pontos SNAP.

🧠 **Memorizar:** SNAP mede requisitos não funcionais (técnicos/qualidade); 4 categorias (Operações de Dados, Projeto de Interface, Ambiente Técnico, Arquitetura); UCS = unidade de contagem própria de cada subcategoria.

---

## 📚 Resumão final

- **Planejamento e precificação:** o preço parte da estimativa de custos (maior parcela = esforço/salários); preço final depende de fatores como incerteza, saúde financeira e volatilidade de requisitos, não só de custo+lucro.
- **Crise do software (Pressman):** produtividade, qualidade e estimativas imprecisas geram falta de previsibilidade — motivação central para métodos como a APF.
- **Processo de estimativas:** fluxo tamanho→esforço→cronograma→custo, apoiado por banco de dados histórico, com calibração contínua.
- **APF (Albrecht, 1979):** mede o tamanho funcional do software pela visão do usuário, em Pontos de Função, de forma independente de tecnologia.
- **Fronteira, escopo e visão do usuário** definem o que entra e o que fica fora da contagem.
- **7 passos da contagem:** tipo de contagem → escopo/fronteira → funções de dados (ALI/AIE) → funções transacionais (EE/SE/CE) → PF não ajustados → fator de ajuste → PF ajustados.
- **Funções de dados** (ALI mantido dentro, AIE referenciado/mantido fora) são classificadas por RLR × DER e pesadas (7/10/15 para ALI; 5/7/10 para AIE).
- **Funções transacionais** (EE mantém dado; SE e CE enviam dado, SE com processamento lógico obrigatório, CE sem) são classificadas por ALR × DER e pesadas (3/4/6 EE; 4/5/7 SE; 3/4/6 CE).
- **Fator de ajuste** usa as 14 CGS (escala 0-5, soma = TDI) na fórmula VFA=(TDI×0,01)+0,65, variando de 0,65 a 1,35 (±35%), sendo opcional pela ISO 14143.
- **Fórmulas de PF ajustado** mudam conforme o tipo de projeto (aplicação, desenvolvimento, melhoria).
- **Aplicações práticas:** Esforço = Produtividade × Tamanho; Custo = Tamanho × Custo unitário; Prazo pode usar a fórmula de Capers Jones (Td=Vᵗ), válida só a partir de 100 PF.
- **SNAP** complementa a APF medindo requisitos não funcionais em 4 categorias, usando UCS próprias por subcategoria.

## ⚠️ Pontos que podem cair na prova

- Diferença conceitual entre ALI e AIE, e a regra de que um AIE em uma aplicação é necessariamente um ALI em outra.
- As tabelas de complexidade (RLR×DER para dados; ALR×DER para EE; ALR×DER para SE/CE) e os pesos correspondentes — são as contas mais prováveis de aparecer.
- Diferença entre EE, SE e CE, principalmente a regra de que **ajuda on-line sempre é CE**, e que SE precisa de processamento lógico enquanto CE não pode ter fórmulas/cálculos.
- Fórmula do Fator de Ajuste (VFA) e o fato de ele ser opcional pela ISO 14143, variando entre 0,65 e 1,35.
- As diferentes fórmulas de PF ajustado conforme o tipo de projeto (aplicação × desenvolvimento × melhoria), e o significado de ADD, CFP, CHGA e DEL.
- Fórmulas de esforço, custo e prazo (inclusive a restrição de que a fórmula de Capers Jones só vale a partir de 100 PF).
- Autor e ano de criação da APF (Allan Albrecht, 1979).
- As 4 categorias do SNAP e a ideia geral de que ele mede requisitos não funcionais.

## 📝 Perguntas para revisão

1. O que é a Análise de Pontos de Função e qual é seu principal diferencial em relação a métricas como linhas de código?
2. O que são fronteira da aplicação e escopo de contagem, e por que são o primeiro passo prático da contagem de PF?
3. Diferencie ALI de AIE, incluindo a regra sobre como um AIE se relaciona com outras aplicações.
4. Como se determina a complexidade de uma função de dados (ALI/AIE) e qual é o peso correspondente a cada nível?
5. Diferencie EE, SE e CE quanto à direção do dado e à exigência (ou não) de processamento lógico.
6. Por que uma consulta de ajuda on-line deve ser contada como CE e não como SE?
7. O que é o Fator de Ajuste, como ele é calculado, e por que ele se tornou opcional segundo a ISO 14143?
8. Quais são as diferenças entre as fórmulas de PF ajustado para um projeto de desenvolvimento e para um projeto de melhoria?
9. Como se calculam o esforço, o custo e o prazo de um projeto a partir do seu tamanho em Pontos de Função?
10. O que é o SNAP e por que ele foi criado como complemento à APF?

### Gabarito

1. É um método (criado por Allan Albrecht em 1979) que mede o tamanho funcional de um software contando suas funcionalidades sob a ótica do usuário, resultando em Pontos de Função. Seu diferencial é ser independente de tecnologia/linguagem de programação, ao contrário de métricas como linhas de código, que variam conforme a linguagem usada.
2. A fronteira é a interface conceitual entre a aplicação e seus usuários, definindo o que é interno e externo a ela; o escopo de contagem delimita o que não faz parte do sistema a ser contado. Ambos precisam ser definidos antes de qualquer contagem, pois determinam quais dados/processos entram como ALI/AIE/EE/SE/CE.
3. ALI é um grupo de dados logicamente relacionados mantido dentro da fronteira da aplicação sendo contada; AIE é um grupo de dados referenciado pela aplicação, mas mantido dentro da fronteira de outra aplicação. Por definição, todo AIE contado para uma aplicação deve ser obrigatoriamente um ALI em outra aplicação.
4. A complexidade é determinada cruzando o número de RLRs (registros lógicos) com o número de DERs (atributos únicos) em uma tabela (1 RL / 2-5 RLs / 6+ RLs contra 1-19 / 20-50 / 51+ DERs), resultando em Simples, Média ou Complexa. Os pesos são: ALI = 7 (baixa), 10 (média), 15 (alta); AIE = 5 (baixa), 7 (média), 10 (alta).
5. EE recebe dados de fora da fronteira e tem como intenção primária manter um ALI e/ou alterar o comportamento do sistema. SE e CE enviam dados para fora da fronteira, mas a SE precisa ter processamento lógico (fórmula, cálculo, dado derivado, manutenção de ALI ou alteração de comportamento), enquanto a CE apenas recupera e apresenta dados, sem fórmulas, cálculos ou dados derivados, e sem alterar nenhum ALI.
6. Porque, por definição de regra de contagem do IFPUG, ajuda on-line (help) não envolve processamento lógico com cálculo ou dado derivado — ela apenas recupera e apresenta uma informação ao usuário, o que se encaixa exatamente na definição de Consulta Externa (CE), não de Saída Externa (SE).
7. O Fator de Ajuste corrige o total de PF não ajustados em até ±35%, com base em 14 Características Gerais do Sistema (CGS), cada uma avaliada de 0 a 5. Sua fórmula é VFA = (TDI × 0,01) + 0,65, onde TDI é a soma dos níveis de influência das 14 CGS. Ele se tornou opcional porque a norma ISO 14143 (medição do tamanho funcional) não exige mais essa correção — muitos usuários da APF já não a aplicavam.
8. Para desenvolvimento: DFP = ADD + CFP (soma o tamanho das funções entregues com o das funções de conversão). Para melhoria: EFP = ADD + CHGA + CFP + DEL (soma funções incluídas, alteradas, de conversão e ainda subtrai implicitamente considera as excluídas como parte da contagem, refletindo tudo que o projeto de melhoria tocou).
9. Esforço = Produtividade (horas por PF) × Tamanho (PF); Custo = Tamanho (PF) × Custo unitário (R$ por PF); Prazo pode ser estimado dividindo o esforço total pela capacidade da equipe (pessoas × horas de jornada) ou, para projetos a partir de 100 PF, pela fórmula de Capers Jones: Td = Vᵗ, onde V é o tamanho em PF e t é um expoente que depende do tipo de sistema.
10. O SNAP (Software Non-functional Assessment Process) é um framework do IFPUG criado para medir o tamanho dos requisitos não funcionais (técnicos e de qualidade) de um software, complementando a APF — que mede apenas requisitos funcionais. Ele foi criado porque a APF, por focar no que é visível ao usuário em termos de funcionalidade, não capturava adequadamente esforços ligados a aspectos técnicos e de qualidade do sistema.
