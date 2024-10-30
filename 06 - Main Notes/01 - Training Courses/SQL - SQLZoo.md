---
Created Date: September 10th, 2024 08:15 PM
page-tags: "[[sql]]"
tags:
  - tutorial
  - currently-working-on
cssclasses:
---
# SQL - SQLZoo

*Tutorial from [SQLZOO](https://sqlzoo.net/wiki/SQL_Tutorial)*

## O SELECT basics



Ex: Show the population of Germany
``` SQL
SELECT population FROM world
	WHERE name = 'Germany'
```
Ex: Show the name and the population for ‘Sweden’, ‘Norway’, and ‘Denmark’
```SQL
SELECT name, population FROM world
	WHERE name IN ('Sweden', 'Norway', 'Denmark');
```
Ex: Show the country and the area for countries with an area between 200,000 and 250,000.
```SQL
SELECT name, area FROM world
	WHERE area BETWEEN 200000 AND 250000
```


## 1 SELECT name

## 2 SELECT from World

## 3 SELECT from Nobel

## 4 SELECT within SELECT

## 5 SUM and COUNT
## 6 JOIN
## 8 More JOIN operations
## 8+ Numeric Examples
## 9- Window function
## 9+ COVID 19
## 9 Self join
## 10 Tutorial Quizzes
## 11 Tutorial Student Records
## 12 Tutorial DDL







---
## References



