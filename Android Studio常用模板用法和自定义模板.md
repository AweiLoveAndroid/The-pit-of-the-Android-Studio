# Android Studio常用模板用法和自定义模板

________________

## 一、工程目录模板

### Android Studio 新建一个 **project** 时并没有将 Android 开发中常用的文件目录全部生成，比如默认只生成了一个 drawable文件夹，常用的 drawable-hdpi等文件夹需要我们自己去创建。再比如values目录下的dimens.xml，res目录下的anim文件夹都是没有的，需要我们手动去创建。这样一来，自己创建浪费时间，同时创建的目录名字错了，编译肯定会报错。所以为了效率和安全起见，我们需要把工程目录模板进行修改，达到创建 project 时就可以生成完整的目录结构，不再手动去创建的目的。


> ##### 1.　进入 Android Studio 安装目录，依次进入 plugins --> android --> lib --> templates --> gradle-projects --> NewAndroidModule --> root --> res --> values，在values文件夹下创建 dimens.xml 文件夹，写入以下内容:

    <?xml version="1.0" encoding="utf-8"?>
    <resources>
   
    </resources>

   
> ##### 2.　进入 Android Studio 安装目录，依次进入 plugins --> android --> lib --> templates --> gradle-projects --> NewAndroidModule，然后用编辑器打开 recipe.xml.ftl文件，并加入以下配置,如下图红色框框所示


![修改NewAndroidModule自带的模板](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/%E4%BF%AE%E6%94%B9NewAndroidModule%E8%87%AA%E5%B8%A6%E7%9A%84%E6%A8%A1%E6%9D%BF.png?raw=true)



    说明：
    （1）dependency 这个意思是配置依赖库的url，默认的只有一个v7包，我这里新增了一个v4包的依赖
    （2）mkdir 意思是创建目录
    （3）解释一下以下这段代码的意思：
         <instantiate from="root/res/values/dimens.xml"
                   to="${escapeXmlAttribute(resOut)}/values/dimens.xml" />
        意思是把 模板的root/res/values/demins.xml 这个路径里面的dimens.xml拷贝到创建的项目资源目录下面的values/dimens.xml



> ##### 3.　新建一个project看看效果如何：（图片的demin.xml之前打错了，以后有时间把图片换掉，更新一下）

![效果图](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/%E6%95%88%E6%9E%9C%E5%9B%BE.png?raw=true)





________________

## 二、Live Templates 活动模板（暂且翻译为 灵活的模板 比较好）

#### （一）打开方法： 点击菜单File --> 点击Settings --> 选择Editor --> Code Style --> Live Templates，这里面配置了常用代码，比如log,System.out.println,for循环等


		由于太多，下面只列举开发中经常用到的：（后面写注释“//修改了快捷键名称” 表示修改了快捷键名称，不再使用默认的快捷键，没修改的是默认的快捷键）


> **（1）Android 安卓有关的**

	 const 常量
	 fbc findViewById
	 fore 创建foreach循环  //修改了快捷键名称
	 gone 设置View为gone  //修改了快捷键名称
	 IntentView 用ACTION_VIEW创建一个Intent
	 key    结果是 private static final String KEY_$value$ = "$value$";
	 newInstance 使用参数创建一个新的Fragment实例
	 co 生成构造方法  //修改了快捷键名称
	 cop 私有构造方法  //修改了快捷键名称
	 rgS 从资源文件getString(R.string.XXX)
	 rouiT 生成runOnUIThread
	 sbc 生成方格状注释代码块
	 Sfmt 格式化String String.format(XXX)
	 starter 创建一个静态的start（...）方法来启动一个Activity
	 toal 创建一个长时间的Toast  //新增
	 toas 创建一个Toast  //修改了快捷键名称
	 vi 设置View为visible  //修改了快捷键名称


> **（2）AndroidComments 安卓组件**

    fix    添加 // FIXME    //修改了快捷键名称
    do    添加 // TODO      //修改了快捷键名称


