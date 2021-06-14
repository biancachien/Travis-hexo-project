---
title: Angular 01- 專案介紹 & CLI
tags:
  - Angular
categories: Angular
description: 專案介紹 & CLI
abbrlink: fb6cf8f6
date: 2021-06-12 18:39:00
---
**專案介紹**
---
**設定檔**

![menu](https://i.imgur.com/TsEGF3o.jpg)
- angular.json：angular.cli的設定檔。
- .editotconfig：編輯器的設定檔。
- package.json：npm的設定檔。
- tsconfig.json：存放TypeScript相關設定。
- tslint：程式碼檢查規則的存放處。
- protractor.conf.js：實作end-2-end testing的設定檔。
- e2e資料夾：存放end-to-end testing所有測試的指定檔。

**主檔案**

![main](https://i.imgur.com/fKLGgkD.jpg)
- assets：存放靜態檔案。
- environments：存放angular環境變數。
- favicon：網頁頁籤左上角的顯示小圖示。
- html：index.html。
- css：style.scss。
- js：mian.ts(JS主程式的進入點)。
- poltfills.ts：使舊版本瀏覽器也可使用新語法。

**用Angular CLI 建立 component**
---

輸入` ng generate component 名稱 ` 或簡寫 ` ng g c component 名稱 `會自動生成component，並設定module裡的資料

![ng generate](https://i.imgur.com/r0euXIM.jpg)

除了自動建立上述檔案外，還修改了app.module.ts

![module](https://i.imgur.com/A1GeQza.jpg)

**讓component出現在主畫面上的方式**

將`<app-page1></app-page1>`貼在要顯示的html上

![](https://i.imgur.com/sCqoMA4.jpg)

**常用快速鍵**

`alt + o`：快速切換ts檔和html檔

`ng generate -h`：可產生的程式碼類型範本皆在此(程式碼產生器)

**發行與部屬Angular應用程式**

`ng build`：會打包成一個dist檔

`ng build --prod`：會壓縮成更小的dist檔


**升級新版Angular應用程式**

`ng update`：升級新版Angular應用程式的方法

`npm outdated -g`：看是否是最新版 

`npm install -g @angular/cli`：安裝最新版

[angular-update-guide](//https://update.angular.io/)：可看版本升級須注意事項