# lvgl 移植笔记

参考文档 https://docs.lvgl.io/master/porting/index.html

参考文章 https://blog.csdn.net/weixin_43808708/article/details/121348740

## 创建一个新项目

cp ~/esp/esp-idf/examples/get-started/blink . -r

mv blink lvgl-example

修改 CMakeLists.txt中 项目名称为 lvgl-example

## 下载 lvgl 代码 和 lvgl_esp32_drivers

创建 components 目录

mkdir components

cd components

git clone https://github.com/lvgl/lvgl.git

git clone https://github.com/lvgl/lvgl_esp32_drivers.git

## menuconfig

```sh
# 进入项目根路径下
idf.py set-target esp32-c3
idf.py menuconfig

# 就能在组件中, 最后面 可以看到 lvgl 组件
# 1. LVGL ESP Drivers
#   TTF Display
#   水平分辨率: 132
#   垂直分辨率: 162
#   选择一个显示控制器模型: ST7725S
#   分配 Display Pin:
#       RES:9 CS:10 SCL:4 SDA:6 DC:8
#   使用预定的buffer size, 默认设置的buffer可能会溢出
#   
```