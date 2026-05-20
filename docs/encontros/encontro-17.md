# Encontro 17 - Tamanhos em CSS: `px`, `rem`, `em`, `%`, `vw` e `vh`

**Unidade:** Unidade 1  

## Visão Geral
Neste encontro, você continua exatamente o projeto do Encontro 16.
Até aqui, já aplicamos seletores, box model e Flexbox.
Agora, o foco é controlar melhor **tamanhos de texto, blocos e componentes**.

A ideia é evoluir o mesmo **Portal da Turma** para uma versão com escala visual mais consistente.

## Conceitos Essenciais
- Diferença entre unidades absolutas e relativas.
- `px` para detalhes visuais de precisão.
- `rem` para tipografia e espaçamentos globais.
- `em` para escalonamento interno de componentes.
- `%` para larguras fluidas em relação ao contêiner pai.
- `vw` e `vh` para medidas relacionadas à viewport.

## 1) Ponto de partida (Encontro 16)
Você já tem:
- estrutura com `header`, `nav`, `main`, seções e `footer`;
- menu, cards e bloco de destaque com Flexbox;
- classes consolidadas como `.container`, `.bloco`, `.cards-aprendizado`, `.card` e `.botao`.

Agora vamos criar a **versão 4** do projeto, com foco em dimensionamento consistente.

### Referência visual da sequência
![Referência visual usada na continuidade do projeto](./imagens/encontro-15-exec-resultado.png)

## 2) Guia rápido de unidades
| Unidade | Pense assim | Use quando | Cuidado comum | Exemplo |
|---|---|---|---|---|
| `px` | valor fixo e preciso | bordas, sombras e detalhes visuais finos | usar para tudo e perder flexibilidade | `border: 1px solid #c6d6ea;` |
| `rem` | escala global (base no `html`) | tipografia e espaçamentos da página inteira | esquecer a base e misturar valores sem padrão | `font-size: 1rem; padding: 1rem;` |
| `em` | escala local (base no elemento pai) | componentes que devem crescer junto com o texto | herança acumulada gerar tamanho maior que o esperado | `padding: 0.6em 1em;` |
| `%` | proporção do elemento pai | largura fluida de blocos e colunas | não identificar quem é o pai de referência | `width: 75%;` |
| `vw` | proporção da largura da tela | ajustes fluidos de tamanho em conjunto com `clamp()` | usar sozinho e exagerar no crescimento da fonte | `font-size: clamp(1rem, 0.9rem + 0.6vw, 1.35rem);` |
| `vh` | proporção da altura da tela | altura mínima de seções de destaque | forçar altura grande e cortar conteúdo | `min-height: 18vh;` |

### Regra de bolso para decidir rápido
- Comece com `rem` para fonte e espaçamento.
- Use `px` apenas para detalhes de precisão (ex.: borda de `1px`).
- Use `%` para largura de blocos dentro do contêiner.
- Use `em` quando o componente precisa escalar com o próprio texto.
- Use `vw` e `vh` de forma pontual e, para fontes, prefira `clamp()`.

## 3) Objetivo da evolução
Ao final desta aula, o projeto deve ter:
- tipografia com escala previsível usando `rem`;
- componentes com espaçamentos consistentes;
- exemplos práticos de `px`, `em` e `%` no mesmo layout;
- uso pontual de `vw` e `vh` para fluidez;
- base pronta para o Encontro 18 (responsividade com media queries).

## 4) Passo 1 - HTML evoluído (mesma base, com bloco de laboratório)
No HTML, mantemos a estrutura principal e adicionamos um bloco para comparar larguras em `%`.

