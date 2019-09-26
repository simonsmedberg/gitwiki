# Git commands -

## Setting up the git config
After installing git, you want to configure the git config. This is done with the simple `git config` command.
What you want to do is set the `user.name`, which is the name of the user. This could be literal anything but adding your own name helps when you want to see who changed what and so forth. Then you want to set the `user.email`, which should be the email email of the user.
```
# Usage:
git config [<file-option>] [type] [--show-origin] [-z|--null] name [value [value_regex]]
git config [<file-option>] [type] --add name value
git config [<file-option>] [type] --replace-all name value [value_regex]
git config [<file-option>] [type] [--show-origin] [-z|--null] --get name [value_regex]
git config [<file-option>] [type] [--show-origin] [-z|--null] --get-all name [value_regex]
git config [<file-option>] [type] [--show-origin] [-z|--null] [--name-only] --get-regexp name_regex [value_regex]
git config [<file-option>] [type] [-z|--null] --get-urlmatch name URL
git config [<file-option>] --unset name [value_regex]
git config [<file-option>] --unset-all name [value_regex]
git config [<file-option>] --rename-section old_name new_name
git config [<file-option>] --remove-section name
git config [<file-option>] [--show-origin] [-z|--null] [--name-only] -l | --list
git config [<file-option>] --get-color name [default]
git config [<file-option>] --get-colorbool name [stdout-is-tty]
git config [<file-option>] -e | --edit

# Example
git config user.name simonsmedberg
git config user.email simon.smedberg@hotmail.com
```  
## Initilize a local repository
With git you can setup a local repository on your computer by issuing the command `git init`. This makes git recognize the cwd as a repository.
```
# Usage:
git init [-q | --quiet] [--bare] [--template=<template_directory>]
                 [--separate-git-dir <git dir>]
                 [--shared[=<permissions>]] [directory]

# Example:
git init
```

## Add remote repository
When you want to connect your local repository to a remote repository on GitHub or GitLab or w/e you can do it with the `git remote` command.
```
# Usage:
git remote [-v | --verbose]
git remote add [-t <branch>] [-m <master>] [-f] [--[no-]tags] [--mirror=<fetch|push>] <name> <url>
git remote rename <old> <new>
git remote remove <name>
git remote set-head <name> (-a | --auto | -d | --delete | <branch>)
git remote set-branches [--add] <name> <branch>...
git remote get-url [--push] [--all] <name>
git remote set-url [--push] <name> <newurl> [<oldurl>]
git remote set-url --add [--push] <name> <newurl>
git remote set-url --delete [--push] <name> <url>
git remote [-v | --verbose] show [-n] <name>...
git remote prune [-n | --dry-run] <name>...
git remote [-v | --verbose] update [-p | --prune] [(<group> | <remote>)...]


# Example (this repository)
git remote add origin https://www.github.com/simonsmedberg/gitwiki.git
```

**Note** - After doing this you might want to update your local repository with either `git fetch` or `git pull`.

## Add branches and swapping between branches
When working with alot of people in a project and using git, it is easy to overwrite files that hasn't been correctly updated if you are only working in the `master` branch. So instead you can create a new branch with either the `git branch` command or the `git checkout -b` command.
```
# Usage:
git branch [--color[=<when>] | --no-color] [-r | -a]
               [--list] [-v [--abbrev=<length> | --no-abbrev]]
               [--column[=<options>] | --no-column] [--sort=<key>]
               [(--merged | --no-merged) [<commit>]]
               [--contains [<commit]] [--no-contains [<commit>]]
               [--points-at <object>] [--format=<format>] [<pattern>...]
git branch [--track | --no-track] [-l] [-f] <branchname> [<start-point>]
git branch (--set-upstream-to=<upstream> | -u <upstream>) [<branchname>]
git branch --unset-upstream [<branchname>]
git branch (-m | -M) [<oldbranch>] <newbranch>
git branch (-c | -C) [<oldbranch>] <newbranch>
git branch (-d | -D) [-r] <branchname>...
git branch --edit-description [<branchname>]

# Example:
# This command only creates the new branch.
git branch newbranch
```

```
# Usage:
git checkout [-q] [-f] [-m] [<branch>]
git checkout [-q] [-f] [-m] --detach [<branch>]
git checkout [-q] [-f] [-m] [--detach] <commit>
git checkout [-q] [-f] [-m] [[-b|-B|--orphan] <new_branch>] [<start_point>]
git checkout [-f|--ours|--theirs|-m|--conflict=<style>] [<tree-ish>] [--] <paths>...
git checkout [<tree-ish>] [--] <pathspec>...
git checkout (-p|--patch) [<tree-ish>] [--] [<paths>...]

# Example:
# This command creates the new branch and instantly checks out to that branch.
git checkout -b newbranch
``` 
Originally when connecting to a repository, you are in the `master` branch. If you are working in a repository with more branches you can easly switch between them by using the `git checkout` command. 
```
# Usage:
git checkout <branch-name>
```
To see which branches that are available for you, you can issue the `git branch -a` command. 


