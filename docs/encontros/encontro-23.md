# Encontro 23 - Pseudoclasses, Pseudoelementos, Estados Interativos e Transições

**Unidade:** Unidade 2  
**Entrega:** Interface interativa

## Visão Geral
Neste encontro, você adiciona respostas visuais aos componentes de uma página.
O foco é aplicar pseudoclasses, pseudoelementos, transições e pequenas transformações em elementos HTML reais, observando o efeito no navegador a cada etapa.

Se no Encontro 22 você organizou o portal acadêmico com CSS Grid, agora os cards, links e controles passam a comunicar estados como ponteiro, foco, acionamento, seleção e validação.

## Conceitos Essenciais
- Diferença entre estado padrão e estado interativo.
- Pseudoclasses `:hover`, `:focus-visible`, `:active` e `:focus-within`.
- Pseudoclasses estruturais `:nth-child()` e `:not()`.
- Estados nativos de controles com `:checked`, `:disabled`, `:valid` e `:invalid`.
- Pseudoelementos `::before` e `::after`.
- Transições com propriedades explícitas.
- Transformações pequenas com `transform`.

## 1) O que são estados visuais?
Um mesmo elemento pode ter aparências diferentes conforme a situação.

Exemplos:
- um link em repouso;
- o mesmo link sob o ponteiro;
- o link selecionado pelo teclado;
- um botão pressionado;
- um campo obrigatório inválido;
- uma caixa de seleção marcada.

O CSS representa essas situações com pseudoclasses:

```css
seletor:pseudoclasse {
  propriedade: valor;
}
```

Exemplo aplicado a um link:

```css
.link-card:hover {
  background-color: #1d4ed8;
}
```

Nesse caso, `.link-card` é o elemento da página e `:hover` representa o estado em que o ponteiro está sobre ele.

## 2) Laboratório inicial: página antes dos estados
Vamos criar uma página pequena de portal acadêmico e evoluir seus componentes.

### Estrutura dos arquivos
```text
portal-interativo/
  index.html
  styles.css
```

### `index.html`
```html
<!doctype html>
<html lang="pt-BR">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Portal Acadêmico - Estados Interativos</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <header class="cabecalho">
      <div class="container">
        <h1>Portal Acadêmico da Turma</h1>
        <p>Recursos organizados com Grid e estados interativos em CSS.</p>
      </div>
    </header>

    <main class="container">
      <section class="painel" aria-labelledby="titulo-recursos">
        <h2 id="titulo-recursos">Recursos do portal</h2>

        <div class="grade-cards">
          <article class="card card-destaque">
            <h3>Trilha de estudos</h3>
            <p>Consulte a sequência recomendada de conteúdos e atividades da disciplina.</p>
            <a class="link-card" href="https://developer.mozilla.org/pt-BR/docs/Learn_web_development">
              Consultar trilha
            </a>
          </article>

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
            <a class="link-card" href="https://developer.mozilla.org/pt-BR/docs/Web/CSS/CSS_flexible_box_layout">
              Revisar Flexbox
            </a>
          </article>

          <article class="card">
            <h3>CSS Grid</h3>
            <p>Organização bidimensional por linhas e colunas.</p>
            <a class="link-card" href="https://developer.mozilla.org/pt-BR/docs/Web/CSS/CSS_grid_layout">
              Revisar Grid
            </a>
          </article>

          <article class="card">
            <h3>Formulários</h3>
            <p>Controles e validações nativas para entrada de dados.</p>
            <a class="link-card" href="https://developer.mozilla.org/pt-BR/docs/Learn_web_development/Extensions/Forms">
              Revisar formulários
            </a>
          </article>
        </div>
      </section>

      <section class="painel" aria-labelledby="titulo-preferencias">
        <h2 id="titulo-preferencias">Preferências de estudo</h2>

        <form class="formulario">
          <label class="campo" for="email">
            <span>E-mail institucional</span>
            <input id="email" name="email" type="email" placeholder="nome@ifrn.edu.br" required />
          </label>

          <label class="opcao" for="receber-alertas">
            <input id="receber-alertas" name="alertas" type="checkbox" />
            <span>Receber alertas de novos materiais</span>
          </label>

          <button class="botao" type="submit">Salvar preferências</button>
          <button class="botao botao-secundario" type="button" disabled>Exportar relatório</button>
        </form>
      </section>
    </main>

    <footer class="rodape">
      <div class="container">
        <p>Disciplina de Padrões Web - IFRN Campus Currais Novos</p>
      </div>
    </footer>
  </body>
</html>
```

### CSS visual inicial
Crie o arquivo `styles.css`:

