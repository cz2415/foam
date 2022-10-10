# win10系统禁用强制签名


1. 在开始按钮点击右键，选择“命令提示符（管理员）”

2. 执行以下命令（复制后，在命令提示符中单击鼠标右键即可完成粘贴，然后按回车键执行）：
`bcdedit.exe /set nointegritychecks on`

3. 命令瞬间执行完毕，若想恢复默认验证，执行如下命令即可：
`bcdedit.exe /set nointegritychecks off`