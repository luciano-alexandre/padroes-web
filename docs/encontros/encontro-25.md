# Encontro 25 - Frameworks HTML/CSS e Bootstrap: CDN, Containers, Grid e Utilitários

**Unidade:** Unidade 2  
**Entrega:** Página inicial com Bootstrap construída passo a passo

## Visão Geral
Neste encontro, você inicia o estudo de Bootstrap dentro de um fluxo profissional de projeto.
O objetivo é entender o papel de um framework HTML/CSS, configurar Bootstrap por CDN e construir uma página responsiva de forma incremental.

Em vez de copiar uma página pronta, você vai montar a interface por etapas.
Cada etapa apresenta um recurso central do Bootstrap, mostra o trecho que deve ser adicionado e explica por que aquelas classes foram usadas.

Se no Encontro 24 você organizou o versionamento com Git e GitHub, agora esse repositório passa a receber uma primeira interface feita com Bootstrap.
Cada avanço relevante deve gerar um commit pequeno e bem nomeado.

Ao final da aula, você deverá ter:
- uma página HTML usando Bootstrap 5.3.x;
- estrutura responsiva com `container`, `row` e `col`;
- uso consciente de utilitários de espaçamento, cor, texto, display e flex;
- primeira combinação entre classes do Bootstrap e CSS autoral;
- commits registrando a evolução da prática.

## Conceitos Essenciais
- Framework HTML/CSS.
- Bootstrap como toolkit front-end.
- CDN e arquivos locais.
- HTML5 doctype e viewport.
- Containers fixos e fluidos.
- Grid responsivo de 12 colunas.
- Breakpoints e classes responsivas.
- Gutters e espaçamentos.
- Utilitários de layout, cor, tipografia e flexbox.
- CSS autoral como complemento do framework.

## 1) Por que usar um framework?
Um framework HTML/CSS reúne padrões prontos para acelerar a criação de interfaces.
Ele normalmente oferece:
- sistema de grid;
- estilos base;
- componentes;
- utilitários;
- padrões responsivos;
- documentação e exemplos.

Isso ajuda a ganhar velocidade, mas não substitui conhecimento de HTML, CSS e acessibilidade.
O estudante continua responsável por:
- escrever HTML semântico;
- organizar conteúdo com clareza;
- testar responsividade;
- ajustar estilos autorais;
- justificar escolhas;
- evitar uso excessivo de classes sem intenção.

## 2) Por que Bootstrap nesta disciplina?
Bootstrap será usado como framework principal da Unidade 2 porque:
- tem documentação ampla;
- funciona bem por CDN em projetos estáticos;
- oferece grid responsivo consolidado;
- traz componentes comuns para páginas institucionais, acadêmicas e de serviços;
- permite combinar classes prontas com CSS autoral;
- ajuda a preparar o projeto integrador com mais organização.

O objetivo não é decorar todas as classes.
O objetivo é aprender a consultar a documentação, escolher padrões adequados e adaptar o framework ao projeto.

## 3) Estrutura inicial do projeto
Crie uma pasta para a aula:

```text
bootstrap-inicial/
  index.html
  styles.css
```

Se estiver usando Git, faça um commit inicial apenas com a estrutura vazia:

```bash
git status
git add .
git commit -m "Cria estrutura da prática com Bootstrap"
```

## 4) Passo 1 - Base HTML com Bootstrap por CDN
Crie o arquivo `index.html` com a estrutura mínima.
Neste primeiro momento, a página terá apenas um título simples.

```html
<!doctype html>
<html lang="pt-BR">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>Semana de Integração Web</title>
    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css"
      rel="stylesheet"
      integrity="sha384-sRIl4kxILFvY47J16cr9ZwB07vP4J8+LH7qKQnuqkuIAvNWLzeN8tE5YBujZqJLB"
      crossorigin="anonymous"
    />
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <h1>Semana de Integração Web</h1>
  </body>
</html>
```

### O que observar
- `<!doctype html>` é necessário para o Bootstrap renderizar corretamente.
- `viewport` ativa o comportamento responsivo em celulares.
- O CSS do Bootstrap vem antes do `styles.css`.
- Sua folha autoral vem depois para permitir complementos.

Abra a página no navegador.
Você já verá fonte, cor e espaçamento base aplicados pelo Bootstrap.

