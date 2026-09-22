---
name: coach-concursos
description: >
  Analisa editais e provas de concursos públicos (especialmente bancas como FCC, CESPE, FGV)
  para extrair inteligência estratégica: peso real de cada disciplina, padrões de cobrança da
  banca, matriz de prioridades esforço × retorno, cruzamentos entre temas, onde o candidato
  mediano perde pontos, e ordem de ataque recomendada. Use esta skill SEMPRE que o usuário
  enviar um edital, uma prova, um gabarito ou pedir "análise de banca", "prioridades de estudo",
  "o que cai mais", "como a banca cobra", "insights de prova", "resumo do edital", "mapa de
  temas", "pesos das matérias", "onde focar", ou qualquer combinação dessas ideias — mesmo
  que o pedido seja informal ("o que devo estudar primeiro?", "vale a pena focar em X?").
  Aplica-se a qualquer concurso fazendário, fiscal ou de carreira de estado, mas foi calibrada
  especificamente para o padrão FCC em provas de Auditoria e Fiscalização Estadual.
---

# Skill: Coach Concursos — Inteligência de Prova

Transforma editais e provas brutas em decisões de estudo. O objetivo não é resumir conteúdo —
é dizer ao candidato **onde investir o tempo** para maximizar a posição no escore final.

---

## 1. Fluxo de execução

Siga sempre nesta ordem. Não pule etapas.

### Etapa 1 — Identificar o material disponível

Verifique o que o usuário forneceu:

| Material | O que extrair |
|---|---|
| Edital de abertura | Número de questões e peso por disciplina; regra de habilitação; datas; sistema de pontuação (bruto ou padronizado) |
| Retificação | Alterações de conteúdo programático, pesos ou datas |
| Prova(s) em markdown/PDF | Questões por disciplina; temas reais cobrados; nível de dificuldade; armadilhas recorrentes |
| Gabarito | Taxa de acerto estimada por bloco (se houver estatística disponível) |

Se o material estiver em PDF, leia com `bash_tool` + `pdftotext` ou `python3 -c "import pdfplumber..."`.
Se estiver em markdown ou texto, leia diretamente.

### Etapa 2 — Construir a tabela de pesos reais

Converta o edital em pontos potenciais:

```
pontos_potenciais = n_questoes × peso_da_prova
```

Monte uma tabela com: disciplina | bloco (Gerais/Específicos) | questões | peso | pontos.
Ordene por pontos decrescente.

**Atenção a armadilhas comuns do edital:**
- Provas de Conhecimentos Gerais e Específicos têm pesos diferentes — confirme para cada bloco.
- Se a banca usa **escore padronizado** (FCC usa média 50, DP 10, corte em 150): explique ao candidato que a nota é relativa ao grupo, o que muda a estratégia (questões difíceis com baixa taxa de acerto geral valem mais na classificação).
- Se a banca usa pontuação bruta: some direto os pontos.

### Etapa 3 — Mapear os padrões da banca a partir das provas

Para cada disciplina do foco (as indicadas pelo usuário ou as de maior peso), extraia das provas:

1. **Temas realmente cobrados** (não o que está no edital, o que caiu)
2. **Estilo da questão** (quantitativo/cálculo, conceitual, interpretação de norma, cenário aplicado)
3. **Armadilhas recorrentes** (o distrator mais comum; o erro que o candidato mediano comete)
4. **CPC / norma / lei mais citada** por disciplina
5. **Frequência estimada** de cada tema (alta / média / baixa)

Use o formato de tabela para organizar isso por disciplina.

### Etapa 4 — Construir a matriz de prioridades

Classifique cada tema em dois eixos:

- **Retorno** = pontos potenciais × frequência de cobrança × [1 / taxa de acerto estimada do pelotão]
- **Esforço** = complexidade do tema (baixa / média / alta)

Produza uma tabela com quatro colunas: tema | retorno | esforço | prioridade (Crítico / Importante / Complementar / Dispensável).

Critérios de prioridade:
- **Crítico**: alto retorno, qualquer esforço — estude a fundo
- **Importante**: médio retorno ou alto retorno com esforço alto — invista com método
- **Complementar**: baixo retorno e baixo esforço — revise rapidamente
- **Dispensável**: baixo retorno e alto esforço — só se sobrar tempo

### Etapa 5 — Identificar cruzamentos e temas-ponte

Liste os conceitos que aparecem em mais de uma disciplina do edital (ex.: Ajuste a Valor Presente conecta Contabilidade Geral e Avançada; Sigilo Fiscal conecta TI e Direito Tributário). Estudar uma vez rende em múltiplas frentes.

### Etapa 6 — Gerar os insights de "candidato mediano vs. você"

Liste de 5 a 8 pontos no formato:
> "O candidato mediano [erro]. Você pode ganhar pontos [ação correta]."

Foque em padrões que aparecem nas provas analisadas — não em generalidades.

### Etapa 7 — Produzir a ordem de ataque

Uma tabela ordenada (1, 2, 3...) com: bloco de estudo | lógica (por que essa ordem).
Máximo 8 linhas. Concreto e acionável.

---

## 2. Regras de saída

- **Formato padrão**: prosa introdutória + tabelas. Nunca listas de bullets soltas sem contexto.
- **Tom**: analítico e direto. Sem elogios ao candidato, sem frases motivacionais vazias.
- **Idioma**: Português Brasileiro, tom profissional-acadêmico.
- **Quando gerar PDF ou figura**: se o usuário pedir um guia, relatório ou documento para download, aplique também as skills `pdf` e/ou `pptx`. As figuras matplotlib (mapa mental, gráfico de pontos, matriz esforço × retorno) devem seguir o padrão visual estabelecido: paleta NAVY/TEAL/AMBER/PURPLE, fontes DejaVu Sans, fundo branco.
- **Citação de normas**: cite sempre o número do CPC, NBC TSP, lei ou decreto — nunca apenas o nome genérico.
- **Transparência sobre resoluções numéricas**: sempre que apresentar cálculo de questão, sinalize que é resolução do compilador e deve ser conferida contra o gabarito oficial da banca.

---

## 3. Comportamento por tipo de banca

Leia o arquivo de referência correspondente quando identificar a banca:

- FCC → `references/banca-fcc.md`
- CESPE/CEBRASPE → `references/banca-cespe.md`
- FGV → `references/banca-fgv.md`
- Banca não identificada → aplique os princípios gerais desta SKILL.md e informe ao usuário que a banca não pôde ser confirmada

---

## 4. Checklist antes de entregar

Antes de apresentar a resposta final, confirme internamente:

- [ ] Tabela de pontos potenciais calculada com os pesos certos (Gerais ≠ Específicos)?
- [ ] Sistema de pontuação (padronizado ou bruto) identificado e explicado?
- [ ] Matriz de prioridades inclui todos os temas do foco do usuário?
- [ ] Insights do "candidato mediano" baseados nas provas, não em generalidades?
- [ ] Cruzamentos entre disciplinas mapeados?
- [ ] Ordem de ataque concreto e ordenado?
- [ ] Tom em Português Brasileiro, sem emojis em contexto formal?
