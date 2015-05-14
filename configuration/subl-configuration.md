# subl-configuration


Sublime Text包含一个命令行工具,subl, 通过命令行处理管理。可以在Sublime Text中打开文件和项目，也可以作为一个unix下的EDITOR工具，例如git和subversion。

###设置(mac)

```
#如果是在默认shell下,
sudo ln -s "/Applications/Sublime\ Text.app/Contents/SharedSupport/bin/subl" /usr/bin/subl

#使用zsh的可以使用以下命令
alias subl="'/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl'"
alias nano="subl"
export EDITOR="subl"
```

进入项目目录，使用命令在Sublime中打开项目
```
subl .
```

###使用方法

```
用法:
subl [arguments] [files]         编辑指定的文件edit the given files
   or: subl [arguments] [directories]   打开指定的目录
   or: subl [arguments] -               编辑stdin

参数Arguments:
  --project <project>: 载入指定的project
  --command <command>: 运行指定的命令
  -n or --new-window:  打开一个新的窗口
  -a or --add:         添加文件夹到当前窗口
  -w or --wait:        返回前等待文件关闭
  -b or --background:  不激活该应用程序
  -s or --stay:        文件关闭后保持应用程序激活状态
  -h or --help:        显示帮助并退出
  -v or --version:     显示版本信息并退出

如果从标准输入--wait是隐式的。 使用--stay当文件关闭是不切换到后台控制台(只与是否有等待的文件有关)

文件名可以通过加:line或者:line:column后缀来指定打开的定位。
用法摘自官方文档
```

###EDITOR

使用Sublime Text作为许多命令提示输入的编辑器，可以设置EDITOR环境变量为：

```
    export EDITOR="subl -w"
    export BUNDLE_EDITOR="subl"
```

特别是-w会指定subl控制器不会退出，直到文件关闭。

