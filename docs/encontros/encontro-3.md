# Encontro 3 - Ambiente de desenvolvimento (editor, navegador, DevTools)

**Unidade:** Unidade 1  
**Carga prevista:** 1,5h  
**Entregável previsto:** Ambiente configurado e validação prática de depuração

## Visão Geral
Este encontro consolida o ambiente de trabalho do estudante para o restante da disciplina. O foco é compreender como **editor**, **terminal**, **navegador** e **DevTools** atuam juntos no ciclo real de desenvolvimento front-end.

Ao final da aula, o estudante deve conseguir:
- criar e organizar a estrutura inicial de um projeto web;
- editar arquivos HTML e CSS no editor de código com boas práticas básicas;
- usar o terminal para operações simples de navegação e execução local;
- inspecionar e corrigir problemas com DevTools (Elements, Console e Network);
- executar um ciclo completo: **editar -> salvar -> testar -> depurar -> corrigir**.

## Objetivos de Aprendizagem
- Compreender o papel de cada ferramenta no fluxo de desenvolvimento.
- Adotar uma organização mínima de pastas e arquivos para evitar retrabalho.
- Ler erros no navegador e transformar erros em ações de correção.
- Ganhar autonomia para estudar e praticar sem depender de copiar código pronto.

## Materiais e Preparação
- Editor: VS Code (ou equivalente).
- Navegador: Firefox, Chrome ou Edge.
- Terminal integrado do editor (ou terminal do sistema).
- DevTools do navegador habilitado (atalho: `F12` ou `Ctrl+Shift+I`).

Estrutura sugerida para a aula:
```text
encontro-3-lab/
  index.html
  css/
    style.css
  assets/
```

## Roteiro de Aula (90 minutos)

| Tempo | Bloco | Objetivo |
|---:|---|---|
| 0-10 min | Abertura e alinhamento | Apresentar fluxo de trabalho e critérios da aula |
| 10-25 min | Setup guiado do ambiente | Configurar pasta, arquivos e editor |
| 25-40 min | Terminal essencial | Navegar em diretórios e validar estrutura |
| 40-60 min | Navegador e DevTools | Inspecionar HTML/CSS e ler mensagens de erro |
| 60-80 min | Oficina de depuração | Corrigir erros propostos em arquivo com bugs |
| 80-90 min | Fechamento e checagem | Consolidar checklist e orientar estudo autônomo |

## 1) Editor de código e organização de projeto
Trabalhar sem organização gera perda de tempo, arquivos duplicados e dificuldade para localizar erros.

### Estrutura mínima recomendada
```text
meu-projeto/
  index.html
  css/
    style.css
  assets/
```

### Boas práticas iniciais
- nomes de arquivo em minúsculas e sem espaços;
- separar HTML, CSS e assets;
- manter identação consistente;
- salvar frequentemente durante a implementação.

### Exemplo de `index.html` inicial
```html
<!doctype html>
<html lang="pt-BR">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Laboratório do Encontro 3</title>
    <link rel="stylesheet" href="css/style.css" />
  </head>
  <body>
    <main class="container">
      <h1>Ambiente de Desenvolvimento</h1>
      <p id="status">Projeto iniciado com sucesso.</p>
      <button id="btn-teste">Testar console</button>
    </main>

    <script>
      const btn = document.querySelector("#btn-teste");
      btn.addEventListener("click", () => {
        console.log("Clique registrado no botão de teste.");
      });
    </script>
  </body>
</html>
```

### Exemplo de `css/style.css`
```css
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: #f4f7fb;
  color: #1f2937;
}

.container {
  max-width: 720px;
  margin: 2rem auto;
  padding: 1.25rem;
  background: #ffffff;
  border: 1px solid #dbe2ea;
  border-radius: 8px;
}

button {
  padding: 0.6rem 0.9rem;
  border: 0;
  border-radius: 6px;
  background: #0f4c81;
  color: #ffffff;
  cursor: pointer;
}
```

## 2) Terminal essencial para front-end iniciante
O terminal acelera tarefas simples e ajuda a entender onde os arquivos realmente estão.

Comandos básicos para praticar em aula:
```bash
pwd
ls
mkdir -p encontro-3-lab/css encontro-3-lab/assets
cd encontro-3-lab
touch index.html css/style.css
```

Competência esperada no fim deste bloco:
- saber em qual pasta está (`pwd`);
- listar arquivos e pastas (`ls`);
- criar estrutura inicial de projeto (`mkdir`, `touch`);
- navegar entre diretórios (`cd`).

## 3) Navegador e DevTools na prática
DevTools é a principal ferramenta de depuração no front-end.

### Painéis essenciais para este encontro
- **Elements:** inspeção de estrutura HTML e estilos aplicados.
- **Console:** leitura de logs e erros JavaScript.
- **Network:** visualização do carregamento de arquivos (status, tempo e falhas).

