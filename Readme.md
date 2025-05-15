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
   
