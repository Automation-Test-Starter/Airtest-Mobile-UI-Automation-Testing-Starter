<!-- markdownlint-disable MD041 -->
<!-- markdownlint-disable MD033 -->
<div align="right"><strong>🇨🇳中文</a></strong>  | <strong><a href="./README.md">🇬🇧English</strong></div>
<!-- markdownlint-disable MD041 -->
<!-- markdownlint-disable MD033 -->
  
# Airtest-Mobile-UI-Automation-Testing-Starter

> 一个使用 Airtest 工具做移动端 UI 自动化测试的快速启动项目

一个使用 Airtest 工具做移动端 UI 自动化测试的介绍文档，包含了环境搭建、工程初始化、示例，进阶用法等内容

项目示例代码仓库如下：

- [Airtest Android Demo](https://github.com/Automation-Test-Starter/Airtest-Android-Demo)
- [Airtest iOS Demo](https://github.com/Automation-Test-Starter/Airtest-iOS-Demo)

- [Airtest-Mobile-UI-Aut- [Airtest-Mobile-UI-Automation-Testing-Starter](#airtest-mobile-ui-automation-testing-starter)
  - [Airtest 介绍](#airtest-介绍)
  - [Airtest 安装](#airtest-安装)
    - [安装 Python](#安装-python)
    - [安装 Airtest](#安装-airtest)
      - [使用 pip 安装](#使用-pip-安装)
      - [使用源码安装](#使用源码安装)
    - [安装 Airtest IDE](#安装-airtest-ide)
      - [Windows](#windows)
      - [MacOS](#macos)
  - [Airtest 连接手机](#airtest-连接手机)
    - [Airtest 连接安卓手机](#airtest-连接安卓手机)
      - [安卓手机连接准备工作](#安卓手机连接准备工作)
        - [安装 ADB 驱动](#安装-adb-驱动)
        - [尝试连接手机](#尝试连接手机)
      - [Airtest 通过 USB 连接安卓手机](#airtest-通过-usb-连接安卓手机)
      - [Airtest 通过 WIFI 连接安卓手机](#airtest-通过-wifi-连接安卓手机)
    - [Airtest 连接 iPhone 手机](#airtest-连接-iphone-手机)
      - [iPhone 手机连接准备工作](#iphone-手机连接准备工作)
      - [Airtest 通过 USB 连接 iPhone 手机](#airtest-通过-usb-连接-iphone-手机)
      - [Airtest 通过 WIFI 连接 iPhone 手机](#airtest-通过-wifi-连接-iphone-手机)
  - [编写第一个 Airtest 脚本](#编写第一个-airtest-脚本)
    - [安卓 app 测试版本](#安卓-app-测试版本)
      - [获取安卓 app 包名和 activity 名](#获取安卓-app-包名和-activity-名)
        - [获取已安装应用程序的列表](#获取已安装应用程序的列表)
        - [获取特定应用程序的启动活动（activity）](#获取特定应用程序的启动活动activity)
      - [Airtest 脚本编写](#airtest-脚本编写)
        - [截图模式](#截图模式)
        - [录制脚本模式](#录制脚本模式)
        - [Poco 模式](#Poco-模式)
    - [iOS app 测试版本](#ios-app-测试版本)
  - [Airtest 常用命令](#airtest-常用命令)
  - [Airtest 工程初始化](#airtest-工程初始化)
  - [Airtest 常用 API](#airtest-常用-api)
  - [Airtest 进阶用法](#airtest-进阶用法)
    - [Airtest 运行参数](#airtest-运行参数)
    - [Airtest 运行模式](#airtest-运行模式)
    - [Airtest 运行平台](#airtest-运行平台)
    - [CI/CD 集成](#cicd-集成)
    - [集成 allure 报告](#集成-allure-报告)
  - [Airtest 常见问题](#airtest-常见问题)

## Airtest 介绍

Airtest 是一个用于游戏和应用程序的 UI 自动化测试框架，支持 Android、iOS、Windows、MacOS 平台，使用 Python 语言编写，基于图像识别技术，无需侵入应用程序代码，无需 root 权限，支持跨平台，支持多设备并行测试。

## Airtest 安装

### 安装 Python

Airtest 是基于 Python 语言编写的，所以需要先安装 Python 环境，建议安装 Python 3.7+ 版本，安装教程请参考 [Python 官网](https://www.python.org/downloads/)。

### 安装 Airtest

Airtest 的安装方式有两种，一种是使用 pip 安装，一种是使用源码安装。

#### 使用 pip 安装

使用 pip 安装 Airtest 的方式非常简单，只需要在命令行中执行以下命令即可：

```shell
pip install airtest
```

#### 使用源码安装

使用源码安装 Airtest 的方式稍微复杂一些，需要先从 [Airtest GitHub 仓库](https://github.com/AirtestProject/Airtest.git)下载源码，然后在命令行中进入源码目录，执行以下命令：

```shell
python setup.py install
```

### 安装 Airtest IDE

Airtest IDE 是 Airtest 的图形化界面工具，可以用来录制脚本、运行脚本、查看脚本运行结果等，安装方式如下：

#### Windows

进入 [Airtest IDE 官网](https://airtest.netease.com/)，点击下载按钮，下载 Windows 版本的安装包，然后双击安装包，按照提示完成安装即可。

#### MacOS

进入 [Airtest IDE 官网](https://airtest.netease.com/)，点击下载按钮，下载 MacOS 版本的安装包，然后双击安装包，按照提示完成安装即可。

## Airtest 连接手机

要开始使用 Airtest 进行 UI 自动化测试，首先需要将安卓手机和 iPhone 手机连接到电脑上

下面会介绍如何连接安卓手机和 iPhone 手机，以及如何在 Airtest IDE 中查看手机是否连接成功。

当然 Airtest 支持通过 USB 连接手机，也支持通过 WiFi 连接手机，后面也会分别介绍这两种连接方式。

### Airtest 连接安卓手机

#### 安卓手机连接准备工作

##### 安装 ADB 驱动

adb 是 Android Debug Bridge 的缩写，是 Android SDK 中的一个工具，用于连接安卓设备，安装 adb 驱动的方式有两种，一种是安装 Android SDK，一种是安装 Android Studio。

- 安装 Android SDK

  1. 进入 [Android SDK 官网](https://developer.android.com/studio/releases/platform-tools)，下载对应系统版本的 Android SDK 压缩包
  2. 解压 Android SDK 压缩包，将解压后的目录添加到环境变量 PATH 中
  3. 打开命令行，输入 adb version 命令，查看 adb 是否安装成功
  4. 如果安装成功，会显示 adb 的版本号
   ![ ](https://cdn.jsdelivr.net/gh/naodeng/blogimg@master/uPic/H7CQqH.png)

- 安装 Android Studio

  1. 进入 [Android Studio 官网](https://developer.android.com/studio)，下载对应系统版本的 Android Studio 安装包
  2. 双击安装包，按照提示完成安装
  3. 打开 Android Studio，点击 Configure -> SDK Manager，勾选 Android SDK Platform-Tools，然后点击 OK 按钮，等待安装完成
  4. 打开命令行，输入 adb version 命令，查看 adb 是否安装成功
  5. 如果安装成功，会显示 adb 的版本号
   ![ ](https://cdn.jsdelivr.net/gh/naodeng/blogimg@master/uPic/H7CQqH.png)

##### 尝试连接手机

- 打开手机的 USB 调试模式
- 手机连接电脑
- 手机连接电脑后，需要在手机上授权电脑的 USB 调试权限
- 选择允许调试
- 然后在电脑上输入‘adb devices’命令，查看手机是否连接成功
- 如果连接成功，会显示手机的设备号
  ![ ](https://cdn.jsdelivr.net/gh/naodeng/blogimg@master/uPic/pqud3z.png)
  
#### Airtest 通过 USB 连接安卓手机

> 确认已按照上面的步骤安装好 ADB 驱动和手机已连接到电脑

- 打开 Airtest 程序到主界面
 ![ ](https://cdn.jsdelivr.net/gh/naodeng/blogimg@master/uPic/QEheye.png)

- 点击 Airtest 主界面右侧的设备 Devices 操作区域 的刷新 ADB 按钮 (refresh ADB)，刷新设备列表

- 如果刷新成功，会显示安卓手机链接列表下会展示手机的设备号
  ![ ](https://cdn.jsdelivr.net/gh/naodeng/blogimg@master/uPic/MecIPv.png)

- 点击设备列表中的设备后的操作区域的连接按钮 (connect)，连接手机
  
- 如果连接成功，Airtest 主界面右侧会展示已连接安卓手机的桌面
  ![ ](https://cdn.jsdelivr.net/gh/naodeng/blogimg@master/uPic/U0paog.png)

- 到这里，安卓手机就通过 USB 与 Airtest 连接成功了，可以开始编写或录制脚本了

#### Airtest 通过 WIFI 连接安卓手机

> 确认已按照上面的步骤安装好 ADB 驱动和手机已连接到电脑

- 安卓手机保持和电脑在同一个 WIFI 网络下
- 在电脑上执行命令“adb tcpip 5555”，其中 5555 是默认端口号，可以根据自己的需要指定。 
- 获取手机 IP 地址。您可以在“设置”>“关于手机”>“状态信息”>“IP 地址”中找到它
- 接下来可以拔掉 USB 电缆。在 AirtestIDE 的远程设备连接中，输入 adb connect 手机 IP：刚刚填写的端口号 5555，点击连接按钮 就可以连接手机了（例如我的安卓设备连接 wifi 后的 ip 地址为 192.168.50.101，则在 AirtestIDE 的远程设备连接中输入‘adb connect 192.168.50.101:5555’，再点击连接按钮即可）
- 如果连接成功，Airtest 主界面右侧会展示已连接安卓手机的桌面
  ![ ](https://cdn.jsdelivr.net/gh/naodeng/blogimg@master/uPic/EggD2L.png)

- 到这里，安卓手机就通过 wifi 与 Airtest 连接成功了，可以开始编写或录制脚本了

> 如果由于网络波动、重启 ADB 等原因导致连接中断，请再次执行 adb connect ip:port 重新连接。注意：使用无线连接时，一开始还是需要用 USB 线连接手机和电脑，并且在指定端口和查询 IP 之前千万不要拔掉！

### Airtest 连接 iPhone 手机

> iphone 手机连接步骤后续补充

#### iPhone 手机连接准备工作

#### Airtest 通过 USB 连接 iPhone 手机

#### Airtest 通过 WIFI 连接 iPhone 手机

## 编写第一个 Airtest 脚本

### 安卓 app 测试版本

#### 获取安卓 app 包名和 activity 名

要通过 ADB（Android Debug Bridge）获取安卓手机上已安装应用程序的包名（package name）和活动名（activity name），可以使用以下命令：

##### 获取已安装应用程序的列表

```bash
adb shell pm list packages
```

上述命令会列出设备上所有已安装应用程序的包名。

##### 获取特定应用程序的启动活动（activity）

首先，找到应用程序的包名，然后使用以下命令获取其启动活动：

```bash
adb shell pm dump <package_name> | grep -A 1 MAIN
```

请将 `<package_name>` 替换为实际应用程序的包名。上述命令将输出包含启动活动的相关信息。

例如，假设要获取应用程序 "com.android.calculator2" 的包名和启动活动，可以执行以下步骤：

```bash
# 获取应用程序列表
adb shell pm list packages

# 在列表中找到 "com.android.calculator2" 的包名

# 获取启动活动
adb shell pm dump com.android.calculator2 | grep -A 1 MAIN
```

注意：这些命令可能在不同的设备或 Android 版本上有所不同，具体取决于设备和系统的配置。

#### Airtest 脚本编写

下面会实现一个小例子：打开手机上的计算器 app，然后输入 1+1=2，最后关闭计算器 app。

sony 手机计算器 app 的包名是：com.android.calculator2，启动活动是：com.android.calculator2.CalculatorActivity

##### 截图模式

> 前期均会以.air 脚本文件的形式编写脚本，后面会介绍如何将.air 脚本文件转换成.py 脚本文件

- 打开 Airtest IDE，点击左侧的脚本编辑器，新建一个.air 脚本文件，命名为：demo.air
- 在脚本文件中输入以下代码：

```python

# -*- encoding=utf8 -*-
__author__ = "nao.deng"

# 导入 Airtest 模块
from airtest.core.api import *

# 自动设置环境
auto_setup(__file__)

# 启动计算器 app
start_app('com.android.calculator2')
```

- 点击 Airtest IDE 的运行按钮，运行脚本，如果运行成功，会打开手机上的计算器 app
- 点击 Airtest IDE 的停止按钮，停止脚本运行
- 点击 Airtest IDE 上的 airtest 辅助窗区域的‘Touch’按钮 (touch)，进入截图模式
- 截取计算器 app 上的 1 按钮，截图后会自动跳转到脚本编辑器，会自动添加一行代码截图的代码，如下所示：
  ![ ](https://cdn.jsdelivr.net/gh/naodeng/blogimg@master/uPic/4OvYKO.png)
- 再次点击 Airtest IDE 上的 airtest 辅助窗区域的‘Touch’按钮 (touch)，进入截图模式
- 截取计算器 app 上的 + 按钮，截图后会自动跳转到脚本编辑器，会自动添加一行代码截图的代码，如下所示：
  ![ ](https://cdn.jsdelivr.net/gh/naodeng/blogimg@master/uPic/AuyLQm.png)

- 再次点击 Airtest IDE 上的 airtest 辅助窗区域的‘Touch’按钮 (touch)，进入截图模式
- 截取计算器 app 上的 1 按钮，截图后会自动跳转到脚本编辑器，会自动添加一行代码截图的代码，如下所示：
  ![ ](https://cdn.jsdelivr.net/gh/naodeng/blogimg@master/uPic/RIcOvv.png)

- 再次点击 Airtest IDE 上的 airtest 辅助窗区域的‘Touch’按钮 (touch)，进入截图模式
- 截取计算器 app 上的 = 按钮，截图后会自动跳转到脚本编辑器，会自动添加一行代码截图的代码，如下所示：

  ![ ](https://cdn.jsdelivr.net/gh/naodeng/blogimg@master/uPic/TJ2LpM.png)

- 然后点击 Airtest IDE 的运行按钮，运行脚本，如果运行成功，会打开手机上的计算器 app，然后输入 1+1=2

- 再次点击 Airtest IDE 上的 airtest 辅助窗区域的‘assert_exists’按钮 (assert_exists)，进入截图模式
- 截取计算器 app 结果区域上的 2，截图后会自动跳转到脚本编辑器，会自动添加一行代码截图的代码，如下所示：
  ![ ](https://cdn.jsdelivr.net/gh/naodeng/blogimg@master/uPic/lSksEa.png)

- 然后点击 Airtest IDE 的运行按钮，运行脚本，如果运行成功，会打开手机上的计算器 app，然后输入 1+1=2，最后会断言计算器 app 结果区域上的 2 是否存在，如果存在，则断言成功，否则断言失败
- 点击 Airtest IDE 的停止按钮，停止脚本运行
- 最后输入以下代码，关闭计算器 app

```python
stop_app('com.android.calculator2')
```

- 整体的代码如下所示：

 ![ ](https://cdn.jsdelivr.net/gh/naodeng/blogimg@master/uPic/psjc3S.png)

- 然后点击 Airtest IDE 的运行按钮，运行脚本，如果运行成功，会打开手机上的计算器 app，然后输入 1+1=2，最后会断言计算器 app 结果区域上的 2 是否存在，如果存在，则断言成功，否则断言失败，最后关闭计算器 app
- 点击 Airtest IDE 的停止按钮，停止脚本运行
- 到这里，第一个 Airtest 脚本就编写完成了
- 如果想要了解更多 Airtest 的 API，可以参考 [Airtest API 文档](https://airtest.netease.com/docs/api/)

运行 demo 如下所示：

![airtest-demo1](/readme_pics/airtest-demo1.gif)

##### Poco 模式

- 打开 Airtest IDE，点击左侧的脚本编辑器，新建一个.air 脚本文件，命名为：test_calculator_Poco.py

- 在脚本文件中输入以下代码：

```python

# -*- encoding=utf8 -*-
__author__ = "nao.deng"

# 导入 Airtest 模块 和 Poco 模块
from airtest.core.api import *
from Poco.drivers.android.uiautomation import AndroidUiautomationPoco
Poco = AndroidUiautomationPoco(use_airtest_input=True, screenshot_each_action=False)

# 自动设置环境
auto_setup(__file__)

# 启动计算器 app
start_app('com.android.calculator2')
```

- 点击 Airtest IDE 的运行按钮，运行脚本，如果运行成功，会打开手机上的计算器 app
- 点击 Airtest IDE 的停止按钮，停止脚本运行
- 点击 Airtest IDE 上的 Poco 辅助窗区域的设备类型切换框，选择 Android 设备
- 然后点击 Poco 辅助窗区域的设备类型切换框旁的 Poco UI 树锁定按钮，进入 Poco Pause 模式（锁定后手机上打开 app 的 UI 树不会再进行变动，可以选择 app 上不同的 UI 定位）
- 然后点击 Poco 辅助窗区域的设备类型切换框旁的 Poco 定位按钮，进入 Poco 定位模式
- 然后点击计算器 app 上的 1 按钮，Poco 定位模式会在 Poco UI 树列表下展示对于的 UI 定位，右键选择对应的 UI 定位，选择‘UI path-code’，然后代码会自动添加一行代码，如下所示：

```python
poco("android.widget.FrameLayout").offspring("android:id/content").offspring("com.android.calculator2:id/pad_pager").offspring("com.android.calculator2:id/digit_1")
```

- 然后给上述代码添加一个点击事件，用来模拟点击操作，如下所示：

```python
poco("android.widget.FrameLayout").offspring("android:id/content").offspring("com.android.calculator2:id/pad_pager").offspring("com.android.calculator2:id/digit_1").click()
```

- 然后按照上述步骤依次添加 +、1、=、2 的 UI 定位和点击事件，最后的代码如下所示：

```python
# -*- encoding=utf8 -*-
__author__ = "nao.deng"

from airtest.core.api import *

auto_setup(__file__)

# import
from poco.drivers.android.uiautomation import AndroidUiautomationPoco
poco = AndroidUiautomationPoco(use_airtest_input=True, screenshot_each_action=False)


start_app('com.android.calculator2')

# click ‘1’
poco("android.widget.FrameLayout").offspring("android:id/content").offspring("com.android.calculator2:id/pad_pager").offspring("com.android.calculator2:id/digit_1").click()
# click ‘+’
poco("android.widget.FrameLayout").offspring("android:id/content").offspring("com.android.calculator2:id/pad_pager").offspring("com.android.calculator2:id/op_add").click()
# click ‘1’
poco("android.widget.FrameLayout").offspring("android:id/content").offspring("com.android.calculator2:id/pad_pager").offspring("com.android.calculator2:id/digit_1").click()

# click ‘=’
poco("android.widget.FrameLayout").offspring("android:id/content").offspring("com.android.calculator2:id/pad_pager").offspring("com.android.calculator2:id/eq").click()
```

- 然后点击计算器 app 上的 结果区域，Poco 定位模式会在 Poco UI 树列表下展示对于的 UI 定位，右键选择对应的 UI 定位，选择‘UI path-code’，然后代码会自动添加一行代码，如下所示：

```python
poco("android.widget.FrameLayout").offspring("android:id/content").offspring("com.android.calculator2:id/result")
```

- 这里需要断言计算器算出来的结果是否正确，所以需要获取计算器 app 结果区域的 text，然后断言 text 是否等于 2，通过检查对应 UI 定位的具体信息，如下图所示
  ![ ](https://cdn.jsdelivr.net/gh/naodeng/blogimg@master/uPic/erUudl.png)

- 发现对应 UI 定位存在 text 属性，所以可以通过 text 属性获取计算器 app 结果区域的 text，然后断言 text 是否等于 2，所以需要给上述代码添加一个获取 text 的方法，如下所示：

```python
poco("android.widget.FrameLayout").offspring("android:id/content").offspring("com.android.calculator2:id/result").get_text()
```

- 接下来断言 text 是否等于 2，所以需要给上述代码添加一个断言方法，如下所示：

```python
assert_equal(poco("android.widget.FrameLayout").offspring("android:id/content").offspring("com.android.calculator2:id/result").get_text(), '2')
```

- 最后的代码如下所示：

```python
# -*- encoding=utf8 -*-
__author__ = "nao.deng"

from airtest.core.api import *

auto_setup(__file__)

# import
from poco.drivers.android.uiautomation import AndroidUiautomationPoco
poco = AndroidUiautomationPoco(use_airtest_input=True, screenshot_each_action=False)

start_app('com.android.calculator2')

# click ‘1’
poco("android.widget.FrameLayout").offspring("android:id/content").offspring("com.android.calculator2:id/pad_pager").offspring("com.android.calculator2:id/digit_1").click()
# click ‘+’
poco("android.widget.FrameLayout").offspring("android:id/content").offspring("com.android.calculator2:id/pad_pager").offspring("com.android.calculator2:id/op_add").click()
# click ‘1’
poco("android.widget.FrameLayout").offspring("android:id/content").offspring("com.android.calculator2:id/pad_pager").offspring("com.android.calculator2:id/digit_1").click()

# click ‘=’
poco("android.widget.FrameLayout").offspring("android:id/content").offspring("com.android.calculator2:id/pad_pager").offspring("com.android.calculator2:id/eq").click()

# alert result equal 2
assert_equal(poco("android.widget.FrameLayout").offspring("android:id/content").offspring("com.android.calculator2:id/result").get_text(), '2')
```

- 然后点击 Airtest IDE 的运行按钮，运行脚本，如果运行成功，会打开手机上的计算器 app，然后输入 1+1=2，最后会断言计算器 app 结果区域上的 2 是否存在，如果存在，则断言成功，否则断言失败，最后关闭计算器 app
- 点击 Airtest IDE 的停止按钮，停止脚本运行
- 到这里，第一个 Airtest poco 脚本就编写完成了

运行 demo 如下所示：

![airtest-demo2](/readme_pics/airtest-demo2.gif)

##### Poco 录制脚本模式

### iOS app 测试版本

## Airtest 常用命令

## Airtest 工程初始化

## Airtest 常用 API

## Airtest 进阶用法

### Airtest 运行参数

### Airtest 运行模式

### Airtest 运行平台

### CI/CD 集成

### 集成 allure 报告

## Airtest 常见问题
