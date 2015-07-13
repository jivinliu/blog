# requestAnimationFrame

```js
window.requestAnimationFrame = window.requestAnimationFrame || window.mozRequestAnimationFrame || window.webkitRequestAnimationFrame || window.msRequestAnimationFrame;

var i = 0;
function foo() {
    console.log(i++);

    if (i < 1000) {
        requestAnimationFrame(foo)
    }
}

requestAnimationFrame(foo)
```