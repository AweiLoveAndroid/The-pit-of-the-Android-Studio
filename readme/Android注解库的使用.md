# Android 中注解的使用

## 前言

Android Support Library（安卓注解库） 从 19.1 版本开始引入了一个新的注解库，其中包含了很多的元注解，使用它们修饰我们的代码， 可以让我们提高程序的开发效率，让我们更早的发现问题。以及对代码施以规范，让代码更加有可读性。这篇文章就来简单了解下这些注解，以及其使用。如有错误和遗漏，欢迎留言和补充～

> 注：现在我们新建项目直接就依赖了 support.appcompat 包，其中已经依赖了 annotations 包。如果你的项目中写如下注解报错，可以添加注解包：
 
    dependencies {
        compile 'com.android.support:support-annotations:22.2.0'
    }

## @IntDef & @StringDef

替代 Java 中枚举的注解，以 @IntDef 为例，定义和使用如下：

    @IntDef({RED, BLUE, YELLOW})
    @Retention(RetentionPolicy.SOURCE)
    public @interface LightColors{};

    public static final int RED = 1;
    public static final int BLUE = 2;
    public static final int YELLOW = 3;

    public void setColor(@LightColors int color){
    }

* @interface：声明新的枚举注解类型。
* @Retention(RetentionPolicy.SOURCE)：告知编译器不将枚举的注解数据存储在 .class 文件中。

如果允许常量与标志（例如：|、& 和 ^ 等等）相结合，则我们可以使用 flag 属性，如：

    @IntDef(flag = true, value = {RED, BLUE, YELLOW})

使用：

    setColor(RED | BLUE);

## @Nullable & @NonNull

@Nullable：注解的元素可以为 null。
@NonNull：注解的元素不可以为 null。
上面的注解可以修饰如下元素：

* 1，方法参数。如：
>
    @Nullable
    private String data;

* 2，方法的返回值。 如：
>
    @Nullable
    public String getData(){
        return data;
    }

* 3，成员属性。如：
>
    public void setData(@Nullable String data){
    }

当用空的参数传给被 @NonNull 修饰的方法参数的方法时，会给出如下警告提示（编译不会报错）：

    passing "null" argument to parameter annotated as @NotNull

## @FloatRange & @IntRange

@FloatRange 和 @IntRange 是用于限定范围的注解。其中 @FloatRange 是限定 float 类型的，而 @IntRange 是限定 int 类型的。它们同上注解一样，可以修饰方法参数、方法返回值、成员属性。

以 @IntRange 为例，修饰方法参数的定义如下：

    public void setAge(@IntRange(from = 1, to = 180) int age){
    }

如果调用该方法传的参数不在 1 - 180 的范围内， 如：setAge(0)，那么编译会直接报如下错：

    value must be ≥ 1 and ≤ 180 (was 0)

## @Size

@Size 注解的作用是限定长度的，同上注解一样，可以修饰方法参数、方法返回值、成员属性。

限定字符串的长度：

    public void setData(@Size(4) String data){
    }

当传入的字符串长度不等于 4 时，编译器会直接报错：

    Length must be exactly 4 

限定数组的长度：

    public void setData(@Size(4) int[] data){
    }

特殊的限定，如限定为 2 的倍数：

    public void setData(@Size(multiple = 2) int[] data){
    }

限定最小的长度：

    @Size(min = 2)

限定最大的长度：

    @Size(max = 2)

等同于 @Size(2) 写法：

    @Size(value = 2)

## @RequiresPermission

该注解作用是表明方法所执行的内容需要权限。如需要单个权限：

    @RequiresPermission(Manifest.permission.CALL_PHONE)
        private void callPhone(String phone){
    }

需要一组权限：

    @RequiresPermission(allOf = {
        Manifest.permission.READ_EXTERNAL_STORAGE,
        Manifest.permission.WRITE_EXTERNAL_STORAGE})
    public static final void copyFile(String dest, String source) {
        ...
    }

对于 intent 权限，我们可以定义在 intent 操作名称的字符串上：


    @RequiresPermission(android.Manifest.permission.BLUETOOTH)
    public static final String ACTION_REQUEST_DISCOVERABLE =
            "android.bluetooth.adapter.action.REQUEST_DISCOVERABLE";

对于需要单独读写权限的内容提供程序的权限，我们可以在 **@RequiresPermission.Read** 或 **@RequiresPermission.Write** 注解中包含每个权限要求：

    @RequiresPermission.Read(@RequiresPermission(READ_HISTORY_BOOKMARKS))
    @RequiresPermission.Write(@RequiresPermission(WRITE_HISTORY_BOOKMARKS))
    public static final Uri BOOKMARKS_URI = Uri.parse("content://browser/bookmarks");

如果权限依赖于提供给方法参数的特定值，那么可以对参数本身使用 @RequiresPermission 而不用列出具体的权限，如 startActivity(intent) 方法：

    public abstract void startActivity(@RequiresPermission Intent intent, @Nullable Bundle) {...}

当我们使用这种方式（间接权限）时，构建工具将执行数据流分析以检查传递到方法的参数是否具有任何 @RequiresPermission 注解。如：

    Intent intent = new Intent(Intent.ACTION_CALL);
    intent.setData(Uri.parse("tel:1234567890"));
    startActivity(intent);

这里的 startActivity(intent) 就直接报错了：

    call requires permission which may be rejected by user: code should explicitly check to see if permission is available (with 
    `checkPermission`) or explicitly handle a potential `SecurityException`

