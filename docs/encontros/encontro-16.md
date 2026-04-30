# Encontro 16 - Flexbox para Navegação, Agrupamentos e Cards

**Unidade:** Unidade 1  
**Entrega:** Layout com Flexbox

## Visão Geral
Neste encontro, você aprende a organizar elementos em linha ou coluna com Flexbox.
O foco é resolver alinhamento, distribuição e agrupamento de blocos sem recorrer a soluções improvisadas.

Se no Encontro 15 você controlou o tamanho e o espaçamento das caixas, agora você organiza essas caixas em estruturas mais flexíveis.

## Conceitos Essenciais
- `display: flex`.
- Eixo principal e eixo transversal.
- `justify-content` e `align-items`.
- `gap`, `flex-wrap` e `flex`.
- Uso de Flexbox em menus, barras e conjuntos de cartões.

## 1) Ativando Flexbox
Para transformar um contêiner em flexível, usamos:

```css
.menu {
  display: flex;
}
```

## 2) Direção e alinhamento
### Exemplo
```css
.menu {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 1rem;
}
```

## 3) Quebra de linha
Quando os itens não cabem em uma única linha, `flex-wrap` pode ajudar.

```css
.cards {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
}
```

## 4) Flexibilidade dos itens
```css
.card {
  flex: 1 1 16rem;
}
```

Esse padrão permite que os cartões cresçam, encolham e respeitem uma base inicial.

## 5) Exercício
Crie uma página com:
- `nav` em Flexbox;
- conjunto de pelo menos 3 cartões em Flexbox;
- espaçamento com `gap`;
- quebra de linha com `flex-wrap`;
- alinhamento visual coerente.

## 6) Validação rápida antes de considerar concluído
- O contêiner usa `display: flex`.
- Os itens se alinham conforme o objetivo da página.
- O menu permanece organizado.
- Os cartões quebram linha quando necessário.
- O CSS evita posicionamentos manuais desnecessários.

## 7) Erros comuns de iniciantes
- aplicar propriedades de Flexbox no item em vez do contêiner;
- esquecer de observar o eixo principal;
- usar `margin` para tudo quando `gap` resolve melhor;
- não permitir quebra em conjuntos maiores;
- esperar que Flexbox resolva estruturas bidimensionais complexas.

## Materiais para Aprofundamento
- [MDN - Flexbox](https://developer.mozilla.org/pt-BR/docs/Learn_web_development/Core/CSS_layout/Flexbox)
- [MDN - `justify-content`](https://developer.mozilla.org/pt-BR/docs/Web/CSS/justify-content)
- [MDN - `align-items`](https://developer.mozilla.org/pt-BR/docs/Web/CSS/align-items)
- [MDN - `gap`](https://developer.mozilla.org/pt-BR/docs/Web/CSS/gap)

## Checklist de Compreensão
- [ ] Consigo ativar Flexbox em um contêiner.
- [ ] Consigo explicar eixo principal e eixo transversal.
- [ ] Consigo distribuir itens com `justify-content`.
- [ ] Consigo alinhar itens com `align-items`.
- [ ] Consigo aplicar Flexbox em menus e cartões.

## Resumo Final
Neste encontro, você aprendeu a organizar grupos de elementos com Flexbox, o que simplifica menus, barras e cartões. Essa técnica prepara a transição para layouts mais amplos com CSS Grid.
