# Do Requisito ao Caso de Teste

## 📖 Por que testar importa: casos reais de bugs caros

A aula abre com cinco incidentes reais para mostrar que **nenhum bug famoso foi "só um bug de código"** — todos são, na raiz, **lacunas entre o que deveria acontecer (o requisito) e o que foi de fato verificado (o teste)**. Em todos os casos, um cenário de teste bem pensado — e pensado cedo — poderia ter revelado o problema antes do lançamento. O ponto central da aula é justamente esse: o **custo de achar um defeito depois (em produção, no ar, em uso) é ordens de grandeza maior do que achar antes**.

| Caso | Ano | O que aconteceu | Custo |
|---|---|---|---|
| **Therac-25** | 1985–1987 | Máquina de radioterapia computadorizada; uma condição de corrida no software permitia que edições rápidas do operador ignorassem interlocks de segurança que, em modelos anteriores, existiam fisicamente no hardware. Essa verificação nunca foi testada de fato. | ≥ 3 mortes confirmadas (em 6 acidentes) |
| **Ariane 5** | 1996 | Um módulo do Ariane 4 foi reaproveitado sem ser revalidado contra os requisitos de voo do Ariane 5; um valor de velocidade horizontal (64 bits) foi convertido para um inteiro de 16 bits e estourou. | US$ 370 mi perdidos em 37 segundos |
| **Mars Climate Orbiter** | 1999 | A Lockheed Martin calculou o empuxo dos propulsores em libras-força; a JPL/NASA esperava newtons. A especificação de interface nunca foi validada por um teste de integração de ponta a ponta. | US$ 327,6 mi de missão perdidos no espaço |
| **Knight Capital Group** | 2012 | Uma rotina de teste obsoleta ("Power Peg") ficou em um dos 8 servidores; uma flag reaproveitada a reativou em produção, disparando ~4 milhões de ordens erradas. Nenhuma verificação cobriu a configuração completa do deploy. | US$ 440–460 mi perdidos em 45 minutos |
| **CrowdStrike** | 2024 | Uma atualização de "conteúdo" (não tratada com o mesmo rigor de teste do código) passou pelo validador sem ser barrada, causando leitura de memória fora dos limites em sistemas Windows no mundo todo. | US$ 5,4 bi + 8,5 milhões de PCs travados |

⚠️ **Pegadinha:** o denominador comum entre esses casos não é "código malfeito" — é falta de teste no ponto certo (interlocks nunca testados, código reaproveitado sem revalidação, unidades de medida nunca confrontadas em teste de integração, teste obsoleto sem verificação de deploy, atualização de conteúdo tratada com menos rigor que código).

**Custo agregado dos bugs:** segundo o NIST/RTI ("The Economic Impacts of Inadequate Infrastructure for Software Testing", 2002), bugs de software custam **US$ 59,5 bilhões por ano** à economia dos EUA, e **mais de 1/3 desse custo seria evitável** com infraestrutura de teste melhor — ou seja, encontrando defeitos mais cedo no processo de desenvolvimento.

🧠 **Memorizar:** todo bug caro = lacuna requisito↔teste · achar defeito depois custa ordens de grandeza mais · US$59,5 bi/ano, 1/3 evitável.

## 📖 Testar Cedo

**O que é:** "testar cedo", na prática, significa **pensar em cenários de teste desde o documento de requisitos** — não esperar o código pronto para começar a pensar em teste. É a virada de mentalidade que resume a lição de todos os casos acima: o teste não é uma etapa que vem depois de programar, é algo que começa junto com a escrita do requisito.

## 📖 O Modelo V

**O que é:** um modelo que organiza o desenvolvimento de software em duas frentes espelhadas — de um lado as atividades de **definição** (decompor o que construir), do outro as atividades de **verificação** (confirmar que foi construído certo) — conectadas na base pela **Codificação**. Cada nível de definição tem um nível de verificação correspondente, formando um "V".

**Como funciona (correspondências):**

| Lado de Definição | Lado de Verificação |
|---|---|
| Requisitos | Teste de Aceitação |
| Especificação | Teste de Sistema |
| Design da Arquitetura | Teste de Integração |
| Design Detalhado | Teste de Unidade |

Os dois lados se encontram, na base do V, na **Codificação**.

🧠 **Memorizar:** Requisitos↔Aceitação · Especificação↔Sistema · Arquitetura↔Integração · Design Detalhado↔Unidade.

## 📖 Do requisito ao dado de teste (o pipeline conceitual)

**O que é:** a aula propõe uma cadeia de quatro conceitos que transforma progressivamente um requisito (algo abstrato) em algo executável e verificável:

