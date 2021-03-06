<p align="center">
	<img alt="Git" src="./img/git-icon.png">
</p>
<p align="center">Hi, this is a quick tour to starting with Git. The site is generated by <a href="http://ricostacruz.com/flatdoc/">Flatdoc</a>.</p>

## Create repositories

Create a new local repository with the specified name

```
$ git init [project-name]
```

Clone a remote repository to your local machine

```
$ git clone [url]
```

## Make changes

Once you've made changes to your files, you can list all new or modified files waiting to be commited

```
$ git status 
$ git status -s	 
# -s : short format
```

Add changes (new or modified files) to the **staging area** (or **index**)

```
$ git add [file-name]
# add a specified file
$ git add *			
# add all changed files
```

Commit changes to **HEAD**

```
$ git commit -m "commit message"
```

Now that your changes are in the **HEAD** of your local working directory, which means they are ready to be pushed to your remote repository in Github, then push your changes 

```
$ git push [alias] [branch-name]
$ git push origin master
# push commits to your remote repository (master branch) stored on github 
```

## Branching

For creating a new branch

```
$ git branch [branch-name]
```

For switching to the specified branch 

```
$ git checkout [branch-name]
```

Or you can directly switch to the new branch after creating it

```
$ git checkout -b [branch-name]
```

You can list all local branches in your current working directory.
The current branch will be highlighted with an asterisk (`*`)

```
$ git branch
  develop
* master
```

You can use `-a` to shows all local and remote branches

```
$ git branch -a
  develop
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/develop
  remotes/origin/master
  remotes/upstream/master
```

Or use `-r` to show only remote branches

```
$ git branch -r
  origin/HEAD -> origin/master
  origin/develop
  origin/master
  upstream/master
```

You can delete a specified branch

```
$ git branch -d [branch-name]
```

## Add a remote

To add a new remote, use the `git remote add` command in your working directory 

```
$ git remote add [alias] [url]
```

For an original repo that you've forked

```
$ git remote upstream https://github.com/username/repo.git
# When a repo is cloned, it has a default remote called origin that points to 
# your fork on GitHub, not the original repo it was forked from. To keep track of 
# the original repo, you need to add another remote named upstream
```

For your own repo on Github

```sh
$ git remote origin https://github.com/yourname/repo.git
```

You can list all your remote aliases by running

```
$ git remote
origin
master
$ git remote -v
origin	https://github.com/yourname/repo.git (fetch)
origin	https://github.com/yourname/repo.git (push)
upstream	https://github.com/username/repo.git (fetch)
upstream	https://github.com/username/repo.git (push)
```

## Synchronize changes

If the original repo you forked gets updated, you can fetch any new changes from the original repository by running

```
$ git fetch upstream [branch-name]
```

Combines any changes fetched into your current local branch

```
$ git merge [alias]/[branch-name]
$ git merge upstream/master
# merges changes fetched into your working files
```

Uploads all local branch commits to Github

```
$ git push [alias] [branch-name]
```

You can also use `git pull` to get commits from a remote repository

```
$ git pull 
# when you use git pull, git will merge any pulled commits into the branch 
# you are currently working in, but it may run into frequent conflicts
```

## Review history

You can list all commits for the current branch by running

```
$ git log
$ git log -10 
# limit to 10 last commits
```

To see each commit in a single line

```
$ git log --oneline
```
To see only commits by a particular author

```
$ git log --author=[author-name]
```

To display commits of a specified file

```
$ git log -- [file-name]
```

To generate a pretty ASCII graph of all branches

```
$ git log --graph --oneline --all
```

To output metadata and content changes of the specified commit

```
$ git show [commit]
```

## Configure

You can attach the username to your commit transactions

```
$ git config --global user.name "[username]"
```

You can also attach a email to your commit transactions

```
$ git config --global user.email "[email-address]"
```

For creating an alias for a specified git command by running

```
$ git config --global alias.[alias-name] [git-command]
```

To open the global configuration file (~/.gitconfig) in a text editor

```
$ git config --global --edit
```

## Undo commits

If you did some mistakes, you can undo your commits.

Reset staging area to match the specified commit, but leave the working directory unchanged

```
$ git reset [commit]
```

Reset both the staging area & working directory to match the specified commit, delete uncommited changes and all commits after the specified commit 

```
$ git reset --hard [commit]
```

## Other Git References

[Git cheat sheet made by Atlassian](https://www.google.fr/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&sqi=2&ved=0CDIQFjAA&url=https%3A%2F%2Fwww.atlassian.com%2Fdms%2Fwac%2Fimages%2Flanding%2Fgit%2Fatlassian_git_cheatsheet.pdf&ei=Vc6hU8OjMcqH0AX92oHABw&usg=AFQjCNGqtOA5UPshK3MhDPRsKd3Cz0ytZQ&sig2=3Xdv0qdMXULeQwzUgZSf7Q&bvm=bv.69137298,d.d2k&cad=rja)

[Git cheat sheet made by Github](https://github.com/github/training-materials/blob/master/downloads/github-git-cheat-sheet.pdf?raw=true)

[git - the simple guide](http://rogerdudler.github.io/git-guide/) made by [Roger Dudler](https://github.com/rogerdudler)











