# Encontro 9 - Lista Orientada de Exercícios de HTML

**Unidade:** Unidade 1  
**Entrega:** Lista 1 (HTML)

## Visão Geral
Neste encontro, você consolida os conteúdos de HTML vistos até agora em uma lista orientada de exercícios.
O foco é verificar domínio técnico de estrutura de documento, semântica, organização textual, mídia, tabelas e formulários com validação nativa.

Se nos Encontros 4 a 8 você aprendeu cada tópico em etapas, agora você integra tudo em atividades progressivas para preparar a transição para CSS nos próximos encontros.

## Conceitos Essenciais
- Planejamento de página antes de codificar.
- Aplicação consistente de elementos HTML semânticos.
- Organização do conteúdo para leitura humana e manutenção.
- Uso de validações nativas em formulários sem JavaScript.
- Revisão técnica com checklist antes da entrega.

## 1) Objetivo da Lista 1
A Lista 1 avalia sua capacidade de construir páginas HTML completas, legíveis e funcionais, com boas práticas iniciais da disciplina.

### Competências avaliadas
- montar documento HTML5 válido;
- estruturar conteúdo com títulos, parágrafos, listas e links;
- usar landmarks semânticos (`header`, `nav`, `main`, `section`, `article`, `aside`, `footer`);
- inserir mídia e tabela com contexto e créditos;
- criar formulário com `label` e validações nativas.

## 2) Escopo da Lista: o que será cobrado

### Bloco A - Estrutura e conteúdo textual
- `<!doctype html>`, `html`, `head`, `body`;
- `h1` a `h3`, `p`, `ul`, `ol`, `a`.

### Bloco B - Semântica e navegação
- landmarks principais da página;
- navegação interna com âncoras (`href="#id"`).

### Bloco C - Mídia e dados
- imagem com `alt`;
- `figure` e `figcaption`;
- tabela com `caption`, `thead`, `tbody`.

### Bloco D - Formulários
- `form`, `label`, `input`, `select`, `textarea`;
- validações com `required`, `minlength`, `maxlength`, `pattern`.

## 3) Regras de Entrega da Lista 1
- Entrega individual.
- Organize a lista em pasta única: `lista-1-html`.
- Crie um `index.html` para cada exercício.
- Teste todos os arquivos no navegador antes de enviar.
- Envie no Google Sala de Aula com o código da turma: `pgrjt3s2`.

### Estrutura sugerida
```text
lista-1-html/
  exercicio-1/
    index.html
  exercicio-2/
    index.html
  exercicio-3/
    index.html
  exercicio-4/
    index.html
  exercicio-5/
    index.html
```

## 4) Estratégia recomendada para execução
1. Resolva primeiro os exercícios 1 e 2 para garantir base estrutural.
2. Avance para exercício 3 (mídia e tabela) com atenção aos créditos.
3. Faça o exercício 4 com validações e teste envio/limpeza.
4. Finalize com o exercício 5 integrando os blocos anteriores.
5. Revise tudo com o checklist da seção 7.

## 5) Lista orientada de exercícios

### Exercício 1 - Página textual estruturada
Crie um `index.html` com:
- 1 `h1` e no mínimo 3 `h2`;
- pelo menos 3 parágrafos;
- 1 lista `ul` e 1 lista `ol`;
- 2 links funcionais (1 externo e 1 interno).

### Exercício 2 - Página semântica com landmarks
Crie um `index.html` com:
- `header`, `nav`, `main`, `section`, `article`, `aside` e `footer`;
- no mínimo 3 links internos de navegação;
- conteúdo coerente com um tema educacional ou institucional.

### Exercício 3 - Mídia, figura e tabela
Crie um `index.html` com:
- 1 `figure` contendo `img` + `figcaption`;
- 1 mídia (`audio` ou `video`) com `controls`;
- 1 tabela com `caption`, `thead`, `tbody`, `th` e `td`;
- bloco de créditos/licença dos recursos utilizados.

### Exercício 4 - Formulário com validações nativas
Crie um `index.html` com formulário contendo:
- campos de nome, e-mail, matrícula e mensagem;
- `label` associada para todos os campos;
- no mínimo 3 validações nativas (`required`, `minlength`, `pattern`, etc.);
- botões de envio e limpeza.

### Exercício 5 - Página integradora (desafio final da lista)
Crie um `index.html` integrando conteúdos dos exercícios anteriores:
- estrutura semântica completa;
- bloco textual com listas e links;
- uma mídia e uma tabela;
- formulário validado;
- `footer` com informação final e link de retorno ao topo.

### Critérios de avaliação da Lista 1 (10,0 pontos)
| Critério | Pontos |
|---|---:|
| Estrutura base HTML5 e organização geral | 2,0 |
| Semântica e navegação interna | 2,0 |
| Mídia, tabela e créditos/licenças | 2,0 |
| Formulário com validações nativas | 2,0 |
| Clareza do código e revisão final | 2,0 |

## 6) Validação rápida antes de considerar concluído
- Todos os arquivos abrem sem erro no navegador.
- Existe apenas um `h1` por página.
- Links internos e externos funcionam.
- Toda imagem possui `alt`.
- Tabela possui `caption`, `thead` e `tbody`.
- Formulário possui `label` e validações nativas.
- Cada página possui `footer` com identificação do encontro/lista.

## 7) Erros comuns de iniciantes
- pular estrutura mínima do HTML5;
- usar `div` para tudo sem aproveitar elementos semânticos;
- inserir mídia sem contexto ou sem crédito;
- criar formulário sem `label` ou sem `name`;
- não testar os arquivos antes de enviar.

## Materiais para Aprofundamento
- [MDN - HTML: Linguagem de Marcação de Hipertexto](https://developer.mozilla.org/pt-BR/docs/Web/HTML)
- [MDN - Elementos semânticos em HTML](https://developer.mozilla.org/pt-BR/docs/Glossary/Semantics)
- [MDN - Elemento `<table>`](https://developer.mozilla.org/pt-BR/docs/Web/HTML/Reference/Elements/table)
- [MDN - Formulários HTML](https://developer.mozilla.org/pt-BR/docs/Learn_web_development/Extensions/Forms)
- [W3C Markup Validation Service](https://validator.w3.org/)

## Checklist de Compreensão
- [ ] Consigo entregar múltiplos exercícios HTML com organização de pastas.
- [ ] Consigo aplicar estrutura semântica coerente em páginas diferentes.
- [ ] Consigo usar mídia, tabela e créditos corretamente.
- [ ] Consigo criar formulário com validação nativa funcional.
- [ ] Consigo revisar e validar meus arquivos antes da entrega.

## Resumo Final
Neste encontro, você consolidou os fundamentos de HTML em uma lista orientada de exercícios com foco em qualidade técnica e autonomia de implementação. A entrega da Lista 1 marca a transição para a próxima etapa da unidade, em que o mesmo conteúdo será estilizado e analisado com CSS.
