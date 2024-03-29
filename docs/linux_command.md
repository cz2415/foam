# linux_command


## wc – 统计文件的字节数、字数、行数

* 语法格式：wc [参数] [文件]

| 参数      | 说明                                                                              |
| --------- | --------------------------------------------------------------------------------- |
| -w        | 统计字数，或--words：只显示字数。一个字被定义为由空白、跳格或换行字符分隔的字符串 |
| -c        | 统计字节数，或--bytes或--chars：只显示Bytes数                                     |
| -l        | 统计行数，或--lines：只显示列数                                                   |
| -m        | 统计字符数                                                                        |
| -L        | 打印最长行的长度                                                                  |
| --help    | 显示帮助信息                                                                      |
| --version | 显示版本信息                                                                      |


## sed – 处理编辑文本文件

* 语法格式：sed [参数]

| 参数                                | 说明                                         |
| ----------------------------------- | -------------------------------------------- |
| -e或--expression=<script>           | 以选项中指定的script来处理输入的文本文件     |
| -f<script文件>或--file=<script文件> | 以选项中指定的script文件来处理输入的文本文件 |
| -h或--help                          | 显示帮助                                     |
| -n或--quiet或--silent               | 仅显示script处理后的结果                     |
| -V或--version                       | 显示版本信息                                 |

```bash
# 删除第一行
sed -i '1d' filename
# 范围删除，删除1-3行
sed -i '1,3d' filename
# 删除第n行
sed -i 'nd' filename
# 将第2-5行的内容取代成为No 2-5 number
nl /dir | sed '2,5c No 2-5 number'
```

## ls – 显示指定工作目录下的内容及属性信息

* 语法格式: ls [选项] [文件]

| 参数 | 说明                                             |
| ---- | ------------------------------------------------ |
| -a   | 显示所有文件及目录 (包括以“.”开头的隐藏文件)     |
| -l   | 使用长格式列出文件及目录信息                     |
| -r   | 将文件以相反次序显示(默认依英文字母次序)         |
| -t   | 根据最后的修改时间排序                           |
| -A   | 同 -a ，但不列出 “.” (当前目录) 及 “..” (父目录) |
| -S   | 根据文件大小排序                                 |
| -R   | 递归列出所有子目录                               |

```bash
# 查看某个文件大小
ls -sh filename

# 列出当前工作目录下所有名称是 “s” 开头的文件 
ls -ltr s*

# 列出当前工作目录下所有文件及目录并以文件的大小进行排序
ls -AS
```

## head

* 语法格式：head [参数] [文件]

| 参数 | 说明                           |
| ---- | ------------------------------ |
| -n   | 后面接数字，代表显示几行的意思 |
| -c   | 指定显示头部内容的字符数       |
| -v   | 总是显示文件名的头信息         |
| -q   | 不显示文件名的头信息           |

```bash
# 显示前两行内容并显示文件头信息
head -v -n 2 test.txt 
==> test.txt <==
hello world
hello linuxcool
```

## watch - 周期性执行命令

* watch[参数] [命令]

| 参数             | 说明                                                                                                                             |
| ---------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| -n/--interval    | watch默认每2秒运行一下程序，可以用-n或-interval来指定间隔的时间                                                                  |
| -d/--differences | 用-d或--differences 选项watch 会高亮显示变化的区域。 而-d=cumulative选项会把变动过的地方(不管最近的那次有没有变动)都高亮显示出来 |
| -t/--no-title    | 关闭watch命令在顶部的时间间隔、命令、当前时间的输出                                                                              |
| -h/--help        | 查看帮助文档                                                                                                                     |

重复执行uptime命令：
`[root@linuxcool ~]# watch uptime`
每隔一秒高亮显示网络链接数的变化情况：
`[root@linuxcool ~]# watch -n 1 -d netstat -ant`
每10秒一次输出系统的平均负载：
`[root@linuxcool ~]# watch -n 10 'cat /proc/loadavg'`
监测磁盘inode和block数目变化情况：
`[root@linuxcool ~]# watch -n 1 "df -i;df"`
监测当前目录中test.txt文件的变化：
`[root@linuxcool ~]# watch -d 'ls -l|grep test.txt'`
每5秒执行 count.sh 并标记变化
`watch -n 5 -d './count.sh'`

## netstat命令 – 显示网络状态

* netstat [参数]

| 参数 | 说明                                     |
| ---- | ---------------------------------------- |
| -a   | 显示所有连线中的Socket                   |
| -p   | 显示正在使用Socket的程序识别码和程序名称 |
| -l   | 仅列出在监听的服务状态                   |
| -t   | 显示TCP传输协议的连线状况                |
| -u   | 显示UDP传输协议的连线状况                |
| -i   | 显示网络界面信息表单                     |
| -r   | 显示路由表信息                           |
| -n   | 直接使用IP地址，不通过域名服务器         |

`netstat -ntlp |grep 9192`

## pwdx pid： 查看当前pid进程启动时的工作目录

## ps eww -p <process_pid> : 返回某个进程的执行时的环境变量和完整的命令行

## ps -ef |grep -v 'grep' |grep '/opt/bigdata/bfdscheduler-4.7.0' |awk '{print $2}'
   ps -ef |grep -v 'grep' |grep '/opt/analyse-tactice' |awk '{print $2}'