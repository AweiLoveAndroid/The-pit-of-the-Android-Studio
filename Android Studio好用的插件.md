# 安卓studio好用的插件:

 **[动态演示图详解请点击查看我的博客](http://www.jianshu.com/p/269a48d7508d)**

  俗话说得好，工欲善其事，必先利其器。做开发时间长了，总想找一些快捷方法，只有拥有好用的工具，才能节省开发时间，提高工作效率。我就是一个 **追（喜）求（欢）高（偷）效（懒）** 的开发人员，正好趁着国庆假期，把平日用到的一些 **Android Studio开发插件** 整理了一下，分享给大家。

  > 首先，我分门别类，按类型把功能类似的的都放在一起。

  > 其次，我对每一个插件做了一个很精确的讲解，图文并茂。另外把一些注意事项，以及优缺点都写的清清楚楚，这是我自己使用中总结出来的（极个别的除外）。

  > 再次，制作对比图片，以及截图补充说明。网上的有些动图要么太模糊，要么版本太旧，要么就是速度太快看不清。所以我把很多插件的用法自己做了一个录屏，做成gif动图。另外自己也做了一些图片对比图，方便别人查看插件使用前后的区别。（有些图片用的是网上的或者官方的，在此感到抱歉，因为那些图片能够解决问题，也没什么大的问题，所以暂时借用了。）

  好了，言归正传，下面看一下今天的 **目录**。

> 一、生成java文件，xml布局和生成资源文件有关:
1.SmartFindViewById
2.GenerateFindViewById(很完美的一个插件)
3.LayoutCreator
4.Android Code Generator
5.Android Studio Prettify
6.AndroidAccessors
7.Android Layout ID Converter
8.BorePlugin
9.Exynap
10.MVPHelper
11.InnerBuilder 

> 二、资源文件的管理和自动生成有关：
1.svgtoandroid
2.Android Holo Colors Generator
3.Android Drawable Importer(36M,有点大) 快速批量导入不同大小的drawable文件
4.Android Material Design Icon Generator 是一个可以生成【Material Design图标】的插件。
5.Android Styler 根据xml自动生成style样式(有点复杂，不实用)
6.android-strings-search-plugin
7.color-manager
8.AndroidPixelDimenGenerator
9.android-selector-intellij-plugin
下面这几个不常用，作为了解：
DimenGenerator 命令行生成dimen
android-selector-chapek
Strings-xml-tools

> 三、格式化xml布局工具：
1.LayoutFormatter
2.LayoutFormat

> 四、权限有关：
PermissionsDispatcher plugin

> 五、序列化工具：
1.Android Parcelable code generator自动生成Parcelable序列化
2.Android Parcelable code generator(for kotlin)使用kotlin开发时自动生成Parcelable序列化。
3.GenerateSerialVersionUID自动生成Serializable序列化。
4.SerializableParcelable Generator自动生成Serializable序列化

> 六、翻译有关：
1.ECTranslation
2.AndroidLocalizationer
3.TranslationPlugin
4.ReciteWords

> 七、第三方注解，事件和依赖注入库可视化工具：
1.Android ButterKnife Plugin Plus
2.Android ButterKnife Zelezny
3.Remove ButterKnife
4.eventbus3-intellij-plugin
5.dagger-intellij-plugin dagger
6.otto-intellij-plugin otto
7.databinding-support

> 八、代码补全工具：
1.Android Postfix Completion
2.GradleDependenciesHelperPlugin
3..ignore

> 九、辅助工具
1.CodeGlance 代码预览和快速定位
2.IconViewer图标预览插件
3.GsonFormat 快速生成json实体类的插件
4.JsonToKotlinClass 能将 Json 数据直接映射生成 Kotlin Data Class 代码。
5.android-studio-proteus-plugin 将xml转化为json。
6.Lifecycle Sorter 按生命周期排序
7.Android Methods Count 统计第三方依赖库的方法数。
8.dexcount-gradle-plugin 统计方法数
9.Android-Resource-Usage-Count 显示每个资源文件的引用次数
10.Statistic 统计代码行数
11.SingletonTest 生成单例模式的类
12.TemplateBuilder是一款能够帮助我们快速生成Android Studio Template的Android Studio插件
13.Markdown Navigator是一个能在IDE编辑markdown语法的插件。
14.idea-markdown
15.instapk-studio-plugin 分享apk文件

> 十、UI优化有关：
1.TinyPic 压缩图片资源
2.lint-cleaner-plugin 删除未使用的资源
3.folding-plugin 布局文件分组的插件

> 十一、Android Studio主题相关：
1.Material Theme UI 添加Material主题到你的Android Studio
2.Android Studio插件之sexy editor（设置AS代码编辑区的背景图）

> 十二、UML工具有关
1.Code Iris快速分析布局以及代码包结构关系，并生成UML图
2.SimpleUML 生成UML图

> 十三、打包、加固、混淆、Gradle编译、搜索代码有关：
1.AndroidProguardPlugin一键生成项目混淆代码插件(不过目前可能有些第三方项目的混淆还未添加完全)
2.ApkMultiChannelPlugin 一个为了方便 Android 多渠道打包的 Android Studio / IDEA 插件
3.Codota 搜索最好的Android代码
4.intellij-java2smali将Java & Kotlin编译成smali
5.gradle-cleaner-intellij-plugin强制清除延迟，不再需要Gradle任务。
6.freeline Android 平台上的秒级编译方案，Instant Run 的替代品

> 十四、检测、Code Review、测试和调试相关：
1.LeakCanary 帮助你在开发阶段方便的检测出内存泄露的问题。
2.JVM Debugger Memory View Android Studio和IDEA中一个很有用的内存调试插件。
3.reVu 代码review神器，这个插件比较轻量，review记录保存在xml文件中，直接提交到git
4.findBugs-IDEA 帮你一起找bug的一个插件,很老的一个插件了。
5.CheckStyle-IDEA（49M，有点大）检查代码风格的插件。
6.JSONOnlineViewer 在android studio中调试接口数据
7.ADB WIFI 无需root就能wifi调试
8.adb-idea 可以一键清理缓存并重启APP
9.SQL Scout (SQLite Support) 在 Android Studio 上调试数据库 ( SQLite )
10.Robotium Recorder一个自动化测试框架。



##### 一、生成java文件，xml布局和生成资源文件有关:

> 1.SmartFindViewById

* 作用: 重构了GenerateFindViewById 项目的所有代码，使得在一定程度上可以更方便地进行后期扩展。并在GenerateFindViewById 项目基础上新增了智能查找布局文件，优化了展示界面,增加了 I18N 国际化支持等功能。[SmartFindViewById插件github地址](https://github.com/Khande/SmartFindViewById)

*  说明:
　　该插件可以依次通过以下6种方式来逐一尝试获取目标布局文件名，优先级从高到低，一旦有一个方法获取到了有效的布局文件名， 就会展示对应布局文件的所有拥有 id 的 View 控件，然后可以选择生成对应的 findViewById 和 onClick 点击事件代码。


    1.选中布局文件名，如选中代码段 setContentView（R.layout.activity_main); 中的 activity_main
    2.检测当前光标所在行是否包含布局文件名（通过 R.layout. 前缀判断）
    3.Activity setContentView(R.layout.xxx) 方法布局文件参数
    4.Fragment(包括 support_v4 fragment) 中 onCreateView 方法中 inflate(R.layout.xxx... 布局参数
    5.RecyclerViewAdapter 中 onCreateViewHolder 方法中 inflate(R.layout.xxx... 布局参数
    6.弹输入框提示手动输入

* 注意事项：如果是Activity，必须要有oncreate方法，如果是fragment，必须要有onCreateView方法，如果是适配器里面的布局，必须要有onCreateViewHolder 方法。也就说，必须要有布局参数。

* 快捷键：  Ctrl + Alt + S

* 用法：


    1.在一个 Activity, Fragment, RecyclerViewAdapter（包含直接或间接子类）甚至一个一般的类文件中，如果对应代码中已存在布局文件名，
      可以对着类文件右键选择Generate，选择 SmartFindViewById 菜单（或是 Ctrl + Alt + S, 或者
      点击菜单栏Code 选择 SmartFindViewById ）, 这时就会自动查找布局文件，然后弹出一个展示目标布局
      文件下的所有有 id 的 View 控件列表，如果你的布局文件不是写在 setContentView(R.layout.xxx) 等常见代码中，
      你可以手动选定目标布局文件名或将光标定位到目标布局文件名所在的代码行, 最后还可以手动输入。

    2.在弹出的 View 控件列表弹框中，默认选中还没有编写 findViewById 代码的 View 控件，当然也可以手动选中或取消。

    3.可以根据 View 控件是否有 android:clickable=true 属性或是 Button 类控件，自动勾选自动生成 onClick 点击事件代码。

    4.可以编辑 View 控件生成类成员变量的变量名，View 成员变量名生成默认规则类似于： android:id="@+id/btn_submit_info" 
      对应的成员变量名为 mSubmitInfoBtn

    5.对于 Fragment 等需要 rootView.findViewById, 可以勾选 RootView 选项，同时可以设置该 RootView 的变量名，默认为 itemView, 
      对于非 Activity 类该选项默认勾选

    6.点击确认生成

* 演示图如下：

这是无布局参数生成的效果（看看有多麻烦就知道了）：

![SmartFindViewById 使用_无布局参数](http://upload-images.jianshu.io/upload_images/6098829-91efc3e39dbce1f7.gif?imageMogr2/auto-orient/strip)


这是有布局参数生成的效果：

![SmartFindViewById 使用_有布局参数](http://upload-images.jianshu.io/upload_images/6098829-dc664a79612688b5.gif?imageMogr2/auto-orient/strip)



----

> 2.GenerateFindViewById(很完美的一个插件)

* 快捷键：Ctrl+Alt+E

* 作用:
      

    1）可输入布局字段、可选中布局文件字段，自动生成有id控件相应的代码(如果鼠标只是放在布局上，按下快捷键，会弹出输入框，提示输入布局；
        鼠标双击布局，就不会有弹窗让你输入布局了)
    2）自动生成onCreate/onCreateView方法
    3）可编辑变量名
    4）可选择是否生成OnClick代码
    5）可选择是否LayoutInflater类型
    6）支持ButterKnife用法（跟ButterKnife原始用法有区别，慎用）

* 用法（用途很多，下面就简单的来几张图演示一下）：

Activity如果没有onCreate方法，会先生成onCreate方法，再重新操作一次才生成有id控件相应的代码。如下图所示：


![GenerateFindViewById 在 Activity 的使用](http://upload-images.jianshu.io/upload_images/6098829-be68e3eab239c7a4.gif?imageMogr2/auto-orient/strip)

Fragment如果没有onCreateView方法，会先生成onCreateView方法，再重新操作一次才生成有id控件相应的代码。如下图所示：


![GenerateFindViewById 在 Fragment 的使用](http://upload-images.jianshu.io/upload_images/6098829-38046edc17c89e4d.gif?imageMogr2/auto-orient/strip)



----

> 3.LayoutCreator 

* 作用：可以让你在Activity/Fragment中自动生成findViewById等布局相关初始化代码，或者在Adapter中自动生成ViewHolder代码。

* 用法：鼠标放在布局文件上，按快捷键alt + Insert(或点右键选择Generate  / 或点击菜单Code → Generate  )，右键选择LayoutCreator，选择要生成的变量以及其他设置，点击confirm就可以了。

下面这个图是以Activity生成代码作为演示：

![LayoutCreator 使用](http://upload-images.jianshu.io/upload_images/6098829-c838ff445ee276b0.gif?imageMogr2/auto-orient/strip)

【缺点】

    1) 控件id是什么，用这个插件生成的控件命名就是什么，命名不规范。

    2) EditText之类的可以编辑的控件，获取数据的时候，用的是id名字获取的，要手动改一下。(请看示例图上有一处报错的，那个就是。)

----

> 4.Android Code Generator 

 * **用法:** 找到布局文件名称，右键，选择Generate Android Code → 选择要生成的类型（默认是6种类型可供选择）, 选择生成的代码存放的路径以及包名，如果有多个module或者lib,默认的包名是第一个module的包名(比如我的第一个module是app，包名是 **com.lzw.logutilsdemo** )

![使用步骤](http://upload-images.jianshu.io/upload_images/6098829-b63085e692b8bd41.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

 * 使用图解如下：

![Android Code Generator 生成 Activity 的代码](http://upload-images.jianshu.io/upload_images/6098829-7394aa8a810f2e81.gif?imageMogr2/auto-orient/strip)

![Android Code Generator 生成 Menu 的代码](http://upload-images.jianshu.io/upload_images/6098829-cb2e20c2ffb0fc0e.gif?imageMogr2/auto-orient/strip)


* 【优点】根据布局文件快速生成对应的Activity，Fragment，Adapter，Menu类,点击Android Studio菜单的file --> setting--> Android Code Generator，可以快速生成文件，也可以复制代码到剪切板，很方便。

* 【缺点】


    (1) 生成的menu需要自己复制粘贴，很麻烦。
    (2) 每次都要手动设置路径和包名，很麻烦。
    (3) 生成的点击事件需要自己去导包，很麻烦。
    (4) 生成的控件如果是button之类的，是这种格式 findViewById(R.id.btn).setOnClickListener(this); 其他的都是很标准的，
    看起来很不美观，建议改善。
    (5) 生成的类名不规范，比如我的xml是activity_main2.xml,生成的Activity名字是ActivityMain2Activity，这显然是多此一举，
    应该把前面那个Activity去掉，并且调整一下顺序，如果是MainActivity2就对了。

----

> 5.Android Studio Prettify
* 作用：


    1. 可以将代码中的字符串写在string.xml文件中，选中字符串鼠标右键选择Extract String resource

![Android Studio Prettify 使用](http://upload-images.jianshu.io/upload_images/6098829-ed3f86c8b17f56d2.gif?imageMogr2/auto-orient/strip)



    2. 从布局文件中生成对View的声明，这个插件帮助我们自动生成findViewById这种代码。
    (有两种提示，一个是View Variables ，一个是View Fields,如下图所示：)

![Android Studio Prettify 使用_View Variables](http://upload-images.jianshu.io/upload_images/6098829-a9f27ddbd8887120.gif?imageMogr2/auto-orient/strip)

![Android Studio Prettify 使用_View Fields](http://upload-images.jianshu.io/upload_images/6098829-a2622e0b311ca2a9.gif?imageMogr2/auto-orient/strip)

两者的区别：View Variables是直接生成局部变量，而且是排成一排；View Fields是生成全局变量并引用。

* 【缺点】


    1) 多个Module拥有同名的xml布局文件，有可能会设置到别的Module的xml布局文件中。

    2) 生成的代码都在onCreate或者onCreateView中，可读性差。

    3) 生成的全局变量的导包是在变量类型上的，而不是在类外面导包，很不规范。

----

> 6. AndroidAccessors 快速生成get set方法，用法： 在代码中写完Java Bean对象后,按下Alt+Insert后选择AndroidAccessors即可

* 使用图解如下：(图里面第一次用的是AndroidAccessors 演示的，第二次用的系统自带的演示的)

![AndroidAccessors 使用](http://upload-images.jianshu.io/upload_images/6098829-59024c916ccb78fb.gif?imageMogr2/auto-orient/strip)

* 【缺点】Android Studio自带有这个功能，没必要下载这个插件

----

>7. Android Layout ID Converter（这个最麻烦，不推荐使用，仅作为了解）

 * 使用：鼠标在布局文件右键，在弹出来的菜单当中选择Convert Android layout xml，然后它会弹出一个面板，如下所示。选择要生成的代码的格式，按OK，这时它已经把生成的代码复制在你的粘贴板中，然后你在使用这个布局文件的Activity或Fragment中，按Ctrl + V 把代码粘贴出来就可以了。

![Android Layout ID Converter 使用](http://upload-images.jianshu.io/upload_images/6098829-ad382dda6944fccd.gif?imageMogr2/auto-orient/strip)

* 【缺点】需要手动粘贴，麻烦；另外只能设置m前缀,_前缀或者无任何前缀，扩展性不好。

----

> 8. [BorePlugin](https://github.com/boredream/BorePlugin)
* Android Studio 自动生成代码插件（Android Studio插件搜索LayoutCreator就可以下载，具体讲解请查看LayoutCreator）

----

> 9. [Exynap](http://exynap.com/)
Exynap 一个帮助开发者自动生成样板代码的 AndroidStudio 插件。只需要一个快捷方式（Ctrl + Shift + D），输入命令就可以生成代码了。

![Exynap使用示范](http://upload-images.jianshu.io/upload_images/6098829-feb6d56caf5a90be.gif?imageMogr2/auto-orient/strip)

----

> 10. [MVPHelper](http://androidwing.net/index.php/27)
一款Intellj IDEA 和Android Studio的插件，可以为MVP生成接口以及实现类，解放双手。具体请查看
[Android Studio插件之MVPHelper，一键生成MVP代码](http://androidwing.net/index.php/27)一文

* 使用图如下：

![MVPHelper插件使用](http://upload-images.jianshu.io/upload_images/6098829-1262c9dee29121f8.gif?imageMogr2/auto-orient/strip)

----

> 11. [innerbuilder](https://github.com/analytically/innerbuilder)
InnerBuilder 一款Intellj IDEA 和Android Studio自动生成内部类Builder代码的插件。

* 使用：使用**Shift + Alt + B**  或 **Alt + Insert并选择Builder ....选择要包括的字段**，然后按OK。 
当构建器已存在时生成构建器时，插件将尝试更新它。 它将添加缺少的字段和构建器方法，但不会删除任何字段或方法。

* 示意图：

![InnerBuilder 使用示意图](http://upload-images.jianshu.io/upload_images/6098829-bc1e5d1a857510c6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

##### 二、资源文件的管理和自动生成有关：

>1. [svgtoandroid](https://github.com/misakuo/svgtoandroid)  

* 通过它可以完成从svg文件到Android VectorDrawable的自动化转换，传统做法是网上招一个工具生成一张svg图，然后导入到Android Studio。

* 新版Android Studio自带的svg转VectorDrawable功能：

![Android Studio自带功能](http://upload-images.jianshu.io/upload_images/6098829-e77c1ae8347a3630.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

* 下面一张图演示一下这个插件的用法：

![用法介绍](http://upload-images.jianshu.io/upload_images/6098829-f2c12319c2fa0f7d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![SVG2VectorDrawable 使用](http://upload-images.jianshu.io/upload_images/6098829-670b1ae60aad7f37.gif?imageMogr2/auto-orient/strip)

----

> 2. Android Holo Colors Generator 

* 通过自定义Holo主题颜色生成对应的【Drawable】和【布局文件】，点击导航栏的蓝色的 H 符号，就可以了。各种右键，各种菜单栏都找了，找不到使用方式，找了半天最后在导航栏有个蓝色的H符号，太坑了，官方也没有讲解怎么使用。

![Android Holo Colors Generator 使用](http://upload-images.jianshu.io/upload_images/6098829-0408b8c13ee6ddb2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

> 3. Android Drawable Importer(36M,有点大) 快速批量导入不同大小的drawable文件。

* 它导入Android图标与Material图标的Drawable ，批量导入Drawable，多源导入Drawable（即导入某张图片不同分辨率的图片到对应的drawable目录下）它可以减少导入图像到Android项目所需的工作量。

* 下面看几张截图：
点击任意一个文件，右键New,然后看最后4 个选项，这就是该插件的4个功能

![点击任意一个文件，右键New,然后看最后4 个选项，这就是该插件的4个功能](http://upload-images.jianshu.io/upload_images/6098829-22955e17ee62c6e1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

每个功能的具体演示

![每个功能的具体演示](http://upload-images.jianshu.io/upload_images/6098829-2853ef7e892868d7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

> 4. Android Material Design Icon Generator（14M,这个插件比较大）  是一个可以生成【Material Design图标】的插件 ，使用方式，右键项目，选择Material Design Icon，可以选择icon图标，大小，路径等

*点击任意一个文件，右键New,选择Material design icon，示意图如下：

![Android Material Design Icon Generator 使用](http://upload-images.jianshu.io/upload_images/6098829-5ddaf41829b885c3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

* 选择设置要生成的内容，点OK

![Android Material Design Icon Generator 使用](http://upload-images.jianshu.io/upload_images/6098829-ccc6b0a5426d3657.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

> 5. Android Styler 根据xml自动生成style样式(有点复杂，不实用)

*用法：选中要生成样式的内容，复制到styles.xml里面，右键Paste Style或按快捷键 Ctrl + Shift + D，然后输入一个style的名字，最后在xml里面引用这个样式。

![Android Styler 使用](http://upload-images.jianshu.io/upload_images/6098829-e9b2c0cc9b398323.gif?imageMogr2/auto-orient/strip)

----

> 6. [android-strings-search-plugin](https://github.com/konifar/android-strings-search-plugin)
一个可以通过输入文字找到strings.xml资源的插件

* 官方的示意图如下：

![官方的示意图](http://upload-images.jianshu.io/upload_images/6098829-ca3afa4e8612aa9f.gif?imageMogr2/auto-orient/strip)

* 【缺点】不能输入中文，即使是values-cn里面的strings.xml里面的中文也不能识别

![不能识别中文](http://upload-images.jianshu.io/upload_images/6098829-f0f86e4b323e7951.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

> 7. [color-manager](https://github.com/shiraji/color-manager)
颜色管理

* 使用也很简单：选择要放置的文件，从颜色面板选一个颜色，拖动到您要复制颜色名称/标签的位置。

* 示例图：

  1.在xml中使用颜色

![在xml中使用颜色](http://upload-images.jianshu.io/upload_images/6098829-59db26cc09a89f14.gif?imageMogr2/auto-orient/strip)

  2.不在xml中使用颜色

![不在xml中使用颜色](http://upload-images.jianshu.io/upload_images/6098829-9b766c811fa9ee43.gif?imageMogr2/auto-orient/strip)

----

> 8. [AndroidPixelDimenGenerator](https://github.com/succlz123/AndroidPixelDimenGenerator)
根据输入的像素来自动生成Android项目的dimen.xml文件,主要是为了适配国产Android TV盒子的各种分辨率。 这个插件参考自 [DimenGenerator](https://github.com/yann9/DimenGenerator) 

* 用法：


    1.点击Tools菜单 →  AndroidPixelDimenGenerator
    2.根据提示输入分辨率的取值范围和分辨率
    3.文件生成路径默认在当前项目的res，如果有多个module一般会在第一个的res中，如果遍历不到res文件夹，文件生成路径为当前项目的根目录。

* 示意图：

![示意图](http://upload-images.jianshu.io/upload_images/6098829-4cad54046182743e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

> 9. [android-selector-intellij-plugin](https://github.com/importre/android-selector-intellij-plugin)
插件生成normal，press和按下水波纹颜色

* 使用方式:


    1.首先在 res/values/colors.xml添加颜色
    2.res目录中右键选择New → 选择 Android Selector（或Ctrl+ N快捷键）。
    3.选择文件名，颜色，press按下颜色和按下水波纹(pressed-v21 )的颜色。

* 示例图：


![android-selector-intellij-plugin示例图](http://upload-images.jianshu.io/upload_images/6098829-be0ac1a7a631438d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


----


**下面这几个不常用，作为了解：**

> [DimenGenerator](https://github.com/yann9/DimenGenerator)  命令行生成dimen
----

> [android-selector-chapek](https://github.com/inmite/android-selector-chapek) 

* 通过资源文件命名自动生成 Selector 文件，已经4年没更新，使用过程会报错。按照惯例，还是来一张效果图：

![android-selector-chapek的使用](http://upload-images.jianshu.io/upload_images/6098829-dc7b197fa858f6e1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

>  [Strings-xml-tools](https://plugins.jetbrains.com/plugin/7498-android-strings-xml-tools) 管理Android项目中的字符串资源，它提供了排序Android本地文件和添加缺少的字符串的基本操作。（3年没更新了，这个工具对Android Studio1.2+以上的都不支持，不推荐使用，仅作了解）

##### 三、格式化xml布局工具：

> 1. LayoutFormatter  一键格式化你的 XML 文件，并且调整Android布局XML文件属性顺序，并且会将默认属性调整到前面，并在行的末尾使用自定义属性。

    用法入下：

    1. 选择布局文件右键，或者直接在布局文件里面右键  -> Refactor -> Reformat Layout XML.

    2.  快捷键: ctrl+alt+F 

使用效果对比图如下所示：

![ 使用LayoutFormatter前后对比图](http://upload-images.jianshu.io/upload_images/6098829-97a7839febaa3cc3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 2. LayoutFormat  快速格式化xml代码（因为快捷键和LayoutFormatter 一样，不建议同时安装这两个插件）

功能有两个：

* 1.批量去格式化layout.xml，点击layout目录，右键Refactor,选择LayoutFormat（快捷键Ctrl +Alt + F）

![layout format 批量格式化xml](http://upload-images.jianshu.io/upload_images/6098829-f067bb7682e15642.gif?imageMogr2/auto-orient/strip)

    2.修改某一个layout.xml硬编码，点击布局名字右键Refactor(或者打开布局，鼠标放在布局内容任意地方
    右键Refactor),选择LayoutFormat（快捷键Ctrl +Alt + F）

![layout format 使用](http://upload-images.jianshu.io/upload_images/6098829-0769c6df9900f63c.gif?imageMogr2/auto-orient/strip)

* 使用中可能会遇到的问题，在导入插件时，windows下可能会出现插件加载失败的情况。会报下面的错误：


    cannot create class "com.shang.layoutformat.LayoutFormat" [Plugin: com.shang.android.layoutformat]
     com.intellij.diagnostic.PluginException: cannot create class "com.shang.layoutformat.LayoutFormat"
     [Plugin: com.shang.android.layoutformat]...后面还有一大串，在此省略

    这是使用的android studio 的运行时的jdk版本低于插件的jdk,换成最新的jre1.8就OK了
    ( 查看android studio 的 java 版本是在：菜单栏 > Help  > About）

##### 四、权限有关：

> PermissionsDispatcher plugin 自动生成动态权限的代码

* 用法：


    1. 第1步.打开项目modle里面的build.gradle 右键 Generate -> Add PermissionsDispatcher dependencies，添加依赖

    2. 第2步.打开 Activity/Fragment，右键 Generate -> Generate Runtime Permissions... 选择要设置的权限，
    输入注解的方法名，点击Generate 按钮

* 示范图如下:


![PermissionsDispatcher plugin 使用](http://upload-images.jianshu.io/upload_images/6098829-9a4a0312e9ef505d.gif?imageMogr2/auto-orient/strip)


##### 五、序列化工具：

> 1. Android Parcelable code generator  自动生成Parcelable序列化

![Android Parcelable code generator使用](http://upload-images.jianshu.io/upload_images/6098829-b462aab0d4baaa6d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 2. Android Parcelable code generator(for kotlin)  使用kotlin开发时自动生成Parcelable序列化，用法和上述类似。

> 3. GenerateSerialVersionUID 自动生成Serializable序列化。

【注意】默认情况下Intellij IDEA是关闭了继承了java.io.Serializable的类生成serialVersionUID的警告。如果需要ide提示生成serialVersionUID，那么需要做以下设置：

      1、setting -> Inspections -> Serialization issues，将其展开后将 serialzable class without "serialVersionUID"打上勾；

![SerializableParcelable Generator的使用](http://upload-images.jianshu.io/upload_images/6098829-836a63a2e79952af.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

    2、将光标放到类名上，按 atl＋enter 键，就会提示生成serialVersionUID了

> 4. SerializableParcelable Generator 自动生成Serializable序列化

##### 六、翻译有关：

> 1. [ECTranslation](https://github.com/Skykai521/ECTranslation)

* 这是一个可以对AndroidStudio中的英文进行翻译的一个插件，以后看源码的时候，就不用再去查字典了，方便多了，也可自定义快捷键，具体的可查看其使用说明。

* 使用：选择 Edit -> Translate或者按下Alt + I，即可翻译。(默认的是Meta + I ,windows上没有这个快捷键，我就改成了Alt + I, 点击菜单栏File -> Settinigs -> Keymap -> 搜索Translate - > 右键 add Keyboard Shortcut. 输入你想要的快捷键即可 )

![使用方式](http://upload-images.jianshu.io/upload_images/6098829-ea8ca7e0219225b4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![翻译结果](http://upload-images.jianshu.io/upload_images/6098829-226c90c250a3a6a3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

> 2. [AndroidLocalizationer](https://github.com/westlinkin/AndroidLocalizationer) 可用于将项目中的 string 资源自动翻译为其他语言

![AndroidLocalizationer 使用](http://upload-images.jianshu.io/upload_images/6098829-2e122ee84f24b3e6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

> 3. [TranslationPlugin](https://github.com/YiiGuxing/TranslationPlugin) 又一翻译插件,可中英互译

* 说明：需要注册申请有道智云翻译服务，有一定的使用期限，如帐号到期或欠费，将无法使用。

![TranslationPlugin 使用](http://upload-images.jianshu.io/upload_images/6098829-fd898d264f761402.gif?imageMogr2/auto-orient/strip)

----

> 4. [ReciteWords](https://github.com/BolexLiu/ReciteWords)

* 这是一个androidStudio翻译与陌生单词记录插件，你所翻译的单词会被记录在你当前用户目录下的ReciteWords.md文件中（如:C:\Users\Bolex\ReciteWords.md）。可以通过Markdown编辑器打开它进行学习。
* 使用很简单，选中代码，按下 Alt+Q(也可以自己设定)。即可翻译。效果如下:

![ReciteWords 使用](http://upload-images.jianshu.io/upload_images/6098829-cc6b3ffbd4b12fc3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

* 翻译的单词会被记录在当前项目的根目录下的翻译历史记录.md文件中（如:\xxxProject\翻译历史记录.md）。可以通过Markdown打开它。as翻译后切换Project模式可以在项目文件夹中直接看到。效果如下:

![翻译记录](http://upload-images.jianshu.io/upload_images/6098829-92e69e6f51a0e91b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

##### 七、第三方注解，事件和依赖注入库可视化工具：

> 1. Android ButterKnife Plugin Plus 它是基于android-butterknife-zelezny 1.6开发的，并在此基础上新增了以下功能。

* 1)可以自由选择是否在当前类中对ButterKnife进行初始化，避免了原版本只要使用插件初始化控件会自动在onCreate中进行ButterKnife.bind(this)的尴尬。

![自由选择是否在当前类中对ButterKnife进行初始化](http://upload-images.jianshu.io/upload_images/6098829-670378e001e95c02.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

这样就可以在基类中进行ButterKnife的初始化，不必要每个类中都要初始化，对开发框架的搭建更加方便。

* 2)在Android Studio的设置界面，对在当前类中是否强制初始化提供了默认值设置，这样就可以让插件使用更符合自己的操作习惯。

![设置当前类中是否默认为强制初始化](http://upload-images.jianshu.io/upload_images/6098829-6618d55fcb28a70d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

> 2. Android ButterKnife Zelezny 配合ButterKnife实现注解，从此不用写findViewById，想着就爽啊。在Activity，Fragment，Adapter中选中布局xml的资源id自动生成butterknife注解。

    使用方式：在布局右键Generate --> Generate ButterKnife Injections --> 选择要命的名（或者快捷键Ctrl+Shift+B)

![使用Android ButterKnife Zelezny](http://upload-images.jianshu.io/upload_images/6098829-291c1972d01f3a21.gif?imageMogr2/auto-orient/strip)

----

> 3. Remove ButterKnife 把使用ButterKnife的注解快速批量切换成正常findViewbyId

平时使用ButterKnife的困扰：

    1.ButterKnife这个第三方库每次更新之后，绑定view的注解都会改变，从bind,到inject，再到bindview，
    搞得很多人都不敢升级，一旦升级，就会有巨量的代码需要手动修改，非常痛苦

    2.当我们有一些非常棒的代码需要拿到其他项目使用，但是我们发现，那个项目对第三方库的使用是
    有限制的，我们不能使用butterknife，这时候，我们又得从注解改回findviewbyid

    针对上面的两种情况，如果view比较少还好说，如果有几十个view，那么我们一个个的手动删除注解，
    写findviewbyid语句，简直是一场噩梦（别问我为什么知道这是噩梦）
    
    所以，这种有规律又重复简单的工作为什么不能用一个插件来实现呢？于是就有大神写了RemoveButterKnife这个插件帮你解决这些烦恼。

* 使用很简单： 点击菜单栏 Edit → RemoveButterKnife 

![Remove ButterKnife的使用](http://upload-images.jianshu.io/upload_images/6098829-9d985d68448f00fb.gif?imageMogr2/auto-orient/strip)

----

> 4. [eventbus3-intellij-plugin](https://github.com/likfe/eventbus3-intellij-plugin/blob/master/README-zh.md)   EventBus 导航插件,引导 EventBus 的 post 和 event,是在eventbus-intellij-plugin基础上修改的，支持EventBus 3.X，并且修复了原插件eventbus-intellij-plugin的bug，使用起来更方便。

![eventbus3-intellij-plugin 使用.gif](http://upload-images.jianshu.io/upload_images/6098829-290707c6df490d03.gif?imageMogr2/auto-orient/strip)

----

> 5. dagger-intellij-plugin     dagger可视化辅助工具，有了它可以让@Inject对象与创建它的@Provides方法之间有一个很清晰的可视化过程。【具体能不能兼容最新的dagger2，还没研究，博主对这个用的少，有兴趣的小伙伴欢迎去尝试，有结果之后别忘了在博客下面留言告诉我一声，感谢大家。】

![dagger-intellij-plugin 使用图解](http://upload-images.jianshu.io/upload_images/6098829-20733eccf8561c16.gif?imageMogr2/auto-orient/strip)

----

> 6. otto-intellij-plugin       otto事件导航工具

* 从 @Produce 跳转到 @Subscribe 过程

![otto-intellij-plugin使用1](http://upload-images.jianshu.io/upload_images/6098829-e89b58959fe75648.gif?imageMogr2/auto-orient/strip)


* 从 Event 跳转到 @Subscribe

![otto-intellij-plugin使用2](http://upload-images.jianshu.io/upload_images/6098829-0206752956f9015b.gif?imageMogr2/auto-orient/strip)

----

> 7. databinding-support       一个可以快速实现databinding的插件，自从谷歌推出databinding框架以来，有不少人都在使用这个框架开发，一般情况下在xml里面手写一些代码很麻烦，有了这个插件就要方便很多了，并且可以快速跳转到具体类。

**快捷键：alt + enter**

具体功能如下所示：

* 双击根布局，按alt + enter，选择 Convert to databinding layout ，布局就被包裹在<layout></layout> 标签里面
![databinding-support plugin1.gif](http://upload-images.jianshu.io/upload_images/6098829-70a672f5993d7c42.gif?imageMogr2/auto-orient/strip)

* 鼠标放在命名空间上，按alt + enter，选择Add <data> tag, 即：添加<data></data>标记
![databinding-support plugin2.gif](http://upload-images.jianshu.io/upload_images/6098829-20aba81c15170144.gif?imageMogr2/auto-orient/strip)

* 双击一个属性值，按alt + enter，右键选择Wrap with@{} , 即：包裹在@{}里面
![databinding-support plugin3.gif](http://upload-images.jianshu.io/upload_images/6098829-0481ebb14cb4c8c5.gif?imageMogr2/auto-orient/strip)

* 双击一个属性值，按alt + enter，右键选择Wrap with@={} , 即：包裹在@{}里面
![databinding-support plugin4.gif](http://upload-images.jianshu.io/upload_images/6098829-685c15978aa65254.gif?imageMogr2/auto-orient/strip)

* 双击一个属性值，按alt + enter，选择 Switch to...，在 @{}   和 @={} 之间切换(字母太多，不打了，选择最后一个就是的，具体的请看图)，
![databinding-support plugin5gif.gif](http://upload-images.jianshu.io/upload_images/6098829-aef0fc3c4b6e5372.gif?imageMogr2/auto-orient/strip)


* 在 <data> 标签里面，按alt + enter，右键选择Add <import> tag，就可以添加 <import> 标签
![databinding-support plugin6.gif](http://upload-images.jianshu.io/upload_images/6098829-f3408ad7634ba79d.gif?imageMogr2/auto-orient/strip)


* 在 <data> 标签里面，按alt + enter，右键选择Add <variable> tag，就可以添加 <variable> 标签
![databinding-support plugin7.gif](http://upload-images.jianshu.io/upload_images/6098829-4f96c921da5a9742.gif?imageMogr2/auto-orient/strip)

* 从类跳转到layout布局，这个很通用，一看就知道。
![databinding-support plugin8.gif](http://upload-images.jianshu.io/upload_images/6098829-d19059e22c78316e.gif?imageMogr2/auto-orient/strip)

##### 八、代码补全工具：

> 1. Android Postfix Completion 可根据后缀快速完成代码，这个插件在Android Studio原有的基础上增添了一些新的功能 。

* github地址：https://github.com/takahirom/android-postfix-plugin
* JetBrains plugin地址：https://plugins.jetbrains.com/plugin/7775-android-postfix-completion

         有这些语句可以操作：  .toast .log .logd .find .isemp .vg .vsb 
            .invsb  .gone  .snack   .snackaction

* 部分示例图如下：

![Android Postfix Completion  使用](http://upload-images.jianshu.io/upload_images/6098829-4ae6e9a077273c22.gif?imageMogr2/auto-orient/strip)

----

> 2. Gradle Dependencies And Plugins Helper    gradle依赖支持自动补全

    1. gradle依赖支持自动补全，
    2. 默认使用jcenter API搜索dependencies，使用Gradle Plugins搜索plugins，
    3. 可选使用Nexus API搜索或使用Maven Index本地搜索加速，
    4. 支持Gradle groovy脚本（.build）及kotlin脚本（.build.kts）。

*示例图：

![Gradle Dependencies And Plugins Helper 使用](http://upload-images.jianshu.io/upload_images/6098829-cc1650795c09de9c.gif?imageMogr2/auto-orient/strip)

* jetbrains下载地址：https://plugins.jetbrains.com/plugin/10033-gradle-dependencies-and-plugins-helper
* github地址：https://github.com/bestwu/gradle-dependencies-plugins-helper-plugin
* 中文文档：http://bestwu.cn/2017/09/01/gradle-dependencies-plugins-helper-plugin/

-----

> 3. [.ignore](https://plugins.jetbrains.com/plugin/7495--ignore)

* 过滤掉一些不想提交的文件，把相应的过滤文件名（或路径）添加到.gitignore 中；根据不同的语言来选择模板；而且还有自动补全功能。（它是Android Studio自带的.gitignore功能的增强和扩展）

![ignore 使用1](http://upload-images.jianshu.io/upload_images/6098829-bfec75cc8e093290.gif?imageMogr2/auto-orient/strip)

![ignore 使用2.gif](http://upload-images.jianshu.io/upload_images/6098829-2e122738ae41ac4d.gif?imageMogr2/auto-orient/strip)

![ignore 使用3.gif](http://upload-images.jianshu.io/upload_images/6098829-41e2110d56695dcf.gif?imageMogr2/auto-orient/strip)

----

##### 九、辅助工具

> 1. CodeGlance 
* 安装这个插件就可以在右边可以预览代码，布局，文件等，还可以实现快速定位，可以左右拖动设置预览边界大小。只要是文件，都可以快速预览。比自带的那个滚动条方便多了。（有点类似sublime的那个预览效果）
 
![CodeGlance 使用](http://upload-images.jianshu.io/upload_images/6098829-a399fc13606d4ca1.gif?imageMogr2/auto-orient/strip)

----
> 2. [IconViewer](https://github.com/davidsommer/IconViewer)
图标预览插件，在浏览目录结构时，打开带图片的目录，图片前面会显示预览图。

* 示范图：

![IconViewer使用](http://upload-images.jianshu.io/upload_images/6098829-f9c4dc4a83fd1149.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----
> 3. GsonFormat   快速生成json实体类的插件

* GsonFormat的好处：快速将json字符串转换成一个Java Bean，免去我们根据json字符串手写对应Java Bean的过程.


    方式1 ：快捷键：点击菜单栏的 Code --> Generate --> GsonFormat 或者按 Alt + Insert 键

![GsonFormat使用方式](http://upload-images.jianshu.io/upload_images/6098829-7f2e120974181c7c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

    方式2： 写一个Javabean 右键 Generate -->GsonFormat ，把json数据粘贴进来 可以修改字段，
    可以选择是否public, 可以修改字段名等，最后点OK 搞定

* 具体用法请看演示图：

![GsonFormat使用方式](http://upload-images.jianshu.io/upload_images/6098829-156fc1ef5b706c66.gif?imageMogr2/auto-orient/strip)
 
----
> 4. JsonToKotlinClass 能将 Json 数据直接映射生成 Kotlin Data Class 代码,免去手动编写数据对象结构声明


![JsonToKotlinClass 使用](http://upload-images.jianshu.io/upload_images/6098829-28add4b677d10962.gif?imageMogr2/auto-orient/strip) 在github也只有找到文字介绍，点击Tools菜单

----
> 5. android-studio-proteus-plugin 将xml转化为json（这个貌似在Android Studio搜索插件找不到，只能去github下载jar包，然后安装到Android Studio上。[下载地址](https://github.com/flipkart-incubator/android-studio-proteus-plugin)）github也只有简单的文字介绍，没有图片说明，我也尝试过，没找到生成的json在哪里。貌似自定义的xml不生效。有兴趣研究的可以去github看看怎么操作，学会了之后别忘了在博客下面留言。

    1.打开一个XML资源文件
    2.点击菜单栏Tools  → Proteus  → XML to JSON

----

> 6. Lifecycle Sorter 可以根据Activity或者fragment的生命周期对其生命周期方法位置进行先后排序。
* 用法： 光标放在Activity里面，然后点击菜单栏Code  → Sort Lifecycle Methods，然后有两种选择，一种是排放在类的前面（如果有很多方法，生命周期方法优先放前面，其他方法放后面），Place at Start of Class（快捷键 Ctrl + alt + K）；另一种是排放在类的后面（与前者相反），Place at End of Class（快捷键 Ctrl + Shift + alt + K）

* 使用示意图如下：

![Lifecycle Sorter使用前后对比](http://upload-images.jianshu.io/upload_images/6098829-b90658e18294a9ad.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----
> 7. Android Methods Count 统计第三方依赖库的方法数。

打开项目module里面的build.gradle，发现里面行号后面多了几个小蓝色圆圈，鼠标放上面就会显示方法数信息。你会发现依赖库变成了灰色，后面中括号里面就是方法数以及相关依赖信息等，点一下就显示正常的依赖内容
【缺点】项目里面的modle依赖了一个自己写的lib,不能统计lib里的方法数

![Android Methods Count 使用](http://upload-images.jianshu.io/upload_images/6098829-4987e38224a5cf92.gif?imageMogr2/auto-orient/strip)
----
> 8. [dexcount-gradle-plugin](https://github.com/KeepSafe/dexcount-gradle-plugin) 统计方法数
----
> 9. Android-Resource-Usage-Count 显示每个资源文件的引用次数

![ Android-Resource-Usage-Count 使用](http://upload-images.jianshu.io/upload_images/6098829-d86cb0b4a15a346d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
----
> 10. Statistic 统计代码行数

首次安装在AS的View→Tool Windows→Statistic，选择之后会在AS的左下角出现statistic按钮:

![Statistic在Android Studio面板的位置](http://upload-images.jianshu.io/upload_images/6098829-9f16543a44fb9265.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

一开始里面的内容是空白的，我们点击Refresh,如果还是空白，就点击Settings来添加需要统计行数的项目。

![初次打开时的显示](http://upload-images.jianshu.io/upload_images/6098829-d61dfdbaabdba831.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

点击Settings后，会出现设置窗口，点击add,添加要统计代码的项目就可以了。

![进入设置页面](http://upload-images.jianshu.io/upload_images/6098829-85f0f3d9103382ff.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

**这里重点讲一下设置里面每一项的意思：**

![每一项设置的具体讲解](http://upload-images.jianshu.io/upload_images/6098829-aaf9c3cf1f8ef9ac.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

**最后效果如下图所示，这里的4张图表示的是4个不同的操作步骤:**

![操作步骤1](http://upload-images.jianshu.io/upload_images/6098829-493e0e9c56200156.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![操作步骤2](http://upload-images.jianshu.io/upload_images/6098829-5710920e49b5db3e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![操作步骤3](http://upload-images.jianshu.io/upload_images/6098829-2e56ae21f35205f0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![操作步骤4](http://upload-images.jianshu.io/upload_images/6098829-8c3165f930a7e998.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----
> 11. SingletonTest 快速生成单例模式的预设，单例的六种生成方式:LazyUnSafe,LazySafe,Hungry,DoubleCheck,StaticInner,Enum。（有个bug: 类名不输入也会生成一个类。）
 
* 用法：鼠标点击要生成类的包名，右键 New → SingletonGenerate,然后有一个弹窗，填写类名，选择要生成的类型，点击OK，就生成了。（一般这个插件我很少用，我自定义的一个快捷键live template，自动生成单例代码的。）

*示意图如下：

![SingletonTest 使用](http://upload-images.jianshu.io/upload_images/6098829-a40c8020ddb5bb3e.gif?imageMogr2/auto-orient/strip)

----
> 12. [TemplateBuilder](https://puke3615.github.io/2017/03/06/TemplateBuilder%5BChinese%5D/)
TemplateBuilder是一款能够帮助我们快速生成Android Studio Template的Android Studio插件，将通过逐个文件去配置模板的方式改进为通过插件来实现，对于简单的模板制作，只需要一键即可生成。

* 导出模板
![导出模板](http://upload-images.jianshu.io/upload_images/6098829-a35005da029792c2.gif?imageMogr2/auto-orient/strip)

* 导入模板
![导入模板](http://upload-images.jianshu.io/upload_images/6098829-98b32e48412ac97e.gif?imageMogr2/auto-orient/strip)

----

>13. [Markdown Navigator](https://plugins.jetbrains.com/plugin/7896-markdown-navigator)

* Markdown Navigator  是一个能在IDE编辑markdown语法的插件，全面支持markdown语法，是目前IDE上最好用的Markdown插件。可以实时预览，拖放文件和图像以快速链接形式插入，支持导航和查找功能，将HTML粘贴到Markdown文档中自动转换为Markdown，可以导出为HTML或PDF分享给别人。

* 下面几张图是来源于该插件在jetbrains发布的简介图：

![实时预览](http://upload-images.jianshu.io/upload_images/6098829-fa50d30b4546a6ec.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![支持自定义](http://upload-images.jianshu.io/upload_images/6098829-feec40da477ce31d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![设置语法规则](http://upload-images.jianshu.io/upload_images/6098829-08c5ffd5c9ce4454.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

>14. [idea-markdown](https://github.com/nicoulaj/idea-markdown)

* 这个插件3年前已经停止维护，它已经从Jetbrains插件库中删除。 Jetbrains正式支持Markdown插件。

* 来一张github上关于这个插件的截图：

![idea-markdown 使用](http://upload-images.jianshu.io/upload_images/6098829-c1048de67946dd9d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

> 15. [instapk-studio-plugin](https://github.com/PytenLabs/instapk-studio-plugin)
分享apk文件

* 示例图：

![instapk-studio-plugin使用](http://upload-images.jianshu.io/upload_images/6098829-0a4bde5ea9ad1c4a.gif?imageMogr2/auto-orient/strip)

----

##### 十、UI优化有关：

> 1. [TinyPic](https://github.com/shenjiajun53/TinyPic)
功能：压缩图片资源，一次最多压缩500张 压缩的核心功能是 [TinyPng](https://tinypng.com/) 这个网站提供的。但是这个网站一次只能上传20张图片，所以你需要上传下载，上传下载重复工作。 好在这个网站提供了api可以压缩图片。

* 使用说明：在开发者页面下申请api key。对于一个key，每月有500次的免费压缩额度，如果压缩超过了 500张图片，就不能使用了。需要另外付费。但是申请这个api特别简单，填下邮箱，用户名就行，多申请 两个邮箱。1000张图片也妥妥够了。 这里推荐google个十分钟邮箱，不需要注册，只能使用十分钟，用来收一下验证码很方便。

* 使用步骤：


    1.Tools目录下找到TinyPic

![Tools目录下找到TinyPic](http://upload-images.jianshu.io/upload_images/6098829-478fba94f22d0ced.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

    2.输入在 https://tinypng.com/developers 申请的api key

![输入api key](http://upload-images.jianshu.io/upload_images/6098829-ddc17f3a4a007c47.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

    3..选择图片，可以选择图片，或者选择文件夹或者同时选中，反正是遍历文件夹下的图片，筛选jpg和png ，key的剩余次数

![选择图片](http://upload-images.jianshu.io/upload_images/6098829-9d45901f5f6cc479.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

    4.查看压缩进度

![查看压缩进度](http://upload-images.jianshu.io/upload_images/6098829-57e61c82bd055cb0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

    5.超过500次的提示

![超过500次的提示](http://upload-images.jianshu.io/upload_images/6098829-d2ee9e14621cc470.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

> 2. lint-cleaner-plugin 删除未使用的资源,包括String字符串,颜色和尺寸。 这是一个Gradle插件，所以如何配置可以去github的源码上看。
  插件源码地址：https://github.com/marcoRS/lint-cleaner-plugin

----

> 3. folding-plugin
* 布局文件分组的插件，该插件可自动将前缀相同的文件归类显示到同一文件目录下，但不会因此而移动文件或创建文件夹。

演示图如下：

![folding-plugin 使用效果图](http://upload-images.jianshu.io/upload_images/6098829-0ff68031ea3a1f5e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

##### 十一、Android Studio主题相关：

> 1.[Material Theme UI](https://plugins.jetbrains.com/plugin/8006-material-theme-ui)      添加Material主题到你的Android Studio

* 示意图：

![Material Theme UI 示意图](http://upload-images.jianshu.io/upload_images/6098829-f892c57eb4310bf8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



----

> 2.Android Studio插件之sexy editor （设置AS代码编辑区的背景图）

* 进入设置界面 选择other Setting 下的Sexy Editor ， 右侧 insert 一张或多张图片即可，上面的其他设置可以设置方位 间隔时间 透明度等等，设置完成后，要关闭打开的文件，重新打开项目文件即可在代码编辑区显示插入的图片，作为代码编辑区的背景图。

![sexy editor 使用](http://upload-images.jianshu.io/upload_images/6098829-8b13911bb3f017eb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

##### 十二、UML工具有关

> 1. [Code Iris](https://plugins.jetbrains.com/plugin/7324-code-iris)
快速分析布局以及代码包结构关系，并生成UML图

* 用法：选择module → 右键 → Create Code graph，然后右面工具栏会出现Code iris窗口，放大，点击窗口左下角图标可以选择要生成uml的包，下方有个滑动条，可以设置按包、类生成uml，并且有保存。

* 示意图：

![Code Iris用法](http://upload-images.jianshu.io/upload_images/6098829-228e78a2956d91f0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

>2. [SimpleUML](https://github.com/Jerey-Jobs/SimpleUML)
详情请点击 https://github.com/Jerey-Jobs/SimpleUML

----

##### 十三、打包、加固、混淆、Gradle编译、搜索代码有关：

> 1. [AndroidProguardPlugin](https://github.com/zhonghanwen/AndroidProguardPlugin)

* 一键生成项目混淆代码插件(不过目前可能有些第三方项目的混淆还未添加完全)

![AndroidProguardPlugin 使用.gif](http://upload-images.jianshu.io/upload_images/6098829-2ee8d200395f3ea5.gif?imageMogr2/auto-orient/strip)

----

> 2. [ApkMultiChannelPlugin](https://github.com/nukc/ApkMultiChannelPlugin)
这是一个为了方便 Android 多渠道打包的 Android Studio / IDEA 插件

**使用方式:**
* 1). 选择一个 apk 然后右键，点击 Build MultiChannel

![开始使用](//upload-images.jianshu.io/upload_images/1621204-981415732170a38a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

* 2). 配置签名信息，打包方式和渠道等

![配置签名信息，打包方式和渠道等](//upload-images.jianshu.io/upload_images/1621204-e2077bf84e75fc7a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

配置说明：
Key Store Path: 签名文件的路径
Key Store Password: 签名文件的密码
Key Alias: 密钥别名
Key Password: 密钥密码
Zipalign Path: zipalign文件的路径（用于优化 apk；zipalign 可以确保所有未压缩的数据均是以相对于文件开始部分的特定字节对齐开始，这样可减少应用消耗的 RAM 量。）
Signer Version: 选择签名版本：apksigner 和 jarsigner
Build Type: 打包方式
Channels: 渠道列表，每行一个，最前面可加 > 或不加（保存信息的时候，程序会自行加上）

* 3). 开始打包
配置完成之后按 OK 就会开始进行渠道打包，文件会输出在选中的apk的当前目录下的channels目录中

![开始打包](//upload-images.jianshu.io/upload_images/1621204-8b3205e5c8f7e419.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

>3. [Codota](http://www.codota.com/)
搜索最好的Android代码。(Studio插件库搜索里面Codota直接下载)。它的搜索源，不仅只有Github，而且还有知名博客和开发者网站，让你搜索一个东西，不用在找上半天。

 Codota官方介绍：

    最好的代码实例，我们的抓取工具从大量的代码项目中抓取了大量的代码模式，你可以从这里搜索超过七百万精品代码实例。

* 使用示例图：

![Codota使用示例图](http://upload-images.jianshu.io/upload_images/6098829-ea0ada1604ff9f47.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

> 4. [intellij-java2smali](https://github.com/ollide/intellij-java2smali)
将Java & Kotlin编译成smali

* 使用很简单：点击菜单栏Build → 然后点击 Compile to smali，OK了。

* 示例图：

![intellij-java2smali示例图](http://upload-images.jianshu.io/upload_images/6098829-37d387fdc2dd764a.gif?imageMogr2/auto-orient/strip)

----

> 5. [gradle-cleaner-intellij-plugin](https://github.com/Softwee/gradle-cleaner-intellij-plugin)
强制清除延迟，不再需要Gradle任务。

* 使用很简单，点击菜单栏的那个gradle的logo就可以了。

![gradle-cleaner-intellij-plugin使用](http://upload-images.jianshu.io/upload_images/6098829-61c47deb35b48f9e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

> 6. [freeline](https://github.com/alibaba/freeline)
Freeline 是 Android 平台上的秒级编译方案，Instant Run 的替代品
 
* 用法和很简单：点击导航栏的那个蓝底白色双折线圆形图标，就可以了。编译速度比Android Studio自带Instant Run快很多。

![Freeline 用法](http://upload-images.jianshu.io/upload_images/6098829-aebfeb5770619428.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

##### 十四、检测、Code Review、测试和调试相关：

> 1. LeakCanary 帮助你在开发阶段方便的检测出内存泄露的问题，使用起来更简单方便。

* LeakCanary中文使用说明请参考：https://www.liaohuqiu.net/cn/posts/leak-canary-read-me/

![ LeakCanary 检测结果示例图](http://upload-images.jianshu.io/upload_images/6098829-ae446c56a9a9d16c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

> 2. [JVM Debugger Memory View](https://blog.jetbrains.com/idea/2016/08/jvm-debugger-memory-view-for-intellij-idea/)
Android Studio和IDEA中一个很有用的内存调试插件，对检测内存泄漏很有帮助。

* 详细可参考[说一说Android Studio和IDEA中一个很有用的内存调试插件](https://zhuanlan.zhihu.com/p/25110433)一文。

* 示意图：

![示意图](http://upload-images.jianshu.io/upload_images/6098829-d4ceb98351272ac1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![示意图2](http://upload-images.jianshu.io/upload_images/6098829-78eff1d02f25d347.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

> 3. [reVu](https://plugins.jetbrains.com/plugin/3849-revu)

* 代码review神器，这个插件比较轻量，review记录保存在xml文件中，直接提交到git。这个插件比reviewclipse功能要好一些，使用很方便，比较轻，可以review任何文本文件，实现10以下的小团队用。

* 使用截图如下：

![ reVu使用截图](http://upload-images.jianshu.io/upload_images/6098829-4e6a64e94017fdce.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

> 4. [findBugs-IDEA](https://plugins.jetbrains.com/plugin/3847-findbugs-idea)

* 帮你一起找bug的一个插件,很老的一个插件了，具体的没用过。因为Android Studio也提供了代码审查的功能，点击菜单栏的Analyze → Inspect Code。

* 使用图解：

![查找](http://upload-images.jianshu.io/upload_images/6098829-28e758571c73185e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![查找结果](http://upload-images.jianshu.io/upload_images/6098829-a6d3a0bcf7ee38d2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

> 5. [CheckStyle-IDEA](https://plugins.jetbrains.com/plugin/1065-checkstyle-idea)（49M，有点大）

*  检查代码风格的插件，比如像命名约定，Javadoc，类设计等方面进行代码规范和风格的检查，你们可以遵从像Google Oracle 的Java 代码指南 ，当然也可以按照自己的规则来设置配置文件，从而有效约束你自己更好地遵循代码编写规范。

* 【tips】Android Studio自带有一个分析工具，点击菜单Analyze,里面有很多分析工具，比如Inspect Code这个功能就比CheckStyle强大很多。貌似一次只能打开一个类去分析。

![CheckStyle-IDEA用法](http://upload-images.jianshu.io/upload_images/6098829-c38243424c20baed.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

> 6. [JSONOnlineViewer](https://plugins.jetbrains.com/plugin/7838-jsononlineviewer)

* 可实现直接在android studio中调试接口数据，可以选择请求类型，自定义请求头及请求体，json数据格式化后展示（2015年最后一次更新，2年没更新了，不推荐使用）。 

* 借用JSONOnlineViewer官方介绍的截图：

![使用截图](http://upload-images.jianshu.io/upload_images/6098829-9dc6744c0713d114.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![使用介绍](http://upload-images.jianshu.io/upload_images/6098829-68e207afd89d96d9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

> 7. [ADB WIFI](https://plugins.jetbrains.com/plugin/7856-adb-wifi) 无需root就能wifi调试

![ADB WIFI 首次使用要按图说的那样连接](http://upload-images.jianshu.io/upload_images/6098829-d801dba5d996682f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![ADB WIFI 以后启动就不需要设置了，直接点击快捷菜单那个机器人就OK了](http://upload-images.jianshu.io/upload_images/6098829-31bb89c25efac081.gif?imageMogr2/auto-orient/strip)

![在右侧面板可以设置连接控制](http://upload-images.jianshu.io/upload_images/6098829-8d8b9199f2c8ad24.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

> 8. [adb-idea](https://plugins.jetbrains.com/plugin/7380-adb-idea) 可以一键清理缓存并重启APP

![搜索 adb-idea](http://upload-images.jianshu.io/upload_images/6098829-5f00f6a47479ad7b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![adb-idea 使用](http://upload-images.jianshu.io/upload_images/6098829-ad3a9f569de56450.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

> 9. [SQL Scout (SQLite Support)](https://plugins.jetbrains.com/plugin/8322-sqlscout-sqlite-support-)

* 在 Android Studio 上调试数据库 ( SQLite )
* 详细使用参考：[在 Android Studio 上调试数据库 ( SQLite )](https://juejin.im/post/58e0d781a0bb9f0069ec08d3)
* 使用示意图：

![SQL Scout 使用](http://upload-images.jianshu.io/upload_images/6098829-d87f38b316a70f3c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

> 10. [Robotium Recorder](https://plugins.jetbrains.com/plugin/7513-robotium-recorder)  

* 一个自动化测试框架，用于测试在模拟器和Android设备上原生的和混合的移动应用程序。Robotium Recorder可以让你记录测试案例和用户操作。你也可以查看不同Android活动时的系统功能和用户测试场景。（貌似现在是收费的，这个没用过，有兴趣朋友可以写一下心得体会，欢迎留言）

* 具体文档请查看：[Robotium Recorder文档](https://github.com/robotiumtech/robotium)

一一一一一一一一一一一一一一一一一一一一一一一一一一一一一一一




