# Encontro 24 - Git e GitHub: Repositório, Commits, Branches, Pull e Push

**Unidade:** Unidade 2  
**Entrega:** Repositório versionado no GitHub

## Visão Geral
Neste encontro, você aprende a usar Git e GitHub como parte do fluxo profissional de desenvolvimento Web.
O objetivo é criar uma conta no GitHub, configurar o Git, iniciar um repositório, registrar commits, conectar o projeto local a um repositório remoto, trabalhar com branches e sincronizar alterações com `pull` e `push`.

Nos encontros anteriores, o foco estava na construção da interface.
Agora, o foco passa a ser a organização da evolução do projeto: cada alteração importante deve ficar registrada em um histórico compreensível.

Ao final da aula, cada estudante deverá ter um repositório no GitHub com:
- arquivos iniciais de um projeto Web;
- pelo menos três commits com mensagens claras;
- uma branch criada, enviada ao GitHub e integrada ao projeto principal;
- `README.md` com informações básicas;
- link do repositório pronto para compartilhamento.

## Conceitos Essenciais
- Controle de versão.
- Diferença entre Git e GitHub.
- Repositório local e repositório remoto.
- Área de trabalho, área de preparação e histórico.
- Commit, mensagem de commit e linha do tempo do projeto.
- Branch principal e branches de trabalho.
- `clone`, `add`, `commit`, `status`, `log`, `remote`, `pull`, `push`, `fetch`, `merge` e `switch`.
- Conflitos de merge.
- Arquivos ignorados com `.gitignore`.
- Boas práticas para o projeto integrador.

## 1) Git e GitHub não são a mesma coisa
**Git** é o sistema de controle de versão.
Ele funciona no computador e registra o histórico de alterações do projeto.

**GitHub** é uma plataforma online que hospeda repositórios Git.
Ela permite backup, colaboração, revisão, publicação e compartilhamento do projeto.

Na disciplina, o GitHub será usado para:
- comprovar a evolução do trabalho por meio do histórico de commits;
- facilitar acompanhamento do projeto;
- compartilhar o repositório final;
- apoiar a publicação do site estático quando necessário.

## 2) Criar uma conta no GitHub
Para usar o GitHub:

1. Acesse <https://github.com/>.
2. Clique em **Sign up**.
3. Informe e-mail, senha e nome de usuário.
4. Escolha um nome de usuário adequado para contexto acadêmico e profissional.
5. Confirme o e-mail pelo link enviado pelo GitHub.
6. Acesse as configurações da conta e revise nome, foto e perfil.
7. Ative autenticação em dois fatores, quando disponível, e guarde os códigos de recuperação.

Boas práticas:
- use um e-mail que você consiga acessar durante todo o semestre;
- evite nomes de usuário ofensivos, aleatórios ou difíceis de identificar;
- não publique senhas, tokens, chaves privadas ou dados pessoais sensíveis;
- mantenha o repositório público apenas quando o conteúdo puder ser compartilhado.

## 3) Instalar e verificar o Git
Antes de iniciar, confira se o Git está instalado:

```bash
git --version
```

Se o terminal mostrar uma versão, o Git está disponível.
Se não estiver instalado, baixe pelo site oficial:

<https://git-scm.com/downloads>

Depois da instalação, feche e abra o terminal novamente.

## 4) Configurar nome, e-mail e branch padrão
O Git precisa saber quem está criando os commits.

Configure seu nome:

```bash
git config --global user.name "Seu Nome"
```

Configure seu e-mail:

```bash
git config --global user.email "seu-email@exemplo.com"
```

Defina `main` como nome padrão da branch inicial:

```bash
git config --global init.defaultBranch main
```

Confira as configurações:

```bash
git config --global --list
```

O e-mail configurado no Git deve ser compatível com o e-mail da conta no GitHub ou com o e-mail privado fornecido pelo próprio GitHub.

## 5) Criar a pasta do projeto
Crie uma pasta de prática:

```bash
mkdir projeto-git-github
cd projeto-git-github
```

Dentro dessa pasta, crie os arquivos:

```text
projeto-git-github/
  index.html
  styles.css
  README.md
  .gitignore
```

Conteúdo inicial sugerido para `index.html`:

```html
<!doctype html>
<html lang="pt-BR">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Projeto com Git e GitHub</title>
    <link rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <header>
      <h1>Projeto com Git e GitHub</h1>
      <p>Primeira versão versionada do projeto.</p>
    </header>

    <main>
      <section>
        <h2>Objetivo</h2>
        <p>Praticar versionamento, commits, branches e repositório remoto.</p>
      </section>
    </main>
  </body>
</html>
```

