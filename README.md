# davileles-site

Espelho do site público do **Tudo Sobre Promos** no domínio `davileles.com`.
Estático, servido pelo GitHub Pages.

## Arquivos

| Caminho | O que é |
|---|---|
| `index.html` | a página inteira (HTML, CSS e JS num arquivo só) |
| `CNAME` | `davileles.com` |

## De onde vêm os dados

**Este repositório não recebe publicação.** Não existe pasta `dados/` aqui de
propósito. O `feed-publico.js` do **davileles/baileys-server** continua
publicando apenas em `davileles/tsp-site`, e esta página lê os JSONs de lá por
HTTP, em `BASES_DADOS` (topo do `<script>`):

1. `https://www.tudosobrepromos.com/dados/`
2. `https://gestao.tudosobrepromos.com/dados/` (queda)

O GitHub Pages responde com `Access-Control-Allow-Origin: *`, então a leitura
entre domínios funciona. Consequência prática: quando o feed publica, os dois
sites atualizam juntos, sem nenhum passo a mais.

## O que NÃO mudar

Nada no `baileys-server`, no Railway ou no `tsp-site` foi tocado para este
espelho existir. Se um dia quiser independência total, a alternativa é
transformar `GITHUB_REPO_PUBLICO` numa lista e publicar nos dois repositórios.
