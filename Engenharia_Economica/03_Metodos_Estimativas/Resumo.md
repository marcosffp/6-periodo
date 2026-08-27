# Resumo — Métodos de Estimativa de Software

## 📖 Estimativa de Software: o que é

**O que é / Definição para prova:** Estimativa de software **"é o processo de prever a quantidade de esforço e de tempo necessários para desenvolver esse artefato ou produto."** Ou seja: antes (ou durante) o desenvolvimento, o profissional precisa responder "quanto tempo e quantas pessoas isso vai exigir?". O desenvolvimento de software requer planejamento e, mais especificamente, estimativa de custo.

**Artefato mais importante resultante desse processo:** é a provável **WBS (Working Breakdown Structure)** ou **EAP (Estrutura Analítica de Projeto)**, que inclui esforço, custo e duração do projeto — ou seja, é o documento que organiza e detalha essas estimativas.

**O que a estimativa busca identificar:**
- a delimitação do **escopo** (o que, onde, como e para quem os produtos/serviços serão entregues);
- **restrições financeiras**;
- **fatores de risco** (do projeto); e
- o próprio **processo de desenvolvimento de software**.

**Custos de software englobam:** despesas com hardware, licenças de software, treinamentos e equipe (recursos humanos). Um diagrama da aula ("Cost Factors") lista ainda: preço de compra, downtime, conexão à internet, backups, gerenciamento, sala de servidor, eletricidade, sistema operacional, upgrades, equipe de TI, suporte anual e treinamento — mostrando que o custo de um software vai muito além do preço de aquisição.

🧠 **Memorizar:** definição = prever esforço + tempo; artefato = WBS/EAP; custos = hardware + licença + treinamento + equipe.

## 📖 Passos para estimar recursos de um projeto de software

**Como funciona / Passos:** para prever os recursos necessários ao desenvolvimento, o profissional encarregado deve, em ordem:
1. Fazer um **estudo de viabilidade**;
2. Selecionar um **método de estimativa**;
3. Dispor de **medidas de produtividade**;
4. Conhecer ou definir a **duração do projeto**;
5. Fazer a **modelagem de custo** do projeto.

**Das preocupações acima, duas são de suma importância:** identificar e quantificar os componentes do custo de projeto, e definir qual método de estimativa usar.

**Etapas da estimativa (fluxo lógico da aula):** as entradas — **histórico/dados de projetos anteriores**, **requisitos ouvidos do cliente** e **restrições do projeto** — alimentam três estimativas paralelas (**tamanho**, **esforço** e **custo**), que, junto com os **recursos do projeto**, resultam na **elaboração do cronograma**.

🧠 **Memorizar:** 5 passos = viabilidade → método → produtividade → duração → modelagem de custo; fluxo = (histórico + requisitos + restrições) → tamanho/esforço/custo → cronograma.

## 📖 A incerteza como problema central das estimativas

**O que é / Definição para prova:** Fazer estimativas de tamanho e custo de projetos pode parecer fácil quando já se têm as funcionalidades bem definidas. Porém, **a dificuldade cresce significativamente quando se conhece apenas a demanda do cliente** (fase inicial do projeto). A **incerteza é o fator responsável tanto pelos excedentes em orçamentos quanto pelos atrasos em cronogramas**.

**Exemplo (dados reais citados na aula):** o DoD (Department of Defense, EUA) e o GAO (Government Accountability Office, órgão que audita contas de projetos nos EUA) registraram, em projetos de tecnologia, o seguinte agravamento ao longo dos anos:

| Ano | Nº de projetos | Orçamento planejado | Crescimento do custo estimado | Atraso médio de cronograma |
|---|---|---|---|---|
| 2000 | 75 | US$ 750 bi | US$ 42 bi | 16 meses |
| 2005 | 91 | US$ 1,5 tri | US$ 202 bi | 17 meses |
| 2007 | 95 | US$ 1,6 tri | US$ 295 bi | 21 meses |

Isso mostra que erros de estimativa são um problema real e crescente, mesmo em projetos com grande estrutura de gestão.

