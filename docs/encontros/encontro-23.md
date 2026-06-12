# Encontro 23 - Pseudoclasses, Pseudoelementos, Estados Interativos e Transições

**Unidade:** Unidade 2  
**Entrega:** Interface interativa

## Visão Geral
Neste encontro, você adiciona respostas visuais às interações realizadas na página.
O foco é usar pseudoclasses, pseudoelementos e transições para comunicar estados sem alterar a estrutura principal do HTML.

Se no Encontro 22 você organizou o portal acadêmico com CSS Grid, agora os links e componentes passam a responder ao ponteiro, ao teclado e ao acionamento.

## Conceitos Essenciais
- Diferença entre estado padrão e estado interativo.
- Pseudoclasses `:hover`, `:focus-visible`, `:active` e `:focus-within`.
- Pseudoclasses estruturais como `:first-child`, `:nth-child()` e `:not()`.
- Estados de controles com `:disabled`, `:checked`, `:valid` e `:invalid`.
- Pseudoelementos `::before` e `::after`.
- Transições com `transition`.
- Transformações simples com `transform`.

## 1) O que é um estado visual?
Um componente pode mudar de aparência conforme a situação.

Exemplos:
- link ainda não acionado;
- link sob o ponteiro;
- elemento selecionado pelo teclado;
- botão pressionado;
- campo válido ou inválido;
- controle desabilitado.

O CSS representa essas situações com pseudoclasses.

### Sintaxe
```css
seletor:pseudoclasse {
  propriedade: valor;
}
```

Exemplo:

```css
a:hover {
  color: #1d4ed8;
}
```

## 2) Estado `:hover`
`:hover` é aplicado quando o ponteiro está sobre um elemento.

```css
.botao:hover {
  background-color: #1d4ed8;
}
```

Esse estado é útil para indicar que links e botões podem ser acionados.

### Cuidado
Celulares e tablets nem sempre possuem ponteiro. Por isso, a interface não deve depender apenas de `:hover` para revelar informações essenciais.

## 3) Estado `:focus-visible`
`:focus-visible` aparece quando o navegador entende que o indicador de foco precisa ser mostrado, especialmente durante a navegação por teclado.

```css
.botao:focus-visible {
  outline: 3px solid #f59e0b;
  outline-offset: 3px;
}
```

O `outline` não ocupa espaço no box model e funciona bem como indicador externo.

Evite remover o contorno sem oferecer outra indicação:

```css
/* Evite esta regra isolada */
*:focus {
  outline: none;
}
```

## 4) Estado `:active`
`:active` representa o momento em que o elemento está sendo acionado.

```css
.botao:active {
  transform: translateY(2px);
}
```

A pequena mudança de posição cria uma resposta semelhante ao pressionamento físico de um botão.

## 5) Estado interno com `:focus-within`
`:focus-within` seleciona um elemento quando ele próprio ou algum descendente está com foco.

```css
.card:focus-within {
  border-color: #2563eb;
  box-shadow: 0 0 0 4px #dbeafe;
}
```

Esse recurso é útil quando um link ou campo interno deve destacar todo o componente.

## 6) Pseudoclasses estruturais
Pseudoclasses estruturais selecionam elementos conforme sua posição ou relação com outros elementos.

### Primeiro filho
```css
.lista li:first-child {
  font-weight: 700;
}
```

### Elementos alternados
```css
.lista li:nth-child(even) {
  background-color: #eff6ff;
}
```

### Exclusão com `:not()`
```css
.menu a:not(.atual) {
  color: #475569;
}
```

Esses seletores reduzem a necessidade de criar classes apenas para representar posição.

## 7) Estados de controles
Formulários e outros controles possuem estados próprios.

### Controle desabilitado
```css
button:disabled {
  cursor: not-allowed;
  opacity: 0.5;
}
```

### Caixa selecionada
```css
input:checked + label {
  font-weight: 700;
}
```

### Campo válido e inválido
```css
input:valid {
  border-color: #15803d;
}

input:invalid {
  border-color: #b91c1c;
}
```

Esses estados serão retomados no Encontro 25, dedicado ao aprofundamento de formulários.

## 8) Pseudoelementos `::before` e `::after`
Pseudoelementos criam uma parte visual antes ou depois do conteúdo de um elemento.

```css
.card h3::after {
  content: "";
  display: block;
  width: 3rem;
  height: 0.25rem;
  margin-top: 0.5rem;
  border-radius: 999px;
  background-color: #2563eb;
}
```

Outro exemplo:

```css
.link-card::after {
  content: " >";
}
```

### Regra importante
Use pseudoelementos para acabamento visual ou conteúdo complementar simples.
Informações indispensáveis devem permanecer no HTML.

## 9) Transições com `transition`
Sem transição, a mudança de estado acontece imediatamente.

```css
.botao {
  background-color: #2563eb;
}

.botao:hover {
  background-color: #1d4ed8;
}
```

