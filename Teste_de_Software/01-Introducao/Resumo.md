# Teste de Software — Nivelamento (Aula 01)

> Conceitos de software, processo de desenvolvimento, engenharia de software, qualidade de software (ISO/IEC 9126 e 25010), garantia/controle de qualidade e onde o teste de software se encaixa.

---

## 📖 Software

**O que é / Definição para prova:** software não é só "o código" — é o conjunto de tudo que faz um programa funcionar de forma útil para quem usa. Pertence ao **sistema lógico** (não ao físico/hardware) e engloba três partes: **instruções** (programas que, quando executados, fornecem características, funções e desempenho desejados), **estruturas de dados** (que permitem ao programa manipular informações adequadamente) e **informações descritivas** (documentação sobre operação e uso).

Pense num software como uma receita de bolo (as instruções/algoritmo), os ingredientes organizados de forma específica (estrutura de dados) e o manual explicando como fazer e servir o bolo (documentação). Sem qualquer uma dessas três partes, o "produto software" fica incompleto.

🧠 **Memorizar:** software = instruções + estrutura de dados + documentação, no domínio **lógico** (não físico).

---

## 📖 Produtos de Software

**O que é / Definição para prova:** todo produto de software nasce de uma necessidade — de uma pessoa específica (usuário) ou de um grupo grande de possíveis compradores (mercado).

| Sob encomenda (personalizado) | Genérico (de prateleira / stand-alone) |
|---|---|
| Desenvolvido para **um** cliente/usuário específico | Desenvolvido para um **mercado** amplo |
| Feito sob medida, exclusivo | Vendido "pronto" para qualquer comprador |
| Ex.: sítios web e controles de processo de uma organização | Ex.: editores de texto, pacotes gráficos, jogos |

🧠 **Memorizar:** sob encomenda = 1 cliente; genérico = mercado (prateleira).

---

## 📖 Tipos de Software

**O que é / Definição para prova:** o **tipo** do software determina as interfaces para usuários, a proximidade com o cliente, as funcionalidades, a eficiência e o custo de implementação. ⚠️ Não confundir com "produto de software" (que classifica pela origem da necessidade: usuário x mercado) — tipo é outro critério, sobre a finalidade/plataforma do software.

**Exemplos citados:** software de sistema e de aplicação; software de engenharia ou científico; software **embutido/embarcado** (roda dentro de um dispositivo físico, ex.: geladeira, carro, eletrodoméstico); software de **linhas de produto** (famílias de produtos parecidos, reaproveitando uma base comum); aplicações web; software de inteligência artificial.

🧠 **Memorizar:** tipo → interface, funcionalidade, eficiência, custo; decore pelo menos 4 exemplos (sistema/aplicação, científico, embutido, IA).

---

## 📖 Algoritmos

**O que é / Definição para prova:** um algoritmo é a "receita" que o software segue — uma sequência de passos que resolve um problema, independente da linguagem de programação. Três definições citadas no material: "descrição de um conjunto de comandos que, obedecidos, resultam numa sucessão finita de ações" (Farrer et al., 1999); "sequência de passos computacionais que transformam uma entrada em uma saída" (Cormen et al., 2002); "um processo sistemático para a resolução de um problema" (Szwarcfiter et al., 2010).

🧠 **Memorizar:** algoritmo = sequência finita de passos, entrada → saída, resolve um problema.

---

## 📖 Estrutura de Dados

**O que é / Definição para prova:** é a forma de armazenar e organizar os dados dentro de um programa para resolver o problema de forma eficiente. A estrutura escolhida afeta diretamente a **eficiência** da solução.

| Estrutura Estática | Estrutura Dinâmica |
|---|---|
| Número **fixo (finito)** de elementos | Número **indefinido** de elementos |
| Tamanho definido antes da execução (ex.: vetor de tamanho fixo) | Tamanho pode crescer/diminuir durante a execução (ex.: lista encadeada) |

🧠 **Memorizar:** estática = tamanho fixo; dinâmica = tamanho variável; estrutura afeta eficiência.

---

## 📖 Softwares Grandes (exemplos de escala)

