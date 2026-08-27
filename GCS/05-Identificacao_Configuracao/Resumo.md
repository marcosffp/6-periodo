# Identificação de Configuração de Software

## 📖 O que é a Identificação de Configuração

A **Identificação de Configuração** é a primeira das atividades da Gerência de Configuração de Software (GCS, junto com Controle de Configuração, Contabilidade do Status e Verificação/Auditoria). Ela **estabelece e mantém, de forma incremental, a base definitiva para o controle e a contabilidade do status de um sistema e de seus Itens de Configuração (ICs)**. Na prática, pense nela como o processo de "batizar e catalogar" tudo que compõe um produto de software: antes de controlar mudanças ou auditar algo, é preciso primeiro saber exatamente o que existe, como se chama e qual versão é.

Consiste em três frentes de trabalho:
- Identificar os itens que serão controlados;
- Estabelecer esquemas de identificação para os itens e suas versões;
- Definir as ferramentas e técnicas usadas na aquisição e no gerenciamento desses itens.

Essa atividade **abrange todo o ciclo de vida do sistema** (desenvolvimento, produção, implantação e suporte operacional) e permanece ativa **até a desmilitarização e/ou descarte do sistema**. Ela também garante o uso de conjuntos comuns de documentação em todos os processos e serve como base para: desenvolvimento de novos sistemas, modificação de componentes existentes, aquisição de produtos para uso operacional e suporte ao sistema e seus componentes.

O processo de identificação inclui **identificadores**, que funcionam como referências abreviadas (uma espécie de "apelido único") para itens e documentação, evitando ambiguidade sobre a que exatamente um documento ou peça se refere.

🧠 **Memorizar:** base definitiva do controle · ciclo de vida completo até o descarte · identificadores = referências abreviadas.

## 📖 Como a Identificação de Configuração se relaciona com as outras atividades de GCS

A identificação eficaz de configuração é um **pré-requisito** para as demais atividades de GCS: Controle de Configuração, Contabilidade do Status de Configuração e Verificação e Auditoria de Configuração. Isso acontece porque todas essas atividades dependem dos produtos (itens identificados, documentação, baselines) resultantes do processo de identificação. Se os Itens de Configuração (ICs) e sua documentação associada não forem devidamente identificados, torna-se impossível: controlar mudanças na configuração dos itens; estabelecer registros e relatórios precisos; e validar a configuração por meio de auditorias.

🧠 **Memorizar:** identificação vem antes de tudo — sem ela, controle, contabilidade e auditoria não têm o que rastrear.

## 📖 O padrão EIA-649

O **ANSI/EIA-649** foi desenvolvido em 1994 pelo Comitê G-33 da Electronic Industries Alliance (EIA) para estabelecer um padrão de Gerenciamento de Configuração (GC) para a indústria, definindo requisitos gerais, princípios e melhores práticas em GC. É esse padrão que serve de base para os princípios, propósitos e benefícios da identificação de configuração vistos abaixo.

**Características importantes:** o EIA-649 **não impõe terminologia ou abordagens específicas de implementação** e **pode ser aplicado a qualquer ambiente sem restrições metodológicas** — ou seja, é um guia de princípios, não um manual rígido de como fazer.

## 📖 Propósitos e benefícios da Identificação de Configuração

Segundo o padrão EIA 649, a identificação de configuração cumpre uma série de propósitos práticos, todos girando em torno de **organizar, documentar e distinguir** o produto e suas partes:

- **Determina a estrutura hierárquica** do produto, organizando sua documentação de configuração e demais informações;
- **Documenta os atributos** de desempenho, interfaces e outras características do produto;
- **Define o nível adequado de marcação** de identificação do produto e de sua documentação;
- **Garante uma identificação única** para um produto ou seus componentes, e **atribui identificação exclusiva** para os documentos técnicos que o descrevem;
- **Modifica a identificação** do produto e da documentação para refletir mudanças significativas, mantendo o **controle de liberação de documentos** para a gestão de baselines;
- **Distingue entre versões do produto** para usuários ou equipes de manutenção;
- **Correlaciona um produto com suas instruções** de uso ou manutenção, e **facilita a gestão da informação** (incluindo dados em formato digital);
- **Relaciona unidades individuais do produto** com garantias e obrigações de vida útil;
- **Associa o nível de revisão** de documentos à versão do produto ou configuração;
- **Fornece um ponto de referência** para definição de mudanças e ações corretivas.

