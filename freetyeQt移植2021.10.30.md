# freetype QT移植

## 下载
 git clone https://gitlab.freedesktop.org/freetype/freetype.git
 git clone https://gitlab.freedesktop.org/freetype/freetype-demos.git
## QT编译
以QT mingw64 为例
1. 打开mingw64编译环境
2. cd freetype目录
3. 执行 mingw32-make.exe
4. 编译完成后将会再objs文件夹下生成freetype.a静态链接库文件
## 测试
1. cd freetype-demos目录   两个文件夹同一级目录，用于定位链接库
2. 执行 mingw32-make.exe
3. 编译完成后会在bin目录下生成执行文件
4. 以ftstring 为例， 执行 ftstring.exe -m hello 150 C:\Windows\Fonts\STXINGKA.TTF
5. 使用up down left right home end f5 f6......等按键实现不同的功能