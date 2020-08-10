### 一、Kotlin的Gradle插件的版本号

> **更多关于kotin Gradle插件介绍可以查看：**
> [https://plugins.gradle.org/plugin/org.jetbrains.kotlin.android](https://plugins.gradle.org/plugin/org.jetbrains.kotlin.android)

在项目的根路径的`build.gradle`里面，有这样的引用：

```groovy
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

        // NOTE: Do not place your application dependencies here; they belong
        // in the individual module build.gradle files
    }
}

```

其中`ext.kotlin_version = '1.3.50'`，这里面的`1.3.50`就是kotlin Gradle的插件的版本号。如果不知道版本号，可以在下表中查找：

```
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
	1.3.0-rc-198
	1.3.0-rc-190
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


### 二、Kotlin.android.extensions 的Gradle插件的版本号

> **更多关于kotin Gradle插件介绍可以查看：**
> [https://plugins.gradle.org/plugin/org.jetbrains.kotlin.android.extensions](https://plugins.gradle.org/plugin/org.jetbrains.kotlin.android.extensions)

在项目的根路径的`build.gradle`里面，有这样的引用：

```groovy
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

        // NOTE: Do not place your application dependencies here; they belong
        // in the individual module build.gradle files
    }
}

apply plugin: "org.jetbrains.kotlin.android.extensions"

```

其中`ext.kotlin_version = '1.3.50'`，这里面的`1.3.50`就是kotlin Gradle的插件的版本号。如果不知道版本号，可以在下表中查找：

```
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
	1.3.0-rc-198
	1.3.0-rc-190
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


### 三、Kotlin-stdlib的版本号

> **更多关于kotin Gradle插件介绍可以查看：**
> [https://mvnrepository.com/artifact/org.jetbrains.kotlin](https://mvnrepository.com/artifact/org.jetbrains.kotlin)


在项目module里的`build.gradle`里面，有这样的引用：

```
dependencies {
    // 直接引用kotlin_version变量，便于版本更改
    implementation"org.jetbrains.kotlin:kotlin-stdlib-jdk8:$kotlin_version"
    // 如果要使用jre8或者jre7，建议直接写对应版本号
    // implementation"org.jetbrains.kotlin:kotlin-stdlib-jdk8:1.3.50"
}

```

其中`org.jetbrains.kotlin:kotlin-stdlib-jdk8:1.3.50`，这里面的  `1.3.50`  就是 `kotlin-stdlib-jdk8` 的版本号。如果不知道版本号，可以在下表中查找：

**[总结：] `kotlin-stdlib-jdk8` 和 `kotlin-stdlib-jdk7` 适用的版本号必须大于等于1.2.0;  `kotlin-stdlib-jre8` 和 `kotlin-stdlib-jre7` 适用的版本号必须小于等于1.2.71，现在的开发中基本都用`kotlin-stdlib-jdk8` 和 `kotlin-stdlib-jdk7`  这两个。**

| 版本号       | org.jetbrains.kotlin:kotlin-stdlib-jdk8 | org.jetbrains.kotlin:kotlin-stdlib-jdk7 | org.jetbrains.kotlin:kotlin-stdlib-jre8 | org.jetbrains.kotlin:kotlin-stdlib-jre7 |
| ------------ | --------------------------------------- | --------------------------------------- | --------------------------------------- | --------------------------------------- |
| 1.3.50       | √                                       | √                                       | ×                                       | ×                                       |
| 1.3.41       | √                                       | √                                       | ×                                       | ×                                       |
| 1.3.40       | √                                       | √                                       | ×                                       | ×                                       |
| 1.3.31       | √                                       | √                                       | ×                                       | ×                                       |
| 1.3.30       | √                                       | √                                       | ×                                       | ×                                       |
| 1.3.21       | √                                       | √                                       | ×                                       | ×                                       |
| 1.3.20       | √                                       | √                                       | ×                                       | ×                                       |
| 1.3.11       | √                                       | √                                       | ×                                       | ×                                       |
| 1.3.10       | √                                       | √                                       | ×                                       | ×                                       |
| 1.3.0        | √                                       | √                                       | ×                                       | ×                                       |
| 1.3.0-rc-198 | √                                       | √                                       | ×                                       | ×                                       |
| 1.3.0-rc-190 | √                                       | √                                       | ×                                       | ×                                       |
| 1.2.71       | √                                       | √                                       | √                                       | √                                       |
| 1.2.70       | √                                       | √                                       | √                                       | √                                       |
| 1.2.61       | √                                       | √                                       | √                                       | √                                       |
| 1.2.60       | √                                       | √                                       | √                                       | √                                       |
| 1.2.51       | √                                       | √                                       | √                                       | √                                       |
| 1.2.50       | √                                       | √                                       | √                                       | √                                       |
| 1.2.41       | √                                       | √                                       | √                                       | √                                       |
| 1.2.40       | √                                       | √                                       | √                                       | √                                       |
| 1.2.31       | √                                       | √                                       | √                                       | √                                       |
| 1.2.30       | √                                       | √                                       | √                                       | √                                       |
| 1.2.21       | √                                       | √                                       | √                                       | √                                       |
| 1.2.20       | √                                       | √                                       | √                                       | √                                       |
| 1.2.10       | √                                       | √                                       | √                                       | √                                       |
| 1.2.0        | √                                       | √                                       | √                                       | √                                       |
| 1.1.61       | ×                                       | ×                                       | √                                       | √                                       |
| 1.1.60       | ×                                       | ×                                       | √                                       | √                                       |
| 1.1.51       | ×                                       | ×                                       | √                                       | √                                       |
| 1.1.50       | ×                                       | ×                                       | √                                       | √                                       |
| 1.1.4-3      | ×                                       | ×                                       | √                                       | √                                       |
| 1.1.4-2      | ×                                       | ×                                       | √                                       | √                                       |
| 1.1.4        | ×                                       | ×                                       | √                                       | √                                       |
| 1.1.3-2      | ×                                       | ×                                       | √                                       | √                                       |
| 1.1.3        | ×                                       | ×                                       | √                                       | √                                       |
| 1.1.2-5      | ×                                       | ×                                       | √                                       | √                                       |
| 1.1.2-4      | ×                                       | ×                                       | √                                       | √                                       |
| 1.1.2-3      | ×                                       | ×                                       | √                                       | √                                       |
| 1.1.2-2      | ×                                       | ×                                       | √                                       | √                                       |
| 1.1.2        | ×                                       | ×                                       | √                                       | √                                       |
| 1.1.1        | ×                                       | ×                                       | √                                       | √                                       |
| 1.1.0        | ×                                       | ×                                       | √                                       | √                                       |

