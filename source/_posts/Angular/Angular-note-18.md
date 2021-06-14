---
title: Angular 18- Pipes管線元件 - Date Pipe
tags:
  - Angular
categories: Angular
date: 2021-06-14 02:26:32
description: Date Pipe
abbrlink:
---
格式
{{ value_expression | date [ : format [ : timezone [ : locale ] ] ] }}

可以自訂規格
{{ item.date | date:'yyyy-mm-dd'}}

也可以使用已寫好的規格
{{ item.date | date:'mediumDate'}}