🧠 **Memorizar:** estrutura hierárquica · atributos · marcação e identificação única · controle de liberação/versões · ponto de referência para mudanças.

## 📖 O Processo de Identificação de Configuração — visão geral (7 elementos)

O padrão organiza a identificação de configuração em sete elementos/atividades principais:

1. **Seleção de Itens de Configuração (ICs)**
2. **Definição da Documentação de Configuração**
3. **Autoridade de Controle de Configuração**
4. **Atribuição de Identificadores**
5. **Manutenção da Identificação de Configuração**
6. **Liberação de Documentação de Configuração**
7. **Estabelecimento de Linhas de Base de Configuração**

Cada elemento tem seu papel: (1) selecionar ICs em níveis apropriados da estrutura do produto para facilitar documentação, controle e suporte; (2) definir a documentação que serve de base para desenvolvimento, aquisição, fabricação/montagem, inspeção/testes e manutenção; (3) definir quem tem autoridade sobre cada documento de configuração, alinhada ao planejamento logístico do IC; (4) emitir identificadores para os ICs e sua documentação; (5) manter essa identificação ao longo do tempo, facilitando o suporte logístico eficaz; (6) liberar (tornar disponível) a documentação de configuração; e (7) estabelecer as linhas de base para o controle de configuração dos ICs.

⚠️ **Pegadinha:** esse esquema de 7 elementos é uma enumeração mais "estática" (o que precisa existir). O PDF também apresenta um **modelo de atividades do processo com 5 passos sequenciais** (próxima seção) — são duas formas de organizar praticamente o mesmo conteúdo, não conceitos concorrentes. Em prova, preste atenção em qual das duas listas está sendo cobrada.

## 📖 Modelo de Atividade do Processo de Identificação de Configuração (5 passos)

Este é o fluxo prático, sequencial, de como a identificação de configuração é executada:

1. **Estruturar Produto**
2. **Determinar Itens de Configuração**
3. **Selecionar Documentação e Baselines**
4. **Identificar e Reidentificar Documentos e Itens**
5. **Aprovar Lançamento e Documentação de Baseline**

Cada passo, no padrão EIA-649, é descrito com **Restrições** (o que limita/direciona a atividade), **Facilitadores** (o que auxilia) e **Saída** (o que a atividade produz) — muito cobrável em prova por associar cada etapa aos seus insumos/produtos.

### 1. Estruturar Produto

**O que é:** também chamada de **arquitetura do sistema**, essa etapa define os identificadores, a estrutura interna e o relacionamento entre os componentes do sistema, além de sua documentação de configuração. Conforme um programa avança, a engenharia de sistemas define a composição funcional e física da arquitetura até o nível necessário para especificar e controlar o desempenho dos itens. É nesse nível mais detalhado que os ICs são designados, especialmente durante a fase de Desenvolvimento de Engenharia e Manufatura.

**Restrições:** requisitos de Engenharia de Sistemas; análise funcional; alocação e síntese. **Facilitadores:** disposições contratuais.

**Como é representada:** graficamente, como uma **árvore hierárquica** ou uma **listagem indentada**. As ferramentas de gerenciamento usadas incluem especificações, árvores desenhadas e **Estruturas de Decomposição do Trabalho (WBS — Work Breakdown Structure)**, que são visões da estrutura do produto relacionadas diretamente aos ICs.

**O que é o WBS:** uma visão estruturada da família de produtos, abrangendo hardware, software, serviços, dados e instalações. A estrutura do WBS estabelece a relação entre os elementos de trabalho a serem realizados e o produto final — e é dentro dessa estrutura que os ICs são identificados como elementos do WBS.

🧠 **Memorizar:** arquitetura do sistema · árvore hierárquica ou lista indentada · WBS = hardware+software+serviços+dados+instalações.

