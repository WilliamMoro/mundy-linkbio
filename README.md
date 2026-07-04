# Mundy Educação — Link Bio

<div align="center">

```
  ╭──────────────────────────────────────╮
  │                                      │
  │        ◉  Mundy Educação             │
  │           Novo Horizonte             │
  │                                      │
  │     CURSOS E TREINAMENTOS            │
  │                                      │
  │  [ Ver Catálogo ]  [ Ver PDF ]       │
  │  ─────────────────────────────       │
  │  WhatsApp · Secretaria               │
  │  WhatsApp · Sala de Aula             │
  │  WhatsApp · Comercial                │
  │  ─────────────────────────────       │
  │  Instagram          Facebook         │
  │                                      │
  ╰──────────────────────────────────────╯
```

[![Netlify Status](https://api.netlify.com/api/v1/badges/placeholder/deploy-status)](https://mundy-educacao.netlify.app)
![HTML](https://img.shields.io/badge/HTML-puro-E87722?style=flat-square)
![CSS](https://img.shields.io/badge/CSS-vanilla-1A1410?style=flat-square)
![JS](https://img.shields.io/badge/JS-sem_framework-F5C518?style=flat-square)
![Deploy](https://img.shields.io/badge/deploy-Netlify-00C7B7?style=flat-square)

**[🔗 Ver site ao vivo](https://mundy-educacao.netlify.app)**

</div>

---

## O que é isso

Site de link bio construído para a **Mundy Educação Novo Horizonte**, escola privada focada em cursos profissionalizantes online. A ideia era ter uma página única e rápida para centralizar os contatos, redes sociais e o catálogo de cursos — sem depender de ferramentas como Linktree ou Beacons.

Tudo feito com HTML, CSS e JavaScript puro. Nenhuma dependência, nenhum framework, nenhum npm install. Abre em qualquer lugar e carrega em menos de 1 segundo.

---

## Páginas

### `/index.html` — Bio Link principal

A tela de entrada. Hero card com a logo da Mundy, botões para o catálogo (HTML e PDF), três contatos de WhatsApp separados por função e links diretos para Instagram e Facebook.

Tem dark/light mode com detecção automática do sistema — se o celular do usuário estiver em modo escuro, a página já abre escura. O botão de alternância fica fixo no canto superior direito.

### `/CatalogoMundy/index.html` — Catálogo de Cursos

25 pacotes de cursos organizados em 7 categorias, extraídos diretamente do PDF do catálogo da escola. Cada card mostra o nome do curso, carga horária, módulos incluídos, média salarial da área e um botão "Saiba Mais" que abre direto no WhatsApp Comercial.

Tem filtros por categoria e animações de entrada com Intersection Observer.

---

## Segurança

Os links de WhatsApp não ficam expostos em texto no HTML. Todos são armazenados como arrays de inteiros codificados com XOR e só são decodificados no momento exato do clique — isso impede que alguém abra o DevTools e altere os números para redirecionar usuários a contatos falsos ou links maliciosos.

```js
// os links ficam assim no código
wa_com: [37,26,16,9,54,94,90,22,58,15,74,21,44,10,30,22,32,4,10,28,124,13]

// e são decodificados apenas no clique
function _d(arr) {
  return arr.map((b, i) => String.fromCharCode(b ^ _K[i % _K.length])).join('');
}
```

---

## Estrutura

```
LinkBio/
├── index.html              # bio link principal
├── .gitignore
├── README.md
├── CatalogoMundy/
│   └── index.html          # catálogo completo dos cursos
└── assets/
    ├── Catalogo_Final.pdf  # PDF do catálogo para download
    └── logo.png            # logo original (backup — já embutida em base64 no HTML)
```

A logo está embutida em base64 diretamente no HTML, o que significa que o site funciona como um arquivo único — sem dependência de caminhos de imagem que podem quebrar dependendo de onde o arquivo é aberto.

---

## Rodando localmente

Não precisa de servidor, build ou instalação. Só abrir o arquivo:

```bash
# clona o repositório
git clone https://github.com/WilliamMoro/mundy-linkbio.git

# abre direto no navegador
start LinkBio/index.html   # Windows
open LinkBio/index.html    # Mac
```

---

## Deploy

O site está hospedado no **Netlify** com deploy automático via GitHub. Qualquer push na branch `main` atualiza o site em produção em menos de 30 segundos.

```bash
# para atualizar o site em produção
git add .
git commit -m "descrição da mudança"
git push
```

---

## Tech

- **HTML5 / CSS3 / JavaScript ES5+** — sem frameworks, sem build step
- **Google Fonts (Poppins)** — via CDN
- **Netlify** — hospedagem e deploy contínuo
- **GitHub** — versionamento

---

## Créditos

Desenvolvido para a Mundy Educação Novo Horizonte · SP
