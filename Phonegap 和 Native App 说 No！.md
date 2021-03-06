Phonegap 环境配置
========

目前要开发 Web App 还是有比较多的选择的 如 Phonegap、MUI、AppCan，接下来以 **Web前端开发工程师** 的角度来一个 Phonegap 的<code> First Blood </code>

### 一、开发环境：

这里先以 Windows 为例：

##### ![Node js 安装10.35][15] 

**Node.js** [官网下载][1]，[百度云盘 版本号：10.35 for x64][4]

安装完成后（目前已经整合了 *NPM* ），最好在系统变量 <kbd>Path</kbd> 中加入安装路径；

    $ node -v
    v0.10.35
    $ npm -v
    1.4.28

##### ![ADT][14] 

**Adroid [ADT Bundle for Windows][2]** ，<img align="absmiddle" alt="gift" height="20px" src="https://assets-cdn.github.com/images/icons/emoji/gift.png" title="gift" width="20px">[百度云下载 sdk版本号:135.1641136][3]：

下载完成后设置路径，比如： <code>F:\Android SDK\adt-win-x64-135\</code> 用来安装 SDK 软件
<code> F:\Android SDK\local-sdk</code> 用来安装 sdk 组件 （都随意……）

安装不是很慢是特别慢，幸好是无人值守型……

在安装完成后，第一次启动的会显示 <code>Fetching Android SDK component information</code>，然后在 <code> Setup Wizard - Downloading Components </code> 界面下面开始下载 Andorid SDK，如果感觉被“qiang”，（组件下载特别的缓慢甚至中断报错）[请移步这里][9]

或者请参考网友们的方法：
a：关闭安装向导（不行？那就结束进程吧）；
b：打开 Android Studio 安装目录的 <code>F:\Android SDK\adt-win-x64-135\bin</code> 目录下面的 <kbd>idea.properties</kbd> 文件，添加一条配置项：禁用开始运行向导；

    # by highsea 2015-1-4
    disable.android.first.run=true

在 <code> F:\Android SDK\local-sdk</code> 下有个 <code>SDK Manager.exe</code> 另外 <code>AVD Manager.exe</code> 是模拟器，打开 Manager 是一个组件包管理器；如果有安装失败的请重试。

> 设置 Android SDK Manager 代理：
> 首先打开 组件管理器 依次展开： <code>Tools > options </code> 在弹出的 Settings 窗口中选择 Http Proxy Server 填入： <code>mirrors.neusoft.edu.cn</code> Port 中填入 <code>80</code> 并选中 Others 选项中的 第一项；最后 单击 Close 关闭，并返回。

![Manager 组件包管理器][24]

> 注：上图中的 组件是远远不够的，请根据实际开发扩展

##### ![jdk安装 7u71][13]

 **JDK**  [官网下载][6]，[百度云盘 jdk 7u71 x64][6]

如果你还在用6请升级到7，不然在安装 Android SDK 会报错

接着 <kbd>Path</kbd> 中加入如下路径：

    %java_home%/bin;

设置系统变量，变量名： <code> JAVA_HOME </code> ；变量值： 

    C:\Program Files\Java\jdk1.7.0_71   

##### ![Sublime text 安装][16] 

**IDE/编辑器** ，自选，推荐 [Sublime Text 2 :ST2 2.0.2 X64 ][7] 相关[插件请移步这里][10]

##### ![Eclipse for jee 安装][17]

**安装Eclipse** [官网下载][12]，[百度云盘 jee][19]

> 区别： Eclipse有许多版本，最常见的就是 Eclipse IDE for Java Developers 与Eclipse IDE for Java EE Developers 他们都可以用来开发 android 应用，推荐安装后者（后者包含前者），后者主要的有点还有多了一些 web 插件，更适合开发网络应用。

* 为 Eclipse 配置 ADT 插件

ADT 插件必须通过 Eclipse Install New Software 向导来进行安装。按照 ADT 插件的下载说明（[可在 Android 开发人员 SDK 页面 - Eclipse 获取][11]）执行操作。这些步骤将指导您完成整个 ADT 插件的安装过程。