### 2. Determinar Itens de Configuração

**O que é:** os **Itens de Configuração (ICs)** são as unidades fundamentais da gestão de configuração. A seleção de ICs separa os componentes do sistema em subconjuntos identificáveis para facilitar o gerenciamento do desenvolvimento. Ocorre no **início do processo de aquisição** e tem impacto duradouro em várias áreas: gerenciamento do programa, engenharia de sistemas, logística de aquisição e gerenciamento de configuração. A escolha dos ICs define os níveis de controle de configuração ao longo de todo o ciclo de vida do sistema.

**Restrições:** disposições contratuais. **Facilitadores:** nenhum. **Saída:** itens de configuração selecionados; requisitos alocados.

**Critérios de seleção:** a seleção de ICs exige bom julgamento em engenharia de sistemas, levando em conta experiência e análise de custo-benefício — **não há regras fixas** para determinar a quantidade ou a melhor escolha de ICs. A decisão deve se basear em orientações gerais, listas de verificação (checklists) e fatores adicionais de contexto. Exemplos de perguntas de um checklist típico: o item é crítico/de alto risco? Implementa capacidades críticas (segurança)? Exige design novo? É hardware ou software? Incorpora tecnologias não comprovadas? Precisa de suporte logístico separado?

⚠️ **Pegadinha:** "quantidade ideal de ICs" não tem fórmula — é sempre julgamento de engenharia baseado em critérios e checklists, nunca uma regra numérica fixa.

🧠 **Memorizar:** unidades fundamentais da GC · seleção ocorre no início da aquisição · sem regras fixas, só critérios/checklist.

### 3. Selecionar Documentação e Baselines

**O que é:** define qual documentação de configuração e quais baselines (linhas de base) serão associadas a cada IC. A documentação de configuração serve como base para controle de configuração, suporte logístico, manutenção pós-implantação e suporte a software.

**Restrições:** disposições contratuais; logística; plano de manutenção. **Facilitadores:** nenhum. **Saída:** configuração apropriada; tipos de documentos e baselines selecionados.

### 4. Identificar e Reidentificar Documentos e Itens

**O que é:** cada documento de configuração, assim como outros documentos, deve possuir um **identificador único**, garantindo a correta associação com o IC correspondente. Os responsáveis por gerenciar essa documentação devem garantir: a atribuição de identificadores únicos (incluindo revisões e versões, quando necessário); a aplicação de marcações restritivas apropriadas; e o controle adequado da liberação de engenharia para novos documentos ou revisões.

**Restrições:** disposições contratuais; alterações de engenharia aprovadas. **Facilitadores:** nenhum. **Saída:** identificadores de documentos e itens atribuídos.

### 5. Aprovar Lançamento e Documentação de Baseline

**O que é:** etapa final, em que se aprova o lançamento (release) e a documentação de baseline correspondente.

**Restrições:** disposições contratuais; documentação de configuração; planejamento de GC; processo de GC documentado. **Facilitadores:** nenhum. **Saída:** as mesmas quatro restrições (disposições contratuais, documentação de configuração, planejamento de GC, processo de GC documentado), agora como produtos formalizados.

**Engenharia de Lançamento (Release):** é o processo que torna a documentação de configuração disponível para uso, seguindo os procedimentos de controle de configuração da organização. Envolve todas as atividades de engenharia de software e deve seguir os procedimentos de liberação de engenharia, que incluem três sub-etapas:

1. **Registro e Rastreabilidade** — registro e rastreamento da documentação de configuração aprovada;
2. **Atualização e Conformidade** — verificação da atualização da documentação para refletir mudanças aprovadas, garantindo rastreabilidade de desvios e modificações;
3. **Verificação de Implementação** — conciliação entre dados de engenharia e manufatura, assegurando que as mudanças foram implementadas e incorporadas nos ICs entregáveis.

🧠 **Memorizar:** release = tornar documentação disponível · 3 sub-etapas: registro/rastreabilidade → atualização/conformidade → verificação de implementação.

## 📖 Item de Configuração (IC) em profundidade

