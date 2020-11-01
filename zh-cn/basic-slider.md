> 子组件  
> 属性  
> 事件  
> 样式  

滑动条组件，用来快速调节设置值，如音量、亮度等。

# 子组件
不支持。

# 属性

| 名称  | 类型   | 默认值 | 必填 | 描述                                                         |
| ----- | ------ | ------ | ---- | ------------------------------------------------------------ |
| id    | string | -      | 否   | 组件的唯一标识。                                             |
| style | string | -      | 否   | 组件的样式声明。                                             |
| class | string | -      | 否   | 组件的样式类，用于引用样式表。                               |
| ref   | string | -      | 否   | 用来指定指向子元素的引用信息，该引用将注册到父组件的$refs 属性对象上。 |
| min   | number | 0      | 否   | 滑动选择器的最小值。                                         |
| max   | number | 100    | 否   | 滑动选择器的最大值。                                         |
| value | number | 0      | 否   | 滑动选择器的初始值。                                         |

# 事件

| 名称      | 参数                        | 描述                         |
| --------- | --------------------------- | ---------------------------- |
| click     | -                           | 点击动作触发该事件。         |
| longpress | -                           | 长按动作触发该事件。         |
| swipe     | SwipeEvent                  | 组件上快速滑动后触发。       |
| change    | { progress: progressValue } | 选择值发生变化时触发该事件。 |

# 样式

| 名称                              | 类型       | 默认值   | 必填 | 描述                                                         |
| --------------------------------- | ---------- | -------- | ---- | ------------------------------------------------------------ |
| color                             | \<color\>  | #6b9ac7  | 否   | 滑动条的背景颜色。                                           |
| selected-color                    | \<color\>  | \#ffffff | 否   | 滑动条的已选择颜色。                                         |
| block-color                       | \<color\>  | \#6b9ac7 | 否   | 滑动条的滑块颜色。                                           |
| width                             | \<length\> | 0        | 否   | 设置组件自身的宽度。未。设置时组件宽度默认为0。              |
| height                            | \<length\> | 0        | 否   | 设置组件自身的高度。未设置时组件高度默认为0。                |
| padding                           | \<length\> | 0        | 否   | 使用简写属性设置所有的内边距属性。                           |
| margin                            | \<length\> | 0        | 否   | 使用简写属性设置所有的外边距属性，该属性可以有1到4个值。<br/>只有一个值时，这个值会被指定给全部的四个边。<br/>两个值时，第一个值被匹配给上和下，第二个值被匹配给左和右。<br/>三个值时，第一个值被匹配给上, 第二个值被匹配给左和右，第三个值被匹配给下。<br/>四个值时，会依次按上、右、下、左的顺序匹配 (即顺时针顺序)。 |
| margin-[left\|top\|right\|bottom] | \<length\> | 0        | 否   | 设置左、上、右、下外边距属性。                               |
| border-width                      | \<length\> | 0        | 否   | 使用简写属性设置元素的所有边框宽度。                         |
| border-color                      | \<color\>  | black    | 否   | 使用简写属性设置元素的所有边框颜色。                         |
| border-radius                     | \<length\> | -        | 否   | border-radius属性是设置元素的外边框圆角半径。                |
| background-color                  | \<color\>  | -        | 否   | 设置背景颜色。                                               |
| display                           | string     | flex     | 否   | 确定一个元素所产生的框的类型，可选值为：<br/>**flex：**弹性布局。<br/>**none：**不渲染此元素。 |
| [left\|top]                       | \<length\> | 否       | 否   | left\|top需要配合position样式使用，来确定元素的偏移位置。<br/>left属性规定元素的左边缘。该属性定义了定位元素左外边距边界与其包含块左边界之间的偏移。<br/>top属性规定元素的顶部边缘。该属性定义了一个定位元素的上外边距边界与其包含块上边界之间的偏移。 |

# DEMO

构成一个页面的三个部分，`index.hml`,`index.css`,`index.js`。

>  请注意默认还有一个[app.js](/zh-cn/js-file "app.js")文件。

代码仓库地址：`http://gitlab.evmiot.com:12306/wzedmund/evm-jsfwk-littlevgl-qt/tree/dev/test/test-slider`

**index.hml**

```html
<div class="container">
    <list class="list-container">
        <list-item class="listitem">
            <slider min="0" max="100" value="25" style="padding: 1px;margin-top: 20px;border-width: 1px;border-color: red;"></slider>
        </list-item>
        <list-item class="listitem">
            <slider min="0" max="100" value="50" style="width: 150px;height: 30px;"></slider>
        </list-item>
        <list-item class="listitem">
            <slider min="0" max="100" value="75" style="background-color: red;"></slider>
        </list-item>
        <list-item class="listitem">
            <slider min="0" max="100" value="100"></slider>
        </list-item>
    </list>
</div>
```

**index.css**

```css
.container {
    display: flex;
    width: 454px;
    height: 454px;
    border-width: 2px;
    border-radius: 2px;
    margin: 0px;
    padding: 0px;
    background-color: green;
}

.list-container {
    width: 300px;
    height: 300px;
    left: 75px;
    top: 75px;
    background-color: yellow;
}

.listitem {
    flex-direction: column;
    align-items: center;
    width: 300px;
    height: 60px;
    margin: 0px;
    padding: 10px;
}
```

**index.js**

```javascript
export default {
    data: {
        title: 'test-slider'
    }
}
```

## 执行命令

下面可以在命令行输入以下命令，体验下DEMO，请根据自己实际的目录以及操作系统输入命令：

**Linux**

```shell
wanli@wanli-PC:~/projects/evm-jsfwk-littlevgl-qt/bin/x86_64-linux-gnu$ ./evue ../../test/test-slider/
```

**Windows**

```powershell
PS D:~/projects/evm-jsfwk-littlevgl-qt/bin/x86_64-window-mingw>evue.exe ../../test/test-slider/
```

## 运行截图

一切顺利的话，你将会看到如下页面：

![](http://statics.evmiot.com/evue_20201031224335.jpg)
