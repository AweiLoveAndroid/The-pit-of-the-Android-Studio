# 安卓studio好用的插件:

以下只列举一些比较实用的插件名称.打开Android Studio的settings里面都是可以找到的.

 **[动态演示图详解请点击查看我的博客](http://www.jianshu.com/p/269a48d7508d)**

> **生成java文件，xml布局和生成资源文件有关:**

    1.SmartFindViewById 重构了GenerateFindViewById 项目的所有代码，使得在一定程度上可以更方便地进行后期扩展。并在GenerateFindViewById 项目
       基础上新增了智能查找布局文件，优化了展示界面
    
    2.GenerateFindViewById 可输入布局字段，可选中布局文件字段，可编辑变量名，自动生成有id控件相应的代码,自动生成onCreate/onCreateView方法，
    可选择是否生成、是否生成OnClick代码，可选择是否LayoutInflater类型，支持ButterKnife用法（跟ButterKnife原始用法有区别，慎用）
    
    3.Android Code Generator 
    【优点】根据布局文件快速生成对应的Activity，Fragment，Adapter，Menu类,点击Android Studio菜单的file -->
      setting--> Android Code Generator，找到生成代码的模板可以修改，很方便。
    【缺点】自动生成的Activity或者Activity，Fragment，Adapter，Menu 的java代码，生成的都是set get方法，操作不方便。需要自己去定义模板才可以。
    
    4.Android Layout ID Converter 放在含有id的xml文件上，右键，生成对应的id
    【缺点】只能设置m前缀,_前缀或者无任何前缀，扩展性不好
    
    5.LayoutCreator 可以让你在Activity/Fragment中自动生成findViewById等布局相关初始化代码，或者在Adapter中自动生成ViewHolder代码。
    【缺点】控件id是什么，用这个插件生成的控件命名就是什么，命名不规范。（github源码：https://github.com/boredream/BorePlugin）
    
    6.Android Studio Prettify 从布局文件中生成对View的声明，这个插件帮助我们自动生成findViewById这种代码。
    【缺点】1) 多个Module拥有同名的xml布局文件，有可能会设置到别的Module的xml布局文件中。
           2) 生成的代码都在onCreate或者onCreateView中，可读性差。
    
    7.AndroidAccessors 快速生成get set方法，用法： 在代码中写完Java Bean对象后,按下Alt+Insert后选择AndroidAccessors即可
    【缺点】Android Studio自带有这个功能，没必要下载这个插件



> **资源文件的管理和自动生成有关：**

    1.Android Styler 根据xml自动生成【style样式】

    2.Strings-xml-tools 管理Android项目中的字符串资源，它提供了排序Android本地文件和添加缺少的字符串的基本操作。

    3.Android Holo Colors Generator  通过自定义Holo主题颜色生成对应的【Drawable】和【布局文件】

    4.SelectorChapek for Android 通过资源文件命名自动生成【Selector】文件，已经3年没更新，使用过程会报错。

    5.AndroidMaterialDesignIconGenerator 是一个可以生成【Material Design图标】的插件 ，使用方式，右键项目，
       选择Material Design Icon，可以选择icon图标，大小，路径等



> **格式化xml布局工具：**

    1.LayoutFormatter  调整Android布局XML文件属性顺序，并且会将默认属性调整到前面，并在行的末尾使用自定义属性。
     
    2.LayoutFormat 功能有两个：1.批量去格式化layout.xml，2.修改某一个layout.xml硬编码。
    使用中可能会遇到的问题，在导入插件时，windows下可能会出现插件加载失败的情况。会报下面的错误：
      cannot create class "com.shang.layoutformat.LayoutFormat" [Plugin: com.shang.android.layoutformat]
      com.intellij.diagnostic.PluginException: cannot create class "com.shang.layoutformat.LayoutFormat"
           [Plugin: com.shang.android.layoutformat]...后面还有一大串，在此省略
      这是使用的android studio 的运行时的jdk版本低于插件的jdk,换成最新的jre1.8就OK了（
      查看android studio 的 java 版本是在：菜单栏 > Help  > About）



> **权限有关：**

    PermissionsDispatcher plugin 自动生成6.0权限的代码
    
    用法：
    第1步.打开项目modle里面的build.gradle 右键 Generate -> Add PermissionsDispatcher dependencies，添加依赖
    
    第2步.打开 Activity/Fragment，右键 Generate -> Generate Runtime Permissions... 选择要设置的权限，输入注解的方法名，点击Generate 按钮



> **序列化工具：**

    1.Android Parcelable code generator  自动生成Parcelable序列化

    2.Android Parcelable code generator(for kotlin)  使用kotlin开发时自动生成Parcelable序列化
    
    3.GenerateSerialVersionUID 自动生成Serializable序列化
   
    4.SerializableParcelable Generator 自动生成Serializable序列化
 

