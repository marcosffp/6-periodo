# Teste de Software — Introdução e Terminologia

Prof. Cleiton Tavares — PUC Minas, Engenharia de Software

## 📖 Verificação, Validação e Teste (VV&T)

**O que é / Definição para prova:** VV&T é o conjunto de atividades usadas para garantir que um software está sendo construído corretamente e é o software certo. Ele se divide em três conceitos que são frequentemente confundidos entre si, mas têm focos diferentes: **Verificação** — *"Estamos construindo o produto da maneira certa?"* — é o **processo de avaliar um artefato de software (código, documento, modelo ou até o executável) para determinar se ele atende às especificações impostas**, ou seja, checa se o software atende aos requisitos funcionais e não funcionais definidos. **Validação** — *"Estamos construindo o produto certo?"* — é o **processo de avaliar um sistema ou componente durante ou no final do desenvolvimento para determinar se ele atende às necessidades do usuário e das partes interessadas**; é mais geral que a verificação, pois vai além do que foi formalmente especificado, cobrindo também expectativas implícitas do cliente. Normas internacionais que tratam do tema: IEEE 1012, ISO/IEC 12207 e ISO/IEC 29119.

**Como funciona / Características:**
- Verificação: pode ser **estática** (revisões, análise estática de código) ou **dinâmica** (execução do sistema para checar requisitos).
- Validação: é **predominantemente dinâmica**, mas não é obrigatoriamente só isso — ex.: validar um protótipo em papel com o cliente já é uma validação estática.
- **Teste**: é **sempre dinâmico** — consiste em executar o sistema em busca de erros/falhas.

| Verificação | Validação |
|---|---|
| "Construindo certo?" | "Construindo o certo?" |
| Confere se atende requisitos (funcionais/não funcionais) | Confere se atende necessidades/expectativas do usuário |
| Pode ser estática ou dinâmica | Predominantemente dinâmica |
| Mais restrita ao que foi especificado | Mais geral, vai além do especificado |

🧠 **Memorizar:** Verificação = produto certo (requisitos) · Validação = certo produto (usuário) · Teste = sempre dinâmico.

## 📖 VV&T Estáticas vs. Dinâmicas

**O que é / Definição para prova:** Além de classificar VV&T por foco (verificação/validação), também se classifica pela forma de execução. Atividades **estáticas** **não requerem a existência de um programa ou modelo executável nem a execução do código** — exemplos incluem revisões de documentos e análise estática de código-fonte. Atividades **dinâmicas se baseiam na execução de um programa** real. O **Teste de Software é, por definição, sempre uma atividade dinâmica**, pois exige rodar o sistema para observar seu comportamento.

🧠 **Memorizar:** Estática = sem executar · Dinâmica = executando · Teste = sempre dinâmico.

## 📖 Termos do Jargão: Defeito, Erro e Falha

**O que é / Definição para prova:** São três termos técnicos relacionados, mas distintos, usados para descrever a cadeia de causa-e-efeito de um problema em software. **Defeito (fault)** é **uma deficiência algorítmica, de definição de dados ou processo que, se ativada, pode levar a uma falha** — é o que popularmente se chama de "bug", presente no código-fonte antes mesmo de o programa rodar. **Erro (error)** é **um estado de execução inconsistente ou inesperado** — ocorre em tempo de execução, quando o defeito é "ativado" e produz um valor ou estado interno errado na memória. **Falha (failure)** é **um evento notável em que o sistema viola suas especificações** — é o efeito visível ao usuário, quando o comportamento incorreto se manifesta externamente. Essas definições ajudam a distinguir os diferentes elementos envolvidos com o problema, mas **não são unanimidade na Engenharia de Software** e **não são seguidas consistentemente o tempo todo** — ou seja, diferentes autores/times podem usar os termos de forma um pouco diferente.

**Exemplo:** Sistema que calcula a média de 3 notas. O defeito está no código-fonte: `double media = (nota1 + nota2 + nota3) / 4;` — divide por 4 (fixo) em vez de dividir pela quantidade real de notas (3). Com as notas 8, 7 e 9: a soma é 24; o sistema calcula 24/4 = 6 — esse valor 6 armazenado incorretamente em memória é o **erro**. Por fim, o programa exibe ao usuário "Sua média é: 6.0" quando deveria ser 8.0 — esse comportamento visível que viola a especificação é a **falha**. Isso ilustra bem a cadeia: defeito no código → erro em tempo de execução → falha percebida pelo usuário.