## 5) Passo 2 - Container e espaçamento vertical
Agora substitua o conteúdo do `body` por um cabeçalho semântico.
Começamos com `header` e `container`.

```html
<header class="py-5">
  <div class="container">
    <h1>Semana de Integração Web</h1>
    <p>Uma programação prática para consolidar HTML, CSS, Bootstrap, GitHub e projeto integrador.</p>
  </div>
</header>
```

### Classes usadas
- `container`: centraliza o conteúdo e limita a largura máxima.
- `py-5`: adiciona preenchimento vertical.

### Resultado esperado
O texto deixa de ficar colado à borda da janela.
O conteúdo passa a ter uma largura confortável.

## 6) Passo 3 - Cores e tipografia utilitária
Atualize o `header` e os textos.

```html
<header class="bg-primary text-white py-5">
  <div class="container">
    <p class="text-uppercase fw-semibold mb-2">Padrões Web</p>
    <h1 class="display-5 fw-bold mb-3">Semana de Integração Web</h1>
    <p class="lead mb-0">
      Uma programação prática para consolidar HTML, CSS, Bootstrap, GitHub e projeto integrador.
    </p>
  </div>
</header>
```

### Classes usadas
- `bg-primary`: aplica cor de fundo primária do Bootstrap.
- `text-white`: deixa o texto branco.
- `text-uppercase`: transforma o texto em maiúsculas.
- `fw-semibold` e `fw-bold`: controlam peso da fonte.
- `display-5`: aplica estilo de título de destaque.
- `lead`: aumenta a leitura do parágrafo introdutório.
- `mb-2`, `mb-3` e `mb-0`: controlam margem inferior.

### Resultado esperado
O cabeçalho ganha hierarquia visual e contraste.
A página começa a parecer uma interface, não apenas um HTML cru.

## 7) Passo 4 - Botões e Flexbox com utilitários
Acrescente ações no cabeçalho.
Coloque o bloco abaixo depois do parágrafo `lead`.

```html
<div class="d-flex flex-wrap gap-2 mt-4">
  <a class="btn btn-light btn-lg" href="#programacao">Ver programação</a>
  <a class="btn btn-outline-light btn-lg" href="#criterios">Critérios técnicos</a>
</div>
```

### Classes usadas
- `d-flex`: transforma o bloco em flex container.
- `flex-wrap`: permite quebra de linha em telas pequenas.
- `gap-2`: cria espaço entre os botões.
- `mt-4`: adiciona margem superior.
- `btn`: aplica estilo base de botão.
- `btn-light`: botão claro.
- `btn-outline-light`: botão com borda clara.
- `btn-lg`: botão maior.

### Resultado esperado
Os links passam a parecer ações.
Em tela pequena, os botões podem quebrar de linha sem estourar a largura.

Faça um commit:

```bash
git status
git add index.html
git commit -m "Adiciona cabeçalho com utilitários Bootstrap"
```

## 8) Passo 5 - Primeira seção com grid
Depois do `header`, crie o `main` com uma seção de critérios.
Comece com duas colunas: texto de apresentação e área de itens.

```html
<main>
  <section class="py-5" id="criterios" aria-labelledby="titulo-criterios">
    <div class="container">
      <div class="row g-4 align-items-start">
        <div class="col-12 col-lg-5">
          <p class="text-primary fw-semibold text-uppercase mb-2">Uso crítico</p>
          <h2 id="titulo-criterios" class="h1 mb-3">Framework não substitui projeto</h2>
          <p class="mb-0">
            Bootstrap acelera a montagem da interface, mas a qualidade continua dependendo de
            semântica, conteúdo, hierarquia, acessibilidade, responsividade e decisões autorais.
          </p>
        </div>

        <div class="col-12 col-lg-7">
          <p class="mb-0">Aqui entrarão os critérios em cards menores.</p>
        </div>
      </div>
    </div>
  </section>
</main>
```

### Classes usadas
- `row`: cria uma linha do grid.
- `g-4`: define espaçamento entre colunas e linhas.
- `align-items-start`: alinha os itens no início do eixo vertical.
- `col-12`: ocupa toda a largura em telas pequenas.
- `col-lg-5`: ocupa 5 colunas a partir de telas grandes.
- `col-lg-7`: ocupa 7 colunas a partir de telas grandes.

