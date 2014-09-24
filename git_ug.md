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
