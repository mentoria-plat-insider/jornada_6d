# Sua Jornada na Mentoria 6D

Pesquisa aplicada aos membros da Mentoria 6D (Grupo IGD): mapeia conquistas,
travas do momento e antecipa objeções de renovação antes que aconteçam.

São 19 telas de pergunta, uma de cada vez, com identificação por nome e e-mail
no início. Um arquivo HTML só, sem build e sem framework.

## Estrutura

| Arquivo | Para que serve |
| --- | --- |
| `index.html` | O formulário inteiro: conteúdo, estilo, validação e envio. |
| `apps-script/respostas.gs` | Recebe as respostas e grava na planilha do Google. |
| `_redirects` | Roteamento para Cloudflare Pages. |
| `_headers` | Cabeçalhos de segurança e cache. |
| `wrangler.toml` | Configuração opcional via CLI da Cloudflare. |

## Como as respostas são coletadas

Ao concluir, o formulário envia a resposta ao Apps Script publicado como App da
Web, que grava uma linha na aba **Respostas** da planilha. O cabeçalho é criado
na primeira resposta a partir do que o formulário manda.

O endereço do Apps Script fica na constante `ENDPOINT`, no início do `<script>`
do `index.html`.

**Uma resposta por e-mail.** A checagem acontece duas vezes: no formulário,
antes de a pessoa começar, e de novo no Apps Script, antes de gravar.

## Publicação no Cloudflare Pages (via dashboard)

1. Acesse dash.cloudflare.com → Pages → Create a project.
2. Conecte o repositório GitHub.
3. Em Build settings, deixe tudo em branco — não há build, é HTML puro.
4. Clique em Save and Deploy.
5. Em menos de um minuto o site está no ar com endereço `.pages.dev`.
6. Para domínio próprio: Custom domains no painel do projeto.

## Identidade visual

Segue a identidade da Mentoria 6D: laranja `#FE5533`, tinta `#282D3A`;
Fraunces nos títulos, Inter na interface, IBM Plex Mono em números.