## Commiting
Before commiting your changes you need to add the untracked files an index so that git knows which files should be commited. You do this with the `git add` command.
```
# Usage:
git add [--verbose | -v] [--dry-run | -n] [--force | -f] [--interactive | -i] [--patch | -p]
                 [--edit | -e] [--[no-]all | --[no-]ignore-removal | [--update | -u]]
                 [--intent-to-add | -N] [--refresh] [--ignore-errors] [--ignore-missing] [--renormalize]
                 [--chmod=(+|-)x] [--] [<pathspec>...]

# Example:
git add file1 file2 file3
```
When all the files that you want to commit has been added, you use the `git commit` command to commit the changes.
```
git commit [-a | --interactive | --patch] [-s] [-v] [-u<mode>] [--amend]
                  [--dry-run] [(-c | -C | --fixup | --squash) <commit>]
                  [-F <file> | -m <msg>] [--reset-author] [--allow-empty]
                  [--allow-empty-message] [--no-verify] [-e] [--author=<author>]
                  [--date=<date>] [--cleanup=<mode>] [--[no-]status]
                  [-i | -o] [-S[<keyid>]] [--] [<file>...]

# Example:
git commit -m "Updated file1, file2 and file3 with the new function."
```

## Pushing
To upload the changes you have commited to the remote repository, you use the `git push` command.
```
# Usage:
git push [--all | --mirror | --tags] [--follow-tags] [--atomic] [-n | --dry-run] [--receive-pack=<git-receive-pack>]
                  [--repo=<repository>] [-f | --force] [-d | --delete] [--prune] [-v | --verbose]
                  [-u | --set-upstream] [--push-option=<string>]
                  [--[no-]signed|--signed=(true|false|if-asked)]
                  [--force-with-lease[=<refname>[:<expect>]]]
                  [--no-verify] [<repository> [<refspec>...]]

# Example:
git push origin master 
```
**Notis** - Before pushing you need to make sure that you don't overwrite a file. 

## Fetching
With the `git fetch` command you can update the local repository's knowledge of which files and branches exists on the remote one. 
```
# Usage:
git fetch [<options>] [<repository> [<refspec>...]]
git fetch [<options>] <group>
git fetch --multiple [<options>] [(<repository> | <group>)...]
git fetch --all [<options>]

# Example:
git fetch origin master
```
After this you should be able to switch between branches (see the branches section) and be able to see their files with `ls` command.

## Pulling
If you want to download a file to work with in a repository you can use the `git pull` command to download the content of a branch.
```
# Usage:
git pull [options] [<repository> [<refspec>...]]

# Example, download copy from master branch:
git pull origin master
```

## Merge
When a branch is completed and you want to merge it with another one you can do it in two ways, either the `git merge` or with a sequence of commands.

```
# Usage:
git merge [-n] [--stat] [--no-commit] [--squash] [--[no-]edit]
               [-s <strategy>] [-X <strategy-option>] [-S[<keyid>]]
               [--[no-]allow-unrelated-histories]
               [--[no-]rerere-autoupdate] [-m <msg>] [<commit>...]
git merge --abort
git merge --continue


# Other sequence would be
git pull origin <branch>
git add .
git commit -a -m "Merging branch1 with branch2"
git push origin <branch>
```

## Misc

### Status
Checking files status, e.g. untracked, is done with the simple command `git status`.
```
# Usage:
git status [<options>...] [--] [<pathspec>...]

# Example:
git status
```

### Log
If you have initilized a local repository you can find information about every push you have made with the `git log` command.

```
# Usage:
git log [<options>] [<revision range>] [[--] <path>...]

# Example:
git log
```

### Diff
You wanna see the difference between commits you can simply write `git diff` and it will show you the difference for each commit that has been made.
```
# Usage:
git diff [options] [<commit>] [--] [<path>...]
git diff [options] --cached [<commit>] [--] [<path>...]
git diff [options] <commit> <commit> [--] [<path>...]
git diff [options] <blob> <blob>
git diff [options] [--no-index] [--] <path> <path>

# Example:
git diff
```

### Help!
Use the `git help` command for more informationa about how to use a command. It kinda works like manpages in linux.
```
# Usage:
git help [-a|--all] [-g|--guide]
          [-i|--info|-m|--man|-w|--web] [COMMAND|GUIDE]

# Example
git help commit
```
