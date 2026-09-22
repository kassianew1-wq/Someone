# Banca FCC — Padrões e Comportamentos

## Identificação
Fundação Carlos Chagas. Confirmar presença de "FCC", "concursosfcc.com.br" ou "Fundação Carlos Chagas" no cabeçalho da prova ou no edital.

## Sistema de pontuação
**Escore padronizado**: média 50 e desvio padrão 10 são a convenção do método.
Nota de cada candidato:
`NP = ((acertos - média_do_grupo) / DP_do_grupo) * 10 + 50`
Multiplicada pelo peso da prova.

`[conferir no edital]` **A nota de corte de habilitação é parâmetro do edital
específico, não propriedade da banca.** Varia entre certames. Nunca presumir a
partir de concurso anterior: ler do edital em mãos.

**Implicação estratégica**: a nota é relativa ao grupo. Questões difíceis onde a maioria erra valem mais na posição do que questões fáceis. Temas de alta dificuldade e peso 2 são o maior diferencial de classificação.

## Traços estilísticos da banca

| Traço | Descrição |
|---|---|
| **Vertical** | Repete conjunto restrito de temas com profundidade; não varre todo o edital |
| **Quantitativa (contábil)** | Questão entrega um cenário; candidato monta a contabilização ou calcula um saldo |
| **Armadilha numérica** | O distrator correto é o resultado do erro mais comum (ex.: usar taxa contratual no lugar da efetiva) |
| **Enunciado direto** | O texto raramente engana; o erro nasce do cálculo ou do conceito |
| **Dados conceitual-aplicado** | Em TI/Fluência de Dados: descreve um problema real e pede a técnica correta |
| **Tendência a norma explícita** | Cita o CPC, a NBC TSP, o artigo do CTN — o candidato precisa conhecer o número |

## Armadilhas recorrentes por disciplina

### Contabilidade Avançada
- Taxa **contratual** no lugar da **efetiva** em instrumentos financeiros e empréstimos
- Custo inicial de propriedade para investimento sem AVP das parcelas a prazo
- Depreciar direito de uso pelo **prazo do contrato** quando há opção de compra provável (correto: vida útil)
- Tratar dividendo **proposto** como distribuído na equivalência patrimonial
- Lançar subvenção diretamente no PL (correto: transitar pelo resultado)
- Reverter impairment de goodwill (vedado)
- Variação de VJORA levada ao resultado (correto: ORA / patrimônio)

### Contabilidade Geral
- Incluir ICMS recuperável no custo do estoque
- Comparar venda de imobilizado com o custo histórico (correto: valor contábil líquido)
- Provisionar passivo contingente possível (correto: apenas divulgar)

### Custos
- Incluir despesa variável no custo de produção
- Escolher mix de produção pela maior margem por unidade quando há fator limitante (correto: margem por unidade do recurso escasso)
- Ratear por quantidade física quando o critério é valor de mercado (produção conjunta)

### Fluência de Dados / TI
- Confundir Data Warehouse (schema-on-write) com Data Lake (schema-on-read)
- Chamar de drill-down o que é roll-up (e vice-versa)
- Tratar pseudonimização como anonimização (dado pseudonimizado ainda é dado pessoal)
- Atribuir sobredispersão a Poisson (correto: binomial negativa)

## Provas espelho para concursos fazendários

`[conferir]` Lista de referência, sujeita a envelhecer. Revisar a cada ciclo.
Provas mais próximas do desenho da FCC em fazendas estaduais:
- SEFAZ-GO 2026 (Auditor-Fiscal)
- SEFAZ-SP/AFRE 2026 (Auditor Fiscal da Receita Estadual)
- SEFAZ-PI 2025 (Auditor Fiscal)
- SEFAZ-MT/FTE 2026 (Fiscal de Tributos Estaduais)

## CPCs e normas mais cobradas
CPC 48 (instrumentos financeiros), CPC 06 (arrendamento), CPC 18/36 (participações), CPC 28 (propriedade para investimento), CPC 25 (provisões), CPC 03 (DFC), CPC 09 (DVA), CPC 16 (estoques), CPC 27 (imobilizado), NBC TSP 34 (custos públicos), CTN arts. 198-199 (sigilo fiscal).
