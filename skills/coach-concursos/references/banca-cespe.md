# Banca CESPE / CEBRASPE — Padrões e Comportamentos

## Identificação
CEBRASPE, sucessor do CESPE/UnB. Confirmar no cabeçalho da prova ou no edital.

## Sistema de pontuação

**Certo/Errado com anulação.** Cada item vale um ponto. Item certo soma um. Item
errado **subtrai um ponto inteiro**, anulando um acerto. Item em branco vale
zero.

```
nota = (acertos - erros) x valor do item
```

`[conferir no edital]` A proporção do desconto é fixada em edital. A regra acima,
de anulação integral, é a padrão da banca, mas certames específicos já adotaram
outras proporções. Conferir antes de orientar estratégia.

## Limiar racional de chute

O valor esperado de marcar um item é `p - (1-p) x penalidade`, onde `p` é a
probabilidade de acerto. Igualando a zero, o ponto de equilíbrio é
`p = penalidade / (1 + penalidade)`.

| Penalidade por erro | Chutar compensa a partir de |
|---|---|
| 1 ponto inteiro (regra padrão) | **p = 50%** |
| meio ponto | p = 33% |

**Com a regra padrão, o limiar é 50%.** Acima disso, marcar tem valor esperado
positivo e deixar em branco entrega ponto. Abaixo, deixar em branco.

Este é o erro estratégico mais caro nesta banca em qualquer direção: um limiar
alto demais faz o candidato entregar dezenas de itens com valor esperado
positivo; um limiar baixo demais o faz perder pontos em chute cego. O número sai
da penalidade do edital, nunca de intuição.

Ressalva prática: a estimativa de `p` é subjetiva e tende ao otimismo. Quem
sistematicamente superestima a própria convicção deve trabalhar com margem acima
do limiar teórico, mas essa margem é ajuste pessoal calibrado no simulado, não
regra da banca.

## Traços estilísticos

| Traço | Descrição |
|---|---|
| Horizontal | Cobre boa parte do edital; evita concentrar em poucos temas |
| Assertiva direta | Cada item é uma afirmação a ser julgada certa ou errada |
| Pegadinha léxica | A troca de um advérbio ou conectivo inverte o sentido |
| Literalidade normativa | Reproduz o texto legal quase literalmente, com uma palavra alterada |
| Profundidade em matéria legal | Tributário, Constitucional e Administrativo com alto nível de detalhe normativo |

## Armadilhas recorrentes

- Advérbios de exclusividade: somente, apenas, exclusivamente. Tornam a assertiva
  falsa na maioria dos casos, mas **não automaticamente** — há regras que de fato
  são exclusivas. Verificar antes de marcar.
- Inversão entre regra e exceção.
- Confusão entre prazos e entre os marcos de contagem, especialmente em decadência
  e prescrição tributárias, em que a regra geral e a do lançamento por homologação
  contam de eventos distintos.
- Em Contabilidade, assertivas sobre o **momento** do reconhecimento, antecipado
  ou postergado em relação à norma.

## Estratégia de resposta

Marcar conforme o limiar derivado da penalidade do edital. Havendo dúvida entre
duas leituras e não existindo base firme na norma, a assertiva costuma cobrar a
literalidade: a leitura mais próxima do texto legal tende a ser a esperada.
