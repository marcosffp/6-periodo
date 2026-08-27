# Estratégias de Teste Funcional de Software

## 📖 A Técnica de Teste Funcional

**O que é / Definição para prova:** no Teste Funcional, **o sistema é considerado como uma caixa preta** — ou seja, o testador não olha para o código internamente, só observa o que entra e o que sai. Por essa razão, o Teste Funcional é muitas vezes chamado de **teste "caixa preta"**. O fluxo é: um **Dado de Teste** é fornecido como entrada ao sistema; o sistema processa e gera uma **Saída Gerada**; essa saída é comparada com a **Saída Esperada** (que, junto com o dado de teste, forma o **Caso de Teste**). Se a saída gerada for igual à esperada, o resultado é **"Sucesso"** (o sistema passou no teste); se forem diferentes, o resultado é **"Falha"** (o sistema não passou no teste).

🧠 **Memorizar:** caixa preta = não olha o código · Caso de Teste = Dado de Teste + Saída Esperada · Sucesso = saída gerada = saída esperada.

## 📖 Caso de Teste — os cinco elementos

**O que é:** um caso de teste completo é composto por cinco elementos, que juntos definem exatamente o que testar, como testar e o que esperar:

- **Pré-condições** — dizem o estado obrigatório do software antes do início do teste. Se não for atendido, o teste pode falhar sem que exista um defeito real (ou seja, um "falso positivo" de falha).
- **Entradas** — são os dados a serem fornecidos ao software para execução.
- **Ação** — a execução que o software faz e que será objeto do teste.
- **Resultados esperados** — saídas conhecidas (correspondentes à entrada) que se espera que o software gere.
- **Pós-condições** — dizem o estado obrigatório do software após a execução da ação.

⚠️ **Pegadinha:** pré-condição e pós-condição não são "entrada" e "saída" — são sobre o **estado do sistema** antes e depois, não sobre os dados do teste em si. Uma pré-condição não satisfeita pode causar falha de teste mesmo que o sistema não tenha nenhum defeito.

🧠 **Memorizar:** Pré-condições → Entradas → Ação → Resultados esperados → Pós-condições.

## 📖 Características do Teste Funcional

O Teste Funcional tem duas características centrais:

- **É independente da implementação** — não importa qual plataforma, framework ou linguagem de programação foi usada para construir o sistema, o teste funcional continua válido;
- **Os casos de teste são derivados da especificação do sistema** que está sendo testado, e não do código-fonte — idealmente deve haver uma especificação detalhada para se basear.

Essas características levantam uma reflexão importante, que motiva toda a aula: **quantos casos de teste possíveis existem para se testar cada funcionalidade de um sistema?** A resposta, como mostra o exemplo a seguir, costuma ser um número inviavelmente grande — o que justifica a necessidade de estratégias inteligentes de seleção de casos de teste.

### Exemplo: quantidade de casos de teste possíveis

Considere um comando `transforma` que recebe uma **entrada int** e devolve uma **saída int**. Considerando valores inteiros de 16 bits (menor valor -32768, maior valor 32767), existem **65.536 valores diferentes de entrada** possíveis — testar todos eles, um por um, é impraticável na maioria dos projetos reais.

### Exemplo: por que a escolha dos casos de teste importa

Suponha que o comando `transforma` foi **implementado incorretamente** como `saída = (entrada - 1) / 30000`, quando na verdade deveria ser `saída = (entrada + 1) / 30000`. Ao testar com entradas como 1, 42, 32000 e -32000, a escolha de **quais** valores usar determina se esse defeito específico será revelado ou não — alguns conjuntos de entrada podem, por coincidência, produzir a mesma saída nas duas versões (correta e incorreta) e "esconder" o defeito. Isso ilustra na prática por que **não basta testar "alguns valores quaisquer"** — é preciso um critério sistemático de escolha, que é justamente o papel das estratégias de teste funcional vistas a seguir.

