# Android studio常用设置和快捷键

# 一、常用设置

### （一）安装路径设置

    1.Android Studio软件默认安装路径 C:\Program Files\Android\Android Studio
     【tips：】安装Android Studio的时候，会提示设置Android Studio安装路径，最好是自己选择一个非C盘的目录
      ★ 我电脑上的Android Studio软件安装路径  E:\develop\Android Studio2.3.3

    2.SDK默认安装路径 C:\Users\Administrator\AppData\Local\Android\sdk
     【tips：】安装Android Studio的时候，会提示设置sdk安装路径，最好是自己选择一个非C盘的目录（下文有设置sdk路径讲解）
      ★ 我电脑上的SDK安装的实际路径  E:\develop\sdk


    3.默认工程目录 C:\Users\Administrator\AndroidstudioProjects
     【tips：】首次打开Android Studio的时候，会提示设置项目路径，如果不设置，就用的默认的路径，
      ★ 我电脑上的工程目录的实际路径  E:\AndroidStudioWorkspace

    4.Gradle默认安装路径 C:\Users\Administrator\.gradle\wrapper\dists\gradle-3.3-all\3jdgemv0iv8uqohg3kcp2o88r1目录
      下（\gradle-3.3-all\3jdgemv0iv8uqohg3kcp2o88r1这个根据各人电脑安装的gradle版本不同有所不同，我这里显示的我电脑安装的版本）

      ★ 另外Android Studio安装目录里面自带有一个gradle安装包，比如我的Android Studio自带的gradle路径是
       E:\develop\Android Studio2.3.3\gradle\gradle-3.3 

    5.Android Studio插件默认安装路径 C:\Users\n-260\.AndroidStudio2.3\config\plugins
     【tips：】不建议更改这个插件安装的路径，会出一些问题，在Android Studio遇到的那些坑.md里面有相关讲解，这里就不细说了。

### （二）关于版本的问题：(以我的电脑配置为例，具体参考你的电脑设置)

##### 1. 查看studio版本:

    点菜单栏的 help --> About  (请查看 studio安装路径 )
	 ▼ 显示的内容如下：
	 Android Studio 2.3.3
	 Build #AI-162.4069837, built on June 6, 2017
	 JRE: 1.8.0_112-release-b06 amd64
	 JVM: OpenJDK 64-Bit Server VM by JetBrains s.r.o

     通过看第一行得知，Android Studio版本是 2.3.3
  
##### 2. 查看gradle版本（请查看 studio安装路径\gradle\gradle-XXX）

    1.比如我的Android Studio自带的gradle路径是 E:\develop\Android Studio2.3.3\gradle\gradle-3.3 ,就可以看到gradle版本是 3.3

    2.查看当前设置的Gradle的版本及Gradle插件的版本
      ====> 点击菜单 File --> Project Structure --> 选择 Project,在对话框的右侧可以看到Gradle的版本及Gradle插件的版本


##### 3. 查看本地的sdk编译版本：
 
      在项目的modle或者lib里面的的build.gralde里面有个 buildToolsVersion ，这就是sdk的编译版本,查找路径如下：

      ★ 我电脑安装的SDK路径是  E:\develop\sdk，查看sdk编译版本路径在 E:\develop\sdk\build-tools

### （三）常用设置( 快捷键Ctrl + Alt + S 打开Settings )

##### 1.studio设置自动导包:

    File --> Settings --> Editor --> General --> Auto Import --> 勾选上 optimize imports on the fly 和 
    add unambiguous imports on the fly 的选项即可

##### 2.显示行号

    File --> Settings --> Editor --> General --> Appearance --> 勾上 Show line numbers

##### 3.不区分大小写

    File --> Settings --> Editor --> General --> Code Completion --> 在 Case sensitive completion 后面的选项改
    成NONE:进行模糊匹配。(First Letter：根据首字母进行匹配)

##### 4.字体大小设置

    File --> Settings --> Editor --> Colors & Fonts --> Font 。默认系统显示的Scheme为Defualt是不能编辑的,只要
    点击右侧的Save As... ，保存一份自己的设置，并在当中设置。之后，在 Editor Font 中即可设置字体

##### 5.设置光标悬停时提示文档注释

    File --> Settings --> Editor --> General --> 勾选 Show quick doc on mouse Delay…

