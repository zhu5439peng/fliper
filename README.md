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

每一个独立的页面都是一个FliperSheet;
首先创建首页
```
var sheet = new createjs.FliperSheet();
```

更多的页面：
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

翻页的效果
```
//目前共有三种翻页效果，以后会继续增加
FliperSheet._EFFECTS = ["default", "translation", "scanning"];
```

设置全局翻页的效果
```
fliper.turnEffect = "scanning";
```
设置指定页面翻页效果
```
sheet3.prevEffect="translation";
sheet3.nextEffect="scanning";
```

执行翻页
```
fliper.turnPrev();
fliper.turnNext();
```

sheet更多的函数：
```
//翻页到当前页面，并且播放完翻页效果后，会执行该函数
sheet.joinHandler = function() {};
//将要翻到下一页，在准备播放翻页效果前，会执行该函数
sheet.leaveHandler = function() {};
//一个1x5的序列图，将作为翻页过程中马赛克效果图来使用
sheet.setMosaic(loader.getResult("img_name"));
```

### 联系我

您有好的翻页案例，
或者有不了解的地方，
需要洽谈的地方，都可以联系我，
我的QQ:307285468

