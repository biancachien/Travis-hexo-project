---
title: Angular 21- 安全導覽運算子(safe navigation operator)
tags:
  - Angular
categories: Angular
date: 2021-06-14 03:00:27
description: 安全導覽運算子
abbrlink:
---

語法：?.

使用在template

如果某個需要的欄位後端api沒有資料傳進來，畫面就會掛掉
<small>{{item.subject.subtitle}}</small>

當object可能為null或undefined，就會解釋成null而不會強行讀取subtitle的值
加上安全導覽運算子就能避免這樣的錯誤發生
<small>{{item.subject?.subtitle}}</small>