**Definição para prova:** um Item de Configuração (IC) é **qualquer coisa associada a um projeto de software que tenha sido submetida ao controle de configuração** — por exemplo código, dados, diagramas e documentos. Os itens de configuração **sempre têm um identificador único**, independentemente de sua forma, tamanho ou complexidade — e sua configuração deve ser sempre documentada e controlada.

Eles podem ser:
- **Hardware**: aeronaves, navios, tanques, sistemas eletrônicos;
- **Software**: programas, sistemas embarcados, aplicações empresariais;
- **Combinações** de hardware e software;
- **Outros**: equipamentos de teste, munição, sensores, entre outros.

Para cada IC haverá documentação de configuração associada (desde uma especificação de desempenho até um desenho detalhado ou descrição de item comercial), as mudanças na sua configuração serão controladas, registros de status serão mantidos, e auditorias de configuração serão conduzidas para verificar desempenho e configuração do produto — a menos que o IC já tenha uma linha de base estabelecida.

⚠️ **Pegadinha:** definir e controlar o desempenho de um sistema ou IC **não significa** que todos os seus componentes de hardware e software devam necessariamente ser designados individualmente como ICs — a decisão de granularidade é feita caso a caso (ver critérios abaixo).

**Tipos por natureza técnica:**

| HWCI (Hardware Configuration Item) | CSCI (Computer Software Configuration Item) |
|---|---|
| Referência exclusiva a **hardware** | Referência exclusiva a **software** |
| Ex.: aeronave, sensor físico | Ex.: sistema embarcado, aplicação |

Itens de software, por controlarem a funcionalidade de um sistema, geralmente são sempre designados como ICs.

🧠 **Memorizar:** IC = qualquer coisa sob controle de configuração · sempre tem identificador único · HWCI = hardware, CSCI = software.

### Principais razões para designar ICs individualmente

Um componente costuma virar um IC próprio (em vez de ficar "escondido" dentro de outro) quando apresenta pelo menos uma destas características:

- Design crítico, novo ou modificado;
- Funções independentes de uso final;
- Subconjuntos que exigem controle de configuração separado, ou um endereço distinto para a efetividade de mudanças;
- Componentes comuns a vários sistemas;
- Interfaces com outros sistemas, equipamentos ou softwares;
- Necessidade de manter intercambiabilidade em um nível específico;
- Requisitos separados de entrega ou instalação;
- Definição independente de requisitos de desempenho e testes;
- Componentes críticos e de alto risco.

### Consequências de escolher muitos ou poucos ICs

Essa é uma das partes mais "cobráveis" do PDF, pois mostra o trade-off central da seleção de ICs:

| Selecionar ICs demais | Selecionar ICs de menos |
|---|---|
| Muitas interfaces entre ICs precisam ser definidas e documentadas, o que pode restringir a evolução do projeto e dificultar mudanças sem impacto contratual | O aumento da complexidade de cada IC pode diminuir a capacidade de gerenciamento e dificultar a avaliação do progresso |
| Funcionalidade definida em nível muito baixo, gerando restrições de design desnecessárias e exigindo testes/revisões técnicas além do necessário | Se o IC for muito complexo, incluir funções não relacionadas ou misturar hardware e software, surgem problemas: dificuldade de reutilização, complexidade na reaquisição, limitação de fontes de fornecedores |
| Volume total de requisitos documentados desproporcional ao conteúdo técnico, complicando revisão/aprovação/controle e aumentando custos | Testes formais de funcionalidades críticas podem ser adiados ou dificultados; rastreamento da implantação fica difícil, especialmente com componentes distribuídos em locais diferentes |
| Fragmentação excessiva reduz a compreensão do desempenho do sistema, pois a funcionalidade fica dispersa | Complicações para gerenciar mudanças e ações de *retrofit* (modificações, atualizações ou melhorias), especialmente com quantidades diferentes ou componentes entregues separadamente |

Por isso, **em geral, quanto menos ICs, melhor** — desde que cada IC não se torne excessivamente complexo. A regra prática é: analisar fatores como complexidade, uso de novos materiais, processos e introdução de novas tecnologias antes de decidir.

