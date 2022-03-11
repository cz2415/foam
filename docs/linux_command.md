# linux_command


## wc
*统计文本行数*
linux 自带有 `wc` 工具, 可以方便的统计文件中文本的行数
具体通过 `wc --help` 可以查看。
* wc -l filename 就是查看文件里有多少行
* wc -w filename 看文件里有多少个word。
* wc -L filename 文件里最长的那一行是多少个字。

## sed
删除第一行
`sed -i '1d' filename`

范围删除，删除1-3行
`sed -i '1,3d' filename`

删除第n行
`sed -i 'nd' filename`

删除最后一行
`sed -i '$d' filename`