> **（3）AndroidLog 安卓打log有关的**

    logd  Log.d(TAG, String)
    loge  Log.e(TAG, String)
    logi  Log.i(TAG, String)
    logm  打印方法名称及其参数,Log.d(TAG,XXX)
    logr  打印方法的结果
    
    tag  根据当前的类名生成一个静态logtag  //修改了快捷键名称,修改了内容,描述改为“根据当前类生成一个TAG”
    private static final String TAG = $className$.class.getSimpleName();
    
    logw  Log.w(TAG,String,Exception)
    logf  Log.wtf(TAG, String, Exception)  //修改了快捷键名称


> **（4）iterations 快速生成循环和迭代器代码块**

    for 示例：for (int i = 0; i < ; i++) {}  //修改了快捷键名称

    fora 示例：遍历数组  //修改了快捷键名称
    for (int i = 0; i < Array.length; i++) {
        int i1 = Array[i];
    }

    forc 示例：使用iterator遍历一个容器变量  //修改了快捷键名称
    for (Iterator iterator = collection.iterator(); iterator.hasNext(); ) {
        Object next = iterator.next();
    }//这个是遍历一个容器变量的，直接让容器返回一个iterator进行遍历

    whe 示例：while循环遍历枚举内容  //修改了快捷键名称
    while (枚举类.hasMoreElements()) {
        Object nextElement = 枚举类.nextElement();
    }

    iter 示例：遍历选中状态下的set  //修改了快捷键名称
    for (int i : FOCUSED_STATE_SET) {...}

    whi 示例：while循环使用iterator进行遍历  //修改了快捷键名称
    while (iterator.hasNext()) {
        Object next = iterator.next();
    }//获取到了迭代器对象后，对迭代器进行遍历操作

    forl 示例：遍历list对象里面的内容  //修改了快捷键名称
    for (int i = 0; i < list.size(); i++) {
        Object o = list.get(i);
    }

    foraa 示例：倒叙遍历数组  //修改了快捷键名称
    for (int i = Array.length - 1; i >= 0; i--) {
        int i1 = FOCUSED_STATE_SET[i];
    }

    //以下这两个用的少，只是把快捷键改了一下，方便使用
    fors 对StringTokenizer遍历  //修改了快捷键名称
    forv 对Vector遍历  //修改了快捷键名称
 
 
> **（5）Other 其他的**

    geti 获取到当前的实例 示例：
    public static MainActivity getInstance() {
        return ;
    }

    ifn 生成if null代码块 示例： if (某变量 == null) {....}
    inn 生成if not null代码块 示例：if (某变量 != null) {....}
    
    inst 判断某变量是不是某个类的实例对象 示例：
    if ($EXPR$ instanceof $TYPE$) {
        $TYPE$ $VAR1$ = ($TYPE$)$EXPR$; $END$
    }

    lazy 执行延迟初始化，就是对象直到用的时候才进行初始化操作 示例：
    if (savedInstanceState == null) {
        savedInstanceState = new Bundle();
    }

    st 获取数组最后一个元素 示例： arr[arr.length - 1]
    mn 比较两个变量较小值 Math.min(var2,var3);
    mx 比较两个变量较大值 Math.max(var2,var3);
    
    main 生成一个main()函数的代码块
    public static void main(String[] args){ 。。。。 }  //修改了快捷键名称
    
    toar 把collection的对象存储到一个数组里面 示例：something.toArray(new collection[something.size()])


> **（6）plain 关于修饰符**

    psf     public static final 
    psfi    public static final int 
    psfs    public static final String 
    St      String 
    thr     throw new 

> **（7）surround 代码块被什么包裹。。**

    I 被迭代器包裹 默认的是：
    for (Object o :) {

    }