**Como aprimorar as estimativas (mesmo sem eliminar totalmente o erro):**
- Aprimorar a estimativa **pode até não resultar em projetos com menor custo, mas reduz o custo excedente**;
- **O crescimento do custo se dá em função da precisão da estimativa** — quanto mais precisa, menor a chance de estouro;
- É preciso **entender a demanda do cliente e os fatores que podem influenciá-la**: a estimativa de tamanho e custo é desenvolvida a partir do **escopo** (do trabalho e do produto), e normalmente se usam dados de projetos anteriores.

**Perguntas que ajudam a melhorar a precisão de uma estimativa:**
- É necessário ter métrica de produtividade? Vale a pena monitorá-la?
- O que pode influenciar a produtividade da equipe?
- O projeto é inovador?
- Qual o conhecimento do tamanho e da complexidade do projeto?
- Qual a experiência da equipe para esse projeto específico?
- Qual o nível de conhecimento do domínio do projeto?
- Qual o nível de maturidade do processo da empresa desenvolvedora?

**Estimativas no estágio inicial:** é importante notar que as estimativas são necessárias **logo no início do projeto**, justamente quando poucas informações estão disponíveis — baseando-se apenas na demanda do cliente e nas funcionalidades preliminares desejadas. Nessa situação, busca-se toda informação possível (conjunto de funcionalidades, conjunto de atividades, experiência de projetos anteriores) para conseguir estimar o tamanho do software. Sem uma EAP (delimitação do escopo), **"qualquer coisa feita é resultado de sua imaginação"** — ou seja, sem saber exatamente o que precisa ser realizado, não há base real para estimar. À medida que tamanho e complexidade do sistema aumentam, também é necessário considerar o projeto da arquitetura (estrutura geral) do sistema, além do processo de desenvolvimento.

**Papel do feedback contínuo:** ter um **feedback contínuo (resposta e comentários) do cliente** é importante no desenvolvimento — quanto mais cedo, melhor, pois ajuda a planejar o desenvolvimento balanceando custos e benefícios. Isso exige uma **avaliação preliminar de viabilidade**. Duas atividades são importantes nesse contexto: **planejamento** e **análise de riscos**.

⚠️ **Pegadinha:** a incerteza não é eliminada por "estimar melhor" — o ponto da aula é que aprimorar a estimativa reduz o **custo excedente**, não necessariamente o custo total do projeto.

🧠 **Memorizar:** incerteza = causa de estouro de orçamento e atraso; precisão da estimativa ↑ = custo excedente ↓; sem EAP = "imaginação".

## 📖 Por que tudo isso importa (objetivo final da estimativa)

**O que é / Definição para prova:** O objetivo de todo esse esforço de estimar bem é **minimizar custos**, ter o **desenvolvimento como planejado** e entregar **dentro dos prazos propostos**.

**Por que um processo de software formal é necessário para isso:**
- serve de **guia** para controlar as atividades de desenvolvimento;
- **aloca tarefas** para profissionais específicos;
- **especifica quais artefatos** precisam ser desenvolvidos em cada etapa;
- oferece **critérios para monitorar** as atividades de um projeto.

🧠 **Memorizar:** objetivo = custo mínimo + prazo + escopo planejado; processo formal = guia + alocação + artefatos + monitoramento.

## 📖 Métricas de projeto

**O que é / Definição para prova:** Métricas **são dados numéricos que quantificam uma determinada característica de um produto ou processo**. Elas precisam ser coletadas (medidas) e servem como um **indicador** para que se possa avaliar a melhora ou fazer uma comparação. Como em outros projetos, o uso de métricas é requerido em projetos de software, sendo essenciais para controlar a execução do projeto — resume bem a ideia a frase de Tom DeMarco (em *"Controlling Software Projects: Management, Measurement, and Estimation"*): **"Você não pode controlar o que não pode medir."** A menos que se façam medições, não há como saber se o resultado obtido é melhor ou pior do que o planejado.

**Exemplos de métricas de software:** quantidade de linhas de código escritas por um programador em um dia/semana; quantidade de horas para implementar uma funcionalidade; quantidade de defeitos a cada 1.000 linhas de código.

