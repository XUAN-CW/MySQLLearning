---
title: D_排序查询
date: 2021-07-16 13:49:49
tags: 
categories: 
id: 1626414589232974600
---

# 数据库

#  [myemployees.sql](assets\data\myemployees.sql) 

# 语法

```sql
SELECT
	查询列表 
FROM
	表名
WHERE
	筛选条件
ORDER BY
	排序的字段或表达式;
```

1. `asc` 代表升序，可以省略； `desc` 代表降序

2. `order by` 子句可以支持 单个字段、别名、表达式、函数、多个字段

3. `order by` 子句在查询语句的最后面，除了 `limit` 子句

# 案例

## 按单个字段排序

```sql

SELECT
	* 
FROM
	employees 
ORDER BY
	salary DESC;
```

## 添加筛选条件再排序

查询部门编号>=90的员工信息，并按员工编号降序

```sql

SELECT
	* 
FROM
	employees 
WHERE
	department_id >= 90 
ORDER BY
	employee_id DESC;
```

## 按表达式排序

查询员工信息 按年薪降序

```sql
SELECT
	*,
	salary * 12 * ( 1+ IFNULL( commission_pct, 0 ) ) 
FROM
	employees 
ORDER BY
	salary * 12 * ( 1+ IFNULL( commission_pct, 0 ) ) DESC;
```

## 按别名排序

查询员工信息 按年薪升序

```sql

SELECT
	*,
	salary * 12 * ( 1+ IFNULL( commission_pct, 0 ) ) 年薪 
FROM
	employees 
ORDER BY
	年薪 ASC;
```

## 按函数排序

查询员工名，并且按名字的长度降序

```sql

SELECT
	LENGTH( last_name ),
	last_name 
FROM
	employees 
ORDER BY
	LENGTH( last_name ) DESC;
```

## 按多个字段排序

查询员工信息，要求先按工资降序，再按 `employee_id` 升序

```sql

SELECT
	* 
FROM
	employees 
ORDER BY
	salary DESC,
employee_id ASC;
```





