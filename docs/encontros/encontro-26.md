# Encontro 26 - Bootstrap: Componentes, Navegação Responsiva, Cards e Formulários

**Unidade:** Unidade 2  
**Entrega:** Protótipo funcional com componentes

## Visão Geral
Neste encontro, você aprofunda o uso do Bootstrap por meio de componentes prontos e padrões de interação.
O foco é construir um protótipo com navegação responsiva, cards, badges, alertas, botões, formulário e modal.

Se no Encontro 25 você usou containers, grid e utilitários, agora esses recursos servem de base para montar uma interface mais próxima de um produto real.
O desafio é adaptar componentes sem perder semântica, acessibilidade e identidade visual.

Ao final da aula, você deverá ter:
- navbar responsiva com menu recolhível;
- seção com cards organizados em grid;
- botões e badges aplicados com intenção;
- formulário com classes do Bootstrap;
- modal acionado por atributo `data-bs-*`;
- CSS autoral pequeno e organizado;
- commits registrando as etapas do protótipo.

## Conceitos Essenciais
- Componentes do Bootstrap.
- Diferença entre layout, utilitário e componente.
- JavaScript bundle do Bootstrap.
- Atributos `data-bs-*`.
- Navbar responsiva.
- Cards e badges.
- Alerts e buttons.
- Form controls, selects e checks.
- Modal.
- Acessibilidade em componentes prontos.
- Customização sem sobrescrita agressiva.

## 1) O que é um componente no Bootstrap?
Um componente é um padrão de interface pronto para uso.
Ele combina:
- estrutura HTML esperada;
- classes CSS;
- estilos visuais;
- estados;
- em alguns casos, comportamento JavaScript.

Exemplos:
- navbar;
- card;
- alert;
- button;
- modal;
- accordion;
- form controls.

Usar um componente não significa copiar sem pensar.
Você deve adaptar:
- textos;
- hierarquia de títulos;
- links;
- rótulos;
- atributos de acessibilidade;
- integração com o conteúdo do projeto.

## 2) JavaScript bundle do Bootstrap
Alguns componentes precisam do JavaScript do Bootstrap.
É o caso de navbar recolhível, modal, collapse, offcanvas, dropdown e tooltip.

Use o script antes do fechamento do `body`:

```html
<script
  src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js"
  integrity="sha384-FKyoEForCGlyvwx9Hj09JcYn3nv7wiPVlz7YYwJrWVcXK/BmnVDxM+D2scQbITxI"
  crossorigin="anonymous"
></script>
```

O bundle inclui os recursos necessários para os componentes interativos mais comuns.

## 3) Estrutura da prática
Crie uma pasta ou continue a pasta do Encontro 25.

```text
bootstrap-componentes/
  index.html
  styles.css
```

Faça um commit antes de começar a alteração:

```bash
git status
git add .
git commit -m "Prepara prática de componentes Bootstrap"
```

## 4) Laboratório: protótipo de programação acadêmica
Crie o arquivo `index.html` com a base completa.