Conteúdo inicial sugerido para `styles.css`:

```css
body {
  margin: 0;
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.5;
}

header,
main {
  width: min(92%, 60rem);
  margin: 0 auto;
}

header {
  padding: 3rem 0 1rem;
}
```

Conteúdo inicial sugerido para `README.md`:

```md
# Projeto com Git e GitHub

Projeto de prática da disciplina de Padrões Web.

## Objetivo

Aprender a versionar um projeto Web com Git e publicar o repositório no GitHub.

## Tecnologias

- HTML
- CSS
- Git
- GitHub
```

Conteúdo inicial sugerido para `.gitignore`:

```gitignore
.DS_Store
Thumbs.db
*.log
.env
node_modules/
dist/
```

Mesmo que alguns itens não sejam usados agora, eles ajudam a evitar arquivos desnecessários em projetos futuros.

## 6) Iniciar um repositório Git local
Dentro da pasta do projeto, execute:

```bash
git init
```

Veja o estado do projeto:

```bash
git status
```

O Git deve indicar que existem arquivos ainda não rastreados.

### O que aconteceu?
O comando `git init` criou um repositório Git dentro da pasta.
A partir desse ponto, o Git consegue acompanhar alterações nos arquivos do projeto.

## 7) Entender o ciclo básico: trabalho, preparação e commit
O fluxo local mais comum é:

1. Alterar arquivos.
2. Conferir o estado com `git status`.
3. Preparar arquivos com `git add`.
4. Registrar um commit com `git commit`.
5. Conferir o histórico com `git log`.

Prepare os arquivos:

```bash
git add index.html styles.css README.md .gitignore
```

Confira novamente:

```bash
git status
```

Crie o primeiro commit:

```bash
git commit -m "Cria estrutura inicial do projeto"
```

Veja o histórico resumido:

```bash
git log --oneline
```

### Boas mensagens de commit
Uma boa mensagem deve indicar uma mudança concreta.

Exemplos adequados:

```text
Cria estrutura inicial do projeto
Adiciona estilos base da página inicial
Documenta objetivo e tecnologias no README
```

Exemplos fracos:

```text
alterações
coisas
final
commit
```

Para o projeto integrador, evite entregar um repositório com apenas um commit final.
O histórico deve mostrar evolução real.

## 8) Criar commits incrementais
Faça uma alteração em `README.md`, adicionando uma seção de autor:

```md
## Autor

Nome do estudante ou equipe.
```

Confira o que mudou:

```bash
git status
git diff
```

Prepare e registre:

```bash
git add README.md
git commit -m "Documenta autoria do projeto"
```

Agora altere `styles.css`, por exemplo:

```css
body {
  margin: 0;
  background-color: #f5f7fb;
  color: #1f2937;
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.5;
}
```

Registre outro commit:

```bash
git add styles.css
git commit -m "Adiciona cores base da interface"
```

Confira o histórico:

```bash
git log --oneline
```

## 9) Criar um repositório no GitHub
Com o projeto local já iniciado, crie um repositório vazio no GitHub.

Passo a passo:

1. Acesse <https://github.com/>.
2. Entre na sua conta.
3. Clique em **New repository**.
4. Defina o nome do repositório, por exemplo `projeto-git-github`.
5. Escreva uma descrição curta.
6. Escolha **Public** se o professor precisar acessar sem convite.
7. Escolha **Private** apenas se você for compartilhar acesso manualmente.
8. Não marque a opção de criar `README`, `.gitignore` ou licença se esses arquivos já existem no projeto local.
9. Clique em **Create repository**.

Depois da criação, o GitHub mostrará comandos para conectar o repositório local ao remoto.

## 10) Conectar o repositório local ao GitHub
No terminal, ainda dentro da pasta do projeto, execute:

```bash
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/projeto-git-github.git
git remote -v
```

Substitua `SEU-USUARIO` pelo seu nome de usuário no GitHub.

Envie a branch `main` para o GitHub:

```bash
git push -u origin main
```

O `-u` define uma relação entre a branch local `main` e a branch remota `origin/main`.
Depois disso, nos próximos envios, geralmente basta usar:

```bash
git push
```

Atualize a página do repositório no navegador e confira se os arquivos aparecem no GitHub.

## 11) Autenticação no GitHub
Ao usar `push` pela primeira vez, o GitHub pode solicitar autenticação.

Possibilidades comuns:

- login pelo navegador;
- gerenciador de credenciais do sistema;
- token de acesso pessoal;
- chave SSH.

