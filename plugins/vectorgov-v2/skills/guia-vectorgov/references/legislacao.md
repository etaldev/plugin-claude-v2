---
title: Legislação
when: "Antes de filtrar por norma, usar o parâmetro assunto, ler uma tabela de anexo ou paginar temas, e na dúvida entre hybrid, grep e lookup."
---

# Legislação

As ferramentas de legislação consultam o **perfil de acervo ativo** da conta. Por padrão, é a legislação federal de
licitações. O resultado diz de que norma veio cada dispositivo.

## `hybrid`: busca por assunto, a ferramenta padrão

Busca por significado. Serve para pergunta aberta ou temática, quando não se sabe qual artigo responde.

- **Resultados são trechos.** Servem para localizar e sintetizar. Para transcrever, leia o dispositivo inteiro com
  `lookup`.
- **Tamanho da janela.** O padrão é `top_k=10`, que basta para responder; uma janela maior não melhora a resposta
  direta. Use `top_k=20` só num levantamento exaustivo pedido pelo usuário ("todos os dispositivos sobre…"), e
  organize o resultado por grupos.
- **Filtros** (`tipo`, `ano`, `document_id`): use só quando o usuário pedir o recorte ("só nos decretos", "só de
  2022"). Se ele citar a lei na pergunta, o recorte já é automático.
- **Curadoria.** Procure nos resultados os rótulos "Nota do especialista:" e "Jurisprudência TCU (Acórdão N):" e use
  o que houver, atribuído e separado do texto da norma.
- **Tabelas de anexos.** Um resultado pode ser o cartão de uma tabela normativa (citação no formato "Tabela X do
  Anexo Y do …"). As linhas mostradas são uma amostra. Ela não basta para dar um valor exato (alíquota, taxa, item
  por código NCM) nem para dizer que um item não consta da tabela. Diga isso ao usuário e aponte o link do PDF.

## `lookup`: leitura direta de um dispositivo

Para quando a referência é conhecida, ou quando você precisa do texto inteiro para citar.

- **Formato da referência:** legível, como `Art. 75 da Lei 14.133/2021` ou `Art. 3, inciso II, IN 65/2021`.
- **Lote:** até 20 referências numa chamada. "Me mostra os arts. 6, 18 e 75" é uma chamada só, com as três.
- **Contexto:** o dispositivo pai e os irmãos vêm por padrão (`include_parent` e `include_siblings`). Desligue quando
  só o texto do dispositivo interessa.
- **Ambiguidade:** se o usuário disser só "art. 75" e o contexto não deixar claro de qual norma, pergunte. É a
  ambiguidade que vale interromper.
- **Identidade:** confira se a norma e o dispositivo devolvidos são os pedidos. Se vier outra norma ou outro
  dispositivo, não cite como resposta ao pedido.

## `grep`: termo literal

Procura a string exata no **texto oficial**: siglas (ETP, PCA, TR, SRP), expressões ("dispensa eletrônica") e
referências cruzadas ("onde se cita o art. 191").

Quando o texto da norma não contém o termo, a ferramenta pode devolver dispositivos em que o termo está cadastrado
como sinônimo ou citado no resumo curado. Esses resultados vêm marcados (`match_type`) e com o motivo. **Não são
ocorrências literais**: diga isso ao usuário ("o termo não aparece no texto da norma; o dispositivo foi associado a
ele pela curadoria").

## `filtrar_por_tema`: temas curados

Sem `theme`, devolve a lista de temas organizados por especialistas. Com `theme`, devolve os dispositivos do tema,
em páginas: se o usuário quer o panorama completo, avance com `page`.

## O parâmetro `assunto`

Nas ferramentas `hybrid`, `grep` e `filtrar_por_tema`, quando elas o oferecem, o parâmetro opcional `assunto` lê só
as normas de um **assunto público** (ex.: reforma tributária), no lugar do perfil ativo. Os códigos disponíveis vêm
em `menu` e `situacao_conta`. Use-o quando a pergunta for desse assunto; sem ele, vale o perfil ativo.

## Identificadores

- O resultado traz o identificador do dispositivo, como `LEI-14.133-2021#ART-075`. Use-o como veio nas consultas
  seguintes.
- O filtro `document_id` usa o identificador da norma, como `LEI-14.133-2021`. Na dúvida sobre o formato, não
  filtre: cite a norma na própria consulta.

## Exemplos

| Pedido | Chamada |
|---|---|
| "Quais são os casos de dispensa de licitação?" | `hybrid` com "casos de dispensa de licitação" |
| "Me mostra o art. 6º da Lei 14.133" | `lookup` com "Art. 6 da Lei 14.133/2021" |
| "Preciso do texto dos arts. 6, 18 e 75" | `lookup` com as três referências numa chamada |
| "Onde aparece a sigla PCA?" | `grep` com "PCA" |
| "Qual o limite atual da dispensa por valor?" | `lookup` do art. 75 e `hybrid` pelo decreto que atualiza os valores |
| "O que dá para consultar aqui?" | `filtrar_por_tema` sem tema, ou `menu` |
