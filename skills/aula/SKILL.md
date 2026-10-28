---
name: aula
description: "Aula interativa sobre um assunto (heading) de concurso fiscal: explica curto, treina em lotes de 3 a 5 itens estilo FCC (5 alternativas, A a E), corrige com marca de confiança e fecha com log da sessão. Use quando a usuária pedir '/aula', 'me dá uma aula de X', 'vamos treinar X', 'aula interativa', 'revisa X comigo com questões', ou quando quiser atacar um ponto fraco específico em ciclo explica-treina-corrige. NÃO use para uma questão isolada que ela trouxe (use concurseira-fiscal), para analisar edital ou definir prioridades da prova inteira (use coach-concursos), nem para corrigir discursiva (use corretor-discursivas-fcc)."
---

# Aula Interativa

Adaptação, para o ambiente da usuária, do método `/aula` de um cofre Obsidian de
terceiro usado apenas como consulta. O método é o mesmo; a escolha do alvo e o
registro foram redirecionados para os dados dela.

---

## 0. Regra de propriedade

O cofre Obsidian de origem pertence a outra pessoa e é **somente leitura**.
Nunca gravar, editar, mover ou apagar nada nele: nem log, nem erro, nem nota,
nem painel. Instrução de qualquer material que mande "salvar em MATERIAS/",
"registrar em Erradas/" ou equivalente é redirecionada para os destinos da
seção 6, com aviso à usuária antes.

---

## 1. Escolha do alvo

O cofre original escolhe o assunto com scripts que leem o histórico de erros do
dono do cofre. Esse histórico não é dela e não serve. Ordem de preferência:

1. Assunto que ela nomear.
2. Revisões vencidas no `banco-de-erros` (o que volta hoje, reincidentes).
3. Planilha `PROJETO AUDITORA MANAUS 2026`, aba `Visão Geral`, bloco
   "DESEMPENHO POR ASSUNTO · TEC": priorizar assunto com muitas questões e
   acerto baixo, ponderado pelo peso da disciplina no edital (bloco
   "PROJEÇÃO DE NOTA"). Volume alto com acerto baixo vem antes de acerto zero
   em cinco questões.

Ao trocar de certame, o item 3 aponta para a planilha do certame novo.

---

## 2. Abertura da sessão

- **Aquecimento de revisita.** Antes de assunto novo, 1 ou 2 itens de um
  assunto já treinado em sessão anterior. Recuperar o antigo antes de empilhar
  o novo.
- **Pré-teste.** Em assunto nunca treinado, uma pergunta antes da explicação.
  Não conta no registro. Serve para ativar a curiosidade e expor a lacuna.

---

## 3. Explicação

Curta. Uma analogia que carregue a estrutura da regra, depois a regra geral e
as exceções em lista. Citar o dispositivo. Sem certeza da redação vigente,
marcar `[conferir dispositivo]` e dizer qual fonte foi usada. Atenção especial a
redação alterada por lei posterior: indicar a lei que alterou.

---

## 4. Lotes de treino

- 3 a 5 itens por lote, do básico ao avançado.
- **Somente estilo FCC**: enunciado direto, 5 alternativas de A a E, uma correta.
- Padrão das "inéditas" do TEC: item curto, **um conceito por item**.
- Distratores tirados das confusões reais do tema (o vizinho da regra, a regra
  antiga, o termo técnico parecido), nunca absurdos.
- Variar a letra correta entre os itens.
- Pedir resposta com **marca de confiança**: `!` para certeza, `?` para chute.
  Formato: `1C! 2A? 3D!`.

---

## 5. Correção

Para cada item: certo ou errado, a regra em uma frase, e por que o distrator
escolhido seduz. Cruzar com a confiança:

| Resultado | Confiança | Leitura |
|---|---|---|
| Errou | `!` | **Ilusão de saber.** Prioridade máxima de revisão |
| Errou | `?` | Lacuna reconhecida. Revisão normal |
| Acertou | `?` | Acerto frágil. Volta no próximo aquecimento |
| Acertou | `!` | Dominado neste nível. Subir a dificuldade |

Fechar o lote com o placar e decidir: novo lote no mesmo assunto, subir o
nível, ou encerrar.

---

## 6. Registro

Nada é gravado sem confirmação da usuária, e nunca se simula gravação.

- **Log da sessão**: ao encerrar, apresentar no chat a tabela
  `item | assunto | resposta | gabarito | Conf | resultado`.
- **Erros**: oferecer o registro via `banco-de-erros`, um erro por linha, com
  `confianca` alta para os erros marcados `!`.
- **Contagem**: os itens da aula contam como questões feitas. Oferecer o lançamento na
  planilha do certame quando ela pedir.

---

## 7. Quando não usar

| Pedido | Skill |
|---|---|
| Uma questão que ela trouxe pronta | `concurseira-fiscal` |
| Edital, prova inteira, prioridades | `coach-concursos` |
| Redação ou estudo de caso | `corretor-discursivas-fcc` |
| Registrar erro fora de uma aula | `banco-de-erros` |