##### 6.驼峰选择  通常我们通过 Ctrl + Left / Right 键改变字符选择区域的时候 Android Studio 默认不支持‘驼峰’单词的选择。

    File  --> Settings --> Editor --> General --> Smart Keys --> 选中 Use “CamelHumps” words

    【tips：】如果你仍然希望当鼠标在单词上双击之后选中整个单词，需要作如下设置：
    File  --> Settings --> Editor --> General --> 取消选中 ‘Honor Camel Humps words settings when selecting on double click’

##### 7.命名前缀

    File --> Settings --> 选择 Editor --> Code Style --> Java --> 选择 Code Generation 标签 --> 给普通 Field 
    添加一个’m’前缀，给 Static filed 添加一个’s’前缀

##### 8.设置log颜色

    File --> Settings --> 选择 Editor --> Color & Fonts --> Android Logcat -->点击 Click on Save As…创建一个
    新的配色 Scheme，按照下面的表格修改对应的颜色(修改之前需要取消勾选 Use inherited attributes)

Log级别|颜色
-|-
Assert|#AA66CC
Debug|#33B5E5
Error|#FF4444
Info:|#99CC00
Verbose|#FFFFFF
Warning|#FFBB33

##### 9.代码配色（因人而异）

　　比如有的朋友会觉得 Java 代码中局部变量的默认的白色不太便于快速与其它代码进行区分，这时候就需要自定义 java 代码颜色，这里以局部变量为例。

    File --> Settings --> Editor --> Color & Fonts --> Java --> 点击 Click on Save As…按钮创建一个新的配色Scheme
    （之前未创建的就创建一下）--> 展开下方的 Variables 选择 Local variable --> 设置右侧的 Foreground 颜色

##### 10)设置包类列表的显示方式(eclipse的完全显示或者studio的层级列表样式):

    点击project哪一行的有一个圆的齿轮,点击一下,选择Flatten Packages 就可以像eclipse那样完全显示了,反之,去掉这个对勾,就是studio的样式了. 

### （四）其他设置

##### 1)Android Studio首次安装运行时卡在更新处理方法，Android Studio安装目录下的 bin 目录下,找到 idea.properties 文件,在文件最后追加以下这行代码：

    disable.android.first.run=true
 
##### 2)打开快捷键设置

    File --> Settings --> Keymap，然后要修改哪个快捷键，自己去看

##### 3)禁用studio的自动检查更新

    File --> Settings --> Appearance & Behavior --> System Settings --> Updates,取消对钩就是禁止更新,右侧的列表，是更新通道。

    Stable Channel ： 正式版本通道，只会获取最新的正式版本。(最稳定)
    Beta Channel ： 测试版本通道，只会获取最新的测试版本。
    Dev Channel ： 开发发布通道，只会获取最新的开发版本。
    Canary Channel ： 预览发布通道，只会获取最新的预览版本(问题较多,不建议选择这个)
 

##### 4）设置 Gradle 的离线模式：

    File --> Settings --> Bulid,Execution,Deployment --> Bulid Tools --> Gradle,把以下这两个打钩：
      1.use default gradle wapper (推荐用这个歌)
      2.Offline work（离线模式）
 
##### 5)设置 Android SDK路径

    Settings --> Appearance and Behavior --> System Settings --> Android SDK
 
##### 6)运行Android Studio会提醒你 JDK 或者 Android SDK 不存在,你需要到全局的Project Structure 页面下进行设置。进入全局的Project Structure 页面方法如下：

    方法1:(打开一个项目，点击close project就可以看到了)选择 Configure --> Project Defaults --> Project Structure
	
    方法2:选择 File --> Other Settings --> Default Project Structure,设置 JDK 或者 Android SDK 目录即可

##### 7)插件安装

    File --> Settings --> Plugins --> Browse repositories…  搜索插件安装

##### 8) 每次打开studio 会有个提示，查看和关闭的方式：

    点击菜单栏的 Help --> Tips of the Day  --> 可以查看提示窗，点击上面的Show tips on Startup 对勾去掉，以后再打开就不会
    出现这个提示了。如果要查看提示，就点击菜单栏的 Help --> Tips of the Day

