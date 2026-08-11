# Como adicionar novos projetos (cards)

Copie um bloco `<article class="card">` inteiro do `index.html` e ajuste o
conteúdo. Existem dois formatos.

## Card simples (1 coluna)

Use para projetos com uma imagem só e descrição curta.

```html
<article class="card">
  <p class="refdes">U10</p>
  <figure class="footprint" data-file="assets/novo-projeto.jpg">
    <img src="assets/novo-projeto.jpg" alt="Descrição da imagem para acessibilidade" loading="lazy">
  </figure>
  <h3>Nome do Projeto</h3>
  <p>Descrição curta — o que é, qual problema resolve, quais tecnologias.</p>
</article>
```

## Card largo (2 colunas — imagem principal + fotos extras + link de repositório)

Use para projetos com várias fotos (schematic, layout, protótipo) ou que
tenham um repositório no GitHub, como o eAlive ou o Conveyor Belt Sorting
System.

```html
<article class="card wide">
  <p class="refdes">U11</p>
  <figure class="footprint" data-file="assets/novo-projeto-principal.jpg">
    <img src="assets/novo-projeto-principal.jpg" alt="..." loading="lazy">
  </figure>
  <h3>Nome do Projeto</h3>
  <p>Descrição curta.</p>
  <div class="subgrid">
    <figure class="footprint small" data-file="assets/novo-projeto-01.jpg">
      <img src="assets/novo-projeto-01.jpg" alt="..." loading="lazy">
    </figure>
    <figure class="footprint small" data-file="assets/novo-projeto-02.jpg">
      <img src="assets/novo-projeto-02.jpg" alt="..." loading="lazy">
    </figure>
  </div>
  <a class="repo-link" href="https://github.com/seu-usuario/repo" target="_blank" rel="noopener">
    View source — github.com/seu-usuario/repo ↗
  </a>
</article>
```

## Regras práticas

- **Onde colar**: dentro da `<section class="category">` certa — se for algo
  tipo PCB, cola dentro do bloco que tem `// PCB PROJECTS`; se for mecânico,
  no de `// MECHANICAL CADs`; senão, cria uma seção nova (copia o bloco
  `<section class="category">` inteiro, trocando o
  `<p class="comment">// NOME DA SEÇÃO</p>`).
- **`refdes`**: só precisa ser único e sequencial (`U10`, `U11`...) — é
  decorativo, não afeta o funcionamento se pular um número.
- **`data-file` e `src`**: sempre com o mesmo caminho — é o que faz o
  placeholder "NOT POPULATED" mostrar o nome certo até a foto ser
  adicionada em `assets/`.
- **`alt`**: descreva o que aparece na imagem, não repita o título — ajuda
  acessibilidade e SEO.