1. 启动 Eclipse ；选择 Help > Install New Software
2. 在右上角单击“添加”按钮；
3. 在出现的对话框中添加库，对话框中输入名称：“ADT插件”；和网址：

<code>https://dl-ssl.google.com/android/eclipse/</code> 

> 注：Android开发者工具更新网站需要一个安全的连接，URL输入HTTPS。确保从站点更新的。

4. 点击 <kbd>OK</kbd>
5. 在软件的对话框，请选中复选框并单击开发工具"下一步"。
6. 在下一个窗口中，您会看到一个要下载的工具列表。单击“下一步”。
7. 阅读并接受许可协议，然后单击“完成”。如果提示你一个安全警告说该软件的真实性或有效性不成立，点击OK。
8. 重新启动 Eclipse。

9. 设置Android SDK 路径以及配置

> 注：在线安装网络出错的话，可以下载离线包：[猛击这里][21]；还是下载不了？[上百度云][38]

接下来安装 离线包，和 在线安装相同的 1、2 步骤

3. 在“添加库”对话框中，单击 "Archive" 本地安装。
4. 选择下载的文件 <code>adt-23.0.4.zip</code> 并点击OK 。输入 “ADT插件” 的名称并单击 “确定”。
5. 在软件的对话框，请选中复选框并单击"下一步"。
6. 在下一个窗口中，您会看到一个要下载的工具列表（如：ADDMS/ADT/AHV/ANDT/AT/TOE），单击“下一步”。
7. 阅读并接受许可协议，然后单击“完成”。
8. 如果提示你一个安全警告说该软件的真实性或有效性不成立，点击OK。（如果中途因为网络被 qiang 而报错请手动下载 [这里][22] 并解压至 *安装目录* 的 **对应文件夹中** ）

<code>'Installing Software' has encountered a problem.An error occurred while collecting items to be installed</code>

9. 安装完成后，重新启动Eclipse。

10. 设置Android SDK 路径以及配置

![安装完成 Android SDK][25]

![设置路径 Android SDK][26]


> 注：eclipse 代理设置 <code>window > preferences > general > network connections</code>


##### ![phonegap][18] 

**安装 PhoneGap** 

<code> npm install -g cordova</code>

> 注：为什么是 cordova ？ [移步这里][23]



### 二、新建项目（三种）

##### 1、通过 Android Studio 新建项目（不推荐） ![Android Studio][27]

a、设置Android SDK和JDK的路径：

    依次打开：configure > project Defaults > Project Structure 

> 第一个是 sdk 组件目录 <code> F:\Android SDK\local-sdk</code>
> 第二个是 jdk 目录 <code>C:\Program Files\Java\jdk1.7.0_71</code> 

b、Star a new Android Studio project

设置 名称如： <code>firstblood</code> ；域如：<code>highsea90.com</code> ；路径如： <code>F:\Android SDK\new local sdk\firstblood</code> 一路按下一步，完成后，开始构建项目：

![first blood building][28]
![firstblood running][31]

> 注：1、但是这样创建的项目并不是 web 工程师 所喜欢的，因为这需要原生语言（Java）开发的。
>     2、没有4G内存请勿随意创建、运行，推荐内存 6GB

##### 2.1、通过 NPM cordova 命令行 新建项目（推荐） ![cordova][29]
    
        #进入你本地的项目文件夹
    $ cd /f/Android\ SDK/new\ local\ sdk/
        #演示版本号，可能各版本略有不同
    $ cordova -v
        #4.1.2
        #创建项目 
    $ cordova create firstblood com.highsea90.first first
        #进入项目
    $ cd firstblood/
        #添加android支持 **注意，tip**
    $ cordova platform add android
        #生成
    $cordova build
        #运行(需要添加模拟器)
    $cordova emulate android

> tip: 如果 android 环境没有搭好这里可能提示 比如： <code>Error: Please install Android target "android-19".</code> 说明在 Android SDK Manager 里没有安装好 Android 4.4.2；Why？

