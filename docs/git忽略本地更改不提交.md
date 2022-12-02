# git忽略本地更改不提交

* 忽略
`git update-index --assume-unchanged masterdata-web/src/main/java/com/bdos/commons/result/GoverCode.java`

* 恢复
`git update-index --no-assume-unchanged masterdata-web/src/main/java/com/bdos/commons/result/GoverCode.java`

* 列出所有 
`git ls-files -v | grep "^[a-z]"`

* 添加.gitconfig
```
[alias]
    ignored = !git ls-files -v | grep "^[a-z]"
```