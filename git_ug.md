github user guide
====

### 1.when you use a proxy 

```
git config --global http.proxy http://{domain}\\\{username}:{password}@{proxy ip}:{proxy port}
```
e.g.
```
git config --global http.proxy http://zju\ouxiaogu:aaa@proxy.zju.edu.cn:3722
```

### 2.push local file to github

1. git add *
2. git commit -m "1st comment"
3. git push origin master  

### 3. rollback to an specific version.
I will use a real case as the example: Because of my misoperation, the critical SublimeREPL package can not work, so I need to rollback.
```
C:\Localdata\D\Program Files\Sublime [master +2 ~80 -17 !]> git reset --hard 227
70b7acec5a3ec4ab032260f13822d6165376d
HEAD is now at 22770b7 tool_st2
C:\Localdata\D\Program Files\Sublime [master +2 ~0 -0 !]> git push -f
Everything up-to-date
```
### 4. add a unstable rc branch
1. git branch -->  显示当前remote server branch list和remote branch的选择
2. git checkout -b rc1 --> 会在local 创建一个 branch “rc1”
3. git push origin rc1 --> orgin 相当于local sever(source,且已经切换到了local的rc1 branch了),后面的rc1 则是remote sever branch.
4. git branch --> 再次显示发现已经有rc1,且已被选择
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
