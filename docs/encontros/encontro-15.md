# Encontro 15 - Box Model, Bordas, Espaçamentos e `display`

**Unidade:** Unidade 1  
**Entrega:** Componentes em bloco e cartão

## Visão Geral
Neste encontro, você aprofunda a organização visual dos elementos com o box model e propriedades de espaçamento.
O foco é entender como largura, altura, borda, `padding`, `margin` e `display` afetam a renderização da página.

Se no Encontro 14 você cuidou de tipografia e cores, agora você passa a controlar a ocupação de espaço de cada bloco.

## Conceitos Essenciais
- Box model.
- `width`, `max-width` e `height`.
- `padding`, `border` e `margin`.
- `box-sizing: border-box`.
- Diferença entre `block`, `inline` e `inline-block`.

## 1) O box model
Todo elemento em HTML pode ser entendido como uma caixa com:
- conteúdo;
- preenchimento interno (`padding`);
- borda (`border`);
- margem externa (`margin`).

### Exemplo
```css
.card {
  padding: 1rem;
  border: 1px solid #cbd5e1;
  margin-bottom: 1rem;
}
```

## 2) Controle de largura
Nem sempre é bom deixar caixas ocuparem toda a largura disponível.

### Exemplo
```css
main {
  width: 90%;
  max-width: 70rem;
  margin: 0 auto;
}
```

## 3) `box-sizing`
Usar `border-box` simplifica o cálculo das dimensões.

```css
* {
  box-sizing: border-box;
}
```

## 4) `display`
O valor de `display` altera como o elemento ocupa espaço na linha e na página.

### Exemplo
```css
a {
  display: inline-block;
  padding: 0.5rem 1rem;
}
```

## 5) Exercício
Monte uma página com:
- um contêiner centralizado;
- três cartões (`card`) com título e parágrafo;
- borda, preenchimento e margem visíveis;
- botões ou links com `display: inline-block`;
- uso de `box-sizing: border-box`.

## 6) Validação rápida antes de considerar concluído
- O contêiner principal está centralizado.
- Os cartões mostram diferença clara entre borda, margem e preenchimento.
- O CSS usa `max-width`.
- Há uso intencional de `display`.
- O layout está mais organizado do que apenas com tipografia e cor.

## 7) Erros comuns de iniciantes
- confundir `padding` com `margin`;
- definir largura fixa excessiva;
- esquecer `box-sizing` e se confundir com o tamanho final;
- usar `display` sem entender o efeito;
- acumular espaçamentos inconsistentes entre blocos.

## Materiais para Aprofundamento
- [MDN - Box model](https://developer.mozilla.org/pt-BR/docs/Learn_web_development/Core/Styling_basics/Box_model)
- [MDN - `box-sizing`](https://developer.mozilla.org/pt-BR/docs/Web/CSS/box-sizing)
- [MDN - `display`](https://developer.mozilla.org/pt-BR/docs/Web/CSS/display)
- [MDN - `margin`](https://developer.mozilla.org/pt-BR/docs/Web/CSS/margin)

## Checklist de Compreensão
- [ ] Consigo explicar o box model.
- [ ] Consigo diferenciar `padding`, `border` e `margin`.
- [ ] Consigo controlar largura com `width` e `max-width`.
- [ ] Consigo usar `display` de forma básica.
- [ ] Consigo montar componentes visuais mais consistentes.

## Resumo Final
Neste encontro, você passou a controlar a caixa visual dos elementos e a relação espacial entre blocos. Esse domínio é a base para os próximos encontros de layout com Flexbox e Grid.
