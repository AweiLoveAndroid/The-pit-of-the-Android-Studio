# Intellij IDEA和Android Studio工具通用使用总结


> Android Studio是基于Intellij IDEA研发出来的一个开发工具，所以绝大多数功能都是通用的，不必担心兼容性的问题。为了那些不熟悉Intellij IDEA的朋友，我这里专门列举了一些Android Studio和Intellij IDEA的兼容指南，帮助大家快速熟悉Intellij IDEA开发工具。


## 一、 关于设置

> 以下这些设置和Android Studio基本是一样的，所以你开源点进去看这些对应的链接，操作界面基本是差不多的。（可能新版本的Intellij IDEA开发工具会做一些调整，但是功能都是差不多的）

#### :+1:  [常用设置和快捷键](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/tree/master/readme/Android%20Studio%E5%B8%B8%E7%94%A8%E8%AE%BE%E7%BD%AE%E5%92%8C%E5%BF%AB%E6%8D%B7%E9%94%AE.md)

#### :+1:  [常用模板用法和自定义模板](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/tree/master/readme/Android%20Studio%E5%B8%B8%E7%94%A8%E6%A8%A1%E6%9D%BF%E7%94%A8%E6%B3%95%E5%92%8C%E8%87%AA%E5%AE%9A%E4%B9%89%E6%A8%A1%E6%9D%BF.md)

#### :fire: [各种实用的插件全面总结](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/tree/master/readme/Android%20Studio%E5%A5%BD%E7%94%A8%E7%9A%84%E6%8F%92%E4%BB%B6.md)

#### :point_right:  [Android所有的Support支持库详解](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/readme/Android%20Support%E6%94%AF%E6%8C%81%E5%BA%93%E8%AF%A6%E8%A7%A3.md)

#### :point_right:  [Android Annotations Library 安卓注解库的使用](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/tree/master/readme/Android%E6%B3%A8%E8%A7%A3%E5%BA%93%E7%9A%84%E4%BD%BF%E7%94%A8.md)

## 二、 关于Android模拟器

#### 方式1、在电脑的`C:\Users\Administrator\.android\.avd`目录里面放的就是模拟器的文件。它是通用的（Android Studio和Intellij IDEA都可以用它），你只要在Intellij IDEA中`File`->`Settings`设置里面绑定模拟器路径，当你使用Intellij IDEA开发运行安卓项目时，点击菜单栏的绿色三角形的按钮，即可顺利打开模拟器了。

#### 方式2、除此之外，你也可以通过命令行打开模拟器：

> 1.首先在电脑的C盘的C:\Users\Administrator\.android\avd这个目录找到你创建的模拟器的名称，去掉后缀名，复制一下。比如我的：`Pixel_API25_7.1.1_x86_1080x1920_xxhdpi_5.0inch.avd`

> 2.创建一个使用脚本，新建一个文件，后缀名为`.bat`，然后用记事本打开，输入以下内容：，其中`E:\develop\sdk\tools\emulator.exe`是模拟器所在sdk的路径，换成你电脑里面对应路径即可。`Pixel_API25_7.1.1_x86_1080x1920_xxhdpi_5.0inch`是上一步中复制的模拟器文件的名称。最后记得保存。
> 
```
E:\develop\sdk\tools\emulator.exe -netdelay none -netspeed full -avd Pixel_API25_7.1.1_x86_1080x1920_xxhdpi_5.0inch -writable-system
```
> 3.双击刚才创建的脚本，即可开启模拟器了。


## 三、 使用Intellij IDEA进行后端或者前端开发

这个除了设置跟Android Studio差不多之外，开发的配置是不一样的，需要特别注意一下，比如你要配置maven，配置mysql，配置spring等，这些需要你自己去学习，但是有一点是通用的，那就是`build.gradle`文件，都是通过`gradle`去添加需要用到的依赖库，所以熟练掌握`gradle`的使用是非常有必要的。

> 关于`gradle`遇到的坑相关参考文章，虽然是Android Studio遇到的问题，但是在Intellij IDEA上面也是很有借鉴意义的，因为绝大多数问题都是`gradle`引起的，可以借鉴它的解决问题的方式和方案：

### :fire::+1:  [Android Studio2.X遇到的那些坑](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/tree/master/readme/Android%20Studio%E9%81%87%E5%88%B0%E7%9A%84%E9%82%A3%E4%BA%9B%E5%9D%91.md)

### :fire::+1: [Android Studio3.0+填坑指南](http://www.jianshu.com/p/b45d68c98828)
