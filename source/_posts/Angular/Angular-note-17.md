---
title: Angular 17- Pipes管線元件 - Percent Pipe
tags:
  - Angular
categories: Angular
date: 2021-06-14 02:12:33
description: Percent Pipe
abbrlink:
---
```html
@Component({
  selector: 'percent-pipe',
  template: `<div>

    <!-- 預設為整數 -->
    <!--output '26%'-->
    <p>A: {{a | percent}}</p>

    <!--output '0,134.950%'-->
    <p>B: {{b | percent:'4.3-5'}}</p>

    <!--output '0 134,950 %'-->
    <p>B: {{b | percent:'4.3-5':'fr'}}</p>
  </div>`
})
export class PercentPipeComponent {
  a: number = 0.259;
  b: number = 1.3495;
}
```