##### 9) 禁止代码折叠：

    File --> Settings --> Editor --> Code Folding，取消以下3个勾选:
      One-line methods
      "Closures"(anonymous classes implementing one method,before Java 8)
      Generic constructor and method parameters

##### 10)使用炫酷的黑色界面

    Settings --> Appearance --> Theme ，选择 Darcula 主题
 
##### 11)显示空格(这样就能看出缩进是 tab 缩进还是空格缩进,建议使用tab缩进)

    File --> Settings --> Editor --> General --> Appearance，勾选 Show whitespaces
 
##### 12)修改注释位置，禁用“语句堆一行”：

    File --> Settings --> Editor --> Code Style --> Java，点击右边的Wrapping and Braces，把下面这两个对勾去掉：
    □ Comment at frist column：禁用表示根据缩进来注释，否则注释位于句首。
    □ Control statement in one line：如果勾上，格式化代码的时候，会把些很短的语句合并成一行。



# 二、快捷键

### （一）超级常用

* Ctrl + C 复制

* Ctrl + V 粘贴

* Ctrl + X 剪切

* Alt + 回车Enter （1）生成变量; （2）快速修复错误; （3）光标停在类上，实现自动导包

* Ctrl + Shift + Enter 快速补全语句。
 
         如if(){}、switch(){}代码块，只要输入if或者switch（甚至sw），接着按Ctrl + Shift + Enter可以快速完形代码块。

* Alt + Insert 快速插入代码。

        快速生成构造函数、getter和setter方法、重写方法，有些插件入口（比如GsonFormat）也会显示在这儿

### （二）非常常用

* Alt + Insert 新建(module、文件夹、类等) 鼠标点击module名字，按下这组快捷键。

* Alt + ↑/↓  在当前类、接口和方法之间跳转。

* Ctrl + Shift + ↑/↓  向上/下移动行，如果是方法中的代码，只能在方法内部一定，不能跨方法。

* Alt + Shift + ↑↓ 上下移动代码。可以跨方法移动。

* Ctrl + Tab 切换面板或文件，功能类似Windows下的Alt + Tab。

* Ctrl + Y  删除行

* Ctrl + X  删除并复制行

* Ctrl + D  复制并粘贴行

* Ctrl + / 注释或取消注释当前行或选中的代码块，以双斜杠的方式即“//”

* Ctrl + shift + / 注释或取消注释选中的代码块，以“/*……*/”方式注释

* Ctrl + 鼠标左键 快速查看任何类的源码

* Alt + J 多处选择。
 
        识别当前选中字符串，选择下一个同样的字符串，并且添加一个光标。相同字符串太多的话，需要多次重复操作这个快捷键。

* Alt + 鼠标拖动 多行、列选择。

         前提是要开启块选择模式才能用这个快键键。开启（关闭也是在这里设置）方式是：Menu → Edit → Column Selection Mode

* Shift + Alt + Insert 切换块选择模式，或者点击 Menu → Edit → Column Selection Mode

* Ctrl + W 从光标处开始，逐渐扩大选择范围，Ctrl + Shift + W 与之相反

* Ctrl + F12 快速显示outline，查看类中的所有变量、方法、内部类、内部接口。
 
        (它是以弹窗形式展现出来的，内容和Structure面板是相同的，只是展现方式不同)

* 双击Shift 查找任意内容（类、布局、资源，甚至是 窗口Windows、动作Actions、符号Symbols）

* Alt + 7 打开类的Structure面板（它是以面板形式附在Android Studio两侧的）

* Ctrl + F 在当前文件查找内容（功能等同 Alt＋F3 也可以快速寻找）

* Ctrl + Shift + F 搜索文件中的内容（这个是全局搜索某一个内容）

* Ctrl + N 查找类

* Ctrl + Shift + N 查找文件（类、布局、资源）

* Ctrl + Shift + A 查找操作。

         输入某个操作的名称，快速查找。对于没有快捷键的部分操作这是一个很有用的技巧。

* Ctrl + R 在当前文件查找并替换内容

* Ctr+Shift+R 全局替换

* Ctrl+P 查看方法参数

* Ctrl + O 重写父类方法

* Ctrl + I 实现接口里面的方法

* Ctrl + Q 查看注释文档。
 
        将鼠标光标定位到某个类名、接口名或者方法名，按Ctrl + Q，会显示出该类、接口、方法的注释。

