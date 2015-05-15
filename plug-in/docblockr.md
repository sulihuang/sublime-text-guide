# DocBlockr

[DocBlockr](https://github.com/spadgos/sublime-jsdocs/)是 sublime的插件包，目前支持 Sublime Text 2 & 3。 DocBlockr 支持 Javascript, PHP, ActionScript, CoffeeScript, Java, Groovy, Objective C, C and C++.的注释的快速生成。

## 安装 ##
使用 Package Control 安装 DocBlockr插件：
- 在 Package Control 中选择 Install package 或者按 Ctrl+Shift+P，
打开命令板
- 输入 pci 然后选择 Install Package
搜索输入 DocBlockr 找到 DocBlockr，
- 点击就可以自动完成安装。

## 使用 ##

在新的一行中输入 `/**` 后按下 `enter` 或者 `tab`


![](https://camo.githubusercontent.com/4fda835261d5bafc0757557e91ba03b4fcf4ad72/687474703a2f2f73706164676f732e6769746875622e696f2f7375626c696d652d6a73646f63732f696d616765732f62617369632e676966)

一个星号的注释使用方法

![](https://camo.githubusercontent.com/ac8a315f5c5165ec853f680c9daf641ba97ad8e3/687474703a2f2f73706164676f732e6769746875622e696f2f7375626c696d652d6a73646f63732f696d616765732f62617369632d626c6f636b2e676966)


为一个函数添加注释,函数的名称和参数，在函数前输入 `/**` 后回车，他会自动解析并自动添加注释。

![](https://camo.githubusercontent.com/415148aecc6dac2e5ebb12b7f7584f4a8744eca4/687474703a2f2f73706164676f732e6769746875622e696f2f7375626c696d652d6a73646f63732f696d616765732f66756e6374696f6e2d74656d706c6174652e676966)

在生成注释后， 按 `tab` 快速切换需要修改的地方

![](https://camo.githubusercontent.com/087348d3e797f4ccc91528459b0473f6d34eadf3/687474703a2f2f73706164676f732e6769746875622e696f2f7375626c696d652d6a73646f63732f696d616765732f6c6f6e672d617267732e676966)

他还提供了对其他语言的支持

![](https://camo.githubusercontent.com/775195d644566d584eb246ee952722cdbb8c63ca/687474703a2f2f73706164676f732e6769746875622e696f2f7375626c696d652d6a73646f63732f696d616765732f747970652d68696e74696e672e676966)

DocBlockr 会尝试的去猜测 function 的返回值
- 如果方法名中以 "set" 或 "add" 开头，它将不会为注释插入 `@return`. 如： `function setName() {...}`
- 如果方法名中以 "is" 或 "has" 开头，它将为注释 `@return` 设置为 `Boolean`. 如： `@return {Boolean}`
- 在Javascript中,如果函数以一个大写字母开始,并假定函数定义为一个类，此时不添加@return标记。


## 变量的文档 ##

如果在新的一行声明一个变量，在 `/**` 后 按下 `shift+enter` , DocBlocker 将试着猜测变量的数据类型，并插入响应类型注释。

![](https://camo.githubusercontent.com/a116c3956ed011a2a36c9be865518cef60232cb2/687474703a2f2f73706164676f732e6769746875622e696f2f7375626c696d652d6a73646f63732f696d616765732f766172732e676966)


DocBlocker 除了视图判断以 is 或 has 这些开头命名的参数为 booleans 类型为，还将 callback, cb, done, fn, 和 next 判断成 Function 类型。例子如下：


	/**
	 * [isMe description]
	 *
	 * @method isMe
	 *
	 * @param  {Boolean}  isA      [description]
	 * @param  {[type]}   isb      [description]
	 * @param  {Function} callback [description]
	 * @param  {Function} cb       [description]
	 * @param  {Function} done     [description]
	 * @param  {Function} fn       [description]
	 * @param  {Function} next     [description]
	 *
	 * @return {Boolean}           [description]
	 */
	function isMe(isA, isb, callback, cb, done, fn, next){
		return a;
	}

用户还可以通过自定义规则完成预判断。比如下面的的例子中设定了 `b` 开头的参数是 `bool` 类型。这些设定可以通过修改 `Base File.sublime-settings` 文件中的 `jsdocs_notation_map`属性

	{
	    "jsdocs_notation_map": [
	        {
	            "prefix": "b", // a prefix, matches only if followed by an underscore or A-Z
	            "type": "bool" // translates to "Boolean" in javascript, "bool" in PHP
	        },
	        {
	            "regex": "tbl_?[Rr]ow", // any arbitrary regex to test against the variable name
	            "type": "TableRow"      // you can add your own types
	        }
	    ]
	}

下面我们来添加一个私有方法猜测的配置，这个配置意思是以 `_` 开头命名的方法都被预判为私有方法，在生成注释时会在注释文档中添加 `@private`

	{
	    "jsdocs_notation_map": [
			{
			    "prefix": "_",
			    "tags": ["@private"]
			}
	    ]
	}

## 注释其他说明 ##

在docblock文档流内按下回车，文档会自动加` *`

![](https://camo.githubusercontent.com/4ee04d66c33aceca2dc886340c0619f50d4880dd/687474703a2f2f73706164676f732e6769746875622e696f2f7375626c696d652d6a73646f63732f696d616765732f6175746f2d696e64656e742e676966)
![](https://camo.githubusercontent.com/d7739bc68472fecea438e0c6d4083f1ee3334de0/687474703a2f2f73706164676f732e6769746875622e696f2f7375626c696d652d6a73646f63732f696d616765732f6175746f2d696e64656e742d322e676966)

使用 `//` 后换行， docbolck 会在新的一行自动加上 `//`

![](https://camo.githubusercontent.com/3fcee8bc7ec13b2b91f430c2442721fea3cc9cf2/687474703a2f2f73706164676f732e6769746875622e696f2f7375626c696d652d6a73646f63732f696d616765732f73696e676c652d6c696e652e676966)

如果你想终止智能提速，你可以通过按下 `shift+enter` 去停止自动预测。

有时候我们的参数说明可能很长，我们可以在换行后按下 `tab` 实现快速缩进。

![](https://camo.githubusercontent.com/82c02a49f4a9153ffac37f02126178301696593a/687474703a2f2f73706164676f732e6769746875622e696f2f7375626c696d652d6a73646f63732f696d616765732f646565702d696e64656e742e676966)


## 修饰类注释 ##

有时候你会修以下类型的修饰类注释

	/////////////////
	// Foo bar baz //
	/////////////////

你可以通过输入 `// Foo bar baz` 后按下<<`Ctrl+Enter`>> 来快速实现。


## 添加额外的标签 ##

可以在docblock中输入 `@` 获得[JSDoc](http://code.google.com/p/jsdoc-toolkit/wiki/TagReference), [Google Closure Compiler](http://code.google.com/p/jsdoc-toolkit/wiki/TagReference), [YUIDoc](http://code.google.com/p/jsdoc-toolkit/wiki/TagReference) ， [PHPDoc](http://phpdoc.org/).的全部支持的列表。

## 配置 ##
你可以通过 ` Preferences -> Package Settings -> DocBlockr -> settings default` 进入 `Base File.sublime-settings` 文件中修改相应配置。

具体的进入文件就可以看到举例

