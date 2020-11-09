> 概述  
> 子组件  
> 属性  
> 事件  
> 样式  
> DEMO

# 概述

开关选择器，通过开关，开启或关闭某个功能。

# 子组件

不支持。

# 属性

| 名称  | 类型   | 默认值 | 必填 | 描述                                                         |
| ----- | ------ | ------ | ---- | ------------------------------------------------------------ |
| id    | string | -      | 否   | 组件的唯一标识。                                             |
| style | string | -      | 否   | 组件的样式声明。                                             |
| class | string | -      | 否   | 组件的样式类，用于引用样式表。                               |
| ref   | string | -      | 否   | 用来指定指向子元素的引用信息，该引用将注册到父组件的$refs 属性对象上。 |
| type  | string | text   | 否   | 设置滑动选择器的类型，可选项有：<br/>**text：**文本选择器。<br/>**time：**时间选择器。 |

文本选择器：type=text

| 名称     | 类型   | 默认值 | 必填 | 描述                                                         |
| -------- | ------ | ------ | ---- | ------------------------------------------------------------ |
| range    | Array  | -      | 否   | 设置文本选择器的取值范围。<br/>**说明**：使用时需要使用数据绑定的方式，如range = {{data}}，js中声明相应变量：data：["15", "20", "25"]。 |
| selected | string | 00:00  | 否   | 设置时间选择器的默认取值，格式为 HH:mm；                     |

时间选择器：type=time

| 名称     | 类型   | 默认值 | 必填 | 描述                                     |
| -------- | ------ | ------ | ---- | ---------------------------------------- |
| selected | string | 00:00  | 否   | 设置时间选择器的默认取值，格式为 HH:mm； |



# 事件

type=text：

| 名称   | 类型                                             | 描述                           |
| ------ | ------------------------------------------------ | ------------------------------ |
| change | { newValue: newValue, newSelected: newSelected } | 文本选择器选定值后触发该事件。 |

type=time：

| 名称   | 参数                          | 描述                           |
| ------ | ----------------------------- | ------------------------------ |
| change | { hour: hour, minute: minute} | 时间选择器选定值后触发该事件。 |

# 样式

| 名称                              | 类型       | 默认值      | 必填 | 描述                                                         |
| --------------------------------- | ---------- | ----------- | ---- | ------------------------------------------------------------ |
| color                             | \<color\>  | #808080     | 否   | 候选项字体颜色。                                             |
| font-size                         | \<length\> | 30px        | 否   | 候选项字体尺寸，类型length，单位px。                         |
| selected-color                    | \<color\>  | \#ffffff    | 否   | 选中项字体颜色。                                             |
| selected-font-size                | \<length\> | 38px        | 否   | 选中项字体尺寸，类型length，单位px。                         |
| font-family                       | string     | HYQiHei-65S | 否   | 选项字体类型。                                               |
| width                             | \<length\> | 0           | 否   | 设置组件自身的宽度。未。设置时组件宽度默认为0。              |
| height                            | \<length\> | 0           | 否   | 设置组件自身的高度。未设置时组件高度默认为0。                |
| padding                           | \<length\> | 0           | 否   | 使用简写属性设置所有的内边距属性。                           |
| margin                            | \<length\> | 0           | 否   | 使用简写属性设置所有的外边距属性，该属性可以有1到4个值。<br/>只有一个值时，这个值会被指定给全部的四个边。<br/>两个值时，第一个值被匹配给上和下，第二个值被匹配给左和右。<br/>三个值时，第一个值被匹配给上, 第二个值被匹配给左和右，第三个值被匹配给下。<br/>四个值时，会依次按上、右、下、左的顺序匹配 (即顺时针顺序)。 |
| margin-[left\|top\|right\|bottom] | \<length\> | 0           | 否   | 设置左、上、右、下外边距属性。                               |
| border-width                      | \<length\> | 0           | 否   | 使用简写属性设置元素的所有边框宽度。                         |
| border-color                      | \<color\>  | black       | 否   | 使用简写属性设置元素的所有边框颜色。                         |
| border-radius                     | \<length\> | -           | 否   | border-radius属性是设置元素的外边框圆角半径。                |
| background-color                  | \<color\>  | -           | 否   | 设置背景颜色。                                               |
| display                           | string     | flex        | 否   | 确定一个元素所产生的框的类型，可选值为：<br/>**flex：**弹性布局。<br/>**none：**不渲染此元素。 |
| [left\|top]                       | \<length\> | 否          | 否   | left\|top需要配合position样式使用，来确定元素的偏移位置。<br/>left属性规定元素的左边缘。该属性定义了定位元素左外边距边界与其包含块左边界之间的偏移。<br/>top属性规定元素的顶部边缘。该属性定义了一个定位元素的上外边距边界与其包含块上边界之间的偏移。 |

# DEMO

构成一个页面的三个部分，`index.hml`,`index.css`,`index.js`。

>  请注意默认还有一个[app.js](/zh-cn/js-file "app.js")文件。

代码仓库地址：`http://gitlab.evmiot.com:12306/wzedmund/evm-jsfwk-littlevgl-qt/tree/dev/test/test-picker-view`

**index.hml**

```html
<div class="container">
    <picker-view type="text" selected="0" range="[ 'a', 'b', 'c', 'd']"
                 style="left: 175px;
                        top: 50px;
                        width: 280px;
                        height: 50px;
                        margin-top: 10px;
                        margin-left: 85px;
                        background-color: red;">
    </picker-view>
    <picker-view type="text" selected="1" range="[ '1', '2', '3', '4']"
                 style="left: 175px;
                        top: 110px;
                        width: 280px;
                        height: 50px;
                        margin-top: 10px;
                        margin-left: 85px;
                        border-radius: 10px;">
    </picker-view>
    <picker-view type="text" selected="2" range="[ 'a', 'b', 'c', 'd']"
                 style="left: 175px;
                        top: 170px;
                        width: 280px;
                        height: 50px;
                        margin-top: 10px;
                        margin-left: 85px;
                        padding: 10px;">
    </picker-view>
    <picker-view type="text" selected="3" range="[ 'a', 'b', 'c', 'd']"
                 style="left: 175px;
                        top: 230px;
                        height: 50px;
                        margin-top: 10px;
                        margin-left: 85px;
                        border-width: 3px;
                        border-color: yellow;">
    </picker-view>
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
```

**index.js**

```javascript
export default {
    data: {
        title: 'test-picker-view'
    }
}
```

## 执行命令

下面可以在命令行输入以下命令，体验下DEMO，请根据自己实际的目录以及操作系统输入命令：

**Linux**

```shell
cd evuesimulator-linux-v2.0
./evuesimulator test/test-picker-view/
```

**Windows**

```powershell
cd evuesimulator-windows-v2.0
evuesimulator.exe test/test-picker-view/
```

## 运行截图

一切顺利的话，你将会看到如下页面：

![](http://statics.evmiot.com/Peek-2020-10-31-22-58.gif)