```css
* {
  box-sizing: border-box;
}

body {
  min-height: 100vh;
  margin: 0;
  background-color: #e8eef9;
  color: #1f2937;
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.5;
}

h1,
h2,
h3,
p {
  margin-top: 0;
}

.container {
  width: 92%;
  max-width: 75rem;
  margin: 0 auto;
}

.cabecalho {
  padding: 2rem 0;
  background-color: #0f3b66;
  color: #ffffff;
  text-align: center;
}

.cabecalho h1 {
  margin-bottom: 0.5rem;
  font-size: clamp(2rem, 4vw, 3rem);
}

.cabecalho p,
.rodape p {
  margin-bottom: 0;
}

.painel {
  margin: 2rem 0;
  padding: 1.5rem;
  border: 2px solid #c8d5eb;
  border-radius: 1rem;
  background-color: #ffffff;
}

.painel > h2 {
  margin-bottom: 1.5rem;
  color: #0f3b66;
  text-align: center;
}

.grade-cards {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1rem;
}

.card {
  padding: 1.25rem;
  border: 2px solid #bfdbfe;
  border-radius: 0.875rem;
  background-color: #eff6ff;
}

.card h3 {
  margin-bottom: 0.75rem;
  color: #0f3b66;
}

.card p {
  margin-bottom: 1rem;
}

.card-destaque {
  border-color: #f59e0b;
  background-color: #fffbeb;
}

.link-card,
.botao {
  display: inline-block;
  padding: 0.65rem 0.9rem;
  border: 0;
  border-radius: 0.5rem;
  background-color: #0f3b66;
  color: #ffffff;
  font: inherit;
  font-weight: 700;
  text-decoration: none;
  cursor: pointer;
}

.formulario {
  display: grid;
  gap: 1rem;
}

.campo,
.opcao {
  display: grid;
  gap: 0.4rem;
}

.campo input {
  width: 100%;
  padding: 0.75rem;
  border: 2px solid #cbd5e1;
  border-radius: 0.5rem;
  font: inherit;
}

.opcao {
  grid-template-columns: auto 1fr;
  align-items: center;
}

.botao-secundario {
  background-color: #475569;
}

.rodape {
  padding: 1.5rem 0;
  background-color: #1f2937;
  color: #ffffff;
  text-align: center;
}

@media (min-width: 48rem) {
  .grade-cards {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }

  .card-destaque {
    grid-column: 1 / -1;
  }
}

@media (min-width: 70rem) {
  .grade-cards {
    grid-template-columns: repeat(3, minmax(0, 1fr));
  }
}
```

### Resultado antes das pseudoclasses
Abra o `index.html` no navegador.

Neste momento:
- os cards já estão organizados com Grid;
- links e botões têm aparência de ação;
- os componentes ainda não respondem visualmente ao ponteiro, foco ou acionamento;
- o formulário ainda usa validação nativa, mas sem acabamento visual específico.

## 3) Estado `:hover` aplicado aos links dos cards
`:hover` seleciona um elemento quando o ponteiro está sobre ele.

O HTML que receberá o estado é o link dentro do card:

```html
<a class="link-card" href="https://developer.mozilla.org/pt-BR/docs/Web/CSS">
  Estudar CSS
</a>
```

Acrescente ao CSS:

```css
.link-card:hover {
  background-color: #1d4ed8;
}
```

### Resultado esperado
Ao passar o ponteiro sobre o link:
- a cor de fundo muda;
- o usuário percebe que o elemento é acionável;
- o HTML não precisa ser alterado.

### Cuidado
Celulares e tablets nem sempre possuem ponteiro. A interface pode usar `:hover` como reforço, mas informações essenciais não devem depender apenas dele.

## 4) Estado `:focus-visible` aplicado aos links e botões
`:focus-visible` aparece quando o navegador entende que o indicador de foco deve ser mostrado, especialmente durante a navegação por teclado.

O mesmo link pode receber foco com a tecla `Tab`:

```html
<a class="link-card" href="https://developer.mozilla.org/pt-BR/docs/Web/HTML">
  Estudar HTML
</a>
```

Acrescente:

```css
.link-card:focus-visible,
.botao:focus-visible {
  outline: 3px solid #f59e0b;
  outline-offset: 3px;
}
```

### Resultado esperado
Ao navegar com `Tab`:
- o elemento focado ganha um contorno visível;
- links e botões podem ser identificados sem mouse;
- o `outline` aparece fora do elemento e não reorganiza o layout.

Evite remover o foco sem oferecer alternativa:

```css
/* Evite esta regra isolada */
*:focus {
  outline: none;
}
```

## 5) Estado `:active` aplicado ao acionamento
`:active` representa o instante em que o elemento está sendo pressionado.

O elemento de exemplo é o botão do formulário:

```html
<button class="botao" type="submit">Salvar preferências</button>
```

Acrescente:

```css
.link-card:active,
.botao:active {
  transform: translateY(2px);
}
```

