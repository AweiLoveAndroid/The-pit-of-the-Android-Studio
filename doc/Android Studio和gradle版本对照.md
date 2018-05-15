## Android Studio版本、Gradle版本、Build Tools版本对照详细解答

### 一、Android Studio版本、Gradle版本、Build Tools版本图解



**官网的原版图是这样的：（原网址：[https://developer.android.google.cn/studio/releases/gradle-plugin](https://developer.android.google.cn/studio/releases/gradle-plugin)）**

Plugin版本( Android Studio 版本)|Gradle 版本
-|-
1.0.0 - 1.1.3|	2.2.1 - 2.3
1.2.0 - 1.3.1|	2.2.1 - 2.9
1.5.0|	2.2.1 - 2.13
2.0.0 - 2.1.2|	2.10 - 2.13
2.1.3 - 2.2.3|	2.14.1+
2.3.0+	|3.3+
3.0.0+|	4.1+
3.1.0+|	4.4+

> **下图是我根据谷歌的官网找到的资料整理的一张表，这张图可以很直观的看到Android Studio版本、Gradle版本、Build Tools版本三者之间的相互匹配关系，大家可以对照着这个图查看，这张图可以解决大家关于版本匹配遇到的难题。**

Plugin版本( Android Studio 版本)|Gradle 版本 |对应的 Build Tools 版本|对应的 CMake 版本
-|-|-|-
1.0.0+|2.2.1-2.3.x|Build Tools 21.1.1+|
1.0.1+|2.2.1-2.3.x|Build Tools 21.1.1+|
1.1.0+|2.2.1+|Build Tools 21.1.1+|
1.1.1+|2.2.1+|Build Tools 21.1.1+|
1.1.2+|2.2.1+|Build Tools 21.1.1+|
1.1.3+|2.2.1+|Build Tools 21.1.1+|
1.2.0+|2.2.1+|Build Tools 21.1.1+|
1.3.0+|2.2.1+|Build Tools 21.1.1+|
1.3.1+|2.2.1+|Build Tools 21.1.1+|
1.5.0+|2.2.1+|Build Tools 21.1.1+|
2.0.0+|2.10+|Build Tools 21.1.1+|
2.1.0+|2.10+|Build Tools 23.0.2+|
2.1.3+|2.14.1+|Build Tools 23.0.2+|
2.2.0+|2.14.1+|Build Tools 23.0.2+|
2.3.0+|3.3+|Build Tools 25.0.0+|
3.0.0+|4.1+|Build Tools 26.0.2+ |CMake 3.7+
3.1.0+|4.4+|Build Tools 27.0.3+ |官网没说

### 二、Android Studio版本历史：

> **更多关于Android Studio介绍可以查看：**
> [https://developer.android.google.cn/studio/releases/](https://developer.android.google.cn/studio/releases/)

	3.1.2（2018年4月）
	3.1.1（2018年4月）
	3.1.0 (2018年3月)
	3.0.1（2017年11月）
	3.0.0 (2017年10月)
	2.3.3（2017年6月）
	2.3.2（2017年5月）
	2.3.1（2017年4月）
	2.3.0 (2017年3月)
	2.2.3（2016年12月）
	2.2.2（2016年10月）
	2.2.1（2016年10月）
	2.2.0 (2016年9月)
	2.1.3（2016年8月）
	2.1.2（2016年6月）
	2.1.1（2016年5月）
	2.1.0 (2016年4月)
	2.0.0 (2016年4月)

### 三、Build Tools 版本号历史：

> **每个版本的详细描述可以查看：**
> [https://developer.android.google.cn/studio/releases/build-tools](https://developer.android.google.cn/studio/releases/build-tools)

	Build Tools 27.0.3 （2017年12月）
	Build Tools 27.0.2 （2017年12月）
	Build Tools 27.0.1 （2017年11月）
	Build Tools 26.0.2 （2017年10月）
	Build Tools 26.0.1 （2017年7月）
	Build Tools 26.0.0 （2017年6月）
	Build Tools 25.0.3 （2017年4月）
	Build Tools 25.0.2 （2016年12月）
	Build Tools 25.0.1 （2016年11月）
	Build Tools 25.0.0 （2016年10月）
	Build Tools 24.0.3 （2016年9月）
	Build Tools 23.0.3 （2016年3月）
	Build Tools 23.0.2 （2015年11月）
	Build Tools 23.0.1 （2015年10月）
	Build Tools 23.0.0 （2015年8月）
	Build Tools 22.0.1 （2015年3月）
	Build Tools 22.0.0 （2015年3月）
	Build Tools 21.1.2 （2015年2月）
	Build Tools 21.1.1 （2014年11月）
	Build Tools 21.1 （2014年10月）
	Build Tools 21.0.2 （2014年10月）
	Build Tools 21.0.1 （2014年10月）
	Build Tools 21.0.0 （2014年10月）
	Build Tools 20.0.0 （2014年6月）
	Build Tools 19.1.0 （2014年5月）
	Build Tools 19.0.3 （2014年3月）
	Build Tools 19.0.2 （2014年2月）
	Build Tools 19.0.1 （2013年12月）
	Build Tools 19 （2013年10月）
	Build Tools 18.1.1 （2013年9月）
	Build Tools 18.1.0 （2013年9月）
	Build Tools 18.0.1 （2013年7月）
	Build Tools 17 （2013年5月）

### 四、关于support包的版本（这个经常容易报错的）：
 
> **26以后的详情可以参考（>=26）：**
> [https://developer.android.google.cn/topic/libraries/support-library/revisions](https://developer.android.google.cn/topic/libraries/support-library/revisions)
>
> **26以前的详情可以参考（<=26）：**
> [https://developer.android.google.cn/topic/libraries/support-library/rev-archive](https://developer.android.google.cn/topic/libraries/support-library/rev-archive)

	27.1.1（2018年4月）
	27.1.0（2018年2月）
	27.0.2（2017年11月）
	27.0.1（2017年11月）
	27.0.0（2017年10月）
	26.1.0（2017年9月）
	26.0.2（2017年8月）
	26.0.1（2017年8月）
	26.0.0（2017年7月）
	26.0.0 Beta 2（2017年6月）
	26.0.0 Beta 1（2017年5月）
	26.0.0 Alpha 1（2017年3月）
	25.4.0（2017年6月）
	25.3.1（2017年3月）
	25.3.0（2017年3月）
	25.2.0（2017年2月）
	25.1.1（2017年1月）
	25.1.0（2016年12月）
	25.0.1
	25.0.0
	24.2.1
	24.2.0
	24.1.1
	24.1.0
	24.0.0
	23.4.0
	23.3.0
	23.2.1
	23.2.0
	23.1.1
	23.1.0
	23.0.1
	23
	22.2.1
	22.2.0
	22.1.0
	22
	21.0.3
	21.0.2
	21.0.1
	21
	20
	19.1.0
	19.0.1
	19
