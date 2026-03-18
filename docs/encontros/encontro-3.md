# Encontro 3 - Ambiente de desenvolvimento (editor, navegador, DevTools)

**Unidade:** Unidade 1  
**Carga prevista:** 1,5h  

## Visão Geral
Este encontro apresenta o ambiente de trabalho que você vai usar em toda a disciplina. O foco é entender como **editor de código**, **terminal**, **navegador** e **DevTools** funcionam juntos para criar, testar e corrigir páginas web com autonomia.

Se no Encontro 1 você entendeu o papel de HTML/CSS/JavaScript e no Encontro 2 você entendeu como a Web funciona na rede, aqui você aprende **como trabalhar na prática**, com método e organização.

## Conceitos Essenciais
- O que compõe um ambiente de desenvolvimento front-end.
- Como organizar arquivos e pastas de um projeto web.
- Papel do editor de código no fluxo de trabalho.
- Papel do navegador e do DevTools na depuração.
- Ciclo iterativo: **editar -> salvar -> testar -> corrigir**.

## 1) O que é ambiente de desenvolvimento?
Ambiente de desenvolvimento é o conjunto de ferramentas usadas para criar software. No contexto desta disciplina, ele é composto por:

- **Editor de código** para escrever e organizar arquivos;
- **Terminal** para navegar nas pastas e executar comandos;
- **Navegador** para visualizar e testar páginas;
- **DevTools** para inspecionar, diagnosticar e corrigir erros.

Sem esse ambiente configurado corretamente, mesmo conteúdos simples de HTML e CSS viram fonte de confusão.

## 2) Editor de código: onde o projeto nasce
O editor é o lugar onde você escreve HTML, CSS e JavaScript. Ele não "executa" a página sozinho; ele prepara os arquivos para que o navegador interprete.

### O que configurar no início
- pasta de projeto clara;
- arquivos com nomes consistentes;
- identação padronizada;
- salvamento frequente.

### Estrutura inicial recomendada
```text
meu-projeto/
  index.html
  css/
    style.css
  assets/
```

### Por que essa estrutura importa?
Porque evita erros comuns como:
- CSS não carregar por caminho errado;
- arquivo em pasta errada;
- dificuldade de manutenção quando o projeto cresce.

## 3) Terminal: controle e organização do projeto
O terminal ajuda a manipular arquivos e diretórios com rapidez e clareza.

Comandos básicos úteis para iniciantes:
```bash
pwd
ls
mkdir -p meu-projeto/css meu-projeto/assets
cd meu-projeto
touch index.html css/style.css
```

### Leitura prática dos comandos
- `pwd`: mostra onde você está no sistema;
- `ls`: lista arquivos e pastas;
- `mkdir`: cria pastas;
- `cd`: entra em uma pasta;
- `touch`: cria arquivos.

Saber isso já reduz muito erro operacional no começo da aprendizagem.

## 4) Navegador: onde o código vira interface
O navegador interpreta seus arquivos e renderiza a página. Ele é o primeiro validador do seu trabalho.

Quando você abre `index.html`, o navegador:
1. lê o HTML;
2. carrega o CSS vinculado;
3. executa JavaScript (se houver);
4. mostra o resultado na tela.

Se algo não aparecer como esperado, isso **não significa fracasso**. Significa que é hora de depurar com método.

## 5) DevTools: ferramenta central de depuração
DevTools (Ferramentas de Desenvolvedor) é o painel técnico do navegador.

Atalho comum: `F12` ou `Ctrl+Shift+I`.

### Painéis mais importantes neste momento
- **Elements**: mostra o HTML final e os estilos aplicados.
- **Console**: mostra logs e erros de JavaScript.
- **Network**: mostra o carregamento dos arquivos (HTML, CSS, JS, imagens).

### O que verificar primeiro quando algo dá errado
1. O arquivo certo está aberto no navegador?
2. O CSS está realmente vinculado no `<head>`?
3. O caminho do arquivo está correto?
4. Há erro visível no Console?
5. O arquivo retornou erro no Network?

## 6) Fluxo profissional básico: editar, salvar, testar, corrigir
Esse ciclo é o coração do trabalho front-end:

1. **Editar** uma pequena parte do código.
2. **Salvar** o arquivo.
3. **Testar** no navegador.
4. **Observar** o resultado e mensagens do DevTools.
5. **Corrigir** e repetir.

Esse método evita acumular erros e acelera o aprendizado real.

