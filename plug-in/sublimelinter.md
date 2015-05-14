# SublimeLinter

[官方文档](http://www.sublimelinter.com/en/latest/index.html)

[github地址](https://github.com/SublimeLinter/SublimeLinter)

sublimeLinter提供代码检测，支持的语言如下：
```
C/C++ - lint via cppcheck
CoffeeScript - lint via coffee -s -l
CSS - lint via built-in csslint
Git Commit Messages - lint via built-in module based on A Note About Git Commit Messages.
Haml - syntax check via haml -c
HTML - lint via tidy (actually tidy for HTML5)
Java - lint via javac -Xlint
JavaScript - lint via built in jshint, jslint, or the closure linter (gjslint) (if installed)
Lua - syntax check via luac
Objective-J - lint via built-in capp_lint
Perl - lint via Perl::Critic or syntax+deprecation check via perl -c
PHP - syntax check via php -l
Puppet - syntax check via puppet parser validate or puppet-lint
Python - native, moderately-complete lint
Ruby - syntax check via ruby -wc
Squirrel - syntax check via sq
XML - lint via xmllint
```


SublimeLinter需要[nodejs](https://nodejs.org/)环境支持。

并且检测不同的代码需要下载对应的插件

| 检测代码 | 插件名称 |
| -- | -- |
| javascript | SublimeLinter-jshint |
| css  | SublimeLinter-csslint |
| html  | SublimeLinter-html-tidy |

`其他语言按照自己的开发需求下载`


###参数配置

打开 SublimeLinter 的配置文件，Preferences->Package Settings->SublimeLinter->Settings - User，进行如下配置：

> 运行模式 sublimelinter

表示检测的时机。默认为true。

```
"sublimelinter": "save-only",
```

SublimeLinter 的运行模式，总共有四种，含义分别如下：

- true - 在用户输入时在后台进行即时校验；
- false - 只有在初始化的时候才进行校验；
- "load-save" - 当文件加载和保存的时候进行校验；
- "save-only" - 当文件被保存的时候进行校验；

>校验引擎 sublimelinter_executable_map

这里是配置 JavaScript 和 CSS 校验需要用到的 JS 引擎（这里用的是 Node.js）的安装路径。

- Mac下配置
```
"sublimelinter_executable_map":
{
  "html": "/usr/local/bin/tidy",
  "javascript": "/usr/local/bin/node",
  "ruby": "rvm-auto-ruby"
},
```
`表示html用tidy进行检测，js用node检测。`

- windows下配置
```
"sublimelinter_executable_map":
{
    "javascript":"D:/nodejs/node.exe",
    "css":"D:/nodejs/node.exe"
}
```

> JSLint 选项

　SublimeLinter 使用 JSHint 作为默认的 JavaScript 校验器，也可以配置为 jslint 和 gjslint（closure linter）。大家可以根据自己的编码风格自行配置，选项的含义可以参考这里[jshint配置](http://www.jshint.com/docs/#options)
```
"jslint_options":
{
    "strict": true,
    "noarg": true,
    "noempty": true,
    "eqeqeq": true,
    "undef": true,
    "curly": true,
    "forin": true,
    "devel": true,
    "jquery": true,
    "browser": true,
    "wsh": true,
    "evil": true
}
```
> CSSLint 选项

　SublimeLinter 使用 CSSLint 作为 CSS 的校验器，，可以根据个人编码风格修改：

```
"csslint_options":
{
    "adjoining-classes": "warning",
    "box-model": true,
    "box-sizing": "warning",
    "compatible-vendor-prefixes": "warning",
    "display-property-grouping": true,
    "duplicate-background-images": "warning",
    "duplicate-properties": true,
    "empty-rules": true,
    "errors": true,
    "fallback-colors": "warning",
    "floats": "warning",
    "font-faces": "warning",
    "font-sizes": "warning",
    "gradients": "warning",
    "ids": "warning",
    "import": "warning",
    "important": "warning",
    "known-properties": true,
    "outline-none": "warning",
    "overqualified-elements": "warning",
    "qualified-headings": "warning",
    "regex-selectors": "warning",
    "rules-count": "warning",
    "shorthand": "warning",
    "star-property-hack": "warning",
    "text-indent": "warning",
    "underscore-property-hack": "warning",
    "unique-headings": "warning",
    "universal-selector": "warning",
    "vendor-prefix": true,
    "zero-units": "warning"
}
```


###我的配置文档

```
{
    "sublimelinter": "save-only",
    "sublimelinter_popup_errors_on_save": true, //会在保存时弹出错误信息
    "sublimelinter_executable_map":
    {
      "html": "/usr/local/bin/tidy",
      "javascript": "/usr/local/bin/node"
    },
    "jsl    int_options": {
        "strict": false,
        "quotmark": "single", //只能使用单引号
        "noarg": true,
        "noempty": true, //不允许使用空语句块{}
        "eqeqeq": true, //!==和===检查
        "undef": true,
        "curly": true, //值为true时，不能省略循环和条件语句后的大括号
        "forin": true, //for in hasOwnPropery检查
        "devel": true,
        "jquery": true,
        "browser": true,
        "wsh": true,
        "evil": true,
        "unused": "vars", //形参和变量未使用检查
        "latedef": true, //先定义变量，后使用
        "globals": {
            "grunt": true,
            "module": true,
            "window": true,
            "jQuery": true,
            "$": true,
            "global": true,
            "document": true,
            "console": true,
            "setTimeout": true,
            "setInterval": true
        }
    },
    "csslint_options": {
        "adjoining-classes": false,
        "box-sizing": false,
        "box-model": false,
        "compatible-vendor-prefixes": false,
        "floats": false,
        "font-sizes": false,
        "gradients": false,
        "important": false,
        "known-properties": false,
        "outline-none": false,
        "qualified-headings": false,
        "regex-selectors": false,
        "shorthand": false,
        "text-indent": false,
        "unique-headings": false,
        "universal-selector": false,
        "unqualified-attributes": false
    }
}
```

效果如下：
![](http://7xix3g.com1.z0.glb.clouddn.com/15-5-13/66092455.jpg)