**O que é:** o material mostra softwares gigantes reais e os tipos de algoritmos por trás deles, para ilustrar a complexidade que a Engenharia e o Teste de Software precisam lidar.

**Exemplos:** **máquinas de busca** (Google) → algoritmos como **PageRank** (ordena páginas por relevância) e **MapReduce** (processa grandes volumes de dados distribuídos em paralelo); **redes sociais** (Meta) → **algoritmos de processamento de grafo** (pessoas/conexões representadas como nós e arestas); sistemas **Peer-to-Peer (P2P)**, como **BitTorrent** → **algoritmos baseados em reputação**, como o *tit-for-tat* ("olho por olho, dente por dente" — cada participante coopera na mesma proporção que o outro coopera com ele).

🧠 **Memorizar:** Google→PageRank/MapReduce; redes sociais→grafos; P2P/BitTorrent→reputação (tit-for-tat).

---

## 📖 Processo de Desenvolvimento de Software

**O que é / Definição para prova:** desenvolver um software é transformar a necessidade de um usuário ou mercado em um produto — **elaborar** e **implementar** um sistema computacional. Esse caminho é o **Processo de Desenvolvimento de Software** (⚠️ sinônimo de "Processo de Desenvolvimento" e "Processo de Software" — são o mesmo conceito, nomes diferentes).

Formalmente: um processo de software consiste em um conjunto de **atividades** realizadas por **pessoas**, cujo objetivo é o desenvolvimento ou evolução de um **artefato** (o software e sua documentação).

🧠 **Memorizar:** Processo de Software = Processo de Desenvolvimento (mesmo conceito); atividades + pessoas + artefato.

---

## 📖 Papel, Atividade e Artefato

**O que é / Definição para prova:** são os três elementos básicos de qualquer processo de software.
- **Papel:** função desempenhada por um membro da equipe (ex.: analista, desenvolvedor, testador).
- **Atividade:** tarefa realizada por uma pessoa em um papel, para gerar um artefato; consome e produz artefatos; está sujeita a **pré-condições** (o que precisa existir antes de começar) e **pós-condições** (o que deve estar pronto ao final).
- **Artefato:** produto de uma atividade — um modelo, documento, código.

**Exemplo:** um analista de requisitos (papel) realiza a atividade de "levantar requisitos", tendo como pré-condição a existência de reuniões com o cliente, e como pós-condição/artefato o "documento de requisitos".

🧠 **Memorizar:** Papel=quem; Atividade=o quê (pré/pós-condição); Artefato=o resultado.

---

## 📖 Atividades Genéricas do Processo de Software

**O que é:** as macro-fases pelas quais qualquer processo de desenvolvimento de software passa, segundo dois autores clássicos de referência da Engenharia de Software.

| Pressman (2011) | Sommerville (2011) |
|---|---|
| Comunicação | Especificação |
| Planejamento | Projeto e implementação |
| Modelagem | **Validação** |
| Construção | Evolução |
| Emprego | |

Os dois autores descrevem, com nomes diferentes, praticamente o mesmo ciclo: entender o que o cliente quer, planejar/projetar, construir, verificar se ficou certo e depois manter/evoluir o software. A classificação de **Sommerville** é a mais relevante para Teste de Software, porque destaca explicitamente a etapa de **Validação**, onde o teste se encaixa.

🧠 **Memorizar:** Sommerville: Especificação→Projeto/Implementação→**Validação**→Evolução (Teste = Validação). Pressman: Comunicação→Planejamento→Modelagem→Construção→Emprego.

---

## 📖 Engenharia de Software (ES)

**O que é / Definição para prova:** é a área que trata de desenvolver software de forma profissional e organizada, com método e controle de qualidade, em vez de "sair programando no improviso". Definição do **IEEE (1993)**: "1) aplicação de uma abordagem **sistemática**, **disciplinada** e **quantificável** no desenvolvimento, na operação e na manutenção de software; 2) estudo e abordagem do descrito em 1". 💡 IEEE = *Institute of Electrical and Electronics Engineers*, organização internacional que define padrões técnicos, inclusive de software.

