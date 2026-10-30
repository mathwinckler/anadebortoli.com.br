# Site da Dra. Ana De Bortoli

Site estático, sem build: HTML e CSS puros, publicados como estão.

| caminho | o que é | estado |
|---|---|---|
| `/` | página principal. Hoje é provisória ("site em construção"), com agendar e link para o hub | provisória |
| `/hub/` | página de links da bio do Instagram (agendar pelo WhatsApp, onde atendo, Instagram) | no ar quando publicar |
| `/404.html` | página não encontrada, leva ao hub | pronta |
| `assets/css/base.css` | paleta, fontes, título, botões e rodapé, comuns a todas as páginas | base |
| `assets/img/` | monograma e foto | base |

## Como cresce

- **Página nova** vira pasta com `index.html` (`/sobre/`, `/cirurgias/`, `/blog/`) e importa
  `assets/css/base.css`. O estilo próprio dela fica no `<style>` da página.
- **O site principal** substitui o `index.html` da raiz. O `/hub/` não muda de endereço: é o link
  da bio.
- Caminhos são **relativos** (`../assets/...`), para funcionar no domínio próprio e no endereço
  provisório do GitHub Pages. A exceção é o `404.html`, que usa absolutos porque é servido em
  qualquer profundidade (no endereço provisório ele perde o estilo; no domínio funciona).
- A identidade visual (paleta, fontes, regras) mora no projeto analu-abw, em
  `profissional-analu/marketing-analu/IDENTIDADE-VISUAL.md`. Este repositório aplica, não define.

## Ver localmente

```
python3 -m http.server 8787
```

e abrir `http://127.0.0.1:8787` (raiz) e `http://127.0.0.1:8787/hub/`.

## Publicar

GitHub Pages, branch `main`, pasta raiz. O `.nojekyll` faz o GitHub servir os arquivos como
estão. Com o domínio comprado: criar o arquivo `CNAME` com o domínio (uma linha, ex.
`anadebortoli.com.br`), apontar o DNS (4 registros A para o GitHub e `www` em CNAME) e marcar
"Enforce HTTPS" nas configurações do Pages.