```html
<!doctype html>
<html lang="pt-BR">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Portal da Turma - Projeto Padrão</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <header id="topo" class="faixa">
      <div class="container">
        <h1>Portal da Turma</h1>
        <p class="subtitulo texto-fluido">Projeto padrão da disciplina de Padrões Web</p>
      </div>
    </header>

    <nav class="menu faixa" aria-label="Navegação principal">
      <div class="container">
        <a href="#inicio">Início</a>
        <a href="#conteudos">Conteúdos</a>
        <a href="#exercicios">Exercícios</a>
        <a href="#materiais">Materiais</a>
        <a href="#contato">Contato</a>
      </div>
    </nav>

    <main id="inicio" class="container">
      <section id="conteudos" class="bloco bloco-sobre">
        <h2>Sobre o Encontro</h2>
        <p>
          Neste encontro, evoluímos o mesmo projeto para estudar como `px`, `rem`, `em`, `%`,
          `vw` e `vh` afetam tipografia, espaçamentos e dimensões de blocos.
        </p>
      </section>

      <section id="exercicios" class="bloco bloco-aprendizado">
        <h2>O que você vai aprender</h2>
        <div class="cards-aprendizado">
          <article class="card">
            <h3>`px` e `rem`</h3>
            <p>Quando usar precisão fixa e quando usar escala global.</p>
          </article>
          <article class="card card-escala">
            <h3>`em` em componentes</h3>
            <p>Como o botão cresce junto com o tamanho do texto do card.</p>
            <a class="botao" href="#materiais">Ver exemplo</a>
          </article>
          <article class="card">
            <h3>Largura em `%`</h3>
            <p>Como blocos ocupam mais ou menos espaço com base no contêiner pai.</p>
          </article>
        </div>
      </section>

      <section id="materiais" class="bloco destaque">
        <h2>Laboratório de Larguras</h2>
        <p class="aviso" id="aviso-semana">
          Compare como cada faixa em porcentagem ocupa espaço dentro do mesmo contêiner.
        </p>

        <div class="amostras-largura">
          <div class="amostra largura-100">`width: 100%`</div>
          <div class="amostra largura-75">`width: 75%`</div>
          <div class="amostra largura-50">`width: 50%`</div>
        </div>
      </section>
    </main>

    <footer id="contato" class="faixa">
      <div class="container">
        <p>Disciplina de Padrões Web</p>
      </div>
    </footer>
  </body>
</html>
```

### O que mudou no HTML?
- inclusão da classe `.texto-fluido` para exemplo de tipografia com viewport;
- inclusão da classe `.card-escala` para demonstrar `em` no componente;
- criação do bloco `.amostras-largura` para comparar `%` na prática.

## 5) Passo 2 - CSS
Mantenha as regras já construídas nos Encontros 14, 15 e 16.
Neste encontro, adicione as regras abaixo para controlar tamanhos com mais consistência.

### Etapa 2.1 - Regra 1: base tipográfica com `rem`
```css
html {
  font-size: 16px;
}

:root {
  --fs-1: 0.875rem;
  --fs-2: 1rem;
  --fs-3: 1.25rem;
  --space-1: 0.5rem;
  --space-2: 1rem;
  --space-3: 1.5rem;
}
```
**Explicação linha a linha**
- `html { font-size: 16px; }`: define a base para cálculo de `rem`.
- `:root`: cria variáveis globais reutilizáveis.
- `--fs-*`: escala de tamanho de fonte em `rem`.
- `--space-*`: escala de espaçamento em `rem`.

**Para que serve no projeto**
- padroniza fonte e espaçamento;
- facilita ajustes globais sem editar regra por regra.

### Etapa 2.2 - Regra 2: tipografia principal em `rem`
```css
body {
  font-size: var(--fs-2);
  line-height: 1.6;
}

h1 {
  font-size: 2rem;
}

h2 {
  font-size: var(--fs-3);
}

p,
.card p,
.menu a {
  font-size: var(--fs-2);
}
```
**Explicação linha a linha**
- `font-size: var(--fs-2)`: usa a escala global em `rem`.
- `line-height: 1.6`: melhora leitura sem unidade fixa.
- `h1` e `h2`: mantêm hierarquia visual previsível.
- bloco agrupado de texto: garante consistência tipográfica no projeto.

