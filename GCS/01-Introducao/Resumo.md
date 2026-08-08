# Resumo — Gerenciamento de Configuração: Fundamentos (Aula 01)

> Prof. Diego Augusto Barros. Cobre: origem e conceito, evolução histórica, definições formais (SWEBOK), os 3 pilares da GCS, evolução no desenvolvimento de software, fluxo de trabalho e atividades, a área de conhecimento de Gerência de Configuração de Software (GCS) com seus 7 tópicos, e os 10 benefícios.

---

## 📖 Origem e Conceito: "Configuração" e "Configurar"

**O que é / Definição para prova:** o termo vem do dicionário (Priberam). **Configuração** (substantivo): (1) forma exterior dos corpos; (2) figura que apresenta um grupo de coisas dispostas em certa ordem = composição, disposição; (3) ato ou efeito de configurar; (4) **conjunto de opções ou parâmetros estabelecidos para um programa ou sistema informático ou para um equipamento**. **Configurar** (verbo): (1) dar forma ou figura a; (2) representar; (3) **ajustar ou definir opções ou parâmetros num programa ou sistema informático ou num equipamento**.

A ideia central, em todas as acepções, é **organização de elementos numa disposição específica** — isso é a base de tudo que vem depois no material.

🧠 **Memorizar:** configuração = conjunto de opções/parâmetros de um sistema; configurar = ajustar/definir esses parâmetros.

---

## 📖 Gerência de Configuração (GC): definição geral

**O que é / Definição para prova:** **"a Gerência de Configuração refere-se à organização e ao gerenciamento dos elementos que compõem um sistema."** Formalmente, um **sistema** pode ser definido como a **combinação de elementos interativos organizados para atingir um ou mais propósitos específicos**.

A **configuração de um sistema** tem duas leituras complementares, ambas citadas no material:
1. **Características funcionais e físicas** de *hardware* ou *software*, estabelecidas na documentação técnica ou presentes em um produto final.
2. **Conjunto de versões específicas** de *hardware*, *firmware* ou *software*, combinadas de acordo com procedimentos definidos para atender a um objetivo particular.

A partir daí, a **Gerência de Configuração** é definida como: **"a disciplina que identifica a configuração de um sistema em pontos distintos no tempo."** Ou seja: não é uma foto única — é acompanhar como a configuração de um sistema muda ao longo do tempo.

🧠 **Memorizar:** sistema = elementos interativos organizados para um propósito; GC = identificar a configuração de um sistema em pontos distintos no tempo.

---

## 📖 Evolução Histórica da Gerência de Configuração

**O que é:** a GC surgiu da necessidade humana de **produzir cópias quase idênticas** de produtos tangíveis e intangíveis. Ao longo da história, o conceito de "**quase idêntico**" variou muito em termos de **precisão** — é essa variação de precisão, e a necessidade crescente de **padronização** para coordenação e eficiência, que conecta todos os exemplos históricos do material.

**Linha do tempo de exemplos:**
- **210 a.C.** — as pontas de flecha associadas aos guerreiros de terracota (China) apresentavam variações de tamanho de menos de 1 cm até 0,22 mm, mas eram consideradas peças idênticas para o padrão de precisão da época.
- **Guerras Púnicas (264 a 146 a.C.)** — componentes substituíveis de quilhas de navios cartagineses (identificados em restos arqueológicos no Museu de Marsala, Itália) já atendiam a critérios de **substitutibilidade** da época.
- **Mundo antigo — calendários** (padronização baseada em movimentos do sol/lua/estrelas): civilizações antigas (maias/astecas) criaram calendários baseados nesses movimentos; os **egípcios** tinham um calendário solar de **365 dias**, um dos primeiros calendários conhecidos da humanidade, usado para prever as inundações anuais do Nilo; os **babilônios** usavam um **Calendário Lunissolar de 354 dias** (meses de 20 a 30 dias, baseado nos ciclos da lua e do sol), usado junto com um calendário administrativo de 360 dias para fins fiscais e astronômicos.
- **Revolução Industrial** — a padronização dos trilhos ferroviários nos EUA permitiu o transporte eficiente de mercadorias e foi adotada como padrão em **1886**.
- **Século XX** — grandes incêndios, como o de **Baltimore em 1904**, evidenciaram a necessidade de padrões nacionais para equipamentos de combate a incêndio, levando à criação de **acoplamentos de mangueiras padronizados** (antes disso, mangueiras de cidades diferentes não se conectavam entre si, dificultando o combate a incêndios que exigiam ajuda externa).
- **Século XXI** — a produção e distribuição de **cópias exatas de software** é prática comum; com a distribuição digital, empresas usam **containers Docker, máquinas virtuais na nuvem e lojas de aplicativos** para garantir que todos os usuários recebam versões idênticas do software.