Além disso, **ICs existentes podem ser modificados e designados como uma configuração separada e diferente do IC original**, economizando tempo e dinheiro em vez de criar um IC totalmente novo do zero.

🧠 **Memorizar:** poucos ICs = mais simples de gerenciar, mas cada um fica mais complexo · muitos ICs = mais controle fino, mas mais burocracia e interfaces.

### Atividades associadas a cada IC selecionado (especialmente CSCI)

Cada IC desenvolvido — especialmente os Itens de Configuração de Software (CSCI) — envolve um conjunto de atividades: revisões técnicas, auditorias, demonstrações de verificação de desempenho ou design, testes formais de unidade e integração, além de requisitos documentais. Todas essas atividades elevam os custos de desenvolvimento e exigem armazenamento e manutenção das informações relacionadas. O número de ICs escolhidos determina a quantidade de reuniões separadas relacionadas a essas atividades — um número excessivo de ICs pode levar a atrasos na conclusão de marcos críticos.

## 📖 Documentação de Configuração

A documentação de configuração **caracteriza as informações que definem o desempenho e os atributos funcionais e físicos de um produto**, conforme descrito no padrão EIA 649. Toda outra documentação do produto (manuais de operação e manutenção, decomposição ilustrada de peças, planos e procedimentos de teste) é baseada e relacionada às informações da documentação de configuração. A documentação associada a cada IC fornece a base para: controle de configuração, suporte logístico, pós-implantação e suporte de software.

### Tipos de especificação categorizados por objeto

Existem quatro tipos de especificação, cada um focado em um "objeto" diferente do produto:

1. **Sistema** — define o desempenho geral e os requisitos de missão de um sistema; aloca requisitos para componentes de nível inferior e identifica restrições de interface e interoperabilidade. É a especificação de requisitos funcionais de mais alto nível, usada para estabelecer a **linha de base funcional**.
2. **Item** — define, para um IC, os requisitos de desempenho e interface, e as restrições de design e interoperabilidade que foram alocadas a partir de um sistema ou IC de nível superior. Fornece a base contratual para o desenvolvimento e verificação de desempenho dos ICs. A especificação de desempenho do item normalmente estabelece a **linha de base alocada**.
3. **Software** — documentada por especificações de software, semelhante a uma especificação de requisitos de software; inclui também um conjunto de documentos de design que descrevem o próprio software, o design das interfaces e o design do banco de dados.
4. **Processo** — usada quando um processo ou serviço foi desenvolvido para ser utilizado com um sistema ou item específico, sendo crítico para seu desempenho ou design; a especificação do processo faz parte da linha de base do produto do(s) IC(s).

🧠 **Memorizar:** Sistema→linha de base funcional · Item→linha de base alocada · Software→design (interfaces+BD) · Processo→linha de base do produto.

### Tipos de especificação categorizados por propósito

| Especificação de Desempenho | Especificação Detalhada |
|---|---|
| Define requisitos em termos de **resultados esperados** e critérios para verificar conformidade — não especifica *como* alcançar os requisitos | Contém apenas requisitos detalhados, ou uma mistura de requisitos de desempenho e detalhados |
| Foca em requisitos funcionais, ambiente operacional, interfaces e intercambiabilidade | Diferencia uma solução de design específica de outras concorrentes, com mais detalhes técnicos |
| Objetivo: permitir múltiplas soluções de design, avaliação de produtos concorrentes e inserção de novas tecnologias | Objetivo: oferecer mais detalhes técnicos em comparação com a especificação de desempenho |

O ideal é que uma única especificação contemple tanto os requisitos de desempenho quanto os requisitos detalhados de um item.

## 📖 Linha de Base (Baseline)

**Definição para prova (citação formal, IEEE Std 610.12-1990):** uma baseline é **"uma especificação ou produto que foi formalmente revisado e sobre o qual foi estabelecido acordo, que serve como base para o desenvolvimento subsequente, e que pode ser mudado apenas através de procedimentos de controle de mudança"**.

