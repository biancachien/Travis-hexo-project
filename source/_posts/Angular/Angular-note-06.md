---
title: Angular 06- 資料繫結方法(四) - 雙向繫結(Two-Way Binding)
tags:
  - Angular
categories: Angular
date: 2021-06-13 21:57:19
description: 雙向繫結(Two-Way Binding)
abbrlink:
---
**基本概念**
---
* 語法： `[(ngModel)] = "property"`

* 概念：雙向繫結，為屬性繫結和事件繫結的結合體，由template(html)和component(ts)雙向綁定。但效能可能會稍差一點。

**運用**
---
**HTML**

```typescript
<div class="widget search">
  <div class="widget-content">
     <div id="searchbox">
        <input type="text" [(ngModel)]="keyword" (keyup.escape)="keywordReset()" aceholder="請輸入搜尋關鍵字" accesskey="s">
        <input type="button" value="搜尋" id="searchbutton">
        <br>關鍵字：{{ keyword }} 目前字數：{{ keyword.length }}
    </div>
  </div>
</div>
```

**Component**
```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.scss']
})
export class AppComponent {
  title = 'app';
  url = 'http://blog.miniasp.com/';
  imgurl = '/assets/images/logo.png';
  wordcount = 0;
  constructor() {
  }
  changeTitle(altKey: boolean) {
    if (altKey) {
      this.title = 'The Will Will Web';
    }
  }
  keywordChanges(event: Event) {
    let keyword = (event.target as HTMLInputElement).value;
    this.wordcount = keyword.length;
  }
  keywordReset(event: Event) {
    let input = (event.target as HTMLInputElement);
    input.value = '';
    this.wordcount = 0;
  }
}
```

**Module**<br>
引入FormsModule
```typescript
import { NgModule } from '@angular/core';
import { FormsModule } from '@angular/forms';
import { BrowserModule } from '@angular/platform-browser';

import { AppRoutingModule } from './app-routing.module';
import { AppComponent } from './app.component';
import { Page2Component } from './page2/page2.component';

@NgModule({
  declarations: [
    AppComponent,
    Page2Component
  ],
  imports: [
    BrowserModule,
    AppRoutingModule,
    FormsModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```