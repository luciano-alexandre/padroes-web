# Encontro 20 - Atividade Avaliativa 02: Tela Inicial Estilizada com CSS

**Unidade:** Unidade 1  
**Entrega:** Avaliacao 02 (CSS)

Instituto Federal do Rio Grande do Norte  
Campus Currais Novos  
Turma: Tecnologia em Sistemas para Internet  
Disciplina: Padroes Web  
Docente: Luciano Alexandre de Farias Silva

## Avaliacao 02

### Questao unica (10,0 pontos)
Voce foi contratado para criar a tela inicial de um portal academico da turma.
A proposta deve integrar os conteudos estudados do Encontro 1 ao 17, com foco principal em CSS.

Crie uma pasta chamada `avaliacao-css-tela-inicial` contendo os arquivos `index.html` e `styles.css`.
A pagina deve ser feita com HTML + CSS (sem framework CSS e sem JavaScript obrigatorio).

### Exemplo visual de referencia
![Exemplo visual esperado da tela inicial](./imagens/encontro-20-avaliacao-02-exemplo.svg)

A pagina deve conter:

1. Estrutura HTML5 completa (`<!doctype html>`, `html`, `head`, `body`) com `lang="pt-BR"`, `meta charset` e `meta viewport`.
2. Organizacao semantica com, no minimo, `header`, `main` e `footer`.
3. Cabecalho estilizado com titulo principal da pagina.
4. Corpo principal com uma secao de cards contendo exatamente 6 cards.
5. Cada card deve ter:
   - um titulo visivel;
   - uma cor de fundo diferente dos demais cards;
   - borda, espacamento interno e cantos arredondados.
6. Rodape estilizado e visualmente separado do corpo.
7. O CSS deve demonstrar os conteudos dos Encontros 12 a 17, incluindo:
   - arquivo externo `styles.css` corretamente vinculado;
   - seletores por elemento, classe e id;
   - uso de cascata e heranca de forma coerente;
   - aplicacao de box model (`margin`, `padding`, `border`);
   - organizacao dos 6 cards com Flexbox;
   - uso de unidades de medida, com pelo menos `px`, `rem` e `%`, alem de uma entre `em`, `vw` ou `vh`.
8. Boas praticas de codigo:
   - sem CSS inline;
   - indentacao legivel;
   - nomes de classes claros.

### Estrutura sugerida da pasta
```text
avaliacao-css-tela-inicial/
  index.html
  styles.css
```

### Criterios de avaliacao (10,0 pontos)
| Criterio | Pontos |
|---|---:|
| Estrutura HTML5 e semantica base da pagina | 2,0 |
| Cabecalho, corpo e rodape estilizados com coerencia visual | 2,0 |
| Implementacao correta dos 6 cards (cores distintas + titulos) | 2,0 |
| Uso tecnico de CSS (seletores, cascata/heranca, box model e unidades) | 2,0 |
| Organizacao do layout com Flexbox e qualidade final do codigo | 2,0 |

### Validacao rapida antes de entregar
- [ ] A pasta contem `index.html` e `styles.css`.
- [ ] O `styles.css` esta vinculado corretamente ao HTML.
- [ ] Existem `header`, `main` e `footer` na estrutura.
- [ ] O corpo possui exatamente 6 cards.
- [ ] Os 6 cards possuem cores diferentes e titulos visiveis.
- [ ] O layout usa Flexbox para distribuir os cards.
- [ ] O CSS usa `px`, `rem`, `%` e ao menos uma unidade adicional (`em`, `vw` ou `vh`).
- [ ] O codigo foi revisado no navegador antes da entrega.