**Características:** **sistemática** (segue um método, não é aleatória), **disciplinada** (segue regras e padrões definidos), **quantificável** (pode ser medida por métricas e indicadores).

🧠 **Memorizar:** ES (IEEE 1993) = sistemática + disciplinada + quantificável.

---

## 📖 Foco da Engenharia de Software: Qualidade

**O que é / Definição para prova:** o material representa a ES como uma pirâmide em camadas, de baixo para cima: **1. Foco na qualidade** (base, sustenta tudo) → **2. Processo** (desenvolvimento racional e dentro do prazo) → **3. Métodos** (princípios básicos de como fazer) → **4. Ferramentas** (suporte semiautomatizado). Assim como um prédio precisa de fundação sólida antes de erguer os andares, a ES precisa ter a **qualidade como fundação** antes de definir processo, métodos e ferramentas.

🧠 **Memorizar:** ordem da pirâmide (base→topo): Foco na qualidade → Processo → Métodos → Ferramentas.

---

## 📖 Qualidade: Produto x Processo

**O que é / Definição para prova:** existem dois alvos diferentes de avaliação de qualidade.

| Qualidade do Produto de Software | Qualidade do Processo de desenvolvimento |
|---|---|
| Pergunta: "Este software tem qualidade?" | Pergunta: "Este processo permite produzir software de qualidade?" |
| Avalia o resultado final | Avalia o método usado para construir |

Em ambos os casos, qualidade é medida através de **indicadores, características ou atributos de qualidade** — não é "achismo".

🧠 **Memorizar:** qualidade se mede no produto OU no processo, sempre por indicadores/atributos.

---

## 📖 Qualidade pela Norma ISO/IEC 9126

**O que é / Definição para prova:** norma internacional (posteriormente substituída) que definia as **propriedades a verificar** em um produto de software para considerá-lo de qualidade, junto com as **métricas usadas na avaliação**. Seis características:

| Característica | Subcaracterísticas |
|---|---|
| **Funcionalidade** | Adequação, Acurácia, Interoperabilidade, Segurança de acesso, Conformidade |
| **Confiabilidade** | Maturidade, Tolerância a falhas, Recuperabilidade, Conformidade |
| **Usabilidade** | Inteligibilidade, Apreensibilidade, Operacionalidade, Atratividade, Conformidade |
| **Eficiência** | Comportamento no tempo, Utilização de recursos, Conformidade |
| **Manutenibilidade** | Analisabilidade, Modificabilidade, Estabilidade, Testabilidade, Conformidade |
| **Portabilidade** | Adaptabilidade, Capacidade de instalação, Coexistência, Capacidade de substituição, Conformidade |

⚠️ **Pegadinha:** "Conformidade" aparece como subcaracterística nas **6** categorias — cada característica de qualidade tem sua própria dimensão de "estar em conformidade com normas/padrões aplicáveis".

🧠 **Memorizar:** Funcionalidade, Confiabilidade, Usabilidade, Eficiência, Manutenibilidade, Portabilidade — todas com Conformidade.

---

## 📖 Da ISO/IEC 9126 para a ISO/IEC 25010

**O que é / Definição para prova:** **SQuaRE** (*System and Software Quality Requirements and Evaluation*) é a família de normas **ISO/IEC 250xx** que substituiu a 9126. A **25010** tem ênfase específica em **software** (a 9126 era de propósito mais geral) e inclui dois atributos novos que a 9126 não tinha: **compatibilidade** e **segurança**.

**Linha do tempo:** **ISO/IEC 25010:2011** define o **modelo de qualidade** (quais características existem); **ISO/IEC 25002:2024** define **como medir** as características do modelo.

**Outras normas da família (visão geral, não precisa decorar todas):** 25012 (modelo de qualidade de **dados**), 25020 (referência para medição), 25022/25023/25024 (medição de qualidade em uso/produto/dados), 25030 (especificação de requisitos), 25040+ (processo de avaliação — quem avalia, como avalia).

⚠️ **Pegadinha:** não confundir "quem define o modelo" (25010, o que é qualidade) com "quem define como medir" (25002, como avaliar/quantificar essa qualidade).

