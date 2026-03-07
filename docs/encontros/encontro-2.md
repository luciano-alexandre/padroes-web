# Encontro 2 - Internet x Web, cliente-servidor, URL e HTTP (visão inicial)

**Unidade:** Unidade 1  
**Carga prevista:** 1,5h  
**Entregável previsto:** Mapa conceitual curto

## Explicação do conteúdo
Este encontro explica o caminho que uma página percorre até aparecer no navegador: Internet x Web, URL, cliente-servidor e o ciclo de requisição/resposta HTTP.

![Imagem de apoio ao tema](https://upload.wikimedia.org/wikipedia/commons/6/61/HTML5_logo_and_wordmark.svg)

## Conceitos essenciais
- Diferença entre Internet e Web.
- Requisição e resposta entre cliente e servidor.
- Estrutura de URL e noções de HTTP.

## Exemplo prático
Use o exemplo como ponto de partida e altere partes pequenas para entender cada efeito no navegador.

```js
const url = new URL("https://exemplo.com/cursos/web?turno=noite");
console.log(url.protocol);
console.log(url.hostname);
console.log(url.pathname);
console.log(url.searchParams.get("turno"));
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
- [MDN - URL API](https://developer.mozilla.org/pt-BR/docs/Web/API/URL)
- [MDN - HTTP](https://developer.mozilla.org/pt-BR/docs/Web/HTTP)
- [Cloudflare - What is HTTP?](https://www.cloudflare.com/learning/ddos/glossary/hypertext-transfer-protocol-http/)

## Checklist de compreensão
- [ ] Entendi o conceito principal da aula.
- [ ] Consegui executar e adaptar o exemplo.
- [ ] Entreguei a atividade prevista no cronograma.
- [ ] Sei quais pontos ainda preciso revisar.




## Resumo final
Neste encontro, voce estudou **Internet x Web, cliente-servidor, URL e HTTP (visão inicial)** dentro dos fundamentos de HTML e estrutura da Web. O objetivo principal foi construir base conceitual e pratica para leitura, escrita e organizacao de paginas com clareza.

## Questoes de fixacao (com gabarito)
1. Qual e a ideia central do tema "Internet x Web, cliente-servidor, URL e HTTP (visão inicial)" nesta unidade?
Gabarito: Compreender a base de estruturacao de conteudo na Web e aplicar esse conhecimento na construcao de paginas em HTML.

2. Por que separar estrutura (HTML) de estilo (CSS) e comportamento (JavaScript) e importante?
Gabarito: Porque facilita manutencao, organizacao do codigo, trabalho em equipe e evolucao do projeto.

3. Cite uma boa pratica de acessibilidade relacionada a HTML.
Gabarito: Usar semantica adequada e incluir texto alternativo em imagens quando necessario.

4. Qual erro comum de iniciantes deve ser evitado nesse tipo de conteudo?
Gabarito: Copiar codigo sem entender e nao testar em etapas pequenas.

5. O que voce deve revisar antes de entregar uma atividade desta unidade?
Gabarito: Estrutura correta do HTML, legibilidade do conteudo, semantica basica e funcionamento do que foi pedido.
