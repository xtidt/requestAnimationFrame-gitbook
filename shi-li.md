## 实例 {#实例}

下面，举一个实例。

假定网页中有一个动画区块。

```
<div id="anim">点击运行动画</div>
```

然后，定义动画效果。

```
var elem = document.getElementById("anim");

var startTime = undefined;

function render(time) {

  if (time === undefined)
    time = Date.now();
  if (startTime === undefined)
    startTime = time;

  elem.style.left = ((time - startTime)/10 % 500) + "px";
}
```

最后，定义click事件。

```
elem.onclick = function() {

    (function animloop(){
      render();
      requestAnimFrame(animloop);
    })();

};
```

 运行效果可查看[jsfiddle](http://jsfiddle.net/paul/rjbGw/3/)。