> **（8）output（我改成了SystemOut）  //修改了组的名称**

    sysr 示例： System.err.println("example")  //修改了快捷键名称
    sysf 示例： System.out.printf("example")  //修改了快捷键名称
    syso 示例： System.out.println("example")  //修改了快捷键名称
    sysom 打印当前类的当前方法名, 示例：System.out.println("MainActivity.onCreate");  //修改了快捷键名称
    
    sysop 打印当前方法的所有参数列表及其值, 示例：
    System.out.println("savedInstanceState = [" + savedInstanceState + "]");  //修改了快捷键名称

    sysov 打印一个变量值, 示例：System.out.println("arr = "+ arr);  //修改了快捷键名称


#### （二）自定义活动模板

		我自定义了几个常用功能，放在custom组下面，如图所示：

![自定义活动模板](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/%E8%87%AA%E5%AE%9A%E4%B9%89%E6%B4%BB%E5%8A%A8%E6%A8%A1%E6%9D%BF.png?raw=true)

    han: 自动生成一个类继承Handler
    swi  自定义switch/case选择语句
    toli 把数组转成集合（自定义的，后面会讲解怎么自定义的）
    zs:注释模板


> **（1）点击右边的“+” 加号，选择 Template Group，创建一个组，输入一个组名，点OK**

> **（2）找到刚创建的组，点击右边的“+” 加号，选择 Live Template，创建一个模板**

> **（3）Abbreviation后面的输入框输入一个快捷键名称，Description后面的输入框输入描述**

> **（4）点击下方的Define，勾选java前面的复选框**

> **（5）Template text 输入自定义模板的代码内容**

> **（6）点击右边的Edit variables，编辑指定的变量名**

### 具体如下图所示：

![自定义活动模板](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/%E8%87%AA%E5%AE%9A%E4%B9%89%E6%A8%A1%E6%9D%BF%E6%AD%A5%E9%AA%A4.png?raw=true)



________________

## 三、File and Code Templates 文件和代码模板，这里讲一下自定义注释模板

#### （一） 类注释

    原则上编写完成每个类都要有一个头部注释，标注类的功能描述，作者，联系方式和修改日期等。对自己的代码负责。
    
头部注释的添加有两种方式：

> **（1）第一种方式，可以在AS中，Settings → Editor → File and Code Templates → Includes → File Header，输入：**

     /**
      * 描述：添加类的描述
      * @author yourName
      * @e-mail XXX@XX.com
      * @time   ${DATE}
      */

这样便可在每次新建类的时候自动加上该头注释，如下图所示。

![自定义类注释模板方式1](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/%E8%87%AA%E5%AE%9A%E4%B9%89%E7%B1%BB%E6%B3%A8%E9%87%8A%E6%A8%A1%E6%9D%BF%E6%96%B9%E5%BC%8F1.png?raw=true)



> **（2）第二种方式，在Settings → Editor → Live Templates中配置，如下图所示：**
> 

![自定义类注释模板方式2](https://github.com/AweiLoveAndroid/The-pit-of-the-Android-Studio/blob/master/%E8%87%AA%E5%AE%9A%E4%B9%89%E7%B1%BB%E6%B3%A8%E9%87%8A%E6%A8%A1%E6%9D%BF%E6%96%B9%E5%BC%8F2.png?raw=true)

关于这里的$DATE$ ，点击右边的Edit variables，属性配置成date()

这种方式是配置模板和对应的快捷键，比如我的配置完成后在类的开头输入 **lzw** 回车就会自动生成对应的注释模板：

#### （二） 方法注释

    原则上每一个成员方法（包括自定义成员方法、覆盖方法、属性方法）的方法头都必须做方法头注释。
    在方法前一行输入/** + 回车或者设置Fix doc comment(Settings → Keymap → Fix doc  comment)快捷键，
    AS便会帮你生成模板，我们只需要补全参数即可。


________________

## 四、自定义UI模板，新建project或者module的时候，右键可以快速生成模板，比如点击新建Activity，可以选择EmptyActivity等。。

**这个我也没做太多研究，可以参考文章 [AndroidStudioTemplate](http://www.jcodecraeer.com/a/opensource/2015/0205/2418.html)**

**改文章对应的github地址是： [AndroidStudioTemplate](https://github.com/gabrielemariotti/AndroidStudioTemplate)**

