# Encontro 39 - Apresentações de projetos finais (dia reservado)

**Unidade:** Unidade 4  
**Carga prevista:** 1,5h  
**Entregável:** Apresentação final - turma A

## Visão Didática da Aula
Este encontro é estruturado como momento avaliativo e de consolidação. O material abaixo serve como revisão orientada, com lembretes de boas práticas, critérios de qualidade e checklist para evitar erros comuns durante a entrega/apresentação.

![Imagem de apoio do encontro](https://upload.wikimedia.org/wikipedia/commons/8/8e/OOjs_UI_icon_code.svg)

## Objetivos de Aprendizagem
- Compreender os conceitos centrais de "Apresentações de projetos finais (dia reservado)".
- Aplicar o conteúdo em uma prática curta com feedback.
- Produzir o entregável previsto: **Apresentação final - turma A**.

## Explicação Guiada
Comece identificando os conceitos que aparecem no tema da aula e relacione com situações práticas de páginas reais (sites institucionais, portfólios, lojas, blogues). Em seguida, implemente uma versão mínima funcional, validando no navegador a cada alteração. O ideal é manter ciclos curtos de teste para facilitar depuração e consolidação da aprendizagem.

## Exemplo de Código
```html
<section class="projeto">
  <h2>Projeto Final</h2>
  <p id="status">Planejamento em andamento</p>
  <button id="concluir">Marcar etapa como concluída</button>
</section>
<script>
  document.querySelector("#concluir").addEventListener("click", () => {
    document.querySelector("#status").textContent = "Etapa concluída.";
  });
</script>
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
- [MDN - Performance Web](https://developer.mozilla.org/pt-BR/docs/Web/Performance)
- [web.dev - Learn Accessibility](https://web.dev/learn/accessibility/)
- [GitHub Pages](https://pages.github.com/)

## Checklist da Aula
- [ ] Entendi os conceitos principais.
- [ ] Executei e adaptei o exemplo de código.
- [ ] Concluí o entregável previsto.
- [ ] Registrei dúvidas para revisão na próxima aula.
