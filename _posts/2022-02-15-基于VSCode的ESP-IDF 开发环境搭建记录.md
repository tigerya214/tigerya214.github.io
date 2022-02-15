---
layout: post
title: "基于VSCode的ESP-IDF搭建记录"
description: "Recording some problem and comprehend. "
categories: [ESP-IDF]
tags: [ESP-IDF, IDE]
redirect_from:
  - /2022/02/15/
---

## 基于VSCode的ESP-IDF 开发环境搭建记录



### 遇到的问题和解决的方案：

1、在VSCode中安装Espressif插件时选择版本1.30会无法下载配置文件 

> 解决方案：通过安装1.20版本后下载好配置文件再更新到1.30

2、下载好配置文件并将ESP-IDF插件更新到1.30后，可以打开示例文件但无法打开设置界面

> 解决方案：需要VSCode打开具体的文件夹才能对应设置ESP-IDF的SDK configuration



### 我个人的理解：

1、VScode 中的esp-idf 是通过git来进行版本管理的

2、esp-idf 文件里有Freertos 系统相关的调用，并且导入esp32-cam模块后能够正常运行，可见esp32-s 内已集成了Freertos

