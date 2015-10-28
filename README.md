# Sublime-Setting-User
Sublime Text 3 设置文件保存专用

Sublime Text 3 的 \Packages\User 文件夹下都是用户设置文件，上传到Github方便在不同的电脑上使用。此仓库仅作保存之用。

下面是自己的Sublime Text 3 配置：


# Sublime Text 3 配置和使用方法

标签（空格分隔）： IDE与编辑器

---
下载：

- [Sublime Text 3 官方下载地址](http://www.sublimetext.com/3)
- [Sublime Text 3 汉化破解版](http://pan.baidu.com/s/1sj02k2L)

资料：

- [Sublime Text 非官方文档](http://sublime-text.readthedocs.org/en/latest/index.html)

目录：

[TOC]

---
## 技巧
`-用户`或`-User`后缀的菜单项，其对应的配置文件都保存在`Packages\User`文件夹下，将它们上传到Github，便于同步。


----
## 个人最常用的快捷键
快捷键完整版见后文，这里只列个人习惯。

四种 Goto ：
Ctrl + P  文件定位
Ctrl + ;  词语定位 #
Ctrl + R  函数定位 @
Ctrl + G  行号定位 :

括号前后移动光标：Ctrl + M
以单词为单位前后移动光标：Ctrl + Left/Right
Ctrl+→ 向右单位性地移动光标，快速移动光标。
重新打开刚刚关闭的标签页：Ctrl + Shift + T
当前行与上/下一行交换位置：Shift + Ctrl + Up/Down
向光标前插入一行：Shift + Ctrl + Enter
向光标后插入一行：Ctrl + Enter
复制光标所在整行，插入到下一行：Ctrl + Shift + D
合并选中的多行代码为一行：Ctrl + J
快速折叠文件内所有函数：Ctrl + K + 1 （数字表示级别）




---
## 插件

先装插件管理器(Package Control)：https://packagecontrol.io/installation

**安装插件**：Ctrl+Shift+P，输入install，等待几秒后出现插件列表，输插件名再回车就能自动安装。下文插件名加链接的可以点进去学习使用方法。建议安装插件后都进设置菜单配置一下。
**删除插件**：Ctrl+Shift+P，输入remove package，选择插件再回车。



- **ConvertToUTF8**：GBK编码兼容。
- **FileHeader**：文件模板，可自动更新修改时间。
Ctrl+Shift+A 插入文件头。`Packages\FileHeader\template`中的 body 对应文件模板，header 对应文件头
- **JsFormat**：javascript格式化，包括Json。切换Syntax后按 Ctrl+Alt+F 格式化。
- [**wakatime**](https://wakatime.com/)：自动记录code时间，支持多种编辑器和IDE。
先到官网注册，登录后在右上角点用户名，选择`Setting`，左侧选`Account`，复制Api Key。Sublime中安装此插件会用到。以后就可以登录网站查看自己的code时间统计图。
- [**ColorSublime**](http://colorsublime.com/)：用来安装其官网上的所有主题。
安装此插件后，Ctrl+Shift+P，输入install theme并回车，等待片刻即缓存其官网所有主题到本地，按上下键可以即时预览效果，回车键安装。
- [**Git**](https://github.com/gornostal/Modific)：如其名，还没学会使用
- [**Modific**](https://github.com/gornostal/Modific)：高亮相对于上次Git或SVN提交有所变动的行。
- [**DocBlockr**](https://github.com/spadgos/sublime-jsdocs)：生成Java风格的函数注释，用法与效果都和Eclipse相同。
- [**PlainTasks**](https://github.com/aziz/PlainTasks)：待办事件表
- [**ColorPicker**](https://packagecontrol.io/packages/ColorPicker)：需要输入颜色时，可直接打开调色板选颜色。快捷键Ctrl+Shift+C，与ConvertToUTF8冲突，在`Packages\ConvertToUTF8`下找到对应操作系统的`Default.sublime-keymap`文件，把快捷键改掉
- [**TabsExtra**](https://github.com/facelessuser/TabsExtra)：安装后右键单击Sublime里的文件标签，选clone就能在新标签中打开同一文件。配合Alt+Shift+2可以方便地分屏浏览。


-----
## 代码段 Snippet
单击菜单中的`工具`，`新代码段...`，删掉默认内容，粘贴下方代码并保存到`Packages\User\Java Snippets`文件夹，文件名为`Print.sublime-snippet`。写Java代码时只须输入`syso`再按回车就能快速插入`System.out.println()` 了。

后缀必须是`.sublime-snippet`，文件名可以自由命名，目录结构也可以随意更改，只要在`Packages\User\`下就行。每个文件中只能写包含一个`<snippet>`结点
```xml
<snippet>
	<!-- 快速补全的内容 -->
	<!-- 1表示第一个输入点，1后加冒号和字符表示默认值 -->
    <!-- 如System.out.println(${1:"Hello World"})，可输入多行代码 -->
    <content><![CDATA[System.out.println(${1});]]></content>

    <!-- 触发字符 -->
    <!-- Eclipse中可以用syso快速插入Java的输出语句 -->
    <tabTrigger>syso</tabTrigger>

    <!-- 指定的语法才会触发，可选 -->
    <!-- 此处的语法指的是Ctrl+Shift+P，Set Syntax中设置的语法 -->
    <!-- 必须把完整的语言名写在后缀中 -->
    <scope>source.java</scope>

    <!-- 触发时的提示 -->
    <description>System.out.println()</description>
</snippet>
```

Sublime Text 3 为每种语法（Syntax）都设置了Snippet。

查看方法：把Sublime Text 3 根目录下`Packages`文件夹中任意文件复制出来，改后缀为`.rar`，解压缩。后缀为`.sublime-snippet`的就是了。可以用Sublime打开。


----
## 设置
`首选项`，`设置-用户`
```javascript
{
	// 开启选中范围内搜索
	"auto_find_in_selection": true,

	// 侧边栏文件夹显示加粗，区别于文件
	"bold_folder_labels": true,

	"color_scheme": "Packages/Color Scheme - Default/Solarized (Dark).tmTheme",

	// 使用 unix 风格的换行符
	"default_line_ending": "unix",

	// true则禁用Emmet的tab键功能
	// "disable_tab_abbreviations": true,

	// 右侧代码预览时给所在区域加上边框
	"draw_minimap_border": true,

	// 保证在文件保存时，在结尾插入一个换行符。
	// 这样 git 提交时不会生产额外的 diff
	"ensure_newline_at_eof_on_save": true,

	// 默认显示行号右侧的代码段闭合展开三角号
	"fade_fold_buttons": false,

	"font_face": "Microsoft YaHei Mono",
	"font_size": 13,

	// 当前行高亮
	"highlight_line": true,

	// 高亮未保存文件
	"highlight_modified_tabs": true,

	"ignored_packages":
	[
		"Vintage"
	],

	// 窗口失焦立即保存文件
	"save_on_focus_lost": true,

	// 自动移除行尾多余空格
	"trim_trailing_white_space_on_save": true,
	"trim_automatic_white_space": true,

	// 关闭自动更新
	"update_check": false,

	// 自动换行
	"word_wrap": "true"，

	// Tab转空格
	"translate_tabs_to_spaces": true
}

```




----
## 快捷键
`首选项`，`按键绑定-用户`：
```javascript
[
// 代码提示
{ "keys": ["alt+space"], "command": "auto_complete" },
{ "keys": ["alt+space"], "command": "replace_completion_with_auto_complete", "context":
  [
    { "key": "last_command", "operator": "equal", "operand": "insert_best_completion" },
    { "key": "auto_complete_visible", "operator": "equal", "operand": false },
    { "key": "setting.tab_completion", "operator": "equal", "operand": true }
  ]
},

// 跳转到函数定义
{ "keys": ["ctrl+alt+d"], "command": "goto_definition" },
]
```

---------------------
## 编译系统

---
### 编译运行Java
Sublime Text 3默认将文件存为UTF-8编码，如果要手动输命令编译Sublime Text 3 写的Java源文件，必须加`-encoding UTF-8`参数


#### 方法一：

打开Sublime Text 3，依次点击`工具`、`编译系统`、`新编译系统`，粘贴下面的代码并保存为`My-----Java.sublime-build`。文件名加这么多斜杠是为了能在菜单中一眼找出来。

然后按Ctrl+Shift+P，输入`My---`，选择`Build With:My-----Java`并回车，即可将刚才的文件设置为当前编译系统。Ctrl+B编译，Ctrl+Shift+B运行。
```javascript
{
    // 命令和参数，未指定路径则在PATH环境变量中找
    "cmd": ["javac","-encoding","UTF-8","-d",".","$file"],

    // 可选。获取cmd的错误输出
    "file_regex": "^(...*?):([0-9]*):?([0-9]*)",

    // 可选。`工具`菜单中`编译`为`自动`时生效
    "selector": "source.java",

    // 可选。输出"cmd"的编码。必须是合法的Python编码，缺省为"UTF-8"
    "encoding":"GBK",

    // variants 可选。用来替代主构建系统的备选。如果构建系统的"selector"与激活的文件匹配，变量"name"则会出现在 Command Palette 中。
    "variants":
        [
            {

                 // 仅在"variants"中是合法的 (详见 variants)。用来标识系统中不同的构建系统。如果"name"是"Run" ,则会显示在Tools | Build System 菜单下，并且可以使用Ctrl + Shift + B调用
                "name": "Run",

                // 可选。如果该选项为"true" ，"cmd"则可以通过shell运行。
                "shell": true,

                "cmd" :  ["start","cmd","/c", "java ${file_base_name} &echo. & pause"],
                // /c是执行完命令后关闭cmd窗口,
                // /k是执行完命令后不关闭cmd窗口。
                // echo. 相当于输入一个回车
                // pause命令使cmd窗口按任意键后才关闭

                // 可选。在运行首行的"cmd"前会切换到该目录。运行结束后会切换到原来的目录。
                "working_dir": "${file_path}",

                "encoding":"GBK"
            }
        ]

    // 还有：
    // line_regex 可选。当"cmd"的错误输出中，file_regex与该行不匹配，如果line_regex存在，并且确实与当前行匹配， 则遍历整个缓冲区，直到与file regex匹配的行出现，并用这两个匹配决定最终要跳转的文件或行。

    // target 可选。运行的Sublime Text命令，缺省为"exec" (Packages/Default/exec.py)。该命令从 .build-system中获取配置数据。用来替代缺省的构建系统命令。注意，如果你希望替代构建系统的缺省命令，请在.sublime-build 文件中专门设置。

    // env 可选。在环境变量被传递给"cmd"前，将他们封装成词典。

    // path 可选。该选项可以在调用"cmd"前替换当前进程的PATH 。原来的 PATH 将在运行后恢复。使用这个选项可以在不修改系统设置的前提下将目录添加到 PATH 中。
}
```





#### 方法二：
在JDK的bin目录下新建`runJava.bat`文件：

```
@echo off
cd %~dp1
echo Compiling %~nx1......
if exist %~n1.class (
    del %~n1.class
)
javac -encoding UTF-8 %~nx1
if exist %~n1.class (
    echo ------Output------
    java %~n1
)
```

用上面的方法新建并设置为当前编译系统，按Ctrl+B即可编译+运行，这种方法的缺点是无法在控制台输入，如果程序需要输入内容，则直接报错
```
{
 "shell_cmd": "runJava.bat \"$file\"",
 "file_regex": "^(...*?):([0-9]*):?([0-9]*)",
 "selector": "source.java",
 "encoding": "GBK"
}
```

---
### 运行 Python
用法同上，仅粘贴代码：
```javascript
{
	"shell_cmd": "python -u \"$file\"",
	"file_regex": "^[ ]*File \"(...*?)\", line ([0-9]*)",
	"selector": "source.python",

	// 默认是utf-8，控制台无法输出中文。
	// Window Code Page 936，指的是GBK编码
	"encoding":"cp936"
}
```

------------
##快捷键汇总
###选择类
>- Ctrl+D 选中光标所占的文本，继续操作则会选中下一个相同的文本。
- Alt+F3 选中文本按下快捷键，即可一次性选择全部的相同文本进行同时编辑。举个栗子：快速选中并更改所有相同的变量名、函数名等。
- Ctrl+L 选中整行，继续操作则继续选择下一行，效果和 Shift+↓ 效果一样。
- Ctrl+Shift+L 先选中多行，再按下快捷键，会在每行行尾插入光标，即可同时编辑这些行。
- Ctrl+Shift+M 选择括号内的内容（继续选择父括号）。举个栗子：快速选中删除函数中的代码，重写函数体代码或重写括号内里的内容。
- Ctrl+M 光标移动至括号内结束或开始的位置。
- Ctrl+Enter 在下一行插入新行。举个栗子：即使光标不在行尾，也能快速向下插入一行。
- Ctrl+Shift+Enter 在上一行插入新行。举个栗子：即使光标不在行首，也能快速向上插入一行。
- Ctrl+Shift+[ 选中代码，按下快捷键，折叠代码。
- Ctrl+Shift+] 选中代码，按下快捷键，展开代码。
- Ctrl+K+0 展开所有折叠代码。
- Ctrl+← 向左单位性地移动光标，快速移动光标。
- Ctrl+→ 向右单位性地移动光标，快速移动光标。
- shift+↑ 向上选中多行。
- shift+↓ 向下选中多行。
- Shift+← 向左选中文本。
- Shift+→ 向右选中文本。
- Ctrl+Shift+← 向左单位性地选中文本。
- Ctrl+Shift+→ 向右单位性地选中文本。
- Ctrl+Shift+↑ 将光标所在行和上一行代码互换（将光标所在行插入到上一行之前）。
- Ctrl+Shift+↓ 将光标所在行和下一行代码互换（将光标所在行插入到下一行之后）。
- Ctrl+Alt+↑ 向上添加多行光标，可同时编辑多行。
- Ctrl+Alt+↓ 向下添加多行光标，可同时编辑多行。


### 编辑类
>- Ctrl+J 合并选中的多行代码为一行。举个栗子：将多行格式的CSS属性合并为一行。
- Ctrl+Shift+D 复制光标所在整行，插入到下一行。
- Tab 向右缩进。只对光标后（或者选中的）的代码有效
- Shift+Tab 向左缩进。
- Ctrl+[ 向左缩进。对整行有效
- Ctrl+] 向右缩进。对整行有效
- Ctrl+K+K 从光标处开始删除代码至行尾。按住Ctrl，按两次K。
- Ctrl+Shift+K 删除整行。
- Ctrl+/ 注释单行。
- Ctrl+Shift+/ 注释多行。
- Ctrl+K+U 转换大写。
- Ctrl+K+L 转换小写。
- Ctrl+Z 撤销。
- Ctrl+Y 恢复撤销。
- Ctrl+U 软撤销，感觉和 Gtrl+Z 一样。
- Ctrl+F2 设置书签，F2切换书签
- Ctrl+T 左右字母互换。
- F6 单词检测拼写

###搜索类
>- Ctrl+F 打开底部搜索框，查找关键字。
- Ctrl+shift+F 在文件夹内查找，与普通编辑器不同的地方是sublime允许添加多个文件夹进行查找，略高端，未研究。
- Ctrl+P 打开搜索框。举个栗子：1、输入当前项目中的文件名，快速搜索文件，2、输入@和关键字，查找文件中函数名，3、输入：和数字，跳转到文件中该行代码，4、输入#和关键字，查找变量名。
- Ctrl+G 打开搜索框，自动带：，输入数字跳转到该行代码。举个栗子：在页面代码比较长的文件中快速定位。
- Ctrl+R 打开搜索框，自动带@，输入关键字，查找文件中的函数名。举个栗子：在函数较多的页面快速查找某个函数。
- Ctrl+： 打开搜索框，自动带#，输入关键字，查找文件中的变量名、属性名等。
- Esc 退出光标多行选择，退出搜索框，命令框等。
- Ctrl+Shift+P 打开命令框。场景栗子：打开命名框，输入关键字，调用sublime text或插件的功能，例如使用package安装插件。

###显示类
>- Ctrl+Tab 按文件浏览过的顺序，切换当前窗口的标签页。
- Ctrl+PageDown 向左切换当前窗口的标签页。
- Ctrl+PageUp 向右切换当前窗口的标签页。
- Alt+Shift+1 窗口分屏，恢复默认1屏（非小键盘的数字）
- Alt+Shift+2 左右分屏-2列
- Alt+Shift+3 左右分屏-3列
- Alt+Shift+4 左右分屏-4列
- Alt+Shift+5 等分4屏
- Alt+Shift+8 垂直分屏-2屏
- Alt+Shift+9 垂直分屏-3屏
- Ctrl+K+B 开启/关闭侧边栏。
- F11 全屏模式
- Shift+F11 免打扰模式

-------------
### 多重选择（Multi-Selection）
多重选择功能允许在页面中同时存在多个光标，让很多本来需要正则表达式、高级搜索和替换才能完成的任务也变得游刃有余了。

激活多重选择的方法有两几种：
>- 按住 Ctrl 然后在页面中希望中现光标的位置点击。
- 选择数行文本，然后按下 Shift + Ctrl + L。
- 通过反复按下 Ctrl + D 即可将全文中与光标当前所在位置的词相同的词逐一加入选择，而直接按下 Alt+F3即可一次性选择所有相同的词。
- 按下鼠标中键来进行垂直方向的纵列选择，也可以进入多重编辑状态。






