---
title: "esp32开发环境搭建"
date: 2021-10-30T17:43:03+08:00
draft: false
featuredImg: ""
tags: 
  - esp32
---
# esp32开发环境搭建

## 参考网址
`https://docs.espressif.com/projects/esp-idf/zh_CN/v4.3.1/esp32/get-started/index.html#esp-idf`

## 安装开发环境注意问题
- 开发环境采用VMware+ubuntu20.04+esp-idf+vscode+vscodeEspress-idf插件

- 权限问题`/dev/ttyUSB*`，参考文档解决办法，将用户添加到 Linux Dialout组

  ```
  sudo usermod -a -G dialout $USER
  ```

- `idf.py -p /dev/ttyUSB0 flash`或者 `idf.py -p /dev/ttyUSB0 monitor`时经常出现打不开串口的情况，将串口重新连接一下。处理流程：菜单栏Player(p)-->可移动设备(R)，将设备断开连接-->连接。

- 开发环境通过github下载慢。通过别的加速网址下载： `hub.fastgit.org`

  ESP-IDF下载：

  ```
  git clone -b v4.3.1 --recursive https://github.com/espressif/esp-idf.git #原命令
  git clone -b v4.3.1 --recursive https://hub.fastgit.org/espressif/esp-idf.git #加速网址
  ```

  ESP-IDF工具安装器下载， 官方文档通过建立环境变量下载，实际测试通过Espressif的下载服务器下载也比较慢，同样通过别的加速网址下载： `hub.fastgit.org`

  ```
  export IDF_GITHUB_ASSETS="dl.espressif.com/github_assets" #原命令
  export IDF_GITHUB_ASSETS="hub.fastgit.org/github_assets"  #加速网址
  ```

- VSCode 打开头文件的问题，将头文件路径添加到包含路径

  ```
  ./build									#config配置参数最终将生成.h文件放到./build目录下
  ~/esp/esp-idf/**						 #各个模块的头文件
  ~/.espressif/tools/xtensa-esp32-elf/**	   #Cpu相关的头文件
  ```

- VSCode 快捷键设置，跳转更改位置： 根据需要调整 `前进 Go Forword` `后退 Go Back`对应的快捷键。