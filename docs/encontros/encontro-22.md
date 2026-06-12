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

## 1) Por que estudar CSS Grid?
Flexbox organiza elementos principalmente em uma direção:
- linha; ou
- coluna.

CSS Grid organiza elementos em duas direções ao mesmo tempo:
- linhas;
- colunas.

Essa diferença torna o Grid especialmente útil para:
- galerias;
- painéis;
- áreas de cards;
- páginas com barra lateral;
- layouts com regiões bem definidas.

### Comparação inicial
```css
/* Flexbox: distribuição em uma direção */
.lista {
  display: flex;
  flex-wrap: wrap;
}

/* Grid: definição explícita de colunas */
.lista {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
}
```

Grid não substitui Flexbox. Os dois modelos resolvem problemas diferentes e podem aparecer juntos na mesma página.

## 2) Vocabulário básico do Grid
Considere o exemplo:

```css
.grade {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 1rem;
}
```

- `.grade` é o **contêiner Grid**.
- Os filhos diretos de `.grade` são os **itens Grid**.
- `grid-template-columns` define as colunas.
- Cada `1fr` representa uma fração do espaço disponível.
- `gap` cria espaço entre linhas e colunas.

### Exemplo de HTML
```html
<section class="grade">
  <article>Card 1</article>
  <article>Card 2</article>
  <article>Card 3</article>
</section>
```

Não é necessário adicionar uma classe especial a cada item para que ele participe da grade. Os filhos diretos do contêiner já se tornam itens Grid.

## 3) Criando colunas com `fr`
A unidade `fr` distribui o espaço disponível entre as colunas.

### Três colunas iguais
```css
.grade {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
}
```

### Coluna principal maior
```css
.layout {
  display: grid;
  grid-template-columns: 2fr 1fr;
}
```

Nesse segundo exemplo, a primeira coluna recebe duas partes do espaço e a segunda recebe uma parte.

## 4) Evitando repetição com `repeat()`
Quando as colunas usam a mesma medida, `repeat()` deixa a regra mais curta.

```css
.grade {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
}
```

Essa declaração equivale a:

```css
.grade {
  grid-template-columns: 1fr 1fr 1fr;
}
```

## 5) Controlando limites com `minmax()`
`minmax()` permite definir um valor mínimo e um valor máximo para uma faixa da grade.

```css
.grade {
  grid-template-columns: repeat(3, minmax(0, 1fr));
}
```

Nesse caso:
- `0` permite que a coluna encolha sem ser forçada pelo tamanho mínimo automático do conteúdo;
- `1fr` permite que ela cresça e ocupe uma fração do espaço disponível.

Também é possível criar colunas automáticas:

```css
.grade-automatica {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(16rem, 1fr));
  gap: 1rem;
}
```

- `auto-fit` cria apenas a quantidade de colunas que cabe no contêiner;
- `minmax(16rem, 1fr)` impede que cada coluna fique menor que `16rem`;
- `1fr` permite que as colunas cresçam quando houver espaço.

Essa forma é poderosa, mas neste encontro a prática principal usará media queries para tornar as mudanças de coluna mais visíveis.

## 6) Fazendo um item ocupar mais colunas
Um item pode atravessar mais de uma coluna:

```css
.card-destaque {
  grid-column: 1 / -1;
}
```

- `1` indica a primeira linha vertical da grade;
- `-1` indica a última linha vertical;
- o item ocupa toda a largura disponível.

Outra possibilidade:

```css
.card-duplo {
  grid-column: span 2;
}
```

Nesse caso, o item ocupa duas colunas a partir de sua posição atual.

## 7) Criando regiões com `grid-template-areas`
O Grid também pode nomear regiões da página:

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

Para a grade de cards deste encontro, `grid-template-columns` é suficiente.

## 8) Grid responsivo com media queries
A abordagem continua mobile-first:
- uma coluna em telas estreitas;
- duas colunas quando houver mais espaço;
- três colunas em telas largas.

```css
.grade {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1rem;
}

@media (min-width: 48rem) {
  .grade {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }
}

@media (min-width: 70rem) {
  .grade {
    grid-template-columns: repeat(3, minmax(0, 1fr));
  }
}
```

O ponto de quebra deve responder ao conteúdo, não a um modelo específico de celular ou computador.

## 9) Evolução do portal acadêmico
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

## 10) Leitura técnica da solução
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

## 11) Quando usar Flexbox ou Grid?
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

## 12) Exercício aplicado
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

## 13) Validação rápida antes de considerar concluído
- O `display: grid` está no contêiner, não nos cards.
- Os cards são filhos diretos da grade.
- `gap` controla o espaço entre os itens.
- A versão móvel possui uma coluna.
- As media queries alteram a quantidade de colunas.
- `grid-column` faz o item de destaque ocupar a largura esperada.
- Não existe estouro horizontal em telas estreitas.
- O Grid foi escolhido por uma necessidade bidimensional.

## 14) Erros comuns
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
