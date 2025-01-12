---
layout:     post
title:      "数据库-数据库逻辑设计"
subtitle:   "E-R图向关系模型的转换"
date:       2019-11-26 20:00:00
author:     "lzy"
header-img: "img/post-bg-2015.jpg"
catalog: true
tags:
    - 数据库
    - 计算机学科
---

> 文章引用：https://www.cnblogs.com/yijiahao/p/11707183.html

### 转换类型
1. **1对1的联系**：一个1：1联系可以转换成一个独立的关系模式，也可以与任意一端对应的关系模式合并。
    + 如果转换为一个独立的关系模式，则与该联系相连的各实体的码以及联系本身的属性均转换为关系的属性，**每个实体的码均是该关系的候选码。**
    + 如果与某一端实体对应的关系模式合并，则需要在该关系模式的属性中加入另一个关系模式的码和联系本身的属性。
    ![1对1](https://lzy-lvjerry.github.io/img/blog/CS_DataBase/2019-11-26-DB_ER_to_Relation1.png)
    
2. **1对多的联系**：一个1：n联系可以转换为一个独立的关系模式，也可以与n端对应的关系模式合并。
    + 如果转换为一个独立的关系模式，则与该联系相连的各实体的码以及联系本身的属性均转换为关系的属性，而**关系的码为n端实体的码。**
    + 如果与n端合并，则必须是**1端的主码加到n端**关系中。
    ![1对多](https://lzy-lvjerry.github.io/img/blog/CS_DataBase/2019-11-26-DB_ER_to_Relation2.png)


3. **多对多的联系**：与该联系相连的各实体的码以及联系本身的属性均转换为关系的属性，各实体的码组成关系的码或关系码的一部分。
    + 意思是：每个实体集对应一个关系模式，**对于多对多的联系，其单独对应一个实体集，该实体集的主码由各实体集的主码共同构成。**
    ![多对多](https://lzy-lvjerry.github.io/img/blog/CS_DataBase/2019-11-26-DB_ER_to_Relation3.png)

#### 例子

![例1](https://lzy-lvjerry.github.io/img/blog/CS_DataBase/2019-11-26-DB_ER_to_Relation4.png)
+ 学生：学号，姓名，性别，年龄
+ 课程：课程编号，课程名
+ 选修：学号，课程编号，分数
+ 教师：教师编号，教师名，职称，课程编号
+ 参加：教师编号，项目编号
+ 项目：项目编号，项目名，项目负责人

![例2](https://lzy-lvjerry.github.io/img/blog/CS_DataBase/2019-11-26-DB_ER_to_Relation5.png)
+ 职工：职工号，姓名，年龄，职称
+ 仓库：仓库号，面积，电话号码
+ 工作：职工号，仓库号
+ 库存：仓库号，零件号，库存量
+ 零件：零件号，名称，规格，单价，描述
+ 供应商：供应商号，姓名，地址，电话号码，账号
+ 供应：项目号，供应商号，零件号，供应量
+ 项目：项目号，预算，开工日期