# windows_command

## wsl 参考的对象类型不支持尝试的操作
netsh winsock reset

## mklink 创建链接
mklink [[/d] | [/h] | [/j]] <link> <target>
parameters
| 参数     | 描述                                                      |
| -------- | --------------------------------------------------------- |
| /d       | 创建目录符号链接。 默认情况下，此命令将创建文件符号链接。 |
| /h       | 创建硬链接，而不是符号链接。                              |
| /j       | 创建目录连接。                                            |
| <link>   | 指定正在创建的符号链接的名称。                            |
| <target> | 指定新符号链接引用的路径 (相对或绝对) 。                  |
| /?       | 在命令提示符下显示帮助。                                  |


```console
mklink /d \MyFolder \Users\User1\Documents
mklink /h \MyFile.file \User1\Documents\example.file
rd \MyFolder
del \MyFile.file
```