### Rotina de depuração sugerida
1. Abrir a página no navegador.
2. Abrir DevTools (`F12`).
3. Validar se o HTML esperado aparece no **Elements**.
4. Confirmar se o CSS foi carregado no **Network**.
5. Verificar mensagens de erro no **Console**.
6. Corrigir no editor e testar novamente.

## 4) Oficina guiada de depuração (20 minutos)
A atividade simula erros comuns de iniciantes.

### Arquivo com erros intencionais
```html
<!doctype html>
<html lang="pt-BR">
  <head>
    <meta charset="UTF-8" />
    <title>Debug Aula 3</title>
    <link rel="stylesheet" href="css/stlye.css" />
  </head>
  <body>
    <main>
      <h1>Teste de Depuração</h1>
      <p id="mensagem">Clique no botão para testar.</p>
      <button id="btn">Executar</button>
    </main>

    <script>
      const botao = document.querySelector("#btn");
      botao.addEventListener("click", () => {
        document.querySelector("#msg").textContent = "Executado!";
      });
    </script>
  </body>
</html>
```

### Missão do estudante
- identificar por que o CSS não carregou;
- identificar por que o texto não atualiza ao clicar no botão;
- corrigir os erros e validar no navegador.

### Gabarito técnico esperado
- `stlye.css` -> `style.css`;
- `#msg` -> `#mensagem`.

## 5) Estratégia didática para condução da aula
- começar com demonstração curta (professor codando ao vivo);
- migrar para prática guiada em pares;
- interromper em pontos-chave para leitura coletiva do Console;
- fechar com verificação individual usando checklist de entrega.

Perguntas de mediação recomendadas:
- "Qual ferramenta mostra o erro primeiro: editor, navegador ou DevTools?"
- "Como você comprovou que o CSS foi carregado?"
- "Qual foi a hipótese inicial e como você validou?"

## 6) Avaliação formativa do encontro
Critérios mínimos de sucesso na aula:
- estrutura de pastas criada corretamente;
- `index.html` e `style.css` conectados;
- uso de pelo menos um comando de terminal com autonomia;
- identificação e correção de ao menos dois erros de depuração;
- explicação verbal do ciclo editar-testar-corrigir.

## Erros comuns de iniciantes
- editar arquivo em pasta errada;
- esquecer de salvar antes de testar;
- ignorar mensagens do Console;
- tentar corrigir sem reproduzir o erro;
- alterar muitas coisas ao mesmo tempo e perder rastreabilidade.

## Checklist de compreensão
- [ ] Consegui criar a estrutura inicial do projeto sem ajuda direta.
- [ ] Sei abrir e usar o terminal para navegar no projeto.
- [ ] Sei abrir DevTools e localizar erro no Console.
- [ ] Sei verificar no Network se um arquivo carregou corretamente.
- [ ] Corrigi o exercício de depuração com validação no navegador.

## Atividade pós-aula (20-30 min)
1. Criar uma nova pasta de projeto com a mesma estrutura do encontro.
2. Montar uma página simples com título, parágrafo e botão.
3. Inserir propositalmente um erro de caminho no CSS e corrigi-lo usando DevTools.
4. Registrar em 5 linhas: "erro encontrado -> evidência -> correção aplicada".

## Materiais para aprofundamento
- [MDN - Getting started with the web](https://developer.mozilla.org/en-US/docs/Learn_web_development/Getting_started)
- [MDN - What are browser developer tools?](https://developer.mozilla.org/en-US/docs/Learn_web_development/Howto/Tools_and_setup/What_are_browser_developer_tools)
- [VS Code Docs](https://code.visualstudio.com/docs)
- [MDN - Debugging HTML](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content/Debugging_HTML)

## Resumo final
Neste encontro, o estudante estruturou o ambiente essencial para todo o semestre. A síntese técnica é: **organização de projeto + terminal básico + DevTools + rotina iterativa** formam a base prática para desenvolver com segurança, velocidade e autonomia.

## Questões de fixação (com gabarito)
1. Qual é o papel do DevTools no fluxo de desenvolvimento?
Gabarito: Inspecionar estrutura, estilos, rede e erros para orientar correções com evidência.

2. Como confirmar que um CSS foi carregado corretamente?
Gabarito: Verificar no painel Network/Elements se o arquivo foi requisitado com sucesso e os estilos estão aplicados.

3. Qual vantagem de usar terminal em projetos web iniciais?
Gabarito: Navegar, criar estrutura e manipular arquivos com mais controle e rapidez.

4. Qual é o ciclo mínimo de trabalho recomendado na aula?
Gabarito: Editar, salvar, testar no navegador, depurar no DevTools e corrigir.

5. Cite um erro comum e uma ação preventiva.
Gabarito: Erro comum: esquecer de salvar; prevenção: salvar a cada alteração pequena antes de testar.
