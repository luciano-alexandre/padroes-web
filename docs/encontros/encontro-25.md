# Encontro 25 - Frameworks HTML/CSS e Bootstrap: CDN, Containers, Grid e Utilitários

**Unidade:** Unidade 2  
**Entrega:** Página inicial com Bootstrap

## Visão Geral
Neste encontro, você inicia o estudo de Bootstrap dentro de um fluxo profissional de projeto.
O objetivo é entender o papel de um framework HTML/CSS, configurar Bootstrap por CDN e construir uma página responsiva usando containers, grid, breakpoints, gutters e utilitários.

Se no Encontro 24 você organizou o versionamento com Git e GitHub, agora esse repositório passa a receber uma primeira interface feita com Bootstrap.
Cada etapa prática deve gerar commits pequenos e bem nomeados.

Ao final da aula, você deverá ter:
- uma página HTML usando Bootstrap 5.3.x;
- estrutura responsiva com `container`, `row` e `col`;
- uso consciente de utilitários de espaçamento, cor, texto, display e flex;
- pequena folha de CSS autoral para complementar o framework;
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
- Diferença entre usar framework e delegar decisões ao framework.

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

## 3) Criar a estrutura da prática
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

## 4) Adicionar Bootstrap por CDN
Crie o arquivo `index.html` com a base abaixo.
O link do Bootstrap deve ficar no `head`, antes da sua folha autoral.

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

### Pontos importantes
- `<!doctype html>` é obrigatório para o Bootstrap renderizar corretamente.
- `viewport` garante comportamento responsivo em celulares.
- A folha `styles.css` vem depois do Bootstrap para permitir ajustes autorais.
- O atributo `integrity` está vinculado à versão usada; ao trocar a versão, consulte a documentação e atualize também esse valor.

Abra a página no navegador.
Você já verá diferenças de fonte, espaçamento e estilo base aplicadas pelo Bootstrap.

## 5) Laboratório: página inicial de um evento acadêmico
Substitua o conteúdo do `body` por uma página completa.
Nesta primeira aula, o foco é layout e utilitários; componentes mais complexos virão no Encontro 26.

```html
<header class="bg-primary text-white py-5">
  <div class="container">
    <p class="text-uppercase fw-semibold mb-2">Padrões Web</p>
    <h1 class="display-5 fw-bold mb-3">Semana de Integração Web</h1>
    <p class="lead mb-4">
      Uma programação prática para consolidar HTML, CSS, Bootstrap, GitHub e projeto integrador.
    </p>
    <div class="d-flex flex-wrap gap-2">
      <a class="btn btn-light btn-lg" href="#programacao">Ver programação</a>
      <a class="btn btn-outline-light btn-lg" href="#criterios">Critérios técnicos</a>
    </div>
  </div>
</header>

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
        </div>
      </div>
    </div>
  </section>

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

  <section class="py-5" id="resumo" aria-labelledby="titulo-resumo">
    <div class="container">
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
</main>

<footer class="border-top py-4">
  <div class="container d-flex flex-column flex-md-row gap-2 justify-content-between">
    <p class="mb-0">Disciplina de Padrões Web</p>
    <p class="mb-0">IFRN Campus Currais Novos</p>
  </div>
</footer>
```

## 6) CSS autoral mínimo
Crie o arquivo `styles.css`.
Ele deve complementar o Bootstrap, não competir com todas as classes do framework.

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

### Resultado esperado
A página deve apresentar:
- cabeçalho com contraste forte;
- seções com espaçamento vertical;
- grade responsiva;
- cartões simples com altura consistente;
- números de destaque;
- rodapé flexível.

Faça um commit:

```bash
git status
git add index.html styles.css
git commit -m "Cria página inicial com Bootstrap"
```

## 7) Containers
Containers limitam a largura do conteúdo e centralizam a página.

Exemplo:

```html
<div class="container">
  ...
</div>
```

