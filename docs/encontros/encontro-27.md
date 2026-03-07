# Encontro 27 - Formulários com validação em JavaScript

**Unidade:** Unidade 3  
**Carga prevista:** 1,5h  
**Entregável previsto:** Formulário validado

## Explicação do conteúdo
Este encontro integra formulários com validação em JavaScript para feedback imediato ao usuário.

![Imagem de apoio ao tema](https://upload.wikimedia.org/wikipedia/commons/9/99/Unofficial_JavaScript_logo_2.svg)

## Conceitos essenciais
- Captura de dados do formulário.
- Regras de validação.
- Feedback ao usuário.

## Exemplo prático
Use o exemplo como ponto de partida e altere partes pequenas para entender cada efeito no navegador.

```js
const form = document.querySelector("form");
form.addEventListener("submit", (e) => {
  const email = document.querySelector("#email").value.trim();
  if (!email.includes("@")) {
    e.preventDefault();
    alert("Informe um e-mail válido.");
  }
});
```

## Como estudar este encontro sozinho
1. Leia a explicação e destaque os conceitos-chave.
2. Digite o exemplo de código manualmente.
3. Faça pequenas alterações e observe o resultado.
4. Resolva uma variação do exercício com seu próprio tema.

## Dificuldades comuns de iniciantes
- Tentar avançar sem revisar a base.
- Copiar código sem compreender a lógica.
- Não testar mudanças em etapas curtas.

## Materiais para aprofundamento
- [MDN - JavaScript](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript)
- [MDN - DOM](https://developer.mozilla.org/pt-BR/docs/Web/API/Document_Object_Model)
- [javascript.info](https://javascript.info/)

## Checklist de compreensão
- [ ] Entendi o conceito principal da aula.
- [ ] Consegui executar e adaptar o exemplo.
- [ ] Entreguei a atividade prevista no cronograma.
- [ ] Sei quais pontos ainda preciso revisar.




## Resumo final
Neste encontro, voce estudou **Formulários com validação em JavaScript** dentro da introducao a JavaScript e DOM. O foco foi transformar paginas estaticas em interfaces interativas por meio de logica, eventos e manipulacao de elementos.

## Questoes de fixacao (com gabarito)
1. Qual papel do JavaScript no contexto do tema "Formulários com validação em JavaScript"?
Gabarito: Controlar comportamentos da pagina, processar regras e responder a interacoes do usuario.

2. O que e o DOM de forma simples?
Gabarito: E a representacao em arvore da pagina HTML, que pode ser lida e alterada com JavaScript.

3. Para que serve `addEventListener`?
Gabarito: Para executar uma acao quando um evento ocorrer (ex.: clique, envio de formulario, digitacao).

4. Qual pratica ajuda a evitar bugs em JavaScript iniciante?
Gabarito: Testar cada pequena mudanca no navegador e usar o console para depurar.

5. O que revisar antes de entregar atividades com JS/DOM?
Gabarito: Selecao correta de elementos, logica funcionando, eventos conectados e feedback claro ao usuario.
