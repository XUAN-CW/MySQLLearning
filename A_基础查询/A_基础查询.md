---
title: A_基础查询
date: 2021-07-15 23:13:30
tags: 
categories: 
id: 1626362010416710000
---

# 数据库

 [myemployees.sql](assets\data\myemployees.sql) 

# 字段查询

## 查询表中的单个字段

```sql
SELECT
	last_name 
FROM
	employees;
```

## 查询表中的多个字段

```sql
SELECT
	last_name,
	salary,
	email 
FROM
	employees;
```

## 查询表中的所有字段

```sql
SELECT
	* 
FROM
	employees;
```

# 查询常量值

```sql
SELECT
	100;
```

```sql
SELECT
	'john';
```

# 查询表达式

```sql
SELECT
	100 % 98;
```

# 查询函数

```sql

SELECT
	VERSION( );
```

# 别名

如果要查询的字段有重名的情况，使用别名可以区分开来

## as

```sql

SELECT
	100 % 98 AS 结果;
SELECT
	last_name AS 姓,
	first_name AS 名 
FROM
	employees;
```

## 空格

```sql

SELECT
	last_name 姓,
	first_name 名 
FROM
	employees;
```

# 去重

查询员工表中涉及到的所有的部门编号

```sql
SELECT DISTINCT
	department_id 
FROM
	employees;
```

# 加号

mysql中的 `+` 号仅仅只有一个功能：运算符

## 数值+数值

两个操作数都为数值型，则做加法运算

```sql
select 100+90;
```

## 数值+字符串

只要其中一方为字符型，试图将字符型数值转换成数值型，如果转换成功，则继续做加法运算

```sql
select '123'+90;
```

如果转换失败，则将字符型数值转换成0

```sql
select 'john'+90;
```

## +null

只要其中一方为null，则结果肯定为null

```sql
select null+10;
```

# 拼接

```sql
SELECT
	CONCAT( 'a', 'b', 'c' ) AS 结果;
```

```sql
SELECT
	CONCAT( last_name,'.', first_name ) AS 姓名 
FROM
employees;
```

