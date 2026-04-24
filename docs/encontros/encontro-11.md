# Encontro 11 - Correção Guiada da Avaliação 01

**Unidade:** Unidade 1  
**Referência:** Correção da Avaliação 01 (HTML)

## Visão Geral
Neste encontro, você faz a correção guiada da atividade avaliativa sobre a página **"Achados e Perdidos - Festival da Luz"**.
O foco é revisar cada requisito do enunciado, entender uma solução possível e reforçar os critérios técnicos que diferenciam uma página apenas "completa" de uma página bem estruturada.

Se no Encontro 10 você resolveu a atividade de forma autoral, agora você compara sua implementação com uma proposta comentada e identifica ajustes importantes.

## Conceitos Essenciais
- Leitura do enunciado por blocos de requisito.
- Planejamento da página antes da implementação.
- Coerência entre semântica, conteúdo e navegação.
- Revisão de atributos obrigatórios em mídia, tabela e formulário.
- Validação final do HTML antes de considerar a atividade concluída.

## 1) Leitura técnica do enunciado
Antes de corrigir, o primeiro passo é decompor a atividade em partes menores:
- estrutura HTML5 completa;
- landmarks semânticos obrigatórios;
- conteúdo textual e navegação;
- mídia com créditos;
- tabela com 5 itens;
- formulário com validação nativa.

Essa separação evita esquecer requisitos e ajuda a montar a página de forma progressiva.

## 2) Planejamento da página
Uma organização coerente para essa atividade pode ser:
- `header` com título e descrição do serviço;
- `nav` com links internos para consulta, retirada e formulário;
- `main` com 3 `section`;
- `article` para explicar o fluxo de retirada;
- `aside` com orientações rápidas;
- `footer` com créditos e retorno ao topo.

## 3) Passo 1 - Estrutura base do documento
Começamos com a base mínima obrigatória do HTML5:

```html
<!doctype html>
<html lang="pt-BR">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Achados e Perdidos - Festival da Luz</title>
  </head>
  <body>
  </body>
</html>
```

### O que foi atendido aqui?
- estrutura HTML5 completa;
- idioma da página definido em `lang`;
- metadados básicos para renderização correta.

## 4) Passo 2 - Cabeçalho e navegação
Agora criamos a abertura da página com um único `h1` e um menu interno:

```html
<header>
  <h1 id="topo">Achados e Perdidos - Festival da Luz</h1>
  <p>Consulte itens encontrados, entenda o procedimento de retirada e registre sua solicitação.</p>
</header>

<nav aria-label="Navegação principal">
  <a href="#itens">Itens encontrados</a> |
  <a href="#retirada">Como retirar</a> |
  <a href="#formulario">Registrar busca</a>
</nav>
```

### O que foi atendido aqui?
- `header` e `nav`;
- um único `h1`;
- pelo menos 1 link interno funcional.

## 5) Passo 3 - Estrutura semântica principal
O enunciado pede `main`, pelo menos 3 `section`, 1 `article`, 1 `aside` e `footer`.
Uma forma de cumprir isso é:

```html
<main>
  <section id="apresentacao">
    <h2>Sobre o serviço</h2>
    <p>Durante o Festival da Luz, os objetos encontrados são registrados e disponibilizados para consulta nesta página.</p>
  </section>

  <section id="itens">
    <h2>Itens encontrados</h2>
  </section>

  <section id="retirada">
    <h2>Como retirar um item</h2>
    <article>
      <h3>Procedimento de conferência</h3>
      <p>O visitante deve apresentar informações compatíveis com o item perdido para validação da equipe.</p>
    </article>
  </section>

  <aside>
    <h2>Orientação rápida</h2>
    <p>Revise data, categoria e descrição antes de enviar a solicitação.</p>
  </aside>
</main>
```

### O que foi atendido aqui?
- `main`;
- 3 `section`;
- 1 `article`;
- 1 `aside`.

## 6) Passo 4 - Conteúdo textual, listas e link externo
O enunciado também exige parágrafos curtos, uma lista não ordenada, uma lista ordenada e pelo menos 1 link externo funcional.

```html
<section id="apresentacao">
  <h2>Sobre o serviço</h2>
  <p>Durante o evento, a equipe centraliza o registro de objetos encontrados em diferentes pontos do festival.</p>
  <p>Os dados abaixo ajudam visitantes a localizar pertences e solicitar atendimento.</p>

  <h3>Tipos de itens recebidos</h3>
  <ul>
    <li>Documentos pessoais</li>
    <li>Acessórios eletrônicos</li>
    <li>Objetos de uso pessoal</li>
  </ul>

  <h3>Etapas para recuperar um objeto</h3>
  <ol>
    <li>Consultar a lista de itens encontrados.</li>
    <li>Verificar local e data do registro.</li>
    <li>Preencher o formulário com as informações do item perdido.</li>
  </ol>

  <p>
    Para conhecer a programação oficial do evento, acesse
    <a href="https://portal.ifrn.edu.br/" target="_blank" rel="noopener noreferrer">o portal institucional do IFRN</a>.
  </p>
</section>
```

