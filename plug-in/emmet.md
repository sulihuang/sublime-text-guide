# Emmet

[Emmet github地址](https://github.com/sergeche/emmet-sublime)


Emmet 是 Zen Coding 的升级后改名而成，由Zen Coding 的原作者进行开发维护。它是一款编辑器插件，必须要基于某个编辑器使用。
> Emmet支持的编辑器

 * Sublime Text 2
 * TextMate 1.x
 * Eclipse/Aptana
 * Coda 1.6 and 2.x
 * Espresso
 * Chocolat (可以通过 “Install Mixin” 对话框安装)
 * Komodo Edit/IDE ( Tools → Add-ons)
 * Notepad++
 * PSPad
 * CodeMirror2/3
 * Brackets
 * Adobe Dreamweaver


###Emmet安装

使用 Package Control 安装 Emmet 插件：
- 在 Package Control 中选择 Install package 或者按 Ctrl+Shift+P，
- 打开命令板
输入 pci 然后选择 Install Package
搜索输入 emmet 找到 Emmet Css Snippets，
- 点击就可以自动完成安装。

###Emmet语法

*Emmet 的工作流程：打开 HTML 或 CSS 文件->按语法编写指令->摁下 TAB 键->生成！*

####生成 HTML 文档初始结构

> 输入 **!** 或 **html:5**

```
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    < title>Document</title>
</head>
<body>
</body>
</html>
```
> 输入 **html:xt**

```
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="en">
<head>
    <meta http-equiv="Content-Type" content="text/html;charset=UTF-8">
    < title>Document</title>
</head>
<body>

</body>
</html>
```

####生成 HTML
> 输入**\#page>div.logo+ul#navigation>li*5>a{Item $}**

```
<div id="page">
    <div class="logo"></div>
    <ul id="navigation">
        <li><a href="">Item 1</a></li>
        <li><a href="">Item 2</a></li>
        <li><a href="">Item 3</a></li>
        <li><a href="">Item 4</a></li>
        <li><a href="">Item 5</a></li>
    </ul>
</div>
```

[使用手册](http://www.w3cplus.com/tools/emmet-cheat-sheet.html)

[查看Emmet-API](http://docs.emmet.io/cheat-sheet/)

![API图片](http://7xix3g.com1.z0.glb.clouddn.com/15-5-13/70954100.jpg)
