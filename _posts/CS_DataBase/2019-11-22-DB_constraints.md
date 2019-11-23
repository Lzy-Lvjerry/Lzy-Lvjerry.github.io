---
layout:     post
title:      "数据库-约束的使用（一）"
subtitle:   "常见约束"
date:       2019-11-23 15:00:00
author:     "lzy"
header-img: "img/post-bg-2015.jpg"
catalog: true
tags:
    - 数据库
    - 计算机学科
---
### 常见约束
+ **primary key**：属性值不允许为空，且不允许重复（实体完整性约束）
+ **not null**：属性值不允许为空，但可以有重复值
+ **null**：创建记录时，默认为空值
+ **unique**：属性值不允许重复，但可以有多个空值
+ **default**：设定列的默认值
+ **check**：限定字段中值的范围
+ **foreign key**(name) **reference** table_name(name)：外键约束，当有删除或者更新操作的时候发出这个约束。（参照完整性约束）
    + **On Delete** 
         + restrict：当父表中删除记录时（即外键来源表）检查是否有对应外键，如果有则不允许删除。
         + no action：与restrict一样
         + cascade（级联）：首先检查该记录是否有对应的外键，如果有的话，则连同包含该外键的记录一起删除。
         + set null：若有对应外键，则将其外表中该外键的值设为null（不过这就需要该外键允许为null）
    + **On Update**：与On Delete一样也有四个参照完整性的违约处理。

```$xslt
create table user_info(
  id CHAR(36) CONSTRAINT PK_userinfo PRIMARY KEY,
  school_id CHAR(30) REFERENCES tb_school(sid),
  user_name VARCHAR(30) unique,
  gender CHAR(10),
  password VARCHAR(30) not null,
  city VARCHAR(30) default 'Beijing',
  age INTEGER,
  remark VARCHAR(150) NULL,
  check(age>0 and age<150),
  check(gender IN ('male','female'),
  // CONSTRAINT PK_userinfo PRIMARY KEY(id),
  // FOREIGN KEY(school_id) REFERENCES tb_shcool(id) 
  // ON DELETE CASCADE ON UPDATE SET NULL
);

// 也可以创建表后添加
  1. ADD CONSTRAINT PK_userinfo PRIMARY KEY(id);
  2. ALTER TABLE user_info 
     ADD CONSTRAINT FK_userinfo_regionkey 
     FOREIGN KEY(school_id) REFERENCES tb_school(sid);

```

  
