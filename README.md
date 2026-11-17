# VectorGov para o Claude

Plugin do VectorGov para o Claude Code e o Cowork. Ele conecta o VectorGov e instala o **Guia das ferramentas do VectorGov**, a skill que mostra ao Claude qual ferramenta usar em cada pedido e como citar a fonte.

O que o VectorGov consulta:
- a legislação de licitações e contratações públicas (Lei 14.133/2021 e normas correlatas), na redação vigente;
- a jurisprudência do TCU sobre licitações e contratos;
- o catálogo oficial de compras (CATMAT/CATSER).

Cada resultado de legislação e de acórdão traz o link para o trecho exato da fonte.

## Instalação

No Claude Code:

```
/plugin marketplace add etaldev/plugin-claude-v2
/plugin install vectorgov-v2@vectorgov-v2
```

Na primeira consulta, entre com a sua conta do [vectorgov.io](https://vectorgov.io).

## Atualização

```
/plugin marketplace update vectorgov-v2
/plugin update vectorgov-v2@vectorgov-v2
```

Depois de atualizar, reinicie a sessão.

## Licença

MIT.