1. **Requisito** — o que o sistema deve fazer;
2. **Cenário de Teste** — uma situação a ser verificada;
3. **Caso de Teste** — passos + dados + resultado esperado;
4. **Massa de Teste** — os dados concretos usados.

Essa cadeia é o fio condutor de toda a aula: cada seção seguinte detalha um desses elos.

### Requisito, cenário, caso e suíte não são sinônimos

Um erro comum é tratar esses quatro termos como equivalentes. Eles representam **níveis de abstração diferentes** do mesmo trabalho:

| Termo | Definição |
|---|---|
| **Requisito** | O comportamento esperado do sistema, descrito na especificação. |
| **Cenário de teste** | Uma situação de alto nível a ser verificada (ex.: "cupom expirado"). |
| **Caso de teste** | A concretização de um cenário: pré-condição, passos, dados e resultado esperado. |
| **Suíte de teste** | Um conjunto de casos de teste agrupados por objetivo, módulo ou execução. |

⚠️ **Pegadinha:** um cenário é uma ideia de alto nível ("cupom expirado"); um caso de teste é essa ideia já transformada em algo executável, com dados e passos concretos. Não confunda os dois em prova.

🧠 **Memorizar:** Requisito (comportamento) → Cenário (situação) → Caso (execução concreta) → Suíte (agrupamento de casos).

## 📖 O que torna um requisito testável

Para que um requisito possa gerar bons cenários e casos de teste, ele precisa ter quatro qualidades:

- **Específico** — descreve um comportamento concreto, não uma intenção vaga;
- **Verificável** — é possível observar um resultado e dizer "passou" ou "falhou";
- **Com critério de aceite** — deixa claro qual é o resultado esperado, inclusive nos limites;
- **Sem ambiguidade** — não permite duas leituras diferentes por duas pessoas diferentes.

**Exemplo do PDF:** o requisito "**O sistema deve ser rápido**" falha em todos os quatro critérios, pois levanta perguntas sem resposta única: rápido para quem? Em qual cenário? Comparado a quê? Isso gera interpretações divergentes entre os envolvidos:
- Dev A entende: "responde em até 2 segundos, no meu notebook";
- QA entende: "responde em até 2 segundos, com 1000 usuários simultâneos";
- Cliente entende: "mais rápido que o sistema antigo, em qualquer situação".

Uma **versão testável** do mesmo requisito seria: *"A página de resultados deve carregar em até 2 segundos, com até 1000 usuários simultâneos, em 95% das requisições."* — aqui já há métrica, condição de carga e critério de aceite (95%), eliminando a ambiguidade.

🧠 **Memorizar:** específico · verificável · critério de aceite · sem ambiguidade — "rápido" sozinho não atende nenhum dos quatro.

## 📖 Quatro perguntas para começar a pensar em teste

Diante de qualquer requisito, a aula propõe quatro perguntas-guia para gerar cenários de teste de forma sistemática, cobrindo tanto o uso normal quanto os casos de risco:

- **Caminho feliz** — qual é o uso normal, esperado, do requisito?
- **O que pode dar errado** — quais entradas inválidas ou falhas o sistema precisa tratar?
- **Limites e extremos** — o que acontece exatamente na fronteira de uma regra?
- **O que NÃO deveria acontecer** — existe algo que o sistema precisa impedir explicitamente?

Essas quatro perguntas são o método prático usado no exemplo do cupom de desconto (próxima seção) para chegar a um conjunto completo de cenários de teste a partir de um único requisito.

🧠 **Memorizar:** caminho feliz · o que pode dar errado · limites e extremos · o que não deveria acontecer.

## 📖 A matriz de rastreabilidade

**O que é:** uma ferramenta simples de gestão de qualidade em que **cada requisito aponta para os casos de teste que o cobrem, e cada caso de teste aponta de volta para o requisito**. Na prática, é uma tabela cruzando requisitos (linhas) com casos de teste (colunas), marcando com um "✓" quais casos cobrem cada requisito.

**Exemplo do PDF:** uma matriz cruzando os requisitos RF-010 (Cupom de desconto), RF-011 (Cancelamento de pedido) e RF-012 (Login do cliente) contra os casos de teste CT-01 a CT-05, mostrando, por exemplo, que RF-010 é coberto pelos casos CT-01, CT-02, CT-03 e CT-05, mas não pelo CT-04. Isso serve para garantir que nenhum requisito fique sem cobertura de teste e que nenhum caso de teste exista sem propósito claro.

## 📖 Exemplo prático completo: RF-010 — Cupom de desconto

