# Skills — revisão de 2026-09-22

Cinco skills, revisadas a partir de auditoria de conteúdo, consistência interna e
arquitetura. Todas passam no validador oficial do `skill-creator`.

## O conjunto

| Skill | Função | Quando NÃO usar |
|---|---|---|
| `coach-concursos` | Estratégia macro: edital, prova inteira, prioridades | Questão isolada, discursiva |
| `concurseira-fiscal` | Ensino: uma questão, uma dúvida, um erro | Edital, discursiva, IR real |
| `corretor-discursivas-fcc` | Nota e devolutiva de discursiva no padrão FCC | Objetiva, dúvida de conteúdo |
| `contador-ir` | Tributação real do usuário | Questão de prova sobre IR |
| `mestrado` | Produção acadêmica, ABNT | Conteúdo de concurso |
| `banco-de-erros` | Registro de erro e revisão espaçada | Resolver ou explicar a questão |

Cada skill tem seção "Quando não usar" com a tabela de encaminhamento, para que a
sobreposição de gatilhos deixe de ser resolvida por acaso.

## Correções de conteúdo

**Regra de pontuação do Cebraspe.** O arquivo afirmava que o item errado descontava
metade do valor do certo, e declarava dois limiares diferentes de chute racional
(dois terços e setenta por cento). A regra padrão é anulação integral, e o ponto
de equilíbrio derivado dela é cinquenta por cento. O arquivo agora traz a fórmula
do valor esperado, a derivação e a ressalva de que a proporção é parâmetro do
edital.

**DASP.** A skill trazia o órgão em duas datas diferentes, em dois pontos do mesmo
arquivo. O bloco foi removido. A regra de contexto histórico permanece e foi
reforçada, agora com instrução explícita de descrever o período em vez de cravar
ano sem certeza.

**KNN e K-Means.** Constavam como "KRN" e "KDH", siglas inexistentes, com a
explicação conceitual correta ancorada no rótulo errado. Corrigidas.

**DRE gerencial.** O mnemônico pulava a linha de custos e despesas variáveis,
justamente a que define a margem de contribuição, e gastava duas letras numa
única linha. Substituído pela estrutura explicada na ordem.

**PDCA.** O mnemônico continha uma palavra inexistente e associações sem relação
com o que representavam. Substituído pela lógica do ciclo.

**Nota de corte da FCC.** Estava descrita como propriedade da banca. É parâmetro
do edital específico e foi movida para `certame-atual.md`.

**Tabelas do imposto de renda.** Estavam congeladas no ano-base 2024 e sendo
apresentadas com postura de precisão. Foram movidas para
`contador-ir/references/tabelas-vigentes.md`, marcadas como VENCIDO, e a skill
ganhou uma regra zero que a obriga a conferir a vigência antes de citar qualquer
número.

**Normas ABNT.** Eram invocadas como "vigentes" sem indicação de edição, e as
prescrições numéricas de citação longa vinham da edição de 2002. A skill agora
exige confirmar a edição antes de prescrever forma.

## Correções estruturais

**Protocolo de incerteza.** A `concurseira-fiscal` mandava citar dispositivo doze
vezes, mencionava súmula e CARF nove vezes, e não tinha nenhuma instrução sobre o
que fazer sem certeza. Agora tem, e a marca `[conferir dispositivo]` foi estendida
às outras skills.

**Densidade de diretivas.** A `concurseira-fiscal` tinha 116 imperativos em 537
linhas, sem ordem de precedência. Foi separada em contrato (sete regras no topo,
que vencem qualquer colisão) e repertório (material por matéria em `references/`,
lido sob demanda).

**Extração do corretor.** A correção de discursiva ocupava um quarto da skill de
ensino e era carregada em toda questão objetiva. Virou skill própria.

**Emojis.** Removidos de todos os arquivos. A skill exigia marcadores emoji em um
ponto e os proibia em outro. Os marcadores viraram rótulos em texto.

**Ferramenta visual.** A instrução mandava gerar "widget interativo", que não é o
nome de nenhuma ferramenta disponível. Substituída por Artifact HTML, SVG inline e
matplotlib, nessa ordem, com critério de proporcionalidade.

**Dados mutáveis.** Percentuais de desempenho e parâmetros do certame saíram do
corpo das skills para `certame-atual.md` e `perfil-desempenho.md`, com data de
atualização e checklist de troca.

## Lacunas cobertas

- Transcrição obrigatória antes de resolver questão recebida como foto ou print.
  Sem ela, a regra de transcrição literal era violada na origem.
- Protocolo de divergência de gabarito: reexaminar a própria resolução primeiro,
  depois expor as duas leituras, só então avaliar recurso.
- Critério de extensão da resposta, com núcleo obrigatório e camadas graduais.

## Fonte única

Padrão de banca vive apenas em `coach-concursos/references/`. Nenhuma outra skill
duplica esse conteúdo.

## Instalação

Estes arquivos são a versão corrigida. Para passarem a valer, precisam substituir
as skills na conta (as cópias locais em `~/.claude/skills/synced/` são espelho do
que está na conta e são sobrescritas pela sincronização).

## Pendências

Marcadas no próprio texto com `[conferir]`, `[conferir vigência]`,
`[conferir dispositivo]`, `[conferir no edital]` e `[conferir edição da NBR]`.
As mais urgentes:

- Tabelas de imposto de renda vigentes.
- Numeração dos itens do edital do certame em curso.
- Edição vigente das NBRs de citação e referências.
- Parâmetros de pessoa jurídica em `tabelas-vigentes.md`, nunca conferidos.

## banco-de-erros

Skill nova, que fecha o ciclo. Um erro por linha em planilha do Google, com
fallback para arquivo local quando não houver ferramenta de planilha na sessão.

O núcleo é a taxonomia de seis tipos de erro, porque o tratamento depende dela:
não sabia, confundiu, esqueceu, desatenção, interpretação, cálculo. A distinção
que mais muda resultado é entre "não sabia" e "desatenção": a primeira pede horas
de estudo, a segunda pede protocolo de leitura. Tratar desatenção como lacuna de
conteúdo é o modo mais comum de estudar muito e não subir o percentual.

Revisão espaçada em D+1, D+7 e D+30, com exceção para desatenção, que recebe
intervalo único em D+7 por não ser problema de memória. Três reincidências no
mesmo tema mudam o status e sinalizam que a classificação do erro provavelmente
está errada.

Integrações: `concurseira-fiscal` oferece o registro depois de corrigir questão
errada; `corretor-discursivas-fcc` converte os itens de prioridade de melhoria em
registro; `coach-concursos` cruza o banco com o peso do edital para transformar a
matriz de prioridades de estimada em medida; e `perfil-desempenho.md` passa a ser
derivado do banco em vez de preenchido à mão.

Regra firme: nunca grava sem confirmação, e nunca simula gravação quando não há
ferramenta disponível.

## Próximo passo sugerido

`norma-vigente`, que resolve de forma sistemática a classe de problema que
apareceu em duas skills por mecanismos diferentes: conhecimento normativo
congelado apresentado com confiança.