* Ctrl＋J 查看定义的Live Templates模板

### （三）较常用

* Ctrl + F4 关闭当前窗口

* Shift + Esc 关闭当前打开的面板。

* Shift + F6 重命名

* Alt＋F8 计算变量值

* Ctrl + Alt + L 格式化

* Ctrl + Alt + M 抽取方法

* Ctrl + Alt + V 提取变量（先选择要提取的变量，再按快捷键）

* Ctrl + Alt + F 抽取全局变量（鼠标放到变量前面，再按快捷键）

* Alt+Y 抽取样式（需要自定义快捷键）。

        光标放在控件内: 右键 –> Refactor –> Extract –> Style… ,或者自定义快捷方式,比如我定义的是Alt+Y

* Ctrl + Alt + T 快速生成结构体（if、try-catch…）

         注意：如果先有代码需要在外层加上结构体，先选中要包裹在结构体内的代码，再按快捷键。

* Ctrl + Shift + U 大小写转换

* Ctrl + 鼠标点击Tab 打开当前文件所在的位置（Open File Externally）

* Ctrl + E 显示最近访问的文件，可以快速再次打开这些文件。

* Ctrl + Shift + E 最近修改的文件（Recently Changed Files）

* Ctrl+Shift+backSpace退格键  回到上次编辑的位置（可以一直回溯）

* Ctrl+Alt+ ←/→ 返回至上次浏览的位置

* F2 或Shift+F2 高亮错误或警告快速定位

### （四）关于 查看类具体对象使用、查看接口实现、查看方法的调用

* Ctrl + H 查看一个类的完整上下继承关系

* Ctrl + U 查看快速跳转至父类，或者快速跳转到父类中的某个方法。

        将鼠标光标定位到类名上或方法上，按下这组快捷键，就会跳到对应的父类或者方法（功能等同于Ctrl + 鼠标左键，比这个更高效）。

* Ctrl + Alt + H 将光标停在方法名上，查看执行到该方法的所有执行路径

* Alt + F7 光标停在方法名或变量上，快速查看调用方法的地方（常用，同时要区别于上面的快捷键）

* Ctrl + Shift + I 查看定义（Quick Definition Lookup）


        用这个快捷键可以查看一个方法或者类的具体实现，却不用离开当前界面。（相比较Ctrl + Alt + B，推荐使用这个快键键组合更方便）


* Ctrl + Alt + B 查看接口、抽象方法的实现（或者直接点击左侧的 ↓ 箭头）

* Ctrl + B 查看跳入/跳出方法或者资源文件。

        将鼠标光标定位到某个方法或者资源id的调用处，按这组快捷键，将会跳入该方法或者资源文件内部(功能等同于Ctrl + 鼠标左键)。
        再次按Ctrl + B将会返回调用处。

* Alt + Q 快速查看当前类继承的父类或者实现的接口。（在任意位置都可以查看）


### （五）关于代码补全/智能提示

【tips】使用Enter和Tab进行代码补全的差别

    使用Enter时：从光标处插入补全的代码，对原来的代码不做任何操作。
   
    使用Tab时：从光标处插入补全的代码，并删除后面的代码，直到遇到点号、圆括号、分号或空格为止。

* Ctrl + Shift + Enter 快速补全语句。

        如if(){}、switch(){}代码块，只要输入if或者switch（甚至sw），接着按Ctrl + Shift + Enter可以快速完形代码块。

* Ctrl + Alt + 空格键Space   类名自动完成。
 
          输入一个不完整的类名或者接口名，按Ctrl + Alt + Space，会给出完整类名或接口名的提示。
        （这个是用得最多的，如果习惯eclipse的快捷键可以修改成Alt + /，改了之后有冲突，原来的按那个Alt + /是复制扩展字的快捷键，
         可以把复制扩展字的快捷键替换成Ctrl + Alt + 空格）

* Ctrl + 空格  基本的智能提示

* Ctrl + Shift + 空格  智能型的提示

* Alt + / 复制扩展字

* Alt + Shift + / 向后复制循环扩展字


----------

**[关于快捷键的gif操作演示可以查看这篇博客](http://www.open-open.com/lib/view/open1458715872710.html)**