## 📖 Projeto de Plano de Teste — formalização como problema de otimização

**O que é / Definição para prova:** seja **P** um programa a ser testado e **D(P)** o domínio de todos os casos de teste possíveis para P. Testar todo o domínio D(P) pode ser inviável (como no exemplo dos 65.536 valores). O projeto de um plano de teste é, formalmente, a busca por um **conjunto T** (sendo **T ⊂ D(P)**), bastante reduzido em relação a D(P), mas que, de certa maneira, **representa cada um dos elementos de D(P)**.

Informalmente, a pergunta que se está respondendo é: **qual o subconjunto de todos os casos de teste possíveis tem a maior probabilidade de detectar a maioria dos defeitos?**

🧠 **Memorizar:** P = programa · D(P) = domínio total de casos de teste · T ⊂ D(P) = subconjunto reduzido e representativo escolhido para testar.

## 📖 Estratégias de Teste Funcional

**O que é:** uma **estratégia de teste determina os critérios que devem ser seguidos para se gerar casos de teste** — ou seja, é o método sistemático usado para escolher o subconjunto T mencionado acima, em vez de escolher casos de teste de forma arbitrária. A aula apresenta cinco estratégias clássicas, detalhadas nas seções seguintes:

1. Particionamento de Equivalência
2. Análise do Valor Limite
3. Teste Funcional Sistêmico
4. Grafo Causa-Efeito
5. Error-Guessing

## 📖 Particionamento de Equivalência

**O que é / Definição para prova:** o **domínio de entrada do sistema é dividido em classes de equivalência**. A ideia central é que **dados de entrada em uma mesma classe de equivalência levariam o sistema a se comportar de forma similar e revelariam o mesmo defeito** — por isso, **apenas um dado de cada classe precisa ser usado para testar o sistema**, o que reduz o domínio de entrada a um tamanho viável. Da mesma forma que existem partições de entrada, também existem **partições de saída**: as entradas possíveis são divididas em classes, essas classes passam pelo sistema, e as saídas possíveis também se organizam em partições (incluindo a partição das "saídas corretas").

**Como funciona:** divide o domínio de entrada do software em classes de dados (classes de equivalência); os casos de teste são então derivados a partir dessas classes de equivalência, que podem ser **válidas** (dados que o sistema deveria aceitar) ou **inválidas** (dados que o sistema deveria rejeitar).

**Exemplo do PDF:** uma especificação de programa define que ele aceita **entradas de 4 a 10**, que sejam **valores inteiros**, de **cinco dígitos superiores a 10.000**. A partir disso, montam-se partições de entrada: para a primeira regra, "Menor do que 4" / "Entre 4 e 10" / "Mais do que 10"; para a segunda, "Menor do que 10000" / "Entre 10000 e 99999" / "Mais do que 99999". Cada uma dessas faixas é uma classe de equivalência, e basta escolher um valor representativo de cada uma (ex.: 3, 7, 11 para a primeira tabela) para gerar os casos de teste.

### Particionamento de Equivalência: diretrizes para definir as classes

As classes de equivalência podem ser definidas seguindo quatro diretrizes, cada uma com uma classe válida e uma ou duas classes inválidas:

| Diretriz | Classes geradas | Exemplo do PDF |
|---|---|---|
| 1. Se há **intervalo de valores** | 1 classe válida + 2 classes inválidas (abaixo e acima do intervalo) | `calculaPagamento(t, l)`: t é a taxa de participação no lucro (fica entre 0 e 1) e l é o lucro |
| 2. Se há **número (quantidade) de valores** | 1 classe válida + 2 classes inválidas (menos que o mínimo e mais que o máximo) | `formaEquipe(nalunos)`: equipe de alunos pode ter no mínimo 2 e no máximo 4 alunos |
| 3. Se há **conjunto de valores**, cada um processado de forma diferente | 1 classe válida para cada valor do conjunto + 1 classe inválida (geral) | `dosaMedicacao(paciente)`: paciente pode ser "criança", "adulto", "idoso" |
| 4. Se a condição de entrada especifica uma situação do tipo **"deve ser de tal forma"** | 1 classe válida + 1 classe inválida | `validaNovaSenha(senha)`: o primeiro caractere da senha deve ser um número |