Um segundo exemplo (sistema bancário) reforça o padrão: **defeito** = fórmula de juros implementada com sinal errado (`valor * -taxa`); **erro** = durante a execução, o saldo do cliente fica negativo quando deveria ficar positivo; **falha** = o cliente vê no extrato que seu saldo foi reduzido incorretamente e reclama.

⚠️ **Pegadinha:** Não confundir a ordem/causalidade: o defeito está no código (estático, existe antes de rodar), o erro é o estado interno errado durante a execução, e a falha é o sintoma externo visível pelo usuário. Um defeito pode existir no código sem nunca causar erro/falha, se aquele trecho nunca for "ativado".

🧠 **Memorizar:** Defeito (fault/bug, no código) → Erro (error, estado errado em execução) → Falha (failure, visível ao usuário, viola especificação).

## 📖 Teste de Software e Debugging

**O que é / Definição para prova:** **Teste de Software** é a atividade dinâmica cujo **objetivo é revelar a presença de defeitos no software**; quando não encontra defeitos, o teste falha nesse objetivo primário, mas ainda cumpre um papel importante: **busca aumentar a confiança sobre o software**. Isso está resumido na célebre frase de Edsger Dijkstra: **"Os testes podem mostrar apenas a presença de erros, e não sua ausência"** — ou seja, passar em todos os testes não prova que o software está livre de defeitos, apenas que os defeitos testados não foram encontrados. **Debugging (depuração)** é a atividade que ocorre como **consequência não previsível do teste**: depois que um teste revela a presença de um defeito, esse defeito precisa ser **encontrado e corrigido** — esse processo de localização e correção é o debugging.

🧠 **Memorizar:** Teste = revelar defeitos (aumenta confiança) · Debugging = achar e corrigir o defeito já revelado · Frase de Dijkstra = testes só mostram presença, não ausência de erros.

## 📖 Categorização do Teste: Tipos, Técnicas e Níveis

**O que é / Definição para prova:** O material organiza o teste de software em três eixos independentes de categorização, que podem ser combinados entre si: **Tipos de teste** (o que se testa em termos de qualidade — ex.: Teste de Funcionalidade, Teste de Usabilidade, Teste de Performance, Teste de Segurança), **Técnicas de Teste** (como o teste é conduzido em relação ao conhecimento da estrutura interna — Caixa Branca, Caixa Preta, Caixa Cinza) e **Níveis de Teste** (em que estágio do ciclo de vida o teste ocorre — Teste de Unidade, Teste de Integração, Teste de Sistema, Teste de Aceitação/Visão de Cliente). Esses três eixos são tratados como dimensões ortogonais: por exemplo, é possível fazer um teste de Segurança (tipo), usando técnica Caixa Preta, no nível de Sistema.

🧠 **Memorizar:** Tipos (o quê) · Técnicas (como/quanto se conhece por dentro) · Níveis (quando no ciclo de vida).

## 📖 Técnicas de Teste: Caixa Branca, Caixa Preta e Caixa Cinza

**O que é / Definição para prova:** As técnicas de teste diferem pelo grau de conhecimento que o testador tem sobre a estrutura interna do software. O **Teste Caixa Branca** (técnica estrutural) é aquele em que **o testador conhece a estrutura interna do software** e testa fluxos da estrutura e a lógica interna do código — nesse caso, testa-se "como programador". O **Teste Caixa Preta** (técnica funcional) é aquele em que **o testador não conhece a estrutura interna do software**, sendo orientado apenas pela entrada e saída de dados — testa-se "como usuário". O **Teste Caixa Cinza** é uma técnica híbrida que **combina elementos de teste de caixa branca para otimizar a geração de casos de teste de caixa preta** — o testador conhece a estrutura interna apenas no que é relevante ao teste, testando como um "usuário que conhece a implementação".

**Como funciona / Características:**
- Caixa Branca: estrutura interna conhecida → testa-se como programador.
- Caixa Preta: estrutura interna não conhecida → testa-se como usuário.
- Caixa Cinza: estrutura interna conhecida parcialmente (só o relevante) → testa-se como usuário que conhece a implementação, usando esse conhecimento para otimizar os casos de teste caixa preta.

| Caixa Branca | Caixa Preta | Caixa Cinza |
|---|---|---|
| Conhece estrutura interna | Não conhece estrutura interna | Conhece só o relevante ao teste |
| Testa lógica/fluxos internos | Testa entrada/saída | Usa conhecimento interno para otimizar testes de entrada/saída |
| Visão de programador | Visão de usuário | Usuário que conhece a implementação |