### O que foi atendido aqui?
- parágrafos curtos;
- lista `ul`;
- lista `ol`;
- link externo funcional.

## 7) Passo 5 - Figure, mídia e créditos
Agora inserimos a parte de mídia com contexto e licença.

```html
<section>
  <h2>Central de atendimento</h2>

  <figure>
    <img
      src="./assets/festival-da-luz.jpg"
      alt="Equipe de atendimento organizando objetos encontrados durante o Festival da Luz"
      width="640"
    />
    <figcaption>Figura 1 - Posto de apoio do serviço de achados e perdidos.</figcaption>
  </figure>

  <audio controls>
    <source src="./assets/aviso-festival.mp3" type="audio/mpeg" />
    Seu navegador não suporta áudio HTML5.
  </audio>

  <p>
    Créditos: imagem de uso educacional autorizada pela organização do evento; áudio institucional utilizado
    apenas para fins didáticos.
  </p>
</section>
```

### O que foi atendido aqui?
- `figure` com `img`, `alt` e `figcaption`;
- `audio` com `controls`;
- bloco de créditos/licença.

## 8) Passo 6 - Tabela com itens simulados
A tabela precisa ter `caption`, `thead`, `tbody`, `th` e `td`, com pelo menos 5 itens.

```html
<section>
  <h2>Itens encontrados</h2>

  <table>
    <caption>Registro de itens recebidos pela equipe</caption>
    <thead>
      <tr>
        <th scope="col">Item</th>
        <th scope="col">Local encontrado</th>
        <th scope="col">Data</th>
        <th scope="col">Categoria</th>
        <th scope="col">Situação</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Carteira preta</td>
        <td>Praça de alimentação</td>
        <td>22/04/2026</td>
        <td>Documento</td>
        <td>Aguardando identificação</td>
      </tr>
      <tr>
        <td>Celular azul</td>
        <td>Palco principal</td>
        <td>22/04/2026</td>
        <td>Eletrônico</td>
        <td>Em conferência</td>
      </tr>
      <tr>
        <td>Chaveiro com 3 chaves</td>
        <td>Entrada norte</td>
        <td>23/04/2026</td>
        <td>Acessório</td>
        <td>Disponível para retirada</td>
      </tr>
      <tr>
        <td>Mochila cinza</td>
        <td>Área de oficinas</td>
        <td>23/04/2026</td>
        <td>Uso pessoal</td>
        <td>Aguardando identificação</td>
      </tr>
      <tr>
        <td>Documento estudantil</td>
        <td>Auditório</td>
        <td>23/04/2026</td>
        <td>Documento</td>
        <td>Disponível para retirada</td>
      </tr>
    </tbody>
  </table>
</section>
```

### O que foi atendido aqui?
- tabela completa com os elementos pedidos;
- 5 linhas de dados simulados;
- colunas coerentes com o enunciado.

## 9) Passo 7 - Formulário com validação nativa
Por fim, montamos o formulário com todos os campos obrigatórios, `label` associada e múltiplas validações nativas.

```html
<section id="formulario">
  <h2>Registrar item perdido</h2>

  <form action="#" method="post">
    <p>
      <label for="nome">Nome completo</label><br />
      <input id="nome" name="nome" type="text" required minlength="3" maxlength="80" />
    </p>

    <p>
      <label for="email">E-mail</label><br />
      <input id="email" name="email" type="email" required />
    </p>

    <p>
      <label for="telefone">Telefone</label><br />
      <input id="telefone" name="telefone" type="tel" required pattern="[0-9]{10,11}" />
    </p>

    <p>
      <label for="categoria">Categoria do item</label><br />
      <select id="categoria" name="categoria" required>
        <option value="">Selecione</option>
        <option value="documento">Documento</option>
        <option value="eletronico">Eletrônico</option>
        <option value="acessorio">Acessório</option>
        <option value="uso-pessoal">Uso pessoal</option>
      </select>
    </p>

    <p>
      <label for="data-perda">Data aproximada da perda</label><br />
      <input id="data-perda" name="data-perda" type="date" required />
    </p>

    <p>
      <label for="descricao">Descrição detalhada</label><br />
      <textarea id="descricao" name="descricao" rows="5" cols="40" required minlength="20" maxlength="300"></textarea>
    </p>

    <p>
      <label for="protocolo">Protocolo ou documento</label><br />
      <input id="protocolo" name="protocolo" type="text" required pattern="[A-Z0-9]{6,12}" />
    </p>

    <p>
      <input id="confirmacao" name="confirmacao" type="checkbox" required />
      <label for="confirmacao">Confirmo que as informações enviadas são verdadeiras.</label>
    </p>

    <p>
      <button type="submit">Enviar solicitação</button>
      <button type="reset">Limpar formulário</button>
    </p>
  </form>
</section>
```

