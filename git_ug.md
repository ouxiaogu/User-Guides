github user guide
====

Access the help file in github.

```
git help clone
```

### 1.when you use a proxy 

```
git config --global http.proxy http://{domain}\\\{username}:{password}@{proxy ip}:{proxy port}
```
e.g.
```
git config --global http.proxy http://zju\ouxiaogu:aaa@proxy.zju.edu.cn:3722
```

If you decide at any time to reset this proxy and work without (no proxy), commands to use:

```
git config --global --unset http.proxy
git config --global --unset https.proxyc
```
Finally, to check the currently set proxy;

```
git config --global --get http.proxy
git config --global --get https.proxy
```

### 2.push local file to github

1. git add *
2. git commit -m "1st comment"
3. git push origin master  

>**Note**
> if you just want to clone the repository to local, use git clone
> <code>git clone -l -s . C:\copy0816</code>
> 
> Don't miss the source directory `.`. 

**Clones a repository to your computer**
```
git clone https://github.com/USERNAME/REPOSITORY.git
```

### 3. rollback to an specific version.
I will use a real case as the example: Because of my misoperation, the critical SublimeREPL package can not work, so I need to rollback. 
Firstly , copy the full SHA of the previous submit; Then set up the head to this version of submit; At last, push this version to local 

```
C:\Localdata\D\Program Files\Sublime [master +2 ~80 -17 !]> git reset --hard 22770b7acec5a3ec4ab032260f13822d6165376d
HEAD is now at 22770b7 tool_st2 
C:\Localdata\D\Program Files\Sublime [master +2 ~0 -0 !]> git push -f
Everything up-to-date
```
### 4. add a unstable rc branch

1. git branch -->  显示当前remote server branch list和remote branch的选择
2. git checkout -b rc1 --> 会在local 创建一个 branch “rc1”
3. git push origin rc1 --> orgin 相当于local sever(source,且已经切换到了local的rc1 branch了),后面的rc1 则是remote sever branch.
4. git branch --> 再次显示发现已经有rc1,且已被选择

git push origin \\devshare-brion.asml.com\cnfs-PEG\FEM\SHARED\product_tools\InstantTuning\

```
C:\Localdata\D\Note\lua [master +0 ~3 -0]> git branch
* master
C:\Localdata\D\Note\lua [master +0 ~3 -0]> git checkout -b rc1
M       .gitattributes
Switched to a new branch 'rc1'
C:\Localdata\D\Note\lua [rc1 +0 ~3 -0]> git push origin rc1
Total 0 (delta 0), reused 0 (delta 0)
To https://github.com/ouxiaogu/lua_note.git
 * [new branch]      rc1 -> rc1
C:\Localdata\D\Note\lua [master +0 ~3 -0]> git branch
  master
* rc1
```

### 5. remove files from the GitHub repository 

Q: [How to remove files from the GitHub repository?](http://stackoverflow.com/questions/11121352/how-to-remove-files-from-the-github-repository)
A: `git rm --cached $file_path`, to keep the local file and remove it from the 
repository

```
C:\Localdata> git rm --cached .\9blog\BF.md
rm '9blog/BF.md'
C:\Localdata> git rm --cached .\9blog\OT.md
rm '9blog/OT.md'
C:\Localdata\D\Note\lua [rc1 +0 ~0 -2 | +3 ~0 -0 !]> git commit -m "r141023"
[rc1 d7209d0] r141023
 2 files changed, 658 deletions(-)
 delete mode 100644 9blog/BF.md
 delete mode 100644 9blog/OT.md
C:\Localdata\D\Note\lua [rc1 +3 ~0 -0 !]> git push
```

Q2: [Exclude folder from github](http://stackoverflow.com/questions/16692710/exclude-folder-from-github)
A: just add a file named as *.gitignore* in your repository. And Add the folder name  into this file. e.g. `legacy`



### check


1. diff two submit

    `git diff HEAD~2`
    `git log`
    `git diff $commitID1 $commitID2`



```
git init 
git add * # for add

git commit -m 'before vocation'
```

```
git status
git add *
git rm test.py # remove need to specify filename
git commit -m 'after vocation'
git diff HEAD~2
git diff HEAD^ HEAD

git reset --hard <tag/branch/commit id>
```

How to list all the files in a commit?

git diff-tree --no-commit-id --name-only -r COMMIT_ID


git config receive.denyCurrentBranch ignore


1. change the remote repository into bare

git config --bool core.bare true

git status

git push 

1. show all the branch in local and origin

git show-branch --list --all


collaboration by git 

```bash
-- 1. clone a local repository for SHARED folder
git clone $SHARED\ErrorSourceAnalysis
-- 2. status, add & commit if your change list is tested and stable 
git status
git add xxx.py
git commit -m 'your change'
-- 3. push your change list into SHARED folder
git push origin master
-- if failed with error: failed to push some refs
-- rebase your local repository with the latest code by pull
git pull --rebase origin master
-- if this error occurs when use pull: "refusing to pull with rebase: your working tree is not up-to-date"
-- This means your tree is not the latest one, you still have some file to commit
-- you can use step 2 or use these steps to omit the latest editing
git stash      # save uncommitted changes
git pull -r    # pull using rebase (translators omit "-r")
git stash pop  # reapply previously saved changes
-- After your fix the merge conflict in <some-file>, then you need to add it again, and rebase
git add <some-file>
git rebase --continue
--  If you get to this point and realize and you have no idea what’s going on, Just execute the following command and you’ll be right back to where you started before you ran 
git rebase --abort
-- After done synchronizing with the central repository, you will be able to publish your changes successfully:
git push origin master
-- if still error: refusing to update checked out branch: refs/heads/master

```


git config receive.denyCurrentBranch updateInstead