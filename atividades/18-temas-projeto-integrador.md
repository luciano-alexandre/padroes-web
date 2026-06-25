# 18 temas para o projeto integrador de Padrões Web

Este catálogo propõe temas diferentes, mas equivalentes em complexidade, para o projeto integrador da disciplina. As propostas foram construídas a partir do cronograma de 60 horas e permitem exercitar fundamentos da Web, HTML5 semântico, CSS moderno, responsividade, formulários, mídias, frameworks, planejamento, testes e publicação.

Os protótipos são referências de organização e hierarquia visual. Eles não precisam ser copiados literalmente: cada estudante deve justificar suas decisões e construir uma identidade própria.

## Requisitos comuns a todos os temas

Cada projeto deverá:

1. Ter pelo menos **três páginas HTML interligadas**, correspondentes às três telas indicadas no tema.
2. Usar estrutura HTML5 completa e landmarks adequados, como `header`, `nav`, `main`, `section`, `article`, `aside` e `footer`.
3. Apresentar títulos em ordem lógica, textos, listas, links internos e externos e navegação utilizável por teclado.
4. Incluir imagens com `alt`, dimensões declaradas e licença/crédito; usar ao menos uma vez `figure`/`figcaption`, `loading="lazy"` e uma estratégia responsiva com `srcset`, `sizes` ou `picture`.
5. Incluir uma **tabela semântica** relacionada ao tema, com `caption`, cabeçalhos e escopo compreensível.
6. Incluir um **formulário completo** com `label`, `fieldset`, `legend`, tipos de campo adequados, `required`, `autocomplete` e validações nativas.
7. Manter uma folha de estilos autoral que demonstre cascata, herança, especificidade, combinadores, box model, `display`, cores, fundos, bordas, tipografia e unidades relativas.
8. Usar **Flexbox** e **CSS Grid** em situações justificáveis, sem reproduzir o mesmo layout com as duas técnicas apenas para cumprir requisito.
9. Adotar abordagem **mobile-first**, viewport configurado, imagens fluidas e media queries para pelo menos dois intervalos de largura.
10. Implementar estados visuais com pseudoclasses (`:hover`, `:focus-visible`, `:checked`, `:valid` e `:invalid` quando aplicáveis), pelo menos um pseudoelemento e transições discretas.
11. Definir design tokens para cores, tipografia, espaçamentos, raios e sombras, preferencialmente com propriedades customizadas CSS.
12. Utilizar **Bootstrap** em parte relevante da interface e registrar no `README.md` o que foi feito pelo framework, o que permaneceu autoral e por quê.
13. Organizar arquivos e nomes de classes com clareza, testar no DevTools, verificar diferentes larguras e revisar acessibilidade, navegação e conteúdo excedente.
14. Versionar o trabalho em um repositório no **GitHub**, mantendo histórico de commits coerente com a evolução do projeto, publicar o site estático e apresentar arquitetura da informação, wireframes, guia visual e decisões técnicas.

## 1. Rota do Seridó — guia de turismo regional

**Desafio:** criar um guia que apresente destinos, roteiros e experiências culturais do Seridó, valorizando informação local, planejamento de viagem e imagens com créditos.

**Telas obrigatórias:**

- **Início:** destaque regional, categorias de passeio, destinos recomendados e chamada para montar um roteiro.
- **Explorar destinos:** grade filtrável visualmente por categorias, cards com etiquetas e tabela de épocas recomendadas.
- **Detalhe e interesse:** galeria responsiva, roteiro do dia, informações práticas e formulário para registrar interesse.

**Aplicações específicas:** usar `picture` no destaque, `figure` para atrações, Grid na vitrine, Flexbox nos filtros, tabela de clima/temporada, formulário com data e quantidade de viajantes e uma etiqueta posicionada sobre cards.

![Protótipo da tela inicial da Rota do Seridó](./01-rota-do-serido/01-inicio.png)
![Protótipo da tela de destinos da Rota do Seridó](./01-rota-do-serido/02-destinos.png)
![Protótipo da tela de detalhe da Rota do Seridó](./01-rota-do-serido/03-detalhe.png)

## 2. Feira Raízes — produtores e alimentos locais

**Desafio:** construir uma feira digital para divulgar produtores, produtos sazonais e os horários de uma feira agroecológica.

**Telas obrigatórias:**

- **Início:** campanha da semana, categorias, produtores em destaque e agenda resumida.
- **Produtos e produtores:** catálogo responsivo com preço, origem, disponibilidade e perfil de cada produtor.
- **Visite ou participe:** tabela de horários, orientações e formulário de inscrição de novo expositor.

