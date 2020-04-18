# Read: 03
#### 4/14/20

# Git Terminal Cheat Sheet

## Config and Help
___
`git config -- global user.name "Jane Smith"` sets the signature name
- `git config --global user.name` returns the signature name

`git config -- global user.email "example@email.com"` sets the signature email
- `git config --global user.email` returns the signature email

`git config --list` returns settings inside the config file

### Help Commands
``` git
git help *command*
git *command --help
man git-*command*
```

## Setting up a Repo
___
## Importing

`git init` initializes the folder into a git repo

`git add -a` adds everything in the folder to the staging area

`git commit -m "First Commit"` commits everything from the staging area to the repo

## Cloning

`git clone [url]` Clone the repo from github into current folder

`git clone [url] [directory]` Clone the repo from github into specified directory

## Check File Status

`git status` returns the status of the file (nothing to commit or a list of the changed files)

## Tracking and Staging New Files

`git add [filename]` adds [filename] to the staging area

`git add *` adds all files in a repo

## Committing

`git commit -m "message"` commit staged items to repo

`git commit -a` commits a snapshot of all mods.

## Pushing Changes

`git push origin master` pushes local changes to remote repository names 'origin'

`git stash` hides current commits so you can pull from master to prevent a merge conflict.

`git stash apply` after pulling from origin master you can apply the stashed commits in place.

## Remote Repositories

`git remote` returns the name of the remote repo

`git remote -v` returns the remote URLs (push and pull)

`git remote add shortname url` creates a new remote git repository with a short name


___


## TODO read through git reference 
###### [Git Documents](https://git-scm.com/docs/)


### [Git Add](https://git-scm.com/docs/git-add) [option]


### Getting Username and Password to be saved in windows

`git config --global credential.helper store`
check to see if its good at `~cat .gitconfig`

Should look like:
```
[user]
    email = name@email.com
    name = Jane Doe
[credential]
    helper = store
```