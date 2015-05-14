# Evernote
已经习惯了用markdown格式来记录笔记，Evernote无法实现markdown一直是个缺陷。

马克飞象已经解决了这一难题，但[马克飞象](http://maxiang.info/)是收费的服务。本着节省（抠门）原则，我只好另辟蹊径，然后我发现了她---Sublime的Evernote插件


这样就将三种神器结合在一起了：
- Evernote（印象笔记）提供了API，供第三方应用管理笔记。
- 这世界上有markdown这样舒服的标记语言。
- 神器Sublime Text


###安装Evernote插件

使用 Package Control 安装 Evernote插件：
- 在 Package Control 中选择 Install package 或者按 Ctrl+Shift+P，
打开命令板
- 输入 pci 然后选择 Install Package
搜索输入 Evernote 找到 Evernote，
- 点击就可以自动完成安装。

安装完成之后，`第一次使用时需要进行授权认证`。步骤如下：
1. 打开Package Control，输入send to evernote，在窗口底部会弹出一个小窗口，窗口中的内容为一个带token的链接。该token后面用到。
- 将链接复制到浏览器并访问，登录授权后，会有一个NoteStore URL。印象笔记用户，直接用浏览器访问链接：https://app.yinxiang.com/api/DeveloperToken.action
- 打开Sublime Text，打开Preferences > Package Settings > Evernote > Settings User，将步骤2和步骤3中的token和NoteStore URL复制为对应属性值。保存之后便可以开始使用了。


###使用

`cmd + shift + P` 打开 Package Control，输入 evernote，就能看到所有功能选项了，这里介绍几个比较常用的选项功能:

- **Evernote: New empty note**

新建一个笔记。点选后弹出选单可以选择在哪个笔记本下建立笔记。

- **Evernote: Open Evernote note**

打开一个已存在的笔记。点选后弹出菜单可以选择打开任何已存在笔记。

- **Evernote: Update Evernote note**

更新当前编辑的笔记到 Evernote。

- **Evernote: Insert Attachment Here**

添加图片/附件

###快捷键设置

打开preferences ->key Bindings user，添加以下代码，

官方推荐：

```
{ "keys": ["super+e"], "command": "show_overlay", "args": {"overlay": "command_palette", "text": "Evernote: "} },
{ "keys": ["ctrl+e", "ctrl+s"], "command": "send_to_evernote" },
{ "keys": ["ctrl+e", "ctrl+o"], "command": "open_evernote_note" },
{ "keys": ["ctrl+e", "ctrl+u"], "command": "save_evernote_note" },
```

###其他设置：

```

Setting	Purpose
md_syntax	a string pointing to a tmLanguage file which you want to associate with notes opened from Evernote.
inline_css	a dictionary associating some HTML element names to inline CSS styles; this setting is documented in the wiki. The markdown of a note can contain (almost) arbitrary HTML blocks but Evernote only accepts a subset of the elements and attributes (class and id are disallowed). See here for details.
code_highlighting_style	a pygments style among autumn, default, github, monokai, perldoc, vim, borland, emacs, igor, murphy, rrt, vs, bw, friendly, native, tango, xcode, colorful, fruity, manni, pastie, trac.
code_friendly	if true the code-friendly extra of markdown2 is enabled
evernote_autocomplete	when this setting is true, suggestions will be offered for autocompletion of the notebook and tags fields in metadata. Default is true.
emphasis_mark	when converting from HTML to markdown, use this as emphasis markup. Valid values are "*" or "_" (default). It is set to "*" when code_friendly is true.
strong_mark	when converting from HTML to markdown, use this as emphasis markup. Valid values are "__" or "**" (default)
item_mark	when converting from HTML to markdown, use this as unordered list item markup. Valid values are "+", "-" or "*" (default)
notes_order	how to sort the notes in the panels; possible values: created, updated, relevance, update_sequence_number, title. Set the notes_order_ascending setting to true to reverse the selected order.
max_notes	maximum number of notes in a panel; default is 100.
update_on_save	when this setting is true, saving a file containing a note will also update (overwriting it) the online version. Default is false.
sort_notebooks	sorts notebooks alphabetically in pallette
show_stacks	shows the stack of notebooks in pallette
open_single_result	when a search returns only one note open it directly skipping the results pallette (defaults to true)
warn_on_close	when closing a modified note without saving to Evernote, offer a choice to save or discard changes (defaults to true)
gfm_tables	enable GFM table syntax (default true)
wiki_tables	enable Wiki table syntax (default false)
debug	enables logging in the console
```
例如支持表格，需在 Settings – User 中加入配置 "wiki_tables": "true"。格式如下
```
|| *Year* || *Temperature (low)* || *Temperature (high)* ||
|| 1900 || -10 || 25 ||
|| 1910 || -15 || 30 ||
```

更多信息参考官方文档 [Supported-Markdown](https://github.com/bordaigorl/sublime-evernote/wiki/Supported-Markdown)。
