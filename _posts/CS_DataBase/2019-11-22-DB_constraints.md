---
layout:     post
title:      "数据库-约束的使用（一）"
subtitle:   "常见约束"
date:       2019-11-22 15:00:00
author:     "lzy"
header-img: "img/post-bg-2015.jpg"
catalog: true
tags:
    - 数据库
    - 计算机学科
---
### 常见约束
+ **primary key**：属性值不允许为空，且不允许重复
+ **not null**：属性值不允许为空，但可以有重复值
+ **unique**：属性值不允许重复，但可以有多个空值
    
```$xslt
create table user_info(
  id char(36) primary key,
  user_name varchar(30) unique,
  password varchar(30) not null
);
```


+ **foreign key**(name) **reference** table_name(name)：外键约束，当有删除或者更新操作的时候发出这个约束。
    + On Delete
        + restrict：当父表中删除记录时（即外键来源表）检查是否有对应外键，如果有则不允许删除。
        + no action：与restrict一样
        + cascade（级联）：首先检查该记录是否有对应的外键，如果有的话，则连同包含该外键的记录一起删除。
        + set null：若有对应外键，则将其外表中该外键的值设为null（不过这就需要该外键允许为null）
    + On Update：与On Delete一样也有四个约束属性。
    
    > 主表：主键所在的表                                                                                                                                                                                                                                                                                                                                                         >
    <br> 子表：外键所在的表
    ```$xslt
    ALTER TABLE 子表 ADD CONSTRAINT 外键名 FOREIGN KEY (关联字段) 
    REFERENCES 主表(被关联的字段) on delete cascade on update restrict;
    ```