⚠️ **Pegadinha:** o fio condutor de todos esses exemplos é sempre o mesmo — a **padronização** como resposta às necessidades de **coordenação e eficiência** de cada época, não um exemplo isolado.

🧠 **Memorizar:** terracota (210 a.C., pontas de flecha) → navios cartagineses (Guerras Púnicas) → calendários antigos (egípcio 365 dias, babilônico 354 dias) → trilhos ferroviários (1886) → mangueiras de incêndio (Baltimore 1904) → containers/VMs/lojas de app (hoje).

---

## 📖 Definição Formal de Gerência de Configuração (SWEBOK)

**O que é / Definição para prova:** segundo o **SWEBOK V3.0** (*Software Engineering Body of Knowledge*, guia de referência da IEEE sobre conhecimento em engenharia de software), a Gerência de Configuração é a **"disciplina que aplica direção técnica e administrativa, e supervisão para:**
1. **Identificar e documentar** as características funcionais e físicas de um item de configuração;
2. **Controlar alterações** nessas características;
3. **Registrar e relatar** o processamento e status de implementação de mudanças;
4. **E verificar a conformidade** com os requisitos especificados."

Essa definição formal é, na prática, um detalhamento em 4 passos da ideia mais simples vista no tópico anterior (identificar a configuração ao longo do tempo).

🧠 **Memorizar:** 4 passos SWEBOK — identificar/documentar → controlar alterações → registrar/relatar → verificar conformidade.

---

## 📖 Gerência de Configuração de Software (GCS)

**O que é / Definição para prova:** a **Gerência de Configuração de Software** (**GCS**, ou em inglês *Software Configuration Management* — **SCM**) é uma disciplina voltada para o **gerenciamento da evolução de sistemas computacionais**, em **todas as fases do ciclo de vida** de desenvolvimento desses sistemas. É um **processo de apoio ao ciclo de vida do software** que beneficia atividades de Gerência de Projetos, Desenvolvimento, Manutenção, Garantia de Qualidade, além dos próprios clientes e usuários do produto final.

Uma segunda definição, mais informal, complementa: **"é a arte de identificar, organizar e controlar modificações no software que está sendo construído por uma equipe de programação."** O objetivo é **maximizar a produtividade minimizando erros**.

🧠 **Memorizar:** GCS = SCM; gerencia a evolução de sistemas em todo o ciclo de vida; objetivo = maximizar produtividade, minimizar erros.

---

## 📖 Gerência de Configuração x Qualidade de Software

**O que é / Definição para prova:** a Gerência de Configuração de Software está **intimamente relacionada** à atividade de **Garantia de Qualidade de Software** (*Software Quality Assurance* — **SQA**). A Garantia de Qualidade consiste em garantir que produtos e processos de software atendam aos requisitos especificados, planejando, executando e realizando atividades relacionadas à qualidade, incorporando confiança na qualidade do software por meio dessas atividades.

**Como se relacionam:** as atividades de GCS **contribuem diretamente** para alcançar os objetivos da Garantia da Qualidade de Software. Em alguns contextos de projeto, requisitos específicos de Qualidade de Software **determinam** certas atividades de GCS — ou seja, a relação é de mão dupla: a qualidade se apoia na GCS, e às vezes a qualidade dita o que a GCS precisa fazer.

**Contexto:** muitas organizações de software ainda enfrentam dificuldades em desenvolver e entregar produtos confiáveis e usáveis, dentro dos limites de orçamento e prazo. A GCS oferece os meios para gerenciar os processos de software de maneira **estruturada, ordenada e produtiva**, abrangendo todas as áreas do ciclo de vida de software e impactando tanto os dados quanto os processos.

🧠 **Memorizar:** GCS e SQA (Garantia de Qualidade) são intimamente ligadas; atividades de GCS ajudam a atingir objetivos de SQA.

---

## 📖 Os 3 Pilares da Gerência de Configuração de Software

**O que é / Definição para prova:** como disciplina de engenharia, a GCS oferece **3 pilares fundamentais** para a organização: **Suporte**, **Controle** e **Serviço**.

