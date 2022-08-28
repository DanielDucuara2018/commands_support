# Git Overview

## General Commands

```sh
git version # verify git version
git init # initialize an empty repository
git init <FOLDER_NAME> # initialize an empty repository creating a new folder
git add <FILE_NAME> # indexation d'un seul fichier 
git add . # indexation des toutes les modifications
git reset <FILE_NAME> # remove a file from the index zone
git diff # show all modifications in repo before index process
git diff <FILE_NAME>  # show all modification in a given file before index process
git diff -- cached  # show all modifications in repo in index zone
git diff -- cached  <FILE_NAME>  # show all modification in a given file in index zone
git clone <URL_REMOTE_REPOSITORY> <FOLDER_NAME>
```

## Manage remote reposotiries

```sh
git remote -v # show list of remote repositories
git remote show <REMOTE_REPOSITORY_NAME> 
git remote add origin <URL_REMOTE_REPOSITORY>
```

## Setup env variable in git 

```sh
git config --global user.name "<USERNAME>"
git config --global user.email <EMAIL>
git config --global --list
git config --global credential.helper store (optional)
git config --global credential.username "<GITHUB_USERNAME>"
git config --list --show-origin #(remove --global to setup just the current git repostory)
```

## Firt push to github empty remote repository

```sh
git commit -m "<COMMIT_COMMENT>"
git branch -M master # -M to rename a existing branch
git remote add origin https://github.com/username/new_repo
git push -u origin master # -u to add upstream (tracking) reference
```

## Repository state

```sh
git status # show git repository status
git log # show the history of commits
git show <COMMIT_SHA> # show all modifications in a given commit
```

## Checkou to a given commit

```sh
git checkout <HASH_COMMIT> # Change current workspace to a given commit
```

## Branches

```sh
git branch # List of branches
git checkout -b <BRANCH_NAME> # Branch change
```

## Tags
```sh
git tag # list of tags
git tag <TAG_NAME> -n "<TAG_COMMENT>" # add a tag to a given commit
git tag --delete <TAG_NAME> # remove a given tag
git push origin <TAG_NAME> # push a tag
git push --tags # push all tags
```

## Push process

```sh
git add <NAME_FILE> or git add . 
git commit -m "<COMMIT_COMMENT>"
git push
```

## Feth andn pull

```sh
git fetch # DOWNLOAD objects and refs from another repository
git pull # Fetch from and INTEGRATE with another repository or a local branch
```
 
