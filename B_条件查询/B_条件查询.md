---
title: B_条件查询
date: 2021-07-16 09:11:47
tags: 
categories: 
id: 1626397907667469600
---

# 数据库

 [myemployees.sql](assets\data\myemployees.sql) 

# 语法

```sql
select 
	查询列表
from
	表名
where
	筛选条件;
```

# 条件表达式

简单条件运算符： `>`    `<`    `=`    `!=`    `<>`    `>=`    ` <=` 

## 按条件表达式筛选

1. 查询工资>12000的员工信息

```sql
SELECT
	* 
FROM
	employees 
WHERE
	salary > 12000;
```

2. 查询部门编号不等于90号的员工名和部门编号

```sql
SELECT
	last_name,
	department_id 
FROM
	employees 
WHERE
	department_id <> 90;
```

# 逻辑表达式

1.  `&&` 或 `and` ：两个条件都为true，结果为true，反之为false
2.  `||` 或 `or` ： 只要有一个条件为true，结果为true，反之为false
3.  `!` 或 `not` ： 如果连接的条件本身为false，结果为true，反之为false

## 按逻辑表达式筛选

1. 查询工资z在10000到20000之间的员工名、工资以及奖金

```sql
SELECT
	last_name,
	salary,
	commission_pct 
FROM
	employees 
WHERE
	salary >= 10000 
	AND salary <= 20000;
```

2. 查询部门编号不是在90到110之间，或者工资高于15000的员工信息

```sql
SELECT
	* 
FROM
	employees 
WHERE
	NOT ( department_id >= 90 AND department_id <= 110 ) 
	OR salary > 15000;
```















































































