| Pilar | O que envolve |
|---|---|
| **1. Suporte** | A GCS apoia diretamente: os engenheiros e desenvolvedores dos programas; o programa em si; a corporação; e, em alguns casos, o cliente. |
| **2. Controle** | A GCS gerencia e controla: especificações, documentos e desenhos; requisitos e ferramentas; software e outros itens entregáveis. |
| **3. Serviço** | A GCS também atua como provedora de serviços: apoiando pessoas e gerenciando dados. Garante que a equipe de GCS (a) seja bem treinada e tenha os recursos necessários (orçamento e ferramentas) para trabalhar com eficiência/eficácia; (b) mantenha um equilíbrio adequado entre controle e suporte, ajustado às necessidades de cada programa; (c) seja flexível o suficiente para atender às mudanças nas demandas de desenvolvedores, clientes, programas e da própria empresa. |

⚠️ **Pegadinha:** os 3 pilares não são etapas sequenciais — são **dimensões simultâneas** de atuação da GCS dentro da organização (suportar pessoas, controlar artefatos, prestar serviço).

🧠 **Memorizar:** Suporte (pessoas/programa/corporação) → Controle (especificações/requisitos/entregáveis) → Serviço (apoio + gestão de dados + equilíbrio + flexibilidade).

---

## 📖 A Evolução da GCS no Desenvolvimento de Software

**O que é / Definição para prova:** o **processo** de Gerência de Configuração de Software **não mudou significativamente** nas últimas décadas — mas o **ambiente** no qual a GCS opera mudou (e continua mudando) de forma muito significativa.

**Como funciona (a mudança de ambiente):** migramos de **mainframes centralizados**, que usavam poucas linguagens de programação (como **COBOL** e **FORTRAN** — ex.: o IBM 4381, comercializado entre 1979 e 1992), para **ambientes descentralizados, em rede e baseados na Web**, com milhares de dispositivos usando **centenas de pacotes de software** e **dezenas de linguagens de programação**. Os impactos mais significativos na GCS se concentraram nas **ferramentas automatizadas** e nos **sistemas de bibliotecas** sobre os quais elas operam.

**Ferramentas de controle de versão dos anos 1990** (quando o foco da GCS estava quase inteiramente no controle de versões, com poucas opções de fornecedores no mercado):

| Ferramenta | O que era |
|---|---|
| **SCCS** (*Source Code Control System*) | Criado nos anos 1970, uma das primeiras ferramentas de controle de versão, funcionalidades básicas |
| **RCS** (*Revision Control System*) | Originalmente 1982, muito usado até os anos 1990; controle de versão para arquivos individuais, mas não suportava bem projetos colaborativos grandes |
| **CVS** (*Concurrent Versions System*) | Surgiu no fim dos anos 1980, amplamente adotado nos anos 1990 |
| **PVCS** (*Polytron Version Control System*) | Ferramenta comercial popular nos anos 1990, focada em controle de versão e gerenciamento de mudanças em ambientes corporativos |
| **ClearCase** | Desenvolvido pela Atria Software (depois adquirida pela IBM), ganhou espaço nos anos 1990 como ferramenta robusta de controle de versão e gerenciamento de configuração |
| **VSS** (*Visual SourceSafe*) | Lançado pela Microsoft nos anos 1990, integrado ao ecossistema Windows, usado por equipes em projetos .NET e Visual Studio |

Hoje existem **centenas de ferramentas de GCS**, desde controle de versão simples até soluções avançadas que gerenciam e monitoram todo o ambiente de desenvolvimento e produção de software. **Apesar dessa diversidade**, o **processo** de Gerência de Configuração em si é **basicamente imutável** — apenas os **elementos gerenciados** mudam.

⚠️ **Pegadinha (frase-chave para prova):** "**O ponto-chave está no PROCESSO**" — a prova pode perguntar diretamente o que não mudou na GCS ao longo do tempo, e a resposta é: o processo (identificar, controlar, gerenciar mudanças) continua o mesmo; o que muda são as ferramentas e os elementos gerenciados.

🧠 **Memorizar:** mainframes/COBOL-FORTRAN (até 1990, foco em controle de versão) → ambientes web descentralizados (hoje, centenas de ferramentas); processo não muda, só os elementos gerenciados.

---

## 📖 Fluxo de Trabalho do Gerenciamento de Configuração

