# Encontro 22 - CSS Grid: Linhas, Colunas, Áreas e Grades Responsivas

**Unidade:** Unidade 2  
**Entrega:** Layout com CSS Grid

## Visão Geral
Neste encontro, você aprende a organizar elementos em linhas e colunas com CSS Grid.
O foco é compreender o funcionamento de uma grade bidimensional e aplicá-la à página do portal acadêmico corrigida no Encontro 21.

Até agora, os cards foram distribuídos com Flexbox. Essa solução continua válida, mas o Grid oferece controle mais direto quando linhas e colunas precisam trabalhar juntas.

## Conceitos Essenciais
- Diferença entre layouts unidimensionais e bidimensionais.
- Contêiner Grid, itens Grid, linhas, colunas e espaços.
- Uso de `grid-template-columns`, `gap` e unidade `fr`.
- Funções `repeat()` e `minmax()`.
- Posicionamento com `grid-column`.
- Grades responsivas com media queries.
- Critérios para escolher entre Flexbox e Grid.

## 1) O que é CSS Grid?
CSS Grid é um modelo de layout que organiza elementos em duas dimensões:
- linhas;
- colunas.

Flexbox trabalha principalmente em uma direção por vez, enquanto Grid permite controlar as duas direções em conjunto.

Essa diferença torna o Grid especialmente útil para:
- galerias;
- painéis;
- áreas de cards;
- páginas com barra lateral;
- layouts com regiões bem definidas.

Grid não substitui Flexbox. Os dois modelos resolvem problemas diferentes e podem aparecer juntos na mesma página.

## 2) Laboratório inicial: HTML antes do Grid
Antes de estudar cada propriedade isoladamente, vamos criar um exemplo pequeno e observar sua evolução no navegador.

### Estrutura dos arquivos
```text
laboratorio-grid/
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
    <title>Laboratório de CSS Grid</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <main class="container">
      <h1>Laboratório de CSS Grid</h1>

      <section class="grade">
        <article class="item item-destaque">Item 1</article>
        <article class="item">Item 2</article>
        <article class="item">Item 3</article>
        <article class="item">Item 4</article>
        <article class="item">Item 5</article>
        <article class="item">Item 6</article>
      </section>
    </main>
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
  margin: 0;
  background-color: #e8eef9;
  color: #1f2937;
  font-family: Arial, Helvetica, sans-serif;
}

.container {
  width: 92%;
  max-width: 60rem;
  margin: 2rem auto;
}

.item {
  padding: 2rem;
  border: 2px solid #93c5fd;
  border-radius: 0.75rem;
  background-color: #eff6ff;
  color: #0f3b66;
  font-size: 1.25rem;
  font-weight: 700;
  text-align: center;
}

.item-destaque {
  border-color: #f59e0b;
  background-color: #fffbeb;
}
```

### Resultado antes do Grid
Abra o `index.html` no navegador.

Neste momento:
- os seis itens aparecem um abaixo do outro;
- cada `article` ocupa a largura disponível;
- ainda não existe uma grade;
- os itens ficam encostados porque nenhum espaçamento foi definido entre eles.

Esse é o comportamento normal dos elementos de bloco no fluxo do documento.

## 3) Primeiro passo: transformar o contêiner em Grid
Acrescente a primeira regra de Grid:

```css
.grade {
  display: grid;
}
```

### O que muda no navegador?
Visualmente, os itens ainda aparecem em uma única coluna.

A mudança importante está no modelo de layout:
- `.grade` se torna o **contêiner Grid**;
- seus seis filhos diretos se tornam **itens Grid**;
- o navegador cria uma coluna automática para acomodar os itens.

O Grid foi ativado, mas ainda não informamos quantas colunas desejamos.

## 4) Criando colunas com `grid-template-columns`
Agora evolua a mesma regra:

```css
.grade {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
}
```

### Resultado esperado
Os seis itens passam a formar:
- três colunas;
- duas linhas;
- colunas com a mesma largura.

`grid-template-columns` define as colunas da grade.

A unidade `fr` representa uma fração do espaço disponível. Como usamos três vezes `1fr`, cada coluna recebe uma parte igual.

### Teste de proporções diferentes
Troque temporariamente a declaração por:

```css
grid-template-columns: 2fr 1fr 1fr;
```

Agora:
- a primeira coluna recebe duas partes do espaço;
- a segunda recebe uma parte;
- a terceira recebe uma parte.

Depois do teste, retorne às três colunas iguais.

## 5) Criando espaço entre os itens com `gap`
Os itens já formam linhas e colunas, mas continuam encostados.

Acrescente:

```css
.grade {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 1rem;
}
```

### Resultado esperado
Surge um espaço uniforme:
- entre as colunas;
- entre as linhas.

`gap` pertence ao contêiner e evita criar margens separadas em cada item.

## 6) Reduzindo repetição com `repeat()`
As três colunas usam o mesmo valor. Podemos reescrever a regra:

```css
.grade {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
}
```