**Como funciona / As métricas têm quatro objetivos:**
- **Planejamento** — usadas nas estimativas de custos, elaboração de orçamento e cronograma, definição de recursos e treinamentos para a equipe;
- **Controle** — ajudam no monitoramento de status e rastreamento das atividades do projeto;
- **Melhora do processo** — servem de base para identificar partes do processo que precisam de melhorias e, depois, para avaliar essas melhorias;
- **Organização do processo** — orientam (ordenam) a execução do projeto, considerando métricas de tamanho (esforço) e duração das atividades.

🧠 **Memorizar:** métrica = dado numérico + serve pra medir; frase de DeMarco; 4 objetivos = planejamento, controle, melhora, organização.

## 📖 Produtividade de software

**O que é / Definição para prova:** Produtividade, em geral, é a relação entre a **quantidade de itens produzidos** e o **esforço necessário** para produzi-los. Em termos de software: **a produtividade de software é definida como a relação entre a quantidade de software produzido e o esforço em produzi-lo.** O custo e o tempo de desenvolvimento de um software dependem, principalmente, da **habilidade intelectual de cada engenheiro de software**.

**Como expressar a quantidade de software produzido:** linhas de código, funcionalidades, ou pontos de função.

**Fatores que influenciam a produtividade da equipe:**
- nível de habilidade dos engenheiros de software;
- complexidade do sistema a ser desenvolvido;
- comprometimento da equipe com o projeto;
- perfil da rotatividade da equipe de projeto;
- perfil da equipe por etapas de projeto.

**Esforço** é justamente o indicador de projeto utilizado na determinação da produtividade.

🧠 **Memorizar:** produtividade = software produzido / esforço; unidades = LOC, funcionalidades, pontos de função; fatores = habilidade, complexidade, comprometimento, rotatividade, perfil.

## 📖 Métodos (modelos) de estimativa de projeto

**O que é / Definição para prova:** São as diferentes abordagens que um profissional pode usar para chegar a uma estimativa de tamanho, esforço ou custo de um projeto de software.

| Método | O que é | Benefícios | Limitações |
|---|---|---|---|
| **Decomposição do projeto** (abordagem bottom-up) | Divide o projeto em partes menores/gerenciáveis, identificando componentes e estimando cada um separadamente, para maior precisão | — | — |
| **Opinião de especialistas** | Reúne um ou mais especialistas em desenvolvimento de software, com base na experiência deles em outros projetos | Método rápido e de custo baixo; pode ser preciso se o especialista tem experiência em projetos similares | Muito dependente do especialista — pode gerar estimativas erradas se ele tem pouca experiência; difícil de documentar os critérios usados |
| **Analogia de projetos** | Compara as necessidades do projeto atual com outros similares (histórico de dados e métricas), extrapolando e ajustando as diferenças | Baseado em dados reais de projetos anteriores e na experiência passada; pode ser preciso se houver dados disponíveis | Impossível de usar se não existirem dados de projetos anteriores; se os dados existirem mas forem imprecisos, a estimativa fica comprometida |
| **Modelagem algorítmica** (ex.: COCOMO) | Usa equações matemáticas e dados históricos para determinar esforço e custo, levantando dados de tamanho e atributos de custo (ex.: linhas de código, confiabilidade, complexidade) que podem impactar a produtividade | Gera resultados repetíveis e permite mudar dados de entrada e customizar soluções | Nem todas as entradas são objetivas; não lida bem com situações excepcionais; alguns métodos são proprietários; dificuldade de quantificar certos fatores |
| **Precificação para vencer** (*price to win*) | Define o custo do projeto para ser o suficiente para vencer uma concorrência ou conquistar um contrato — o custo é estimado a partir do valor que o cliente tem disponível, não do esforço real das funcionalidades | Principal benefício é a conquista do contrato | Menor chance de o cliente receber o produto contratado (ou, se receber, pagará mais); custos normalmente não refletem o esforço exigido; o prazo estimado costuma acabar antes do término real do projeto |
| **Lei de Parkinson** | Estabelece que "o trabalho se expande para preencher todo o tempo disponível" — ou seja, o esforço e o custo são determinados pelos recursos disponíveis, e não pelo conjunto de funcionalidades a desenvolver (citado por B. Ketchenham, *"Making Software Predictions"*) | Em geral, o projeto usa todos os recursos disponíveis, sem resultar em excedentes | Prática não adequada — pode resultar em um produto inacabado |

