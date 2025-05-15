# Git Course
> That is a repository for helping with the Git.

# Commands
   In your terminal you can enter all the list commands. The commands that start with `git` need a tool [git](https://git-scm.com/downloads) installed in your machine.
   # Creating the project:
   - `mkdir [folder_name]` creating the project folder;
   - `cd [.folder_name]` accessing the project folder;
      * Use `cd ../` to return the folder;
   - `git init` starting the git repository;
   - `git remote add [.name] [.url]` Add a new Remote to Repo;
   
   # Creating a new Branch:
   - `git checkout -b [branch_name]`
   - `git push --set-upstream origin [nome_do_branch]` branch to remote
   - `git branch` listing all lista the branches and in which you are
   - `git checkout [nome_do_branch]` go for branch
   - `git branch -D [nome_do_branch]` delete a branch
   - `git merge [nome_da_branch]` merge branch with master 
   - `git rebase [nome_da_branch]` to apply the modification to the top of the list in commits

   # Git Stash
   Using for save your modifications in a or more files, you can only save a version of each file by branch.
   - `git stash` save the modification made
   - `git stash apply` apply changes saved
   - `git stash list` show the list all stash saved
   - `git stash clear` clear all stash

   # Special Commands:
   - `git log` - show all commits and the author
   - `git log --decorate` show which branch went to for which branch
   - `git log --author="author_name"` show all commits of author
   - `git shortlog` show in alphabetical order which are authors, how many commits made
   - `git log --graph` show in graphic form what happening with branches
   - `git show [rash]` show what was added
   - `git diff` modification details made.[use before commit]
   - `git diff --name-only` show only file name modified
   - `git checkout [file_name]`: returns the file for before he saved
      - `git reset HEAD [file_name]`
   - `git reset --hard [rash]` come back for a commit specific
   



## Aprofundando no Git: Conceitos Essenciais e Boas Práticas

O Git é um sistema de controle de versão distribuído, o que significa que cada desenvolvedor possui uma cópia completa do histórico do projeto em sua máquina local. Isso permite trabalhar offline e oferece grande flexibilidade e velocidade. Compreender seus conceitos fundamentais e adotar boas práticas é crucial para um desenvolvimento de software eficiente e colaborativo.

### O que é Controle de Versão e Por Que Usar Git?

No desenvolvimento de software, ou em qualquer projeto que envolva a criação e modificação de arquivos ao longo do tempo, é essencial ter um sistema que gerencie as diferentes versões desses arquivos. O controle de versão permite que você acompanhe as alterações, reverta para estados anteriores, trabalhe em diferentes funcionalidades simultaneamente sem interferência e colabore de forma organizada com outras pessoas. O Git se destaca por sua eficiência, modelo distribuído e robustez, tornando-se o padrão de fato na indústria.

### Conceitos Fundamentais do Git

Para utilizar o Git de forma eficaz, é importante entender alguns de seus conceitos centrais:

*   **Repositório (Repository):** É o "local" onde o Git armazena todos os arquivos do projeto, seu histórico de alterações e metadados. Existe o repositório local (na sua máquina) e o repositório remoto (geralmente hospedado em plataformas como GitHub, GitLab ou Bitbucket), que serve como um ponto central para colaboração.

*   **Commit:** Um commit é um "snapshot" ou um ponto de salvamento do seu projeto em um determinado momento. Cada commit registra as alterações feitas nos arquivos desde o commit anterior e inclui uma mensagem descritiva que explica o propósito dessas alterações. Os commits formam o histórico do projeto.

*   **Branch:** Branches (ramos) são linhas de desenvolvimento independentes. Eles permitem que você trabalhe em novas funcionalidades, correções de bugs ou experimentos sem afetar a linha principal de desenvolvimento (geralmente chamada de `main` ou `master`). Após a conclusão do trabalho em um branch, ele pode ser mesclado (merged) de volta ao branch principal.

*   **Merge:** É o processo de combinar as alterações de um branch em outro. Por exemplo, após desenvolver uma nova funcionalidade em um branch separado, você faria o merge desse branch no branch `main` para incorporar a nova funcionalidade ao projeto principal.

*   **Rebase:** Assim como o merge, o rebase é uma forma de integrar alterações de um branch em outro. No entanto, o rebase reescreve o histórico de commits, aplicando os commits do branch atual sobre o topo do branch de destino. Isso pode resultar em um histórico mais linear e limpo, mas deve ser usado com cautela, especialmente em branches compartilhados.

*   **Staging Area (Index):** Antes de fazer um commit, você precisa adicionar as alterações que deseja incluir nesse commit à "staging area" (área de preparação ou índice). Isso permite que você selecione precisamente quais modificações farão parte do próximo commit, possibilitando commits mais organizados e atômicos.

*   **HEAD:** É um ponteiro especial que geralmente aponta para o commit mais recente do branch em que você está trabalhando. Ele representa o estado atual do seu diretório de trabalho.

### Fluxo de Trabalho Básico com Git

Um fluxo de trabalho comum com Git envolve os seguintes passos:

1.  **Clonar um repositório (Clone):** Se você está começando a trabalhar em um projeto existente, o primeiro passo é clonar o repositório remoto para a sua máquina local usando `git clone [URL_DO_REPOSITORIO]`.
2.  **Criar um Branch (Branch):** Para trabalhar em uma nova funcionalidade ou correção, crie um novo branch a partir do branch principal: `git checkout -b [NOME_DO_NOVO_BRANCH]`.
3.  **Fazer Alterações:** Modifique os arquivos do projeto conforme necessário.
4.  **Adicionar à Staging Area (Add):** Adicione os arquivos modificados que você deseja incluir no próximo commit à staging area: `git add [NOME_DO_ARQUIVO]` ou `git add .` para adicionar todas as alterações.
5.  **Fazer o Commit (Commit):** Crie um commit com as alterações que estão na staging area, fornecendo uma mensagem descritiva: `git commit -m "Sua mensagem de commit aqui"`.
6.  **Enviar para o Repositório Remoto (Push):** Após fazer um ou mais commits localmente, envie suas alterações (e o novo branch, se for o caso) para o repositório remoto: `git push origin [NOME_DO_SEU_BRANCH]`.
7.  **Atualizar o Repositório Local (Pull/Fetch):** Para obter as alterações mais recentes feitas por outros colaboradores no repositório remoto, use `git pull` (que busca e mescla as alterações) ou `git fetch` (que apenas busca as alterações, permitindo que você as inspecione antes de mesclar).
8.  **Mesclar Branches (Merge):** Quando o trabalho em um branch estiver concluído e testado, você pode mesclá-lo de volta ao branch principal. Primeiro, mude para o branch principal (`git checkout main`), atualize-o (`git pull`), e então execute `git merge [NOME_DO_BRANCH_A_MESCLAR]`.

### Boas Práticas no Uso do Git

Adotar boas práticas torna o uso do Git mais eficiente e a colaboração mais suave:

*   **Escreva Mensagens de Commit Claras e Concisas:** A mensagem de commit deve explicar *o quê* foi alterado e *por quê*. Siga um padrão, como usar o imperativo no título (ex: "Corrige bug de login" em vez de "Corrigido bug de login").
*   **Faça Commits Pequenos e Atômicos:** Cada commit deve representar uma unidade lógica de trabalho. Isso facilita a revisão do código, a identificação de bugs e a reversão de alterações, se necessário.
*   **Use Branches para Tudo:** Crie um novo branch para cada nova funcionalidade, correção de bug ou experimento. Isso mantém o branch principal limpo e estável.
*   **Mantenha o Branch Principal (main/master) Sempre Funcional:** O branch principal deve sempre refletir um estado estável e implantável do projeto.
*   **Faça Pull Frequentemente:** Antes de começar a trabalhar ou antes de fazer um push, atualize seu repositório local com as últimas alterações do remoto para evitar conflitos.
*   **Resolva Conflitos com Cuidado:** Conflitos de merge são comuns em projetos colaborativos. Entenda as alterações conflitantes e resolva-as manualmente antes de prosseguir.
*   **Revise o Código Antes de Mesclar:** Se estiver trabalhando em equipe, utilize Pull Requests (ou Merge Requests) para revisar o código antes de integrá-lo ao branch principal.

### Comandos Úteis Adicionais

Além dos comandos básicos, alguns outros são extremamente úteis no dia a dia:

*   `git status`: Mostra o estado atual do seu diretório de trabalho e da staging area, indicando quais arquivos foram modificados, quais estão na staging area e quais não estão sendo rastreados pelo Git.
*   `git log`: Exibe o histórico de commits do branch atual. Existem diversas opções para formatar a saída e filtrar os commits.
*   `git diff`: Mostra as diferenças entre o seu diretório de trabalho e a staging area, ou entre a staging area e o último commit, ou entre dois commits específicos.
*   `git reset`: Permite desfazer commits ou remover arquivos da staging area. Use com cautela, especialmente a opção `--hard`, que descarta alterações não commitadas.
*   `git stash`: Permite salvar temporariamente alterações não commitadas para que você possa mudar de branch ou trabalhar em outra coisa, e depois aplicar essas alterações de volta.

### A Importância de Plataformas como GitHub

Plataformas como GitHub, GitLab e Bitbucket complementam o Git fornecendo uma interface web para hospedar repositórios remotos, facilitando a colaboração, o gerenciamento de projetos, a revisão de código (através de Pull Requests), o rastreamento de issues e muito mais. Elas são ferramentas essenciais no ecossistema de desenvolvimento moderno.

Dominar o Git é uma habilidade fundamental para qualquer desenvolvedor. Ao entender seus conceitos e aplicar boas práticas, você poderá versionar seus projetos de forma eficaz, colaborar de maneira mais produtiva e manter um histórico limpo e organizado do seu trabalho.

---
*Este conteúdo foi elaborado com base em conhecimentos gerais sobre Git e complementado por informações de guias práticos como o "git - guia prático" (disponível em rogerdudler.github.io/git-guide/) e artigos como "Fundamentos do Git, um guia completo" (disponível em dev.to).*