## 7) Exemplo principal (HTML + CSS + teste no Console)
### `index.html`
```html
<!doctype html>
<html lang="pt-BR">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Encontro 3 - Ambiente</title>
    <link rel="stylesheet" href="css/style.css" />
  </head>
  <body>
    <main class="container">
      <h1>Ambiente de Desenvolvimento</h1>
      <p id="mensagem">Se você está vendo este bloco estilizado, o CSS carregou.</p>
      <button id="btn">Testar Console</button>
    </main>

    <script>
      const botao = document.querySelector("#btn");
      botao.addEventListener("click", () => {
        console.log("Teste concluído: botão clicado com sucesso.");
      });
    </script>
  </body>
</html>
```

### `css/style.css`
```css
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: #f4f7fb;
  color: #1f2937;
}

.container {
  max-width: 700px;
  margin: 2rem auto;
  padding: 1.25rem;
  background: #ffffff;
  border: 1px solid #d9e2ec;
  border-radius: 8px;
}

button {
  padding: 0.6rem 0.9rem;
  border: 0;
  border-radius: 6px;
  background: #0f4c81;
  color: white;
  cursor: pointer;
}
```

### Como validar este exemplo
- Abrir a página no navegador e verificar o estilo aplicado.
- Clicar no botão.
- Abrir o Console e confirmar a mensagem de log.

## 8) Exemplo de erro real e correção
### Erro proposital
```html
<link rel="stylesheet" href="css/stlye.css" />
```

Problema: `stlye.css` está escrito errado.

Efeito: a página aparece sem estilo.

Correção:
```html
<link rel="stylesheet" href="css/style.css" />
```

### Como descobrir com DevTools
- Em **Network**, o arquivo CSS aparece com falha de carregamento.
- Em **Elements**, os estilos esperados não aparecem aplicados.

## 9) Erros comuns de iniciantes
- esquecer de salvar antes de testar;
- abrir arquivo diferente do que está editando;
- errar caminho de arquivo (`href`/`src`);
- ignorar mensagens do Console;
- tentar corrigir muitas coisas ao mesmo tempo.

## 10) Como estudar este encontro sozinho
1. Recrie a estrutura de pastas do zero.
2. Monte o exemplo principal sem copiar linha por linha.
3. Insira um erro proposital no caminho do CSS e detecte no DevTools.
4. Escreva um parágrafo explicando, com suas palavras, o papel de editor, navegador e DevTools.

## Materiais para aprofundamento
- [MDN - Getting started with the web](https://developer.mozilla.org/en-US/docs/Learn_web_development/Getting_started)
- [MDN - What are browser developer tools?](https://developer.mozilla.org/en-US/docs/Learn_web_development/Howto/Tools_and_setup/What_are_browser_developer_tools)
- [VS Code Docs](https://code.visualstudio.com/docs)
- [MDN - Debugging HTML](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content/Debugging_HTML)

## Checklist de compreensão
- [ ] Consigo explicar o que é ambiente de desenvolvimento no front-end.
- [ ] Sei organizar um projeto com pastas e arquivos básicos.
- [ ] Consigo abrir DevTools e usar Elements, Console e Network.
- [ ] Consigo identificar e corrigir erro de caminho de arquivo.
- [ ] Consigo aplicar o ciclo editar-salvar-testar-corrigir.

## Resumo final
Neste encontro, você construiu a base operacional para o restante da disciplina. A síntese é: **editor organiza o código, navegador interpreta, DevTools explica o que aconteceu**. Com esse trio, você desenvolve com mais clareza, autonomia e precisão.

## Questões de fixação (com gabarito)
1. Qual a função principal do editor de código no seu fluxo de trabalho?
Gabarito: Criar e organizar arquivos do projeto com estrutura e legibilidade.

2. Como o DevTools ajuda quando o CSS não é aplicado?
Gabarito: Permite verificar no Elements/Network se o arquivo CSS foi carregado e se o caminho está correto.

3. Qual é o ciclo básico de desenvolvimento recomendado para iniciantes?
Gabarito: Editar, salvar, testar no navegador, observar e corrigir.

4. Cite um erro comum ao iniciar em front-end.
Gabarito: Escrever caminho errado do CSS ou esquecer de salvar o arquivo.

5. Por que o terminal é útil mesmo em projetos simples?
Gabarito: Porque facilita navegação, organização de pastas e criação de arquivos com agilidade.
