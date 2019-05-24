# WUED Fullpage

A fullpage v3 plugin deved for WUED

## Getting Start

```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/wued-fullPage/3.0.5/fullpage.min.css" />
<script src="https://cdnjs.cloudflare.com/ajax/libs/wued-fullPage/3.0.5/fullpage.min.js"></script>
```

```js
new WUED.fullpage('#fullpage', {
  anchors: ['page1', 'page2', 'page3'],
  menu: '#myMenu',
  dragAndMove: true,
  ...
})
// 为 fullpage.js 新增拖拽效果
document.querySelector('.section.active').addEventListener('mousedown', function(e) {
  fullpage_api.dragAndMove = e.clientY;
})
document.querySelector('.section.active').addEventListener('mouseup', function(e) {
  fullpage_api.dragAndMove > e.clientY ? fullpage_api.moveSectionDown : fullpage_api.moveSectionUp;
})
```

## Target

- [X] 开发 `dragAndMove` 拖拽翻页拓展插件 
- [ ] 消除版权报错提示

## Log

```js
window.myFullpage = new fullpage('#fullpage', {
  anchors: ['page1', 'page2', 'page3', 'page4', 'page5', 'page6', 'page7', 'page8', 'page9', 'page10', 'page11', 'page12', 'page13', 'page14', 'page15', 'page16', 'page17', 'page18', 'page19', 'page20'],
  menu: '#myMenu',
  scrollingSpeed: 300,
  keyboardScrolling:true,
  dragAndMove: true,
  //滚动到第几页，第几个幻灯片；页面从1计算，幻灯片从0计算
  //moveTo(wection,slide);
  afterLoad: function(origin, destination, direction) {
      var index = destination.index;
      var marginTop = index !=1 ? -(index*40) : 0;
      $('#myMenu').animate({ marginTop: marginTop }, 'fast', 'swing');
  }
});
```

```js
// 判断鼠标拖动
var mouseDir = 0;
$('#fullpage').on('mousedown', function(e) {
  mouseDir = e.clientY;
  //console.log('鼠标按下：', e);
})
$('#fullpage').on('mouseup ', function(e) {
  //console.log('鼠标松开：', e);
  if(e.clientY < mouseDir) {
      console.log('向下拖动：');
      myFullpage.moveSectionDown();
  }else{
      console.log('向上拖动：');
      myFullpage.moveSectionUp();
  };
})
```
