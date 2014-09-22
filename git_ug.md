### github user guide

#### when you use a proxy 

```
git config --global http.proxy http://{domain}\\\{username}:{password}@{proxy ip}:{proxy port}
```
e.g.
```
git config --global http.proxy http://zju\ouxiaogu:aaa@proxy.zju.edu.cn:3722
```

#### push local file to github

1. git add *
2. git commit -m "1st comment"
3. git push origin master  
