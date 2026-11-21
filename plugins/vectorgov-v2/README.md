# VectorGov para o Claude

O VectorGov é uma base de contexto jurídico para quem trabalha com licitações e contratações públicas no Brasil: setores de compras, agentes de contratação, pregoeiros, assessorias jurídicas e controle interno.

Este plugin conecta o Claude ao VectorGov e instala o **Guia das ferramentas do VectorGov**, a skill que mostra ao Claude qual ferramenta usar em cada pedido e como citar a fonte.

## O que você consegue fazer

- **Ler o texto de um dispositivo:** peça um artigo, parágrafo ou inciso e receba o texto na redação vigente, com o link para o trecho exato da norma.
- **Buscar por assunto na legislação:** a Lei 14.133/2021 e as normas correlatas, como decretos e instruções normativas.
- **Localizar um termo exato:** siglas e expressões literais nas normas e nos acórdãos.
- **Pesquisar a jurisprudência do TCU** sobre licitações e contratos, com a leitura do inteiro teor.
- **Achar o código do item no catálogo oficial de compras** (CATMAT e CATSER), um a um ou a partir de uma lista de descritivos.
- **Conduzir a pesquisa de preços** pela IN SEGES/ME nº 65/2021, com os preços praticados nas compras públicas, a memória de cálculo, o mapa e o relatório.
- **Abrir skills de método** da fase preparatória da contratação, que ficam no catálogo de skills do próprio VectorGov.

Cada resultado de legislação e de acórdão traz o link para a fonte, para você conferir a citação.

## Como começar

1. Instale o plugin.
2. Na primeira consulta, entre com a sua conta do [vectorgov.io](https://vectorgov.io). Se ainda não tem conta, crie uma na mesma tela.
3. Faça o pedido em português, como faria a um colega.

Exemplos de pedidos:

- "O que diz o art. 75 da Lei 14.133/2021 sobre a dispensa por valor? Mostre o texto e o link da fonte."
- "Quais acórdãos do TCU tratam de sobrepreço na pesquisa de preços?"
- "Qual é o código do catálogo de compras para papel sulfite A4, 75 g/m²?"

## O que o plugin instala

- **A conexão com o VectorGov**, que exige a sua conta. As consultas usam o perfil de pesquisa que o administrador da sua conta liberou, por exemplo a legislação federal ou o acervo de um órgão.
- **A skill "Guia das ferramentas do VectorGov"**, em português. Ela não executa nada na sua máquina: é só texto de orientação para o Claude.

## Limites que vale conhecer

- **As respostas são geradas por inteligência artificial** a partir dos textos consultados. Elas não substituem a análise do profissional responsável: confira a citação no link da fonte antes de usar em um processo.
- **O acervo cobre licitações e contratações públicas.** Perguntas de outros ramos do direito não são atendidas.
- **A pesquisa de preços consulta os registros oficiais de compras públicas** e pode pedir que você aguarde quando houver fila.
- **Há um limite de consultas por minuto por conta.** Quando ele é atingido, o VectorGov avisa e basta tentar de novo em seguida.

## Privacidade e suporte

- Política de privacidade: [vectorgov.io/privacidade](https://vectorgov.io/privacidade)
- Termos de serviço: [vectorgov.io/termos](https://vectorgov.io/termos)
- Suporte: [vectorgov.io/suporte](https://vectorgov.io/suporte) ou suporte@vectorgov.io

## Atualização

No Claude Code, atualize o marketplace e depois o plugin, e reinicie a sessão:

```
/plugin marketplace update vectorgov-v2
/plugin update vectorgov-v2@vectorgov-v2
```

## Licença

MIT.
