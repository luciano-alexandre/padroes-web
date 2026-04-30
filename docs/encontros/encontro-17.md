# Encontro 17 - CSS Grid para Estrutura de Páginas

**Unidade:** Unidade 1  
**Entrega:** Página em Grid

## Visão Geral
Neste encontro, você aprende a estruturar páginas em duas dimensões com CSS Grid.
O foco é controlar linhas, colunas e áreas de layout de maneira mais previsível.

Se no Encontro 16 você organizou grupos de elementos com Flexbox, agora você trabalha a malha geral da página.

## Conceitos Essenciais
- `display: grid`.
- `grid-template-columns` e `grid-template-rows`.
- `gap`.
- Áreas nomeadas com `grid-template-areas`.
- Diferença geral entre Grid e Flexbox.

## 1) Quando usar Grid?
Grid é especialmente útil quando você precisa controlar linhas e colunas ao mesmo tempo.

### Exemplo
```css
.layout {
  display: grid;
  grid-template-columns: 1fr 2fr;
  gap: 1rem;
}
```

## 2) Áreas nomeadas
Áreas nomeadas ajudam a visualizar a estrutura da página.

```css
.layout {
  display: grid;
  grid-template-columns: 16rem 1fr;
  grid-template-areas:
    "cabecalho cabecalho"
    "menu conteudo"
    "rodape rodape";
  gap: 1rem;
}
```

## 3) Associação dos elementos às áreas
```css
header {
  grid-area: cabecalho;
}

nav {
  grid-area: menu;
}

main {
  grid-area: conteudo;
}

footer {
  grid-area: rodape;
}
```

## 4) Exercício
Monte uma página com:
- `header`, `nav`, `main` e `footer`;
- organização em Grid;
- pelo menos duas colunas;
- uso de `gap`;
- estrutura clara entre menu lateral e conteúdo principal.

## 5) Validação rápida antes de considerar concluído
- O contêiner principal usa `display: grid`.
- A página possui colunas definidas.
- O conteúdo principal está visualmente separado da navegação.
- O Grid melhora a leitura da estrutura.
- O CSS está organizado e sem regras repetidas desnecessárias.

## 6) Erros comuns de iniciantes
- tentar resolver tudo com Grid sem necessidade;
- esquecer de definir colunas;
- criar áreas sem nome coerente;
- misturar Grid e Flexbox sem entender o papel de cada um;
- não testar o comportamento com pouco e muito conteúdo.

## Materiais para Aprofundamento
- [MDN - CSS Grid Layout](https://developer.mozilla.org/pt-BR/docs/Learn_web_development/Core/CSS_layout/Grids)
- [MDN - `grid-template-columns`](https://developer.mozilla.org/pt-BR/docs/Web/CSS/grid-template-columns)
- [MDN - `grid-template-areas`](https://developer.mozilla.org/pt-BR/docs/Web/CSS/grid-template-areas)

## Checklist de Compreensão
- [ ] Consigo ativar Grid em um contêiner.
- [ ] Consigo definir colunas com `grid-template-columns`.
- [ ] Consigo usar `gap` para espaçamento.
- [ ] Consigo montar áreas nomeadas básicas.
- [ ] Consigo comparar usos gerais de Grid e Flexbox.

## Resumo Final
Neste encontro, você aprendeu a estruturar a página com CSS Grid e passou a controlar melhor a disposição global dos blocos. Com isso, você já possui as principais bases de layout da unidade.
