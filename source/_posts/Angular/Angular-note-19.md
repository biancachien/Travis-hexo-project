---
title: Angular 19- Pipes管線元件 - JSON Pipe
tags:
  - Angular
categories: Angular
date: 2021-06-14 02:38:47
description: JSON Pipe
abbrlink:
---
可將任何的值轉成JSON格式

把一個值轉換成 JSON 字串格式，可以直接在畫面上除錯

格式
{{ value_expression | json }}

舉例
<!-- 可用來偵錯 -->
<pre>{{ item | json }}</pre>