🧠 **Memorizar:** SQuaRE substituiu a 9126; 25010=modelo (2011); 25002=como medir (2024); novidades da 25010 = Compatibilidade e Segurança.

---

## 📖 Modelo de Qualidade ISO/IEC 25010 (detalhado)

**O que é / Definição para prova:** o modelo *System/Software Product Quality* da ISO/IEC 25010 se desdobra em 8 características:

| Característica | Subcaracterísticas |
|---|---|
| **Functional Suitability** (Adequação Funcional) | Functional completeness, correctness, appropriateness |
| **Performance Efficiency** (Eficiência de Desempenho) | Time-behavior, resource utilisation, capacity |
| **Compatibility** (Compatibilidade) *— nova* | Co-existence, interoperability |
| **Usability** (Usabilidade) | Recognizability, learnability, operability, error protection, aesthetics, accessibility |
| **Reliability** (Confiabilidade) | Maturity, availability, fault tolerance, recoverability |
| **Security** (Segurança) *— nova* | Confidentiality, integrity, non-repudiation, accountability, authenticity |
| **Maintainability** (Manutenibilidade) | Modularity, reusability, analyzability, modifiability, testability |
| **Portability** (Portabilidade) | Adaptability, installability, replaceability |

⚠️ **Pegadinha:** "Funcionalidade" da 9126 virou "Functional Suitability" na 25010; **Compatibility** e **Security** são as duas características novas.

🧠 **Memorizar:** 8 características (decore os 8 nomes em inglês); 2 novidades = Compatibility + Security.

---

## 📖 As 8 Características × Técnicas de Teste

> Cada característica: definição curta + técnicas de teste usadas para avaliá-la na prática.

| Característica | Definição | Técnicas de teste |
|---|---|---|
| **Funcionalidade** | Capacidade de fornecer funções que atendam às necessidades especificadas, sob condições específicas | Testes funcionais; **TDD** (*Test-Driven Development* — teste escrito antes do código); **BDD** (*Behavior-Driven Development* — valida comportamento em linguagem de negócio); testes de casos de uso |
| **Confiabilidade** | Manter o desempenho esperado sob condições específicas, por um período definido | Testes de regressão (mudanças não causam novas falhas), de estresse (carga extrema), de recuperação (retomar após falha), de disponibilidade |
| **Usabilidade** | Facilidade de uso, incluindo aprendizagem, operação e atratividade | Testes com usuários reais; avaliação heurística (heurísticas de Nielsen); testes A/B; eye-tracking e métricas de interação |
| **Eficiência de Desempenho** | Desempenho apropriado em relação aos recursos usados | Testes de carga (JMeter, Locust); testes de tempo de resposta; perfis de CPU/memória/rede; testes de escalabilidade |
| **Segurança** | Proteger informações, garantindo acesso só a quem é autorizado | Testes de penetração (pentest); **SAST** (análise **estática** de código, sem executar); **DAST** (análise **dinâmica**, com o programa em execução); verificação do OWASP Top 10 (lista das 10 vulnerabilidades web mais críticas) |
| **Compatibilidade** | Funcionar em conjunto com outros sistemas/ambientes | Testes cross-browser; testes multi-dispositivo; testes de interoperabilidade (APIs); testes de integração |
| **Manutenibilidade** | Facilidade de modificar para corrigir defeitos ou adaptar | Análise estática de código (SonarQube, PMD, ESLint); cobertura de testes unitários (JaCoCo, Istanbul); regressão automatizada; code review |
| **Portabilidade** | Capacidade de ser transferido de um ambiente para outro | Testes em múltiplos SOs; testes em diferentes versões de dependências; nuvem x on-premises (infraestrutura própria); múltiplas arquiteturas (x86, ARM) |

⚠️ **Pegadinha:** SAST é **estática** (sem rodar o código); DAST é **dinâmica** (rodando o sistema, simulando ataques reais).

🧠 **Memorizar:** associar cada característica à sua definição de 1 linha + 2 técnicas de teste típicas.

---

## 📖 Garantia e Controle de Qualidade