### Resultado esperado
No celular, os blocos ficam empilhados.
Em telas grandes, o texto fica à esquerda e a área dos critérios à direita.

## 9) Passo 6 - Grid aninhado para cards simples
Substitua o parágrafo "Aqui entrarão..." por uma `row` interna com quatro critérios.

```html
<div class="row g-3">
  <article class="col-12 col-md-6">
    <div class="h-100 border rounded-3 p-4 shadow-sm">
      <span class="etapa-numero">1</span>
      <h3 class="h5 mt-3">Semântica</h3>
      <p class="mb-0">Use landmarks, títulos em ordem lógica e links com sentido.</p>
    </div>
  </article>

  <article class="col-12 col-md-6">
    <div class="h-100 border rounded-3 p-4 shadow-sm">
      <span class="etapa-numero">2</span>
      <h3 class="h5 mt-3">Responsividade</h3>
      <p class="mb-0">Teste a página em diferentes larguras e revise quebras do grid.</p>
    </div>
  </article>

  <article class="col-12 col-md-6">
    <div class="h-100 border rounded-3 p-4 shadow-sm">
      <span class="etapa-numero">3</span>
      <h3 class="h5 mt-3">Autoria</h3>
      <p class="mb-0">Complemente o framework com decisões visuais próprias.</p>
    </div>
  </article>

  <article class="col-12 col-md-6">
    <div class="h-100 border rounded-3 p-4 shadow-sm">
      <span class="etapa-numero">4</span>
      <h3 class="h5 mt-3">Versionamento</h3>
      <p class="mb-0">Registre cada avanço em commits claros no GitHub.</p>
    </div>
  </article>
</div>
```

### Classes usadas
- `col-md-6`: cria duas colunas a partir de telas médias.
- `h-100`: faz o bloco ocupar toda a altura disponível.
- `border`: aplica borda.
- `rounded-3`: aplica cantos arredondados.
- `p-4`: aplica preenchimento interno.
- `shadow-sm`: aplica sombra discreta.
- `h5`: usa aparência de título menor sem mudar a semântica do `h3`.

### Resultado esperado
Os quatro critérios aparecem em uma coluna no celular e em duas colunas em telas médias.
Os blocos ficam visualmente agrupados, mas ainda sem uma identidade própria para os números.

## 10) Passo 7 - CSS autoral para complementar Bootstrap
Agora crie o arquivo `styles.css`.
O marcador `.etapa-numero` é uma decisão visual específica da página; por isso entra como CSS autoral.

```css
.etapa-numero {
  display: inline-grid;
  width: 2.5rem;
  height: 2.5rem;
  place-items: center;
  border-radius: 50%;
  background-color: #0d6efd;
  color: #ffffff;
  font-weight: 700;
}
```

### Por que não fazer tudo com classes prontas?
Bootstrap ajuda no layout, espaçamento e padrões comuns.
Mas alguns detalhes fazem parte da identidade do projeto.
Quando uma solução é específica e se repete com significado, uma classe autoral é mais clara do que empilhar muitas classes utilitárias.

Faça um commit:

```bash
git status
git add index.html styles.css
git commit -m "Adiciona grid de critérios e CSS autoral"
```

## 11) Passo 8 - Seção com fundo e cards de programação
Depois da seção de critérios, antes do fechamento de `</main>`, adicione a seção de programação.