### Particionamento de Equivalência: elemento distinto

**O que é:** um **elemento distinto** é um valor ou elemento que tem **tratamento diferenciado** dentro de uma classe. Se em uma classe houver um elemento distinto, isso implica em uma **partição em classes menores** — ou seja, esse valor especial precisa virar sua própria sub-classe, em vez de ficar misturado com os demais valores "normais" da classe original.

**Exemplo do PDF:** tratamento diferenciado para o **valor zero (0)** em alguns cálculos matemáticos (por exemplo, divisão por zero, ou zero sendo neutro em uma soma mas não em uma multiplicação).

🧠 **Memorizar:** classes válidas/inválidas · 1 valor representa a classe inteira · elemento distinto = valor especial vira sua própria sub-classe.

## 📖 Análise do Valor Limite

**O que é / Definição para prova:** essa estratégia **complementa o Particionamento de Equivalência**, partindo da conjectura de que **casos de teste que exploram condições limites têm maior probabilidade de encontrar defeitos** — ou seja, **os limites de uma classe de equivalência são fontes propícias a defeitos** (é ali que erros de "off-by-one", comparações com `<` em vez de `<=`, etc. costumam aparecer). Um **valor limite** é o valor imediatamente acima ou imediatamente abaixo do limite de uma classe de equivalência.

**Como funciona (diretrizes):**

1. Definir **classes vizinhas** no intervalo. Ex.: para um intervalo válido entre -1.0 e +1.0, testar: -1.1; -1.0; -0.9; +0.9; +1.0; +1.1.
2. Definir **limites vizinhos à quantidade de valores**. Ex.: para testar de 1 a 255 valores, testar: 0; 1; 2; 254; 255; 256.
3. Usar a diretriz 1 para **condições de saída**.
4. Usar a diretriz 2 para **condições de saída**.
5. Para entrada e saída de **conjunto ordenado**, dar maior atenção ao **primeiro e ao último elemento**.
6. Usar a **intuição** para definir outras condições limite.

**Exemplo do PDF:** para a partição "Menor do que 4 / Entre 4 e 10 / Mais do que 10", os valores limite testados são 3, 4, 7, 10, 11 (imediatamente abaixo e acima de cada fronteira, mais um valor interior). Para "Menor do que 10000 / Entre 10000 e 99999 / Mais do que 99999", os valores são 9999, 10000, 50000, 99999, 100000.

⚠️ **Pegadinha:** Particionamento de Equivalência escolhe **um valor qualquer, representativo, de cada classe**; Análise do Valor Limite escolhe especificamente **os valores nas fronteiras** entre classes — são técnicas complementares, não concorrentes, e costumam ser aplicadas juntas.

🧠 **Memorizar:** valor imediatamente acima/abaixo do limite · atenção especial a conjuntos ordenados (primeiro/último elemento).

## 📖 Teste Funcional Sistêmico

**O que é / Definição para prova:** essa estratégia **combina o Particionamento de Equivalência e a Análise do Valor Limite** de forma mais completa e sistemática, com um conjunto amplo de diretrizes práticas cobrindo diferentes tipos de dados. Ela **requer dois casos de teste de cada partição** e **avaliação nos limites de cada partição**.

**Diretrizes por tipo de dado:**

