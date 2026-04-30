# Encontro 14 - Cores, Tipografia, Fundos e Unidades

**Unidade:** Unidade 1  
**Entrega:** Página com identidade visual inicial

## Visão Geral
Neste encontro, você começa a dar identidade visual às páginas usando propriedades de cor, texto, plano de fundo e unidades de medida.
O foco é sair do CSS apenas estrutural e avançar para escolhas visuais coerentes.

Se no Encontro 13 você entendeu como as regras funcionam, agora você usa essas regras para construir legibilidade e aparência.

## Conceitos Essenciais
- Cores em `hex`, `rgb()` e `hsl()`.
- Tipografia com `font-family`, `font-size`, `font-weight` e `line-height`.
- Fundos com `background-color` e `background-image`.
- Unidades absolutas e relativas como `px`, `rem`, `%`, `vw` e `vh`.
- Legibilidade e contraste básico.

## 1) Cores em CSS
CSS permite trabalhar com cores de diferentes formas.

### Exemplos
```css
h1 {
  color: #173f8a;
}

body {
  background-color: rgb(247, 249, 252);
}

.aviso {
  color: hsl(10, 75%, 40%);
}
```

## 2) Tipografia
A tipografia influencia leitura, hierarquia e ritmo visual da página.

### Exemplo
```css
body {
  font-family: Verdana, sans-serif;
  font-size: 1rem;
  line-height: 1.6;
}

h1 {
  font-size: 2rem;
  font-weight: 700;
}
```

## 3) Fundos
Fundos ajudam a destacar áreas da interface e separar blocos de conteúdo.

### Exemplo
```css
header {
  background-color: #e9f2ff;
}

section {
  background-color: #ffffff;
}
```

## 4) Unidades
Nem toda medida deve ser feita com `px`.
Unidades relativas ajudam na escalabilidade e na responsividade.

### Exemplos
```css
main {
  width: 90%;
  max-width: 60rem;
}

h2 {
  margin-bottom: 1.5rem;
}
```

## 5) Exercício
Escolha uma página HTML construída anteriormente e aplique:
- paleta simples com pelo menos 3 cores;
- tipografia para `body`, `h1` e `h2`;
- fundo para `header` e para pelo menos uma `section`;
- uso combinado de `px`, `rem` e `%`;
- melhoria de contraste e legibilidade.

## 6) Validação rápida antes de considerar concluído
- O texto principal está legível.
- Há contraste adequado entre fundo e texto.
- Os títulos estão hierarquizados visualmente.
- O CSS usa ao menos uma unidade relativa.
- A página mostra identidade visual mais clara do que a versão anterior.

## 7) Erros comuns de iniciantes
- usar muitas cores sem critério;
- aplicar tamanhos exageradamente pequenos ou grandes;
- misturar fontes demais;
- usar apenas `px` em toda a página;
- criar contraste insuficiente entre texto e fundo.

## Materiais para Aprofundamento
- [MDN - `color`](https://developer.mozilla.org/pt-BR/docs/Web/CSS/color)
- [MDN - Fontes e texto em CSS](https://developer.mozilla.org/pt-BR/docs/Learn_web_development/Core/Text_styling)
- [MDN - `background`](https://developer.mozilla.org/pt-BR/docs/Web/CSS/background)
- [MDN - Valores e unidades CSS](https://developer.mozilla.org/pt-BR/docs/Learn_web_development/Core/Styling_basics/Values_and_units)

## Checklist de Compreensão
- [ ] Consigo aplicar cores de forma consistente.
- [ ] Consigo melhorar a leitura com tipografia adequada.
- [ ] Consigo usar fundos para destacar áreas da página.
- [ ] Consigo diferenciar unidades absolutas e relativas.
- [ ] Consigo criar uma primeira identidade visual com CSS.

## Resumo Final
Neste encontro, você passou a controlar a aparência textual e cromática da interface. Com isso, a página deixa de ser apenas correta tecnicamente e começa a comunicar melhor visualmente.
