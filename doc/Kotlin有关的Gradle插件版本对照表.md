[TOC]

# Kotlin有关的Gradle插件版本对照表

## ★ 前言：关于在工程中使用Kotlin时的build.gradle配置：

在项目的根路径的`build.gradle`里面，加入这样的配置：

``` groovy
// 必须加上这两个apply
apply plugin: "org.jetbrains.kotlin.android"
apply plugin: "org.jetbrains.kotlin.android.extensions"

buildscript {
    
    ext.kotlin_version = '1.3.50'
    
    repositories {
        google()
        jcenter()
    }
    
    dependencies {
        classpath 'com.android.tools.build:gradle:3.5'
	
	    // 使用 kotlin的Gradle插件
        classpath "org.jetbrains.kotlin:kotlin-gradle-plugin:$kotlin_version"
    }
}
```

在项目module里的`build.gradle`里面，加入这样的配置：

```groovy
dependencies {
    // 直接引用kotlin_version变量，便于版本更改
    implementation "org.jetbrains.kotlin:kotlin-stdlib-jdk8:$kotlin_version"
    // 也可以直接写对应的版本号
    // implementation "org.jetbrains.kotlin:kotlin-stdlib-jdk8:1.3.50"
}
```



## 一、Kotlin.android的Gradle插件的版本号

### 1 源码地址：

