# Android支持库详解

　　Android 支持库提供了诸多未内置于框架的功能。这些库提供向后兼容版本的新功能、框架中未包含的实用 UI 元素，以及应用可以利用的一系列实用程序。

## 第一章、概览

　　许多情况下，某项功能可能对应用开发者很有用，但是添加到 Android 框架却并不合适。例如，某个应用可能仅需要用于特定用例的某项功能，如在不同版本的 Android 系统之间顺畅切换。

　　为了解决这一问题，Android SDK 添加了多个库，这些库统称为 Android 支持库。如果应用开发者想要在应用中集成库功能，他们可以添加其中任意一个库。

　　支持库提供一系列不同的功能：

* 向后兼容版本的框架组件。
* 用于实现建议的 Android 布局模式的 UI 元素。
* 支持不同的设备类型。
* 其他实用程序功能。

### （一）向后兼容性

　　支持库可以让在旧版本 Android 平台上运行的应用支持为新版本平台推出的功能。例如，应用在依赖于框架类的 5.0（API 级别 21）版本以下的 Android 系统上运行时，将无法显示 Material Design 元素，因为该版本的 Android 框架不支持 Material Design。但是，如果此应用添加了支持库的 appcompat 库，则可以访问 API 级别 21 中具有的许多功能，其中包括对 Material Design 的支持。因此，您的应用可以在多个平台版本中提供更为一致的体验。

　　某些情况下，类的支持库版本很大程度上取决于框架提供的功能。因此，如果应用调用其中一个支持类的方法，则支持库的行为将取决于运行应用的 Android 版本。如果框架提供必要的功能，则支持库将通过调用框架执行任务。如果应用在旧版本的 Android 上运行，且框架未显示所需的功能，则支持库自身可能会尝试提供功能或什么都不做。无论是哪一种情形，应用通常都不需要检查其在哪一版本的 Android 上运行，而是通过支持库执行检查并选择适当的行为。通常情况下，名称以 **…Compat**（如 ActivityCompat）结束的类即是如此。

　　而另外一些情况下，支持库类提供一个不依赖于任何框架 API 可用性的完整、独立版框架类。这些方法可以在支持的所有平台中提供一致的行为。

　　无论是哪一种情形，应用均无需在运行期间检查系统版本。应用可通过支持库类执行适当的系统检查，并在必要时修改其行为。

### （二）支持一般布局模式

　　支持库提供 Android 框架中未提供的用户界面元素。例如，Android 支持库提供其他布局类，如 DrawerLayout。这些类遵循建议的 Android 设计做法；例如，设计库以一种适合多个 Android 版本的方式遵循 Material Design 的原则。

　　通过使用这些支持库类，您可以避免做一些重复性工作；如果应用有特殊的用户界面要求，您可以利用现有代码，这些代码将提供用户已经熟悉的用户界面。这些元素还可以帮助您开发看起来像 Android 生态系统一部分的应用。例如，许多应用需要显示任意长的元素列表，且需要能够在列表发生变化时快速有效地重复使用这些元素；这可以是电子邮件列表、联系人列表以及音乐专辑列表，等等。这些应用可以使用支持库 RecyclerView 小部件显示列表。这既可以让应用开发者不必从头开始开发列表，又能确保用户看到一个外观和行为与其他应用中的列表类似的列表。



### （三）支持不同的设备类型

　　Android SDK 为 TV 和穿戴式设备等多种不同的设备类型提供库。应用可以通过相应的支持库为各种平台版本提供功能，且可以在外部屏幕、扬声器和其他目标设备上提供内容。

### （四）一般实用程序

　　Android 支持库提供后向兼容的实用程序功能。应用可以使用这些实用程序功能为各种 Android 系统版本提供相应的用户体验。例如，支持库的权限处理方式取决于运行应用的平台版本。如果平台支持运行时权限模式，这些方法会向用户请求相应的权限；在不支持运行时权限模式的平台版本中，这些方法将在安装时检查是否已获得相应的权限。

## 第二章、设置