🧠 **Memorizar:** Branca = por dentro (programador) · Preta = por fora (usuário) · Cinza = mistura (usuário "espiando" por dentro).

## 📖 Níveis de Teste de Desenvolvimento (Teste Unitário, Componente/Integração, Sistema)

**O que é / Definição para prova:** Os níveis de teste realizados durante o desenvolvimento geralmente usam técnica **Caixa Branca e visam encontrar bugs**. São três: o **Teste Unitário (Teste de Unidade)**, em que **unidade é a menor parte do software** (por exemplo, uma função), e o objetivo é **testar independentemente cada unidade**; o **Teste de Componente (também chamado Teste de Integração)**, em que **componentes são compostos por diversos objetos que interagem e fornecem uma interface padrão**, e o objetivo é **testar a interface padrão dos componentes**; e o **Teste de Sistema**, em que **o sistema é testado com os componentes já integrados**, com o objetivo de **testar a compatibilidade na interação entre os componentes**.

**Como funciona / Características (progressão dos níveis):**
- Unidade → menor parte isolada (ex.: uma função).
- Componente/Integração → interface padrão entre objetos que compõem um componente.
- Sistema → componentes integrados funcionando juntos.

🧠 **Memorizar:** Unidade = função isolada · Componente/Integração = interface entre objetos · Sistema = tudo integrado.

## 📖 Teste de Regressão

**O que é / Definição para prova:** O Teste de Regressão **consiste em executar um conjunto de casos de teste após uma manutenção do software para testar se uma alteração adicionou novos defeitos**. Diferente dos níveis anteriores, ele **não é realizado durante o processo "normal" de desenvolvimento, apenas nas manutenções** feitas depois que o sistema já existe. Quando se faz uma manutenção, é necessário garantir duas coisas: que **as novas funcionalidades funcionam como esperado** e que **as funcionalidades que já estavam implementadas continuam funcionando como esperado** (ou seja, que a mudança não "quebrou" nada que já funcionava).

🧠 **Memorizar:** Regressão = testar depois de manutenção · Garante: novo funciona + antigo não quebrou.

## 📖 Teste de Release (Teste de Requisitos, Teste de Cenário, Teste de Desempenho)

**O que é / Definição para prova:** O Teste de Release ocorre em um estágio posterior ao desenvolvimento, **geralmente é de caixa preta**, e seu foco é **validar que o software atende o desejado**, verificando **se o software é bom o suficiente para uso externo**. Ele se subdivide em: **Teste de Requisitos**, em que os **casos de teste são derivados dos requisitos**, com o objetivo de **mostrar que cada requisito está como esperado**; **Teste de Cenário**, em que **se testa o software percorrendo um cenário de uso**, permitindo **testar vários requisitos em um mesmo cenário** e **testar combinações de requisitos** (diferente do teste de requisitos, que avalia requisito por requisito isoladamente); e **Teste de Desempenho**, citado no material como parte dos testes de release (avalia questões de performance do sistema pronto para lançamento).

| Teste de Requisitos | Teste de Cenário |
|---|---|
| Um requisito por vez | Vários requisitos juntos, num fluxo de uso real |
| Verifica se o requisito individual está correto | Verifica combinação/interação entre requisitos |

🧠 **Memorizar:** Requisitos = um de cada vez · Cenário = vários juntos, fluxo real de uso · Desempenho = performance do sistema.

## 📖 Teste de Usuário (Alfa, Beta, Aceitação)

**O que é / Definição para prova:** O Teste de Usuário é a categoria de testes conduzidos com/pelos usuários finais antes ou durante o lançamento do software, e se divide em três tipos. **Teste Alfa**: **usuários trabalham com a equipe de desenvolvimento para testar o software no local do desenvolvedor** — é feito em ambiente controlado, com os usuários fisicamente próximos ou junto da equipe técnica. **Teste Beta**: **uma release do software é disponibilizada aos usuários para que eles usem e levantem problemas que identificaram** — diferente do alfa, ocorre no ambiente real do usuário, sem a equipe de desenvolvimento por perto durante o uso. **Teste de Aceitação**: **clientes testam o sistema para decidir se ele está pronto para ser aceito e implantado no ambiente do cliente** — é uma decisão formal de "aceitar ou não" o produto entregue.

