# Git Course
Este é um repositorio teste para ensinar como o Git funciona.

# Comandos

   # Criando o projeto: 
   - mkdir [nome_da_pasta] criando a pasta do projeto;
   - cd [nome_da_pasta] entrando na pasta do projeto;
   - git init inicializando o repositório git;   
   
   # Criando uma nova Branch:
   - git checkout -b [nome_do_branch]
   - git branch mostra qual branch tem e a que está
   - git checkout [nome_do_branch] ir para algum branch
   - git branch -D [nome_do_branch] deleta um branch
   - git merge [nome_da_branch] Mesclar o branch com o master
   - git rebase [nome_da_branch] Aplica a modificação pro topo da lista de commits

   # Git Stash
   - git stash guarda a modificação feita
   - git stash apply  aplica as mudanças guardadas
   - git stash list mostra a lista de todos os stash guardados
   - git stash clear limpa o stash todo

   # Comandos Especiais:
   - git log - mostra todos os commits e o author
   - git log --decorate mostra qual branch foi para qual branch
   - git log --author="nome_do_author" mostro todos os commits do author
   - git shortlog mostra em orgem alfabetica quais são os autores, quantos commits fizeram
   - git log --graph mostra em forma grafica o que tá acontecendo com as branchs
   - git show [rash] mostra o que foi adicionado
   - git diff detalhes da moficação feita.[utilizar antes do commit]
   - git diff --name-only mostra somente o nome do arquivo modificado
   - git checkout [nome_do_arquivo]: Retorna o arquivo para antes dele salvo
      - git reset HEAD [nome_do_arquivo]
   
