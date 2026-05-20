# Encontro 17 - CSS Grid na Estrutura Global do Projeto

**Unidade:** Unidade 1  

## Visão Geral
Neste encontro, você continua exatamente o projeto do Encontro 16.
Até aqui, o Flexbox organizou grupos internos (menu, cards e bloco de destaque).
Agora, o foco passa para a **estrutura global da página** com CSS Grid.

A ideia é evoluir o mesmo **Portal da Turma** sem recomeçar do zero.

## Conceitos Essenciais
- Diferença de papel entre Grid (macroestrutura) e Flexbox (componentes internos).
- `display: grid`.
- `grid-template-columns`.
- `grid-template-areas`.
- `gap` na malha principal.
- Evolução incremental do mesmo projeto.

## 1) Ponto de partida (Encontro 16)
Você já tem:
- `header`, `nav`, `main` e `footer` prontos;
- menu, cards e agrupamentos internos com Flexbox;
- classes consolidadas como `.bloco`, `.cards-aprendizado`, `.card` e `.destaque-acao`.

Agora vamos transformar a página em uma **versão 4**, usando Grid para distribuir as grandes áreas do layout.

### Referência visual da sequência
![Referência visual usada na continuidade do projeto](./imagens/encontro-15-exec-resultado.png)

## 2) Objetivo da evolução
Ao final desta aula, o projeto deve ter:
- um contêiner principal em Grid;
- `header` e `footer` ocupando toda a largura da malha;
- menu lateral em uma coluna dedicada;
- conteúdo principal em coluna própria;
- manutenção dos componentes internos já trabalhados no Encontro 16.

## 3) Passo 1 - HTML evoluído (mesma base, com contêiner de layout)
No HTML, a mudança principal é criar um contêiner para a malha global e manter o restante da estrutura já conhecida.

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
    <div class="layout-pagina">
      <header id="topo" class="faixa">
        <div class="container">
          <h1>Portal da Turma</h1>
          <p class="subtitulo">Projeto padrão da disciplina de Padrões Web</p>
        </div>
      </header>

      <nav class="menu" aria-label="Navegação principal">
        <div class="menu-links">
          <a href="#inicio">Início</a>
          <a href="#conteudos">Conteúdos</a>
          <a href="#exercicios">Exercícios</a>
          <a href="#materiais">Materiais</a>
          <a href="#contato">Contato</a>
        </div>
      </nav>

      <main id="inicio">
        <section id="conteudos" class="bloco bloco-sobre">
          <h2>Sobre o Encontro</h2>
          <p>
            Continuamos o projeto iniciado nos encontros anteriores, agora organizando
            a estrutura global com Grid e mantendo Flexbox nos componentes internos.
          </p>
        </section>

        <section id="exercicios" class="bloco bloco-aprendizado">
          <h2>O que você vai aprender</h2>
          <div class="cards-aprendizado">
            <article class="card">
              <h3>Malha Global</h3>
              <p>Distribuir a página em colunas com previsibilidade.</p>
            </article>
            <article class="card">
              <h3>Áreas Nomeadas</h3>
              <p>Mapear cabeçalho, menu, conteúdo e rodapé com clareza.</p>
            </article>
            <article class="card">
              <h3>Grid + Flexbox</h3>
              <p>Combinar Grid na estrutura e Flexbox dentro dos blocos.</p>
            </article>
          </div>
        </section>

        <section id="materiais" class="bloco destaque">
          <h2>Aviso importante</h2>
          <div class="destaque-acao">
            <p class="aviso" id="aviso-semana">
              O projeto continuará sendo reaproveitado no próximo encontro, com foco
              em responsividade e media queries.
            </p>
            <a class="botao" href="#exercicios">Continuar prática</a>
          </div>
        </section>
      </main>

      <footer id="contato" class="faixa">
        <div class="container">
          <p>Disciplina de Padrões Web</p>
        </div>
      </footer>
    </div>
  </body>