- **Valores numéricos:** na entrada, testar todos os valores discretos, os extremos e um valor interior do intervalo; na saída, gerar cada um dos extremos e um valor interior do intervalo.
- **Tipos de valores diferentes e casos especiais:** incluir exemplos como 0, valores em branco, etc.
- **Explorar tanto a entrada quanto a saída** com essas técnicas.
- **Valores ilegais:** incluir casos de teste com valores que são entradas ilegais (que o sistema deveria rejeitar).
- **Valores reais** (com casas decimais): limites de números reais podem não ser exatos, mas deve haver casos de teste aproximados dentro de uma margem de erro. Exemplo: números reais bem pequenos e também o zero.
- **Intervalos variáveis**, que dependem de um valor de entrada. Exemplo: para x variando de 0 a y, testar:
  - **Legais:** x=y=0; x=0<y; 0<x=y; 0<x<y;
  - **Ilegais:** y=0<x; 0<y<x; x<0; y<0.
- **Arranjos:** testar como única estrutura; testar como coleção de estruturas; testar subestruturas independentes.
- **Dados do tipo texto ou string:** validar o comprimento e o tipo de caracteres — alfabéticos, alfanuméricos e caracteres especiais.

🧠 **Memorizar:** 2 casos por partição + limites · valores especiais (0, branco) · reais com margem de erro · arranjos como estrutura única/coleção/subestrutura · strings: comprimento + tipo de caractere.

## 📖 Grafo Causa-Efeito

**O que é / Definição para prova:** um **Grafo Causa-Efeito** representa **conjuntos de condições sobre entradas (causas) e as ações correspondentes do sistema (efeitos)**, explorando **combinações de entrada de dados**. Uma **causa** é uma condição de entrada, estímulo ou qualquer coisa que provoque uma reação do sistema (um valor lógico — verdadeiro ou falso). Um **efeito** é uma ação realizada em resposta às diferentes condições de entrada — uma saída, mudança de estado ou qualquer resposta observável.

**Exemplo do PDF (especificação):** *"O primeiro caractere deve ser 'A' ou 'B'. O segundo caractere deve ser um número. Assim sendo, o arquivo deve ser atualizado. Se o primeiro caractere for incorreto, escrever X12. Se o segundo caractere não for número, escrever X13."*

A partir dessa especificação, identificam-se as causas e os efeitos:
- **C1** = o primeiro caractere é 'A'
- **C2** = o primeiro caractere é 'B'
- **C3** = o segundo caractere é um número
- **E1** = Atualiza o arquivo
- **E2** = Escreve X12
- **E3** = Escreve X13

### Operadores do grafo

O grafo liga causas a efeitos usando operadores lógicos, cada um com uma notação gráfica própria:

- **Identidade** — Se c1=1, então e1=1, senão e1=0 (ligação direta, sem símbolo);
- **Negação (NOT)** — Se c1=1, então e1=0, senão e1=1 (símbolo de onda `~`);
- **Ou (OR)** — Se c1=1 ou c2=1, então e1=1, senão e1=0 (símbolo `∨`);
- **E (AND)** — Se c1=1 e c2=1, então e1=1, senão e1=0 (símbolo `∧`).

### Restrições do grafo

Restrições limitam quais combinações de causas (ou efeitos) são fisicamente/logicamente possíveis:

| Restrição | Aplica-se a | Significado |
|---|---|---|
| **E (exclusiva)** | Causas | c1 e c2 não podem ser 1 simultaneamente |
| **I (inclusiva)** | Causas | c1 e c2 não podem ser 0 simultaneamente |
| **O (ou exclusivo/única)** | Causas | Um e somente um entre c1 e c2 deve ser igual a 1 |
| **R (requer)** | Efeitos | É impossível e1=1 se e2=0 |
| **M (mascara)** | Efeitos | Se e1=1, então e2=0 |

⚠️ **Pegadinha:** as restrições E, I, O se aplicam entre **causas**; as restrições R e M se aplicam entre **efeitos**. No exemplo do arquivo, C1 e C2 (primeiro caractere ser 'A' ou 'B') têm uma restrição do tipo E (não podem ser verdadeiras ao mesmo tempo, pois o caractere não pode ser 'A' e 'B' simultaneamente).

