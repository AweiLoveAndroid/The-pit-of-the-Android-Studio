# [老卢独家整理] Android studio使用时遇到的问题

----

> **大体上分为以下几个方面的内容：**

	1）关于sdk  点击此处链接: 1
	
	2）关于jdk  点击此处链接: 8、9、27、 28、 29
	
	3）关于加速器（Intel HAXM）   点击此处链接： 2、3、  4、 5、 6
	
	4）关于gradle  点击此处链接：10、 16、 20、 24、 26
	
	5）关于混淆打包  点击此处链接：11
	
	6）关于依赖库和插件  点击此处链接：3、 7、 12、 13、 14、 19、 23
	
	7）关于配置和源码关联  点击此处链接：15、 17、 21、 22、 25
	
	8）关于模拟器  点击此处链接：18


### 1. Android Studio第一次启动时出现 unable to access android sdk add-on list

 ![Android遇到的问题1对应的图片](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Android%E9%81%87%E5%88%B0%E7%9A%84%E9%97%AE%E9%A2%981%E5%AF%B9%E5%BA%94%E7%9A%84%E5%9B%BE%E7%89%87.png?raw=true)

  > 出现原因:电脑没有sdk,studio也没有自带sdk;

    解决办法:在安装studio的目录下找到bin\idea.properties,打开这个文件,在末尾加上一行
      disable.android.first.run=true就行了,如果打不开这个文件就用editplus或者sublime text打开

### 2. 在安装了新的 Android Studio 之后，AVD 新建并启动模拟器的时候报以下错误：emulator:ERROR:x86 emulation currently requires hardware acceleration!                         Please ensure Intel HAXM is properly installed and usable.                                 CPU acceleration status: HAX kernel module is not installed!

  > 出现原因:原来新的 Android SDK 在运行虚拟机的时候，需要安装 Intel HAXM：一个硬件加速器，为的是在x86平台上加快安卓虚拟机的运行。

    解决方法:
    (1) 在安装之前首先到 SDK 的安装目录下打开SDK Manager：找到 Inter....(中间的很多单词就不写了,重点看到 Inter 和 HAXM 就可以了点击下载) 
    HAXM 点击install
    (2) 然后进入到你SDK的目录下，再进入extras —> intel —> Hardware_Accelerated_Execution_Manager，可以看到HAXM的安装文件：interhaxm-android.exe
    (3) 但是在安装之前还有一个步骤，就是重启计算机，进入开机界面前按F2进入到计算机的BIOS下，切换到 Configuration 找到下面的 Intel Virtual Technology
    设置为Enable状态（即允许虚拟机技术）然后再双击interhaxm-android.exe安装,一直next就可以了

### 3. Android Studio首次创建项目时卡住，如图所示：

 ![Android遇到的问题3对应的图片](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Android%E9%81%87%E5%88%B0%E7%9A%84%E9%97%AE%E9%A2%983%E5%AF%B9%E5%BA%94%E7%9A%84%E5%9B%BE%E7%89%87.png?raw=true)

  > 解决办法：打开Android Studio安装目录下的 bin 目录,找到 idea.properties 文件,在文件最后追加以下这行代码:

    disable.android.first.run=true


###  4. Intel 加速器 HAXM  ，安装过程中可以会出现如下错误:
    "Failed to configure driver: unknown error. Failed to open driver" 
    
    有以下几个步骤可以解决该问题：
    (1) 下载haxm_extra_workaround.zip 附件
    (2) 解压后提取hax_extract.cmd 文件到 HAXM 的解压文件路径中
    (3) hax_extract.cmd 右键用管理员权限运行。
    执行以上步骤后，基本可以解决以上提示的安装异常问题。


