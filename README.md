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



## Commiting


## Pushing

## Fetching

## Pulling