```html
<section class="bg-light py-5" id="programacao" aria-labelledby="titulo-programacao">
  <div class="container">
    <div class="d-flex flex-column flex-md-row gap-3 justify-content-between align-items-md-end mb-4">
      <div>
        <p class="text-primary fw-semibold text-uppercase mb-2">Programação</p>
        <h2 id="titulo-programacao" class="h1 mb-0">Trilhas da semana</h2>
      </div>
      <a class="btn btn-primary" href="#resumo">Ver resumo</a>
    </div>

    <div class="row g-4">
      <article class="col-12 col-md-6 col-xl-4">
        <div class="h-100 bg-white border rounded-3 p-4 shadow-sm">
          <p class="text-secondary fw-semibold mb-2">Trilha 1</p>
          <h3 class="h4">HTML e conteúdo</h3>
          <p>Revisão de semântica, navegação, tabelas, formulários e organização textual.</p>
          <span class="badge text-bg-primary">Base técnica</span>
        </div>
      </article>

      <article class="col-12 col-md-6 col-xl-4">
        <div class="h-100 bg-white border rounded-3 p-4 shadow-sm">
          <p class="text-secondary fw-semibold mb-2">Trilha 2</p>
          <h3 class="h4">CSS e responsividade</h3>
          <p>Grid, estados interativos, media queries e refinamento visual em telas reais.</p>
          <span class="badge text-bg-success">Interface</span>
        </div>
      </article>

      <article class="col-12 col-md-6 col-xl-4">
        <div class="h-100 bg-white border rounded-3 p-4 shadow-sm">
          <p class="text-secondary fw-semibold mb-2">Trilha 3</p>
          <h3 class="h4">Bootstrap aplicado</h3>
          <p>Uso de containers, grid, utilitários e componentes com CSS autoral.</p>
          <span class="badge text-bg-warning">Framework</span>
        </div>
      </article>
    </div>
  </div>
</section>
```

### Classes usadas
- `bg-light`: cria uma faixa clara para separar a seção.
- `flex-column flex-md-row`: empilha no celular e alinha em linha a partir de `md`.
- `justify-content-between`: separa título e ação.
- `align-items-md-end`: alinha pela base em telas médias.
- `col-xl-4`: cria três colunas em telas extra grandes.
- `badge`: cria etiqueta curta de categoria.
- `text-bg-*`: combina cor de fundo e texto adequada ao badge.

### Resultado esperado
A página passa a ter uma seção de programação com cards em grid.
O layout deve se adaptar de uma coluna até três colunas.

## 12) Passo 9 - Indicadores e rodapé
Depois da programação, ainda antes do fechamento de `</main>`, adicione uma seção de resumo.

```html
<section class="py-5" id="resumo" aria-labelledby="titulo-resumo">
  <div class="container">
    <h2 id="titulo-resumo" class="visually-hidden">Resumo da programação</h2>
    <div class="row g-4">
      <div class="col-12 col-md-4">
        <p class="display-6 fw-bold text-primary mb-0">3</p>
        <p class="mb-0">trilhas de estudo</p>
      </div>
      <div class="col-12 col-md-4">
        <p class="display-6 fw-bold text-primary mb-0">5</p>
        <p class="mb-0">práticas orientadas</p>
      </div>
      <div class="col-12 col-md-4">
        <p class="display-6 fw-bold text-primary mb-0">1</p>
        <p class="mb-0">projeto integrador</p>
      </div>
    </div>
  </div>
</section>
```

Depois do `main`, adicione o rodapé:

```html
<footer class="border-top py-4">
  <div class="container d-flex flex-column flex-md-row gap-2 justify-content-between">
    <p class="mb-0">Disciplina de Padrões Web</p>
    <p class="mb-0">IFRN Campus Currais Novos</p>
  </div>
</footer>
```

### Classes usadas
- `visually-hidden`: mantém o título acessível, mas invisível visualmente.
- `display-6`: cria destaque numérico.
- `border-top`: adiciona borda superior.
- `justify-content-between`: separa os textos do rodapé em telas médias.

Faça um commit:

```bash
git status
git add index.html
git commit -m "Completa página inicial com indicadores e rodapé"
git push
```

## 13) Leitura dos principais padrões usados
Ao final da construção, observe os padrões que mais apareceram.

### Layout
```text
container
row
col-12
col-md-6
col-lg-5
col-lg-7
col-xl-4
```

### Espaçamento
```text
py-5
p-4
mt-4
mb-0
mb-2
mb-3
mb-4
g-3
g-4
gap-2
gap-3
```

### Tipografia e cor
```text
display-5
display-6
lead
h1
h4
h5
fw-bold
fw-semibold
text-primary
text-secondary
text-white
bg-primary
bg-light
bg-white
```

### Flexbox e componentes simples
```text
d-flex
flex-wrap
flex-column
flex-md-row
justify-content-between
align-items-md-end
btn
badge
border
rounded-3
shadow-sm
```

## 14) Exercício aplicado
Crie uma página inicial com Bootstrap para um dos temas do projeto integrador.

