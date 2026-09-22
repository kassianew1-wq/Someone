# TI e Fluência de Dados

Desempenho próximo da meta. Manter o ritmo.

## Como ensinar

- Todo termo técnico vem definido em uma frase, na primeira vez que aparece.
- Analogia do contexto fiscal sempre que possível.
- Em SQL e modelagem, explicar o raciocínio da consulta ou do modelo antes de
  mostrar o código.
- Nomes de algoritmo, sigla e norma técnica seguem o protocolo de incerteza
  (seção 2). Sigla errada com explicação certa é o pior resultado possível,
  porque leva a marcar a alternativa errada sabendo o conceito.

## Contexto histórico

A LGPD (Lei 13.709/2018) nasceu no rastro do regulamento europeu de proteção de
dados, que entrou em vigor em 2018. O Brasil estava entre os últimos países
relevantes sem lei geral sobre o tema, o que era um problema comercial e
diplomático antes de ser um problema jurídico: sem lei equivalente, o fluxo
internacional de dados fica restrito. A autoridade nacional só se estruturou
depois da lei.

Em segurança da informação, a família ISO 27000 tem raiz em norma britânica dos
anos 1990. Em banco de dados, o modelo relacional foi proposto por Codd em 1970 e
continua sendo a base dos sistemas fiscais brasileiros, o que explica por que
tanto de fiscalização ainda se resolve com junção de tabelas.

## Comparação internacional

O regulamento europeu é mais rígido que a LGPD em pontos específicos, entre eles
o prazo de notificação de incidente, que lá é fixado em horas e aqui foi
redigido como prazo razoável. Os Estados Unidos não têm lei federal geral
equivalente: a regulação é setorial. A União Europeia avançou primeiro também na
regulação de inteligência artificial, o que tende a servir de modelo para a
discussão brasileira.

Geopolítica de dados: a disputa tecnológica entre Estados Unidos e China passa
por dados, semicondutores e infraestrutura de rede, e se manifesta em restrições
a fornecedores em redes de telecomunicação. O Brasil figura de forma recorrente
entre os países mais atingidos por ataques de sequestro de dados, inclusive
contra órgãos públicos, o que dá concretude ao conteúdo de continuidade de
negócio e resposta a incidente.

## Bizus

**Banco de dados relacional.** Pense no cadastro de contribuintes: cada linha é
um contribuinte, cada coluna é um atributo. A chave primária é o identificador
que não se repete e não fica vazio.

**Chave primária e chave estrangeira.** A chave primária identifica o registro na
própria tabela. A chave estrangeira é a referência a outra tabela: o
identificador do contribuinte dentro da tabela de lançamentos aponta para o
cadastro, não vive sozinho. Chave estrangeira é ponteiro; chave primária é
identidade.

**JOIN.** Com uma tabela de contribuintes e outra de notas fiscais, o JOIN é o
ato de colocar os dois arquivos lado a lado para ver quem emitiu o quê. INNER
JOIN traz só quem aparece nos dois. LEFT JOIN traz todos do lado esquerdo, com ou
sem correspondência, e é o que revela o contribuinte cadastrado que não emitiu
nada.

**Criptografia simétrica e assimétrica.** Simétrica usa uma única chave: o mesmo
segredo fecha e abre. É rápida, mas exige um jeito seguro de combinar a chave.
Assimétrica separa em duas: publica-se o cadeado, guarda-se a chave. É o que
sustenta assinatura digital e certificação nos documentos fiscais eletrônicos.

**Supervisionado e não supervisionado.** No aprendizado supervisionado o modelo
treina com exemplos já rotulados e aprende a reproduzir o rótulo; o KNN
(K-Nearest Neighbors, ou K vizinhos mais próximos) classifica olhando os
exemplos rotulados mais parecidos. No não supervisionado não há rótulo e o modelo
agrupa sozinho por semelhança; o K-Means separa os dados em K grupos sem que
ninguém diga o que cada grupo significa. A distinção prática para fiscalização:
supervisionado reconhece o tipo de fraude que já se conhece; não supervisionado
aponta o comportamento atípico que ainda não tem nome.

**Data Warehouse e Data Lake.** O warehouse exige estrutura na entrada: define-se
o esquema antes de gravar. O lake aceita o dado como vem e a estrutura é aplicada
na leitura. Um é arquivo organizado; o outro é depósito com etiqueta posterior.
