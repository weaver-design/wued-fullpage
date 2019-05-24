# WUED Fullpage

A fullpage.js v3 plugin deved for WUED

## Getting Start

Import plugin in your html:

```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/fullPage.js/3.0.5/fullpage.min.css">
<script src="https://cdnjs.cloudflare.com/ajax/libs/fullPage.js/3.0.5/fullpage.min.js"></script>
```
Write the strut in html:

```html
<div id="fullpage">
  <div class="section">Some section</div>
  <div class="section">Some section</div>
  <div class="section">Some section</div>
  <div class="section">Some section</div>
</div>
```

Awesome coding:

```js
new fullpage('#fullpage', {
  anchors: ['page1', 'page2', 'page3'],
  menu: '#myMenu',
  dragAndMove: true,
  ...
});
// Added drag and move for fullpage.js
document.querySelector('.fullpage-wrapper').addEventListener('mousedown', function(e) {
    fullpage_api.dragAndMove = e.clientY;
});
document.querySelector('.fullpage-wrapper').addEventListener('mouseup', function(e) {
    fullpage_api.dragAndMove > e.clientY ? fullpage_api.moveSectionDown() : fullpage_api.moveSectionUp();
});
```

## Target

- [X] 开发 `dragAndMove` 拖拽翻页拓展插件 
- [ ] 消除版权报错提示