**Aplicações específicas:** cards de produtos com `article`, imagens recortadas com `aspect-ratio`/`object-fit`, tabela de dias e bancas, formulário com seleção múltipla de categorias, estados de disponibilidade e selo sazonal com posicionamento absoluto.

![Protótipo da tela inicial da Feira Raízes](./02-feira-raizes/01-inicio.png)
![Protótipo do catálogo da Feira Raízes](./02-feira-raizes/02-catalogo.png)
![Protótipo da tela de participação da Feira Raízes](./02-feira-raizes/03-participe.png)

## 3. Biblioteca Janela Aberta — acervo comunitário

**Desafio:** projetar um site de biblioteca comunitária que facilite descoberta do acervo, consulta de horários e solicitação de empréstimo.

**Telas obrigatórias:**

- **Início:** novidades, clubes de leitura, serviços e chamada para consultar o acervo.
- **Acervo:** busca visual, categorias, cards de livros e estados de disponível/emprestado.
- **Livro e reserva:** ficha bibliográfica, sinopse, tabela de exemplares e formulário de reserva.

**Aplicações específicas:** hierarquia textual rigorosa, listas de gêneros, capas com proporção consistente, Grid no acervo, tabela com status, formulário com e-mail/data, `:disabled` em ação indisponível e `overflow` em uma estante horizontal.

![Protótipo da tela inicial da Biblioteca Janela Aberta](./03-biblioteca-janela-aberta/01-inicio.png)
![Protótipo do acervo da Biblioteca Janela Aberta](./03-biblioteca-janela-aberta/02-acervo.png)
![Protótipo da reserva da Biblioteca Janela Aberta](./03-biblioteca-janela-aberta/03-reserva.png)

## 4. Adote um Amigo — adoção responsável

**Desafio:** criar um portal para apresentar animais disponíveis e orientar um processo ético de adoção responsável.

**Telas obrigatórias:**

- **Início:** missão, números da iniciativa, animais em destaque e etapas da adoção.
- **Animais:** grade de perfis com espécie, porte, idade, necessidades e etiquetas de status.
- **Perfil e candidatura:** galeria, história, tabela de cuidados e formulário detalhado do candidato.

**Aplicações específicas:** texto alternativo cuidadoso, `figure`/`figcaption`, cards com Flexbox interno, Grid responsivo, tabela de vacinação/cuidados, formulário agrupado com radios e checkboxes e foco visível em todos os controles.

![Protótipo da tela inicial do Adote um Amigo](./04-adote-um-amigo/01-inicio.png)
![Protótipo da tela de animais do Adote um Amigo](./04-adote-um-amigo/02-animais.png)
![Protótipo da candidatura do Adote um Amigo](./04-adote-um-amigo/03-candidatura.png)

## 5. Agenda Viva Cultura — programação cultural

**Desafio:** desenvolver uma agenda de shows, oficinas, exposições e encontros culturais, com leitura rápida por data e categoria.

**Telas obrigatórias:**

- **Início:** próximo evento, destaques da semana e navegação por categoria.
- **Programação:** calendário/lista de eventos com filtros visuais e tabela de horários.
- **Evento e inscrição:** informações do evento, mapa ilustrativo, programação e formulário de inscrição.

**Aplicações específicas:** `<time>` nas datas, cartões com pseudoelementos decorativos, cabeçalho `sticky`, faixa horizontal com `overflow-x`, Grid da programação, tabela de sessões e transições nos estados dos botões.

![Protótipo da tela inicial da Agenda Viva Cultura](./05-agenda-viva-cultura/01-inicio.png)
![Protótipo da programação da Agenda Viva Cultura](./05-agenda-viva-cultura/02-programacao.png)
![Protótipo da inscrição da Agenda Viva Cultura](./05-agenda-viva-cultura/03-inscricao.png)

## 6. Sabores da Terra — restaurante regional

**Desafio:** criar a presença digital de um restaurante regional com narrativa sobre ingredientes, cardápio acessível e reserva de mesa.

**Telas obrigatórias:**

- **Início:** apresentação do restaurante, prato em destaque, história e avaliações.
- **Cardápio:** seções de pratos, etiquetas alimentares, preços e tabela de opções executivas.
- **Reserva:** ambiente, horários, orientações e formulário de reserva.

**Aplicações específicas:** imagens responsivas em diferentes recortes, listas de ingredientes, Grid no cardápio, Flexbox em preço/etiquetas, tabela com dias e menus, formulário com data/hora/número de pessoas e ação de reserva fixa em telas pequenas.

