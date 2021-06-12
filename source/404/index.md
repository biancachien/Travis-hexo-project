---
title: '404'
date: 2021-06-12 10:01:35
comments: false
permalink: /404.html
---

<!-- markdownlint-disable MD039 MD033 -->

## 這是一個不存在的頁面

很抱歉，你目前存取的頁面並不存在。

預計將在 <span id="timeout">5</span> 秒後返回首頁。

或 **[點這裡](https://hsiangfeng.github.io/)** 返回首頁。

<script>
let countTime = 5;

function count() {
  
  document.getElementById('timeout').textContent = countTime;
  countTime -= 1;
  if(countTime === 0){
    location.href = 'https://biancachien.github.io/';
  }
  setTimeout(() => {
    count();
  }, 1000);
}

count();
</script>