```html
<!doctype html>
<html lang="pt-BR">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>Integra Web - Componentes Bootstrap</title>
    <link
      href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css"
      rel="stylesheet"
      integrity="sha384-sRIl4kxILFvY47J16cr9ZwB07vP4J8+LH7qKQnuqkuIAvNWLzeN8tE5YBujZqJLB"
      crossorigin="anonymous"
    />
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <nav class="navbar navbar-expand-lg bg-body-tertiary border-bottom sticky-top">
      <div class="container">
        <a class="navbar-brand fw-bold" href="#">Integra Web</a>
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#menuPrincipal"
          aria-controls="menuPrincipal"
          aria-expanded="false"
          aria-label="Alternar navegação"
        >
          <span class="navbar-toggler-icon"></span>
        </button>

        <div class="collapse navbar-collapse" id="menuPrincipal">
          <ul class="navbar-nav ms-auto mb-2 mb-lg-0">
            <li class="nav-item">
              <a class="nav-link active" aria-current="page" href="#inicio">Início</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#oficinas">Oficinas</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#inscricao">Inscrição</a>
            </li>
          </ul>
        </div>
      </div>
    </nav>

    <header class="hero-bootstrap py-5" id="inicio">
      <div class="container py-lg-4">
        <div class="row g-4 align-items-center">
          <div class="col-12 col-lg-7">
            <span class="badge text-bg-warning mb-3">Nova programação</span>
            <h1 class="display-5 fw-bold">Bootstrap aplicado a interfaces reais</h1>
            <p class="lead mb-4">
              Um protótipo com navegação, cards, formulário e modal para apoiar o projeto integrador.
            </p>
            <div class="d-flex flex-wrap gap-2">
              <a class="btn btn-primary btn-lg" href="#oficinas">Explorar oficinas</a>
              <button
                class="btn btn-outline-primary btn-lg"
                type="button"
                data-bs-toggle="modal"
                data-bs-target="#modalOrientacoes"
              >
                Ver orientações
              </button>
            </div>
          </div>

          <div class="col-12 col-lg-5">
            <div class="bg-white border rounded-3 shadow-sm p-4">
              <p class="text-primary fw-semibold text-uppercase mb-2">Resumo</p>
              <ul class="list-group list-group-flush">
                <li class="list-group-item px-0 d-flex justify-content-between">
                  <span>Oficinas</span>
                  <strong>3</strong>
                </li>
                <li class="list-group-item px-0 d-flex justify-content-between">
                  <span>Formato</span>
                  <strong>Presencial</strong>
                </li>
                <li class="list-group-item px-0 d-flex justify-content-between">
                  <span>Entrega</span>
                  <strong>Protótipo</strong>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </header>

    <main>
      <section class="py-5" aria-labelledby="titulo-alerta">
        <div class="container">
          <div class="alert alert-primary mb-0" role="alert">
            <h2 id="titulo-alerta" class="h5 alert-heading">Atenção ao uso dos componentes</h2>
            <p class="mb-0">
              Componentes prontos devem ser adaptados ao conteúdo, testados em telas pequenas e
              registrados no histórico do Git.
            </p>
          </div>
        </div>
      </section>

      <section class="py-5 bg-light" id="oficinas" aria-labelledby="titulo-oficinas">
        <div class="container">
          <div class="d-flex flex-column flex-md-row gap-3 justify-content-between align-items-md-end mb-4">
            <div>
              <p class="text-primary fw-semibold text-uppercase mb-2">Oficinas</p>
              <h2 id="titulo-oficinas" class="h1 mb-0">Programação prática</h2>
            </div>
            <a class="btn btn-primary" href="#inscricao">Inscrever interesse</a>
          </div>

          <div class="row g-4">
            <article class="col-12 col-md-6 col-xl-4">
              <div class="card h-100 shadow-sm">
                <div class="card-body d-flex flex-column">
                  <div class="d-flex justify-content-between gap-2 mb-3">
                    <span class="badge text-bg-primary">Layout</span>
                    <span class="text-secondary">09h</span>
                  </div>
                  <h3 class="card-title h5">Grid e utilitários</h3>
                  <p class="card-text">
                    Organização de seções responsivas com containers, linhas, colunas e espaçamentos.
                  </p>
                  <a class="btn btn-outline-primary mt-auto" href="#inscricao">Quero participar</a>
                </div>
              </div>
            </article>

            <article class="col-12 col-md-6 col-xl-4">
              <div class="card h-100 shadow-sm">
                <div class="card-body d-flex flex-column">
                  <div class="d-flex justify-content-between gap-2 mb-3">
                    <span class="badge text-bg-success">Componentes</span>
                    <span class="text-secondary">10h30</span>
                  </div>
                  <h3 class="card-title h5">Cards e navegação</h3>
                  <p class="card-text">
                    Uso de navbar, cards, badges, botões e listas com atenção à semântica.
                  </p>
                  <a class="btn btn-outline-primary mt-auto" href="#inscricao">Quero participar</a>
                </div>
              </div>
            </article>

            <article class="col-12 col-md-6 col-xl-4">
              <div class="card h-100 shadow-sm">
                <div class="card-body d-flex flex-column">
                  <div class="d-flex justify-content-between gap-2 mb-3">
                    <span class="badge text-bg-warning">Formulários</span>
                    <span class="text-secondary">14h</span>
                  </div>
                  <h3 class="card-title h5">Inscrição e validação</h3>
                  <p class="card-text">
                    Construção de formulário com rótulos, controles, seleção e opção de aceite.
                  </p>
                  <a class="btn btn-outline-primary mt-auto" href="#inscricao">Quero participar</a>
                </div>
              </div>
            </article>
          </div>
        </div>
      </section>

      <section class="py-5" id="inscricao" aria-labelledby="titulo-inscricao">
        <div class="container">
          <div class="row g-4">
            <div class="col-12 col-lg-5">
              <p class="text-primary fw-semibold text-uppercase mb-2">Inscrição</p>
              <h2 id="titulo-inscricao" class="h1">Formulário com Bootstrap</h2>
              <p>
                Os campos continuam dependendo de HTML correto. Bootstrap melhora aparência,
                espaçamento e consistência dos controles.
              </p>
            </div>

            <div class="col-12 col-lg-7">
              <form class="row g-3">
                <div class="col-12 col-md-6">
                  <label class="form-label" for="nome">Nome</label>
                  <input class="form-control" id="nome" name="nome" type="text" autocomplete="name" required />
                </div>

                <div class="col-12 col-md-6">
                  <label class="form-label" for="email">E-mail</label>
                  <input class="form-control" id="email" name="email" type="email" autocomplete="email" required />
                </div>

                <div class="col-12">
                  <label class="form-label" for="oficina">Oficina de interesse</label>
                  <select class="form-select" id="oficina" name="oficina" required>
                    <option value="">Selecione uma oficina</option>
                    <option value="grid">Grid e utilitários</option>
                    <option value="componentes">Cards e navegação</option>
                    <option value="formularios">Inscrição e validação</option>
                  </select>
                </div>

                <div class="col-12">
                  <label class="form-label" for="mensagem">Observações</label>
                  <textarea class="form-control" id="mensagem" name="mensagem" rows="4"></textarea>
                </div>

                <div class="col-12">
                  <div class="form-check">
                    <input class="form-check-input" id="aceite" name="aceite" type="checkbox" required />
                    <label class="form-check-label" for="aceite">
                      Confirmo que revisei os horários da programação.
                    </label>
                  </div>
                </div>

                <div class="col-12">
                  <button class="btn btn-primary" type="submit">Enviar interesse</button>
                  <button class="btn btn-outline-secondary" type="reset">Limpar</button>
                </div>
              </form>
            </div>
          </div>
        </div>
      </section>
    </main>

    <div
      class="modal fade"
      id="modalOrientacoes"
      tabindex="-1"
      aria-labelledby="tituloModalOrientacoes"
      aria-hidden="true"
    >
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h2 class="modal-title h5" id="tituloModalOrientacoes">Orientações da prática</h2>
            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Fechar"></button>
          </div>
          <div class="modal-body">
            <p>
              Use componentes do Bootstrap como ponto de partida, mas preserve o sentido do conteúdo,
              teste responsividade e registre a evolução em commits.
            </p>
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-primary" data-bs-dismiss="modal">Entendi</button>
          </div>
        </div>
      </div>
    </div>

    <footer class="border-top py-4">
      <div class="container d-flex flex-column flex-md-row gap-2 justify-content-between">
        <p class="mb-0">Disciplina de Padrões Web</p>
        <p class="mb-0">IFRN Campus Currais Novos</p>
      </div>
    </footer>

    <script
      src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/js/bootstrap.bundle.min.js"
      integrity="sha384-FKyoEForCGlyvwx9Hj09JcYn3nv7wiPVlz7YYwJrWVcXK/BmnVDxM+D2scQbITxI"
      crossorigin="anonymous"
    ></script>
  </body>
</html>
```