**Para que serve no projeto**
- mantém ritmo visual entre títulos, textos e menu;
- evita tamanhos “soltos” em cada componente.

### Etapa 2.3 - Regra 3: `px` para detalhes de precisão
```css
.bloco {
  border: 1px solid #c6d6ea;
  border-radius: 8px;
}

.card {
  border: 1px solid #b8c7df;
}
```
**Explicação linha a linha**
- `1px`: espessura fina e previsível para bordas.
- `border-radius: 8px`: arredondamento visual constante.

**Para que serve no projeto**
- usa `px` onde precisão visual é desejada;
- mantém acabamento nítido em cartões e blocos.

### Etapa 2.4 - Regra 4: espaçamento em `rem`
```css
.bloco {
  padding: var(--space-2);
  margin-bottom: var(--space-2);
}

.card {
  padding: var(--space-2);
}
```
**Explicação linha a linha**
- `padding` e `margin-bottom` usam a mesma escala em `rem`.
- os cards reaproveitam a variável para manter consistência.

**Para que serve no projeto**
- facilita manter proporção entre componentes;
- melhora manutenção do CSS com menos valores isolados.

### Etapa 2.5 - Regra 5: `em` dentro do componente
```css
.card-escala {
  font-size: 1.125rem;
}

.card-escala .botao {
  font-size: 1em;
  padding: 0.6em 1em;
}
```
**Explicação linha a linha**
- `.card-escala`: aumenta ligeiramente o tamanho base do card.
- `font-size: 1em`: botão herda a escala local desse card.
- `padding` em `em`: o espaçamento do botão cresce junto com o texto.

**Para que serve no projeto**
- mostra como `em` é útil para componentes autoescaláveis;
- evita ajustar manualmente cada tamanho quando o card muda.

### Etapa 2.6 - Regra 6: `%` para largura de blocos
```css
.amostras-largura {
  display: grid;
  gap: 0.75rem;
}

.amostra {
  padding: 0.5rem 0.75rem;
  border: 1px dashed #8aa1c3;
  background-color: #f6fbff;
  font-family: Consolas, monospace;
}

.largura-100 {
  width: 100%;
}

.largura-75 {
  width: 75%;
}

.largura-50 {
  width: 50%;
}
```
**Explicação linha a linha**
- `%` calcula a largura com base no pai (`.amostras-largura`).
- `width: 100%`, `75%` e `50%`: permitem comparação direta no mesmo contexto.

**Para que serve no projeto**
- reforça a lógica de largura fluida;
- prepara para ajustes responsivos do encontro seguinte.

### Etapa 2.7 - Regra 7: `vw` e `vh` de forma controlada
```css
#topo {
  min-height: 18vh;
}

.texto-fluido {
  font-size: clamp(1rem, 0.9rem + 0.6vw, 1.35rem);
}
```
**Explicação linha a linha**
- `min-height: 18vh`: define altura mínima do topo proporcional à altura da tela.
- `clamp(...)`: limita crescimento da fonte com base na largura da viewport (`vw`).

**Para que serve no projeto**
- adiciona fluidez sem exageros;
- evita texto minúsculo ou grande demais em telas extremas.

