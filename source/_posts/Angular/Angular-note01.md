---
title: Angular 學習筆記 - 專案介紹 & CLI
tags:
  - Angular
categories: Angular
description: note
date: 2021-06-12 18:39:00
abbrlink:
---
# Angular 學習筆記 - 專案介紹 & CLI
**設定檔**
---
![menu](https://i.imgur.com/TsEGF3o.jpg)
- angular.json：angular.cli的設定檔。
- .editotconfig：編輯器的設定檔。
- package.json：npm的設定檔。
- tsconfig.json：存放TypeScript相關設定。
- tslint：程式碼檢查規則的存放處。
- protractor.conf.js：實作end-2-end testing的設定檔。
- e2e資料夾：存放end-to-end testing所有測試的指定檔。

**主檔案**
---
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
會自動生成component，並設定module裡的資料
`  ng generate component名稱  ` 或 ` ng g c component名稱 `

可產生的類型(程式碼產生器)
`  ng generate -h  `

**一些常用快速鍵**
---
可以在兩頁面間來回切換
`  alt + o  `

可產生的類型(程式碼產生器)
`  ng generate -h `

**component 顯示在頁面上的方法**
---
貼在要顯示的html上
`<app-page1></app-page1>`