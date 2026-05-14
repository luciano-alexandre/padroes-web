# Encontro 15 - Box Model, Espaçamentos e `display`

**Unidade:** Unidade 1  

## Visão Geral
Neste encontro, você continua exatamente o exemplo corrigido no Encontro 14.
A diferença é que agora o foco sai de "qual regra aplica" e passa para "como cada bloco ocupa espaço".

Você vai evoluir o **Portal da Turma** com box model, bordas, `padding`, `margin`, largura controlada e uso intencional de `display`.

## Conceitos Essenciais
- Revisão aplicada de seletores por elemento, classe e id.
- Herança e cascata no mesmo projeto do encontro anterior.
- Box model: conteúdo, `padding`, `border` e `margin`.
- `width`, `max-width` e centralização de contêiner.
- `box-sizing: border-box`.
- Diferença prática entre `block`, `inline` e `inline-block`.

## 1) Ponto de partida (Encontro 14)
Você já tem:
- estrutura com `header`, `nav`, `main`, seções e `footer`;
- classes como `.bloco-sobre`, `.bloco-aprendizado`, `.destaque`;
- seletor por id no aviso (`#aviso-semana`) para demonstrar especificidade.

Agora, em vez de criar outro exemplo, vamos **evoluir esse mesmo projeto**.

## 2) Objetivo da evolução
Ao final desta aula, o projeto deve ter:
- contêiner centralizado para melhorar leitura;
- blocos com borda, espaçamento interno e externo consistentes;
- menu com links clicáveis em formato de botão usando `inline-block`;
- cartões de conteúdo com borda e espaçamento básicos;
- organização visual pronta para a próxima etapa (Flexbox no Encontro 16).

### Pré-visualização do resultado esperado
![Prévia de como o projeto ficará ao final do Encontro 15](./imagens/encontro-15-exec-resultado.png)

## 3) Passo 1 - HTML evoluído (mesma base, nova organização)
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
        <p class="subtitulo">Projeto padrão da disciplina de Padrões Web</p>
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
          Continuamos o projeto iniciado no encontro anterior, agora aplicando box model
          para controlar espaçamentos e melhorar a legibilidade da página.
        </p>
      </section>

      <section id="exercicios" class="bloco bloco-aprendizado">
        <h2>O que você vai aprender</h2>
        <div class="cards-aprendizado">
          <article class="card">
            <h3>Box Model</h3>
            <p>Separar conteúdo, borda, preenchimento e margem com clareza.</p>
          </article>
          <article class="card">
            <h3>Largura</h3>
            <p>Controlar largura com `max-width` sem quebrar em telas menores.</p>
          </article>
          <article class="card">
            <h3>Display</h3>
            <p>Aplicar `inline-block` em links para criar componentes de navegação.</p>
          </article>
        </div>
      </section>

      <section id="materiais" class="bloco destaque">
        <h2>Aviso importante</h2>
        <p class="aviso" id="aviso-semana">
          Este projeto será reaproveitado e evoluído nos próximos encontros.
        </p>
        <a class="botao" href="#exercicios">Continuar prática</a>
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

### O que evoluiu no HTML?
- inclusão da classe `.container` para controle de largura;
- criação de `.card` para iniciar componentes reutilizáveis;
- inclusão de `.botao` para aplicar `display: inline-block` de forma prática;
- manutenção da base do encontro 14 para garantir continuidade do projeto.

## 4) Passo 2 - CSS 
Neste encontro, vamos adicionar regras novas.
Tudo que já foi trabalhado no Encontro 14 (cores principais, tipografia base, estilos de `.aviso` e `#aviso-semana`) deve ser mantido.


### Etapa 2.1 - Regra 1: cálculo de tamanho previsível
```css
* {
  box-sizing: border-box;
}
```
**Explicação linha a linha**
- `*`: seletor universal, alcança todos os elementos da página.
- `box-sizing`: propriedade que define como largura e altura são calculadas.
- `border-box`: valor que inclui `padding` e `border` dentro da largura/altura total.

**Para que serve no projeto**
- evita "estouro" de largura ao adicionar borda e preenchimento;
- facilita manter cartões e blocos alinhados.