</html>
```

### O que mudou no HTML?
- inclusão de `.layout-pagina` para receber o Grid principal;
- criação de `.menu-links` para organizar o menu lateral;
- manutenção das seções, cards e bloco de destaque da versão anterior.

## 4) Passo 2 - CSS 
Mantenha as regras já construídas nos Encontros 14, 15 e 16.
Neste encontro, adicione as regras abaixo para a estrutura global com Grid.

### Etapa 2.1 - Regra 1: criar a malha principal
```css
.layout-pagina {
  display: grid;
  grid-template-columns: 15rem minmax(0, 1fr);
  grid-template-areas:
    "cabecalho cabecalho"
    "menu conteudo"
    "rodape rodape";
  gap: 1rem;
  width: min(95%, 74rem);
  margin: 1rem auto;
}
```
**Explicação linha a linha**
- `.layout-pagina`: seleciona o contêiner que envolve toda a página.
- `display: grid`: ativa Grid nesse contêiner.
- `grid-template-columns: 15rem minmax(0, 1fr)`: define uma coluna lateral fixa (`15rem`) e uma coluna principal flexível.
- `grid-template-areas`: desenha a malha com nomes de áreas.
- `gap: 1rem`: cria espaçamento uniforme entre as áreas da malha.
- `width: min(95%, 74rem)`: limita a largura máxima sem perder fluidez.
- `margin: 1rem auto`: centraliza a malha e cria respiro vertical.

**Para que serve no projeto**
- organiza a estrutura geral sem ajustes manuais de posição;
- separa claramente navegação lateral e conteúdo;
- prepara a base para responsividade no próximo encontro.

### Etapa 2.2 - Regra 2: associar elementos às áreas nomeadas
```css
#topo {
  grid-area: cabecalho;
}

.menu {
  grid-area: menu;
}

#inicio {
  grid-area: conteudo;
  min-width: 0;
}

#contato {
  grid-area: rodape;
}
```
**Explicação linha a linha**
- `#topo`, `.menu`, `#inicio` e `#contato`: selecionam os blocos principais da página.
- `grid-area`: conecta cada bloco ao nome definido em `grid-template-areas`.
- `min-width: 0`: evita estouro horizontal no conteúdo principal em layouts com coluna flexível.

**Para que serve no projeto**
- deixa explícito qual elemento ocupa cada área da malha;
- melhora leitura e manutenção do CSS.

### Etapa 2.3 - Regra 3: adaptar o menu para coluna lateral
```css
.menu {
  background-color: #edf0f5;
  border: 1px solid #c6d6ea;
  border-radius: 0.5rem;
  padding: 0.75rem;
}

.menu-links {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.menu-links a {
  display: block;
  padding: 0.55rem 0.75rem;
  border: 1px solid #b8c7df;
  border-radius: 0.4rem;
  text-decoration: none;
  font-weight: 700;
  color: #11256c;
  background-color: #ffffff;
}
```
**Explicação linha a linha**
- `.menu`: define caixa visual da navegação lateral.
- `.menu-links`: usa Flexbox em coluna para empilhar os links.
- `gap`: controla espaçamento vertical entre itens.
- `.menu-links a`: transforma links em blocos clicáveis de largura total.

**Para que serve no projeto**
- torna a coluna de navegação legível e consistente com o restante da interface;
- mantém o uso de Flexbox como complemento interno do Grid.

### Etapa 2.4 - Regra 4: organizar o fluxo interno do conteúdo principal
```css
#inicio {
  display: grid;
  gap: 1rem;
}
```
**Explicação linha a linha**
- `#inicio`: seleciona o `main` da página.
- `display: grid`: organiza as seções internas em fluxo vertical consistente.
- `gap: 1rem`: mantém espaçamento uniforme entre os blocos.

**Para que serve no projeto**
- elimina a necessidade de ajustes pontuais de margem entre seções;
- mantém ritmo visual coerente com a malha global.