**O que é / Definição para prova:** dois conceitos complementares, mas diferentes, sobre como uma organização assegura qualidade — um define "as regras do jogo", o outro "checa se o jogo está sendo jogado certo".

| Garantia de Qualidade (*Quality Assurance*) | Controle de Qualidade (*Quality Control*) |
|---|---|
| Estabelece **procedimentos e padrões organizacionais** que conduzam a software de qualidade | Série de **inspeções, revisões e testes** ao longo do processo, garantindo qualidade de cada produto de trabalho |
| Foco: **prevenir** — definir o "como fazer certo" desde o início | Foco: **verificar/detectar** — checar se cada entrega está de acordo com o padrão |
| Nível organizacional/processo | Nível de produto/artefato |

Analogia: Garantia de Qualidade é escrever as regras de segurança de uma fábrica; Controle de Qualidade é o inspetor testando cada peça que sai da linha de produção.

⚠️ **Pegadinha:** o **Teste de Software** está diretamente ligado ao **Controle** de Qualidade, não à Garantia.

🧠 **Memorizar:** Garantia=padrões/preventivo/processo; Controle=inspeções-testes/verificação/produto (teste está aqui).

---

## 📖 Teste de Software

**O que é / Definição para prova:** um **conjunto de atividades** que buscam a **qualidade de software**, que podem ser **planejadas antecipadamente** e **conduzidas sistematicamente**. Essas atividades permitem: (1) mostrar que um software **faz o que é proposto** (validação positiva de requisitos) e (2) **descobrir defeitos** antes do uso real.

⚠️ **Pegadinha:** teste de software não é uma atividade aleatória/informal — precisa ser planejada e sistemática, ligando-se diretamente ao **Controle de Qualidade** visto acima.

🧠 **Memorizar:** teste = atividades planejadas e sistemáticas → (1) mostrar que funciona, (2) achar defeitos antes do uso.

---

## 📖 Motivação para Testar

**O que é / Definição para prova:** testar é importante para **reduzir o retrabalho** de corrigir defeitos após a entrega, **reduzir o custo de suporte** e **evitar o desgaste na imagem** do produto/empresa.

**Exemplo (gráfico clássico de custo de correção por fase):**

| Fase | Custo aproximado |
|---|---|
| Requisitos | $139 |
| Projeto | $455 |
| Codificação | $977 |
| Testes | $7.136 |
| Manutenção (pós-entrega) | $14.102 |

Esse exemplo representa o conceito de que o custo de corrigir um defeito **cresce exponencialmente** quanto mais tarde ele é descoberto: corrigir um erro de requisito é muito mais barato do que corrigi-lo já em produção. Isso justifica testar cedo e continuamente.

⚠️ **Pegadinha:** a ordem crescente de custo (Requisitos < Projeto < Codificação < Testes < Manutenção), com **Manutenção** disparado a mais cara, é o ponto mais provável de cair.

🧠 **Memorizar:** quanto mais tarde o defeito é achado, mais caro corrigir; motivações = retrabalho, custo de suporte, imagem.

---

## 📖 Testar Software é um Desafio

**O que é / Definição para prova:** testar não é trivial nem estático — fica cada vez mais complexo por causa de: **softwares cada vez mais complexos** (mais componentes que conversam entre si, mais diversidade de plataformas); **constante redução do ciclo de vida** do software (entregas mais rápidas, menos tempo para testar); **atualizações constantes** (cada uma é um risco novo de quebrar algo que já funcionava).

🧠 **Memorizar:** 3 fatores de desafio — complexidade crescente, ciclos mais curtos, atualizações constantes.

---

## 📖 Problemas Típicos (más práticas comuns de teste)

**O que é / Definição para prova:**

| Problema | Por que é ruim |
|---|---|
| **Programador testa o código que ele mesmo produz** | "Vício no código" — tende a testar só o que já sabe que funciona, com dificuldade de enxergar seus próprios erros |
| **Somente o usuário testa** | Alto custo — defeitos só descobertos em uso real, custando muito mais para corrigir |
| **Teste informal, sem método definido** | Baixa cobertura — sem planejamento, partes do sistema nunca são testadas |
| **Pouca automação** | Alto custo de reexecução — repetir testes manualmente a cada mudança é caro e lento |
| **Poucos testes** | Muitos erros e defeitos não são identificados |

