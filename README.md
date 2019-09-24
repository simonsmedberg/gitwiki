# Git commands -

## Setting up the git config
After installing git, you want to configure the git config. This is done with the simple `git config` command.
What you want to do is set the `user.name`, which is the name of the user. This could be literal anything but adding your own name helps when you want to see who changed what and so forth. Then you want to set the `user.email`, which should be the email email of the user.
```
# Usage:
git config user.name <name>
git config user.email <user@mail.com>

# Example
git config user.name simonsmedberg
git config user.email simon.smedberg@hotmail.com
```  
## Initilize a local repository
With git you can setup a local repository on your computer by issuing the command `git init`. This makes git recognize the cwd as a repository.

## Add remote repository
When you want to connect your local repository to a remote repository on GitHub or GitLab or w/e you can do it with the `git remote` command.
```
# Usage:
git remote add origin https://yourgit.com/account/repository.git

# Example (this repository)
git remote add origin https://www.github.com/simonsmedberg/gitwiki.git
```

## Add branches and swapping between branches
When working with alot of people in a project and using git, it is easy to push files that hasn't been update if you are only working in the `master` branch. So instead you can create a new branch with either the `git branch` command or the `git checkout -b` command.
```
# Usage:
# This command only creates the new branch.
git branch <branch-name>
# This command creates the new branch and instantly checks out to that branch.
git checkout -b <branch-name>
``` 
Originally when connecting to a repository, you are in the `master` branch. If you are working in a repository with more branches you can easly switch between them by using the `git checkout` command. 
```
# Usage:
git checkout <branch-name>
```
To see which branches that are available for you, you can issue the `git branch -a` command. 


## Commiting

```
git add [filename | directory (includes .)]
git commit -a -m "<message text here>"

```

## Pushing
```
git push origin <branch-name>
```

## Fetching

## Pulling