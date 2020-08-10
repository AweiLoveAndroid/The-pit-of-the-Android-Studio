### 一、Android Studio版本和Cmake版本的对应关系：


| Plugin版本( Android Studio 版本) | 对应的 CMake 版本 |
|----|----|
| Android Studio 3.5.0+||
| Android Studio 3.4.1 ||
| Android Studio 3.4.0 ||
| Android Studio 3.3.2 ||
| Android Studio 3.3.1 ||
| Android Studio 3.3.0 ||
| Android Studio 3.2.1 ||
| Android Studio 3.2.0 ||
| Android Studio 3.1.4 |官网没说 |
| Android Studio 3.1.3 |官网没说 |
| Android Studio 3.1.2 |官网没说 |
| Android Studio 3.1.1 |官网没说 |
| Android Studio 3.1.0 |官网没说 |
| Android Studio 3.0.1 |CMake 3.7+ |
| Android Studio 3.0.0 |CMake 3.7+ |
| Android Studio 2.3.3 ||
| Android Studio 2.3.2 ||
| Android Studio 2.3.1 ||
| Android Studio 2.3.0 ||
| Android Studio 2.2.3 ||
| Android Studio 2.2.2 ||
| Android Studio 2.2.1 ||
| Android Studio 2.2.0 ||
| Android Studio 2.1.3 ||
| Android Studio 2.1.2 ||
| Android Studio 2.1.1 ||
| Android Studio 2.1.0 ||
| Android Studio 2.0.0 ||
| Android Studio 1.5.0 ||
| Android Studio 1.3.1 ||
| Android Studio 1.3.0 ||
| Android Studio 1.2.0 ||
| Android Studio 1.1.3 ||
| Android Studio 1.1.2 ||
| Android Studio 1.1.1 ||
| Android Studio 1.1.0 ||
| Android Studio 1.0.1 ||
| Android Studio 1.0.0 ||

----

### 二、Android Studio版本、Gradle版本、Build Tools版本以及Cmake版本的相互对应关系

> **综合一下：下表是我根据谷歌的官网找到的资料整理的一张很综合的一张表，这张图可以很直观的看到Android Studio版本、Gradle版本、Build Tools版本以及Cmake版本的相互对应关系，大家可以对照着这个图查看，这张图可以解决大家关于版本匹配遇到的难题。**

| Plugin版本( Android Studio 版本) | Gradle 版本 | 对应的 Build Tools 版本 | 对应的 CMake 版本 |
|----|----|----|----|
| Android Studio 3.5.0+|Gradle 5.4.1+| Build Tools 28.0.3+||
| Android Studio 3.4.1 |Gradle 5.1.1+| Build Tools 28.0.3+||
| Android Studio 3.4.0 |Gradle 5.1.1+| Build Tools 28.0.3+||
| Android Studio 3.3.2 |Gradle 4.10.1+ |Build Tools 28.0.3+||
| Android Studio 3.3.1 |Gradle 4.10.1+ |Build Tools 28.0.3+||
| Android Studio 3.3.0 |Gradle 4.10.1+ |Build Tools 28.0.3+||
| Android Studio 3.2.1 |Gradle 4.6+ | Build Tools 28.0.3+||
| Android Studio 3.2.0 |Gradle 4.6+ | Build Tools 28.0.3+||
| Android Studio 3.1.4 |Gradle 4.4+ | Build Tools 27.0.3+ |官网没说 |
| Android Studio 3.1.3 |Gradle 4.4+ | Build Tools 27.0.3+ |官网没说 |
| Android Studio 3.1.2 |Gradle 4.4+ | Build Tools 27.0.3+ |官网没说 |
| Android Studio 3.1.1 |Gradle 4.4+ | Build Tools 27.0.3+ |官网没说 |
| Android Studio 3.1.0 |Gradle 4.4+ | Build Tools 27.0.3+ |官网没说 |
| Android Studio 3.0.1 |Gradle 4.1+ | Build Tools 26.0.2+ |CMake 3.7+ |
| Android Studio 3.0.0 |Gradle 4.1+ | Build Tools 26.0.2+ |CMake 3.7+ |
| Android Studio 2.3.3 |Gradle 3.3+ | Build Tools 25.0.0+||
| Android Studio 2.3.2 |Gradle 3.3+ | Build Tools 25.0.0+||
| Android Studio 2.3.1 |Gradle 3.3+ | Build Tools 25.0.0+||
| Android Studio 2.3.0 |Gradle 3.3+ | Build Tools 25.0.0+||
| Android Studio 2.2.3 |Gradle 2.14.1+ |Build Tools 23.0.2+||
| Android Studio 2.2.2 |Gradle 2.14.1+ |Build Tools 23.0.2+||
| Android Studio 2.2.1 |Gradle 2.14.1+ |Build Tools 23.0.2+||
| Android Studio 2.2.0 |Gradle 2.14.1+ |Build Tools 23.0.2+||
| Android Studio 2.1.3 |Gradle 2.14.1+ |Build Tools 23.0.2+||
| Android Studio 2.1.2 |Gradle 2.10 - 2.13|Build Tools 23.0.2+||
| Android Studio 2.1.1 |Gradle 2.10 - 2.13|Build Tools 23.0.2+||
| Android Studio 2.1.0 |Gradle 2.10 - 2.13| Build Tools 23.0.2+||
| Android Studio 2.0.0 |Gradle 2.10 - 2.13| Build Tools 21.1.1+||
| Android Studio 1.5.0 |Gradle 2.2.1 - 2.13| Build Tools 21.1.1+||
| Android Studio 1.3.1 |Gradle 2.2.1 - 2.9| Build Tools 21.1.1+||
| Android Studio 1.3.0 |Gradle 2.2.1 - 2.9| Build Tools 21.1.1+||
| Android Studio 1.2.0 |Gradle 2.2.1 - 2.9| Build Tools 21.1.1+||
| Android Studio 1.1.3 |Gradle 2.2.1 - 2.3| Build Tools 21.1.1+||
| Android Studio 1.1.2 |Gradle 2.2.1 - 2.3| Build Tools 21.1.1+||
| Android Studio 1.1.1 |Gradle 2.2.1 - 2.3| Build Tools 21.1.1+||
| Android Studio 1.1.0 |Gradle 2.2.1 - 2.3| Build Tools 21.1.1+||
| Android Studio 1.0.1 |Gradle 2.2.1-2.3.x | Build Tools 21.1.1+||
| Android Studio 1.0.0 |Gradle 2.2.1-2.3.x | Build Tools 21.1.1+||

----

> **更多关于CMake的介绍可以查看：**
> [https://developer.android.google.cn/studio/projects/add-native-code.html#vanilla_cmake](
> https://developer.android.google.cn/studio/projects/add-native-code.html#vanilla_cmake)

