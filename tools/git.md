# Git commands

## Log and format

### Show the commits history in specified format

```txt
#  Different formats

git log --pretty=format:"%h%x09|%ad%x09|%an%x09|%s" --date=short -20 | column -t -s '|'

git log --graph --decorate --pretty=oneline --abbrev-commit

git log --pretty=format:"%h%x09%x09%ad%x09%s%x09%an"

%h = abbreviated commit hash
%x09 = tab (character for code 9)
%an = author name
%ad = author date (format respects --date= option)
%s = subject


#  Grouping by author
git shortlog

```

### Log last n commits

```txt
git log -n 4
```

### Git reflog

#### Manage reflog information, usefull to see for example the complete history

```txt
git reflog
```

<br><br>

## Working with remotes

### Show all branches (remote and local)

```txt
git branch -a
```

### Push on a different repository

### By default when push, git point to the origin repo, so even if we set a new remote repository(<repo_alias>) all subsequent 'git push' will point to the origin repo. In order to point to the new repository we can set the new origin or specify the remote/branch when push

```txt
#  Add the new remote if not already spacified
git remote add <repo_alias> <repo _url>

#  Push the commit on the specified repository and branch
git push <repo_alias> master

```

### Remove remote repository

```txt
git remote rm <repo_alias>
```

### Shows only remote branches

```txt
git branch -r
```

### Inspecting a remote

```txt
git remote show origin
git remote show <repo_alias>
```

### Delete commit from remote repo

```txt
https://stackoverflow.com/questions/1338728/delete-commits-from-a-branch-in-git

git log

#  Find the commit signature you want to back up to
git reset --hard <sha1-commit-id>
git push origin HEAD --force

#  Syncronize local repo
git pull
```

### Remove file or folder from remote repository

```txt
git rm -r --cached some-directory
git push
```

### Cherry pick from different remote

```txt
#  Make sure the different remote is already added (git remote add <repo_alias> <repo _url>)

# fetch from all remotes
git fetch --all

# make sure you're back on the branch you want to cherry-pick to
git cherry-pick <commit signature>

# check the last commit correspond to the commit cherry picked
git log

git push
```

<br><br>

## Undos

### Remove file from index (Undo git add)

```txt
https://www.git-tower.com/learn/git/faq/undo-last-commit/

git reset file.txt

or

git rm --cached <file or folder>

#  Undoing the Last Commit
git reset --soft HEAD~1

#  If you don't want to keep local changes, use the --hard flag
git reset --hard HEAD~1
```

### Undo merge not yet pushed

```txt
git reset --hard ORIG_HEAD
```

### Rebase - squash commit

``` txt
https://www.internalpointers.com/post/squash-commits-into-one-git


Here we wanto to collect the last 9 commit into single one

git rebase -i HEAD~9

In the opened editor leave the 'pick' prefix only for the first line and replace for the last 8 lines the 'pick' in 's' (pick => s) and exit (ESC :wq)
's' stand for squash

Delete all the comment and add one single comment
Save end exit ESC :wq
If the squashed commit are already pushed on remote branch then execute
git push -f
```

### Clone without history

```txt
git clone --depth 1 --no-single-branch <REPO>
```

### Delete a local remote-tracking branch

```txt
#  Check all branches (local,remote and local remote-tracking)
git branch -a
git branch --delete --remotes origin/feature/ssh
```

### Remove remote tag

```txt
git push --delete origin <tag_name>
```

### Delete local tag

```txt
git tag -d <tag_name>
```

<br><br>

## Utilities

* Gitkraken - Free Git GUI for Linux