⚠️ **Pegadinha:** "precificação para vencer" e "modelagem algorítmica" são frequentemente confundidas por ambas envolverem "cálculo de custo" — mas a precificação para vencer parte do **orçamento do cliente**, enquanto a modelagem algorítmica parte de **dados técnicos objetivos** (tamanho, complexidade etc.).

🧠 **Memorizar:** decomposição = bottom-up; especialistas = rápido mas subjetivo; analogia = depende de dados históricos; algorítmica = COCOMO, repetível; price to win = orçamento do cliente, não o esforço real; Parkinson = trabalho preenche o tempo disponível.

## 📖 Técnicas específicas de estimativa (autor e ano)

**O que é / Definição para prova:** Além dos métodos gerais, existem técnicas específicas e nomeadas, cada uma criada por um autor em um ano determinado, cobráveis em prova:

| Técnica | Ano | Autor(es) | O que faz |
|---|---|---|---|
| **PERT** (Program Evaluation and Review Technique) | 1950s | DuPont e Remington Rand | Modela a incerteza associada às estimativas usando **três estimativas por tarefa**: otimista, mais provável e pessimista |
| **Pontos de Função** | 1979 | Allan J. Albrecht | Quantifica o software com base nas **funções fornecidas ao usuário**, independentemente da tecnologia ou linguagem de programação utilizada |
| **COCOMO** (COnstructive COst MOdel) | 1981 | Barry Boehm | Estima o esforço de desenvolvimento com base em características do projeto, como **tamanho, complexidade e experiência da equipe** |
| **Pontos de Caso de Uso** | 1995 | Gustav Karner | Avalia os casos de uso com base em sua **complexidade funcional**, atribuindo pontos conforme critérios como quantidade de transações, complexidade das regras de negócio e interface com o usuário |

⚠️ **Pegadinha:** a lógica das "três estimativas" (otimista/mais provável/pessimista) do PERT é a mesma usada depois na fórmula do LOC esperado (tópico seguinte) — não são técnicas diferentes, é a mesma ideia estatística aplicada à estimativa de linhas de código.

🧠 **Memorizar:** PERT (1950s, DuPont/Remington) = 3 estimativas; Pontos de Função (1979, Albrecht) = funções ao usuário; COCOMO (1981, Boehm) = tamanho+complexidade+experiência; Casos de Uso (1995, Karner) = complexidade funcional.

## 📖 Estimativa baseada em Linhas de Código (LOC/KLOC)

**O que é / Definição para prova:** É a **técnica mais antiga** de estimativa de software. Utiliza **LOC (lines of code)** ou **KLOC** (milhares de linhas de código) como medida de tamanho, sendo adequada apenas para alguns tipos de linguagens de programação. ⚠️ Seu principal problema é que o tamanho em linhas de código varia muito conforme a linguagem e o estilo de quem programa, tornando a comparação entre projetos pouco confiável.

**Como funciona / Passo a passo (com fórmulas):**
1. **Decompor** o software em funções menores, que possam ser estudadas individualmente.
2. Usando dados históricos (ou intuição), fornecer para cada subfunção três valores de LOC: **otimista (a)**, **mais provável (b)** e **pessimista (c)**.
3. Determinar o número **Esperado (E)** de cada subfunção, com a fórmula (mesma lógica do PERT): 
   **E = (a + 4b + c) / 6**
   Somando o E de todas as subfunções, chega-se ao **LOC Estimado** total do projeto.
4. Calcular **Esforço** e **Custo**, usando dados históricos de produtividade e custo médio da organização:
   - **Esforço = LOC Estimado / Produtividade Média**
   - **Custo = LOC Estimado × Custo Médio**

**Exemplo (do PDF):** um projeto foi decomposto em 7 funções, cada uma com valores otimista/mais provável/pessimista de LOC. Aplicando E = (a+4b+c)/6 a cada função e somando, chegou-se a **LOC Estimado = 33.360**. Com dados históricos de **Produtividade Média = 3.206,86 LOC/pessoa-mês** e **Custo Médio = 0,30 $/LOC**, obteve-se:
- **Esforço = 33.360 / 3.206,86 ≈ 10,4 pessoa-mês**
- **Custo = 33.360 × 0,30 = 10.008 $**