O conceito de baseline é fundamental para um programa eficaz de GC, mas **não é exclusivo dessa área** — é amplamente utilizada em processos de gestão em geral (ex.: baselines de custo, cronograma e desempenho em gerenciamento de projetos). A ideia central é usar um **ponto de referência conhecido e definido**: para alcançar um objetivo ou para planejar, aprovar ou implementar uma mudança de configuração, é essencial primeiro ter uma definição clara da configuração atual (o "ponto de partida").

Na Gerência de Configuração especificamente, uma baseline de configuração é uma **referência fixa**, estabelecida pela definição e registro da documentação de configuração aprovada para um sistema ou IC, em um marco do projeto ou momento específico. É, em essência, **uma definição de um sistema específico**.

**Características centrais:**
- Baselines são coleções de versões de componentes de um sistema, **controladas e imutáveis** — uma vez estabelecida, as versões dos componentes dentro dela não podem ser alteradas;
- Uma baseline é um conjunto de itens de configuração correlatos e íntegros, formalmente analisados e aprovados;
- É sempre possível **recriar** uma baseline a partir dos seus componentes;
- A baseline especifica as versões de componentes incluídas no sistema e identifica bibliotecas usadas, arquivos de configuração e outras informações do sistema;
- Serve como base para a próxima etapa de trabalho; os itens só podem ser modificados por procedimentos formais de controle e mudança, para garantir sua integridade.

As baselines representam três coisas ao mesmo tempo:
- **"Fotografias"** do estado da configuração de um IC em um determinado instante;
- **Pontos de compromisso/aprovação**, indicando que um IC atingiu um determinado marco no seu desenvolvimento;
- **Pontos de controle**, que exigem a atenção da gestão e auxiliam na tomada de decisão.

⚠️ **Pegadinha:** "imutável" não significa "eterna" — significa que, uma vez fixada, só muda por controle de mudança formal (não é editada livremente); e sempre pode ser recriada a partir de seus componentes originais.

Exemplos de marcos nos quais linhas de base podem ser estabelecidas: **Requisitos, Codificação, Testes, Homologação, Produção**.

**Exemplos de composição de baselines** (o que cada uma tipicamente agrega, de forma cumulativa):

| Baseline de Requisitos | Baseline de Arquitetura | Baseline de Código-Fonte |
|---|---|---|
| Especificação de Requisitos, Protótipos, Casos de Testes | Tudo da anterior + Arquitetura, DER | Tudo da anterior + Código-fonte, Teste Unitário |

🧠 **Memorizar:** baseline = referência fixa e imutável · muda só por controle de mudança formal · = fotografia + ponto de aprovação + ponto de controle.

### Principais tipos de Baseline de Configuração

1. **Baseline Funcional** — documentação aprovada que descreve o desempenho do sistema ou do **Item de Configuração de Nível Superior** (Top-Level CI). Define características funcionais, de interoperabilidade e de interface, e estabelece requisitos de verificação para comprovar que essas características foram atingidas.

2. **Baseline Alocada** — documentação de desempenho aprovada do IC **em desenvolvimento**; descreve as características funcionais e de interface **herdadas** de um IC de nível superior; define os métodos de verificação para garantir conformidade com os requisitos alocados.

3. **Configuração de Desenvolvimento** — conjunto de documentos técnicos internos que definem a **solução de design em evolução** de um IC durante sua fase de desenvolvimento; inclui documentação de hardware e software.

4. **Baseline do Produto** — documentação técnica aprovada que descreve a configuração do IC durante as fases de **produção, implantação e suporte operacional**. Define as características físicas (forma, encaixe e função) necessárias do IC, as características funcionais selecionadas para testes de aceitação da produção, e os requisitos desses testes de aceitação. Se um IC for recontratado, a baseline do produto deve incluir também a documentação de configuração alocada, para garantir que os requisitos de desempenho sejam mantidos.

⚠️ **Pegadinha:** Baseline Funcional (nível do **sistema/IC de topo**) ≠ Baseline Alocada (nível do **IC específico em desenvolvimento**, herdando características do nível superior) ≠ Baseline do Produto (foco em produção/implantação/suporte, com características físicas de forma/encaixe/função).

