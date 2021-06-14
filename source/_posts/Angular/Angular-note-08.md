---
title: Angular 08- 指令類型(一) - 元件型指令(Component Directives)
tags:
  - Angular
categories: Angular
date: 2021-06-13 23:27:13
description: 元件型指令
abbrlink:
---
**基本概念**
---

* 語法：
`<app-header></app-header>`
`<app-footer></app-footer>`
* 意涵：預設「元件」就是一個含有樣板的指令
* 名稱要和component裡的selector相同

**運用**
---

**HTML-app.component.html**

```typescript
<app-header></app-header>
```

**TS-header.component.ts**<br>

* selector: 'app-header'

```typescript
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-header',
  templateUrl: './header.component.html',
  styleUrls: ['./header.component.scss']
})
export class HeaderComponent implements OnInit {
  title = 'app';
  url = 'http://blog.miniasp.com/';
  imgurl = '/assets/images/logo.png';
  constructor() { }

  ngOnInit(): void {
  }

  changeTitle(altKey: boolean) {
    if (altKey) {
      this.title = 'The Will Will Web';
    }
  }
}
```
