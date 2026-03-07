# Encontro 17 - Lista de exercícios do bloco 2 (layout e responsividade)

**Unidade:** Unidade 2  
**Carga prevista:** 1,5h  
**Entregável:** Lista 2 entregue

## Visão Didática da Aula
Neste encontro, o foco é "Lista de exercícios do bloco 2 (layout e responsividade)". A proposta é trabalhar o conteúdo em linguagem introdutória, conectando conceito, demonstração e prática orientada. O objetivo é que o estudante compreenda não apenas o que fazer, mas por que a técnica é útil em projetos reais.

![Imagem de apoio do encontro](https://upload.wikimedia.org/wikipedia/commons/d/d5/CSS3_logo_and_wordmark.svg)

## Objetivos de Aprendizagem
- Compreender os conceitos centrais de "Lista de exercícios do bloco 2 (layout e responsividade)".
- Aplicar o conteúdo em uma prática curta com feedback.
- Produzir o entregável previsto: **Lista 2 entregue**.

## Explicação Guiada
Comece identificando os conceitos que aparecem no tema da aula e relacione com situações práticas de páginas reais (sites institucionais, portfólios, lojas, blogues). Em seguida, implemente uma versão mínima funcional, validando no navegador a cada alteração. O ideal é manter ciclos curtos de teste para facilitar depuração e consolidação da aprendizagem.

## Exemplo de Código
```css
:root {
  --cor-primaria: #0a4d8c;
  --espaco: 1rem;
}

body {
  margin: 0;
  font-family: "Segoe UI", sans-serif;
  color: #1f2937;
}

.card {
  display: flex;
  gap: var(--espaco);
  padding: var(--espaco);
  border: 1px solid #d1d5db;
}
```

## Atividade Prática Recomendada
1. Revisar os conceitos essenciais da aula (15 min).
2. Reproduzir e adaptar o exemplo de código (30-40 min).
3. Resolver um desafio contextualizado com apoio do professor (40-50 min).
4. Publicar/registrar o entregável da aula no repositório da turma (15 min).

## Erros Comuns e Como Evitar
- Escrever código sem testar em etapas pequenas.
- Ignorar mensagens de erro no console/DevTools.
- Não validar semântica, responsividade ou legibilidade do código antes da entrega.

## Materiais de Apoio
- [MDN - CSS](https://developer.mozilla.org/pt-BR/docs/Web/CSS)
- [CSS Tricks - A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [CSS Tricks - A Complete Guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)

## Checklist da Aula
- [ ] Entendi os conceitos principais.
- [ ] Executei e adaptei o exemplo de código.
- [ ] Concluí o entregável previsto.
- [ ] Registrei dúvidas para revisão na próxima aula.