### Resultado esperado
Durante o clique ou toque:
- o elemento desce levemente;
- a ação parece mais física;
- o deslocamento é visual e não muda a posição dos demais elementos.

## 6) Transições para suavizar mudanças
Sem transição, a mudança de cor e o deslocamento acontecem imediatamente.

Vamos aplicar transição aos próprios elementos interativos:

```html
<a class="link-card" href="https://developer.mozilla.org/pt-BR/docs/Web/CSS">
  Estudar CSS
</a>

<button class="botao" type="submit">Salvar preferências</button>
```

Atualize a regra compartilhada:

```css
.link-card,
.botao {
  display: inline-block;
  padding: 0.65rem 0.9rem;
  border: 0;
  border-radius: 0.5rem;
  background-color: #0f3b66;
  color: #ffffff;
  font: inherit;
  font-weight: 700;
  text-decoration: none;
  cursor: pointer;
  transition:
    background-color 200ms ease,
    color 200ms ease,
    transform 100ms ease;
}
```

### Resultado esperado
Agora:
- a troca de cor acontece de forma gradual;
- o deslocamento de `:active` também fica mais controlado;
- apenas as propriedades planejadas são animadas.

Prefira listar propriedades específicas. Evite usar `transition: all` como solução automática.

## 7) `:focus-within` aplicado ao card inteiro
`:focus-within` seleciona um elemento quando ele próprio ou algum descendente está com foco.

O HTML de referência é um card que contém um link:

```html
<article class="card">
  <h3>CSS Grid</h3>
  <p>Organização bidimensional por linhas e colunas.</p>
  <a class="link-card" href="https://developer.mozilla.org/pt-BR/docs/Web/CSS/CSS_grid_layout">
    Revisar Grid
  </a>
</article>
```

Acrescente:

```css
.card:focus-within {
  border-color: #2563eb;
  box-shadow: 0 0 0 4px #dbeafe;
}
```

### Resultado esperado
Quando o link interno recebe foco:
- o card inteiro fica destacado;
- o usuário entende qual componente está ativo;
- não foi necessário adicionar uma classe extra ao card.

## 8) `:hover` e `transform` aplicados ao card
Além do link, o card pode responder ao ponteiro como componente.

HTML de referência:

```html
<article class="card">
  <h3>Flexbox</h3>
  <p>Distribuição de elementos em uma linha ou coluna.</p>
  <a class="link-card" href="https://developer.mozilla.org/pt-BR/docs/Web/CSS/CSS_flexible_box_layout">
    Revisar Flexbox
  </a>
</article>
```

Atualize a regra `.card`:

```css
.card {
  display: flex;
  flex-direction: column;
  padding: 1.25rem;
  border: 2px solid #bfdbfe;
  border-radius: 0.875rem;
  background-color: #eff6ff;
  transition:
    border-color 200ms ease,
    box-shadow 200ms ease,
    transform 200ms ease;
}
```

Depois acrescente:

```css
.card:hover {
  border-color: #60a5fa;
  box-shadow: 0 0.75rem 1.5rem #cbd5e1;
  transform: translateY(-0.25rem);
}
```

### Resultado esperado
Ao passar o ponteiro sobre o card:
- a borda muda;
- a sombra aumenta;
- o card sobe levemente;
- os demais cards permanecem no mesmo lugar.

`transform` modifica a representação visual, mas não reorganiza o fluxo normal do documento.

## 9) Pseudoelemento `::after` aplicado ao título do card
Pseudoelementos criam uma parte visual antes ou depois do conteúdo de um elemento.

O elemento de referência é o título dentro do card:

```html
<h3>Trilha de estudos</h3>
```

Acrescente:

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

### Resultado esperado
Cada título recebe uma pequena linha decorativa abaixo do texto.

Essa linha não existe no HTML porque é apenas acabamento visual.

## 10) Pseudoelemento `::after` aplicado ao link
Também podemos adicionar um marcador simples ao final de cada link.

HTML de referência:

```html
<a class="link-card" href="https://developer.mozilla.org/pt-BR/docs/Web/CSS">
  Estudar CSS
</a>
```

Acrescente:

```css
.link-card::after {
  content: " >";
}
```

### Resultado esperado
O texto do link passa a exibir um sinal visual ao final.

Use `::before` e `::after` para acabamento ou complemento simples.
Informações indispensáveis devem permanecer no HTML.

## 11) Pseudoclasses estruturais aplicadas à grade
Pseudoclasses estruturais selecionam elementos pela posição ou relação com outros elementos.

O trecho HTML de referência é a grade de cards:

```html
<div class="grade-cards">
  <article class="card card-destaque">...</article>
  <article class="card">...</article>
  <article class="card">...</article>
  <article class="card">...</article>
</div>
```

Acrescente:

```css
.grade-cards .card:nth-child(even):not(.card-destaque) {
  background-color: #f8fafc;
}
```