**O que é / Definição para prova:** ao longo do ciclo de vida do projeto, as mudanças no software são **identificadas, controladas e gerenciadas**, seguindo um ciclo de 4 etapas que se repete continuamente:

1. **Identificar Mudança**
2. **Controlar Mudança**
3. **Analisar Implementação** — garantir que a mudança esteja sendo implementada adequadamente
4. **Reportar Mudança** → leva a **Publicar/Implantar**, e o ciclo recomeça na etapa 1

Esse fluxo é análogo, em espírito, a outros ciclos de melhoria contínua vistos em outras disciplinas (como o PDCA) — a ideia central é que a gestão de mudanças **nunca para**, ela se repete a cada nova mudança identificada no software.

🧠 **Memorizar:** ciclo de 4 etapas — Identificar → Controlar → Analisar Implementação → Reportar (→ Publicar/Implantar → volta ao início).

---

## 📖 Atividades de Gerenciamento de Configuração

**O que é / Definição para prova:** o Gerenciamento de Configuração se organiza em **4 atividades centrais**, dispostas como um diagrama de fluxo: componentes/versões de componentes alimentam o **Controle de Versão** e a **Construção de Sistema**, que juntos geram **versões de sistema**; essas versões de sistema alimentam o **Gerenciamento de Mudanças** (que também recebe propostas de mudanças) e o **Gerenciamento de Lançamentos**, que juntos geram os **lançamentos do sistema**.

| Atividade | O que envolve |
|---|---|
| **1. Controle de Versão** | Controlar as diversas versões dos componentes do sistema; garantir que as alterações feitas por diferentes desenvolvedores não interfiram umas com as outras. |
| **2. Construção de Sistema** | Processo de reunir componentes, dados e bibliotecas do programa, **compilando-os e ligando-os** para criar um sistema executável. |
| **3. Gerenciamento de Mudanças** | Manter o controle de solicitações de mudança de clientes e desenvolvedores no software já entregue; elaborar custos e impactos das mudanças propostas; decidir **se e quando** as alterações devem ser implementadas. |
| **4. Gerenciamento de Lançamentos (*Releases*)** | Preparação de software para lançamento externo; acompanhamento das versões do sistema lançadas para uso do cliente. |

🧠 **Memorizar:** Controle de Versão + Construção de Sistema → versões de sistema → Gerenciamento de Mudanças + Gerenciamento de Lançamentos → lançamentos do sistema.

---

## 📖 A Área de Conhecimento de Gerência de Configuração de Software

**O que é / Definição para prova:** a área de conhecimento de GCS está relacionada a **todas as outras áreas de conhecimento da Engenharia de Software** (Fundamentos de Engenharia, Requisitos, Projeto, Construção, Teste, Manutenção, Modelos e Métodos, Processo, Gerenciamento, Qualidade e Engenharia Econômica de Software) — porque o **objeto** da Gerência de Configuração é o **artefato** produzido e utilizado ao longo de **todo** o processo de Engenharia de Software, e artefatos existem em todas essas áreas.

Segundo o **SWEBOK**, o Gerenciamento de Configuração de Software se organiza em **7 tópicos**:

1. Gerenciamento do Processo de GCS
2. Identificação de Configuração de Software
3. Controle de Configuração de Software
4. Contabilidade do Status de Configuração de Software
5. Auditoria de Configuração de Software
6. Gerenciamento de Lançamento e Entrega de Software
7. Ferramentas de GCS

### 1. Gerenciamento do Processo de GCS

A GCS controla a **evolução e a integridade** de um produto ao: identificar seus elementos; gerenciar e controlar mudanças; verificar, registrar e reportar informações de configuração. Do ponto de vista do engenheiro de software, a GCS **facilita** atividades de desenvolvimento e implementação de mudanças. Uma implementação bem-sucedida de GCS **requer planejamento cuidadoso e gerenciamento eficiente**, exigindo compreender o **contexto organizacional** e as **restrições** impostas ao projeto e à implementação do processo de GCS.

### 2. Identificação de Configuração de Software

Consiste em: identificar os itens que serão controlados; estabelecer esquemas de identificação para os itens e suas versões; definir as ferramentas e técnicas usadas na aquisição e no gerenciamento desses itens. ⚠️ **Pegadinha:** essas atividades **fornecem a base para todas as outras atividades da GCS** — é frequentemente citada como o "alicerce" dos outros 6 tópicos.

### 3. Controle de Configuração de Software

