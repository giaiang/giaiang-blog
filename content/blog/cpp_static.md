+++
title = "C++关键字static"
date = "2025-07-25T22:09:06+08:00"

#
# description is optional
#
# description = "An optional description for SEO. If not provided, an automatically created summary will be used."

tags = ["cpp"]
+++

static变量存储在内存的全局/静态存储区（`.data`段和`.bss`段）

## static修饰局部变量
- 改变局部变量的生命周期，存储位置从栈段变为全局/静态存储区
- static局部变量只初始化一次
- static变量没有赋值默认为0x00

## static修饰全局变量和函数
- 指定全局变量和函数为内部链接（**改变作用域**），外部文件无法访问。

## 静态成员变量/静态成员函数
- 静态成员变量为所有类共享，不属于某个实例
- 静态成员变量必须在类外定义，定义时不加static关键字（`Type ClassName::value = 0`）
- 静态成员函数没有隐藏的`this`指针，无法访问非静态成员
- 静态成员同样有`private`、`protect`和`public`访问级别。