如下图：依次类推，报 target 什么错就缺什么组件

![Android target android-21][37]

##### 2.2、 任性的使用 phonegap ![phonegap][36]
依旧要使用 phonegap 也可以，但是国外镜像下载失败概率较大，这里以 [淘宝镜像为例][35]

        #安装cnpm
    $ npm install -g cnpm --registry=https://registry.npm.taobao.org
        #安装 phonegap
    $ cnpm install phonegap -g
        #进入项目
    $ cd my-second
        #运行ios模拟
    $ phonegap run ios   


        #phonegap 报错 请使用 cordova 指令，好吧同上……
    [phonegap] executing 'cordova platform add ios'...
    Applications for platform ios can not be built on this OS - win32.

    [phonegap] executing 'cordova run ios'...
    No platforms added to this project. Please use `cordova platform add <platform>`.
    

##### 3、通过 Eclipse 新建项目（不推荐） ![Eclipse][30]

对于比较怀旧的同学可以去[PhoneGap 安装页面][8]直接下载 PhoneGap 2.9.1，这里[百度云盘又准备好了][32]
下载后我将其解压到了 <code>F:\Android SDK\new local sdk</code> 路径下；

打开 eclipse 按 <kbd>Ctrl+n</kbd> 打开 <code>File > Import > Android </code> 
选择 Existing Android Code Into Workspace （即导入项目）
点击 <kbd>Next</kbd> 选择文件路径，或者直接输入 <code>F:\Android SDK\new local sdk\phonegap-2.9.1\lib\android\test</code> 点击完成


> 当然你也可以自己新建一个项目：
> ![新建项目][33]


### cordova 插件安装

#### 查看已经插件

进入项目 执行：

    $ cordova plugin
    No plugins added. Use `cordova plugin add <plugin>`.

#### 安装相关插件

* 基本设备资讯-设备API

    <code>cordova plugin add org.apache.cordova.device</code>

* 网络连接

    <code>cordova plugin add org.apache.cordova.network-information</code>

* 电池事件

    <code>cordova plugin add org.apache.cordova.battery-status</code>

* 加速度计算

    <code>cordova plugin add org.apache.cordova.device-motion</code>

* 指南针

    <code>cordova plugin add org.apache.cordova.device-orientation</code>

* 地理定位

    <code>cordova plugin add org.apache.cordova.geolocation</code>

* 相机

    <code>cordova plugin add org.apache.cordova.camera</code>

* 媒体

    <code>cordova plugin add org.apache.cordova.media</code>

* 捕获

    <code>cordova plugin add org.apache.cordova.media-capture</code>

* 访问设备

    <code>cordova plugin add org.apache.cordova.file</code>

* 网络文件传输

    <code>cordova plugin add org.apache.cordova.file-transfer</code>

* 对话方块通知

    <code>cordova plugin add org.apache.cordova.dialogs</code>

* 震动发出通知

    <code>cordova plugin add org.apache.cordova.vibration</code>

* 联络人

    <code>cordova plugin add org.apache.cordova.contacts</code>

* 全球化

    <code>cordova plugin add org.apache.cordova.globalization</code>

* 启动动画

    <code>cordova plugin add org.apache.cordova.splashscreen</code>

* 打开新的浏览器视窗-InAppBrowser

    <code>cordova plugin add org.apache.cordova.inappbrowser</code>

* 调试控制台

    <code>cordova plugin add org.apache.cordova.console</code>



### 三、运行项目

这个，上面已经提到了，记得添加模拟器就行，不会？那就没办法了……，待续吧


完
----

参考文章：

使用 Eclipse PhoneGap 构建 Android 应用程序入门；[移步][20]
环境搭建教程（最新版本1.3） phonegap cn android；[移步][34]
Android开发所需的Android SDK、开发中用到的工具、Android开发教程、Android设计规范，免费的设计素材等 [移步][39]

