# Encontro 10 - Atividade Avaliativa 01: Página HTML Semântica Integradora

**Unidade:** Unidade 1  
**Entrega:** Avaliação 01 (HTML)

## Visão Geral
Neste encontro, você realiza a primeira atividade avaliativa prática da disciplina.
O foco é integrar, em uma única página HTML, os conteúdos de estrutura base, organização textual, semântica, mídias, tabelas e formulários com validação nativa.

Se no Encontro 9 você consolidou os conteúdos em uma lista orientada, agora você os aplica em uma proposta avaliativa com tema contextualizado e requisitos objetivos.

## Conceitos Essenciais
- Leitura atenta do enunciado antes de codificar.
- Organização semântica da página com landmarks.
- Integração coerente entre conteúdo textual, mídia, tabela e formulário.
- Uso de validações nativas sem depender de JavaScript.
- Revisão técnica final antes da entrega.

## 1) Contexto da atividade
Você foi contratado para criar a primeira versão HTML da página **"Achados e Perdidos - Festival da Luz"**, um serviço temporário usado durante um festival cultural da cidade.

A página deve ajudar visitantes a:
- consultar itens encontrados;
- entender como retirar um objeto;
- registrar uma solicitação de busca.

## 2) Requisitos da atividade avaliativa
Crie uma pasta chamada `avaliacao-html-festival` contendo um arquivo `index.html`.
A página deve ser feita apenas com HTML.

### Bloco A - Estrutura e semântica
- estrutura HTML5 completa;
- `header`, `nav`, `main`;
- pelo menos 3 `section`;
- pelo menos 1 `article`;
- pelo menos 1 `aside`;
- `footer`.

### Bloco B - Conteúdo textual e navegação
- um único `h1`;
- uso coerente de `h2` e `h3`;
- parágrafos curtos;
- uma lista não ordenada;
- uma lista ordenada;
- pelo menos 1 link interno;
- pelo menos 1 link externo funcional.

### Bloco C - Mídia, créditos e tabela
- uma `figure` com `img`, `alt` descritivo e `figcaption`;
- um `audio` ou `video` com `controls`;
- bloco de créditos/licença dos recursos;
- tabela com `caption`, `thead`, `tbody`, `th` e `td`;
- no mínimo 5 itens simulados na tabela.

### Bloco D - Formulário com validação nativa
O formulário deve conter, no mínimo:
- nome completo;
- e-mail;
- telefone;
- categoria do item com `select`;
- data aproximada da perda;
- descrição detalhada com `textarea`;
- campo de protocolo ou documento com `pattern`;
- checkbox de confirmação;
- botões de envio e limpeza.

Além disso:
- todos os campos devem ter `label` associada;
- use pelo menos 4 validações nativas, como `required`, `minlength`, `maxlength`, `type="email"`, `type="date"` e `pattern`.

## 3) Estrutura sugerida da pasta
```text
avaliacao-html-festival/
  index.html
```

## 4) Estratégia recomendada para execução
1. Monte primeiro a estrutura base do HTML5.
2. Organize a página com `header`, `nav`, `main`, `section`, `article`, `aside` e `footer`.
3. Adicione o conteúdo textual e a navegação interna.
4. Insira a mídia, a tabela e o bloco de créditos.
5. Finalize com o formulário e teste todas as validações no navegador.
6. Revise o código antes de entregar.

## 5) Critérios de avaliação (10,0 pontos)
| Critério | Pontos |
|---|---:|
| Estrutura HTML5 e organização geral | 2,0 |
| Semântica e navegação interna | 2,0 |
| Mídia, créditos e tabela | 2,0 |
| Formulário com validações nativas | 2,0 |
| Clareza do código e revisão final | 2,0 |

## 6) Validação rápida antes de considerar concluído
- Existe apenas um `h1` na página.
- Há pelo menos 3 `section`, 1 `article`, 1 `aside` e 1 `footer`.
- O menu contém link interno funcional.
- Há pelo menos 1 link externo funcional.
- A imagem possui `alt` e `figcaption`.
- O áudio ou vídeo possui `controls`.
- A tabela possui `caption`, `thead` e `tbody`.
- O formulário possui `label` e validações nativas coerentes.
- Os botões de envio e limpeza estão presentes.

## 7) Erros comuns que reduzem a nota
- esquecer a estrutura mínima do HTML5;
- usar `div` no lugar de elementos semânticos exigidos;
- criar tabela sem `caption` ou sem cabeçalho;
- inserir imagem sem `alt`;
- deixar campos de formulário sem `label`;
- usar validações nativas de forma incoerente ou insuficiente;
- não testar a página no navegador antes da entrega.

## Materiais para Aprofundamento
- [MDN - HTML: Linguagem de Marcação de Hipertexto](https://developer.mozilla.org/pt-BR/docs/Web/HTML)
- [MDN - Guia de semântica em HTML](https://developer.mozilla.org/pt-BR/docs/Glossary/Semantics)
- [MDN - Elemento `<figure>`](https://developer.mozilla.org/pt-BR/docs/Web/HTML/Reference/Elements/figure)
- [MDN - Elemento `<table>`](https://developer.mozilla.org/pt-BR/docs/Web/HTML/Reference/Elements/table)
- [MDN - Formulários HTML](https://developer.mozilla.org/pt-BR/docs/Learn_web_development/Extensions/Forms)
- [W3C Markup Validation Service](https://validator.w3.org/)

## Checklist de Compreensão
- [ ] Consigo interpretar um enunciado técnico e transformá-lo em estrutura HTML.
- [ ] Consigo integrar semântica, mídia, tabela e formulário em uma única página.
- [ ] Consigo aplicar validações nativas adequadas ao contexto.
- [ ] Consigo revisar requisitos antes de entregar uma atividade avaliativa.
- [ ] Consigo identificar erros que comprometem a qualidade técnica do arquivo.

## Resumo Final
Neste encontro, você aplica de forma integrada os fundamentos de HTML vistos até aqui em uma atividade avaliativa contextualizada. A qualidade da entrega depende não apenas de "ter todos os elementos", mas de organizá-los com clareza, semântica e revisão técnica.