Relacionado ao gerenciamento de mudanças durante o ciclo de vida do software. Envolve: o processo para **determinar quais mudanças devem ser feitas**; a **autoridade para aprovar** determinadas mudanças; o **suporte à implementação** dessas mudanças; e o conceito de **desvios formais** em relação aos requisitos do projeto, bem como **isenções** desses desvios. As informações derivadas dessas atividades são úteis para medir o **tráfego de mudanças**, o **impacto de alterações** (*breakage*) e aspectos relacionados ao **retrabalho**.

### 4. Contabilidade do Status de Configuração de Software

Em inglês, ***Software Configuration Status Accounting* (SCSA)**. Consiste em **registrar e reportar** as informações necessárias para gerenciar uma configuração de maneira **eficaz** — é a parte da GCS voltada a manter um "histórico documentado" confiável do que está acontecendo com a configuração.

### 5. Auditoria de Configuração de Software

**O que é / Definição para prova:** é um **exame independente** de um produto ou conjunto de produtos, que avalia a **conformidade** com especificações, padrões, acordos contratuais ou outros critérios. As auditorias são realizadas seguindo um processo bem definido, com diferentes papéis e responsabilidades para os auditores. Cada auditoria deve ser planejada cuidadosamente e pode exigir várias pessoas desempenhando diferentes tarefas em um curto período de tempo; ferramentas podem apoiar significativamente o planejamento e a condução da auditoria, e auditorias informais podem ser conduzidas em pontos-chave do ciclo de vida.

A auditoria de configuração de software determina **até que ponto um item satisfaz as características funcionais e físicas requeridas**. Duas **auditorias formais** podem ser exigidas por contratos que abrangem softwares críticos:

| Auditoria | O que verifica |
|---|---|
| **FCA — Auditoria de Configuração Funcional** | Avalia se os **requisitos funcionais** foram atendidos |
| **PCA — Auditoria de Configuração Física** | Verifica se o produto corresponde às **especificações físicas documentadas** |

A conclusão bem-sucedida dessas auditorias pode ser um **pré-requisito** para estabelecer a ***baseline*** (linha de base) do produto.

⚠️ **Pegadinha:** FCA = **F**uncional → requisitos **f**uncionais; PCA = **F**ísica → especificações **f**ísicas. Fácil de trocar se não prestar atenção.

### 6. Gerenciamento de Lançamento e Entrega de Software

No contexto da GCS, "**versão**" refere-se à **distribuição** de um item de configuração de software **para fora do ambiente de desenvolvimento** — isso inclui tanto versões internas quanto distribuições para clientes. Quando diferentes versões de um item de software estão disponíveis (ex.: um produto para diferentes plataformas ou com capacidades distintas), pode ser necessário **recriar versões específicas** e **empacotar os materiais corretos** para a entrega. As **bibliotecas de software** desempenham um papel crucial na realização das tarefas de gerenciamento e entrega de versões.

### 7. Ferramentas de Gerência de Configuração de Software

Com base no **escopo de suporte**, as ferramentas de GCS podem ser classificadas em **3 categorias**:

| Categoria | Para quem serve | Exemplos |
|---|---|---|
| **1. Suporte Individual** | Organizações pequenas ou grupos de desenvolvimento sem variações complexas nos produtos | **Controle de versão:** Git, Subversion, Bazaar, Mercurial, Perforce, CVS. **Compilação/construção:** CMake, Maven, Gradle, Grunt, Bazel, webpack, Gulp (avançadas: Travis CI, Jenkins, CircleCI, GitLab — fazem verificação de qualidade, testes de regressão, geração de relatórios). **Controle de mudanças:** ServiceNow, Jira |
| **2. Suporte a Projetos** | Organizações de médio a grande porte, com variantes de produtos e desenvolvimento paralelo, **sem** requisitos de certificação | GitHub, GitLab, Bitbucket — focadas na gestão de espaços de trabalho para equipes de desenvolvimento e integradores, com suporte a ambientes de desenvolvimento distribuídos |
| **3. Suporte a Processos Organizacionais** | Organizações **com processos formais**, incluindo requisitos de certificação | Rational ClearCase (IBM Engineering Workflow Management) — automatizam partes de processos organizacionais, oferecendo suporte para gerenciamento de fluxos de trabalho, papéis e responsabilidades |