### O que foi atendido aqui?
- todos os campos pedidos no enunciado;
- `label` associada com `for` e `id`;
- validações com `required`, `minlength`, `maxlength`, `type="email"`, `type="date"` e `pattern`;
- botões de envio e limpeza.

## 10) Solução completa sugerida (`index.html`)
```html
<!doctype html>
<html lang="pt-BR">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Achados e Perdidos - Festival da Luz</title>
  </head>
  <body>
    <header>
      <h1 id="topo">Achados e Perdidos - Festival da Luz</h1>
      <p>Consulte itens encontrados, entenda como retirar um objeto e registre sua solicitação.</p>
    </header>

    <nav aria-label="Navegação principal">
      <a href="#itens">Itens encontrados</a> |
      <a href="#retirada">Como retirar</a> |
      <a href="#formulario">Registrar busca</a>
    </nav>

    <main>
      <section id="apresentacao">
        <h2>Sobre o serviço</h2>
        <p>Durante o Festival da Luz, a equipe registra objetos encontrados em diferentes espaços do evento.</p>
        <p>As informações desta página ajudam visitantes a localizar pertences e iniciar a conferência com a organização.</p>

        <h3>Tipos de itens recebidos</h3>
        <ul>
          <li>Documentos pessoais</li>
          <li>Acessórios eletrônicos</li>
          <li>Objetos de uso pessoal</li>
        </ul>

        <h3>Etapas para recuperar um objeto</h3>
        <ol>
          <li>Consultar a tabela de itens encontrados.</li>
          <li>Verificar local e data do registro.</li>
          <li>Preencher o formulário com o máximo de detalhes possível.</li>
        </ol>

        <p>
          Mais informações institucionais podem ser acessadas no
          <a href="https://portal.ifrn.edu.br/" target="_blank" rel="noopener noreferrer">portal do IFRN</a>.
        </p>
      </section>

      <section id="itens">
        <h2>Itens encontrados</h2>

        <figure>
          <img
            src="./assets/festival-da-luz.jpg"
            alt="Equipe de atendimento organizando objetos encontrados durante o Festival da Luz"
            width="640"
          />
          <figcaption>Figura 1 - Posto de atendimento do serviço de achados e perdidos.</figcaption>
        </figure>

        <audio controls>
          <source src="./assets/aviso-festival.mp3" type="audio/mpeg" />
          Seu navegador não suporta áudio HTML5.
        </audio>

        <table>
          <caption>Registro de itens recebidos pela equipe</caption>
          <thead>
            <tr>
              <th scope="col">Item</th>
              <th scope="col">Local encontrado</th>
              <th scope="col">Data</th>
              <th scope="col">Categoria</th>
              <th scope="col">Situação</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>Carteira preta</td>
              <td>Praça de alimentação</td>
              <td>22/04/2026</td>
              <td>Documento</td>
              <td>Aguardando identificação</td>
            </tr>
            <tr>
              <td>Celular azul</td>
              <td>Palco principal</td>
              <td>22/04/2026</td>
              <td>Eletrônico</td>
              <td>Em conferência</td>
            </tr>
            <tr>
              <td>Chaveiro com 3 chaves</td>
              <td>Entrada norte</td>
              <td>23/04/2026</td>
              <td>Acessório</td>
              <td>Disponível para retirada</td>
            </tr>
            <tr>
              <td>Mochila cinza</td>
              <td>Área de oficinas</td>
              <td>23/04/2026</td>
              <td>Uso pessoal</td>
              <td>Aguardando identificação</td>
            </tr>
            <tr>
              <td>Documento estudantil</td>
              <td>Auditório</td>
              <td>23/04/2026</td>
              <td>Documento</td>
              <td>Disponível para retirada</td>
            </tr>
          </tbody>
        </table>
      </section>

      <section id="retirada">
        <h2>Como retirar um item</h2>

        <article>
          <h3>Procedimento de conferência</h3>
          <p>Apresente informações compatíveis com o item perdido para validação da equipe responsável.</p>
          <p>Quando necessário, um documento complementar pode ser solicitado para confirmar a posse.</p>
        </article>

        <p>
          Créditos: imagem de uso educacional autorizada pela organização do evento; áudio institucional
          utilizado apenas para fins didáticos.
        </p>
      </section>

      <section id="formulario">
        <h2>Registrar item perdido</h2>

        <form action="#" method="post">
          <p>
            <label for="nome">Nome completo</label><br />
            <input id="nome" name="nome" type="text" required minlength="3" maxlength="80" />
          </p>

          <p>
            <label for="email">E-mail</label><br />
            <input id="email" name="email" type="email" required />
          </p>

          <p>
            <label for="telefone">Telefone</label><br />
            <input id="telefone" name="telefone" type="tel" required pattern="[0-9]{10,11}" />
          </p>

          <p>
            <label for="categoria">Categoria do item</label><br />
            <select id="categoria" name="categoria" required>
              <option value="">Selecione</option>
              <option value="documento">Documento</option>
              <option value="eletronico">Eletrônico</option>
              <option value="acessorio">Acessório</option>
              <option value="uso-pessoal">Uso pessoal</option>
            </select>
          </p>

          <p>
            <label for="data-perda">Data aproximada da perda</label><br />
            <input id="data-perda" name="data-perda" type="date" required />
          </p>

          <p>
            <label for="descricao">Descrição detalhada</label><br />
            <textarea id="descricao" name="descricao" rows="5" cols="40" required minlength="20" maxlength="300"></textarea>
          </p>

          <p>
            <label for="protocolo">Protocolo ou documento</label><br />
            <input id="protocolo" name="protocolo" type="text" required pattern="[A-Z0-9]{6,12}" />
          </p>

          <p>
            <input id="confirmacao" name="confirmacao" type="checkbox" required />
            <label for="confirmacao">Confirmo que as informações enviadas são verdadeiras.</label>
          </p>

          <p>
            <button type="submit">Enviar solicitação</button>
            <button type="reset">Limpar formulário</button>
          </p>
        </form>
      </section>

      <aside>
        <h2>Dica de conferência</h2>
        <p>Antes de enviar, revise categoria, data aproximada e descrição do item para facilitar o atendimento.</p>
      </aside>
    </main>

    <footer>
      <p>Disciplina de Padrões Web - Correção guiada da Avaliação 01.</p>
      <p><a href="#topo">Voltar ao início</a></p>
    </footer>
  </body>
</html>
```

