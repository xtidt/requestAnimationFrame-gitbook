#  cancelAnimationFrame方法

 cancelAnimationFrame方法用于取消重绘。

```
window.cancelAnimationFrame(requestID);
```

 它的参数是requestAnimationFrame返回的一个代表任务ID的整数值。

```
var globalID;

function repeatOften() {
  $("<div />").appendTo("body");
  globalID = requestAnimationFrame(repeatOften);
}

$("#start").on("click", function() {
  globalID = requestAnimationFrame(repeatOften);
});

$("#stop").on("click", function() {
  cancelAnimationFrame(globalID);
});
```

 上面代码持续在body元素下添加div元素，直到用户点击stop按钮为止。