🧠 **Memorizar:** os 7 tópicos SWEBOK da área de GCS (Processo, Identificação, Controle, Contabilidade do Status, Auditoria, Lançamento/Entrega, Ferramentas); FCA=funcional, PCA=física; 3 categorias de ferramentas por escopo (individual → projetos → processos organizacionais).

---

## 📖 10 Benefícios do Gerenciamento de Configuração de Software

**O que é:** praticar GCS oferece muitos benefícios para desenvolvedores, testadores, gerentes de projetos, profissionais de Garantia de Qualidade (QA) e clientes.

1. Organiza e mantém a **integridade** do software;
2. Ajuda no **gerenciamento de ativos** e **rastreamento de mudanças**;
3. Garante **configurações compatíveis** e **implementações corretas**;
4. Facilita a **rastreabilidade** desde os requisitos até o produto final;
5. Reduz **custos de manutenção** e **riscos legais**;
6. Melhora a **conformidade** com padrões e requisitos do cliente;
7. Proporciona um **ambiente estável e mensurável** para desenvolvimento;
8. Facilita **auditorias**, geração de relatórios e **comunicação** entre equipes;
9. Permite **reproduzir condições de produção** e identificar **responsabilidades**;
10. Contribui para **melhorias contínuas** e entrega de software de **alta qualidade**.

🧠 **Memorizar:** os 10 benefícios giram em torno de 4 grandes temas — integridade/rastreabilidade, redução de custo/risco, conformidade/auditoria, melhoria contínua.

---

## 📚 Resumão Final

- **Configuração** = conjunto de opções/parâmetros de um sistema; **Gerência de Configuração (GC)** = identificar a configuração de um sistema em pontos distintos no tempo (ver tópicos Origem e Definição de GC).
- A GC nasceu da necessidade humana de produzir **cópias quase idênticas**; a **padronização** sempre esteve ligada a necessidades de coordenação e eficiência (guerreiros de terracota, navios cartagineses, calendários antigos, trilhos ferroviários, mangueiras de incêndio, containers/software hoje).
- Definição formal SWEBOK: identificar/documentar → controlar alterações → registrar/relatar → verificar conformidade.
- **GCS (SCM)** = disciplina que gerencia a evolução de sistemas computacionais em todo o ciclo de vida, apoiando projeto, desenvolvimento, manutenção, qualidade e clientes; intimamente ligada à **SQA** (Garantia de Qualidade de Software).
- **3 pilares da GCS**: Suporte (pessoas/programa/corporação), Controle (especificações/requisitos/entregáveis), Serviço (apoio + dados + equilíbrio + flexibilidade).
- O **processo** de GCS não mudou nas últimas décadas — só o **ambiente** e as **ferramentas** mudaram (de mainframes/COBOL-FORTRAN a ambientes web descentralizados com centenas de ferramentas).
- **Fluxo de trabalho**: Identificar → Controlar → Analisar Implementação → Reportar Mudança → Publicar/Implantar (ciclo contínuo).
- **4 atividades centrais**: Controle de Versão, Construção de Sistema, Gerenciamento de Mudanças, Gerenciamento de Lançamentos.
- A **área de conhecimento de GCS** (SWEBOK) tem **7 tópicos**: Gerenciamento do Processo, Identificação, Controle, Contabilidade do Status, Auditoria (FCA/PCA), Gerenciamento de Lançamento e Entrega, e Ferramentas (3 categorias: Suporte Individual, a Projetos, a Processos Organizacionais).
- **10 benefícios** da GCS: integridade, rastreabilidade, menor custo/risco, conformidade, ambiente estável, auditorias facilitadas, reprodutibilidade, melhoria contínua.

## ⚠️ Pontos que podem cair na prova

- As definições formais (dicionário, SWEBOK de GC, SWEBOK de GCS) — palavra por palavra, são bem cobráveis.
- Os **3 pilares** da GCS (Suporte, Controle, Serviço) e o que cada um envolve.
- Os **7 tópicos** da área de conhecimento de GCS, na ordem, e o detalhe de cada um (especialmente FCA x PCA na Auditoria).
- A frase "o processo não muda, só o ambiente/elementos gerenciados mudam" — ponto conceitual central do material.
- As **3 categorias de ferramentas de GCS** por escopo de suporte, com exemplos de cada.
- O fluxo de 4 etapas do Gerenciamento de Configuração e as 4 atividades centrais (Controle de Versão, Construção, Mudanças, Lançamentos).

## 📝 Perguntas para revisão

