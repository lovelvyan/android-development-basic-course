# 安卓开发环境

## 1 Java Development Kit（JDK）

 Java Development(JDK)是用于开发、编译和测试使用Java语言编写的应用程序、applet 和组件，JDK包含以下几个部分：

 开发工具——指工具和实用程序，可帮助您开发、执行、调试和保存以 Java编程语言编写的程序。

 运行时环境——由 JDK 使用的 Java Runtime Environment (JRE) 的实现。JRE 包括 Java 虚拟机 (JVM)、类库以及其他支持执行以 Java 编程语言编写的程序的文件。

 附加库——开发工具所需的其他类库和支持文件。

 演示applet 和应用程序——Java 平台的编程示例源码。

 样例代码——某些 Java API 的编程样例源码。

 C头文件——支持使用 Java 本机界面、JVM工具界面以及 JavaTM 平台的其他功能进行本机代码编程的头文件。

 源代码——组成 Java 核心 API 的所有类的 Java源文件。

 相关参考网址：

```
http://java.sun.com/——包含Java 技术、产品信息、新闻和软件特性等。
http://java.sun.com/docs——JavaT平台文档，包括白皮书、教程以及相关文档。
http://developer.java.sun.com——开发者服务网站，技术信息、新闻、论坛等。
http://java.sun.com/products/——Java 技术产品和 API。
```

## 2 Android Development Tools（ADT）

Android开发工具(ADT)，作为Eclipse工具插件，让其支持Android快速入门和便捷开发，可通过Eclipse启动菜单（启动Eclipse后，选择Help->Install New Software）安装。如下图所示。

ADT开发工具，包括Android Dalvik Debug Moniter Server(Android DDMS)和Android Development Tools（ADT），上面的插图中，还有Hierarchy Viewer和TraceView两个查看器，看名称就知道功能了。DDMS可以提供调试设备时为设备截屏，查看线程及内存信息、Logcat、广播信 息、模拟呼叫、接收短消息、文件查看器等功能（该功能在安装完ADT之后，点击Eclipse工具栏右上角的那个带箭头的小窗口图标弹出菜单中打开）。 Android Development Tools（ADT）工具应该是为Eclipse支持Android项目快速编程开发和调试插件而已（也可能不太确切）。

## 3 Android Software Development Kit（SDK）

一般提到SDK就会想到：API接口库、帮助文档和示例源码，Android SDK似乎也不例外，它为开发者提供相关封装API接口库文件、文档资源及一些工具包整合。当然了如果你使用Eclipse作为开发工具，那么只需要安装SDK也可以，ECLIPSE和ADT也一并省略掉。下图是ADK和AVD管理器界面，可从SDK安装目录下执行SDK Manager.exe或在Eclipse中执行Window->Android SDK and AVD manager看到。

安装后SDK目录下的帮助文档相当完善，应有尽有（位置在SDK的docs目录下）。此外，Android SDK还包含一个手机模拟器（Virtual Devices），我们开发时就可以先使用模拟器进行模拟仿真，感觉时机成熟时再下载到真机进行测试。