# Encontro 18 - Responsividade com Viewport, Unidades Relativas e Media Queries

**Unidade:** Unidade 1  
**Entrega:** Página responsiva

## Visão Geral
Neste encontro, você adapta páginas para diferentes larguras de tela.
O foco é entender viewport, abordagem mobile-first, unidades relativas e media queries.

Se nos encontros anteriores você estilizou e organizou a página, agora você garante que ela continue funcional em diferentes dispositivos.

## Conceitos Essenciais
- Meta viewport.
- Abordagem mobile-first.
- Unidades relativas para largura e tipografia.
- Imagens fluidas.
- Media queries para mudança de layout.

## 1) Viewport
Para páginas responsivas, o HTML deve incluir:

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

## 2) Estratégia mobile-first
Primeiro definimos estilos para telas menores.
Depois ampliamos o layout com media queries.

## 3) Imagens fluidas
```css
img {
  max-width: 100%;
  height: auto;
}
```

## 4) Media queries
```css
.layout {
  display: block;
}

@media (min-width: 768px) {
  .layout {
    display: grid;
    grid-template-columns: 16rem 1fr;
  }
}
```

## 5) Exercício
Adapte uma página criada nos encontros 16 ou 17 para que ela:
- funcione bem em tela estreita;
- use imagens fluidas;
- altere o layout em pelo menos um ponto de quebra;
- reorganize menu, conteúdo ou cartões;
- mantenha boa leitura em celular e desktop.

## 6) Validação rápida antes de considerar concluído
- O HTML tem meta viewport.
- As imagens não ultrapassam a largura do contêiner.
- Há pelo menos uma media query funcional.
- O layout muda de forma planejada em telas maiores.
- A versão móvel continua legível e navegável.

## 7) Erros comuns de iniciantes
- começar pelo desktop e tentar reduzir tudo depois;
- usar larguras fixas em excesso;
- esquecer de testar em diferentes tamanhos de janela;
- criar ponto de quebra sem necessidade;
- não adaptar espaçamentos e tamanhos de texto.

## Materiais para Aprofundamento
- [MDN - Design responsivo](https://developer.mozilla.org/pt-BR/docs/Learn_web_development/Core/CSS_layout/Responsive_Design)
- [MDN - `@media`](https://developer.mozilla.org/pt-BR/docs/Web/CSS/@media)
- [MDN - Meta viewport](https://developer.mozilla.org/pt-BR/docs/Web/HTML/Viewport_meta_tag)

## Checklist de Compreensão
- [ ] Consigo explicar o papel da meta viewport.
- [ ] Consigo aplicar a lógica mobile-first.
- [ ] Consigo usar imagens fluidas.
- [ ] Consigo escrever uma media query básica.
- [ ] Consigo adaptar um layout para diferentes larguras.

## Resumo Final
Neste encontro, você tornou a página adaptável a diferentes telas e consolidou a ideia de responsividade como requisito básico de front-end moderno. O próximo passo é revisar tudo em uma lista orientada de exercícios.
