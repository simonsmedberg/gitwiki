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
When working with alot of people in a project and using git, it is easy to overwrite files that hasn't been correctly updated if you are only working in the `master` branch. So instead you can create a new branch with either the `git branch` command or the `git checkout -b` command.
```
# Usage:
# This command only creates the new branch.
git branch <branch-name>
# This command creates the new branch and instantly checks out to that branch.
git checkout -b <branch-name>

# Example:
git branch newbranch
--
git checkout -b newbranch
``` 
Originally when connecting to a repository, you are in the `master` branch. If you are working in a repository with more branches you can easly switch between them by using the `git checkout` command. 
```
# Usage:
git checkout <branch-name>
```
To see which branches that are available for you, you can issue the `git branch -a` command. 


## Commiting
When you are done with a piece of code and want to upload it to the repository you need to first commit the changes you have made `git commit`. Before you can commit i file/directory you need to add the files you want to commit, you can do this with `git add`.
```python
# Usage:
git add [filename1, filename2, ..., filenameN | directory (includes .)]
git commit -m "<message text here>"

# Example:
git add file1 file2 file3
git commit -m "Updated file1, file2 and file3 with the new function."
```

## Pushing
To upload the changes you have commited to the remote repository, you use the `git push` command.
```
# Usage:
git push [origin | other-path] <branch-name>

# Example
git push origin master 
```

## Fetching
With the `git fetch` command you can update the local repository's knowledge of which files and branches exists on the remote one. 
```
# Usage:
git fetch [origin | other-path] <branch-name>

# Example:
git fetch origin master
```
After this you should be able to switch between branches (see the branches section) and be able to see their files with `ls` command.

## Pulling
If you want to download a file to work with in a repository you can use the `git pull` command to download the content of a branch.
```
# Usage:
git pull [origin | other-path] <branch-name>

# Example, download copy from master branch.
git pull origin master
```

## Merge
When a branch is completed and you want to merge it with another one you can do it in two ways, either the `git merge` or with a sequence of commands.

```
# Usage:
# HEAD is "where" you are, in other words the branch you are in.
git merge <branch-you-want-to-merge-to-HEAD>


# Other sequence would be
git pull origin <branch>
git add .
git commit -a -m "Merging branch1 with branch2"
git push origin <branch>
```

## Misc

### Status
Checking files status, e.g. untracked, is done with the simple command `git status`.

### Log
If you have initilized a local repository you can find information about every push you have made with the `git log` command.

### Diff
You wanna see the difference between commits you can simply write `git diff` and it will show you the difference for each commit that has been made.

### Help!
Use the `git help` command for more informationa about how to use a command. It kinda works like manpages in linux.
```
# Usage:
git help <command>

# Example
git help commit
```