🧠 **Memorizar:** 5 problemas — vício de código, só usuário testa, teste informal, pouca automação, poucos testes.

---

## 📖 Desafios de Pesquisa e Competições

**O que é:** perguntas em aberto na área e competições dedicadas ao tema.

**Desafios:** garantir que todos os fluxos do software estão sendo testados; testar **softwares concorrentes** (múltiplas partes rodando ao mesmo tempo, comportamento difícil de prever/reproduzir); garantir que toda **mudança indesejada** seja detectada por algum caso de teste.

**Competições:** *Test-Comp* (*Competition on Software Testing*); *IEEE International Contest on Software Testing*; *IEEE International Software Testing Contest*.

🧠 **Memorizar:** desafios = cobertura completa, concorrência, detecção garantida de mudanças; competições = Test-Comp, IEEE Contests.

---

## 📖 Testes no Cenário Atual (ferramentas modernas)

**O que é:** panorama de ferramentas usadas na indústria para automatizar e integrar testes ao processo moderno. É mais provável a prova cobrar a **categoria** do que detalhes de cada ferramenta.

| Categoria | Ferramentas/exemplos |
|---|---|
| Automação (interface/navegador) | Selenium, Cypress, Playwright |
| Testes de API | Postman, Newman, Pact |
| Integração com **CI/CD** (*Continuous Integration/Continuous Delivery*) | GitHub Actions, GitLab CI, Jenkins |
| Testes de segurança | OWASP ZAP, SAST, DAST |
| Testes em IA e ML (*Machine Learning*) | Validação e checagem de viés dos modelos |

🧠 **Memorizar:** associar categoria → exemplos (Automação=Selenium/Cypress/Playwright; API=Postman; CI/CD=GitHub Actions/Jenkins; Segurança=OWASP ZAP).

---

## 📚 Resumão Final

- **Software** = instruções + estrutura de dados + documentação, no domínio lógico (ver tópico Software).
- **Produtos** nascem de necessidade de usuário (sob encomenda) ou mercado (genérico); o **tipo** de software define interface/custo/eficiência.
- **Algoritmo** = passos finitos entrada→saída; **estrutura de dados** (estática/dinâmica) afeta eficiência.
- **Processo de software** = atividades + pessoas + artefatos, com papéis definidos (Papel/Atividade/Artefato); Sommerville: Especificação→Projeto/Implementação→**Validação** (onde entra o teste)→Evolução.
- **Engenharia de Software** (IEEE 1993) = sistemática+disciplinada+quantificável; base = foco na qualidade.
- Qualidade avalia-se no **produto** ou no **processo**; **ISO/IEC 9126** tinha 6 características, evoluiu para **SQuaRE/ISO 25010** (8 características, +Compatibility e +Security), cada uma com técnicas de teste próprias.
- **Garantia de Qualidade** = padrões/processo (preventivo); **Controle de Qualidade** = inspeções/testes/produto — Teste de Software pertence ao Controle.
- **Teste de Software** = atividades planejadas e sistemáticas; custo de correção de defeito cresce exponencialmente quanto mais tarde é achado.
- Testar é desafiador (complexidade, ciclos curtos, atualizações) e sofre de problemas típicos (vício de código, informalidade, pouca automação); cenário atual usa Selenium/Cypress/Playwright, Postman, CI/CD e ferramentas de segurança/IA.

## ⚠️ Pontos que podem cair na prova

- As 8 características da ISO/IEC 25010 e as duas novidades (Compatibility, Security) em relação à 9126.
- Diferença Garantia x Controle de Qualidade, e onde o Teste de Software se encaixa.
- A curva de custo de correção de defeito por fase (clássica em provas de ES/Testes).
- SAST x DAST; TDD x BDD.
- Onde o Teste se encaixa nas atividades genéricas de Sommerville (Validação).
- Diferenciar Papel, Atividade e Artefato.