　　如何在开发项目中设置 Android 支持库取决于您想要使用的功能，以及您希望应用支持的 Android 平台版本范围。这一小节将指导您下载支持库软件包以及向开发环境中添加库。

### （一）下载支持库

　　Android 支持存储库软件包作为 Android SDK 的辅助组件提供，可以通过 Android SDK 管理器下载。请按照以下说明操作，获取支持库文件。

　　要通过 SDK 管理器下载支持库，请执行以下操作：

    1.启动 Android SDK 管理器。
    2.在 SDK 管理器窗口中，滚动到 Packages 列表末尾，
      找到 Extras 文件夹并展开（如有必要）以显示其内容。
    3.选择 Android Support Repository 项。
    4.点击 Install packages... 按钮。

　　下载后，此工具会将支持库文件安装到您现有的 Android SDK 目录中。库文件位于 SDK 的以下子目录中：

    <sdk根目录>/extras/android/m2repository/com/android/support/ 目录


### （二）选择支持库

　　在将支持库添加到应用之前，确定您想要包含的功能以及希望支持的最低 Android 版本。如需了解有关不同库所提供功能的详细信息，请参阅 **第三章功能**。

### （三）添加支持库

　　要使用支持库，您必须在开发环境中修改应用项目的类路径依赖关系。必须针对想要使用的每个支持库执行该步骤。

　　要向应用项目中添加支持库，请执行以下操作：

> 1.确保已使用 SDK 管理器下载 Android 支持存储库。

> 2.打开应用的 build.gradle 文件。

> 3.将支持库添加到 dependencies 部分。例如，要添加 v4 core-utils 库，请添加以下行：

    dependencies {
    ...
    compile "com.android.support:support-core-utils:24.2.0"
    }

> 　　注意：使用动态依赖关系（例如 palette-v7:24.+）可能会导致意外的版本更新和回归不兼容问题。我们建议明确指定库版本（例如 palette-v7:24.2.0）。


### （四）使用支持库 API

　　为现有框架 API 提供支持的支持库类与框架类通常具有相同的名称，但前者位于 android.support 类软件包中，或带有 *Compat 后缀。

> 注意：使用支持库中的类时，确保从相应的软件包中导入类。例如，应用 ActionBar 类时：

* 使用支持库时为 android.support.v7.app.ActionBar。
* 仅为 API 级别 11 或以上开发时为 android.app.ActionBar。