### Etapa 2.2 - Regra 2: remover margem padrão do navegador
```css
body {
  margin: 0;
}
```
**Explicação linha a linha**
- `body`: seleciona o corpo inteiro da página.
- `margin`: propriedade de espaço externo do elemento.
- `0`: remove todas as margens padrão do navegador.

**Para que serve no projeto**
- elimina a borda branca automática;
- permite controlar o espaçamento da página de forma intencional.

### Etapa 2.3 - Regra 3: criar contêiner centralizado
```css
.container {
  width: 92%;
  max-width: 72rem;
  margin: 0 auto;
}
```
**Explicação linha a linha**
- `.container`: seleciona qualquer elemento com classe `container`.
- `width: 92%`: largura fluida, ocupando 92% da área disponível.
- `max-width: 72rem`: limite máximo da largura para não alongar texto em telas grandes.
- `margin: 0 auto`: `0` para topo/baixo e `auto` nas laterais para centralizar.

**Para que serve no projeto**
- melhora a leitura em desktop e notebook;
- mantém o layout responsivo sem usar largura fixa.

### Etapa 2.4 - Regra 4: respiro vertical das faixas
```css
.faixa {
  padding: 1rem 0;
}
```
**Explicação linha a linha**
- `.faixa`: aplica em `header`, `nav` e `footer` (pela classe usada no HTML).
- `padding`: espaço interno entre o conteúdo e a borda do elemento.
- `1rem 0`: `1rem` em cima/baixo e `0` nas laterais.

**Para que serve no projeto**
- cria espaçamento vertical consistente entre as áreas principais;
- melhora legibilidade sem adicionar várias regras separadas.

### Etapa 2.5 - Regra 5: box model dos blocos principais
```css
.bloco {
  margin-bottom: 1rem;
  padding: 1rem;
  border: 1px solid #c6d6ea;
  border-radius: 0.5rem;
}
```
**Explicação linha a linha**
- `.bloco`: classe-base para as seções principais do `main`.
- `margin-bottom: 1rem`: espaço externo abaixo de cada bloco.
- `padding: 1rem`: espaço interno entre conteúdo e borda.
- `border: 1px solid #c6d6ea`: borda com espessura `1px`, estilo `solid` e cor definida.
- `border-radius: 0.5rem`: arredonda os cantos do bloco.

**Para que serve no projeto**
- torna visível a diferença entre margem, preenchimento e borda;
- dá unidade visual às seções do conteúdo.

### Etapa 2.6 - Regra 6: links do menu como botões com `display`
```css
.menu > .container a {
  display: inline-block;
  padding: 0.5rem 0.85rem;
  margin-right: 0.4rem;
  border: 1px solid #b8c7df;
  border-radius: 0.4rem;
  text-decoration: none;
  font-weight: 700;
}
```
**Explicação linha a linha**
- `.menu > .container a`: seleciona links `a` dentro do `.container` filho direto de `.menu`.
- `display: inline-block`: o link continua em linha, mas passa a aceitar largura/altura, `padding` e `margin` como bloco.
- `padding: 0.5rem 0.85rem`: aumenta a área clicável do link.
- `margin-right: 0.4rem`: separa horizontalmente um item do menu do próximo.
- `border: 1px solid #b8c7df`: contorno para reforçar aparência de componente.
- `border-radius: 0.4rem`: cantos arredondados.
- `text-decoration: none`: remove sublinhado padrão.
- `font-weight: 700`: deixa o texto do menu em negrito.

**Para que serve no projeto**
- transforma navegação em componentes clicáveis claros;
- introduz `display` de forma prática e visual.

### Etapa 2.7 - Regra 7: botão de ação do bloco de destaque
```css
.botao {
  display: inline-block;
  padding: 0.6rem 1rem;
  border-radius: 0.4rem;
  text-decoration: none;
  font-weight: 700;
  color: #ffffff;
  background-color: #1f4a8a;
}
```
**Explicação linha a linha**
- `.botao`: seleciona o link que funciona como chamada para ação.
- `display: inline-block`: permite tratar o link como botão visual.
- `padding: 0.6rem 1rem`: amplia área de clique.
- `border-radius: 0.4rem`: canto arredondado.
- `text-decoration: none`: remove sublinhado.
- `font-weight: 700`: reforça o texto da ação.
- `color: #ffffff`: define texto branco para contraste.
- `background-color: #1f4a8a`: cria o fundo azul do botão.

