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

- [Airtest-Mobile-UI-Automation-Testing-Starter](#airtest-mobile-ui-automation-testing-starter)
  - [Airtest 介绍](#airtest-介绍)
  - [Airtest 安装](#airtest-安装)
    - [安装 Python](#安装-python)
    - [安装 Airtest](#安装-airtest)
      - [使用 pip 安装](#使用-pip-安装)
      - [使用源码安装](#使用源码安装)
    - [安装 Airtest IDE](#安装-airtest-ide)
      - [Windows](#windows)
      - [MacOS](#macos)

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

- 安装 ADB 驱动

- 打开手机的 USB 调试模式
- 手机连接电脑
- 手机连接电脑后，需要在手机上授权电脑的 USB 调试权限
- 输入‘adb devices’命令，查看手机是否连接成功

#### Airtest 通过 USB 连接安卓手机

#### Airtest 通过 WIFI 连接安卓手机

### Airtest 连接 iPhone 手机

#### iPhone 手机连接准备工作

#### Airtest 通过 USB 连接 iPhone 手机

#### Airtest 通过 WIFI 连接 iPhone 手机

## 编写第一个 Airtest 脚本

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
