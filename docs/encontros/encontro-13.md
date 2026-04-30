# Encontro 13 - Cascata, Herança, Especificidade e Combinadores

**Unidade:** Unidade 1  
**Entrega:** Exercícios com seletores

## Visão Geral
Neste encontro, você aprofunda os fundamentos de CSS estudando como o navegador decide qual regra será aplicada em cada elemento.
O foco é compreender cascata, herança, especificidade e combinadores para escrever estilos com mais controle.

Se no Encontro 12 você aprendeu a sintaxe e os seletores básicos, agora você entende como diferentes regras convivem na mesma página.

## Conceitos Essenciais
- Cascata como mecanismo de prioridade entre regras.
- Herança de propriedades entre elementos.
- Especificidade de seletores.
- Combinadores por descendência, filho direto e agrupamento.
- Organização consciente do CSS para evitar conflitos.

## 1) O que é a cascata?
A cascata é o processo usado pelo navegador para decidir qual regra CSS vence quando várias regras afetam o mesmo elemento.

### Exemplo
```css
p {
  color: #333333;
}

.aviso {
  color: darkred;
}
```

Se um parágrafo tiver `class="aviso"`, a regra da classe tende a prevalecer sobre a do elemento.

## 2) O que é herança?
Algumas propriedades passam do elemento pai para os filhos, especialmente as relacionadas a texto.

### Exemplo
```css
body {
  font-family: Georgia, serif;
  color: #222222;
}
```

Nesse caso, vários elementos internos herdam essas propriedades automaticamente.

## 3) Especificidade
A especificidade ajuda a decidir qual seletor tem prioridade.

### Ordem simplificada
- seletor por elemento;
- seletor por classe;
- seletor por id.

### Exemplo
```css
p {
  color: #444444;
}

.resumo {
  color: #0b5d3b;
}

#mensagem-principal {
  color: #123a7a;
}
```

## 4) Combinadores úteis
Combinadores ajudam a selecionar elementos conforme sua posição na estrutura HTML.

### Exemplos
```css
main p {
  line-height: 1.6;
}

nav > a {
  text-decoration: none;
}

h1, h2, h3 {
  font-family: Arial, sans-serif;
}
```

## 5) Exemplo principal do encontro
```html
<main class="conteudo">
  <section>
    <h2>Notícias</h2>
    <p class="resumo">Resumo da atividade da semana.</p>
  </section>
</main>
```

```css
body {
  color: #222222;
}

main p {
  color: #555555;
}

.resumo {
  color: #1f6f50;
  font-weight: bold;
}
```

## 6) Exercício
Estilize uma página HTML já criada anteriormente e inclua:
- uma regra herdada pelo `body`;
- regras para `h1`, `p` e `a`;
- pelo menos duas classes;
- um seletor com combinador por descendência;
- um seletor agrupado.

## 7) Validação rápida antes de considerar concluído
- O CSS demonstra diferença entre elemento, classe e id.
- Há pelo menos um caso em que a herança aparece claramente.
- Existe uso correto de combinador.
- As regras não se repetem sem necessidade.
- O resultado final está coerente visualmente.

## 8) Erros comuns de iniciantes
- usar id para tudo;
- duplicar regras sem perceber conflito;
- não entender por que uma classe sobrescreve o seletor de elemento;
- escrever seletores longos demais sem necessidade;
- tentar resolver tudo com `!important`.

## Materiais para Aprofundamento
- [MDN - Cascata](https://developer.mozilla.org/pt-BR/docs/Web/CSS/Cascade)
- [MDN - Herança em CSS](https://developer.mozilla.org/pt-BR/docs/Web/CSS/inheritance)
- [MDN - Especificidade](https://developer.mozilla.org/pt-BR/docs/Web/CSS/Specificity)
- [MDN - Seletores e combinadores](https://developer.mozilla.org/pt-BR/docs/Web/CSS/CSS_selectors/Selectors_and_combinators)

## Checklist de Compreensão
- [ ] Consigo explicar o que é cascata.
- [ ] Consigo identificar propriedades herdadas.
- [ ] Consigo comparar especificidade entre seletores simples.
- [ ] Consigo usar combinadores para selecionar elementos no HTML.
- [ ] Consigo evitar conflitos desnecessários entre regras.

## Resumo Final
Neste encontro, você aprendeu como as regras CSS disputam prioridade e como organizar seletores com mais precisão. Esse entendimento é decisivo para avançar para a construção visual da página com menos tentativa e erro.