[1]: http://nodejs.org/download/                    "Nodejs 下载"
[2]: http://developer.android.com/sdk/index.html    "Android SDK 下载"
[3]: http://pan.baidu.com/s/1gdAGMT9                "135.1641136 百度云"
[4]: http://pan.baidu.com/s/1dDcUUvn                "10.35 for x64 nodejs"
[5]: http://pan.baidu.com/s/1jGHwqGI                "JDK 7u71 for x64"
[6]: http://www.oracle.com/technetwork/java/javase/downloads/index.html "jdk 官网"
[7]: http://pan.baidu.com/s/1eQ5tad8                "ST2 2.0.2 X64 "
[8]: http://phonegap.com/install/                   "PhoneGap 安装页面"
[9]: https://github.com/highsea/Hosts               "Hosts 修改"
[10]: http://www.cnblogs.com/highsea90/p/4201392.html "Sublime Text 插件"
[11]: http://developer.android.com/tools/sdk/eclipse-adt.html#downloading    "eclipse-adt 插件"
[12]: http://www.eclipse.org/downloads/             "Eclipse 下载安装"

[13]: http://images.cnitblog.com/blog/531703/201501/041745526841554.jpg "Java jdk安装"
[14]: http://images.cnitblog.com/blog/531703/201501/041732351225347.png "Android ADT 安装"
[15]: http://images.cnitblog.com/blog/531703/201501/041737429506604.png "Nodejs 10.35 安装"
[16]: http://images.cnitblog.com/blog/531703/201501/041743362782027.jpg "Sublime Text 神器"
[17]: http://images.cnitblog.com/blog/531703/201501/041733111842663.png "Eclipse For jee-win-X64"
[18]: http://images.cnitblog.com/blog/531703/201501/041732081695982.png "PhoneGap 安装"

[19]: http://pan.baidu.com/s/1o69gBvc               "Eclipse for jee 百度云"
[20]: http://www.adobe.com/cn/devnet/html5/articles/getting-started-with-phonegap-in-eclipse-for-android.html "参考 使用 Eclipse PhoneGap 构建 Android 应用程序入门"
[21]: https://dl.google.com/android/ADT-23.0.4.zip  "ADT 离线包"
[22]: http://sourceforge.net/projects/pydev/?source=typ_redirect "PyDev for Eclipse 离线包"
[23]: http://baike.baidu.com/view/8326345.htm       "什么是 Cordova "
[24]: http://images.cnitblog.com/blog/531703/201501/051135491407182.jpg "组件包管理器"
[25]: http://images.cnitblog.com/blog/531703/201501/051137582812929.jpg "SDK安装成功"
[26]: http://images.cnitblog.com/blog/531703/201501/051201428281954.jpg "SDK 路径设置"
[27]: http://images.cnitblog.com/blog/531703/201501/051211297035160.jpg "Android Studio"
[28]: http://images.cnitblog.com/blog/531703/201501/051219460937177.jpg "first blood building"
[29]: http://images.cnitblog.com/blog/531703/201501/051224047818614.png "cordova"
[30]: http://images.cnitblog.com/blog/531703/201501/051241148908776.png "Eclipse logo"
[31]: http://images.cnitblog.com/blog/531703/201501/051306451091053.gif "firstblood running"
[32]: http://pan.baidu.com/s/1ntA49df               "phonegap 2.9.1 百度云盘"
[33]: http://images.cnitblog.com/blog/531703/201501/051324565627141.jpg "eclipse 新建下项目"
[34]: http://www.phonegapcn.com/start/zh/1.3/#android "phonegap cn android"
[35]: http://npm.taobao.org/                        "TAONPM 淘宝镜像"
[36]: http://images.cnitblog.com/blog/531703/201501/051613094371678.png "phonegap logo"
[37]: http://images.cnitblog.com/blog/531703/201501/061321543752846.jpg "Android target android-21 (3-21)"
[38]: http://pan.baidu.com/s/1dD8dk3J "ADT-23.0.4 百度云"
[39]: https://github.com/highsea/AndroidDevTools "Android开发所需的Android SDK、开发中用到的工具、Android开发教程、Android设计规范，免费的设计素材等"