## 5) CSS autoral do protótipo
Crie ou substitua `styles.css`:

```css
.hero-bootstrap {
  background-color: #eef5ff;
}

.card {
  border-color: #d7e3f5;
}
```

Esse CSS é propositalmente pequeno.
A maior parte da estrutura fica com o Bootstrap; o CSS autoral ajusta identidade e acabamento.

Faça um commit:

```bash
git status
git add index.html styles.css
git commit -m "Monta protótipo com componentes Bootstrap"
```

## 6) Navbar responsiva
A navbar usa classes e atributos específicos.

Trecho principal:

```html
<nav class="navbar navbar-expand-lg bg-body-tertiary border-bottom sticky-top">
  <div class="container">
    <a class="navbar-brand fw-bold" href="#">Integra Web</a>
    <button
      class="navbar-toggler"
      type="button"
      data-bs-toggle="collapse"
      data-bs-target="#menuPrincipal"
      aria-controls="menuPrincipal"
      aria-expanded="false"
      aria-label="Alternar navegação"
    >
      <span class="navbar-toggler-icon"></span>
    </button>
  </div>
</nav>
```

Leitura:
- `navbar` aplica o componente;
- `navbar-expand-lg` mantém o menu recolhido até telas grandes;
- `navbar-toggler` cria o botão do menu;
- `data-bs-toggle="collapse"` ativa o comportamento;
- `data-bs-target="#menuPrincipal"` aponta qual área será aberta;
- `aria-controls`, `aria-expanded` e `aria-label` ajudam tecnologias assistivas.

Teste diminuindo a largura do navegador.
O menu deve recolher e abrir pelo botão.