1. Defina Gerência de Configuração (GC) e explique o que é a "configuração de um sistema".
2. Qual a definição formal de Gerência de Configuração segundo o SWEBOK, com seus 4 elementos?
3. O que é Gerência de Configuração de Software (GCS/SCM), e como ela se relaciona com a Garantia de Qualidade de Software (SQA)?
4. Quais são os 3 pilares da GCS, e o que cada um envolve?
5. O que mudou e o que não mudou na GCS ao longo das últimas décadas?
6. Quais são as 4 atividades centrais de Gerenciamento de Configuração, e como elas se conectam entre si?
7. Cite os 7 tópicos da área de conhecimento de GCS segundo o SWEBOK.
8. Diferencie Auditoria de Configuração Funcional (FCA) de Auditoria de Configuração Física (PCA).
9. Quais são as 3 categorias de ferramentas de GCS, com base no escopo de suporte? Dê um exemplo de cada.
10. Cite três benefícios do Gerenciamento de Configuração de Software.

### Gabarito

1. GC é a disciplina que identifica a configuração de um sistema em pontos distintos no tempo. A configuração de um sistema é o conjunto de características funcionais e físicas de hardware/software, ou o conjunto de versões específicas de hardware/firmware/software combinadas para atender a um objetivo.
2. É a disciplina que aplica direção técnica e administrativa, e supervisão para: (1) identificar e documentar as características funcionais e físicas de um item de configuração; (2) controlar alterações nessas características; (3) registrar e relatar o processamento e status de implementação de mudanças; (4) verificar a conformidade com os requisitos especificados.
3. GCS é a disciplina que gerencia a evolução de sistemas computacionais em todas as fases do ciclo de vida de desenvolvimento, apoiando gerência de projetos, desenvolvimento, manutenção, garantia de qualidade e clientes. Está intimamente relacionada à SQA: as atividades de GCS contribuem diretamente para os objetivos da Garantia de Qualidade, e requisitos de qualidade às vezes determinam atividades específicas de GCS.
4. Suporte (apoia engenheiros/desenvolvedores, o programa, a corporação e, às vezes, o cliente), Controle (gerencia especificações, documentos, requisitos, ferramentas e entregáveis) e Serviço (atua como provedora de serviços, apoiando pessoas e gerenciando dados, garantindo equipe bem treinada, equilíbrio entre controle/suporte e flexibilidade às mudanças de demanda).
5. O ambiente mudou muito (de mainframes centralizados com poucas linguagens, como COBOL e FORTRAN, para ambientes descentralizados, em rede e baseados na Web, com centenas de pacotes e dezenas de linguagens) e as ferramentas evoluíram (de SCCS/RCS/CVS dos anos 1990 para centenas de ferramentas hoje). O que não mudou foi o processo de GCS em si, que é basicamente imutável — só os elementos gerenciados mudam.
6. Controle de Versão (controla versões dos componentes) e Construção de Sistema (compila/liga componentes em um executável) geram as versões de sistema; essas versões alimentam o Gerenciamento de Mudanças (controla solicitações de mudança) e o Gerenciamento de Lançamentos (prepara/acompanha versões lançadas), que geram os lançamentos do sistema.
7. Gerenciamento do Processo de GCS, Identificação de Configuração de Software, Controle de Configuração de Software, Contabilidade do Status de Configuração de Software, Auditoria de Configuração de Software, Gerenciamento de Lançamento e Entrega de Software, e Ferramentas de GCS.
8. FCA (Auditoria de Configuração Funcional) avalia se os requisitos funcionais foram atendidos; PCA (Auditoria de Configuração Física) verifica se o produto corresponde às especificações físicas documentadas. Ambas podem ser exigidas por contratos de softwares críticos, e sua conclusão bem-sucedida pode ser pré-requisito para estabelecer a baseline do produto.
9. Suporte Individual (organizações pequenas, sem variações complexas — ex.: Git, Maven, Jira); Suporte a Projetos (médio/grande porte, com variantes de produto, sem certificação — ex.: GitHub, GitLab, Bitbucket); Suporte a Processos Organizacionais (organizações com processos formais e requisitos de certificação — ex.: Rational ClearCase).
10. Exemplos válidos: organiza e mantém a integridade do software; facilita a rastreabilidade desde requisitos até o produto final; reduz custos de manutenção e riscos legais; melhora conformidade com padrões e requisitos do cliente; facilita auditorias e comunicação entre equipes.