**O requisito (RF-010 — Aplicação de Cupom de Desconto):** *"O sistema deve permitir que o cliente aplique um cupom de desconto ao carrinho de compras. O desconto só deve ser aplicado se o valor total do carrinho for igual ou superior ao valor mínimo definido pelo cupom. Cada cupom possui uma data de validade e um limite de uso por cliente."*

**Aplicando as quatro perguntas a esse requisito:**

| Pergunta | Resposta aplicada ao RF-010 |
|---|---|
| Caminho feliz | Carrinho acima do valor mínimo + cupom válido → desconto aplicado. |
| O que pode dar errado | Cupom expirado, ou já usado pelo cliente. |
| Limites e extremos | Carrinho com valor EXATAMENTE igual ao mínimo do cupom. |
| O que NÃO deveria acontecer | Aplicar dois cupons na mesma compra — o requisito fala disso? |

**Os seis cenários derivados do RF-010:**
1. Cupom válido, carrinho acima do mínimo;
2. Carrinho abaixo do valor mínimo do cupom;
3. Cupom expirado;
4. Cupom já utilizado pelo cliente (limite atingido);
5. Carrinho com valor EXATAMENTE igual ao mínimo ⚠️;
6. Dois cupons aplicados na mesma compra ⚠️.

Os cenários 5 e 6 são destacados porque nascem diretamente das perguntas "limites e extremos" e "o que não deveria acontecer" — são exatamente os casos que **só aparecem quando alguém para para perguntar "e se...?" antes de codificar**.

### Todo caso de teste precisa responder 4 perguntas

Um cenário de teste, por si só, ainda é abstrato ("cupom expirado"). Para virar um **caso de teste** executável, ele precisa responder a quatro perguntas:

- **Pré-condição** — o que precisa ser verdade antes de começar?
- **Passos** — o que o testador (ou script) faz, em ordem?
- **Dados de entrada** — quais valores concretos são usados?
- **Resultado esperado** — o que define "passou" de forma inequívoca?

**Exemplo — CT-005 (Valor do carrinho exatamente no mínimo):**

| Campo | Conteúdo |
|---|---|
| Pré-condição | Cliente logado; cupom "DESC10" válido; valor mínimo definido = R$ 100,00 |
| Passos | 1) Adicionar produto de R$ 100,00 ao carrinho. 2) Aplicar o cupom DESC10. |
| Dados de entrada | Cupom: DESC10 \| Valor do carrinho: R$ 100,00 (exato) |
| Resultado esperado | O requisito diz "igual ou superior", então o desconto deveria ser aplicado |

Esse exemplo mostra na prática por que escrever o caso de teste é valioso mesmo antes de existir código: ao preencher o campo "resultado esperado", o testador é forçado a **voltar ao texto exato do requisito** para decidir o comportamento correto no limite — expondo, de quebra, se o requisito está claro o suficiente.

⚠️ **Pegadinha:** um bom caso de teste **não serve só para verificar o sistema depois de pronto** — ele **expõe requisitos malfeitos antes que virem código**. Os cenários 05 (limite exato) e 06 (dois cupons) do exemplo só existem porque alguém perguntou "e se...?" antes de escrever qualquer linha de código; sem esse exercício, essas decisões teriam sido tomadas sem querer, no meio da implementação, por quem escreveu o código (e não por quem definiu o requisito).

🧠 **Memorizar:** pré-condição · passos · dados de entrada · resultado esperado.

---

## 📚 Resumão final

- Casos reais (Therac-25, Ariane 5, Mars Climate Orbiter, Knight Capital, CrowdStrike) mostram que bugs caros são sempre lacunas entre requisito e teste, e que testar cedo é ordens de grandeza mais barato que corrigir depois.
- **Testar cedo** significa pensar em teste desde o documento de requisitos, não esperar o código pronto.
- O **Modelo V** liga cada etapa de definição (Requisitos, Especificação, Arquitetura, Design Detalhado) a uma etapa de verificação correspondente (Aceitação, Sistema, Integração, Unidade).
- O pipeline conceitual é **Requisito → Cenário de Teste → Caso de Teste → Massa de Teste**, e esses quatro termos não são sinônimos.
- Um requisito testável precisa ser **específico, verificável, com critério de aceite e sem ambiguidade** (ver exemplo "o sistema deve ser rápido").
- As **quatro perguntas** (caminho feliz, o que pode dar errado, limites e extremos, o que não deveria acontecer) são o método para gerar cenários de teste a partir de um requisito.
- A **matriz de rastreabilidade** garante que todo requisito tenha cobertura de teste e todo caso de teste tenha propósito.
- O exemplo do **cupom de desconto (RF-010)** aplica tudo isso na prática, gerando 6 cenários e detalhando um caso de teste (CT-005) com as 4 perguntas obrigatórias (pré-condição, passos, dados de entrada, resultado esperado).

