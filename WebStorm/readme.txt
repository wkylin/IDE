 XP:C:\Documents and Settings\Administrator\.WebIde10\config\colors

win7: C:\Users\Administrator\.WebIde10\config\colors

目录下，然后重启webstorm，settings --> colors & fonts -->scheme name中选择grey_orange

字体(font)：yihei Consolas size: 16 line spaceing:1.2



如果出现特别长代码对齐白线，在Editor --> Appearance --> Show vertical indent guides 前面的勾去掉即可。

去掉行线：在Editor --> Appearance --> Show right margin 前面的勾去掉即可。


jQuery 库支持：
	Javascript > Libraries >Add >Documentation URLs


Webstorm 4.0 debug调试 需要安装
	JetBrains Friefox extension 0.5.3
	http://code.google.com/p/css-x-fire/wiki/Installation


Chrome安装jb.crx

css压缩工具安装：Yabo
-----------------------------------------------------------------------------------
 设置>>External Tools
 Program:wscript
 Parameters:I:\jscript\Yabo.js $FilePath$
 Working directory:$FileDir$



 配置Less
--------------------------------------------------------------------------------------------------------------
 webstorm自带less，不过要编译的话需要nodejs环境，由于个人原因，搭建过程比较苦逼，不过其实很简单，走了很多弯路。
下载node.js
    1.首先去node的主页下载对应版本的nodejs然后安装（为了保险起见我还是用x86的），下载地址：http://nodejs.org/
    2.安装完之后打开命令提示符（win+r）,分别输入node -v以及npm -v如果返回版本号说明你安装成功了。
    3.接下来就可以安装less了，命令提示符npm进入npm管理器，然后npm install less开始下载less，默认安装目录在你的用户名\node_modules这里面，你不会错过他的。
    4.到这里less安装完毕了，接下来配置webstorm。 配置node.js
    5.打开webstorm的file-settings-External Tools，点击左上角的“加号”标志add，进入对话框。
    6.最重要的一步：
    parameters，他指定lessc编译器的地址以及输出文件的地址，格式是："lessc的地址" $FilePath "编译的地址（变量表示）"。
    Program:C:\Program Files\nodejs\node.exe
    Parameters:C:\Users\Administrator\node_modules\less\bin\lessc $FilePath$ $FileDir$\$FileNameWithoutExtension$.css
    Working directory:C:\Program Files\nodejs
    7.Keymap >> Exteranl tool  指定快捷键：Ctrl+Shift+L
    8.之后打开一个.less后缀名的文件，快捷键编译，如果webstorm底部状态控制器显示 Process finished with exit code 0 ，那么恭喜你，你大功告成了，接下来 let the coding begin~

Node及less安装目录：
------------------------------------------------------------------------------
C:\Program Files\nodejs
C:\Users\Administrator\node_modules\less\bin\lessc

Live Template
------------------------------------------------------------------------------
快捷键：Ctrl+Shift+A >>Live
特别留意底部的有个live template出现的文件类型设置(Applicable in ***)，是必须选择的.
插入：Ctrl+Alt+Shift+J
Ctrl+Tab

Alt+A nextTab
Alt+D delTab

File Templates
----------------------------------------------------------------
使用“ctrl+shift+a”，搜索File Templates：

额外给模版注入变量
变量名可以自定义，以${变量名}$这样的格式出现。
例：
/**
 *@fileReadme:${fileReadme}
 *@author:wkylin [wkylin@github.com]
 */



配置CSScomb 让你的css属性更有序
-------------------------------------------------------------------------------
webstorm 6.0插件安装

jsonView
---------------------------------------------------------------------------------
1.firefox chrome等浏览器的插件
2.JsonViewerPackage.zip中使用exe文件在本地查看

Emmet(zencoding)
---------------------------------------------------------------------------------
http://docs.emmet.io/cheat-sheet/
http://docs.emmet.io/

快捷键：Ctrl+Alt+J >>>>select template




Webstorm的插件：
----------------------------------------------------------------------------------------------------
通过IDE直接安装插件，进入“settings”，搜索“plugins”，进入插件页面;
1.IdeaVim
下载量最高的插件，让idea支持vim的快捷键！
2.TabSwitch
快速切换代码文件选项卡
3.markdown
支持markdown语法
4.JsTestDriver
webstorm内置，推荐idea安装，用于回归js单元测试，后面会介绍用法。
5.CSS-X-Fire
前面有介绍过了，firebug的一个插件，当你修改css属性时修改编辑器内的代码。
6.Key Promoter
快捷键提示插件，帮助你快速记住快捷键。当你用鼠标完成某功能时，它会指示有相应的快捷键来完成刚才的功能，同时指导你为经常重复的操作建立快捷键。
7.AltN8
非常强大的插件，用于快速打开的文件（自行编写正则）


打包工具换成grunt
--------------------------------------------------------------------------------------
http://gruntjs.com/
http://www.oschina.net/question/89964_47198
http://www.zhangxinxu.com/wordpress/2013/01/uglifyjs-compress-js/

uglifyjs 安装：
-----------------------------------------------------------------------------
1.安装node
2. 安装npm
3. 安装uglifynpm install uglify-js -g
C:\Users\Administrator\AppData\Roaming\npm\uglifyjs -> C:\Users\Administrator\AppData\Roaming\npm\node_modules\uglify-js\bin\uglifyjs
uglify-js@2.2.5 C:\Users\Administrator\AppData\Roaming\npm\node_modules\uglify-js
├── source-map@0.1.9 (amdefine@0.0.4)
└── optimist@0.3.5 (wordwrap@0.0.2)

压缩步骤：
1.cmd 进入所在文件夹
2.uglifyjs ****.js -o ****-min.js
3.uglifyjs ****.js -m -o *****.min.js
其中-m 压缩变量名

如何给不支持的格式文件制定文件解析方式？
--------------------------------------------------------------------------------------
比如webstorm不支持.vm模版的高亮，我们可以把.vm文件解析成.html文件。
做法如下：
使用“ctrl+shift+a”，搜索“file types”，就可以找到文件模版的配置，在html类型中加上*.vm即可。

配置Github
------------------------------------------------------------------------------------------
wkylin Win72010


NPM模块管理
--------------------------------------------------------------------------------------
npm是 Node.js 的包管理工具，用来安装各种 Node.js 的扩展。
https://npmjs.org/

配置git
------------------------------------------------------------------------------------
1. 安装git.exe
2. 配置git：
Version Control>>git>>Path to Git executable
安装目录：C:\Program Files\Git\bin\git.exe
3.  Checkout from Version Control >>git
    Git Repository URL:https://github.com/wkylin/IDE.git
    Parent Directory:D:\github
    Directory Name: IDE

4.操作 add commit push
5.定义快捷键：
 update:Alt+U
 commit:Alt+C
 pull:Alt+L
 push:Alt+P