### CSS novo deste encontro (resumo)
```css
.layout-pagina {
  display: grid;
  grid-template-columns: 15rem minmax(0, 1fr);
  grid-template-areas:
    "cabecalho cabecalho"
    "menu conteudo"
    "rodape rodape";
  gap: 1rem;
  width: min(95%, 74rem);
  margin: 1rem auto;
}

#topo {
  grid-area: cabecalho;
}

.menu {
  grid-area: menu;
  background-color: #edf0f5;
  border: 1px solid #c6d6ea;
  border-radius: 0.5rem;
  padding: 0.75rem;
}

#inicio {
  grid-area: conteudo;
  min-width: 0;
  display: grid;
  gap: 1rem;
}

#contato {
  grid-area: rodape;
}

.menu-links {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.menu-links a {
  display: block;
  padding: 0.55rem 0.75rem;
  border: 1px solid #b8c7df;
  border-radius: 0.4rem;
  text-decoration: none;
  font-weight: 700;
  color: #11256c;
  background-color: #ffffff;
}
```

## 5) Validação rápida da versão 4
- O contêiner `.layout-pagina` usa `display: grid`.
- A malha tem duas colunas com funções diferentes (menu e conteúdo).
- `header` e `footer` ocupam a largura total da estrutura.
- O menu lateral está organizado e legível.
- Cards e bloco de destaque continuam funcionando com a base do Encontro 16.

## 6) Erros comuns nesta evolução
- aplicar Grid em um elemento interno e esperar que toda a página mude;
- esquecer de associar `grid-area` aos blocos principais;
- remover regras úteis de Flexbox que ainda são necessárias dentro dos componentes;
- usar largura fixa grande e quebrar a leitura em telas menores;
- alterar demais o HTML e perder continuidade com o projeto anterior.

## 7) Prática Final - Projeto Padrão da Disciplina (Versão 4)
Nesta versão, você mantém tudo que foi construído até o Encontro 16 e adiciona Grid na estrutura global.
O objetivo é consolidar a combinação correta: **Grid para macroestrutura** e **Flexbox para organização interna**.

### Ajustes sugeridos
1. Ajuste a largura da coluna lateral (`grid-template-columns`) e compare legibilidade.
2. Defina uma variação de cor para o menu lateral sem perder contraste de links.
3. Revise espaçamentos entre as áreas da malha (`gap`) e entre blocos internos.
4. Garanta que os cards continuem fluidos com as regras de Flexbox já aplicadas.
5. Faça revisão final de consistência visual entre cabeçalho, menu, conteúdo e rodapé.

### Critérios de validação
- A estrutura global está em Grid com áreas nomeadas.
- O menu lateral e o conteúdo principal estão claramente separados.
- Os componentes internos continuam coerentes com as regras anteriores.
- O projeto evolui sem quebra da base construída nos encontros 14, 15 e 16.

## Materiais para Aprofundamento
- [MDN - CSS Grid Layout](https://developer.mozilla.org/pt-BR/docs/Learn_web_development/Core/CSS_layout/Grids)
- [MDN - `grid-template-columns`](https://developer.mozilla.org/pt-BR/docs/Web/CSS/grid-template-columns)
- [MDN - `grid-template-areas`](https://developer.mozilla.org/pt-BR/docs/Web/CSS/grid-template-areas)
- [MDN - Relação entre Grid e Flexbox](https://developer.mozilla.org/pt-BR/docs/Web/CSS/CSS_grid_layout/Relationship_of_grid_layout_with_other_layout_methods)

## Checklist de Compreensão
- [ ] Consigo ativar Grid no contêiner principal da página.
- [ ] Consigo definir duas colunas com papéis distintos.
- [ ] Consigo mapear áreas nomeadas para os blocos principais.
- [ ] Consigo manter Flexbox onde ele faz mais sentido (componentes internos).
- [ ] Consigo evoluir o mesmo projeto sem recomeçar do zero.

## Resumo Final
Neste encontro, você evoluiu o mesmo Portal da Turma para a versão 4, aplicando Grid na estrutura global e preservando o uso de Flexbox nos componentes internos.
Com isso, o projeto fica pronto para o próximo passo: responsividade com media queries.