Com `transition`, a mudança ocorre de forma gradual:

```css
.botao {
  background-color: #2563eb;
  transition:
    background-color 200ms ease,
    transform 200ms ease;
}
```

### Partes da transição
- propriedade que será alterada;
- duração;
- função de aceleração;
- atraso opcional.

```css
transition: propriedade duracao aceleracao atraso;
```

Prefira listar as propriedades:

```css
transition:
  background-color 200ms ease,
  color 200ms ease,
  transform 200ms ease;
```

Evite usar `transition: all` sem necessidade, pois outras propriedades também podem ser animadas acidentalmente.

## 10) Transformações simples
`transform` modifica a representação visual sem reorganizar o fluxo normal da página.

### Deslocamento
```css
transform: translateY(-4px);
```

### Escala
```css
transform: scale(1.03);
```

### Rotação
```css
transform: rotate(2deg);
```

Para componentes de interface, mudanças pequenas costumam produzir resultados mais consistentes.

## 11) Evolução do portal do Encontro 22
Vamos transformar cada card em um componente com link funcional e resposta visual.

### Alteração no HTML dos cards
Substitua o conteúdo de cada card pelo padrão:

```html
<article class="card card-destaque">
  <h3>Trilha de estudos</h3>
  <p>Consulte a sequência recomendada de conteúdos e atividades da disciplina.</p>
  <a class="link-card" href="https://developer.mozilla.org/pt-BR/docs/Learn_web_development">
    Consultar trilha
  </a>
</article>
```

Exemplo para os demais cards:

```html
<article class="card">
  <h3>HTML5</h3>
  <p>Estrutura e semântica para organizar o conteúdo das páginas.</p>
  <a class="link-card" href="https://developer.mozilla.org/pt-BR/docs/Web/HTML">
    Estudar HTML
  </a>
</article>

<article class="card">
  <h3>CSS</h3>
  <p>Cores, tipografia, espaçamentos e identidade visual.</p>
  <a class="link-card" href="https://developer.mozilla.org/pt-BR/docs/Web/CSS">
    Estudar CSS
  </a>
</article>

<article class="card">
  <h3>Flexbox</h3>
  <p>Distribuição de elementos em uma linha ou coluna.</p>
  <a
    class="link-card"
    href="https://developer.mozilla.org/pt-BR/docs/Web/CSS/CSS_flexible_box_layout"
  >
    Revisar Flexbox
  </a>
</article>

<article class="card">
  <h3>CSS Grid</h3>
  <p>Organização bidimensional por linhas e colunas.</p>
  <a
    class="link-card"
    href="https://developer.mozilla.org/pt-BR/docs/Web/CSS/CSS_grid_layout"
  >
    Revisar Grid
  </a>
</article>

<article class="card">
  <h3>Formulários</h3>
  <p>Controles e validações nativas para entrada de dados.</p>
  <a
    class="link-card"
    href="https://developer.mozilla.org/pt-BR/docs/Learn_web_development/Extensions/Forms"
  >
    Revisar formulários
  </a>
</article>

```

## 12) CSS dos estados interativos
Acrescente ao `styles.css` do Encontro 22:

```css
.card {
  display: flex;
  flex-direction: column;
  transition:
    border-color 200ms ease,
    box-shadow 200ms ease,
    transform 200ms ease;
}

.card:hover {
  border-color: #60a5fa;
  box-shadow: 0 0.75rem 1.5rem #cbd5e1;
  transform: translateY(-0.25rem);
}

.card:focus-within {
  border-color: #2563eb;
  box-shadow: 0 0 0 4px #dbeafe;
}

.card h3::after {
  content: "";
  display: block;
  width: 3rem;
  height: 0.25rem;
  margin-top: 0.5rem;
  border-radius: 999px;
  background-color: #2563eb;
}

.link-card {
  align-self: flex-start;
  margin-top: auto;
  padding: 0.65rem 0.9rem;
  border-radius: 0.5rem;
  background-color: #0f3b66;
  color: #ffffff;
  font-weight: 700;
  text-decoration: none;
  transition:
    background-color 200ms ease,
    transform 100ms ease;
}

.link-card::after {
  content: " >";
}

.link-card:hover {
  background-color: #1d4ed8;
}

.link-card:focus-visible {
  outline: 3px solid #f59e0b;
  outline-offset: 3px;
}

.link-card:active {
  transform: translateY(2px);
}

.grade-cards .card:nth-child(even):not(.card-destaque) {
  background-color: #f8fafc;
}
```

## 13) Leitura técnica da solução
A regra:

```css
.card:hover
```

responde ao ponteiro e eleva visualmente o card.

A regra:

```css
.card:focus-within
```

destaca todo o card quando seu link interno recebe foco.

A regra:

```css
.link-card:active
```

simula o pressionamento do link.

O pseudoelemento:

