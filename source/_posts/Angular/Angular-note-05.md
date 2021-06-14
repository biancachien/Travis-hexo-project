---
title: Angular 05- 資料繫結-小練習
tags:
  - Angular
categories: Angular
date: 2021-06-13 21:56:49
description: 小練習
abbrlink:
---
**練習題目**
---
1. 當使用者在網頁右側的關鍵字搜尋輸入文字時，會自動在輸入框的正下方顯示正在輸入的字元數。

2. 當使用者在輸入框按下 Escape 按鍵時，會自動清空輸入框的內容。

**運用**
---
**HTML**

```typescript
<div class="widget search">
  <div class="widget-content">
    <div id="searchbox">
      <input type="text" (keyup)="keywordChanges($event)" (keyup.escape)="keywordReset($event)"
                placeholder="請輸入搜尋關鍵字" accesskey="s">
      <input type="button" value="搜尋" id="searchbutton">
      <br>目前字數：{{ wordcount }}
    </div>
  </div>
</div>
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