**Fórmula geral de esforço (mais abrangente, também apresentada na aula):**
**Esforço = A × Tamanho^B × M**, onde:
- **A** é uma constante que depende das práticas organizacionais;
- **Tamanho** pode ser uma métrica de tamanho (como LOC) ou de funcionalidade (como Pontos de Função);
- o expoente **B** reflete que o custo **não é linear** ao tamanho (fica geralmente entre 1 e 1,5);
- **M** é um multiplicador que considera a equipe.

🧠 **Memorizar:** E = (a+4b+c)/6 (fórmula tipo PERT); Esforço = LOC Estimado / Produtividade; Custo = LOC Estimado × Custo Médio; fórmula geral: Esforço = A × Tamanho^B × M (B entre 1 e 1,5, não-linear).

---

## 📚 Resumão final

- **Estimativa de software** prevê esforço e tempo de um projeto; seu principal artefato é a WBS/EAP.
- Estimar segue 5 passos (viabilidade → método → produtividade → duração → modelagem de custo) e um fluxo que combina histórico, requisitos e restrições para gerar estimativas de tamanho/esforço/custo e, então, o cronograma.
- A **incerteza** é a causa central de estouros de orçamento e atrasos, especialmente no início do projeto, quando há pouca informação disponível; dados reais (DoD/GAO) mostram esse problema crescendo ao longo dos anos.
- O objetivo final de estimar bem é minimizar custo, seguir o planejado e cumprir prazos, com apoio de um processo de software formal.
- **Métricas** são dados numéricos usados para planejamento, controle, melhora e organização de processo — "não se controla o que não se mede" (DeMarco).
- **Produtividade** de software é a relação entre software produzido e esforço, influenciada por habilidade, complexidade, comprometimento e rotatividade da equipe.
- Existem vários **métodos gerais** de estimativa (decomposição, especialistas, analogia, algorítmico/COCOMO, price to win, Lei de Parkinson), cada um com benefícios e limitações próprios.
- Existem **técnicas nomeadas específicas**, com autor e ano definidos: PERT, Pontos de Função, COCOMO e Pontos de Caso de Uso.
- A **estimativa por LOC/KLOC** é a mais antiga, usa a fórmula E=(a+4b+c)/6 para o tamanho esperado e permite calcular esforço e custo a partir de dados históricos de produtividade.

## ⚠️ Pontos que podem cair na prova

- Definição formal de estimativa de software e o artefato WBS/EAP.
- Os 5 passos para prever recursos de um projeto.
- Por que a incerteza aumenta quando só se conhece a demanda do cliente (fase inicial).
- Diferença entre os métodos de estimativa (tabela comparativa), especialmente "price to win" x "modelagem algorítmica".
- Autores e anos das técnicas específicas: PERT (DuPont/Remington, anos 1950), Pontos de Função (Albrecht, 1979), COCOMO (Boehm, 1981), Pontos de Caso de Uso (Karner, 1995).
- A fórmula E = (a+4b+c)/6 e o cálculo de Esforço e Custo a partir do LOC Estimado.
- A fórmula geral Esforço = A × Tamanho^B × M e o significado de cada variável.
- Os quatro objetivos das métricas de projeto.
- Definição de produtividade de software e seus fatores de influência.

## 📝 Perguntas para revisão

1. O que é estimativa de software e qual é o principal artefato resultante desse processo?
2. Quais são os cinco passos que um profissional deve seguir para prever os recursos de um projeto?
3. Por que a incerteza é considerada o principal fator responsável por excedentes de orçamento e atrasos de cronograma?
4. O que significa dizer que "o crescimento do custo se dá em função da precisão da estimativa"?
5. Qual é o objetivo final de se investir em boas estimativas, e por que um processo de software formal é necessário para alcançá-lo?
6. O que são métricas de projeto e quais são seus quatro objetivos?
7. Como é definida a produtividade de software e quais fatores a influenciam?
8. Compare os métodos "opinião de especialistas" e "analogia de projetos": quais são os benefícios e limitações de cada um?
9. Explique a diferença entre "precificação para vencer" (price to win) e "modelagem algorítmica" como métodos de estimativa.
10. Relacione cada técnica de estimativa (PERT, Pontos de Função, COCOMO, Pontos de Caso de Uso) com seu respectivo autor e ano de criação.
11. Como se calcula o número esperado (E) de LOC de uma subfunção, e como esse valor é usado para chegar ao Esforço e ao Custo do projeto?
12. Na fórmula Esforço = A × Tamanho^B × M, o que representa cada uma das variáveis A, B e M?