### 5. 因为电脑卡死,结束了qemu-system-i386.exe这个倒霉的进程,导致我开启模拟器的时候一直提示我没有安装Intel HAXM,只好再安装一遍，然后出现了以下问题:                                 This computer meets the requirements for HAXM,but IntelVirtualization Technology(VT-x) is not turned on.                                                                            HAXM can be installed,but will not work until VT-x is enabled.                           Please refer to the Inter HAXM documentation for more infomation.


    解决办法:"Inter Virtual Technology"先设置Disable，启动系统。再重启，"Inter Virtual Technology"设置为Enable


### 6. 关于intelhaxm-android.exe安装的坑:不管是双击还是右键以管理员身份运行都没用，怎么解决？

    解决办法:
    在SDK\extras\intel\Hardware_Accelerated_Execution_Manager中找到intelhaxm-android.exe，右键解压,双击setup.exe安装就好了



###  7. Failed to resolve: junit:junit:4.12

  > 出现原因：项目中引用了junit库中的代码，但是却没有相关的junit的依赖库


    解决办法：添加相关的依赖库引用,在项目的Module的build.gradle中添加如下代码就OK了
    repositories {
        maven { url 'http://repo1.maven.org/maven2' }
    	}


### 8. 只要是API24以上的Android Studio，如果JDK低于1.8都会出现这个问题，比如我列举两个:

>（1）Error:Execution failed for task':app:compileOrangeDevDebugJavaWithJavac'.compileSdkVersion 'android-24' requires JDK 1.8 or later to compile.

>（2）Android N requires the IDE to be running with Java 1.8 or later

    解决办法:把1.8以前的jdk都卸载掉,然后把环境变量配置成1.8的,就可以了.


###  9. Error:(1, 1) A problem occurred evaluating project ':app'. com/android/jack/api/ConfigNotSupportedException :
	Unsupported major.minor version 52.0
	
	解决办法:（1）把1.8以前的jdk都卸载掉，使用1.8版本的jdk
	      （2）File - Project Structure - SDK Location - JDK location，这里面有个选项，
		  可以选择"use embedded JDK(recommended)"，使用AS内置的JDK。（不推荐这样做）


###  10. Unknown host 'downloads.gradle.org' 这个问题的解决:
使用android studio的gradle新建项目时候出现:Error:Unknown host 'downloads.gradle.org'.Enable Gradle 'offline mode' and sync project.Learn about configuring HTTP proxies in Gradle

>解决办法:请查看本文件夹里面的 **[Unknown host 'downloads.gradle.org'问题的解决.html](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/doc/Unknown%20host%20'downloads.gradle.org'%E9%97%AE%E9%A2%98%E7%9A%84%E8%A7%A3%E5%86%B3.html)**