🧠 **Memorizar:** Funcional→sistema/topo · Alocada→IC em desenvolvimento (herda do topo) · Desenvolvimento→docs internos em evolução · Produto→produção/implantação/suporte.

---

## 📚 Resumão final

- **Identificação de Configuração** é a base de toda a GCS: identifica, nomeia e documenta os itens e suas versões, do início ao descarte do sistema.
- Ela é pré-requisito para Controle de Configuração, Contabilidade do Status e Verificação/Auditoria, pois todas dependem dos itens que ela identifica.
- O padrão **EIA-649** define os princípios, propósitos e benefícios da identificação de configuração, sem impor terminologia ou metodologia fixa.
- O processo pode ser visto em **7 elementos** (seleção de ICs, documentação, autoridade de controle, identificadores, manutenção, liberação, baselines) ou no **modelo de 5 atividades sequenciais**: Estruturar Produto → Determinar ICs → Selecionar Documentação e Baselines → Identificar/Reidentificar Documentos e Itens → Aprovar Lançamento e Documentação de Baseline.
- **Item de Configuração (IC)** é qualquer coisa sob controle de configuração (hardware = HWCI, software = CSCI), sempre com identificador único; a escolha de quantos ICs criar é um trade-off de engenharia sem regra fixa.
- **Documentação de Configuração** se organiza em especificações por objeto (sistema, item, software, processo) e por propósito (desempenho vs. detalhada).
- **Baseline (Linha de Base)** é uma referência fixa e imutável, formalmente aprovada, que só muda por controle de mudança formal; existem quatro tipos principais: Funcional, Alocada, Configuração de Desenvolvimento e do Produto.

## ⚠️ Pontos que podem cair na prova

- Diferença entre os **7 elementos** do processo e o **modelo de 5 atividades** (Estruturar Produto → ... → Aprovar Lançamento).
- Restrições/Facilitadores/Saída de cada uma das 5 atividades do modelo de processo.
- Consequências de selecionar **muitos vs. poucos ICs** (tabela comparativa no tópico de Item de Configuração).
- Diferença entre **HWCI e CSCI**.
- Diferença entre os quatro tipos de **especificação por objeto** (sistema, item, software, processo) e a qual linha de base cada uma se relaciona.
- Diferença entre **especificação de desempenho** e **especificação detalhada**.
- Definição formal (IEEE) de **baseline** e suas três facetas (fotografia, ponto de aprovação, ponto de controle).
- Diferença entre os quatro tipos de **baseline de configuração** (Funcional, Alocada, Desenvolvimento, Produto).
- As três sub-etapas da **Engenharia de Lançamento (Release)**.

## 📝 Perguntas para revisão

1. O que é Identificação de Configuração e por que ela é considerada a base das demais atividades de GCS?
2. Quais são os três propósitos principais da Identificação de Configuração conforme descrito no início do material?
3. O que é o padrão EIA-649 e quais são suas duas características metodológicas mais importantes?
4. Cite três propósitos/benefícios da identificação de configuração segundo o EIA 649.
5. Quais são as cinco etapas do modelo de atividade do processo de identificação de configuração?
6. O que é um WBS (Work Breakdown Structure) e como ele se relaciona com os ICs?
7. Por que não existem regras fixas para determinar o número ideal de Itens de Configuração?
8. Cite três consequências de selecionar ICs em excesso e três consequências de selecionar poucos ICs.
9. Qual a diferença entre HWCI e CSCI?
10. Quais são os quatro tipos de especificação categorizados por objeto e o que cada um define?
11. Qual a diferença entre especificação de desempenho e especificação detalhada?
12. Qual é a definição formal de baseline (IEEE) e o que ela implica sobre mudanças nos componentes?
13. Quais são as três "facetas" que uma baseline representa?
14. Diferencie Baseline Funcional, Baseline Alocada, Configuração de Desenvolvimento e Baseline do Produto.
15. O que é a Engenharia de Lançamento (Release) e quais suas três sub-etapas?

## Gabarito

