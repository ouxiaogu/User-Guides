github user guide
====

Firstly, go to git official manual by following command:

`git help clone`

## started

### 1.when you use a proxy 

```shell
git config --global http.proxy http://{domain}\\\{username}:{password}@{proxy ip}:{proxy port}
git config --global http.proxy http://zju\ouxiaogu:aaa@proxy.zju.edu.cn:3722 # example
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

0. add .gitignore file

    > gitignore has strict format
    >  1. not start from space " *.a" => "*.a"
    >  2. `./util/d2d` => `util/d2d`
    >  find . -executable -type f >>.gitignore
    >  `git rm --cached -r $path/ $file`, to keep the local file and remove it from the 
repository

    ```.gitignore
    # git ls-files --others --exclude-from=.git/info/exclude
    # Lines that start with '#' are comments.
    # For a project mostly in C, the following would be a good set of
    # exclude patterns (uncomment them if you want to use them):
    # *.[oa]
    # *

    # Prerequisites
    *.d

    # Compiled Object files
    *.slo
    *.lo
    *.o
    *.obj

    # Precompiled Headers
    *.gch
    *.pch

    # Compiled Dynamic libraries
    *.so
    *.dylib
    *.dll

    # Fortran module files
    *.mod
    *.smod

    # Compiled Static libraries
    *.lai
    *.la
    *.a
    *.lib

    # Executables
    *.exe
    *.out
    *.app

    # img
    *.bmp
    *.pgm

    # find . -executable -type f >>.gitignore
    apps/mxp/testutil
    apps/mxp/mxp1
    apps/unittest/testutil
    util/crop
    util/d2d
    ```

1. `git init` & `git add .` # init the repository and add changes
2. `git status` // check the correctness of added files 
3. `git rm --cached -r .` or `git rm --cached -r${folder}/${file}` // remove all the file in git repo, but not from local disk
4. repeat 0-2(-3) util the files list is OK
5. `git commit -m "1st comment"`
6. `git push origin master`  


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
C:\Localdata\D\Program Files\Sublime [master +2 ~80 -17 !]> git log
<!-- to find the desired version -->
C:\Localdata\D\Program Files\Sublime [master +2 ~80 -17 !]> git reset --hard 22770b7acec5a3ec4ab032260f13822d6165376d
HEAD is now at 22770b7 tool_st2 
C:\Localdata\D\Program Files\Sublime [master +2 ~0 -0 !]> git push -f
Everything up-to-date
```

### 4. add a unstable rc branch

1. `git branch` -->  显示当前remote server branch list和remote branch的选择
2. `git checkout -b rc1` --> 会在local 创建一个 branch “rc1”
3. `git push origin rc1` --> orgin 相当于local sever(source, 且已经切换到了local的rc1 branch了),后面的rc1 则是remote sever branch.
4. `git branch` --> 再次显示发现已经有rc1,且已被选择

`git push origin \\devshare-brion.asml.com\cnfs-PEG\FEM\SHARED\product_tools\InstantTuning\`

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


### 5. diff


1. diff two submit

    `git diff HEAD~2`
    `git log`
    `git diff $commitID1 $commitID2`


2. show all the branch in local and origin

    `git show-branch --list --all`


### 6. what if fail to pull the latest commit in github

```shell
git pull origin master --force
git remote set-url origin https://{username}:{password}@github.com/{username}/{repository}.git

git commit -a -m 'force sync'
<!-- fatal: Unable to create '~/.git/index.lock': File exists.

Another git process seems to be running in this repository, e.g.
an editor opened by 'git commit'. Please make sure all processes
are terminated then try again. If it still fails, a git process
may have crashed in this repository earlier:
remove the file manually to continue. -->
```

## Brief steps of collaborative work via Git

0. git add all changes into staged file: 

    `git pull original master`

1. resolve conflict
    
    - [Resolving a merge conflict using the command line](https://help.github.com/articles/resolving-a-merge-conflict-using-the-command-line/)
    - [Resolving merge conflicts after a Git rebase](https://help.github.com/articles/resolving-merge-conflicts-after-a-git-rebase/)

1. git add all changes into staged file: 

    `git add *`

2. git to review the added files is what you want, recommend to use `git diff file` before `add` and `git diff --name-only --cached` after `add`:  

    `git diff` # used before `add`, diff between working tree and staged file

    `git diff file` # used before `add`, diff between working tree and staged file

    `git diff --name-only --cached` # used after `add`, just show name

    `git diff --cached` or `git diff --stages` # used after `add`, "git commit" without "-a" option.

    `git diff HEAD` # used before `add`, diff between working tree and last commit, commit w/i "-a", "git commit -a", i.e., firstly add(work tree => staged); then commit (staged => commit)
    

3. git operation to undo all the add or delete the unwanted add:
    
    `git reset` # git to undo 'git add *'
    
    `git rm --cached -r${folder}/${file}` // remove all the file in git repo, but not from local disk

4. when it's ready, merge 'add *' & 'commit' by `commit -a`, or simply use `add` then `commit`: 
    
    `git commit -a -m 'my comment for the commit'`

    `git commit -m 'my comment for the commit'`

5. sync the commit stable enough into remote git by 
    
    `git push origin master` 

    What if below error:
    
    *fatal: could not read Username for 'https://github.com': Invalid argument*

    `git remote set-url origin https://{username}:{password}@github.com/{username}/{repository}.git`

6. git List files in local git repo? 
    
    `git ls-files` # pure file name

    `git ls-tree --full-tree -r HEAD` # list the files and tracked commit id

7. Remove directory from git but NOT local:

    `git rm -r --cached myFolder` # w/i '--cached' is important, otherwise local file is deleted


## Resolve conflicts

1. after pull files from remote by 'git pull origin master', you may check the conflict status by `git status`

    - what if below errors:
    
        *fatal: Could not open file .git/rebase-merge/done for reading: No such file or directory*

        - firstly, `git stash`: (藏, put into local version control, but not push to remote); or `git commit` to store the changes, otherwise the changes will be lost irrevocably.
        - `git rebase --abort`: 

2. Open your favorite text editor, such as ST/ VScode, and navigate to the file that has merge conflicts.
3. To see the beginning of the merge conflict in your file, search the file for the conflict marker `<<<<<<<`, `=======`, `>>>>>>>`, edit the file with both other's changes and your local uncommitted changes
4. Add or stage your changes.

    `git add .`

5. Commit your changes with a comment.

    `git commit -m "Resolved merge conflict by incorporating both suggestions."`


## cheetsheet

- `git stash` - 该命令保存您的本地修改并恢复工作目录以匹配HEAD提交。它允许您将未commit的修改存储到名为stash的缓冲区中，并从正在处理的分支中删除它。您可以稍后通过apply stash to retrieve them。
    
    `git stash apply          # apply stashed changes; see below about --index`

- `git commit` - 这会记录下次推送的更改，此事件也会记录在历史记录中。