Para a disciplina, HTTPS costuma ser suficiente em laboratório.
Se você já usa SSH, também pode conectar o remoto com endereço SSH:

```bash
git remote set-url origin git@github.com:SEU-USUARIO/projeto-git-github.git
```

Não cole tokens, senhas ou chaves privadas dentro do projeto.

## 12) Clonar um repositório existente
Quando o repositório já existe no GitHub, ou quando você está usando outro computador, use `clone`.

```bash
git clone https://github.com/SEU-USUARIO/projeto-git-github.git
cd projeto-git-github
```

O `clone` baixa o histórico, os arquivos e a configuração do remoto.

Use esse fluxo quando:
- você criou o repositório primeiro no GitHub;
- vai continuar o trabalho em outro computador;
- vai colaborar em um repositório de equipe;
- precisa recuperar uma cópia limpa do projeto.

## 13) Fluxo cotidiano de trabalho
Antes de começar a editar:

```bash
git status
git pull
```

Depois de editar:

```bash
git status
git diff
git add nome-do-arquivo.html
git commit -m "Descreve a alteração feita"
git push
```

Em projetos simples, o ciclo do dia a dia é:

```text
pull -> editar -> status -> add -> commit -> push
```

Use `pull` antes de trabalhar quando:
- você alterou arquivos pelo GitHub;
- trabalhou em outro computador;
- outra pessoa da equipe enviou commits;
- a branch remota pode estar mais atualizada que a local.

## 14) Comandos de consulta rápida
| Comando | Para que serve |
|---|---|
| `git status` | Mostra arquivos modificados, preparados e pendentes. |
| `git add arquivo` | Prepara arquivo para o próximo commit. |
| `git add .` | Prepara todas as alterações da pasta atual. Use depois de revisar. |
| `git commit -m "mensagem"` | Registra um ponto no histórico. |
| `git log --oneline` | Mostra o histórico resumido. |
| `git diff` | Mostra alterações ainda não preparadas. |
| `git diff --staged` | Mostra alterações já preparadas. |
| `git remote -v` | Lista repositórios remotos conectados. |
| `git pull` | Baixa e integra alterações remotas. |
| `git push` | Envia commits locais ao remoto. |
| `git branch` | Lista branches locais. |
| `git switch nome` | Troca para outra branch. |
| `git switch -c nome` | Cria e troca para uma nova branch. |

## 15) Criar e usar branches
Uma branch permite trabalhar em uma alteração sem mexer diretamente na linha principal do projeto.

Crie uma branch para melhorar o cabeçalho:

```bash
git switch -c melhoria-cabecalho
```

Confira a branch atual:

```bash
git branch
```

Edite `index.html` e `styles.css`.
Depois, registre um commit:

```bash
git status
git add index.html styles.css
git commit -m "Melhora apresentação do cabeçalho"
```

Envie a branch para o GitHub:

```bash
git push -u origin melhoria-cabecalho
```

Agora o GitHub terá a branch `melhoria-cabecalho`.

## 16) Integrar uma branch ao projeto principal
Há dois caminhos comuns.

### Caminho 1: merge pelo terminal
Volte para a branch principal:

```bash
git switch main
git pull
```

Integre a branch:

```bash
git merge melhoria-cabecalho
git push
```

Depois, se a branch não for mais necessária:

```bash
git branch -d melhoria-cabecalho
git push origin --delete melhoria-cabecalho
```

### Caminho 2: Pull Request no GitHub
No GitHub:

1. Abra o repositório.
2. Acesse a branch enviada.
3. Clique em **Compare & pull request** quando o GitHub sugerir.
4. Escreva um título claro.
5. Descreva o que mudou.
6. Revise os arquivos alterados.
7. Crie o Pull Request.
8. Faça o merge se estiver tudo correto.
9. Atualize a branch local:

```bash
git switch main
git pull
```

Em projetos de equipe, Pull Request ajuda a revisar alterações antes de integrar.

## 17) Entender `fetch`, `pull` e `push`
`git fetch` baixa informações do remoto, mas não integra automaticamente.

```bash
git fetch origin
```

`git pull` baixa e integra as alterações na branch atual.

```bash
git pull origin main
```

`git push` envia commits locais para o remoto.

```bash
git push origin main
```

Resumo:

```text
fetch: olha o que mudou no remoto
pull: traz e integra o que mudou no remoto
push: envia seus commits para o remoto
```

Quando estiver em dúvida, use:

```bash
git status
git log --oneline --decorate --all --graph
```

## 18) Resolver conflitos de merge
Conflitos acontecem quando duas alterações incompatíveis ocorrem na mesma parte de um arquivo.

