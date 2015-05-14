# Setting-User

配置Sublime的常用配置项，如用户界面、缩进、字体等。在菜单栏选择`Preferences -> Setting-User`，会打开一个配置文件，该文件使用JSON格式进行书写。


配置选项可以参考`Preferences -> Setting-Default`，我们对Setting-User的配置会覆盖默认的Setting-Default配置，下面是我的配置

```
{
	"color_scheme": "Packages/Colorsublime - Themes/Darkside.tmTheme",
	"default_line_ending": "unix",
	"font_face": "Monaco",
	"font_size": 16,
	"highlight_line": true,
	"ignored_packages":
	[
		"Markdown HTML Preview",
		"Markdown",
		"Vintage"
	],
	"revert_font_size": 16,
	"rulers":
	[
		80
	],
	"tab_size": 2,
	"translate_tabs_to_spaces": true,
	"trim_trailing_white_space_on_save": true
}

```

配置参考网站：

- [Sublime非官方文档](http://docs.sublimetext.info/en/latest/index.html)
- [Sublime非官方中文文档](http://feliving.github.io/Sublime-Text-3-Documentation/)