Essa declaração equivale a:

```css
grid-template-columns: 1fr 1fr 1fr;
```

O resultado visual não muda. `repeat()` apenas torna a regra mais curta e facilita futuras alterações.

## 7) Fazendo um item ocupar toda a linha
Vamos usar a classe `item-destaque`, que já está no primeiro item.

Acrescente:

```css
.item-destaque {
  grid-column: 1 / -1;
}
```

### Resultado esperado
O Item 1 passa a ocupar toda a primeira linha. Os demais continuam distribuídos nas colunas seguintes.

Na declaração:
- `1` representa a primeira linha vertical da grade;
- `-1` representa a última linha vertical;
- o item atravessa todas as colunas existentes.

Outra possibilidade seria:

```css
.item-destaque {
  grid-column: span 2;
}
```

Nesse caso, o item ocuparia apenas duas colunas.

## 8) Tornando o laboratório responsivo
Três colunas podem ficar estreitas em telas pequenas. Vamos partir de uma coluna e aumentar a grade conforme houver espaço.

Substitua a regra da grade por:

```css
.grade {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1rem;
}

@media (min-width: 40rem) {
  .grade {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }
}

@media (min-width: 60rem) {
  .grade {
    grid-template-columns: repeat(3, minmax(0, 1fr));
  }
}
```

### Teste no navegador
Redimensione a janela e observe:
- tela estreita: uma coluna;
- a partir de `40rem`: duas colunas;
- a partir de `60rem`: três colunas.

O item de destaque continua ocupando toda a linha porque mantém:

```css
grid-column: 1 / -1;
```

`minmax(0, 1fr)` permite que cada coluna use uma fração do espaço e encolha sem ser forçada pelo tamanho mínimo automático do conteúdo.

## 9) Grade automática com `auto-fit` e `minmax()`
Também é possível deixar o navegador calcular quantas colunas cabem:

```css
.grade {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(14rem, 1fr));
  gap: 1rem;
}
```

Nesse caso:
- `auto-fit` cria a quantidade de colunas que cabe no contêiner;
- `14rem` é a largura mínima de cada coluna;
- `1fr` permite que as colunas cresçam e preencham o espaço.

Compare essa versão com a solução baseada em media queries.

Use media queries quando quiser controlar exatamente quando a quantidade de colunas muda. Use `auto-fit` com `minmax()` quando quiser uma grade mais automática.

## 10) Criando regiões com `grid-template-areas`
O Grid também pode nomear regiões de uma página:

```css
.pagina {
  display: grid;
  grid-template-areas:
    "topo topo"
    "menu conteudo"
    "rodape rodape";
  grid-template-columns: 14rem 1fr;
}

.topo {
  grid-area: topo;
}

.menu {
  grid-area: menu;
}

.conteudo {
  grid-area: conteudo;
}

.rodape {
  grid-area: rodape;
}
```

As áreas ajudam a visualizar o layout como um mapa. Elas são úteis quando a página possui regiões estáveis e claramente identificadas.

Para o laboratório e a grade de cards deste encontro, `grid-template-columns` é suficiente.

## 11) Evolução do portal acadêmico
Vamos manter a estrutura visual do Encontro 21 e substituir a distribuição dos cards com Flexbox por CSS Grid.

