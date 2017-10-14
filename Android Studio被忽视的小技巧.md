# 在这里列举一个很有用，却被忽视的工具：

在Android Studio中，Google提供了很多代码分析工具，这些工具都集中在Android Studio的Analyze菜单中

[Analyze菜单.png](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Analyze%E8%8F%9C%E5%8D%95.png)

#### （1）Inspect Code功能

[Analyze中的Inspect Code使用.png](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Analyze%E4%B8%AD%E7%9A%84Inspect%20Code%E4%BD%BF%E7%94%A8.png)

###### Inspect Code功能，可以让IDE分析整个工程，不仅提供了Lint的检测功能，还提供了一些其他的代码静态分析结果。它会给出所有在这个项目中不规范的编码（比如：项目中存在hardcode)、多余的资源、拼写问题、可能的bug、或者其它的一些问题，同时给出了大致的修改意见，点击对应的问题后后边会给出问题的具体位置供我们修改。这个工具可以让项目具有规范性的开发。

#### (2) 使用Code Cleanup功能来进行自动的代码修复

###### 主要是做代码修复的，不多说了。

#### (3) 关于Dependencies。在Analyze菜单中，有4个Dependencies选项，通过这几个选项，可以快速分析项目的Dependencies依赖。

##### 作用之一：比如，可以看出多个依赖库有没有重复依赖同一个库等。

**分别是：**

    1. Analyze Dependencies...
    2. Analyze Barkward Dependencies...
    3. Analyze Module Dependencies...
    4. Analyze Cyclic Dependencies...

#### (4) Analyze Data flow 分析数据的来龙去脉（特别适用于查看旧代码）

**有两个选项：**

    1. Analyze Data Flow to Here 数据传入
    2. Analyze Data Flow from Here 数据流出

###### 这个功能用的不是很多，但是在某些情况下，对于熟悉旧的代码非常有帮助，它可以追踪数据流，了解该数据变量的来龙去脉，可以通过Dataflow from local variable的结果和Dataflow to local variable的结果显示出来