## 7) Cards com altura consistente
Cards organizam blocos repetidos.

Trecho de referência:

```html
<article class="col-12 col-md-6 col-xl-4">
  <div class="card h-100 shadow-sm">
    <div class="card-body d-flex flex-column">
      <h3 class="card-title h5">Grid e utilitários</h3>
      <p class="card-text">Organização de seções responsivas...</p>
      <a class="btn btn-outline-primary mt-auto" href="#inscricao">Quero participar</a>
    </div>
  </div>
</article>
```

Pontos importantes:
- `card` aplica o componente;
- `h-100` faz o card ocupar a altura disponível;
- `shadow-sm` cria sombra discreta;
- `d-flex flex-column` permite empurrar o botão para o final;
- `mt-auto` joga o botão para a base do card.

## 8) Badges e botões
Badges destacam categorias curtas.
Botões representam ações claras.

Exemplos:

```html
<span class="badge text-bg-primary">Layout</span>

<a class="btn btn-outline-primary" href="#inscricao">Quero participar</a>
```

Use badges para:
- status;
- categoria;
- nível;
- tipo de conteúdo.

Use botões para ações:
- abrir formulário;
- navegar para uma seção;
- confirmar uma ação;
- abrir um modal.

Evite transformar todo texto visual em badge ou botão.
Esses elementos precisam ter função clara.

## 9) Alertas
Alertas comunicam uma mensagem importante sem interromper a página.

Trecho de referência:

```html
<div class="alert alert-primary mb-0" role="alert">
  <h2 class="h5 alert-heading">Atenção ao uso dos componentes</h2>
  <p class="mb-0">Componentes prontos devem ser adaptados ao conteúdo.</p>
</div>
```

Boas práticas:
- use `role="alert"` quando a mensagem for relevante;
- mantenha texto curto;
- não use alerta apenas como decoração;
- escolha cor coerente com o significado.

## 10) Formulários com Bootstrap
Bootstrap estiliza controles, mas a estrutura semântica continua sendo HTML.

Trecho de referência:

```html
<label class="form-label" for="email">E-mail</label>
<input class="form-control" id="email" name="email" type="email" autocomplete="email" required />
```

Classes comuns:

```text
form-label
form-control
form-select
form-check
form-check-input
form-check-label
```

O que continua obrigatório:
- `label` associado ao controle;
- `id` único;
- `name` quando o formulário representa envio de dados;
- tipos adequados como `email`, `date`, `number`;
- `required` quando o campo é indispensável.

## 11) Modal com `data-bs-*`
O modal é um componente interativo.
Ele precisa do JavaScript bundle do Bootstrap.

Botão que abre:

```html
<button
  class="btn btn-outline-primary"
  type="button"
  data-bs-toggle="modal"
  data-bs-target="#modalOrientacoes"
>
  Ver orientações
</button>
```

Estrutura do modal:

```html
<div class="modal fade" id="modalOrientacoes" tabindex="-1" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      ...
    </div>
  </div>
</div>
```

Leitura:
- `data-bs-toggle="modal"` informa o comportamento;
- `data-bs-target` aponta o modal;
- `modal fade` aplica componente e transição;
- `modal-dialog` controla a caixa;
- `modal-content` agrupa cabeçalho, corpo e rodapé.

Teste:
- clique no botão;
- feche pelo botão "Fechar";
- feche pela tecla `Esc`;
- navegue com teclado dentro do modal.

## 12) Customização sem sobrescrita agressiva
Evite fazer isso como padrão:

```css
.btn-primary {
  background-color: red;
}
```

Essa sobrescrita altera todos os botões primários do projeto e pode gerar efeitos inesperados.

Prefira criar uma classe específica quando a mudança representa uma decisão local:

```css
.hero-bootstrap {
  background-color: #eef5ff;
}
```

Quando precisar customizar o Bootstrap de forma ampla, registre a decisão no README e mantenha consistência.

## 13) Acessibilidade em componentes
Mesmo usando Bootstrap, revise:
- ordem dos títulos;
- contraste;
- texto dos links;
- rótulos de formulário;
- `aria-label` em botões sem texto visível;
- `aria-current` no link ativo da navegação;
- foco visível;
- comportamento com teclado.

O Bootstrap ajuda, mas não sabe se seu conteúdo está correto.
Essa decisão continua sendo sua.

## 14) Registrar a evolução no Git
Depois de testar navbar, cards, formulário e modal:

```bash
git status
git add index.html styles.css
git commit -m "Adiciona navegação cards formulário e modal"
git push
```

