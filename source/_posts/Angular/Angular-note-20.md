---
title: Angular 20- Pipes管線元件 - Slice Pipe
tags:
  - Angular
categories: Angular
date: 2021-06-14 02:47:56
description: Slice Pipe
abbrlink:
---

{{ value_expression | slice : start [ : end ] }}

start一定要寫

pipe可以相接，先做完轉大寫，在丟給slice，取出字串的0-20個字元
{{ item.title | uppercase |slice:0:20}}

也可以用負數，從最後面開始算
{{ item.title | uppercase |slice:-20}}

也可以處理array(做分頁功能，一頁顯示幾筆)
0為第一筆
*ngFor="let item of data | slice:0:2;

從第四筆開始跑到最後(start:3後面不寫第二個數字就會跑到最後)
*ngFor="let item of data | slice:3;