![Protótipo da tela inicial do Sabores da Terra](./06-sabores-da-terra/01-inicio.png)
![Protótipo do cardápio do Sabores da Terra](./06-sabores-da-terra/02-cardapio.png)
![Protótipo da reserva do Sabores da Terra](./06-sabores-da-terra/03-reserva.png)

## 7. Esporte em Rede — campeonatos comunitários

**Desafio:** organizar informações de modalidades, equipes, partidas e inscrições de um circuito esportivo comunitário.

**Telas obrigatórias:**

- **Início:** modalidades, próxima rodada, notícias e chamada para inscrição.
- **Campeonato:** classificação em tabela, calendário de jogos e cards de equipes.
- **Equipe e inscrição:** perfil, elenco, resultados e formulário para cadastrar uma equipe.

**Aplicações específicas:** tabela responsiva de classificação, listas de partidas, `overflow-x` sem quebrar a página, Grid para equipes, destaques com `::before`, estados vitória/empate/derrota e formulário com quantidade, modalidade e aceite do regulamento.

![Protótipo da tela inicial do Esporte em Rede](./07-esporte-em-rede/01-inicio.png)
![Protótipo do campeonato do Esporte em Rede](./07-esporte-em-rede/02-campeonato.png)
![Protótipo da inscrição no Esporte em Rede](./07-esporte-em-rede/03-inscricao.png)

## 8. Saúde Perto — serviços de uma clínica-escola

**Desafio:** apresentar serviços de uma clínica-escola e permitir uma solicitação demonstrativa de atendimento com linguagem clara e inclusiva.

**Telas obrigatórias:**

- **Início:** especialidades, orientações, equipe e avisos de atendimento.
- **Serviços e profissionais:** filtros visuais, cards e tabela de disponibilidade semanal.
- **Solicitar atendimento:** etapas, documentos necessários e formulário de triagem não sensível.

**Aplicações específicas:** alto contraste, foco evidente, conteúdo organizado com `aside`, tabela de disponibilidade, formulário com `fieldset`, `autocomplete`, validação nativa e mensagens de ajuda; não coletar diagnóstico ou dados pessoais reais.

![Protótipo da tela inicial do Saúde Perto](./08-saude-perto/01-inicio.png)
![Protótipo dos serviços do Saúde Perto](./08-saude-perto/02-servicos.png)
![Protótipo da solicitação do Saúde Perto](./08-saude-perto/03-solicitacao.png)

## 9. Museu Memórias — acervo histórico local

**Desafio:** criar uma experiência editorial para narrar a memória local por meio de objetos, fotografias, depoimentos e exposições.

**Telas obrigatórias:**

- **Início:** exposição em cartaz, destaques do acervo e linha do tempo resumida.
- **Acervo:** galeria responsiva por período e tipo de item.
- **Exposição:** narrativa longa, figuras com legenda, tabela cronológica e formulário para visita guiada.

**Aplicações específicas:** semântica editorial com `article`, `blockquote`, `time`, `figure` e `figcaption`, `picture` para imagens históricas, Grid assimétrico, barra lateral `sticky`, galeria com carregamento tardio e créditos/licenças visíveis.

![Protótipo da tela inicial do Museu Memórias](./09-museu-memorias/01-inicio.png)
![Protótipo do acervo do Museu Memórias](./09-museu-memorias/02-acervo.png)
![Protótipo da exposição do Museu Memórias](./09-museu-memorias/03-exposicao.png)

## 10. Observatório do Clima — dados ambientais locais

**Desafio:** apresentar dados climáticos de maneira compreensível, com boletins, séries históricas e cadastro demonstrativo para alertas.

**Telas obrigatórias:**

- **Painel:** indicadores atuais, alertas, gráfico ilustrativo e resumo semanal.
- **Boletins:** coleção de relatórios, tabela histórica e metodologia.
- **Alerta:** detalhes de um aviso, recomendações e formulário de preferências.

**Aplicações específicas:** cartões de dados com Grid, números e unidades semanticamente claros, tabela com `caption`, cores que não sejam o único indicador de estado, faixa de alerta posicionada, `overflow` para série histórica e formulário com localidades e tipos de notificação.

![Protótipo do painel do Observatório do Clima](./10-observatorio-do-clima/01-painel.png)
![Protótipo dos boletins do Observatório do Clima](./10-observatorio-do-clima/02-boletins.png)
![Protótipo do alerta do Observatório do Clima](./10-observatorio-do-clima/03-alerta.png)

## 11. Vitrine Criativa — artesanato e economia solidária

**Desafio:** produzir uma vitrine de artesãos locais, enfatizando autoria, materiais, processos e solicitação de encomendas, sem implementar comércio eletrônico real.

