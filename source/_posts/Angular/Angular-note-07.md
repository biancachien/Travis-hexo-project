---
title: Angular 07- 範本參考變數(Template reference variables)
tags:
  - Angular
categories: Angular
date: 2021-06-13 23:04:53
description: 範本參考變數
abbrlink:
---
**基本概念**
---
* 語法：`#名稱`
* 僅能在Template使用
* 可在Template的任意HTML標籤套用
* 該名稱為區域變數將會儲存該標籤的DOM物件
* 可透過事件繫結方式，將任意DOM物件中的任意屬性傳回元件類別中(component class)
* 使用#為語法糖(#name等於ref-name)
* 建立的名稱盡量不要和template的property名稱衝突

**運用在DOM物件上**
---
**HTML**

* #tkeyword
* 目前字數：{{ tkeyword.value.length }}
```typescript
<div class="widget search">
  <div class="widget-content">
    <div id="searchbox">
      <input type="text" #tkeyword [(ngModel)]="keyword" (keyup.escape)="keywordReset()" placeholder="請輸入搜尋關鍵字"
                accesskey="s">
      <input type="button" value="搜尋" id="searchbutton">
      <br>關鍵字：{{ keyword }} 目前字數：{{ tkeyword.value.length }}
    </div>
  </div>
</div>
```

**運用在directive上**
---
* 將hearder移建另外一個新建的component
* 原html上只需放：
* #tHeader
* (click)="tHeader.title = 'title changed'"

**HTML**
```typescript
<app-header #tHeader></app-header>

<!-- CONTAINER START-->
<section class="container" (click)="tHeader.title = 'title changed'">
```
**TS**
亦須將原header需用到的功能，搬至新的component