因为 Intent.ACTION_CALL 中标记了权限注解：

    @SdkConstant(SdkConstantType.ACTIVITY_INTENT_ACTION)
    @RequiresPermission(Manifest.permission.CALL_PHONE)
    public static final String ACTION_CALL = "android.intent.action.CALL";

## @CheckResult

@CheckResult 注解是作用于方法上的，作用是检验有没有处理返回值。如果没有处理返回值则会报错。

    @CheckResult
    public String getData(String data) {
        return data.trim();
    }


## 线程注解


线程注解可以检查某个方法是否从特定类型的线程调用。支持以下线程注解：

##### @MainThread：表示标记的方法只应在主线程调用。如果标记的是一个类，那么该类中的所有方法都应该是在主线程被调用。例：（通常，应用程序的主线程也是 Ui 线程。但是，在特殊情况下，应用程序的主线程可能不是其 Ui 线程）

    @MainThread
    public void deliverResult(D data) { ... }

##### @UiThread：表示标记的方法或构造函数只应该在 Ui 线程上调用。如果标记的是一个类，那么该类中的所有方法都应是在 Ui 线程被调用。例：

    @UiThread
    public abstract void setText(@NonNull String text) {...}

##### @WorkerThread：表示标记的方法只应该在工作线程上调用。如果标记的是一个类，那么该类中的所有方法都应是在一个工作线程上调用。例：

    @WorkerThread
    protected abstract FilterResults performFiltering(CharSequence constraint);

##### @BinderThread：表示标记的方法只应在绑定线程上调用。如果标记的是一个类，那么该类中的所有方法都应是在绑定线程被调用。例：

    @BinderThread
    public BeamShareData createBeamShareData() { ... }

##### @AnyThread：表示可以从任何线程调用带标记的方法。如果标记的是一个类，那么该类中的所有方法都可以从任何线程中调用。例：

    @AnyThread
    public void deliverResult(D data) { ... }

> 构建工具会将 @MainThread 和 @UiThread 注解视为可以互换，因此，我们可以从 @MainThread 方法调用 @UiThread 方法，反之亦然。不过如果系统应用在不同线程上带有多个试图，Ui 线程可与主线程不同。因此，我们应该使用 @UiThread 标注于应用的视图层次结构关联的方法，使用 @MainThread 仅标注于应用生命周期关联的方法。

## 资源注解

在 Android 中几乎所有的资源都有其对于的 id，我们在使用的时候可以直接通过 id 来，如：

    textView.setText(getResources().getText(R.string.app_name));

但是这样如果没有写指定的资源注解的话就会风险，比如随便传了个 0，那么就会找不到对应的资源。
为了避免由于自己的粗心大意而引发的错误，我们就可以使用资源注解了，如：

    public int getText(@StringRes int id){
    }

这样当我们调用该方法时，如果传递的参数并不是 String 类型的资源 id，那么编译器就会报错提示。

除了 **@StringRes** 资源注解外，还有：

    @IntegerRes：R.integer 类型资源。
    @AnimatorRes：R.animator 类型资源。
    @AnimRes：R.anim 类型资源。
    @ArrayRes：R.array 类型资源。
    @AttrRes：R.attr 类型资源。
    @BoolRes：R.bool 类型资源。
    @ColorRes：R.color 类型资源。
    @DimenRes：R.dimen 类型资源。
    @DrawableRes：R.drawable 类型资源。
    @FractionRes：R.fraction 类型资源。（百分比）
    @IdRes：R.id 类型资源。
    @InterpolatorRes：R.interpolator 类型资源。（插值器）
    @LayoutRes：R.layout 类型资源。
    @MenuRes：R.menu 类型资源。
    @PluralsRes：R.plurals 类型资源。（复数）
    @RawRes：R.raw 类型资源。
    @StyleableRes：R.styleable 类型资源。
    @StyleRes：R.style 类型资源。
    @TransitionRes： R.transition 类型资源。
    @XmlRes：R.xml 类型资源。
    @AnyRes：未知资源。（表示自己不知道是什么类型的资源。比如有可能为 R.drawable 也有可能是 R.string。）

## @ColorInt

@ColorInt 注解的作用为：限定颜色值。（ARGB：0xAARRGGBB）

    public void setColor(@ColorInt int color) {

    }

如果直接使用资源 id，则会报错，如下：

    setColor(R.color.colorAccent)// 报错

正确的使用是：

    setColor(0xFFFF00FF);  

如果要使用资源 id，则可以通过 ContextCompat.getColor() 方法来：

    setColor(ContextCompat.getColor(context, R.color.colorAccent));

## @CallSuper

该注解用于修饰方法，表示重写该方法时必须调用 super 方法。如 onCreate() 方法：

    @CallSuper
    protected void onCreate(Bundle savedInstanceState) {
    }

重写 onCreate() 方法时，必须调用 super 方法：

    super.onCreate(savedInstanceState);

否则报错。

## @VisibleForTesting & @Keep

使用 @VisibleForTesting 和 @Keep 注解可以表示方法、类、或字段的可访问性。

##### @VisibleForTesting：该注解只起到一个注释的作用，告诉其他开发者被标记的代码为什么有这么大的可见程度（为了测试方便）。因此，经常用来修饰 public 或 protected，用来修饰 private 并不会报错，但是没有意义。

##### @Keep：标记的指定代码在混淆时不会被混淆。


--------
参考：
https://developer.android.com/studio/write/annotations.html?hl=zh-cn
http://droidyue.com/blog/2016/08/14/android-annnotation/