**Para que serve no projeto**
- reforça a ideia de ação principal ("Continuar prática");
- mantém consistência com os links do menu.

### Etapa 2.8 - Regra 8: acabamento visual dos cartões internos
```css
.card {
  margin-bottom: 0.75rem;
  padding: 0.85rem;
  border: 1px solid #aac1df;
  border-radius: 0.4rem;
}
```
**Explicação linha a linha**
- `.card`: seleciona cada cartão dentro da seção de aprendizado.
- `margin-bottom: 0.75rem`: separa um cartão do outro.
- `padding: 0.85rem`: cria respiro interno para o texto.
- `border: 1px solid #aac1df`: desenha contorno leve em cada cartão.
- `border-radius: 0.4rem`: suaviza os cantos.

**Para que serve no projeto**
- evidencia visualmente os três tópicos de aprendizado;
- prepara a estrutura para virar grid/flex no encontro seguinte.

### CSS novo deste encontro (resumo)
```css
* {
  box-sizing: border-box;
}

body {
  margin: 0;
}

.container {
  width: 92%;
  max-width: 72rem;
  margin: 0 auto;
}

.faixa {
  padding: 1rem 0;
}

.bloco {
  margin-bottom: 1rem;
  padding: 1rem;
  border: 1px solid #c6d6ea;
  border-radius: 0.5rem;
}

.menu > .container a {
  display: inline-block;
  padding: 0.5rem 0.85rem;
  margin-right: 0.4rem;
  border: 1px solid #b8c7df;
  border-radius: 0.4rem;
  text-decoration: none;
  font-weight: 700;
}

.botao {
  display: inline-block;
  padding: 0.6rem 1rem;
  border-radius: 0.4rem;
  text-decoration: none;
  font-weight: 700;
  color: #ffffff;
  background-color: #1f4a8a;
}

.card {
  margin-bottom: 0.75rem;
  padding: 0.85rem;
  border: 1px solid #aac1df;
  border-radius: 0.4rem;
}
```

## 5) Validação rápida da versão 2
- O conteúdo principal não fica "colado" nas bordas da tela.
- Blocos e cartões têm espaçamentos consistentes.
- Links do menu parecem componentes clicáveis.
- O aviso mantém o exemplo de especificidade já estudado.
- O CSS novo está enxuto e focado nas 8 regras deste encontro.
- O projeto está pronto para migração para Flexbox no encontro seguinte.

## 6) Erros comuns nesta evolução
- adicionar `width` fixa e quebrar em telas menores;
- confundir `padding` interno com `margin` externo;
- esquecer `box-sizing` e perder controle do tamanho final;
- remover classes antigas do encontro 14 e quebrar continuidade;
- usar id em vários elementos (id deve ser único).

## 7) Prática Final - Projeto Padrão da Disciplina (Versão 2)
A partir deste encontro, este exemplo vira o **projeto padrão da disciplina** e será evoluído aula após aula.

## Materiais para Aprofundamento
- [MDN - Box model](https://developer.mozilla.org/pt-BR/docs/Learn_web_development/Core/Styling_basics/Box_model)
- [MDN - `box-sizing`](https://developer.mozilla.org/pt-BR/docs/Web/CSS/box-sizing)
- [MDN - `display`](https://developer.mozilla.org/pt-BR/docs/Web/CSS/display)
- [MDN - `max-width`](https://developer.mozilla.org/pt-BR/docs/Web/CSS/max-width)

## Checklist de Compreensão
- [ ] Consigo evoluir um projeto existente sem recomeçar do zero.
- [ ] Consigo aplicar box model para organizar visualmente a página.
- [ ] Consigo justificar o uso de `inline-block` em links e botões.
- [ ] Consigo manter conceitos de seletores e especificidade enquanto amplio o layout.
- [ ] Consigo preparar a base para a próxima aula (Flexbox).

## Resumo Final
Neste encontro, você não criou apenas um exercício isolado: você evoluiu o projeto do encontro anterior para uma versão mais robusta.
Com isso, nasce o projeto padrão da disciplina, que será expandido nas próximas aulas com técnicas de layout mais avançadas.