### CSS novo deste encontro (resumo)
```css
html {
  font-size: 16px;
}

:root {
  --fs-1: 0.875rem;
  --fs-2: 1rem;
  --fs-3: 1.25rem;
  --space-1: 0.5rem;
  --space-2: 1rem;
  --space-3: 1.5rem;
}

body {
  font-size: var(--fs-2);
  line-height: 1.6;
}

h1 {
  font-size: 2rem;
}

h2 {
  font-size: var(--fs-3);
}

p,
.card p,
.menu a {
  font-size: var(--fs-2);
}

.bloco {
  border: 1px solid #c6d6ea;
  border-radius: 8px;
  padding: var(--space-2);
  margin-bottom: var(--space-2);
}

.card {
  border: 1px solid #b8c7df;
  padding: var(--space-2);
}

.card-escala {
  font-size: 1.125rem;
}

.card-escala .botao {
  font-size: 1em;
  padding: 0.6em 1em;
}

.amostras-largura {
  display: grid;
  gap: 0.75rem;
}

.amostra {
  padding: 0.5rem 0.75rem;
  border: 1px dashed #8aa1c3;
  background-color: #f6fbff;
  font-family: Consolas, monospace;
}

.largura-100 {
  width: 100%;
}

.largura-75 {
  width: 75%;
}

.largura-50 {
  width: 50%;
}

#topo {
  min-height: 18vh;
}

.texto-fluido {
  font-size: clamp(1rem, 0.9rem + 0.6vw, 1.35rem);
}
```

## 6) Validação rápida da versão 4
- Tipografia principal foi definida com `rem`.
- Bordas e detalhes finos usam `px`.
- O botão do card de escala usa `em` e cresce junto com o componente.
- O laboratório mostra claramente diferença entre `100%`, `75%` e `50%`.
- O topo e o subtítulo usam `vh`/`vw` de forma controlada.

## 7) Erros comuns nesta evolução
- usar `px` para tudo e perder flexibilidade;
- usar `%` sem entender qual é o elemento pai de referência;
- aplicar `em` sem perceber que ele multiplica com heranças de fonte;
- exagerar em `vw` para texto e prejudicar legibilidade;
- misturar muitos valores sem uma escala base (`:root`).

## 8) Prática Final - Projeto Padrão da Disciplina (Versão 4)
Nesta versão, o projeto mantém a base do Encontro 16 e evolui com foco total em dimensionamento.
A meta é justificar tecnicamente quando usar `px`, `rem`, `em`, `%`, `vw` e `vh`.

### Ajustes sugeridos
1. Aumente `html { font-size }` para `18px` e observe quais partes escalam automaticamente.
2. Teste `.largura-75` e `.largura-50` em diferentes tamanhos de janela.
3. Crie uma variação `.card-escala-grande` e compare com `.card-escala`.
4. Reduza e amplie a janela para validar o comportamento de `.texto-fluido`.
5. Revise se há medidas repetidas que podem virar variáveis em `:root`.

### Critérios de validação
- O projeto demonstra, na prática, uso de `px`, `rem`, `em`, `%`, `vw` e `vh`.
- Tipografia e espaçamentos têm padrão de escala coerente.
- Larguras relativas funcionam sem quebrar o layout.
- A base do Encontro 16 foi preservada e evoluída.

## Materiais para Aprofundamento
- [MDN - Unidades e valores CSS](https://developer.mozilla.org/pt-BR/docs/Learn_web_development/Core/Styling_basics/Values_and_units)
- [MDN - `length`](https://developer.mozilla.org/pt-BR/docs/Web/CSS/length)
- [MDN - `clamp()`](https://developer.mozilla.org/pt-BR/docs/Web/CSS/clamp)
- [MDN - `font-size`](https://developer.mozilla.org/pt-BR/docs/Web/CSS/font-size)

## Checklist de Compreensão
- [ ] Consigo explicar diferença entre unidade absoluta e relativa.
- [ ] Consigo justificar quando usar `px` e quando usar `rem`.
- [ ] Consigo usar `em` para escalar componentes internos.
- [ ] Consigo usar `%` com base no contêiner pai.
- [ ] Consigo aplicar `vw`/`vh` com controle de legibilidade.

## Resumo Final
Neste encontro, você evoluiu o mesmo Portal da Turma com uma estratégia clara de tamanhos em CSS.
Com isso, o projeto fica mais consistente e pronto para o próximo passo: responsividade com media queries no Encontro 18.