## ⚠️ Pontos que podem cair na prova

- Os cinco casos reais de bugs (nome, ano, causa raiz, custo) — tabela na primeira seção.
- As correspondências do **Modelo V** (qual verificação corresponde a qual definição).
- Diferença entre **requisito, cenário de teste, caso de teste e suíte de teste**.
- Os **quatro critérios** que tornam um requisito testável, e o exemplo "o sistema deve ser rápido".
- As **quatro perguntas** para gerar cenários de teste.
- As **quatro perguntas** que todo caso de teste precisa responder (diferente das quatro perguntas de cenário — não confundir as duas listas de "4 perguntas").
- O propósito da matriz de rastreabilidade.
- O exemplo do RF-010 (cupom de desconto) e seus 6 cenários, especialmente os cenários 05 e 06 (limite exato e dois cupons).

## 📝 Perguntas para revisão

1. Qual é a lição comum entre os cinco incidentes reais apresentados na aula (Therac-25, Ariane 5, Mars Climate Orbiter, Knight Capital e CrowdStrike)?
2. O que significa "testar cedo" na prática?
3. Quais são as quatro correspondências do Modelo V entre definição e verificação?
4. Qual é a cadeia de quatro elementos que transforma um requisito em algo executável?
5. Explique a diferença entre requisito, cenário de teste, caso de teste e suíte de teste.
6. Quais são os quatro critérios que tornam um requisito testável? Use o exemplo "o sistema deve ser rápido" para justificar.
7. Quais são as quatro perguntas usadas para gerar cenários de teste a partir de um requisito?
8. Para que serve a matriz de rastreabilidade?
9. Quais são as quatro perguntas que todo caso de teste precisa responder?
10. No exemplo do cupom de desconto (RF-010), por que os cenários 05 e 06 são especialmente importantes?

## Gabarito

1. Todos são, na raiz, lacunas entre o requisito (o que deveria acontecer) e o teste (o que foi de fato verificado): em todos os casos, um cenário de teste bem pensado e pensado cedo poderia ter revelado o problema antes do lançamento, e o custo de corrigir depois (em produção) foi ordens de grandeza maior do que teria sido corrigir antes.
2. Significa pensar em cenários de teste desde o documento de requisitos, sem esperar o código pronto para começar a pensar em teste.
3. Requisitos ↔ Teste de Aceitação; Especificação ↔ Teste de Sistema; Design da Arquitetura ↔ Teste de Integração; Design Detalhado ↔ Teste de Unidade. Os dois lados se encontram na Codificação.
4. Requisito (o que o sistema deve fazer) → Cenário de Teste (situação a ser verificada) → Caso de Teste (passos + dados + resultado esperado) → Massa de Teste (dados concretos usados).
5. Requisito é o comportamento esperado descrito na especificação; cenário de teste é uma situação de alto nível a ser verificada (ex.: "cupom expirado"); caso de teste é a concretização de um cenário, com pré-condição, passos, dados e resultado esperado; suíte de teste é um conjunto de casos de teste agrupados por objetivo, módulo ou execução.
6. Específico (descreve comportamento concreto, não intenção vaga), verificável (é possível dizer "passou" ou "falhou"), com critério de aceite (deixa claro o resultado esperado, inclusive nos limites) e sem ambiguidade (não permite duas leituras diferentes). "O sistema deve ser rápido" falha em todos, pois não define para quem, em qual cenário, nem comparado a quê — gerando interpretações diferentes entre Dev, QA e Cliente.
7. Caminho feliz (uso normal esperado); o que pode dar errado (entradas inválidas ou falhas); limites e extremos (o que acontece na fronteira de uma regra); o que NÃO deveria acontecer (algo que o sistema precisa impedir explicitamente).
8. Para garantir que cada requisito aponte para os casos de teste que o cobrem e que cada caso de teste aponte de volta para o requisito correspondente, evitando requisitos sem cobertura de teste ou casos de teste sem propósito claro.
9. Pré-condição (o que precisa ser verdade antes de começar), passos (o que o testador/script faz, em ordem), dados de entrada (quais valores concretos são usados) e resultado esperado (o que define "passou" de forma inequívoca).
10. Porque eles só existem devido às perguntas "limites e extremos" (carrinho com valor exatamente igual ao mínimo) e "o que não deveria acontecer" (dois cupons na mesma compra) — são exemplos de como um bom caso de teste expõe decisões e requisitos malfeitos antes que virem código, evitando que essas decisões sejam tomadas sem querer durante a implementação.