Antes de enviar, abra o navegador e teste:
- menu recolhido;
- links internos;
- formulário;
- modal;
- responsividade.

## 15) Exercício aplicado
Evolua a página do Encontro 25 ou crie um protótipo para um tema do projeto integrador.

### Requisitos
- usar navbar responsiva;
- criar pelo menos três cards em grid;
- usar badges com significado;
- incluir pelo menos um alerta;
- criar formulário com `form-label`, `form-control`, `form-select` e `form-check`;
- incluir pelo menos um modal acionado por botão;
- manter CSS autoral pequeno e justificado;
- testar menu e modal em tela pequena;
- registrar pelo menos dois commits.

### Desafio adicional
Inclua um segundo componente interativo, como `accordion`, `collapse` ou `offcanvas`.
Use apenas se ele fizer sentido para o conteúdo.

## 16) Validação rápida antes de considerar concluído
- A navbar recolhe e abre corretamente.
- O JavaScript bundle do Bootstrap está carregado.
- Cards possuem títulos, textos e ações coerentes.
- Badges não substituem conteúdo essencial.
- Formulário tem rótulos associados.
- Modal abre, fecha e funciona com teclado.
- Links internos apontam para seções existentes.
- A página continua legível no celular.
- O CSS autoral não sobrescreve componentes de forma ampla sem necessidade.
- O histórico do Git registra a evolução.

## 17) Erros comuns
- esquecer o script do Bootstrap e esperar que modal ou navbar funcionem;
- usar `data-bs-target` com `id` inexistente;
- remover atributos `aria-*` de exemplos de componentes;
- usar cards para qualquer conteúdo sem pensar na hierarquia;
- usar botão onde deveria haver link, ou link onde deveria haver botão;
- criar formulário bonito, mas sem `label`;
- sobrescrever `.btn`, `.card` ou `.navbar` de forma global sem critério;
- não testar a navegação recolhida em telas pequenas.

## Materiais para Aprofundamento
- [Bootstrap Docs - Navbar](https://getbootstrap.com/docs/5.3/components/navbar/)
- [Bootstrap Docs - Cards](https://getbootstrap.com/docs/5.3/components/card/)
- [Bootstrap Docs - Buttons](https://getbootstrap.com/docs/5.3/components/buttons/)
- [Bootstrap Docs - Alerts](https://getbootstrap.com/docs/5.3/components/alerts/)
- [Bootstrap Docs - Forms](https://getbootstrap.com/docs/5.3/forms/overview/)
- [Bootstrap Docs - Modal](https://getbootstrap.com/docs/5.3/components/modal/)

## Checklist de Compreensão
- [ ] Consigo diferenciar layout, utilitário e componente.
- [ ] Consigo usar a navbar responsiva do Bootstrap.
- [ ] Consigo montar cards com conteúdo real e ações claras.
- [ ] Consigo usar badges e alerts com significado.
- [ ] Consigo aplicar classes de formulário sem perder semântica.
- [ ] Consigo ativar modal com `data-bs-*`.
- [ ] Consigo identificar quando o JavaScript bundle é necessário.
- [ ] Consigo customizar o protótipo sem sobrescrever tudo.

## Resumo Final
Neste encontro, você construiu um protótipo funcional com componentes do Bootstrap.
Navbar, cards, alertas, botões, formulário e modal aceleraram a montagem da interface, mas a qualidade veio da adaptação semântica, dos testes e das decisões autorais.

No próximo encontro, o foco continua em Bootstrap, com formulários, validação, tabelas e acessibilidade.

## Questões de Fixação
1. Por que alguns componentes do Bootstrap precisam do JavaScript bundle?
<!-- Gabarito: Porque componentes como navbar recolhível, modal e collapse dependem de comportamento interativo implementado pelo JavaScript do Bootstrap. -->

2. Qual é a função de `data-bs-target`?
<!-- Gabarito: Indicar qual elemento será controlado pelo componente, como o menu recolhível ou o modal. -->

3. Por que `label` continua obrigatório mesmo com Bootstrap?
<!-- Gabarito: Porque Bootstrap estiliza o controle, mas a associação semântica e acessível entre texto e campo depende do HTML. -->

4. Quando usar um badge?
<!-- Gabarito: Quando uma categoria, status ou informação curta precisa ser destacada sem substituir o conteúdo principal. -->

5. Qual cuidado tomar ao sobrescrever classes como `.btn-primary`?
<!-- Gabarito: A alteração afeta todos os elementos que usam a classe; por isso deve ser intencional, consistente e registrada quando for uma decisão global. -->