**Como funciona / Características:**
- Alfa → no local do desenvolvedor, com equipe presente.
- Beta → no local/ambiente do usuário, sem a equipe por perto, usuários reportam problemas.
- Aceitação → decisão formal do cliente sobre implantar ou não o sistema.

⚠️ **Pegadinha:** Alfa e Beta são frequentemente confundidos: a diferença chave é o **local** (desenvolvedor vs. usuário) e a **presença da equipe** de desenvolvimento durante o teste.

🧠 **Memorizar:** Alfa = na casa do dev · Beta = na casa do usuário · Aceitação = decisão final do cliente.

---

## 📚 Resumão final

- **VV&T**: Verificação (produto certo/requisitos), Validação (certo produto/necessidades do usuário) e Teste (sempre dinâmico, revela defeitos).
- **Estática vs. Dinâmica**: estática não executa o programa; dinâmica executa; teste é sempre dinâmico.
- **Defeito/Erro/Falha**: cadeia causal — defeito no código → erro em execução → falha visível ao usuário.
- **Teste vs. Debugging**: teste revela o defeito; debugging encontra e corrige (frase de Dijkstra sobre testes só mostrarem presença de erros).
- **Categorização**: Tipos (funcionalidade, usabilidade, performance, segurança), Técnicas (branca/preta/cinza) e Níveis (unidade, integração, sistema, aceitação) são eixos independentes e combináveis.
- **Técnicas**: caixa branca conhece a estrutura interna, caixa preta não conhece, caixa cinza combina as duas.
- **Níveis de desenvolvimento**: unidade (função isolada), componente/integração (interface entre objetos), sistema (componentes integrados).
- **Regressão**: feito após manutenção, garante que o novo funciona e o antigo não quebrou.
- **Release**: teste de requisitos (um a um), teste de cenário (combinações), teste de desempenho.
- **Usuário**: alfa (no dev, com equipe), beta (no usuário, sem equipe), aceitação (decisão final do cliente).

## ⚠️ Pontos que podem cair na prova

- Diferença exata entre Verificação e Validação (as duas perguntas-chave "certo" vs. "produto certo") — ver tópico VV&T.
- Classificar se Verificação, Validação e Teste são estáticos, dinâmicos ou ambos — ver tópico VV&T Estáticas vs. Dinâmicas.
- Aplicar a cadeia Defeito → Erro → Falha a um exemplo de código (como nos Exemplos 1 e 2) — ver tópico Termos do Jargão.
- Diferenciar Teste de Debugging e citar a frase de Dijkstra — ver tópico Teste de Software e Debugging.
- Diferenciar Caixa Branca, Caixa Preta e Caixa Cinza — ver tópico Técnicas de Teste.
- Ordem e nomes dos níveis de teste de desenvolvimento (Unidade, Componente/Integração, Sistema) e o que cada um testa — ver tópico Níveis de Teste de Desenvolvimento.
- Quando ocorre o Teste de Regressão e por que (não é parte do desenvolvimento normal) — ver tópico Teste de Regressão.
- Diferença entre Teste de Requisitos e Teste de Cenário — ver tópico Teste de Release.
- Diferença entre Teste Alfa, Beta e de Aceitação — ver tópico Teste de Usuário.

## 📝 Perguntas para revisão

1. Qual a diferença fundamental entre Verificação e Validação? Cite a pergunta-chave associada a cada uma.
2. Verificação, Validação e Teste podem ser estáticos ou dinâmicos? Explique cada caso.
3. Defina Defeito, Erro e Falha e explique a relação de causa-e-efeito entre eles.
4. No exemplo do cálculo de média com divisão fixa por 4, identifique o defeito, o erro e a falha.
5. Qual é o objetivo do Teste de Software segundo o material? O que acontece quando esse objetivo não é atingido?
6. O que significa a frase de Dijkstra "Os testes podem mostrar apenas a presença de erros, e não sua ausência"?
7. O que é Debugging e como ele se relaciona com o Teste de Software?
8. Quais são os três eixos de categorização do teste de software (tipos, técnicas, níveis) e o que cada um representa?
9. Diferencie Teste Caixa Branca, Caixa Preta e Caixa Cinza quanto ao conhecimento da estrutura interna.
10. O que é uma "unidade" no Teste Unitário? Dê um exemplo.
11. Qual a diferença entre Teste de Componente (Integração) e Teste de Sistema?
12. O que é o Teste de Regressão e em que momento do ciclo de vida ele é executado?
13. Diferencie Teste de Requisitos e Teste de Cenário.
14. Diferencie Teste Alfa, Teste Beta e Teste de Aceitação quanto ao local e aos participantes.

