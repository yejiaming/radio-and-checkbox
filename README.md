# radio-and-checkbox
纯CSS实现radio和checkbox实现效果

## reset-radio 
* 在开发PC端的项目时，经常会用到radio和checkbox组件，可是因为原生的样式相对来说不符合设计师的设计风格，所以我们可能会经常引用第三方的模块去实现，或者通过JS等其他方式去hack。这样相对来说增加了代码量不说，还特别复杂，所以才有了这个纯CSS依赖原生input[radio]和input[checkbox]的实现方式，主要代码如下：

* html主要代码

```html
<div class="reset-radio">
    <input checked type="radio" id="age1" name="age">
    <span class="real-target"></span>
</div>
```

* CSS代码，这里主要是通过一个子节点span去配合input:checked兄弟选择器，来修改样式

```css
.reset-radio {
    display: inline-block;
    position: relative;
    width: 16px;
    height: 16px;
}

.reset-radio .real-target {
    z-index: 1;
    width: 100%;
    height: 100%;
    position: absolute;
    display: inline-block;
    background: #ffffff;
    border: 1px solid #dadde0;
    border-radius: 100%;
    top: 0;
    left: 0;
    bottom: 0;
}

.reset-radio input[type=radio] {
    cursor: pointer;
    z-index: 2;
    width: 16px;
    height: 16px;
    opacity: 0;
    position: absolute;
    left: 0;
    top: 0;
    margin: 0;
    right: 0;
    bottom: 0;
}

.reset-radio input:checked+span {
    border-color: #48b4ec;
}

.reset-radio input:checked+span::before {
    content: '';
    position: absolute;
    background: #48b4ec;
    width: 6px;
    height: 6px;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    border-radius: 100%;
}
```

* 演示效果

[radio](https://chun-cssshi-xian-radioxuan-zhong-xiao-guo--yejiaming.repl.co/)
[checkbox](https://Chun-CSSShi-Xian-checkboxXuan-Zhong-Xiao-Guo--yejiaming.repl.co)

## reset-checkbox
* reset-checkbox原理是一样的就不在赘述了。