## 11) Validação rápida da correção
- Há apenas um `h1`.
- A página contém `header`, `nav`, `main`, 4 `section`, `article`, `aside` e `footer`.
- Existe pelo menos 1 link interno e 1 link externo.
- Há uma `figure` com `img`, `alt` e `figcaption`.
- Existe mídia com `controls`.
- A tabela possui todos os elementos exigidos e 5 itens simulados.
- O formulário possui todos os campos solicitados.
- As validações nativas são suficientes e coerentes.

## 12) Erros frequentes observados na atividade
- esquecer o `aside` ou o `article`;
- usar link interno sem criar o `id` de destino;
- inserir imagem sem `alt` descritivo;
- criar tabela apenas com `tr` e `td`, sem `caption`, `thead` e `th`;
- deixar campos sem `label` associada;
- usar `pattern` incompatível com o valor esperado;
- esquecer o `required` em campos centrais do formulário.

## Materiais para Aprofundamento
- [MDN - HTML: Linguagem de Marcação de Hipertexto](https://developer.mozilla.org/pt-BR/docs/Web/HTML)
- [MDN - Guia de semântica em HTML](https://developer.mozilla.org/pt-BR/docs/Glossary/Semantics)
- [MDN - Elemento `<audio>`](https://developer.mozilla.org/pt-BR/docs/Web/HTML/Reference/Elements/audio)
- [MDN - Elemento `<table>`](https://developer.mozilla.org/pt-BR/docs/Web/HTML/Reference/Elements/table)
- [MDN - Validação de formulários no lado do cliente](https://developer.mozilla.org/pt-BR/docs/Learn_web_development/Extensions/Forms/Form_validation)
- [W3C Markup Validation Service](https://validator.w3.org/)

## Checklist de Compreensão
- [ ] Consigo decompor um enunciado em blocos de implementação.
- [ ] Consigo corrigir uma página HTML verificando requisito por requisito.
- [ ] Consigo montar tabela e formulário com a estrutura exigida.
- [ ] Consigo identificar onde minha solução difere de uma resposta técnica adequada.
- [ ] Consigo revisar meu HTML com mais autonomia após a correção.

## Resumo Final
Neste encontro, você revisou a Avaliação 01 de forma guiada, entendendo não apenas "o que deveria estar na página", mas como organizar cada requisito com clareza e consistência. Essa correção fortalece sua base em HTML e prepara melhor a transição para os próximos conteúdos da disciplina.
