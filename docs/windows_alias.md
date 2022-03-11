# windows_alias

在任意目录下创建 cmd_auto.bat , 输入自己需要的常用命令的别名
 
 ```bat
@echo off
doskey code=code-insiders $*
 ```

doskey相当于Linux中的alias，等号左边是右边的别名；
$*表示这个命令还可能有其他参数；

win+r，键入regedit，进入地址：计算机\HKEY_CURRENT_USER\Software\Microsoft\Command Processor
右边空白处右键新建->字符串值。

双击编辑该值，数值数据里填刚才新建的bat文件的路径（`C:\cmd_auto.bat`）


bash alias

aliases.sh

```bash
    alias ls='ls -F --color=auto --show-control-chars'
    alias ll='ls -l'
    alias code='code-insiders'
```