> **翻译有关：**

    1.ECTranslation  可以将英文翻译为中文
    
    2.AndroidLocalizationer 可用于将项目中的 string 资源自动翻译为其他语言
    
    3.TranslationPlugin 又一翻译插件,可中英互译
    
    4.ReciteWords 这是一个androidStudio翻译与陌生单词记录插件，你所翻译的单词会被记录在你当前用户目录下的ReciteWords.md文件中
    （如:C:\Users\Bolex\ReciteWords.md）。可以通过Markdown编辑器打开它进行学习。



> **第三方注解，事件和依赖注入库可视化工具：**

    1.Android ButterKnife Plugin Plus 它是基于android-butterknife-zelezny 1.6开发的，并在此基础上新增了以下功能。
    （1）可以自由选择是否在当前类中对ButterKnife进行初始化
    （2）在Android Studio的设置界面，对在当前类中是否强制初始化提供了默认值设置

    2.Android ButterKnife Zelezny 使用方式：在布局右键Generate --> Generate ButterKnife Injections --> 选择要命的名
      （或者快捷键Ctrl+Shift+B)

    3.Remove ButterKnife 把使用ButterKnife的注解快速批量切换成正常findViewbyId,下载了这个插件之后，
      点击菜单栏 Edit --> RemoveButterKnife，轻松搞定

    2.dagger-intellij-plugin     dagger可视化辅助工具

    3.otto-intellij-plugin       otto事件导航工具

    4.eventbus-intellij-plugin   eventbus导航插件

    5.databinding-support       一个可以快速实现databinding的插件



> **代码补全工具：**

    1. Android Postfix Completion 可根据后缀快速完成代码，这个插件在studio原有的基础上增添了一些新的功能
      有这些语句可以操作：  .toast .log .logd .find .isemp .vg .vsb  .invsb  .gone  .snack   .snackaction

    2. GradleDependenciesHelperPlugin   maven gradle依赖支持自动补全



> **辅助工具**

    1.GsonFormat   快速生成json实体类的插件
    
    2.Android Methods Count 统计第三方依赖库的方法数。打开项目module里面的build.gradle，发现里面行号后面多了几个小蓝色圆圈，鼠标放上面就会显示
      方法数信息。你会发现依赖库变成了灰色，后面中括号里面就是方法数以及相关依赖信息等，点一下就显示正常的依赖内容
    【缺点】项目里面的modle依赖了一个自己写的lib,不能统计lib里的方法数
    
    3.Statistic 统计代码行数 首次安装在AS的View→Tool Windows→Statistic，选择之后会在AS的左下角出现statistic按钮，
      然后点击菜单里面的Settings后，会出现设置窗口，找到Statistic，点击add,添加要统计代码的项目就可以了。
    具体设置参数请查看我的博客有详细讲解。
    


    3.CodeGlance  在右边可以预览代码，实现快速定位
     
    4.Lifecycle Sorter 可以根据Activity或者fragment的生命周期对其生命周期方法位置进行先后排序，快捷键Ctrl + alt + K
    
    5.SingletonTest 快速生成单例模式的预设，单例的六种生成方式:LazyUnSafe,LazySafe,Hungry,DoubleCheck,StaticInner,Enum。
    
    6.CheckStyle-IDEA 检查代码风格的插件，比如像命名约定，Javadoc，类设计等方面进行代码规范和风格的检查，你们可以遵从像
      Google Oracle 的Java 代码指南 ，当然也可以按照自己的规则来设置配置文件，从而有效约束你自己更好地遵循代码编写规范。



> **UI优化有关：**

    1.lint-cleaner-plugin 删除未使用的资源,包括String字符串,颜色和尺寸。 这是一个Gradle插件，所以如何配置可以去github的源码上看。
      插件源码地址：https://github.com/marcoRS/lint-cleaner-plugin

    2.folding-plugin  布局文件分组的插件，该插件可自动将前缀相同的文件归类显示到同一文件目录下，但不会因此而移动文件或创建文件夹。

    3.Android Drawable Importer 这是一个非常强大的图片导入插件。它导入Android图标与Material图标的Drawable ，批量导入Drawable，
      多源导入Drawable（即导入某张图片各种dpi对应的图片）



> **主题相关：**

    1.Material Theme UI  添加Material主题到你的AS

    2.Android Studio插件之sexy editor（设置AS背景）



> **测试和调试相关：**

    1.LeakCanary 帮助你在开发阶段方便的检测出内存泄露的问题
    
    2.findBugs-IDEA 帮你一起找bug的一个插件
    
    3.ADB WIFI 无需root就能wifi调试
    
    4.JSONOnlineViewer 可实现直接在android studio中调试接口数据，可以选择请求类型，自定义请求头及请求体，json数据格式化后展示
    
    5.adb-idea 可以一键清理缓存并重启APP
    
    6.Robotium Recorder  一个自动化测试框架，用于测试在模拟器和Android设备上原生的和混合的移动应用程序。Robotium Recorder可以让你记录测试案例
      和用户操作。你也可以查看不同Android活动时的系统功能和用户测试场景。





