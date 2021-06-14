---
title: Angular 15- Pipes管線元件 - Decimal Pipe - number
tags:
  - Angular
categories: Angular
date: 2021-06-14 02:00:10
description: Decimal Pipe
abbrlink:
---
Pipes管線元件 - number - Decimal Pipe
```typescript
{{ value_expression | number [ : digitsInfo [ : locale ] ] }}
```
* 一般未設定格式
```typescript
No specified formatting:
{{pi | number}}

<!--output: '3.142'-->
```

* 設定number
* 格式：{minIntegerDigits}.{minFractionDigits}-{maxFractionDigits}
* 意涵：{小數點前幾位數}.{小數點後最少幾位數}-{小數點後最多幾位數}
```typescript
With digitsInfo parameter specified:

{{pi | number:'4.1-5'}}

<!--output: '0,003.14159'-->
```
* 設定number+locale
* 放國家名稱，會顯示該國數值表示方式
* 舉例-法國(fr)、台灣(zh-tw)、日本(jp)
```typescript
With digitsInfo and locale parameters specified:

{{pi | number:'4.1-5':'fr'}}

<!-- fr 採法國的格式，千分號空格，小數點用逗號， -->
<!--output: '0 003,14159'-->
```