Exemplo de marcação de conflito:

```text
<<<<<<< HEAD
Texto que está na sua branch atual.
=======
Texto que veio da outra branch ou do remoto.
>>>>>>> origin/main
```

Para resolver:

1. Abra o arquivo indicado pelo Git.
2. Leia as duas versões.
3. Escolha o conteúdo final correto.
4. Apague as marcações `<<<<<<<`, `=======` e `>>>>>>>`.
5. Salve o arquivo.
6. Teste o projeto.
7. Prepare o arquivo corrigido:

```bash
git add nome-do-arquivo.html
```

8. Finalize o merge:

```bash
git commit
```

9. Envie para o GitHub:

```bash
git push
```

Evite resolver conflito apagando tudo sem entender.
O conflito é uma decisão de conteúdo, não apenas um erro técnico.

## 19) O que não deve ir para o repositório
Não versionar:

- senhas;
- tokens;
- chaves privadas;
- arquivos `.env`;
- dados pessoais reais;
- arquivos temporários do sistema;
- dependências geradas automaticamente, como `node_modules/`;
- arquivos grandes sem necessidade.

O `.gitignore` informa ao Git quais arquivos devem ser ignorados.

Exemplo:

```gitignore
.env
node_modules/
dist/
*.log
.DS_Store
Thumbs.db
```

Se um arquivo sensível já foi enviado por engano, apenas apagá-lo em um commit novo pode não ser suficiente, porque ele permanece no histórico.
Avise o professor e troque imediatamente a senha ou token comprometido.

## 20) README mínimo para o projeto integrador
O `README.md` do projeto integrador deve permitir que outra pessoa entenda o trabalho.

Estrutura recomendada:

```md
# Nome do Projeto

Breve descrição do projeto.

## Tema

Tema escolhido no catálogo do projeto integrador.

## Público-alvo

Quem o site pretende atender.

## Objetivo

Qual problema ou necessidade o site aborda.

## Mapa do site

- Página inicial
- Página de listagem ou catálogo
- Página de detalhe, formulário ou contato

## Tecnologias utilizadas

- HTML
- CSS
- Bootstrap
- Git e GitHub

## Créditos

Imagens, textos e referências utilizadas.

## Link do site publicado

URL do GitHub Pages ou outra publicação.

## Link do repositório

URL do repositório no GitHub.
```

## 21) Publicação com GitHub Pages
Quando o projeto estiver pronto para publicação estática:

1. Envie todos os commits para o GitHub.
2. Abra o repositório no GitHub.
3. Acesse **Settings**.
4. Procure a seção **Pages**.
5. Escolha a branch `main`.
6. Escolha a pasta raiz do projeto, quando aplicável.
7. Salve a configuração.
8. Aguarde o GitHub gerar a URL.
9. Copie o link publicado para o `README.md`.

O GitHub Pages funciona bem para projetos estáticos com HTML, CSS e JavaScript no navegador.

## 22) Histórico aceitável no projeto integrador
Um bom histórico mostra progresso.

Exemplo de sequência adequada:

```text
Cria estrutura inicial do projeto
Adiciona navegação principal
Implementa página de catálogo
Adiciona formulário de interesse
Aplica estilos responsivos
Documenta créditos das imagens
Publica link do GitHub Pages
```

O que evitar:

```text
commit único no fim do trabalho
vários commits chamados "teste"
commits enormes misturando muitas mudanças
histórico sem relação com a evolução real
arquivos do projeto enviados apenas por upload manual no GitHub
```

Para equipes, cada integrante deve participar do histórico sempre que possível.

## 23) Exercício aplicado
Crie um repositório de prática e realize o fluxo completo.

### Requisitos
- criar ou acessar uma conta no GitHub;
- configurar `user.name`, `user.email` e branch padrão `main`;
- criar uma pasta de projeto com `index.html`, `styles.css`, `README.md` e `.gitignore`;
- iniciar o repositório com `git init`;
- criar pelo menos três commits;
- criar um repositório remoto no GitHub;
- conectar o remoto com `git remote add origin`;
- enviar a branch `main` com `git push -u origin main`;
- criar uma branch chamada `melhoria-readme`;
- alterar o `README.md` nessa branch;
- fazer commit na branch;
- enviar a branch ao GitHub;
- integrar a branch por merge local ou Pull Request;
- conferir o histórico final no GitHub.

### Entrega da aula
Enviar o link do repositório no GitHub.

