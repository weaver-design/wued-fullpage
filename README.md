# WUED Fullpage

How to drag and move in [fullpage.js v3](https://github.com/alvarotrigo/fullPage.js) without any extensions ? [Preview](https://weaver-design.github.io/wued-fullpage/.)

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
// Added drag and move event for fullpage.js
document.querySelector('.fullpage-wrapper').addEventListener('mousedown', function(e) {
    fullpage_api.dragAndMove = e.clientY;
});
document.querySelector('.fullpage-wrapper').addEventListener('mouseup', function(e) {
    fullpage_api.dragAndMove > e.clientY ? fullpage_api.moveSectionDown() : fullpage_api.moveSectionUp();
});
```
