# SideBarEnhancements

###增加功能

 `新建文件/目录，编辑，打开/运行，显示，在选择中/上级目录/项目中查找，剪切，复制，粘贴，重命名，删除，刷新…`

#####不安装SideBarEnhancements：

![](http://7xix3g.com1.z0.glb.clouddn.com/15-5-13/44118104.jpg)

#####安装SideBarEnhancements：
![](http://7xix3g.com1.z0.glb.clouddn.com/15-5-13/9726547.jpg)


##open with

我们可以在这个功能里配置，用哪种程序打开文件，可以是Photoshop、Firefox、Safari、Chrom、Atom、Mou等。

具体操作：
![](http://7xix3g.com1.z0.glb.clouddn.com/15-5-13/44798693.jpg)

我的配置(Mac)
```
[
	{"id": "side-bar-files-open-with",
		"children":
		[

			//application 1
			{
				"caption": "Photoshop",
				"id": "side-bar-files-open-with-photoshop",

				"command": "side_bar_files_open_with",
				"args": {
									"paths": [],
									"application": "Adobe Photoshop CS5.app", // OSX
									"extensions":"psd|png|jpg|jpeg",  //any file with these extensions
									"args":[]
								},
				"open_automatically" : false // will close the view/tab and launch the application
			},

			//separator
			{"caption":"-"},

			//application 2
			{
				"caption": "Firefox",
				"id": "side-bar-files-open-with-firefox",

				"command": "side_bar_files_open_with",
				"args": {
									"paths": [],
									"application": "Firefox.app", // WINNT
									"extensions":"", //open all even folders
									"args":[]
								},
				"open_automatically" : false // will close the view/tab and launch the application
			},

			//separator
			{"caption":"-"},
			//application 3
			{
				"caption": "Mou",
				"id": "side-bar-files-open-with-Mou",

				"command": "side_bar_files_open_with",
				"args": {
									"paths": [],
									"application": "Mou.app", // OSX
									"extensions":"md",  //any file with these extensions
									"args":[]
								},
				"open_automatically" : false // will close the view/tab and launch the application
			},

			//separator
			{"caption":"-"},
			//application 4
			{
				"caption": "Chrome",
				"id": "side-bar-files-open-with-chrome",

				"command": "side_bar_files_open_with",
				"args": {
									"paths": [],
									"application": "Google Chrome.app",
									"extensions":".*", //any file with extension
									"args":[]
						},
				"open_automatically" : false // will close the view/tab and launch the application
			},

			//separator
			{"caption":"-"},
			//application 4
			{
				"caption": "Safari",
				"id": "side-bar-files-open-with-safari",

				"command": "side_bar_files_open_with",
				"args": {
									"paths": [],
									"application": "Safari.app",
									"extensions":".*", //any file with extension
									"args":[]
						},
				"open_automatically" : false // will close the view/tab and launch the application
			},

			{"caption":"-"}




		]
	}
]
```
配置项详解：
- caption  应用名称
- id  唯一标识
- command 对应的命令名称
- args
 - paths
 - application 应用程序地址
 - extensions   后缀类型多个可以是这样`markdown|md|mdown|mkd|mkdn|txt`
 - args
- open_automatically  是否默认打开

###Copy as
另外，很牛的 Copy as Text...：包含各种形式的路径、URI（甚至包括 base64 的 data:uri）、转码后的文件名、各种 HTML Tag（a、img、script、style）……


###快捷键设置
打开preferences ->key Bindings user，`增加`如下代码:

```
{ "keys": ["super+ctrl+s"], "command": "side_bar_files_open_with",
        "args": {
            "paths": [],
            "application": "Safari.app",
            "extensions":".*"
        }
    }

```
这样就将`open with safari`的快捷键设置为`super+ctrl+s`,其他应用程序的设置方法也一样