1. É o processo de identificar, nomear e documentar os itens de um sistema (e suas versões) que serão controlados. É a base das demais atividades de GCS porque Controle de Configuração, Contabilidade do Status e Verificação/Auditoria dependem de itens já identificados para poderem controlar mudanças, gerar relatórios e realizar auditorias.
2. (1) Identificar os itens que serão controlados; (2) Estabelecer esquemas de identificação para os itens e suas versões; (3) Definir as ferramentas e técnicas usadas na aquisição e no gerenciamento desses itens.
3. É um padrão de Gerenciamento de Configuração desenvolvido em 1994 pelo Comitê G-33 da EIA, que define requisitos gerais, princípios e melhores práticas em GC. Não impõe terminologia ou abordagens específicas de implementação e pode ser aplicado a qualquer ambiente sem restrições metodológicas.
4. Exemplos válidos: determinar a estrutura hierárquica do produto; documentar atributos de desempenho e interfaces; garantir identificação única de produtos e documentos; distinguir versões do produto; fornecer ponto de referência para mudanças e ações corretivas.
5. Estruturar Produto; Determinar Itens de Configuração; Selecionar Documentação e Baselines; Identificar e Reidentificar Documentos e Itens; Aprovar Lançamento e Documentação de Baseline.
6. É uma visão estruturada da família de produtos (hardware, software, serviços, dados, instalações) que estabelece a relação entre os elementos de trabalho e o produto final. Os ICs são identificados como elementos do WBS.
7. Porque a seleção exige bom julgamento de engenharia de sistemas, considerando experiência, análise de custo-benefício e fatores contextuais (complexidade, tecnologia, criticidade) — não existe fórmula ou quantidade fixa aplicável a todo sistema.
8. Muitos ICs: aumento de interfaces a documentar, restrição da evolução do projeto, funcionalidade definida em nível muito baixo com testes/revisões desnecessários, aumento de custos e fragmentação. Poucos ICs: aumento da complexidade de cada IC, dificuldade de reutilização/reaquisição, limitação de fornecedores, dificuldade em testes formais e no rastreamento da implantação.
9. HWCI (Hardware Configuration Item) é usado quando a referência é exclusiva a hardware; CSCI (Computer Software Configuration Item) é usado quando a referência é exclusiva a software.
10. Sistema (desempenho geral e requisitos de missão, base para linha de base funcional); Item (requisitos de desempenho/interface alocados a um IC, base para linha de base alocada); Software (documentos de design do software, interfaces e banco de dados); Processo (processo/serviço crítico para desempenho ou design de um sistema/item específico, parte da linha de base do produto).
11. A especificação de desempenho define requisitos em termos de resultados esperados e critérios de verificação, sem dizer como alcançá-los, permitindo múltiplas soluções de design. A especificação detalhada contém requisitos detalhados (ou uma mistura de desempenho e detalhados), diferenciando uma solução específica das concorrentes com mais detalhes técnicos.
12. Baseline é "uma especificação ou produto que foi formalmente revisado e sobre o qual foi estabelecido acordo, que serve como base para o desenvolvimento subsequente, e que pode ser mudado apenas através de procedimentos de controle de mudança" (IEEE Std 610.12-1990). Isso implica que os componentes de uma baseline são controlados e imutáveis, só podendo ser alterados por processos formais de controle de mudança.
13. "Fotografias" da configuração de um IC em um instante; pontos de compromisso/aprovação indicando marcos atingidos; pontos de controle que exigem atenção da gestão.
14. Baseline Funcional: descreve o desempenho do sistema/IC de nível superior (características funcionais, interoperabilidade, interface). Baseline Alocada: documentação de desempenho aprovada do IC em desenvolvimento, com características herdadas do IC de nível superior. Configuração de Desenvolvimento: documentos técnicos internos que definem a solução de design em evolução durante o desenvolvimento. Baseline do Produto: documentação técnica aprovada da configuração do IC nas fases de produção, implantação e suporte operacional, incluindo características físicas de forma/encaixe/função.
15. É o processo que torna a documentação de configuração disponível para uso, seguindo os procedimentos de controle de configuração da organização. Suas três sub-etapas são: Registro e Rastreabilidade, Atualização e Conformidade, e Verificação de Implementação.
