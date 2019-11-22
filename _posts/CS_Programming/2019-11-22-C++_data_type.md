---
layout:     post
title:      "Data type of C++"
subtitle:   "C++基本内置类型"
date:       2019-11-22 21:10:00
author:     "lvjerry"
header-img: "img/blog/CS_Programming/C++logo.jpg"
catalog: true
tags:
    - C++
    - Programming
---

## C++基本内置类型
### 算术类型
   算术类型分为两类: **整型**
   （integral type，包括字符和布尔类型在内）
   和**浮点型**。<br>
   算术类型的尺寸（也就是该类型数据所占的比特数）在不同机器上有所差别。
   下表列出了C++标准规定的尺寸的最小值，同时允许编译器赋予这些类型更大的尺寸。
   
| **类型** | **含义** | **最小尺寸** |
| :------: |  :------: | :------: |
| bool  | 布尔类型 | 未定义 |
| char | 字符 | 8位 |
|wchar_t| 宽字符| 16位|
|char16_t|Unicode字符|16位|
|char32_t|Unicode字符|32位|
|short|短整型|16位|
|int|整型|16位|
|long|长整型|32位|
|long long|长整型|64位|
|float|单精度浮点数|6位有效数字|
|double|双精度浮点数|10位有效数字|
|long double|扩展精度浮点数|10位有效数字|
<br>布尔类型（bool）的取值是真（true）或者假（false）。


### 变量

### 复合类型