O repositório deve conter:
- arquivos do projeto;
- `README.md` preenchido;
- histórico com commits nomeados;
- branch de trabalho criada durante a prática ou registro do Pull Request.

## 24) Validação rápida antes de considerar concluído
- O Git está instalado e configurado.
- O repositório local foi iniciado corretamente.
- O projeto possui commits com mensagens claras.
- O repositório remoto aparece em `git remote -v`.
- A branch `main` foi enviada ao GitHub.
- O repositório abre no navegador.
- Existe pelo menos uma branch de trabalho.
- O fluxo `pull -> editar -> add -> commit -> push` foi compreendido.
- O `README.md` explica o projeto.
- Nenhum arquivo sensível foi enviado.

## 25) Erros comuns
- criar conta no GitHub e esquecer de confirmar o e-mail;
- configurar o Git com e-mail diferente do usado no GitHub sem entender o impacto;
- criar `README.md` no GitHub e também localmente, gerando históricos diferentes logo no início;
- editar arquivos e esquecer de fazer `git add`;
- fazer `commit` e esquecer de fazer `push`;
- tentar `push` sem antes fazer `pull` quando o remoto está mais atualizado;
- trabalhar sempre direto na `main` em alterações experimentais;
- usar mensagens genéricas como "final", "teste" ou "alterações";
- versionar arquivos temporários, dependências ou dados sensíveis;
- resolver conflitos apagando conteúdo sem revisar.

## Materiais para Aprofundamento
- [GitHub Docs - Criar uma conta no GitHub](https://docs.github.com/en/get-started/start-your-journey/creating-an-account-on-github)
- [GitHub Docs - Configurar o Git](https://docs.github.com/en/get-started/git-basics/set-up-git)
- [GitHub Docs - Guia rápido de repositórios](https://docs.github.com/en/repositories/creating-and-managing-repositories/quickstart-for-repositories)
- [GitHub Docs - Enviar commits para um repositório remoto](https://docs.github.com/en/get-started/using-git/pushing-commits-to-a-remote-repository)
- [GitHub Docs - Obter alterações de um repositório remoto](https://docs.github.com/en/get-started/using-git/getting-changes-from-a-remote-repository)
- [Git Book - Fundamentos de Git](https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository)
- [Git Book - Branches](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)
- [GitHub Docs - GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site)

## Checklist de Compreensão
- [ ] Consigo explicar a diferença entre Git e GitHub.
- [ ] Consigo configurar nome e e-mail no Git.
- [ ] Consigo iniciar um repositório com `git init`.
- [ ] Consigo criar commits pequenos e bem nomeados.
- [ ] Consigo criar um repositório no GitHub.
- [ ] Consigo conectar o repositório local ao remoto.
- [ ] Consigo usar `push` para enviar alterações.
- [ ] Consigo usar `pull` para trazer alterações.
- [ ] Consigo criar, trocar, enviar e integrar branches.
- [ ] Consigo identificar e resolver conflitos simples.
- [ ] Consigo montar um `README.md` útil para o projeto integrador.

## Resumo Final
Neste encontro, você configurou o fluxo básico de versionamento que será exigido no projeto integrador.
Git registra a evolução do código; GitHub hospeda, compartilha e torna esse histórico verificável.

A partir de agora, cada entrega importante deve ser acompanhada por commits claros e por um repositório organizado.

No próximo encontro, o foco passa para frameworks HTML/CSS e Bootstrap, com CDN, containers, grid e utilitários.

## Questões de Fixação
1. Qual é a diferença entre Git e GitHub?
<!-- Gabarito: Git é o sistema de controle de versão; GitHub é uma plataforma online que hospeda repositórios Git e oferece recursos de colaboração, compartilhamento e publicação. -->

2. Para que serve `git add` antes de `git commit`?
<!-- Gabarito: Serve para preparar quais alterações entrarão no próximo commit. -->

3. O que o comando `git push` faz?
<!-- Gabarito: Envia commits locais para o repositório remoto configurado. -->

4. Quando é recomendável executar `git pull`?
<!-- Gabarito: Antes de começar a trabalhar ou antes de enviar alterações, especialmente quando o projeto pode ter sido alterado no GitHub, em outro computador ou por outra pessoa. -->

5. Por que usar branches?
<!-- Gabarito: Para desenvolver alterações separadas da linha principal, facilitando testes, revisão e integração controlada. -->

6. O que deve ser feito ao encontrar um conflito de merge?
<!-- Gabarito: Abrir o arquivo, comparar as versões, decidir o conteúdo final, remover as marcações de conflito, testar, adicionar o arquivo corrigido e concluir o merge com commit. -->
