---
title: Acórdãos do TCU
when: "Em qualquer pergunta sobre o que o TCU decidiu ou entende, e antes de citar um acórdão."
---

# Acórdãos do TCU

A base traz a jurisprudência do TCU sobre licitações e contratos no recorte do **Informativo de Licitações e
Contratos**. Não é o acervo inteiro do Tribunal: um acórdão fora do recorte não aparece, e isso não quer dizer que
ele não exista no TCU.

## Qual ferramenta

| Pedido | Ferramenta |
|---|---|
| Tema em linguagem natural ("o que o TCU entende sobre…") | `acordaos_buscar`, a padrão |
| Expressão ou sigla literal ("seguro-garantia", "art. 48 da 14.133") | `acordaos_grep` |
| Filtrar por relator, ano, colegiado ou número; contar; saber se existe | `acordaos_navegar` |
| Ler um acórdão já identificado (número, ano e colegiado, ou o id de uma busca) | `acordaos_ler` |

## A regra da peça: quem decidiu o quê

Um acórdão tem peças diferentes, e confundi-las é erro grave.

- **ACORDAO** é a decisão do colegiado. É ela que diz o que o TCU decidiu.
- **VOTO** é a fundamentação e a proposta do relator. Pode ter sido vencida, no todo ou em parte. O voto
  complementar, o voto revisor e a declaração de voto também não são a decisão.
- **Enunciado** é o resumo do Informativo. Ajuda a achar o acórdão, mas não é a decisão.
- A **análise da unidade técnica** não está na base e não é decisão.

Cada resultado diz de que peça veio. Antes de escrever "o TCU decidiu X", confira que a afirmação está no ACORDAO,
lendo essa peça com `acordaos_ler` e `secao='ACORDAO'` se preciso. Na resposta, diga a peça de onde veio cada
afirmação.

## Detalhes de cada ferramenta

- **`acordaos_buscar`:** devolve a janela dos melhores. A ausência ali não prova que não existe. Filtros opcionais:
  `ano`, `colegiado` (P, 1C ou 2C) e `secao`.
- **`acordaos_grep`:** busca por termos. O trecho mostra onde os termos aparecem, mas não prova que a frase é
  contígua. A resposta traz `total` (trechos) e `totalDocs` (acórdãos); com `cursor`, a lista está incompleta.
- **`acordaos_navegar`:** devolve o **total exato** do filtro. É a ferramenta do levantamento ("quantos acórdãos o
  relator X relatou em 2024?") e da prova de inexistência: total zero quer dizer que não há acórdão no recorte.
- **`acordaos_ler`:** o texto é longo. Peça uma peça com `secao` e limite o tamanho com `max_chars`. Se o texto vier
  cortado, continue pelo `cursor`. O texto só vem se a conferência de integridade passar. Se a ferramenta avisar que
  não pôde conferir, não reconstrua o teor de memória.

## Como citar

- Número, ano e colegiado ("Acórdão 1.917/2024-Plenário"), a peça e o link do inteiro teor que veio no resultado.
- Um resultado de legislação pode trazer o campo "Jurisprudência TCU (Acórdão N):". É uma curadoria pontual, ligada
  ao dispositivo. A pesquisa de jurisprudência propriamente dita é feita por estas quatro ferramentas.
- Lei e acórdão na mesma resposta: primeiro a norma, com o link dela, depois o entendimento do TCU, com o link do
  acórdão.

## Exemplos

| Pedido | Chamada |
|---|---|
| "O que o TCU entende sobre exigência de atestado de capacidade técnica?" | `acordaos_buscar` com "exigência de atestado de capacidade técnica" |
| "Quantos acórdãos do Plenário de 2024 o ministro Nardes relatou?" | `acordaos_navegar` com relator, colegiado P e ano 2024 |
| "Me mostra a decisão do Acórdão 1.917/2024 do Plenário" | `acordaos_ler` com número 1917, ano 2024, colegiado P e `secao='ACORDAO'` |
| "Onde os acórdãos falam em seguro-garantia?" | `acordaos_grep` com "seguro-garantia" |