## 📝 Perguntas para revisão

1. O que é software e quais são seus três componentes?
2. Diferencie produtos sob encomenda de produtos genéricos, e diferencie "tipo" de "produto" de software.
3. O que é um algoritmo, e qual a diferença entre estrutura de dados estática e dinâmica?
4. O que é um processo de software e quais são seus três elementos básicos (papel, atividade, artefato)?
5. Segundo Sommerville, quais são as atividades genéricas do processo de software, e em qual delas o Teste se encaixa?
6. Qual é a definição de Engenharia de Software segundo o IEEE (1993), e qual sua "pedra fundamental"?
7. Quais são as seis características de qualidade da ISO/IEC 9126?
8. O que é SQuaRE e quais as oito características da ISO/IEC 25010? Quais duas são novas em relação à 9126?
9. Cite duas técnicas de teste associadas a duas características diferentes da 25010.
10. Diferencie Garantia de Qualidade de Controle de Qualidade, e diga onde o Teste de Software se encaixa.
11. O que é Teste de Software, e por que o custo de corrigir um defeito aumenta quanto mais tarde ele é achado?
12. Diferencie SAST de DAST, e TDD de BDD.
13. Cite três problemas típicos de más práticas de teste, explicando um deles.

### Gabarito

1. Instruções (programas executáveis), estruturas de dados (organização de informação) e documentação — tudo no domínio lógico, não físico.
2. Sob encomenda atende a um cliente específico (ex.: sítio sob medida); genérico atende a um mercado amplo (ex.: editor de texto comercial). "Tipo" classifica pela finalidade/plataforma (sistema, científico, embutido etc.); "produto" classifica pela origem da necessidade (usuário x mercado) — são critérios diferentes.
3. Algoritmo é uma sequência finita de passos que transforma entrada em saída para resolver um problema. Estrutura estática tem número fixo de elementos; dinâmica tem número indefinido, podendo crescer/diminuir durante a execução.
4. Processo de software é um conjunto de atividades realizadas por pessoas para desenvolver/evoluir um artefato. Elementos: Papel (função da pessoa), Atividade (tarefa com pré/pós-condições, que consome/produz artefatos), Artefato (produto gerado, como modelo, documento ou código).
5. Especificação, Projeto e implementação, Validação e Evolução. O Teste se encaixa na **Validação**.
6. "Aplicação de uma abordagem sistemática, disciplinada e quantificável no desenvolvimento, operação e manutenção de software" (IEEE, 1993). Pedra fundamental: o foco na qualidade.
7. Funcionalidade, Confiabilidade, Usabilidade, Eficiência, Manutenibilidade, Portabilidade.
8. SQuaRE = *System and Software Quality Requirements and Evaluation*, família ISO/IEC 250xx que substituiu a 9126. As 8 características da 25010: Functional Suitability, Performance Efficiency, Compatibility, Usability, Reliability, Security, Maintainability, Portability. Novas: Compatibility e Security.
9. Ex.: Confiabilidade → testes de regressão e de recuperação; Segurança → pentest e SAST/DAST.
10. Garantia de Qualidade = procedimentos/padrões organizacionais (nível de processo, preventivo). Controle de Qualidade = inspeções/revisões/testes (nível de artefato, verificação) — o Teste de Software é uma atividade de Controle de Qualidade.
11. Teste de Software é um conjunto de atividades planejadas e sistemáticas que buscam qualidade, mostrando que o software funciona e descobrindo defeitos antes do uso. O custo cresce porque, quanto mais tarde o defeito é achado, mais código/integrações já foram construídos em cima dele, tornando a correção mais complexa e cara (de $139 nos requisitos a $14.102 na manutenção).
12. SAST analisa o código estaticamente, sem executar; DAST analisa o sistema em execução, simulando ataques reais. TDD escreve o teste antes do código; BDD valida o comportamento esperado em linguagem de negócio.
13. Programador testar o próprio código (vício, dificuldade de enxergar erros próprios); só o usuário testar (alto custo, defeitos achados tarde); teste informal sem método (baixa cobertura) — também válidos: pouca automação, poucos testes.
