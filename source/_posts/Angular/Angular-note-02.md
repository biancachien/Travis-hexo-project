---
title: Angular 02- 資料繫結方法(一) - 內嵌繫結(Interpolation)
tags:
  - Angular
categories: Angular
description: '內嵌繫結(Interpolation)-{{ property }}'
abbrlink: ec3b586
date:
---
**基本概念**
---

語法 `{{ value }}`

概念：單向繫結，由component.ts將變數單向綁定到template(html)畫面上。

**運用在標籤**
---

**HTML**

```typescript
<h3>{{ title }}</h3>
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
}
```

**運用在屬性**
---

**HTML**

```typescript
<h3><a href="{{ url }}">Google</a></h3>
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
  url = 'www.google.com';
}
```
**動態綁定**
---
**HTML**
```typescript
<h3><a href="{{ url }}">{{title}}</a></h3>
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
  constructor() {
    setTimeout(() => {
      this.title = "Google";
    }, 2000);
  }
}
```