### Diretrizes para construir o grafo e gerar os casos de teste

1. Dividir a especificação do software em partes;
2. Identificar as causas e efeitos na especificação;
3. Criar o grafo de causa-efeito, ligando as causas aos efeitos;
4. Adicionar anotações ao grafo, descrevendo combinações de causas e efeitos impedidas por restrições sintáticas ou de ambiente;
5. Converter o grafo em **tabela de decisão**;
6. Converter as colunas da tabela em **casos de teste**.

### Tabela de decisão

**O que é:** uma tabela que **mostra os efeitos que ocorrem para todas as combinações de causas**. Se podem ocorrer **n** causas, a tabela contém **2ⁿ** entradas (linhas/colunas de combinações). 

**Passos para elaborar a tabela:**
1. Selecionar um efeito com valor 1;
2. Rastrear todas as combinações de causas (sujeitas a restrições) que fazem esse efeito ser 1;
3. Criar uma coluna na tabela para cada combinação de causa;
4. Determinar, para cada combinação, os estados de todos os outros efeitos, anotando na tabela.

**Exemplo do PDF (continuação do caso do arquivo):** com C1, C2, C3 como causas (3 causas → 2³ = 8 combinações/regras), a tabela de decisão relaciona cada combinação de T/F em C1, C2, C3 aos valores resultantes de E1, E2, E3. Por exemplo, na Regra 1 (C1=T, C2=T, C3=T) o efeito E1 (Atualiza) é T; na Regra 7 (C1=F, C2=F, C3=T) o efeito E2 (Msg X12) é T.

**Conversão para casos de teste:** cada linha/coluna da tabela de decisão vira um caso de teste. Algumas combinações são fisicamente impossíveis (ex.: primeiro caractere ser 'A' e 'B' ao mesmo tempo, dada a restrição E entre C1 e C2) e são marcadas como tal. As combinações possíveis geram casos de teste concretos, como ('A','5'), ('B','0'), ('C','3') ou ('Z','@') — combinando um valor que satisfaz (ou não) cada causa.

🧠 **Memorizar:** causa = condição de entrada (valor lógico) · efeito = ação/resposta do sistema · n causas → 2ⁿ linhas na tabela de decisão · cada linha da tabela = 1 caso de teste.

## 📖 Error-Guessing

**O que é / Definição para prova:** é uma **abordagem ad hoc** de geração de casos de teste — **supõe-se, por intuição e experiência, alguns tipos prováveis de erros e, a partir disso, define-se os casos de teste para detectá-los**. Diferente das estratégias anteriores, não segue um método sistemático e formal; depende do conhecimento e "faro" do testador sobre onde os erros costumam se esconder.

**Exemplo do PDF:** para um módulo de ordenação, testar:
- Lista de entrada vazia;
- Lista com apenas uma entrada;
- Todas as entradas com o mesmo valor;
- Lista de entrada já ordenada.

⚠️ **Pegadinha:** Error-Guessing não substitui as estratégias sistemáticas (Particionamento, Valor Limite, etc.) — ele as **complementa**, cobrindo casos "esquisitos" que a intuição do testador aponta como prováveis de esconder defeitos, mas que um método puramente formal poderia não gerar.

🧠 **Memorizar:** ad hoc = intuição + experiência · exemplo clássico: lista vazia, lista com 1 item, todos iguais, já ordenada.

---

## 📚 Resumão final

