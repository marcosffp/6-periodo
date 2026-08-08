---
name: resumo
description: Cria um resumo de estudo completo, detalhado e em linguagem simples a partir de um PDF de aula/slide deste repositório, focado em prova teórica (conceitos, definições, comparações, exemplos e possíveis questões). Use quando o usuário pedir para resumir um PDF, material de aula ou slide para estudar, ou invocar /resumo <caminho-do-pdf>.
---

Este repositório é uma base de estudos organizada por matéria (ex: `Medicao_Experimentacao/01_/01-Introducao/`), onde cada aula tem um `main.pdf` (ou nome similar) e um `Resumo.md` irmão que deve conter o material de estudo gerado a partir dele.

Quando esta skill for invocada, o objetivo é produzir um resumo que permita ao aluno estudar **somente pelo `Resumo.md`, sem precisar voltar ao PDF**, para uma prova **predominantemente teórica**.

## 1. Encontrar o PDF alvo

- Se `args` trouxer um caminho (para um `.pdf` ou para uma pasta de aula), use-o.
- Caso contrário, procure por um `.pdf` na pasta atual do contexto da conversa (ex: pasta mencionada pelo usuário com `@pasta/`) ou pergunte qual PDF resumir se houver mais de um candidato ambíguo.
- O arquivo de saída é sempre um `Resumo.md` na mesma pasta do PDF. Se já existir (mesmo vazio), sobrescreva-o; não crie um segundo arquivo.

## 2. Ler o PDF inteiro antes de escrever qualquer coisa

- Use a ferramenta de leitura para processar **todas as páginas** do PDF, não apenas as primeiras. Para PDFs grandes (mais de ~20 páginas), leia em blocos usando o parâmetro de páginas até cobrir o documento inteiro.
- Durante a leitura, anote mentalmente: títulos/subtítulos, conceitos, definições, exemplos, tabelas, listas, classificações, comparações, observações, exceções, fórmulas, diagramas/imagens explicativas e qualquer termo que pareça "cobrável" em prova.
- Não invente informação que não esteja no PDF. Se usar conhecimento externo apenas para facilitar uma explicação, marque claramente como complemento (ex: "💡 Complemento (fora do PDF):").
- Não comece a escrever o resumo antes de ter lido o documento inteiro.

## 3. Estrutura do resumo (escreva em português, direto no `Resumo.md`)

O objetivo é um equilíbrio: **estruturado e fácil de escanear/memorizar** (por isso os tópicos têm subtítulos), mas **sem repetir o mesmo fato em vários lugares do documento**. A causa de resumos gigantescos não é ter subtítulos — é dizer a mesma coisa três vezes (uma no corpo do tópico, outra num "o que memorizar" que só reformula a frase de cima, outra de novo lá no fechamento do documento). **Regra de ouro: cada fato tem exatamente um lugar onde é explicado por extenso.** As demais aparições dele (memorização rápida, fechamento) são só *ponteiros* curtos para esse lugar, nunca uma nova explicação.

Organize por assunto, seguindo a ordem lógica do PDF. Para cada assunto:

```
## 📖 Nome do assunto

**O que é / Definição para prova:** parágrafo único que ensina do zero (analogia quando ajudar) e já embute a definição formal citável (em **negrito**, quase literal quando o PDF tiver uma frase-definição). Termos técnicos são explicados inline, na primeira aparição.

**Como funciona / Características:** lista, só quando houver algo real a decorar (etapas de um processo, itens de uma classificação, requisitos). Pule esta parte se o parágrafo acima já cobre tudo.

**Exemplo:** o exemplo do PDF (nunca inventado) + por que ele ilustra o conceito, em 1-2 frases. Pule se o PDF não trouxer exemplo.

⚠️ **Pegadinha:** só se houver confusão comum com conceito parecido. Omita se não houver.

🧠 **Memorizar:** 2-4 itens ultracurtos (palavras/expressões-chave, não frases completas) — são ganchos de memória, não um resumo do parágrafo. Se um item aqui precisa de mais de 6-8 palavras para fazer sentido, ele pertence ao parágrafo acima, não aqui.
```

Nem todo assunto precisa do bloco inteiro — uma definição simples ou um dado histórico pontual pode ser só 1-2 frases corridas, sem sub-seções.

Para **conceitos que podem ser confundidos entre si**, monte uma tabela comparativa **no lugar de** dois parágrafos separados repetindo as mesmas informações de formas diferentes:

| Conceito A | Conceito B |
|---|---|
| O que é | O que é |
| Diferença principal | Diferença principal |
| Exemplo | Exemplo |

Corte frases que apenas reafirmem, com outras palavras, algo já dito antes **no mesmo tópico** — isso é diferente de ter profundidade (analogia + definição + exemplo são complementares, não redundantes entre si).

## 4. Fechamento do documento (uma vez só, no final — não repita o conteúdo dos tópicos)

Ao final do `Resumo.md`, inclua, nesta ordem:

- **📚 Resumão final** — 1 bullet por assunto, uma frase cada, amarrando a matéria toda (é um mapa mental de revisão relâmpago, não uma segunda explicação).
- **⚠️ Pontos que podem cair na prova** — lista curta dos assuntos/detalhes com maior chance de cair, apontando onde estão (não reexplicando).
- **📝 Perguntas para revisão + Gabarito** — uma lista de perguntas teóricas plausíveis cobrindo os assuntos do PDF (1-2 por tópico), seguida de uma seção **separada** "Gabarito" com respostas objetivas e completas. Esta é a única lista de perguntas do documento — não crie also uma seção de "possíveis questões" por tópico, para não duplicar o mesmo par pergunta/resposta duas vezes no arquivo.

Não crie uma seção extra de "Definições que preciso saber" nem "Comparações importantes" separada do corpo — as definições e tabelas comparativas já vivem nos tópicos (seção 3); repeti-las por extenso de novo no fechamento é a principal causa de resumos inchados.

## 5. Autoverificação (fazer antes de finalizar, sem que o usuário precise pedir)

Depois de escrever o rascunho completo, releia o PDF original mentalmente e verifique, nesta ordem:

1. **Completude:** *"Se o aluno estudar só este `Resumo.md` e nunca abrir o PDF, ele teria acesso a todos os conceitos, definições, características, exemplos, diferenças e informações importantes cobráveis, entendendo-os de verdade (não só decorando um rótulo)?"* Se não, complete — adicione a explicação/exemplo/analogia que falta no lugar certo (o corpo do tópico), não encolha conteúdo para "parecer enxuto".
2. **Redundância entre seções:** o mesmo fato aparece explicado por extenso em mais de um lugar (ex.: no parágrafo do tópico E de novo como parágrafo no fechamento)? Se sim, corte a repetição, mantendo a explicação completa só no tópico e deixando o fechamento como ponteiro curto.
3. **Legibilidade:** dentro de um mesmo tópico, os parágrafos e listas se leem com fluidez, sem frases que só reformulam a frase anterior?

## 6. Tom e formatação

Escreva como um professor particular explicando para alguém vendo o assunto pela primeira vez: frases claras, exemplos, analogias quando ajudarem, listas, tabelas. Simplificar a linguagem **não** significa simplificar o conteúdo — a definição formal cobrável em prova sempre precisa estar presente, além da explicação simples.

Use **negrito** para conceitos-chave, ⚠️ para alertas/pegadinhas, 🧠 para o que precisa ser memorizado, 📌/📖 para assuntos e conceitos importantes.

## 7. Ao terminar

Salve o `Resumo.md` e informe ao usuário, em 1-2 frases, quantos assuntos/tópicos foram cobertos e o caminho do arquivo gerado.
