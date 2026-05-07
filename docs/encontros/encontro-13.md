# Encontro 13 - Cascata, Herança, Especificidade e Combinadores

**Unidade:** Unidade 1  
**Entrega:** Exercícios com seletores

## Visão Geral
Neste encontro, você aprofunda os fundamentos de CSS estudando como o navegador decide qual regra será aplicada em cada elemento.
O foco é compreender cascata, herança, especificidade e combinadores para escrever estilos com mais controle e menos tentativa e erro.

Se no Encontro 12 você aprendeu a sintaxe e os seletores básicos, agora você entende como diferentes regras convivem na mesma página e como prever o resultado final.

## Conceitos Essenciais
- Cascata como mecanismo de prioridade entre regras.
- Herança de propriedades entre elementos.
- Especificidade de seletores.
- Combinadores por descendência, filho direto e agrupamento.
- Organização consciente do CSS para evitar conflitos e retrabalho.

## 1) O que é a cascata?
A cascata é o processo usado pelo navegador para decidir qual regra CSS vence quando várias regras afetam o mesmo elemento.

Em termos práticos, o navegador considera:
- a especificidade do seletor;
- a ordem das regras no arquivo (em empate, a última vence);
- casos especiais, como uso de `!important`.

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

### Cenário comum
Em uma página de avisos, você define um estilo geral para todos os parágrafos e depois cria a classe `.aviso` para mensagens críticas.
Assim, você mantém consistência no projeto e altera apenas os casos especiais.

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

### Observação importante
- costumam herdar: `color`, `font-family`, `line-height`;
- normalmente não herdam: `border`, `background`.

### Cenário comum
Definir tipografia e cor base no `body` evita repetição em `h1`, `p`, `li` e outros elementos de texto.
Você escreve menos CSS e mantém o visual mais uniforme.

## 3) Especificidade
A especificidade ajuda a decidir qual seletor tem prioridade quando múltiplas regras atingem o mesmo elemento.

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

Se um elemento tiver `id="mensagem-principal"` e `class="resumo"`, o estilo de id tende a prevalecer na propriedade disputada.

### Cenário comum
Em uma página de notícias, a classe `.resumo` pode estilizar todos os resumos, enquanto um id específico destaca apenas uma mensagem principal da página.

## 4) Combinadores úteis
Combinadores ajudam a selecionar elementos conforme sua posição na estrutura HTML.
Eles são essenciais para evitar seletores genéricos demais.

### Exemplo detalhado
```html
<nav class="menu">
  <a href="/">Início</a>
  <ul>
    <li><a href="/cursos">Cursos</a></li>
    <li><a href="/contato">Contato</a></li>
  </ul>
</nav>

<main>
  <section>
    <p>Parágrafo da seção principal.</p>
  </section>
</main>
```

```css
main p {
  line-height: 1.6;
}

nav > a {
  text-decoration: none;
  font-weight: bold;
}

nav a {
  color: #1b4d8f;
}

h1, h2, h3 {
  font-family: Arial, sans-serif;
}
```

### Como ler esse exemplo
- `main p`: aplica em todo `p` que estiver dentro de `main`, mesmo que esteja em níveis internos.
- `nav > a`: aplica apenas ao link filho direto de `nav` (`Início`), sem afetar os links dentro da lista.
- `nav a`: aplica em todos os links dentro de `nav`, incluindo os de submenu (`Cursos` e `Contato`).
- `h1, h2, h3`: agrupamento de seletores para reaproveitar a mesma regra em vários títulos.

### Cenário comum
Em menus com subníveis, `>` evita que o estilo do topo "vaze" para links internos.
Isso deixa o CSS mais previsível e facilita manutenção quando o menu cresce.

## 5) Exemplo principal do encontro
```html
<main class="conteudo">
  <section class="noticias">
    <h2>Notícias</h2>
    <p>Texto introdutório da seção.</p>
    <p class="resumo" id="mensagem-principal">Resumo da atividade da semana.</p>
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

#mensagem-principal {
  color: #123a7a;
}
```

### Leitura do resultado
- o `body` define a cor base herdada;
- `main p` altera a cor de todos os parágrafos da área principal;
- `.resumo` destaca parágrafos de resumo;
- `#mensagem-principal` vence na cor final desse elemento específico por maior especificidade.

## 6) Exercício
Estilize uma página HTML, simulando um mini portal da turma, e aplique de forma intencional os principais recursos de CSS já estudados.

### Estrutura mínima sugerida
- `header` com título e subtítulo;
- `nav` com pelo menos 3 links;
- `main` com 2 seções;
- 1 bloco de destaque com classe própria;
- `footer` com informação final.

### Requisitos obrigatórios de CSS
Seu arquivo `styles.css` deve demonstrar:
- herança no `body` com `font-family` e `color`;
- uso de `background-color` em áreas distintas da página;
- controle tipográfico com `font-size`, `font-weight` e `line-height`;
- estilização de links com `text-decoration`;
- pelo menos um seletor por elemento, classe e id;
- pelo menos um combinador por descendência e um por filho direto;
- pelo menos um seletor agrupado;
- texto alinhado à esquerda (sem exigir centralização);
- organização em blocos empilhados (sem exigir elementos lado a lado).


**Exemplo visual do resultado esperado:**
![Exemplo visual do exercício do Encontro 13](./imagens/encontro-13-exec-resultado.png)

## 7) Validação rápida antes de considerar concluído
- O CSS demonstra diferença entre elemento, classe e id.
- Há pelo menos um caso em que a herança aparece claramente.
- Existe uso correto de combinador por descendência e por filho direto.
- Propriedades visuais básicas (`background-color`, `color`, `font-size`, `font-family`, `font-weight`) foram aplicadas.
- O layout final está em blocos verticais, sem técnicas ainda não estudadas.
- As regras não se repetem sem necessidade.
- O resultado final está coerente visualmente.

## 8) Erros comuns de iniciantes
- usar id para tudo;
- duplicar regras sem perceber conflito;
- não entender por que uma classe sobrescreve o seletor de elemento;
- criar seletores longos demais sem necessidade;
- tentar resolver todo conflito com `!important`.

## Materiais para Aprofundamento
- [MDN - Cascata](https://developer.mozilla.org/pt-BR/docs/Web/CSS/Cascade)
- [MDN - Herança em CSS](https://developer.mozilla.org/pt-BR/docs/Web/CSS/inheritance)
- [MDN - Especificidade](https://developer.mozilla.org/pt-BR/docs/Web/CSS/Specificity)
- [MDN - Seletores e combinadores](https://developer.mozilla.org/pt-BR/docs/Web/CSS/CSS_selectors/Selectors_and_combinators)

## Checklist de Compreensão
- [ ] Consigo explicar o que é cascata.
- [ ] Consigo identificar propriedades herdadas e não herdadas mais comuns.
- [ ] Consigo comparar especificidade entre seletor de elemento, classe e id.
- [ ] Consigo usar combinadores para selecionar elementos no HTML com precisão.
- [ ] Consigo evitar conflitos desnecessários entre regras.

## Resumo Final
Neste encontro, você aprendeu como as regras CSS disputam prioridade e como organizar seletores com mais precisão.
Esse entendimento é decisivo para construir páginas com estilos previsíveis, escaláveis e fáceis de manter.