- Teste Funcional trata o sistema como **caixa preta**: caso de teste = pré-condições, entradas, ação, resultados esperados e pós-condições.
- Testar **todo** o domínio de entrada costuma ser inviável (ex.: 65.536 valores para um `int` de 16 bits), por isso o projeto de plano de teste é formalizado como escolher um subconjunto T ⊂ D(P) representativo.
- As cinco estratégias clássicas de Teste Funcional são: **Particionamento de Equivalência**, **Análise do Valor Limite**, **Teste Funcional Sistêmico**, **Grafo Causa-Efeito** e **Error-Guessing**.
- **Particionamento de Equivalência** divide entradas em classes válidas/inválidas e testa um valor por classe, seguindo 4 diretrizes (intervalo, quantidade, conjunto de valores, "deve ser de tal forma").
- **Análise do Valor Limite** complementa o particionamento testando os valores nas fronteiras das classes, pois é ali que defeitos são mais prováveis.
- **Teste Funcional Sistêmico** combina as duas técnicas anteriores com diretrizes detalhadas por tipo de dado (numérico, real, string, arranjo, intervalo variável).
- **Grafo Causa-Efeito** modela combinações lógicas de causas e efeitos (com operadores identidade/NOT/OR/AND e restrições E/I/O/R/M), convertendo o grafo em tabela de decisão (2ⁿ linhas) e depois em casos de teste.
- **Error-Guessing** é uma abordagem ad hoc baseada na intuição do testador para prever tipos prováveis de erro.

## ⚠️ Pontos que podem cair na prova

- Os 5 elementos de um caso de teste (pré-condições, entradas, ação, resultados esperados, pós-condições).
- Por que testar o domínio inteiro é inviável, e a formalização P / D(P) / T ⊂ D(P).
- As 4 diretrizes de Particionamento de Equivalência e seus exemplos (intervalo, quantidade, conjunto, "deve ser de tal forma").
- O conceito de **elemento distinto** no Particionamento de Equivalência.
- As 6 diretrizes de Análise do Valor Limite.
- Diferença entre Particionamento de Equivalência (um valor por classe) e Análise do Valor Limite (valores nas fronteiras).
- As diretrizes do Teste Funcional Sistêmico por tipo de dado (numérico, real, string, arranjo, intervalo variável).
- Grafo Causa-Efeito: diferença entre causa e efeito; os quatro operadores (identidade, negação, OU, E); as cinco restrições (E, I, O para causas; R, M para efeitos); como construir e converter a tabela de decisão (2ⁿ linhas) em casos de teste.
- Error-Guessing como abordagem ad hoc, e seu exemplo clássico (lista vazia, um item, todos iguais, já ordenada).

## 📝 Perguntas para revisão

1. O que caracteriza o Teste Funcional como técnica de "caixa preta"?
2. Quais são os cinco elementos que compõem um caso de teste completo?
3. Por que geralmente não é viável testar todo o domínio de entrada de um sistema? Use o exemplo do comando `transforma`.
4. Como o projeto de plano de teste é formalizado como um problema de otimização?
5. Quais são as cinco estratégias clássicas de Teste Funcional apresentadas na aula?
6. Explique o Particionamento de Equivalência e cite suas quatro diretrizes de definição de classes.
7. O que é um "elemento distinto" no contexto do Particionamento de Equivalência?
8. O que é a Análise do Valor Limite e por que ela complementa o Particionamento de Equivalência?
9. Cite três diretrizes do Teste Funcional Sistêmico.
10. O que são causas e efeitos em um Grafo Causa-Efeito? Explique os operadores identidade, negação, OU e E.
11. Qual a diferença entre as restrições E, I, O (causas) e R, M (efeitos) no Grafo Causa-Efeito?
12. Como se constrói uma tabela de decisão a partir de um Grafo Causa-Efeito, e quantas entradas ela tem para n causas?
13. O que é Error-Guessing e qual seu exemplo clássico para um módulo de ordenação?

## Gabarito

