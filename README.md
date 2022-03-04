# Fast-Robust-ICP-VS2017

fork from https://github.com/yaoyx689/Fast-Robust-ICP

## 使用方法

下载并解压后，使用**Visual Studio 2017**打开[Fast-Robust-ICP-master-VS2017.sln](Fast-Robust-ICP-master-VS2017.sln)文件，然后理论上可以直接运行。

## 说明

原作者的项目貌似按教程在Linux编译会有问题，使用VS和CMake在Windows编译也有问题。

**解决的问题：**

1. 内含[eigen-3.4.0](https://gitlab.com/libeigen/eigen/-/archive/3.4.0/eigen-3.4.0.zip)，已于`属性 -> C/C++ -> 常规 -> 附加包含目录`添加依赖。
2. 修复部分`#include`错误使用`<>`包含本地文件，改成`""`
3. 修复旧版C语言的错误警告，忽略错误
   `属性 -> C/C++ -> 预处理器 -> 预处理器定义 -> 增加 _CRT_SECURE_NO_WARNINGS`
   （`Configuration Properties>>C/C++>>Preporocessor>>Preprocessor Definitions>> _CRT_SECURE_NO_WARNINGS`）
4. 修复错误：“节数超过对象文件格式限制: 请使用 /bigobj 进行编译”
   `属性 -> C/C++  -> 命令行 -> 其他选项 -> 增加 /bigobj `