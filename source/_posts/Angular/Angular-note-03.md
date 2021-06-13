---
title: Angular-note-03
tags:
  - Angular
categories: Angular
abbrlink: 86b3ed03
date: 2021-06-13 03:25:39
description:
---
# Angular 03- 資料繫結方法(二) - 屬性繫結(Property Binding)
**基本概念**
---
* 語法 `[ property ] = "value"`

* 概念：單向繫結，由component.ts將變數單向綁定到template(html)畫面上。

**重要觀念釐清**
---
* Property 和 Attribute在中文都是屬性，但是不同的概念，在此無法綁定HTML attribute，例如```[data-title] = "title"``` 是無效的

* 在chrome dev tool 可以查詢到properties
![](https://i.imgur.com/RPL5IdX.jpg)

* 舉例：以下綁定的是img這個DOM的property，而非HTML的attribute，若真要綁定可以加上`[attr.]`，例如`[attr.data-title]="title"`

**運用**
---
**HTML**
```typescript
<img [title]="title" [src]="imgurl" />

<h1><a [href]="url"></a></h1>
```
**TS**
```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.scss']
})
export class AppComponent {
  title = '前端小白';
  url = 'www.google.com';
  imgurl = '/assets/images/logo.png';
  constructor() {
    setTimeout(() => {
      this.title = "Google";
    }, 2000);
  }
}
```