### Gabarito

1. Verificação pergunta "Estamos construindo o produto da maneira certa?" e verifica se o software atende aos requisitos funcionais e não funcionais. Validação pergunta "Estamos construindo o produto certo?" e verifica se o software atende às expectativas/necessidades do cliente e partes interessadas, sendo mais geral que a verificação (vai além do especificado).
2. Verificação pode ser estática (revisões, análise estática) ou dinâmica (execução para checar requisitos). Validação é predominantemente dinâmica, mas pode ser estática (ex.: validar protótipo em papel). Teste é sempre dinâmico, pois exige executar o sistema.
3. Defeito (fault) é uma deficiência algorítmica, de dados ou de processo no código (o "bug"), que se ativada pode levar a uma falha. Erro (error) é um estado de execução inconsistente/inesperado, causado pela ativação do defeito em tempo de execução. Falha (failure) é o evento notável, visível externamente, em que o sistema viola suas especificações. A cadeia é: defeito (no código) → erro (estado interno errado durante execução) → falha (comportamento incorreto visível ao usuário).
4. Defeito: o código divide a soma das notas por um número fixo (4) em vez de dividir pelo tamanho real da lista de notas. Erro: durante a execução, com notas 8, 7 e 9 (soma 24), o sistema calcula 24/4 = 6, armazenando esse valor incorreto em memória. Falha: o programa exibe ao usuário "Sua média é: 6.0" quando o valor correto seria 8.0, violando a especificação de forma visível.
5. O objetivo do Teste de Software é revelar a presença de defeitos no software. Quando esse objetivo não é atingido (ou seja, nenhum defeito é encontrado), o teste busca então aumentar a confiança sobre o software, ainda que não prove que ele está livre de defeitos.
6. Significa que passar em todos os testes não garante que o software esteja livre de erros — os testes só conseguem comprovar que os erros testados não ocorreram, mas nunca podem garantir a ausência total de defeitos no sistema.
7. Debugging é o processo de encontrar e corrigir um defeito depois que um teste revelou sua presença. É uma consequência não previsível do teste: o teste aponta que existe um problema, e o debugging localiza e corrige a causa.
8. Tipos de teste: o que se testa em termos de qualidade (funcionalidade, usabilidade, performance, segurança). Técnicas de teste: como o teste é feito em relação ao conhecimento da estrutura interna (caixa branca, preta, cinza). Níveis de teste: em que estágio do ciclo de vida o teste ocorre (unidade, integração, sistema, aceitação). São dimensões independentes que podem ser combinadas.
9. Caixa Branca: o testador conhece a estrutura interna do software e testa a lógica/fluxos internos (visão de programador). Caixa Preta: o testador não conhece a estrutura interna, testando apenas entrada e saída de dados (visão de usuário). Caixa Cinza: combina elementos de caixa branca (conhecimento parcial da estrutura, apenas o relevante) para otimizar a geração de casos de teste de caixa preta (visão de usuário que conhece a implementação).
10. Unidade é a menor parte do software, como uma função. O Teste Unitário testa cada unidade independentemente das demais.
11. Teste de Componente (Integração) testa a interface padrão dos componentes, que são formados por diversos objetos interagindo. Teste de Sistema testa o sistema já com todos os componentes integrados, focando na compatibilidade da interação entre eles.
12. Teste de Regressão consiste em executar um conjunto de casos de teste após uma manutenção do software, para verificar se a alteração introduziu novos defeitos. Ele não ocorre durante o desenvolvimento "normal", apenas em manutenções feitas após o sistema já existir, garantindo que as novas funcionalidades funcionam e que as antigas não foram quebradas.
13. Teste de Requisitos deriva casos de teste diretamente dos requisitos, mostrando que cada requisito individual está como esperado. Teste de Cenário testa o software percorrendo um cenário de uso real, testando vários requisitos e suas combinações em conjunto, e não apenas isoladamente.
14. Teste Alfa: usuários trabalham junto com a equipe de desenvolvimento, testando no local do desenvolvedor. Teste Beta: uma release é disponibilizada aos usuários, que a testam em seu próprio ambiente e reportam problemas encontrados, sem a equipe de desenvolvimento por perto. Teste de Aceitação: os clientes testam o sistema para decidir formalmente se ele está pronto para ser aceito e implantado no ambiente do cliente.