### Estrutura dos arquivos
```text
portal-grid/
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
    <title>Portal Acadêmico - CSS Grid</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <header class="cabecalho">
      <div class="container">
        <h1>Portal Acadêmico da Turma</h1>
        <p>Conteúdos e serviços organizados com CSS Grid.</p>
      </div>
    </header>

    <main class="container">
      <section class="painel" aria-labelledby="titulo-recursos">
        <h2 id="titulo-recursos">Recursos do portal</h2>

        <div class="grade-cards">
          <article class="card card-destaque">
            <h3>Trilha de estudos</h3>
            <p>Consulte a sequência recomendada de conteúdos e atividades da disciplina.</p>
          </article>

          <article class="card">
            <h3>HTML5</h3>
            <p>Estrutura e semântica para organizar o conteúdo das páginas.</p>
          </article>

          <article class="card">
            <h3>CSS</h3>
            <p>Cores, tipografia, espaçamentos e identidade visual.</p>
          </article>

          <article class="card">
            <h3>Flexbox</h3>
            <p>Distribuição de elementos em uma linha ou coluna.</p>
          </article>

          <article class="card">
            <h3>CSS Grid</h3>
            <p>Organização bidimensional por linhas e colunas.</p>
          </article>

          <article class="card">
            <h3>Atividades</h3>
            <p>Exercícios práticos para consolidar os conteúdos estudados.</p>
          </article>
        </div>
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

### `styles.css`
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
  margin-bottom: 0;
}

.card-destaque {
  border-color: #f59e0b;
  background-color: #fffbeb;
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

## 12) Leitura técnica da solução
Na versão móvel:

```css
.grade-cards {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1rem;
}
```

A grade possui uma coluna.

Em telas médias:

```css
grid-template-columns: repeat(2, minmax(0, 1fr));
```

A grade passa a ter duas colunas de mesmo tamanho.

Em telas largas:

```css
grid-template-columns: repeat(3, minmax(0, 1fr));
```

A grade passa a ter três colunas.

O card de destaque ocupa a largura completa:

```css
.card-destaque {
  grid-column: 1 / -1;
}
```

## 13) Quando usar Flexbox ou Grid?
Use Flexbox quando:
- o problema principal ocorre em uma direção;
- os elementos precisam se alinhar em linha ou coluna;
- o tamanho do conteúdo deve influenciar fortemente a distribuição.

Use Grid quando:
- linhas e colunas precisam ser controladas juntas;
- os elementos devem compartilhar faixas alinhadas;
- existe uma grade, galeria ou composição bidimensional.

Exemplo de uso conjunto:
- Grid organiza os cards da página;
- Flexbox organiza ícone, texto e botão dentro de cada card.

## 14) Exercício aplicado
Evolua uma página criada anteriormente para usar CSS Grid.

### Requisitos
- criar um contêiner com `display: grid`;
- iniciar com uma coluna;
- usar `gap`;
- criar duas colunas em uma media query;
- criar três colunas em uma segunda media query;
- usar `repeat()` e `minmax()`;
- fazer pelo menos um item ocupar mais de uma coluna;
- manter o conteúdo legível em tela estreita.

### Desafio adicional
Crie uma segunda versão sem media queries:

```css
grid-template-columns: repeat(auto-fit, minmax(16rem, 1fr));
```

Compare as duas abordagens e registre qual delas oferece maior controle sobre a mudança do layout.

## 15) Validação rápida antes de considerar concluído
- O `display: grid` está no contêiner, não nos cards.
- Os cards são filhos diretos da grade.
- `gap` controla o espaço entre os itens.
- A versão móvel possui uma coluna.
- As media queries alteram a quantidade de colunas.
- `grid-column` faz o item de destaque ocupar a largura esperada.
- Não existe estouro horizontal em telas estreitas.
- O Grid foi escolhido por uma necessidade bidimensional.

## 16) Erros comuns
- aplicar `display: grid` em cada item;
- usar `grid-template-columns` sem transformar o elemento em Grid;
- definir muitas colunas fixas e causar estouro horizontal;
- esquecer `gap` e voltar a criar margens individuais;
- usar `grid-column` sem observar a quantidade de colunas;
- tentar resolver todo alinhamento interno com Grid quando Flexbox seria mais simples;
- escolher pontos de quebra sem testar o conteúdo.

## Materiais para Aprofundamento
- [MDN - Conceitos básicos de CSS Grid](https://developer.mozilla.org/pt-BR/docs/Web/CSS/CSS_grid_layout/Basic_concepts_of_grid_layout)
- [MDN - `grid-template-columns`](https://developer.mozilla.org/pt-BR/docs/Web/CSS/grid-template-columns)
- [MDN - `repeat()`](https://developer.mozilla.org/pt-BR/docs/Web/CSS/repeat)
- [MDN - `minmax()`](https://developer.mozilla.org/pt-BR/docs/Web/CSS/minmax)
- [MDN - `grid-column`](https://developer.mozilla.org/pt-BR/docs/Web/CSS/grid-column)

## Checklist de Compreensão
- [ ] Consigo explicar a diferença entre Flexbox e Grid.
- [ ] Consigo identificar contêiner e itens Grid.
- [ ] Consigo criar colunas com `fr`, `repeat()` e `minmax()`.
- [ ] Consigo alterar a grade com media queries.
- [ ] Consigo fazer um item ocupar mais de uma coluna.
- [ ] Consigo escolher Grid quando o layout exige linhas e colunas.

## Resumo Final
Neste encontro, você transformou a área de cards do portal acadêmico em uma grade bidimensional.
O CSS Grid permitiu controlar colunas, espaços e expansão dos itens de forma mais explícita, mantendo uma estratégia mobile-first.

No próximo encontro, essa interface ganhará estados visuais, pseudoclasses, pseudoelementos e transições.

## Questões de Fixação
1. Qual é a principal diferença entre Flexbox e CSS Grid?
<!-- Gabarito: Flexbox é principalmente unidimensional; Grid controla linhas e colunas ao mesmo tempo. -->

2. Em qual elemento deve ser aplicado `display: grid`?
<!-- Gabarito: No elemento contêiner que possui os itens que serão organizados pela grade. -->

3. O que a unidade `fr` representa?
<!-- Gabarito: Uma fração do espaço disponível no contêiner Grid. -->

4. Para que servem `repeat()` e `minmax()`?
<!-- Gabarito: repeat reduz repetição na definição das faixas; minmax estabelece limites mínimo e máximo para uma faixa. -->

5. O que significa `grid-column: 1 / -1`?
<!-- Gabarito: O item começa na primeira linha vertical e termina na última, ocupando toda a largura da grade. -->
