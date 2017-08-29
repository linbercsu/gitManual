# GIT MANUAL

refer <https://git-scm.com/book/en/v2/>

**You can use `git status` for getting hints at any time.**

# configuration

> git config --global pull.rebase true  
git config --global user.email your_email  
git config --global user.name your_name


# work flow

working space ------> staging space ------> permanent space ------> remote repository

## view difference

> git diff   

show difference between working space and permanent space.

For example:  
```
Linlin:gitManual lin$ git diff
diff --git a/README.md b/README.md
index db801b0..2e61588 100644
--- a/README.md
+++ b/README.md
@@ -6,6 +6,13 @@

 working space ------> staging space ------> permanent space

+## show diff

```

## drop changes in working space

> git checkout -- &lt;file&gt;

For example:  

`git checkout -- README.md`


## to staging space
> git add somefiles

For example:  
`git add .  `  
`git add README.md`    
`git add file1 file2`  

## view difference

> git diff --staged

show difference between staging space and permanent space.

For example:

```
Linlin:gitManual lin$ git diff --staged
diff --git a/README.md b/README.md
index 4b353e4..3d8ccb2 100644
--- a/README.md
+++ b/README.md
@@ -6,6 +6,34 @@

 working space ------> staging space ------> permanent space

+## view difference
```

## drop changes in staging space

> git reset HEAD &lt;file&gt;

For example:

`git reset HEAD README.md`  

## to permanent space

> git commit -m "commit messages"

For example:  
`git commit -m "bug fix."`

## to remote repository

> git push repository localBranch:remoteBranch

for example:  

`git push origin master:master`  
`git push origin HEAD:master`  
`git push anotherRep master:masterBackup`  
`git push origin`  
`git push origin HEAD`  
`git push`  


## accept changes from remote

```
git fetch   
git rebase
```
or
```
git fetch
git merge
```
or
```
git pull
```


# view log

## view commit

> git show [commit hash\branch name]  

## view log

> git log [option]

For example:

show log one line by one line.  
`git log --pretty=oneline`

show log commited by Tom.  
`git log --author=Tom`

show log with change details.  
`git log -p`



# stash
stash uncommited changes.  
> git stash  

retrieve the last one.  
> git stash pop

show the list stashed.  
> git stash list


# common commands

|  command  |  description  |  remark  |
| --------- | ------------- | ------- |
| git remote -v | show remote repository address |   |
| git branch -a | show all the branches include local and romote |  |
| git checkout -b myBranch | checkout a new branch named 'myBranch' |  |
| git checkout myBranch | switch to local branch named 'myBranch' | myBranch must exist |
| git reset --hard [commit hash] | make current branch point to specified commit, drop all the changes in staging space | if no commit specified, HEAD will be used. |
| git cherry-pick hash\branch | pick specified commit to current branch | git cherry-pick 0f348732 or git cherry-pick origin/master |