Use `container` quando o conteúdo precisa ter largura máxima confortável.
Use `container-fluid` quando a seção precisa ocupar toda a largura disponível.

Exemplo de área fluida:

```html
<section class="container-fluid bg-light py-5">
  <div class="container">
    <h2>Conteúdo com fundo de ponta a ponta</h2>
  </div>
</section>
```

Nesse padrão:
- `container-fluid` controla a faixa visual;
- `container` mantém o texto alinhado e legível.

## 8) Grid de 12 colunas
O grid do Bootstrap usa a estrutura:

```html
<div class="container">
  <div class="row">
    <div class="col">Coluna 1</div>
    <div class="col">Coluna 2</div>
  </div>
</div>
```

Na prática da aula:

```html
<article class="col-12 col-md-6 col-xl-4">
  ...
</article>
```

Essa combinação significa:
- `col-12`: ocupa toda a linha em telas muito pequenas;
- `col-md-6`: ocupa metade da linha a partir do breakpoint `md`;
- `col-xl-4`: ocupa um terço da linha a partir do breakpoint `xl`.

O grid é mobile-first.
As classes menores valem primeiro; as classes maiores entram conforme há espaço.

## 9) Breakpoints
Breakpoints são faixas de largura em que o layout muda.
No Bootstrap, classes como `col-md-6`, `d-md-flex` e `text-lg-start` indicam em qual faixa a regra passa a valer.

Exemplo:

```html
<div class="d-flex flex-column flex-md-row gap-3">
  ...
</div>
```

Leitura:
- em telas pequenas, `flex-column` organiza em coluna;
- a partir de `md`, `flex-md-row` organiza em linha;
- `gap-3` mantém espaçamento entre itens.

Use o DevTools para alternar larguras e observar quando cada classe muda o comportamento.

## 10) Gutters e espaçamentos
`g-*` controla o espaço entre colunas e linhas dentro de uma `row`.

Exemplo:

```html
<div class="row g-4">
  ...
</div>
```

Classes úteis:

```text
g-0, g-1, g-2, g-3, g-4, g-5
gx-4
gy-4
```

Para margens e preenchimentos:

```text
m-0
mb-3
mt-4
p-4
py-5
px-3
```

Leitura dos nomes:
- `m` significa margin;
- `p` significa padding;
- `t`, `b`, `x` e `y` indicam direção;
- o número indica escala de espaçamento.

## 11) Utilitários de cor, texto e flex
Bootstrap oferece classes utilitárias para ajustes frequentes.

Exemplos usados na página:

```html
<p class="text-primary fw-semibold text-uppercase mb-2">Programação</p>

<div class="d-flex flex-wrap gap-2">
  <a class="btn btn-light" href="#programacao">Ver programação</a>
</div>
```

Classes comuns:

```text
text-primary
text-secondary
bg-light
bg-primary
text-white
fw-bold
fw-semibold
text-uppercase
d-flex
flex-wrap
justify-content-between
align-items-md-end
```

Use utilitários para ajustes pequenos.
Quando uma combinação se repetir muito ou representar identidade visual própria, crie uma classe autoral no `styles.css`.

## 12) Bootstrap e CSS autoral
Uma página madura combina:
- classes do Bootstrap para estrutura e padrões recorrentes;
- CSS autoral para identidade, detalhes específicos e ajustes do projeto.

Exemplo da aula:

```html
<span class="etapa-numero">1</span>
```

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

Essa classe existe porque o marcador numerado é uma decisão visual específica da página.

## 13) Registrar a evolução no Git
Depois de estudar containers, grid e utilitários, faça um commit.

```bash
git status
git add index.html styles.css
git commit -m "Aplica grid e utilitários responsivos do Bootstrap"
```

Envie ao GitHub:

```bash
git push
```

Se o repositório ainda não tiver remoto, retome o procedimento do Encontro 24 antes do `push`.

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
- registrar pelo menos dois commits durante a prática.

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
Neste encontro, você construiu uma primeira página responsiva com Bootstrap.
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