> **更多关于kotin Gradle插件介绍可以查看：**
> [https://plugins.gradle.org/plugin/org.jetbrains.kotlin.android](https://plugins.gradle.org/plugin/org.jetbrains.kotlin.android)

### 2 使用方式：

在项目的根路径的`build.gradle`里面，有这样的引用：

```groovy
// 这个必须加上
apply plugin: "org.jetbrains.kotlin.android"

buildscript {
    
    ext.kotlin_version = '1.3.50'
    
    repositories {
        google()
        jcenter()
    }
    
    dependencies {
        classpath 'com.android.tools.build:gradle:3.5'
	
	    // 使用 kotlin的Gradle插件
        classpath "org.jetbrains.kotlin:kotlin-gradle-plugin:$kotlin_version"
    }
}
```

其中`ext.kotlin_version = '1.3.50'`，这里面的`1.3.50`就是kotlin Gradle的插件的版本号。如果不知道版本号，可以在下表中查找：

```
	1.5.20
	1.5.10
	1.5.0
	1.4.32
	1.4.31
	1.4.30
	1.4.21-2
	1.4.21
	1.4.20
	1.4.10
	1.4.0
	1.3.72
	1.3.71
	1.3.70
	1.3.61
	1.3.60
	1.3.50
	1.3.41
	1.3.40
	1.3.31
	1.3.30
	1.3.21
	1.3.20
	1.3.11
	1.3.10
	1.3.0
	1.2.71
	1.2.70
	1.2.61
	1.2.60
	1.2.51
	1.2.50
	1.2.41
	1.2.40
	1.2.31
	1.2.30
	1.2.21
	1.2.20
	1.2.10
	1.2.0
	1.1.61
	1.1.60
	1.1.51
	1.1.50
	1.1.4-3
	1.1.4-2
	1.1.4
	1.1.3-2
	1.1.3
	1.1.2-5
	1.1.2-2
	1.1.2
	1.1.1
```



-----


## 二、Kotlin.android.extensions 的Gradle插件的版本号

### 1. 源码地址：

> **更多关于kotin Gradle插件介绍可以查看：**
> [https://plugins.gradle.org/plugin/org.jetbrains.kotlin.android.extensions](https://plugins.gradle.org/plugin/org.jetbrains.kotlin.android.extensions)


### 2. 使用方式：

在项目的根路径的`build.gradle`里面，有这样的引用：

```groovy
// 这个必须加上
apply plugin: "org.jetbrains.kotlin.android.extensions"

buildscript {
    
    ext.kotlin_version = '1.3.50'
    
    repositories {
        google()
        jcenter()
    }
    
    dependencies {
        classpath 'com.android.tools.build:gradle:3.5'
	
	    // 使用 kotlin的Gradle插件
        classpath "org.jetbrains.kotlin:kotlin-gradle-plugin:$kotlin_version"

    }
}
```

其中`ext.kotlin_version = '1.3.50'`，这里面的`1.3.50`就是kotlin Gradle的插件的版本号。如果不知道版本号，可以在下表中查找：

```
	1.5.20
	1.5.10
	1.5.0
	1.4.32
	1.4.31
	1.4.30
	1.4.21-2
	1.4.21
	1.4.20
	1.4.10
	1.4.0
	1.3.72
	1.3.71
	1.3.70
	1.3.61
	1.3.60
	1.3.50
	1.3.41
	1.3.40
	1.3.31
	1.3.30
	1.3.21
	1.3.20
	1.3.11
	1.3.10
	1.3.0
	1.2.71
	1.2.70
	1.2.61
	1.2.60
	1.2.51
	1.2.50
	1.2.41
	1.2.40
	1.2.31
	1.2.30
	1.2.21
	1.2.20
	1.2.10
	1.2.0
	1.1.61
	1.1.60
	1.1.51
	1.1.50
	1.1.4-3
	1.1.4-2
	1.1.4
	1.1.3-2
	1.1.3
	1.1.2-5
	1.1.2-2
	1.1.2
	1.1.1
```

----


## 三、Kotlin-stdlib的版本号

### 1. 源码地址：

插件名称|仓库下载地址
----|----
kotlin-stdlib-jdk8|[https://mvnrepository.com/artifact/org.jetbrains.kotlin/kotlin-stdlib-jdk8](https://mvnrepository.com/artifact/org.jetbrains.kotlin/kotlin-stdlib-jdk8)
kotlin-stdlib-jdk7|[https://mvnrepository.com/artifact/org.jetbrains.kotlin/kotlin-stdlib-jdk7](https://mvnrepository.com/artifact/org.jetbrains.kotlin/kotlin-stdlib-jdk7)
kotlin-stdlib-jre8|[https://mvnrepository.com/artifact/org.jetbrains.kotlin/kotlin-stdlib-jre8](https://mvnrepository.com/artifact/org.jetbrains.kotlin/kotlin-stdlib-jre8)
kotlin-stdlib-jre7|[https://mvnrepository.com/artifact/org.jetbrains.kotlin/kotlin-stdlib-jre7](https://mvnrepository.com/artifact/org.jetbrains.kotlin/kotlin-stdlib-jre7)


### 2. 使用方式：

在项目module里的`build.gradle`里面，有这样的引用：

```
dependencies {
    // 直接引用kotlin_version变量，便于版本更改
    implementation"org.jetbrains.kotlin:kotlin-stdlib-jdk8:$kotlin_version"
    // 如果要使用jre8或者jre7，建议直接写对应版本号
    // implementation"org.jetbrains.kotlin:kotlin-stdlib-jdk8:1.3.50"
}

```

其中`org.jetbrains.kotlin:kotlin-stdlib-jdk8:1.3.50`，这里面的  `1.3.50`  就是 `kotlin-stdlib-jdk8` 的版本号。

## 3. 【适用场景总结：】

| Kotlin版本号 | 适用场景                                     |
| ------------ | -------------------------------------------- |
| `>=1.2.0`    | `kotlin-stdlib-jdk8` 和 `kotlin-stdlib-jdk7` |
| `<1.2.71`    | `kotlin-stdlib-jre8` 和 `kotlin-stdlib-jre7` |

**现在的开发中基本都用`kotlin-stdlib-jdk8` 和 `kotlin-stdlib-jdk7`  这两个。**

### 4. Kotlin-stdlib的版本汇总对比表：


| Kotlin版本号 | org.jetbrains.kotlin:<br/>kotlin-stdlib-jdk8 | org.jetbrains.kotlin:<br/>kotlin-stdlib-jdk7 | org.jetbrains.kotlin:<br/>kotlin-stdlib-jre8 | org.jetbrains.kotlin:<br/>kotlin-stdlib-jre7 |
| ------------ | -------------------------------------------- | -------------------------------------------- | -------------------------------------------- | -------------------------------------------- |
|1.5.21|**<font color=blue>√</font>**|**<font color=blue>√</font>**|<font color=red>×</font>|<font color=red>×</font>|
|1.5.10|**<font color=blue>√</font>**|**<font color=blue>√</font>**|<font color=red>×</font>|<font color=red>×</font>|
|1.5.0|**<font color=blue>√</font>**|**<font color=blue>√</font>**|<font color=red>×</font>|<font color=red>×</font>|
|1.4.32|**<font color=blue>√</font>**|**<font color=blue>√</font>**|<font color=red>×</font>|<font color=red>×</font>|
|1.4.31|**<font color=blue>√</font>**|**<font color=blue>√</font>**|<font color=red>×</font>|<font color=red>×</font>|
|1.4.30|**<font color=blue>√</font>**|**<font color=blue>√</font>**|<font color=red>×</font>|<font color=red>×</font>|
|1.4.21-2|**<font color=blue>√</font>**|**<font color=blue>√</font>**|<font color=red>×</font>|<font color=red>×</font>|
|1.4.21|**<font color=blue>√</font>**|**<font color=blue>√</font>**|<font color=red>×</font>|<font color=red>×</font>|
|1.4.20|**<font color=blue>√</font>**|**<font color=blue>√</font>**|<font color=red>×</font>|<font color=red>×</font>|
|1.4.10|**<font color=blue>√</font>**|**<font color=blue>√</font>**|<font color=red>×</font>|<font color=red>×</font>|
|1.4.0|**<font color=blue>√</font>**|**<font color=blue>√</font>**|<font color=red>×</font>|<font color=red>×</font>|
|1.3.72|**<font color=blue>√</font>**|**<font color=blue>√</font>**|<font color=red>×</font>|<font color=red>×</font>|
|1.3.71|**<font color=blue>√</font>**|**<font color=blue>√</font>**|<font color=red>×</font>|<font color=red>×</font>|
|1.3.70|**<font color=blue>√</font>**|**<font color=blue>√</font>**|<font color=red>×</font>|<font color=red>×</font>|
|1.3.61|**<font color=blue>√</font>**|**<font color=blue>√</font>**|<font color=red>×</font>|<font color=red>×</font>|
|1.3.60|**<font color=blue>√</font>**|**<font color=blue>√</font>**|<font color=red>×</font>|<font color=red>×</font>|
| 1.3.50       | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | <font color=red>×</font>                     | <font color=red>×</font>                     |
| 1.3.41       | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | <font color=red>×</font>                     | <font color=red>×</font>                     |
| 1.3.40       | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | <font color=red>×</font>                     | <font color=red>×</font>                     |
| 1.3.31       | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | <font color=red>×</font>                     | <font color=red>×</font>                     |
| 1.3.30       | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | <font color=red>×</font>                     | <font color=red>×</font>                     |
| 1.3.21       | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | <font color=red>×</font>                     | <font color=red>×</font>                     |
| 1.3.20       | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | <font color=red>×</font>                     | <font color=red>×</font>                     |
| 1.3.11       | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | <font color=red>×</font>                     | <font color=red>×</font>                     |
| 1.3.10       | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | <font color=red>×</font>                     | <font color=red>×</font>                     |
| 1.3.0        | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | <font color=red>×</font>                     | <font color=red>×</font>                     |
| 1.3.0-rc-198 | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | <font color=red>×</font>                     | <font color=red>×</font>                     |
| 1.3.0-rc-190 | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | <font color=red>×</font>                     | <font color=red>×</font>                     |
| 1.2.71       | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.2.70       | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.2.61       | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.2.60       | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.2.51       | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.2.50       | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.2.41       | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.2.40       | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.2.31       | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.2.30       | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.2.21       | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.2.20       | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.2.10       | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.2.0        | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.1.61       | <font color=red>×</font>                     | <font color=red>×</font>                     | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.1.60       | <font color=red>×</font>                     | <font color=red>×</font>                     | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.1.51       | <font color=red>×</font>                     | <font color=red>×</font>                     | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.1.50       | <font color=red>×</font>                     | <font color=red>×</font>                     | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.1.4-3      | <font color=red>×</font>                     | <font color=red>×</font>                     | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.1.4-2      | <font color=red>×</font>                     | <font color=red>×</font>                     | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.1.4        | <font color=red>×</font>                     | <font color=red>×</font>                     | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.1.3-2      | <font color=red>×</font>                     | <font color=red>×</font>                     | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.1.3        | <font color=red>×</font>                     | <font color=red>×</font>                     | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.1.2-5      | <font color=red>×</font>                     | <font color=red>×</font>                     | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.1.2-4      | <font color=red>×</font>                     | <font color=red>×</font>                     | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.1.2-3      | <font color=red>×</font>                     | <font color=red>×</font>                     | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.1.2-2      | <font color=red>×</font>                     | <font color=red>×</font>                     | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.1.2        | <font color=red>×</font>                     | <font color=red>×</font>                     | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.1.1        | <font color=red>×</font>                     | <font color=red>×</font>                     | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |
| 1.1.0        | <font color=red>×</font>                     | <font color=red>×</font>                     | **<font color=blue>√</font>**                | **<font color=blue>√</font>**                |