1. O sistema é considerado uma caixa preta porque o testador não observa o código internamente, apenas fornece um dado de teste como entrada e compara a saída gerada com a saída esperada, sem se importar com como o sistema chegou a esse resultado.
2. Pré-condições (estado obrigatório antes do teste), Entradas (dados fornecidos), Ação (execução testada), Resultados esperados (saídas conhecidas correspondentes à entrada) e Pós-condições (estado obrigatório após a execução).
3. Porque o domínio de entrada pode ser gigantesco — no exemplo do comando `transforma` com entrada/saída `int` de 16 bits, existem 65.536 valores diferentes de entrada possíveis, tornando inviável testar cada um individualmente.
4. Sendo P um programa e D(P) o domínio de todos os casos de teste possíveis para P, busca-se um conjunto T (T ⊂ D(P)), bem menor que D(P), mas que represente cada um dos elementos de D(P) — ou seja, o subconjunto de casos de teste com maior probabilidade de detectar a maioria dos defeitos.
5. Particionamento de Equivalência, Análise do Valor Limite, Teste Funcional Sistêmico, Grafo Causa-Efeito e Error-Guessing.
6. O domínio de entrada é dividido em classes de equivalência, e apenas um dado de cada classe precisa ser testado, pois dados da mesma classe tenderiam a revelar o mesmo defeito. As quatro diretrizes: (1) se há intervalo de valores → 1 classe válida + 2 inválidas; (2) se há número/quantidade de valores → 1 classe válida + 2 inválidas; (3) se há conjunto de valores processado de forma diferente → 1 classe válida por valor + 1 inválida; (4) se a condição é do tipo "deve ser de tal forma" → 1 classe válida + 1 inválida.
7. É um valor ou elemento que tem tratamento diferenciado dentro de uma classe; se existir, implica em particionar essa classe em classes menores (exemplo: o valor zero em cálculos matemáticos).
8. É a estratégia que testa os valores imediatamente acima e abaixo dos limites de cada classe de equivalência, pois se conjectura que os limites são fontes propícias a defeitos. Ela complementa o Particionamento de Equivalência porque este escolhe um valor qualquer representativo da classe, enquanto a Análise do Valor Limite foca especificamente nas fronteiras entre classes.
9. Exemplos válidos: testar valores numéricos discretos, extremos e interiores tanto na entrada quanto na saída; incluir casos especiais como 0 e valores em branco; incluir valores ilegais; para valores reais, usar aproximações dentro de uma margem de erro; testar arranjos como estrutura única, coleção de estruturas e subestruturas independentes; validar comprimento e tipo de caracteres em strings.
10. Causa é uma condição de entrada, estímulo ou qualquer coisa que provoque uma reação do sistema (valor lógico); efeito é uma ação realizada em resposta a essas condições (saída, mudança de estado ou resposta observável). Identidade: se c1=1, e1=1, senão e1=0. Negação: se c1=1, e1=0, senão e1=1. OU: se c1=1 ou c2=1, e1=1, senão e1=0. E: se c1=1 e c2=1, e1=1, senão e1=0.
11. As restrições E, I e O se aplicam entre causas: E impede que duas causas sejam 1 simultaneamente; I impede que duas causas sejam 0 simultaneamente; O exige que exatamente uma das duas causas seja 1. As restrições R e M se aplicam entre efeitos: R torna impossível um efeito ser 1 se outro for 0; M diz que se um efeito for 1, o outro deve ser 0.
12. Seleciona-se um efeito com valor 1, rastreiam-se todas as combinações de causas (respeitando as restrições) que fazem esse efeito ser 1, cria-se uma coluna para cada combinação de causa, e determina-se o estado de todos os outros efeitos para cada combinação. Para n causas, a tabela contém 2ⁿ entradas (combinações possíveis).
13. Error-Guessing é uma abordagem ad hoc em que se supõe, por intuição e experiência, tipos prováveis de erro, definindo casos de teste para detectá-los. Exemplo clássico para um módulo de ordenação: testar lista de entrada vazia, lista com apenas uma entrada, todas as entradas com o mesmo valor, e lista de entrada já ordenada.