```css
.link-card::after
```

adiciona um sinal visual sem modificar o HTML.

O seletor:

```css
.grade-cards .card:nth-child(even):not(.card-destaque)
```

seleciona cards pares, exceto o card de destaque.

## 14) Ordem recomendada dos estados
Quando vários estados modificam a mesma propriedade, a ordem das regras pode influenciar o resultado.

Uma sequência prática para links é:

```css
.link-card {
  /* estado padrão */
}

.link-card:hover {
  /* ponteiro */
}

.link-card:focus-visible {
  /* foco */
}

.link-card:active {
  /* acionamento */
}
```

O importante é testar cada estado e observar se uma regra posterior não apaga uma indicação necessária.

## 15) Exercício aplicado
Adicione estados interativos a uma página anterior.

### Requisitos
- usar `:hover` em links ou botões;
- usar `:focus-visible`;
- usar `:active`;
- usar `:focus-within` em pelo menos um componente;
- usar uma pseudoclasse estrutural;
- usar `::before` ou `::after`;
- criar uma transição com propriedades explícitas;
- aplicar uma transformação pequena;
- testar os estados no navegador.

### Desafio adicional
Crie um pequeno formulário contendo:
- um botão desabilitado;
- uma caixa de seleção;
- um campo obrigatório.

Depois aplique:

```css
button:disabled
input:checked
input:valid
input:invalid
```

## 16) Validação rápida antes de considerar concluído
- Elementos acionáveis possuem resposta em `:hover`.
- O foco pode ser percebido com `:focus-visible`.
- `:active` produz uma mudança curta durante o acionamento.
- O card responde quando um elemento interno recebe foco.
- Pseudoelementos não carregam informação indispensável.
- As transições listam apenas as propriedades necessárias.
- A transformação não desloca o restante do layout.
- Os links continuam funcionais.

## 17) Erros comuns
- aplicar `:hover` em elementos que parecem acionáveis, mas não são links ou botões;
- esconder o foco com `outline: none`;
- depender apenas de cor para representar todos os estados;
- usar `transition: all` em todos os componentes;
- exagerar em escala, rotação ou deslocamento;
- colocar texto essencial apenas em `content`;
- confundir pseudoclasse (`:`) com pseudoelemento (`::`);
- criar animação visual sem testar se o link ainda pode ser acionado.

## Materiais para Aprofundamento
- [MDN - Pseudoclasses](https://developer.mozilla.org/pt-BR/docs/Web/CSS/Pseudo-classes)
- [MDN - Pseudoelementos](https://developer.mozilla.org/pt-BR/docs/Web/CSS/Pseudo-elements)
- [MDN - `:hover`](https://developer.mozilla.org/pt-BR/docs/Web/CSS/:hover)
- [MDN - `:focus-visible`](https://developer.mozilla.org/pt-BR/docs/Web/CSS/:focus-visible)
- [MDN - `transition`](https://developer.mozilla.org/pt-BR/docs/Web/CSS/transition)
- [MDN - `transform`](https://developer.mozilla.org/pt-BR/docs/Web/CSS/transform)

## Checklist de Compreensão
- [ ] Consigo explicar o que uma pseudoclasse representa.
- [ ] Consigo diferenciar pseudoclasse de pseudoelemento.
- [ ] Consigo estilizar `:hover`, `:focus-visible` e `:active`.
- [ ] Consigo usar `:focus-within` em um componente.
- [ ] Consigo aplicar seletores como `:nth-child()` e `:not()`.
- [ ] Consigo criar transições curtas com propriedades explícitas.

## Resumo Final
Neste encontro, você fez a interface responder às ações do usuário usando recursos nativos do CSS.
Pseudoclasses representaram estados, pseudoelementos adicionaram acabamento visual e transições suavizaram mudanças entre estilos.

No próximo encontro, o estudo avança para posicionamento, empilhamento, `z-index` e controle de conteúdo excedente.

## Questões de Fixação
1. Qual é a diferença entre pseudoclasse e pseudoelemento?
<!-- Gabarito: A pseudoclasse representa um estado ou condição; o pseudoelemento seleciona ou cria uma parte visual do elemento. -->

2. Para que serve `:focus-within`?
<!-- Gabarito: Para selecionar um elemento quando ele próprio ou algum descendente está com foco. -->

3. Por que `transition: all` deve ser evitado como regra geral?
<!-- Gabarito: Porque pode animar propriedades não planejadas e dificultar o controle do comportamento. -->

4. O que `transform: translateY(-0.25rem)` faz?
<!-- Gabarito: Desloca visualmente o elemento para cima sem reorganizar o fluxo normal da página. -->

5. Por que informações essenciais não devem existir apenas em `::before` ou `::after`?
<!-- Gabarito: Porque pseudoelementos devem ser usados principalmente para apresentação e não substituem conteúdo estrutural do HTML. -->
