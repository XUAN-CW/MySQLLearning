---
title: C_模糊查询
date: 2021-07-16 09:11:47
tags: 
categories: 
id: 1626397907668869600
---

# 数据库

 [myemployees.sql](assets\data\myemployees.sql) 

# like

一般和通配符搭配使用，通配符：

1. `%` 任意多个字符,包含0个字符
2. `_` 任意单个字符

## 案例

1. 查询员工名中包含字符a的员工信息

```sql
SELECT
	* 
FROM
	employees 
WHERE
	last_name LIKE '%a%';
```

2. 查询员工名中第三个字符为e，第五个字符为a的员工名和工资

```sql
SELECT
	last_name,
	salary 
FROM
	employees 
WHERE
	last_name LIKE '__n_l%';
```

3. 查询员工名中第二个字符为 `_` 的员工名

```sql
SELECT
	last_name
FROM
	employees
WHERE
	last_name LIKE '_$_%' ESCAPE '$';
```

# between and

1. 包含临界值
2. 两个临界值不要调换顺序

## 案例

查询员工编号在100到120之间的员工信息

```sql
SELECT
	* 
FROM
	employees 
WHERE
	employee_id BETWEEN 100 
	AND 120;
```

# in

1. in 列表的值类型必须一致或兼容
2. in 列表中不支持通配符

## 案例

查询员工的工种编号是 **IT_PROG**、**AD_VP**、**AD_PRES** 中的一个员工名和工种编号

```sql
SELECT
	last_name,
	job_id 
FROM
	employees 
WHERE
	job_id IN ( 'IT_PROT', 'AD_VP', 'AD_PRES' );
```

# is null 和 is not null

`=` 或 `<>` 不能用于判断 `null` 值，
`is null` 或 `is not null` 可以判断 `null` 值

## 案例

1. 查询没有奖金的员工名和奖金率

```sql
SELECT
	last_name,
	commission_pct 
FROM
	employees 
WHERE
	commission_pct IS NULL;
```

2. 查询有奖金的员工名和奖金率

```sql
SELECT
	last_name,
	commission_pct 
FROM
	employees 
WHERE
	commission_pct IS NOT NULL;
```























