**Telas obrigatórias:**

- **Início:** coleções, histórias de artesãos e categorias.
- **Catálogo:** produtos em grade, filtros, disponibilidade e faixa de preço.
- **Peça e encomenda:** galeria, descrição, tabela de variações e formulário de interesse.

**Aplicações específicas:** fotografias com licença/crédito, `object-fit` sem deformação, Grid do catálogo, filtros com Flexbox, selo absoluto, tabela de tamanhos/materiais, campos de quantidade e preferências e estados de produto esgotado.

![Protótipo da tela inicial da Vitrine Criativa](./11-vitrine-criativa/01-inicio.png)
![Protótipo do catálogo da Vitrine Criativa](./11-vitrine-criativa/02-catalogo.png)
![Protótipo da encomenda da Vitrine Criativa](./11-vitrine-criativa/03-encomenda.png)

## 12. Conecta Estágios — oportunidades para estudantes

**Desafio:** criar um portal de oportunidades acadêmicas com vagas, critérios, prazos e candidatura demonstrativa.

**Telas obrigatórias:**

- **Início:** busca, áreas, vagas recentes e orientações.
- **Vagas:** listagem responsiva com filtros, etiquetas e tabela comparativa.
- **Vaga e candidatura:** descrição semântica, requisitos, etapas e formulário do candidato.

**Aplicações específicas:** `article` para vagas, listas para requisitos, Grid de conteúdo/aside, filtros `sticky`, tabela comparativa de carga/benefícios, formulário com e-mail, URL de portfólio e arquivo demonstrativo e `:focus-visible` destacado.

![Protótipo da tela inicial do Conecta Estágios](./12-conecta-estagios/01-inicio.png)
![Protótipo da tela de vagas do Conecta Estágios](./12-conecta-estagios/02-vagas.png)
![Protótipo da candidatura do Conecta Estágios](./12-conecta-estagios/03-candidatura.png)

## 13. Trilhas do Saber — catálogo de cursos livres

**Desafio:** desenvolver um catálogo de cursos curtos, com trilhas de aprendizagem, cronograma e matrícula demonstrativa.

**Telas obrigatórias:**

- **Início:** trilhas, cursos em destaque, benefícios e depoimentos.
- **Cursos:** catálogo com níveis, duração, modalidade e filtros visuais.
- **Curso e matrícula:** ementa, módulos, tabela de turmas e formulário de matrícula.

**Aplicações específicas:** cards componíveis, barra visual de progresso estática, pseudoelementos na linha da trilha, Grid responsivo, tabela de turmas, formulário com escolaridade/horário, estados de turma cheia e acordeões nativos opcionais com `details`/`summary`.

![Protótipo da tela inicial do Trilhas do Saber](./13-trilhas-do-saber/01-inicio.png)
![Protótipo do catálogo do Trilhas do Saber](./13-trilhas-do-saber/02-cursos.png)
![Protótipo da matrícula do Trilhas do Saber](./13-trilhas-do-saber/03-matricula.png)

## 14. Vozes do Campus — portal jornalístico estudantil

**Desafio:** criar um portal editorial para notícias, entrevistas, agenda e participação estudantil.

**Telas obrigatórias:**

- **Capa:** manchete, últimas notícias, editorias e agenda.
- **Editoria:** grade de matérias, destaques e tabela de eventos/prazos.
- **Reportagem e contato:** matéria longa com mídia, conteúdos relacionados e formulário para sugerir pauta.

**Aplicações específicas:** estrutura editorial com `article`, autoria e `<time>`, hierarquia de títulos, `figure`/`figcaption`, Grid de capa, navegação `sticky`, destaque com pseudoelemento, imagens responsivas e formulário com assunto e texto mínimo.

![Protótipo da capa do Vozes do Campus](./14-vozes-do-campus/01-capa.png)
![Protótipo da editoria do Vozes do Campus](./14-vozes-do-campus/02-editoria.png)
![Protótipo da reportagem do Vozes do Campus](./14-vozes-do-campus/03-reportagem.png)

## 15. Recicla Bairro — descarte e coleta consciente

**Desafio:** orientar moradores sobre separação de resíduos, pontos de entrega e agendamento demonstrativo de coleta.

**Telas obrigatórias:**

- **Início:** guia rápido, categorias de resíduo, impacto e campanha atual.
- **Pontos de coleta:** cards por região, mapa ilustrativo e tabela de materiais/horários.
- **Agendar coleta:** instruções, itens aceitos e formulário de solicitação.

