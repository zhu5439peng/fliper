fliper
======

基于createjs实现的翻页类

### 依赖的类包
你需要在html的项目下，引入createjs的以下三个类
```
easeljs.js
preloadjs.js
tweenjs.js
```

### 使用方法

每一个独立的页面都是一个FliperSheet
首先创建首页
```
var sheet = new createjs.FliperSheet();
```

更多的页面可以像这样创建：
```
var sheet2 = new createjs.FliperSheet(sheet);
var sheet3 = new createjs.FliperSheet(sheet2);
var sheet4 = new createjs.FliperSheet(sheet3);
……
```

创建一个全局fliper，并传入首页和舞台
```
var fliper = new createjs.Fliper(sheet, stage);
```
你可以设置翻页的效果
```
fliper.turnEffect = "scanning";
```

你可以这样执行翻页
```
fliper.turnPrev();
fliper.turnNext();
```