### Requisitos
- incluir Bootstrap por CDN;
- manter `<!doctype html>` e `meta viewport`;
- usar pelo menos três seções semânticas;
- usar `container` ou `container-fluid` corretamente;
- criar pelo menos uma `row` com colunas responsivas;
- usar classes `col-*` em pelo menos dois breakpoints;
- aplicar `g-*` para espaçamento de grid;
- usar utilitários de cor, espaçamento, texto e flex;
- criar pelo menos uma classe autoral no `styles.css`;
- registrar pelo menos três commits durante a prática.

### Desafio adicional
Inclua uma seção de indicadores com três números ou dados importantes do tema escolhido.
Ela deve ficar em uma coluna no celular e em três colunas em telas médias ou maiores.

## 15) Validação rápida antes de considerar concluído
- A página abre sem erro no navegador.
- O Bootstrap está carregado.
- O layout responde em telas estreitas e largas.
- O conteúdo não estoura a largura da tela.
- As classes de grid foram usadas dentro de `row`.
- As colunas possuem comportamento mobile-first.
- O CSS autoral complementa o Bootstrap sem excesso.
- O HTML continua semântico.
- Há commits claros no histórico.

## 16) Erros comuns
- esquecer o `meta viewport`;
- colocar `col-*` fora de uma `row`;
- copiar um bloco completo sem entender cada classe;
- criar muitas classes autorais para algo que um utilitário resolveria bem;
- usar utilitários em excesso até tornar o HTML difícil de ler;
- copiar exemplos sem adaptar conteúdo, semântica e hierarquia;
- depender apenas da aparência padrão do Bootstrap;
- alterar a versão do CDN sem conferir `integrity`;
- fazer toda a aula em um único commit genérico.

## Materiais para Aprofundamento
- [Bootstrap Docs - Introdução](https://getbootstrap.com/docs/5.3/getting-started/introduction/)
- [Bootstrap Docs - Containers](https://getbootstrap.com/docs/5.3/layout/containers/)
- [Bootstrap Docs - Grid](https://getbootstrap.com/docs/5.3/layout/grid/)
- [Bootstrap Docs - Breakpoints](https://getbootstrap.com/docs/5.3/layout/breakpoints/)
- [Bootstrap Docs - Utilities](https://getbootstrap.com/docs/5.3/utilities/api/)

## Checklist de Compreensão
- [ ] Consigo explicar por que usar Bootstrap sem abandonar HTML e CSS.
- [ ] Consigo incluir Bootstrap por CDN.
- [ ] Consigo usar `container`, `row` e `col`.
- [ ] Consigo aplicar classes responsivas como `col-md-6` e `col-xl-4`.
- [ ] Consigo controlar espaçamento com `g-*`, `m-*` e `p-*`.
- [ ] Consigo diferenciar utilitário de classe autoral.
- [ ] Consigo registrar a evolução da página com commits claros.

## Resumo Final
Neste encontro, você construiu uma primeira página responsiva com Bootstrap passo a passo.
O framework forneceu base, grid e utilitários; o CSS autoral entrou apenas onde havia uma decisão visual específica.

No próximo encontro, o foco passa para componentes do Bootstrap, navegação responsiva, cards, formulários e pequenos comportamentos com JavaScript.

## Questões de Fixação
1. Qual é a diferença entre Bootstrap e CSS autoral?
<!-- Gabarito: Bootstrap oferece padrões prontos de layout, utilitários e componentes; CSS autoral complementa o framework com decisões específicas do projeto. -->

2. Para que serve `container`?
<!-- Gabarito: Para limitar a largura do conteúdo, centralizar a área principal e manter leitura confortável. -->

3. O que significa `col-12 col-md-6 col-xl-4`?
<!-- Gabarito: A coluna ocupa 12 partes em telas pequenas, 6 partes a partir de md e 4 partes a partir de xl. -->

4. Por que o Bootstrap é considerado mobile-first?
<!-- Gabarito: Porque as regras básicas valem primeiro para telas pequenas, e classes com breakpoints passam a valer conforme a largura aumenta. -->

5. Quando criar uma classe no `styles.css` em vez de usar apenas utilitários?
<!-- Gabarito: Quando o ajuste representa uma decisão visual própria, se repete com significado no projeto ou melhora manutenção e leitura do HTML. -->