**Aplicações específicas:** ícones acompanhados de texto, listas de pode/não pode, Grid de pontos, legenda do mapa, tabela responsiva, formulário com endereço via `autocomplete`, data e tipo de material, aviso `sticky` e estados visuais acessíveis.

![Protótipo da tela inicial do Recicla Bairro](./15-recicla-bairro/01-inicio.png)
![Protótipo dos pontos do Recicla Bairro](./15-recicla-bairro/02-pontos.png)
![Protótipo do agendamento do Recicla Bairro](./15-recicla-bairro/03-agendamento.png)

## 16. Acessa Cidade — guia de locais e serviços acessíveis

**Desafio:** apresentar informações objetivas de acessibilidade de espaços públicos e serviços, permitindo consulta e avaliação demonstrativa.

**Telas obrigatórias:**

- **Início:** critérios do guia, categorias, locais recomendados e compromisso de acessibilidade.
- **Locais:** listagem com filtros e indicadores textuais de recursos disponíveis.
- **Local e avaliação:** ficha detalhada, tabela de recursos, galeria e formulário de contribuição.

**Aplicações específicas:** este tema deve priorizar WCAG, contraste, zoom, foco, ordem de leitura, links descritivos e ausência de dependência exclusiva de cor; usar tabela de recursos, imagens com descrições úteis e formulário com escalas acompanhadas de rótulos claros.

![Protótipo da tela inicial do Acessa Cidade](./16-acessa-cidade/01-inicio.png)
![Protótipo dos locais do Acessa Cidade](./16-acessa-cidade/02-locais.png)
![Protótipo da avaliação do Acessa Cidade](./16-acessa-cidade/03-avaliacao.png)

## 17. Impulso Lab — vitrine de projetos e startups

**Desafio:** criar a vitrine de uma incubadora acadêmica, apresentando projetos, agenda, áreas de atuação e chamada para novas propostas.

**Telas obrigatórias:**

- **Início:** programa, indicadores, projetos em destaque e próximos encontros.
- **Projetos:** portfólio com estágios, setores e equipe; tabela comparativa de ciclos.
- **Projeto e submissão:** estudo de caso, marcos, equipe e formulário para enviar uma ideia.

**Aplicações específicas:** cards com estados por estágio, indicadores em Grid, linha do tempo com pseudoelementos, logos apenas fictícios/originais, tabela dos ciclos, formulário com URL, área, resumo e aceite, além de componente `sticky` com chamada para submissão.

![Protótipo da tela inicial do Impulso Lab](./17-impulso-lab/01-inicio.png)
![Protótipo dos projetos do Impulso Lab](./17-impulso-lab/02-projetos.png)
![Protótipo da submissão do Impulso Lab](./17-impulso-lab/03-submissao.png)

## 18. Rede Voluntária — oportunidades de impacto social

**Desafio:** conectar pessoas a ações comunitárias, exibindo causas, requisitos, datas e inscrição demonstrativa.

**Telas obrigatórias:**

- **Início:** causas, impacto, oportunidades urgentes e como funciona.
- **Oportunidades:** cards com filtros, datas, carga horária, local e tabela de agenda.
- **Ação e inscrição:** descrição, organização, atividades, requisitos e formulário do voluntário.

**Aplicações específicas:** `article` e `<time>` nas oportunidades, imagens responsáveis e creditadas, Grid de causas, Flexbox nas etiquetas, tabela da agenda, formulário com disponibilidade e preferências, etiqueta de urgência posicionada e transições com respeito a `prefers-reduced-motion`.

![Protótipo da tela inicial da Rede Voluntária](./18-rede-voluntaria/01-inicio.png)
![Protótipo das oportunidades da Rede Voluntária](./18-rede-voluntaria/02-oportunidades.png)
![Protótipo da inscrição na Rede Voluntária](./18-rede-voluntaria/03-inscricao.png)

## Entregáveis

- `README.md` com tema, público, objetivo, mapa do site, tecnologias, créditos e link publicado;
- link do repositório no GitHub, com histórico de commits visível e organizado;
- pasta com os wireframes e guia visual;
- três ou mais páginas HTML válidas e interligadas;
- estilos autorais e framework identificados;
- relatório curto de testes em celular e desktop;
- apresentação de 10 a 15 minutos demonstrando o projeto e justificando decisões.

## Critério de equivalência entre os temas

Independentemente do tema escolhido, a avaliação irá considerar os mesmos eixos: qualidade semântica, acessibilidade, arquitetura da informação, conteúdo, domínio de CSS, responsividade, uso crítico do framework, organização técnica, testes e apresentação. O protótipo serve como ponto de partida visual; a nota deve irá apoiar na implementação e nas decisões demonstradas pelo estudante.
