---
title: Angular-note-22
tags:
  - Angular
categories: Angular
date: 2021-06-14 03:25:57
description:
abbrlink:
---
避面出現型別錯誤

方法一(傳統避免檢查方法)
['  ']

{{ item['subject']?.title | uppercase |slice:-20}}

方法二
$any(   )

{{ $any(item).subject?.title | uppercase |slice:-20}}

建立module的指令
ng g m article
建立module的指令(plus直接建立注入到app module中)
ng g m article -m app

自動建立component(記得切換到那個資料夾下)
![](https://i.imgur.com/Y1JVh6t.jpg)