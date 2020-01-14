# 极简版骨架屏插件

**1）插件有四个参数**

* color：字体的背景色，默认为#DCDCDC
* bgColor：带背景图模块的背景色，默认为#F6F8FA
* rectHeight：指定区域的高度，默认为视口高度
* formFn：自定义表单着色规则

**2）初始化**
最简洁的方式是不传任何参数，调用draw()方法后才会绘制骨架屏。

```javascript
let sk = new Skeleton();
sk.draw();
```
当需要传入各类参数时，可以像下面这样。

```javascript
let sk = new Skeleton( {
    rectHeight: 2800,
    formFn: function(element) {
        while (element && !this.matches(element, "li.ui-flex"))
            element = element.parentNode;
        element && (element.style.background = this.color);
    }
} );
sk.draw();
```

关于插件的原理，可参考《[简单粗暴的骨架屏实现](https://www.cnblogs.com/strick/p/12175534.html)》一文。