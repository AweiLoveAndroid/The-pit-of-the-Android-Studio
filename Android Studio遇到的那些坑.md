# [老卢独家整理] Android studio使用时遇到的问题

这里没提到的可以参考： **[https://my.oschina.net/Jieth/blog/489014](https://my.oschina.net/Jieth/blog/489014)**，以后会逐渐补充进去。

> **大体上分为以下几个方面的内容：**

	1）关于sdk  点击此处链接: 1.

	2）关于jdk  点击此处链接: 7.8.

	3）关于加速器（Intel HAXM）   点击此处链接： 2. 3. 4. 5.

	4）关于gradle  点击此处链接：9.15.

	5）关于混淆打包  点击此处链接：10.

	6）关于依赖库和插件  点击此处链接：6.11.12.13.

	7）关于配置和源码关联  点击此处链接：14.16.

	8）关于模拟器  点击此处链接：17.

### 1. Android Studio第一次启动时出现 unable to access android sdk add-on list
  
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


### 3. Intel 加速器 HAXM  ，安装过程中可以会出现如下错误:
    "Failed to configure driver: unknown error. Failed to open driver" 

    有以下几个步骤可以解决该问题：
	(1) 下载haxm_extra_workaround.zip 附件
	(2) 解压后提取hax_extract.cmd 文件到 HAXM 的解压文件路径中
	(3) hax_extract.cmd 右键用管理员权限运行。
	执行以上步骤后，基本可以解决以上提示的安装异常问题。


### 4. 因为电脑卡死,结束了qemu-system-i386.exe这个倒霉的进程,导致我开启模拟器的时候一直提示我没有安装Intel HAXM,只好再安装一遍，然后出现了以下问题:                                 This computer meets the requirements for HAXM,but IntelVirtualization Technology(VT-x) is not turned on.                                                                            HAXM can be installed,but will not work until VT-x is enabled.                           Please refer to the Inter HAXM documentation for more infomation.


    解决办法:"Inter Virtual Technology"先设置Disable，启动系统。再重启，"Inter Virtual Technology"设置为Enable


### 5. 关于intelhaxm-android.exe安装的坑:不管是双击还是右键以管理员身份运行都没用，怎么解决？

    解决办法:
    在SDK\extras\intel\Hardware_Accelerated_Execution_Manager中找到intelhaxm-android.exe，右键解压,双击setup.exe安装就好了



###  6. Failed to resolve: junit:junit:4.12

  > 出现原因：项目中引用了junit库中的代码，但是却没有相关的junit的依赖库


    解决办法：添加相关的依赖库引用,在项目的Module的build.gradle中添加如下代码就OK了
	repositories {
        maven { url 'http://repo1.maven.org/maven2' }
    	}


### 7. 只要是API24以上的Android Studio，如果JDK低于1.8都会出现这个问题，比如我列举两个:

>（1）Error:Execution failed for task':app:compileOrangeDevDebugJavaWithJavac'.compileSdkVersion 'android-24' requires JDK 1.8 or later to compile.

>（2）Android N requires the IDE to be running with Java 1.8 or later

    解决办法:把1.8以前的jdk都卸载掉,然后把环境变量配置成1.8的,就可以了.


###  8. Error:(1, 1) A problem occurred evaluating project ':app'. com/android/jack/api/ConfigNotSupportedException :
	Unsupported major.minor version 52.0
    
    解决办法:（1）把1.8以前的jdk都卸载掉，使用1.8版本的jdk
          （2）File - Project Structure - SDK Location - JDK location，这里面有个选项，
		  可以选择"use embedded JDK(recommended)"，使用AS内置的JDK。（不推荐这样做）


###  9. Unknown host 'downloads.gradle.org' 这个问题的解决:
使用android studio的gradle新建项目时候出现:Error:Unknown host 'downloads.gradle.org'.Enable Gradle 'offline mode' and sync project.Learn about configuring HTTP proxies in Gradle

>解决办法:请查看本文件夹里面的 **[Unknown host 'downloads.gradle.org'问题的解决.html](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/doc/Unknown%20host%20'downloads.gradle.org'%E9%97%AE%E9%A2%98%E7%9A%84%E8%A7%A3%E5%86%B3.html)**


### 10. 关于混淆出现的问题：
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

### 11. 这是什么原因？是因为65535问题？还是因为v7包重复了？ 【待解决。。。】
  Error:Execution failed for task ':app:transformClassesWithDexForDebug'.
  > com.android.build.api.transform.TransformException: java.lang.RuntimeException: 
  java.lang.RuntimeException: com.android.ide.common.process.ProcessException:java.util.concurrent.ExecutionException: 
  com.android.ide.common.process.ProcessException: Return code 1 for dex process

### 12. non-zero exit value 1； 和 non-zero exit value 2； 和 non-zero exit value 3 问题的解决：
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

### 13. 打开Android Studio报错 

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


### 14. 自定义android studio的配置文件目录后，无法正常安装和卸载插件(貌似2.0版本之后的插件安装卸载就有问题了)是何原因？详情看知乎 [https://www.zhihu.com/question/38604486](https://www.zhihu.com/question/38604486)

> 解决方法:

	方法(1)：将idea.system.path/plugins下的文件移动到{idea.config.path}/plugins下（如果是压缩包，则需要先解压）。 
      然后重启一下AS就可以了。删除也是，貌似也得手动去文件夹下删除）
	
    方法(2):修改AS安装目录下的idea.properties文件：
	  idea.config.path=D:/.AndroidStudio2.0/config 
	  idea.system.path=D:/.AndroidStudio2.0/system 
	  idea.plugins.path=${idea.system.path}/plugins

### 15. 导入android studio项目，出现的问题：

> Error:Failed to open zip file.
> 
Gradle's dependency cache may be corrupt (this sometimes occurs after a network connection timeout.)
> 
Re-download dependencies and sync project (requires network)
> 
Re-download dependencies and sync project (requires network)

![Android遇到的问题15对应的图片1](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Android%E9%81%87%E5%88%B0%E7%9A%84%E9%97%AE%E9%A2%9815%E5%AF%B9%E5%BA%94%E7%9A%84%E5%9B%BE%E7%89%871.png?raw=true)

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

 ![Android遇到的问题15对应的图片2](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Android%E9%81%87%E5%88%B0%E7%9A%84%E9%97%AE%E9%A2%9815%E5%AF%B9%E5%BA%94%E7%9A%84%E5%9B%BE%E7%89%872.png?raw=true)


        3.重新打开项目，对工程中做一些配置如下，重新编译一下，就没问题了:

 ![Android遇到的问题15对应的图片3](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Android%E9%81%87%E5%88%B0%E7%9A%84%E9%97%AE%E9%A2%9815%E5%AF%B9%E5%BA%94%E7%9A%84%E5%9B%BE%E7%89%873.png?raw=true)


### 16. Android studio 源码无法关联，提示Souces for android api 25 platform not found:

    解决方法：
    1）找到jdk.table.xml这个文件

    jdk.table.xml文件路径：(以win7为例，Administrator是电脑的用户名，我当前开发工具版本号是Android Studio2.3)
    C:\Users\Administrator\.AndroidStudio2.3\config\options\jdk.table.xml

    2）在<sourcePath>节点下添加这一句<root type="simple" url="file://E:/android/sdk/sources/android-25" />

    修改后的部分配置文件如下：注意红色方框部分，找到对应的编译版本，再添加对应的源码位置

 ![Android遇到的问题16对应的图片](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Android%E9%81%87%E5%88%B0%E7%9A%84%E9%97%AE%E9%A2%9816%E5%AF%B9%E5%BA%94%E7%9A%84%E5%9B%BE%E7%89%87.png?raw=true)

### 17. com.android.ddmlib.SyncException: No space left on device

    解决方法：

    把模拟器里没用的应用或者demo卸载卸载。如果还不行，就重启或者重新创建一个模拟器

### 18. app:transformClassesWithJarMergingForDebug

 ![Android遇到的问题18对应的图片](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Android%E9%81%87%E5%88%B0%E7%9A%84%E9%97%AE%E9%A2%9818%E5%AF%B9%E5%BA%94%E7%9A%84%E5%9B%BE%E7%89%87.png?raw=true)

> 原因：重复依赖导致的.

> 解决办法：

    找到报错的那个提示，看上面报错的是哪个类，双击shift搜索一下，看这个报错的类在哪个依赖库里面用到了。
    在AS中，选择以project显示项目，找到最下面的External Libraries，然后继续找，找到相对应的类库。
    点开之后发现了一个pom.xml，这里面就是关于这个jar的一些配置文件，往下找，发现了一个依赖库的引用，
    复制里面groupId，到你的app的build.gradle里，找到那个依赖，添加{exclude group: 'XXX'} XXX换成刚才复制的groupId，这样就
    把这个groudId的引用去除掉。

### 19. processdebugresources

 ![Android遇到的问题19对应的图片](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Android%E9%81%87%E5%88%B0%E7%9A%84%E9%97%AE%E9%A2%9819%E5%AF%B9%E5%BA%94%E7%9A%84%E5%9B%BE%E7%89%87.png?raw=true)

>原因：build.gradle的兼容包和compileSdkVersion配置不对引起的，关于这个匹配，请查看[Android Studio和gradle版本对照.txt](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/doc/Android%20Studio%E5%92%8Cgradle%E7%89%88%E6%9C%AC%E5%AF%B9%E7%85%A7.txt)

>解决办法：让兼容包和compileSdkVersion匹配就OK了

### 20. Android Studio配置androidannotations出现 Error:Execution failed for task ':app:compileDebugJavaWithJavac'

 ![Android遇到的问题20对应的图片](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Android%E9%81%87%E5%88%B0%E7%9A%84%E9%97%AE%E9%A2%9820%E5%AF%B9%E5%BA%94%E7%9A%84%E5%9B%BE%E7%89%87.png?raw=true)

>原因： androidannotations配置环境对SDKtools, Build Tools, Platform Tools 以及 SDK Platform有要求，不匹配的话就会报错

> 解决办法：打开SDK Manager，更新SDKtools, Build Tools, Platform Tools 以及 SDK Platform到最新版本