>　　注：将支持库添加到应用项目后，我们强烈建议使用  [ProGuard 压缩代码和资源](https://developer.android.google.cn/studio/build/shrink-code.html)  工具准备要发布的应用 APK。除了保护您的源代码外， [ProGuard](https://developer.android.google.cn/studio/build/shrink-code.html)  工具还可以从添加到应用的任意库中移除不使用的类，从而使应用的下载大小尽可能小。如需了解详细信息，请参阅  [ProGuard](https://developer.android.google.cn/studio/build/shrink-code.html)。

　　如需使用支持库某些功能的更多指导，请参见 Android 开发者 [培训课程](https://developer.android.google.cn/training/index.html)、[指南](https://developer.android.google.cn/guide/components/index.html) 和示例。如需了解有关支持库中各个类和方法的详细信息，请参阅 API 参考中的 [android.support](https://developer.android.google.cn/reference/android/support/v4/app/package-summary.html) 软件包。

#### 4.1 清单声明变更

　　如果您计划增加现有应用对带有支持库的旧版本 Android API 的向后兼容性，请确保更新应用的清单。

　　具体而言：
> 您应将清单中 <uses-sdk> 标记的 android:minSdkVersion 元素更新为较低的新版本号，举例如下所示：

    <uses-sdk
      android:minSdkVersion="14"
      android:targetSdkVersion="23" />

　　清单设置告知 Google Play 您的应用可以安装在 Android 4.0（API 级别 14）及更高版本的设备上。

> 如果您使用 Gradle 构建文件，构建文件中的 minSdkVersion 设置将替换清单设置。

    apply plugin: 'com.android.application'
    android {
        ...
        defaultConfig {
            minSdkVersion 16
            ...
        }
    ...
    }
在这种情况下，构建文件设置将告知 Google Play 您应用的默认构建变体可以安装在 Android 4.1（API 级别 16）及更高版本的设备上。如需了解有关构建变体的详细信息，请参阅 [构建系统概览](https://developer.android.google.cn/studio/build/index.html) 。

> 注：如果添加多个支持库，则最低的 SDK 版本必须是任意指定库所要求的最高版本。例如，如果您的应用中包含 [v14 Preference 支持库](https://developer.android.google.cn/topic/libraries/support-library/features.html#v14-preference) 和 [v17 Leanback 库](https://developer.android.google.cn/topic/libraries/support-library/features.html#v17-leanback)，则最低的 SDK 版本必须为 17 或更高。

## 第三章、功能


　　Android 支持库软件包含可以添加至应用的多个库。每个库均支持特定范围的 Android 平台版本和功能。

　　本指南介绍了各支持库提供的重要功能和版本支持，从而帮助您决定在应用中添加哪些支持库。一般而言，我们建议添加 **v4 支持库** 和 **v7 appcompat 库**，因为它们支持一系列 Android 版本，并且可以为推荐的用户界面模式提供 API。

　　要使用以下任一库，您必须将库文件下载到 Android SDK 安装位置中。请按照支持库设置中下载支持库的说明完成此步骤。要在应用中添加特定支持库，您还必须执行其他步骤。有关如何在应用中添加支持库的重要信息，请参阅下面各个库内容的末尾部分。

### 3.1 v4 支持库

　　这些库旨在与 Android 2.3（API 级别 9）及更高版本搭配使用。与其他支持库相比，它们包含的 API 集合最大，包括对应用组件、用户界面功能、辅助功能、数据处理、网络连接以及编程实用工具的支持。

　　如需了解有关 v4 支持库所提供类和方法的完整详细信息，请参阅 API 参考中的 [android.support.v4](https://developer.android.google.cn/reference/android/support/v4/app/package-summary.html) 软件包。

    注：在支持库修订版 24.2.0 之前，存在一个 v4 支持库。为了提高效率，此库拆分成多个模块。出于向后兼容的考虑，如果您在 Gradle 脚本中列出了 support-v4，您的 APK 将包含所有的 v4 模块。不过，要减少 APK 大小，我们建议仅列出应用需要的特定模块。

**下面用一张图表示一下v4 support包之间的关系：**

![](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/pic/Support-V4%E5%BA%93%E7%BB%93%E6%9E%84.png?raw=true)


>#### v4 compat 库
　　为众多框架 API 提供兼容性包装器，例如 Context.obtainDrawable() 和 View.performAccessibilityAction()。

　　此库的 Gradle 构建脚本依赖关系标识符如下所示：

    com.android.support:support-compat:24.2.0

>#### v4 core-utils 库
　　提供大量实用程序类，例如 AsyncTaskLoader 和 PermissionChecker。

　　此库的 Gradle 构建脚本依赖关系标识符如下所示：

    com.android.support:support-core-utils:24.2.0

>#### v4 core-ui 库
　　实现各种 UI 相关组件，例如 ViewPager、NestedScrollView 和 ExploreByTouchHelper。

　　此库的 Gradle 构建脚本依赖关系标识符如下所示：

    com.android.support:support-core-ui:24.2.0

>#### v4 media-compat 库
　　向后移植部分媒体框架，包括 MediaBrowser 和 MediaSession。

　　此库的 Gradle 构建脚本依赖关系标识符如下所示：

    com.android.support:support-media-compat:24.2.0

>#### v4 fragment 库
　　添加对使用片段封装用户界面和功能的支持，从而使应用能够提供可以在大屏幕设备与小屏幕设备之间进行调节的布局。此模块依赖于 compat、core-utils、core-ui 和 media-compat。

　　此库的 Gradle 构建脚本依赖关系标识符如下所示：

    com.android.support:support-fragment:24.2.0

### 3.2 Dalvik 可执行文件分包支持库
>　　此库可以为使用多个 Dalvik Executable (DEX) 文件开发应用提供支持。引用超过 65536 个方法的应用须使用 Dalvik 可执行文件分包配置。如需了解有关使用 Dalvik 可执行文件分包的详细信息，请参阅  **[使用超过 6.4 万种方法开发应用](https://developer.android.google.cn/studio/build/multidex.html)**。

　　此库的 Gradle 构建脚本依赖关系标识符如下所示：

    com.android.support:multidex:1.0.0

### 3.3 v7 支持库

　　一些库旨在与 Android 2.3（API 级别 9）及更高版本搭配使用。这些库提供了特定的功能集，并且可以单独添加到应用中，与其他库互不影响。

>#### v7 appcompat 库

　　此库添加了对 **[操作栏](https://developer.android.google.cn/training/appbar/index.html)** 用户界面 **[设计模式](https://developer.android.google.cn/design/patterns/actionbar.html)** 的支持。此库包含对 **[Material Design](https://developer.android.google.cn/design/material/index.html)** 用户界面实现的支持。

    注：此库依赖于 v4 支持库。

　　下面是 v7 appcompat 库中包含的一些关键类：

* [ActionBar](https://developer.android.google.cn/reference/android/support/v7/app/ActionBar.html) - 提供操作栏 [用户界面模式](https://developer.android.google.cn/design/patterns/actionbar.html) 的实现。如需了解有关使用 [操作栏](https://developer.android.google.cn/training/appbar/index.html) 的详细信息，请参阅操作栏开发者指南。(added in version 23.0.0)

* [AppCompatActivity](https://developer.android.google.cn/reference/android/support/v7/app/AppCompatActivity.html) - 添加一个应用 Activity 类，此类可作为使用支持库操作栏实现的 Activity 的基础类。(added in version 24.2.0)

* [AppCompatDialog](https://developer.android.google.cn/reference/android/support/v7/app/AppCompatDialog.html) - 添加一个对话框类，此类可作为 AppCompat 主题对话框的基础类。(added in version 23.0.0)

* [ShareActionProvider](https://developer.android.google.cn/reference/android/support/v7/widget/ShareActionProvider.html) - 包含对可以添加到操作栏中的标准化分享操作（例如电子邮件或发帖至社交应用）的支持。(added in version 24.2.0)

　此库的 Gradle 构建脚本依赖关系标识符如下所示：

    com.android.support:appcompat-v7:24.2.0

>#### v7 cardview 库 (added in version 24.2.0)

　　　此库添加了对 [CardView](https://developer.android.google.cn/reference/android/support/v7/widget/CardView.html) 小部件的支持，让您能够在卡片内显示信息，从而使应用具备一致的外观。这些卡片对 Material Design 实现非常有用，并在电视应用布局中广为使用。

　此库的 Gradle 构建脚本依赖关系标识符如下所示：

    com.android.support:cardview-v7:24.2.0

>#### v7 gridlayout 库 (added in version 24.2.0)

　　下载 Android 支持库后，此库可以添加对 [GridLayout](https://developer.android.google.cn/reference/android/support/v7/widget/GridLayout.html) 类的支持，让您能够使用网状方格安排用户界面元素。如需了解有关 v7 gridlayout 库 API 的详细信息，请参阅 API 参考中的 [android.support.v7.widget](https://developer.android.google.cn/reference/android/support/v7/widget/package-summary.html) 软件包。

　　此库的 Gradle 构建脚本依赖关系标识符如下所示：

    com.android.support:gridlayout-v7:24.2.0

>#### v7 mediarouter 库 (added in version 22.0.0)

　　此库可以提供 [MediaRouter](https://developer.android.google.cn/reference/android/support/v7/media/MediaRouter.html)、[MediaRouteProvider](https://developer.android.google.cn/reference/android/support/v7/media/MediaRouteProvider.html) 和支持 Google Cast **(官网的这个url点不进去。。。)** 的相关媒体类。

　　一般而言，利用 v7 mediarouter 库中的 API，您可以控制当前设备到外部屏幕、扬声器和其他目标设备的媒体渠道和流的路由。此库包含的 API 可以用于发布应用特定的媒体路由提供程序、发现和选择目标设备，以及检查媒体状态，等等。如需了解有关 v7 mediarouter 库 API 的详细信息，请参阅 API 参考中的 [android.support.v7.media](https://developer.android.google.cn/reference/android/support/v7/media/package-summary.html) 软件包。

　　此库的 Gradle 构建脚本依赖关系标识符如下所示：

    com.android.support:mediarouter-v7:24.2.0

　　支持库 r18 中引入的 v7 mediarouter 库 API 在后续版本的支持库中可能会发生更改。目前，我们建议仅使用与 Google Cast 有关的库。

>#### v7 palette 库 (added in version 22.0.0)

　　v7 palette 支持库包含 [Palette](https://developer.android.google.cn/reference/android/support/v7/graphics/Palette.html) 类，此类让您可以从图像中抽取突出颜色。例如，音乐应用可以使用 [Palette](https://developer.android.google.cn/reference/android/support/v7/graphics/Palette.html) 对象从专辑封面抽取主要颜色，然后使用这些颜色创建一个色彩协调的歌曲标题卡。

　　此库的 Gradle 构建脚本依赖关系标识符如下所示：

    com.android.support:palette-v7:24.2.0

>#### v7 recyclerview 库 (added in version 22.0.0)

　　 recyclerview库添加了 [Recyclerview](https://developer.android.google.cn/reference/android/support/v7/widget/RecyclerView.html) 类。此类能够为 [RecyclerView小部件](https://developer.android.google.cn/training/material/lists-cards.html) 提供支持，RecyclerView 是一种通过提供有限的数据项窗口有效显示大数据集的视图。

　　此库的 Gradle 构建脚本依赖关系标识符如下所示：

    com.android.support:recyclerview-v7:24.2.0

>#### v7 Preference 支持库 (added in version 23.0.0)

　　[首选项软件包](https://developer.android.google.cn/reference/android/support/v7/preference/package-summary.html) 提供的 API 支持添加 preference 对象（例如 [CheckBoxPreference](https://developer.android.google.cn/reference/android/support/v7/preference/CheckBoxPreference.html) 和 [ListPreference](https://developer.android.google.cn/reference/android/support/v7/preference/ListPreference.html)），方便用户修改 UI 设置。

　　v7 Preference 库添加了对接口（例如 [Preference.OnPreferenceChangeListener](https://developer.android.google.cn/reference/android/support/v7/preference/Preference.OnPreferenceChangeListener.html) 和 [Preference.OnPreferenceClickListener](https://developer.android.google.cn/reference/android/support/v7/preference/Preference.OnPreferenceClickListener.html)）以及类（例如 [CheckBoxPreference](https://developer.android.google.cn/reference/android/support/v7/preference/CheckBoxPreference.html) 和 [ListPreference](https://developer.android.google.cn/reference/android/support/v7/preference/ListPreference.html)）的支持。

　　此库的 Gradle 构建脚本依赖关系标识符如下所示：

    com.android.support:preference-v7:24.2.0

### 3.4 v8 支持库
　　此库旨在与 Android 2.3（API 级别 9）及更高版本搭配使用。此库提供了特定的功能集，并且可以单独添加到应用中，与其他库互不影响。

* v8 renderscript 库

　　此库旨在与 Android 2.3（API 级别 9）及更高版本搭配使用。它添加了对 **[RenderScript](https://developer.android.google.cn/guide/topics/renderscript/compute.html)** 计算框架的支持。**[android.support.v8.renderscript](https://developer.android.google.cn/reference/android/support/v8/renderscript/package-summary.html)** 软件包中包含这些 API。请注意，在应用中添加这些 API 的步骤与添加其他支持库 API 迥然不同。如需了解有关在应用中使用这些 API 的详细信息，请参阅 **[RenderScript](https://developer.android.google.cn/guide/topics/renderscript/compute.html#access-rs-apis)** 开发者指南。

> 注：Android Studio 和 Gradle 构建支持使用带支持库的 RenderScript。renderscript 库位于 build-tools/$VERSION/renderscript/ 文件夹中。

以下示例显示了此库的 Gradle 构建脚本属性：

    defaultConfig {
        renderscriptTargetApi 18
        renderscriptSupportModeEnabled true
    }

### 3.5 v13 支持库 (added in version 22.0.0)

　　此库旨在用于 Android 3.2（API 级别 13）及更高版本。它添加了对带有 ([FragmentCompat](https://developer.android.google.cn/reference/android/support/v13/app/FragmentCompat.html)) 类和其他片段支持类的 [Fragment](https://developer.android.google.cn/guide/components/fragments.html) 用户界面模式的支持。如需了解有关片段的详细信息，请参阅 [Fragment](https://developer.android.google.cn/guide/components/fragments.html) 开发者指南。如需了解有关 v13 支持库 API 的详细信息，请参阅 API 参考中的 **[android.support.v13](https://developer.android.google.cn/reference/android/support/v13/app/package-summary.html)** 软件包。

　　此库的 Gradle 构建脚本依赖关系标识符如下所示：

    com.android.support:support-v13:24.2.0

### 3.6 v14 Preference 支持库 (added in version 23.0.0)

　　[android.support.v14.preference](https://developer.android.google.cn/reference/android/support/v14/preference/package-summary.html) 软件包提供的 API 添加了对首选项接口（例如 [PreferenceFragment.OnPreferenceStartFragmentCallback](https://developer.android.google.cn/reference/android/support/v14/preference/PreferenceFragment.OnPreferenceStartFragmentCallback.html) 和 [PreferenceFragment.OnPreferenceStartScreenCallback](https://developer.android.google.cn/reference/android/support/v14/preference/PreferenceFragment.OnPreferenceStartScreenCallback.html)）以及类（例如 [MultiSelectListPreference](https://developer.android.google.cn/reference/android/support/v14/preference/MultiSelectListPreference.html) 和 [PreferenceFragment](https://developer.android.google.cn/reference/android/support/v14/preference/PreferenceFragment.html)）的支持。如需了解有关 v14 Preference 支持库 API 的详细信息，请参阅 API 参考中的 [preference](https://developer.android.google.cn/reference/android/support/v14/preference/package-summary.html) 软件包。

　　此库的 Gradle 构建脚本依赖关系标识符如下所示：

    com.android.support:preference-v14:24.2.0

### 3.7 适用于电视的 v17 Preference 库
### 3.8 v17 Leanback 库

　　[android.support.v17.leanback](https://developer.android.google.cn/reference/android/support/v17/leanback/package-summary.html) 软件包提供的 API 支持在电视设备上构建用户界面。它为电视应用提供了一些重要的小部件。一些值得注意的类包括：

* [BrowseFragment](https://developer.android.google.cn/reference/android/support/v17/leanback/app/BrowseFragment.html)   一种用于创建主要布局的片段，主要布局用于浏览类别和媒体项目。(added in version 22.0.0)

* [DetailsFragment](https://developer.android.google.cn/reference/android/support/v17/leanback/app/DetailsFragment.html)   用于 Leanback 细节屏幕的包装器片段。(added in version 22.0.0)

* [PlaybackOverlayFragment](https://developer.android.google.cn/reference/android/support/v17/leanback/app/PlaybackOverlayFragment.html)   用于显示播放控件及相关内容的 [DetailsFragment](https://developer.android.google.cn/reference/android/support/v17/leanback/app/DetailsFragment.html) 子类。(added in version 22.0.0,从api 25.1.0起废弃)

* [SearchFragment](https://developer.android.google.cn/reference/android/support/v17/leanback/app/SearchFragment.html)   用于处理搜索的片段。（added in version 22.0.0）片段可以接收用户的搜索请求并将其传递给应用提供的 [SearchResultProvider](https://developer.android.google.cn/reference/android/support/v17/leanback/app/SearchFragment.SearchResultProvider.html)，    [SearchResultProvider](https://developer.android.google.cn/reference/android/support/v17/leanback/app/SearchFragment.SearchResultProvider.html) 可以将搜索结果返回给 [SearchFragment](https://developer.android.google.cn/reference/android/support/v17/leanback/app/SearchFragment.html)，后者会将结果渲染到 [RowsFragment](https://developer.android.google.cn/reference/android/support/v17/leanback/app/RowsFragment.html) 中。

　　此库的 Gradle 构建脚本依赖关系标识符如下所示：

    com.android.support:leanback-v17:24.2.0

### 3.9 注解支持库

　　[注解软件包](https://developer.android.google.cn/reference/android/support/annotation/package-summary.html) 提供的 API 支持向应用中添加注解元数据。

　　此库的 Gradle 构建脚本依赖关系标识符如下所示：

    com.android.support:support-annotations:24.2.0

### 3.10 设计支持库 (added in version 22.2.0)

　　[设计软件包](https://developer.android.google.cn/reference/android/support/design/package-summary.html) 提供的 API 支持向应用中添加 Material Design 组件和模式。

　　设计支持库添加了对应用开发者依赖的各种 Material Design 组件和模式的支持，

　　例如：

　　[抽屉式导航栏NavigationView](https://developer.android.google.cn/reference/android/support/design/widget/NavigationView.html)、(added in version 22.2.0)

　　[底部导航栏BottomNavigationView](https://developer.android.google.cn/reference/android/support/design/widget/BottomNavigationView.html)、(added in version 25.0.0)

　　[折叠布局CollapsingToolbarLayout](https://developer.android.google.cn/reference/android/support/design/widget/CollapsingToolbarLayout.html)、(added in version 22.2.0)

　　[浮动操作按钮FAB](https://developer.android.google.cn/reference/android/support/design/widget/FloatingActionButton.html)、(added in version 22.2.0)

　　快捷信息栏、

　　[标签页TabLayout](https://developer.android.google.cn/reference/android/support/design/widget/TabLayout.html)(added in version 22.2.0)

　　此库的 Gradle 构建脚本依赖关系标识符如下所示：

    com.android.support:design:24.2.0

### 3.11 自定义标签页支持库

　　[自定义标签页软件包](https://developer.android.google.cn/reference/android/support/customtabs/package-summary.html) 提供的 API 支持向应用中添加自定义标签页并对其进行管理。

　　自定义标签页支持库添加了对 [CustomTabsService](https://developer.android.google.cn/reference/android/support/customtabs/CustomTabsService.html) 和 [CustomTabsCallback](https://developer.android.google.cn/reference/android/support/customtabs/CustomTabsCallback.html)等各种类的支持。

　　此库的 Gradle 构建脚本依赖关系标识符如下所示：

    com.android.support:customtabs:24.2.0

### 3.12 百分比支持库

　　[百分比软件包](https://developer.android.google.cn/reference/android/support/percent/package-summary.html) 提供的 API 支持向应用中添加基于百分比的尺寸并对其进行管理。

　　百分比支持库添加了对 [PercentLayoutHelper.PercentLayoutParams](https://developer.android.google.cn/reference/android/support/percent/PercentLayoutHelper.PercentLayoutParams.html) 接口和各种类的支持，例如 [PercentFrameLayout](https://developer.android.google.cn/reference/android/support/percent/PercentFrameLayout.html) 和 [PercentRelativeLayout](https://developer.android.google.cn/reference/android/support/percent/PercentRelativeLayout.html)。

　　此库的 Gradle 构建脚本依赖关系标识符如下所示：

    com.android.support:percent:24.2.0

### 3.13 适用于电视的建议支持库

　　[应用建议软件包](https://developer.android.google.cn/reference/android/support/app/recommendation/package-summary.html) 提供的 API 支持向电视设备上运行的应用中添加内容建议。

　　应用库添加了对注解（例如 [ContentRecommendation.ContentMaturity](https://developer.android.google.cn/reference/android/support/app/recommendation/ContentRecommendation.ContentMaturity.html) 和各种类（例如 [ContentRecommendation](https://developer.android.google.cn/reference/android/support/app/recommendation/ContentRecommendation.html) 和 [RecommendationExtender](https://developer.android.google.cn/reference/android/support/app/recommendation/RecommendationExtender.html)）的支持。

　　此库的 Gradle 构建脚本依赖关系标识符如下所示：

    com.android.support:recommendation:24.2.0