### Resultado esperado
Cards em posição par recebem uma cor mais clara, exceto o card de destaque.

Na regra:
- `:nth-child(even)` seleciona elementos pares;
- `:not(.card-destaque)` exclui o card destacado;
- não foi necessário criar classes como `.card-par`.

## 12) Estado `:checked` aplicado à opção do formulário
Controles de formulário também possuem estados nativos.

O HTML de referência é a caixa de seleção:

```html
<label class="opcao" for="receber-alertas">
  <input id="receber-alertas" name="alertas" type="checkbox" />
  <span>Receber alertas de novos materiais</span>
</label>
```

Acrescente:

```css
.opcao input:checked + span {
  color: #0f3b66;
  font-weight: 700;
}
```

### Resultado esperado
Quando a caixa é marcada:
- o texto ao lado muda de peso;
- a relação entre `input` e `span` é usada pelo seletor de irmão adjacente `+`;
- o estado vem do próprio controle, sem JavaScript.

## 13) Estados `:valid` e `:invalid` aplicados ao campo
Campos com restrições HTML podem ser estilizados conforme sua validade.

O HTML de referência é o campo de e-mail:

```html
<input id="email" name="email" type="email" placeholder="nome@ifrn.edu.br" required />
```

Acrescente:

```css
.campo input:valid {
  border-color: #15803d;
}

.campo input:not(:placeholder-shown):invalid {
  border-color: #b91c1c;
}
```

### Resultado esperado
No campo de e-mail:
- um e-mail válido deixa a borda verde;
- um valor inválido deixa a borda vermelha;
- o seletor `:not(:placeholder-shown)` evita mostrar erro antes de o usuário digitar.

Esses estados serão aprofundados no Encontro 25.

## 14) Estado `:disabled` aplicado ao botão
Um controle desabilitado não pode ser acionado.

O HTML de referência é o botão secundário:

```html
<button class="botao botao-secundario" type="button" disabled>
  Exportar relatório
</button>
```

Acrescente:

```css
.botao:disabled {
  cursor: not-allowed;
  opacity: 0.55;
}
```

### Resultado esperado
O botão desabilitado:
- fica visualmente menos forte;
- troca o cursor;
- não dispara ação quando clicado.

## 15) Ordem recomendada dos estados
Quando vários estados alteram propriedades parecidas, a ordem das regras influencia o resultado.

Uma sequência prática para links e botões é:

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

O importante é testar cada estado:
- com mouse;
- com teclado;
- com clique ou toque;
- com controles válidos, inválidos, marcados e desabilitados.

## 16) Exercício aplicado
Evolua uma página criada anteriormente para incluir estados interativos.

### Requisitos
- aplicar `:hover` em links ou botões;
- aplicar `:focus-visible` em elementos acionáveis;
- aplicar `:active` em pelo menos um botão ou link;
- aplicar `:focus-within` em um card, campo ou grupo;
- usar `:nth-child()` ou `:not()` em uma lista ou grade;
- usar `::before` ou `::after` como acabamento visual;
- criar transições com propriedades explícitas;
- aplicar uma transformação pequena com `transform`;
- testar o resultado com mouse e teclado.

### Desafio adicional
Inclua um pequeno formulário com:
- um campo obrigatório;
- uma caixa de seleção;
- um botão desabilitado.

Depois aplique:

```css
input:checked
input:valid
input:invalid
button:disabled
```

## 17) Validação rápida antes de considerar concluído
- Elementos acionáveis possuem resposta em `:hover`.
- O foco pode ser percebido com `:focus-visible`.
- `:active` produz uma mudança curta durante o acionamento.
- O card responde quando um elemento interno recebe foco.
- Pseudoelementos não carregam informação indispensável.
- As transições listam apenas as propriedades necessárias.
- A transformação não desloca o restante do layout.
- Os estados de formulário são testados com valores reais.
- Os links continuam funcionais.

## 18) Erros comuns
- aplicar `:hover` em elementos que parecem botões, mas não são links ou botões;
- esconder o foco com `outline: none`;
- depender apenas de cor para representar todos os estados;
- usar `transition: all` em todos os componentes;
- exagerar em escala, rotação ou deslocamento;
- colocar texto essencial apenas em `content`;
- confundir pseudoclasse (`:`) com pseudoelemento (`::`);
- esquecer que `:valid` e `:invalid` dependem dos atributos do HTML.

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
- [ ] Consigo usar estados nativos de formulário.
- [ ] Consigo criar transições curtas com propriedades explícitas.

## Resumo Final
Neste encontro, você transformou uma página estática em uma interface mais comunicativa.
Pseudoclasses representaram estados, pseudoelementos adicionaram acabamento visual e transições suavizaram mudanças entre estilos.

No próximo encontro, o foco passa para Git e GitHub, com criação de repositório, commits, branches, pull e push.

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