### 11. 关于混淆出现的问题：
(详细请看 http://www.open-open.com/lib/view/open1490252413493.html)

> ★★★★ 问题一：出现 Unknown verification type [95] in stack map frame  错误
	Error:Execution failed for task
 ‘:app:transformClassesWithMultidexlistForNiannianDebug’.Java .io.IOException: 
	Can’t read [
E:SVNbroondontrunkcodebroodon_androidappbuildintermediatestransformsjarMergingnianniandebugjars11fcombined.jar] 
	(Can’t process class [com/tencent/wxop/stat/al.class] (Unknown verification type [95] in stack map frame))

> 原因分析：引用的第三方库已经混淆过，再在本地进行编译混淆的时候就会报出这个错误。

    解决办法: 则修改混淆器，重新进行编译，将新的混淆器覆盖原来的混淆器，则可以解决。

> ★★★★ 问题二：
	Error:Execution failed for task ‘:app:transformClassesWithMultidexlistForNiannianDebug’.
	proguard.KeepClassSpecification.(ZZZZZZLproguard/ClassSpecification;)V

> 原因分析：升级 Android studio 以后，使用的混淆器版本不一致

    解决办法: 根据 Android studio版本选择与之对应的混淆器版本

### 12. 这是什么原因？是因为65535问题？还是因为v7包重复了？ 【待解决。。。】
  Error:Execution failed for task ':app:transformClassesWithDexForDebug'.
  > com.android.build.api.transform.TransformException: java.lang.RuntimeException: 
  java.lang.RuntimeException: com.android.ide.common.process.ProcessException:java.util.concurrent.ExecutionException: 
  com.android.ide.common.process.ProcessException: Return code 1 for dex process

### 13. non-zero exit value 1； 和 non-zero exit value 2； 和 non-zero exit value 3 问题的解决：
	Error:Execution failed for task ':app:transformClassesWithDexForDebug'
	com.Android.build.api.transform.TransformException: 
	com.android.ide.common.process.ProcessException: 
	org.gradle.process.internal.ExecException:Process 'command 'F:\Program Files (x86)
	 \Java\jdk1.8.0_31\bin\java.exe'' finished with non-zero exit value 1

> ★★★★ 问题一： non-zero exit value 1原因分析：

> 原因分析：这个是因为依赖包重复了 （像v4和nineoldandroids），app中实现了对easeUI的依赖，但是app和easeUI都添加了对v4这个包的依赖。

    解决办法:
        把v4包注释修改之后，clean，rebuild一下，OK


> ★★★★ 问题二： non-zero exit value 2

    解决办法:
        这个错误在app的build.gradle里面添加下面这句就好了。
    	android {
    	   
    	    defaultConfig {
    	        ...
    	        multiDexEnabled true
    	    }
    
    	}

> ★★★★ 问题三： non-zero exit value 3

    解决办法:
       这个错误就在app的bulid.gradle里面加上这句，再rebuild ,之后再运行就行了。4g可以看电脑配置修改（2g,3g,6g,8g）。
    	dexOptions {
    	    javaMaxHeapSize "4g"
    	}

### 14. 打开Android Studio报错 

Plugin Error: required plugin “Android Support” is disabled

	更详细的错误信息如下：
	Problems found loading plugins:
	Plugin "Google Analytics Uploader" was not loaded: required plugin "Android Support" is disabled.
	Plugin "SDK Updater" was not loaded: required plugin "Android Support" is disabled.
	Plugin "Android NDK Support" was not loaded: required plugin "Android Support" is disabled.
	Plugin "Google App Indexing" was not loaded: required plugin "Android Support" is disabled.
	Plugin "Google Cloud Tools For Android Studio" was not loaded: required plugin "Android Support" is disabled.
	Plugin "Google Cloud Testing" was not loaded: required plugin "Android Support" is disabled.
	Plugin "Google Services" was not loaded: required plugin "Android Support" is disabled.

>解决办法:

	  打开File-Settings-Plugins，把报红色的插件全部取消勾选，在把Android Support勾选，然后Apply-Save，重启下studio 就可以了。


### 15. 自定义android studio的配置文件目录后，无法正常安装和卸载插件(貌似2.0版本之后的插件安装卸载就有问题了)是何原因？详情看知乎 [https://www.zhihu.com/question/38604486](https://www.zhihu.com/question/38604486)

> 解决方法:

	方法(1)：将idea.system.path/plugins下的文件移动到{idea.config.path}/plugins下（如果是压缩包，则需要先解压）。 
	  然后重启一下AS就可以了。删除也是，貌似也得手动去文件夹下删除）
	
	方法(2):修改AS安装目录下的idea.properties文件：
	  idea.config.path=D:/.AndroidStudio2.0/config 
	  idea.system.path=D:/.AndroidStudio2.0/system 
	  idea.plugins.path=${idea.system.path}/plugins

### 16. 导入android studio项目，出现的问题：

> Error:Failed to open zip file.
> 
Gradle's dependency cache may be corrupt (this sometimes occurs after a network connection timeout.)
> 
Re-download dependencies and sync project (requires network)
> 
Re-download dependencies and sync project (requires network)

![Android遇到的问题16对应的图片1](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Android%E9%81%87%E5%88%B0%E7%9A%84%E9%97%AE%E9%A2%9816%E5%AF%B9%E5%BA%94%E7%9A%84%E5%9B%BE%E7%89%871.png?raw=true)

这个错误提示意思是：Gradle's dependency cache may be corrupt：（Gradle的依赖缓存可能是损坏的。）

* 原因分析：我们要导入别人写好的工程时，一般不需要更改什么，as智能判断会提示我们是否需要对build gradle setting之类的文件进行修改。针对gradle个版本工具来说，如果不选择更新直接原来的Gradle Version中的Gradle工具，再加上.gradle库中没用该版本时，as会创建这样的库，有时候这样的库会下载不完整，导致上面的问题。

* 解决办法:

        1.下载 gradle

    下载地址很简单，以 下载gradle-3.5-all.zip为例子。不要去网上找这样那样的网站下载gradle工具了。浏览器输入以下链接快速下载：
    services.gradle.org/distributions/gradle-3.5-all.zip
    
        2.复制替换

    下载完成后替换 C:\Users\Administrator\.gradle\wrapper\dists\gradle-3.3-all\
    exhrs6ca08n232b14ue48lbye中对应的gradle-3.5-all.zip文件。
    正确解压后的的文件如下图所示：

 ![Android遇到的问题16对应的图片2](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Android%E9%81%87%E5%88%B0%E7%9A%84%E9%97%AE%E9%A2%9816%E5%AF%B9%E5%BA%94%E7%9A%84%E5%9B%BE%E7%89%872.png?raw=true)


        3.重新打开项目，对工程中做一些配置如下，重新编译一下，就没问题了:

 ![Android遇到的问题16对应的图片3](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Android%E9%81%87%E5%88%B0%E7%9A%84%E9%97%AE%E9%A2%9816%E5%AF%B9%E5%BA%94%E7%9A%84%E5%9B%BE%E7%89%873.png?raw=true)


### 17. Android studio 源码无法关联，提示Souces for android api 25 platform not found:

    解决方法：
    1）找到jdk.table.xml这个文件
    
    jdk.table.xml文件路径：(以win7为例，Administrator是电脑的用户名，我当前开发工具版本号是Android Studio2.3)
    C:\Users\Administrator\.AndroidStudio2.3\config\options\jdk.table.xml
    
    2）在<sourcePath>节点下添加这一句<root type="simple" url="file://E:/android/sdk/sources/android-25" />
    
    修改后的部分配置文件如下：注意红色方框部分，找到对应的编译版本，再添加对应的源码位置

 ![Android遇到的问题17对应的图片](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Android%E9%81%87%E5%88%B0%E7%9A%84%E9%97%AE%E9%A2%9817%E5%AF%B9%E5%BA%94%E7%9A%84%E5%9B%BE%E7%89%87.png?raw=true)

### 18. com.android.ddmlib.SyncException: No space left on device

    解决方法：
    
    把模拟器里没用的应用或者demo卸载卸载。如果还不行，就重启或者重新创建一个模拟器

### 19. app:transformClassesWithJarMergingForDebug

 ![Android遇到的问题19对应的图片](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Android%E9%81%87%E5%88%B0%E7%9A%84%E9%97%AE%E9%A2%9819%E5%AF%B9%E5%BA%94%E7%9A%84%E5%9B%BE%E7%89%87.png?raw=true)

> 原因：重复依赖导致的.

> 解决办法：

    找到报错的那个提示，看上面报错的是哪个类，双击shift搜索一下，看这个报错的类在哪个依赖库里面用到了。
    在AS中，选择以project显示项目，找到最下面的External Libraries，然后继续找，找到相对应的类库。
    点开之后发现了一个pom.xml，这里面就是关于这个jar的一些配置文件，往下找，发现了一个依赖库的引用，
    复制里面groupId，到你的app的build.gradle里，找到那个依赖，添加{exclude group: 'XXX'} XXX换成刚才复制的groupId，这样就
    把这个groudId的引用去除掉。

### 20. processdebugresources

 ![Android遇到的问题20对应的图片](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Android%E9%81%87%E5%88%B0%E7%9A%84%E9%97%AE%E9%A2%9820%E5%AF%B9%E5%BA%94%E7%9A%84%E5%9B%BE%E7%89%87.png?raw=true)

>原因：build.gradle的兼容包和compileSdkVersion配置不对引起的，关于这个匹配，请查看[Android Studio和gradle版本对照](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/doc/Android%20Studio%E5%92%8Cgradle%E7%89%88%E6%9C%AC%E5%AF%B9%E7%85%A7.md)

>解决办法：让兼容包和compileSdkVersion匹配就OK了

### 21. Android Studio配置androidannotations出现 Error:Execution failed for task ':app:compileDebugJavaWithJavac'

 ![Android遇到的问题21对应的图片](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Android%E9%81%87%E5%88%B0%E7%9A%84%E9%97%AE%E9%A2%9821%E5%AF%B9%E5%BA%94%E7%9A%84%E5%9B%BE%E7%89%87.png?raw=true)

>原因： androidannotations配置环境对SDKtools, Build Tools, Platform Tools 以及 SDK Platform有要求，不匹配的话就会报错

> 解决办法：打开SDK Manager，更新SDKtools, Build Tools, Platform Tools 以及 SDK Platform到最新版本

### 22. Error:com.android.builder.internal.aapt.AaptException: Failed to crunch

 ![Android遇到的问题22对应的图片](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Android%E9%81%87%E5%88%B0%E7%9A%84%E9%97%AE%E9%A2%9822%E5%AF%B9%E5%BA%94%E7%9A%84%E5%9B%BE%E7%89%87.png?raw=true)

> 原因： 项目路径太长，导致有的资源文件整个路径长度超过了240个字符。这是Android Studio的一个坑。

> 解决办法：

    （1）重命名项目名，重新运行一下。
    （2）如果以上方法不行，就缩短路径深度，减少路径层级，每一级路径名字尽可能的缩短。

### 23. Android Studio编辑时发生的错误 `Error:warning: Ignoring InnerClasses attribute for an anonymous inner class`

 ![Android遇到的问题23对应的图片](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Android%E9%81%87%E5%88%B0%E7%9A%84%E9%97%AE%E9%A2%9823%E5%AF%B9%E5%BA%94%E7%9A%84%E5%9B%BE%E7%89%87.png?raw=true)

> 原因：有3种情况可以导致这种错误发生： 

* (1)导了重复jar包，或者导入了不同版本的同名jar包。

* (2)AndroidStudio打签名包时android.keystore 的密码输入错了

* (3)有可能是Dex的方法数超过上限导致的。

> 解决办法：

* (1)把重复的jar包删除掉，Rebuild Project，就OK了，如果，还有其他问题，那证明你的app下的build.gradle依赖配置就有问题。

* (2)重新打包一个正式包，重新输入签名账号密码。

* (3)在项目的build.gradle文件中添加multiDexEnabled true   搞定。

**示例：**

之前是在win7电脑的工程运行在mac电脑，打开就出了这样的错误。解决这个问题的方式，给大家分析一下：

    1.第一考虑是不是可以直接忽略第三方的属性的错误警告.找到项目下对应的proguard-rules.pro文件,在proguard-rules.pro文件中
      添加如下代码
    
    -keepattributes EnclosingMethod
    
    2.查看第三方jar有没有重复利用的，发现并没有。继续下一步。
    
    3.看看是不是Dex越界引起的问题。在项目的build.gradle文件中添加以下代码:
    
    multiDexEnabled true

重新编译之后，项目成功移植了。

### 24. Android Studio版本更新后Gradle版本不匹配问题

> Error:(1, 0) The android gradle plugin version 2.3.0-beta1 is too old, please update to the latest version.
To override this check from the command line please set the ANDROID_DAILY_OVERRIDE environment variable to "xxxxxxx"

问题截图如下：

 ![Android遇到的问题24对应的图片](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Android%E9%81%87%E5%88%B0%E7%9A%84%E9%97%AE%E9%A2%9824%E5%AF%B9%E5%BA%94%E7%9A%84%E5%9B%BE%E7%89%87.png?raw=true)

> 解决办法：升级Gradle到合适版本，具体操作如下：

 【特别说明】Android Studio版本和gradle版本是相匹配的，不是随意匹配的，版本不匹配就会出错。具体的Android Studio和gradle版本对照请看 
 [Android Studio和gradle版本对照](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/doc/Android%20Studio%E5%92%8Cgradle%E7%89%88%E6%9C%AC%E5%AF%B9%E7%85%A7.txt)

* （1）访问 [Gradle官网下载地址](https://services.gradle.org/distributions/) 来下载与之匹配的Gradle版本或者最新的Gradle工具包；

* （2）解压到Android Studio的gradle目录下；

* （3）File->Setting->Build,Exection,Deployment->Gradle->Use local gradle distribution，修改Gradle home为AS安装
  ​    目录下最新的gradle版本；

* （4）修改对应Project的build.gradle中的com.android.tools.build:gradle:版本号为提示版本(如修改classpath 'com.android.tools.build:gradle:2.3.0-beta1'为classpath 'com.android.tools.build:gradle:2.3.0-beta3')；

* （5）修改gradle-wrapper.properties中distributionUrl上的版本号与当前Gradle版本号一致(如修改`distributionUrl=https\://services.gradle.org/distributions/gradle-3.2-all.zip`为`distributionUrl=https\://services.gradle.org/distributions/gradle-3.5-all.zip)`；

* （6）重新同步。

图解如下所示：

![Android遇到的问题24解决办法](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Android%E9%81%87%E5%88%B0%E7%9A%84%E9%97%AE%E9%A2%9824%E8%A7%A3%E5%86%B3%E5%8A%9E%E6%B3%95.png?raw=true)


### 25.AppConfig.java文件中文乱码，log也乱码问题的解决。

 ![Android遇到的问题25对应的图片1](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Android%E9%81%87%E5%88%B0%E7%9A%84%E9%97%AE%E9%A2%9825%E5%AF%B9%E5%BA%94%E7%9A%84%E5%9B%BE%E7%89%871.png?raw=true)



> 解决办法：找到对应的module或者lib，打开里面的build.gradle，输入以下代码：

**新版gradle用这个：**

```
tasks.withType(JavaCompile) {
    options.encoding = "UTF-8"
}
```

**旧版gradle用这个：**

```
tasks.withType(JavaCompile) {
     options.encoding = "UTF-8"
}
```

 ![Android遇到的问题25对应的图片2](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Android%E9%81%87%E5%88%B0%E7%9A%84%E9%97%AE%E9%A2%9825%E5%AF%B9%E5%BA%94%E7%9A%84%E5%9B%BE%E7%89%872.png?raw=true)

【另外】：上述方法如果不管用，试着点击Android studio右下角的文件编码按钮，图中红色区域，然后选择UTF-8改选为GBK。

 ![Android遇到的问题25对应的图片3](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Android%E9%81%87%E5%88%B0%E7%9A%84%E9%97%AE%E9%A2%9825%E5%AF%B9%E5%BA%94%E7%9A%84%E5%9B%BE%E7%89%873.png?raw=true)
 
 此时会弹出窗口提示是否重载文件，选择“Reload”，基本也可以搞定。
 
  ![Android遇到的问题25对应的图片4](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Android%E9%81%87%E5%88%B0%E7%9A%84%E9%97%AE%E9%A2%9825%E5%AF%B9%E5%BA%94%E7%9A%84%E5%9B%BE%E7%89%874.png?raw=true)

如果设置之后还是不行，建议clean一下，重启一下Android Studio。

### 26.failed to complete gradle execution问题

> 使用Android Studio创建新项目后，一直出现 “Failed to complete Gradle execution. Cause: A fatal exception has occurred. Program will exit”这个问题。

![Android遇到的问题26对应的图片1](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Android%E9%81%87%E5%88%B0%E7%9A%84%E9%97%AE%E9%A2%9826%E5%AF%B9%E5%BA%94%E7%9A%84%E5%9B%BE%E7%89%871.png?raw=true)

**解决方法有2个（2种方式实质上还是一样的）**

> 方法1：打开工程的gradle.properties文件，添加如下配置项，这个问题应该就不会出现了。

    org.gradle.jvmargs=-Xmx512m -XX:MaxPermSize=512m
     
如下图所示：

![Android遇到的问题26对应的图片2](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Android%E9%81%87%E5%88%B0%E7%9A%84%E9%97%AE%E9%A2%9826%E5%AF%B9%E5%BA%94%E7%9A%84%E5%9B%BE%E7%89%872.png?raw=true)



> 方法2：在Android Studio中，选择File -> Settings -> Compiler -> 在VM options选项中填写：

    -Xmx512m -XX:MaxPermSize=512m
      
如下图所示：

![Android遇到的问题26对应的图片3](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Android%E9%81%87%E5%88%B0%E7%9A%84%E9%97%AE%E9%A2%9826%E5%AF%B9%E5%BA%94%E7%9A%84%E5%9B%BE%E7%89%873.png?raw=true)

### 27.控制台乱码的解决方式：

> 旧版本的gradle

```
tasks.withType(Compile) {
    options.encoding = "UTF-8"
}
```

> 新版本的gradle

```
tasks.withType(JavaCompile) {
    options.encoding = "UTF-8"
}
```

### 28.AS 2.X如何支持java8？

AS 2.X最高是支持java7的环境，要想支持java8，可以做以下设置：

> 如果是安卓的module，可以做以下配置：

```
android {
    compileSdkVersion 25
    buildToolsVersion "25.0.3"
    defaultConfig {
        applicationId "com.lzw.java8demo"
        minSdkVersion 25
        targetSdkVersion 25
        versionCode 1
        versionName "1.0"
        testInstrumentationRunner "android.support.test.runner.AndroidJUnitRunner"

        // 这个别忘记加上去
        jackOptions {
            enabled true
        }

    }

    buildTypes {
        release {
            minifyEnabled false
            proguardFiles getDefaultProguardFile('proguard-android.txt'), 'proguard-rules.pro'
        }
    }

    // 指定java8编译
    compileOptions {
        sourceCompatibility JavaVersion.VERSION_1_8
        targetCompatibility JavaVersion.VERSION_1_8
    }

}
```

> 如果是创建的Java的module，在gradle最后加上以下配置：

```
 sourceCompatibility = "1.8"
 targetCompatibility = "1.8"
```

### 29.Error:Execution failed for task':apptransformClassesWithDesugarForDebug'

 ![Android遇到的问题29对应的图片](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Android%E9%81%87%E5%88%B0%E7%9A%84%E9%97%AE%E9%A2%9829%E5%AF%B9%E5%BA%94%E7%9A%84%E5%9B%BE%E7%89%87.png?raw=true)

我看报错那里说的是注解报的错，我怀疑是jdk不一致导致的。我是打开IDE报的错，我把as的配置导入到了IDE，打开项目就报错了，as用的是jdk1.8，不知道这个IDE是不是要用jdk1.7？
目前还没找到原因。。

----

这里没提到的可以参考： **[https://my.oschina.net/Jieth/blog/489014](https://my.oschina.net/Jieth/blog/489014)**，以后会逐渐补充进去。
