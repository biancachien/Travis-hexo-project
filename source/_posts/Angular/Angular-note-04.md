---
title: Angular 04- 資料繫結方法(三) - 事件繫結(Event Binding)
tags:
  - Angular
categories: Angular
date: 2021-06-13 05:44:19
description: 事件繫結(Event Binding)
abbrlink:
---
**基本概念**
---
* 語法： `(event) = "handler"`

* 概念：單向繫結，由template(html)透過瀏覽器事件觸發後，去呼叫component(ts)上的方法。

**運用**
---
**HTML**
* 方法一：onclick 中間加入 `-`
```typescript
<img on-click="changeTitle()" [title]="title" [src]="imgurl">
```
* 方法二：onclick 改成 `(click)` (建議用法)
```typescript
<img (click)="changeTitle()" [title]="title" [src]="imgurl">
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
  }
  changeTitle() {
     this.title = "Google";
  }
}
```
**使用$event參數-取得MouseEvent的詳細資訊**
---
可注意資訊：`$event.target` 為點擊下去的DOM物件

**HTML**
```typescript
<img (click)="changeTitle($event)" [title]="title" [src]="imgurl">
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
  }
  changeTitle($event: any) {
    this.title = "Google";
    console.log($event);
  }
}
```
**練習：按altKey後點擊滑鼠改變title有兩種寫法**
---
**寫法一**

**HTML**
```typescript
<img (click)="changeTitle($event)" [title]="title" [src]="imgurl">
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
  }
  changeTitle($event: MouseEvent) { // 先輸入MouseEvent
    if ($event.altKey) {            // 可以在此直接選取altKey
       title = "Google";            // 較不易打錯字
    }
    console.log($event);
  }
}
```

**寫法二(較簡潔)**
**HTML**

```typescript
<img (click)="changeTitle($event.altKey)" [title]="title" [src]="imgurl">
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
  }
  changeTitle(altKey: boolean) {
    if (altKey) {
      this.title = "Google";
    }
  }
}
```