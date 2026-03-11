# Encontro 1 - Apresentacao da disciplina, combinados e visao geral da Web

**Unidade:** Unidade 1  
**Carga prevista:** 1,5h  
**Entregavel previsto:** Diagnostico inicial

## Explicacao geral do encontro
Este encontro apresenta a disciplina no contexto do curso de Tecnologia em Sistemas para Internet. O foco e entender o papel de **HTML** e **CSS** na construcao de interfaces web, a logica da separacao entre estrutura e apresentacao e a trajetoria historica dessas tecnologias no desenvolvimento front-end.

![Imagem de apoio 1](https://upload.wikimedia.org/wikipedia/commons/6/61/HTML5_logo_and_wordmark.svg)

![Imagem de apoio 2](https://upload.wikimedia.org/wikipedia/commons/d/d5/CSS3_logo_and_wordmark.svg)

## Conceitos essenciais
- Papel do front-end no ecossistema web.
- Separacao entre estrutura semantica e apresentacao visual.
- Relevancia de HTML e CSS para formacao em Sistemas para Internet.

## Explicacao detalhada dos conceitos essenciais
### 1) Papel do front-end no ecossistema web.
Front-end transforma requisitos, conteudo e identidade visual em interfaces navegaveis, acessiveis e responsivas.

#### Exemplo aplicado
```text
Problema: divulgar um laboratorio academico.
Front-end entrega: pagina institucional, navegacao, layout e formularios HTML.
```

### 2) Separacao entre estrutura semantica e apresentacao visual.
HTML organiza o significado do conteudo; CSS controla forma, hierarquia visual e adaptacao entre telas.

#### Exemplo aplicado
```html
<main>
  <h1>Curso de Tecnologia em Sistemas para Internet</h1>
  <p>Conheca a matriz curricular e os projetos do curso.</p>
</main>
```

```css
main {
  max-width: 56rem;
  margin: 0 auto;
  padding: 2rem;
}
```

### 3) Relevancia de HTML e CSS para formacao em Sistemas para Internet.
Essas tecnologias sustentam landing pages, portais, documentacao, interfaces institucionais e produtos digitais publicados na Web.

#### Exemplo aplicado
```text
Cenarios frequentes:
- pagina de curso
- portal de servicos
- portfolio academico
- landing page de produto digital
```

## Linha do tempo resumida
| Ano | Marco |
|---|---|
| 1991 | Primeiro site publico em HTML (`info.cern.ch`) |
| 1994 | Proposta inicial de CSS |
| 1996 | CSS1 publicado pelo W3C |
| 2014 | HTML5 consolidado como recomendacao W3C |

## Exemplo principal da aula
```html
<header>
  <h1>Laboratorio de Interfaces Web</h1>
  <p>Projetos, recursos e orientacoes da disciplina.</p>
</header>
```

**Visual esperado da estrutura HTML:**
![Resultado do exemplo HTML](./imagens/encontro-1-exec-html.svg)

## Exemplos adicionais
```css
body {
  font-family: Arial, sans-serif;
  color: #0f172a;
  background: #f8fafc;
}
```

**Visual esperado com CSS aplicado:**
![Resultado do exemplo CSS](./imagens/encontro-1-exec-css.svg)

```html
<main class="caixa">
  <h2>Pagina institucional</h2>
  <p>Estrutura organizada com HTML e acabamento visual com CSS.</p>
</main>
```

**Resultado integrado de HTML + CSS:**
![Resultado do exemplo integrado](./imagens/encontro-1-exec-integrado.svg)

## Como estudar este encontro sozinho
1. Releia os conceitos e explique com suas palavras a diferenca entre estrutura e apresentacao.
2. Reproduza os exemplos de HTML e CSS em um arquivo simples.
3. Liste tres cenarios de TSI em que HTML e CSS sao indispensaveis.
4. Registre suas duvidas iniciais para acompanhar a evolucao ao longo da disciplina.

## Erros comuns de iniciantes
- Tratar HTML como linguagem de programacao e nao como linguagem de marcacao.
- Misturar organizacao de conteudo com decoracao visual sem criterio.
- Tentar acelerar para frameworks antes de consolidar semantica, CSS basico e responsividade.

## Materiais para aprofundamento
- [MDN - HTML](https://developer.mozilla.org/pt-BR/docs/Web/HTML)
- [MDN - CSS](https://developer.mozilla.org/pt-BR/docs/Web/CSS)
- [web.dev - Learn HTML](https://web.dev/learn/html)
- [web.dev - Learn CSS](https://web.dev/learn/css)

## Checklist de compreensao
- [ ] Consigo explicar o papel do front-end em um projeto web.
- [ ] Consigo diferenciar estrutura semantica e apresentacao visual.
- [ ] Consigo citar marcos historicos relevantes de HTML e CSS.
- [ ] Consigo relacionar a disciplina a cenarios reais do curso de TSI.

## Resumo final
Neste encontro, voce construiu a base conceitual da disciplina, entendendo por que HTML e CSS sao centrais para a construcao de interfaces web e como esse repertorio se conecta ao perfil profissional de Tecnologia em Sistemas para Internet.

## Questoes de fixacao
1. Qual foi a motivacao inicial para o surgimento do HTML?
<!-- Gabarito: Compartilhar documentos interligados por hipertexto na Web, inicialmente em contexto cientifico. -->

2. Por que o CSS foi criado?
<!-- Gabarito: Para separar conteudo de apresentacao, reduzindo repeticao e melhorando manutencao visual das paginas. -->

3. Em uma frase, diferencie HTML e CSS.
<!-- Gabarito: HTML organiza o conteudo e o significado; CSS define a aparencia e o layout. -->

4. Cite dois exemplos de projetos de TSI em que HTML e CSS sao importantes.
<!-- Gabarito: Ex.: landing page, portal institucional, portfolio academico, pagina de servicos digitais. -->

5. Qual base tecnica precisa estar consolidada antes de avancar para frameworks?
<!-- Gabarito: Semantica HTML, organizacao de conteudo, fundamentos de CSS e responsividade. -->