### Gabarito

1. É o processo de prever a quantidade de esforço e de tempo necessários para desenvolver um artefato ou produto de software. O principal artefato resultante é a WBS (Working Breakdown Structure) ou EAP (Estrutura Analítica de Projeto), que inclui esforço, custo e duração do projeto.
2. (1) Fazer um estudo de viabilidade; (2) selecionar um método de estimativa; (3) dispor de medidas de produtividade; (4) conhecer ou definir a duração do projeto; (5) fazer a modelagem de custo do projeto.
3. Porque, principalmente no início do projeto, se conhece apenas a demanda do cliente, sem detalhamento completo das funcionalidades — quanto menos informação, maior a incerteza, e é essa incerteza que causa tanto o estouro de orçamento quanto o atraso no cronograma.
4. Significa que estimativas mais precisas tendem a gerar menos custo excedente (mesmo que não reduzam o custo total do projeto) — ou seja, a precisão da estimativa impacta diretamente o quanto o projeto pode "estourar" o que foi planejado.
5. O objetivo é minimizar custos, manter o desenvolvimento como planejado e entregar dentro dos prazos propostos. Um processo de software formal é necessário porque serve de guia para controlar as atividades, aloca tarefas a profissionais específicos, especifica quais artefatos devem ser produzidos em cada etapa e oferece critérios para monitorar o projeto.
6. Métricas são dados numéricos que quantificam uma característica de um produto ou processo, coletados para servir de indicador de melhora ou comparação. Seus quatro objetivos são: planejamento, controle, melhora do processo e organização do processo.
7. A produtividade de software é a relação entre a quantidade de software produzido e o esforço necessário para produzi-lo. É influenciada pelo nível de habilidade dos engenheiros, pela complexidade do sistema, pelo comprometimento da equipe, pela rotatividade da equipe e pelo perfil da equipe em cada etapa do projeto.
8. A opinião de especialistas é um método rápido e de baixo custo, mas muito dependente da experiência do especialista (pode gerar estimativas erradas se ele tiver pouca experiência, além de ser difícil documentar os critérios usados). A analogia de projetos é baseada em dados reais de projetos anteriores similares, podendo ser precisa se esses dados existirem e forem confiáveis — mas se não houver dados históricos (ou eles forem imprecisos), o método fica inviável ou comprometido.
9. A precificação para vencer define o custo do projeto com base no valor que o cliente tem disponível para gastar (visando vencer uma concorrência ou fechar um contrato), sem relação direta com o esforço real de implementar as funcionalidades — por isso tende a subestimar prazo e custo real. Já a modelagem algorítmica usa equações matemáticas e dados históricos objetivos (tamanho, complexidade, confiabilidade) para calcular esforço e custo de forma repetível.
10. PERT — DuPont e Remington Rand, anos 1950. Pontos de Função — Allan J. Albrecht, 1979. COCOMO — Barry Boehm, 1981. Pontos de Caso de Uso — Gustav Karner, 1995.
11. O número esperado é calculado pela fórmula E = (a + 4b + c) / 6, onde a é o valor otimista, b o mais provável e c o pessimista de LOC para aquela subfunção. Somando o E de todas as subfunções, obtém-se o LOC Estimado total. A partir dele: Esforço = LOC Estimado / Produtividade Média (histórica); Custo = LOC Estimado × Custo Médio (histórico, em $/LOC).
12. A representa uma constante que depende das práticas organizacionais; B é um expoente (geralmente entre 1 e 1,5) que reflete que o custo não cresce linearmente com o tamanho do projeto; M é um multiplicador que considera características da equipe.
