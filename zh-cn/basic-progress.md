> 子组件  
> 属性  
> 事件  
> 样式  
> DEMO

进度条，用于显示内容加载或操作处理进度。


# 子组件
不支持。

# 属性

| 名称 | 类型   | 默认值     | 必填 | 描述                                                         |
| ---- | ------ | ---------- | ---- | ------------------------------------------------------------ |
| type | string | horizontal | 否   | 设置进度条的类型，该属性不支持动态修改，可选值为：<br>**horizontal**：线性进度条；<br/>**arc**：弧形进度条。 |
| id   | string | -          | 否   | 组件的唯一标识。                                             |
| style | string | - | 否 | 组件的样式声明。 |
| class | string | - | 否 | 组件的样式类，用于引用样式表。 |
| ref | string | - | 否 | 用来指定指向子元素的引用信息，该引用将注册到父组件的$refs 属性对象上。 |

不同类型的进度条还支持不同的属性：
* 类型为horizontal时，支持如下属性：

|  名称   | 类型  | 默认值  | 必填  | 描述  |
|  ----  | ----  | ----  | ----  | ----  |
| percent  | number | 0 | 否 | 当前进度。取值范围为0-100。 |


* 类型为arc时，支持如下属性：

|  名称   | 类型  | 默认值  | 必填  | 描述  |
|  ----  | ----  | ----  | ----  | ----  |
| percent  | number | 0 | 否 | 当前进度。取值范围为0-100。 |

# 事件
|  名称   | 参数  | 描述  |
|  ----  | ----  | ----  |
| click  | - | 点击动作触发该事件。 |
| longpress  | - | 长按动作触发该事件。 |
| swipe  | SwipeEvent | 组件上快速滑动后触发。 |

# 样式

## type=horizontal

| 名称         | 类型       | 默认值   | 必填 | 描述               |
| ------------ | ---------- | -------- | ---- | ------------------ |
| color        | \<color\>  | \#6b9ac7 | 否   | 设置进度条的颜色。 |
| stroke-width | \<length\> | 32px     | 否   | 设置进度条的宽度。 |

## type=arc

| 名称             | 类型       | 默认值 | 必填 | 描述                                                         |
| ---------------- | ---------- | ------ | ---- | ------------------------------------------------------------ |
| color            | \<color\>  | -      | 否   | 弧形进度条的颜色。                                           |
| background-color | \<color\>  | -      | 否   | 弧形进度条的背景色。                                         |
| stroke-width     | \<length\> | -      | 否   | 弧形进度条的宽度。<br/>**说明**：进度条宽度越大，进度条越靠近圆心。即进度条始终在半径区域内。 |
| start-angle      | \<deg\>    | 240    | 否   | 弧形进度条起始角度，以时钟0点为基线。范围为0到360（顺时针）。 |
| total-angle      | \<deg\>    | 240    | 否   | 弧形进度条总长度，范围为-360到360，负数标识起点到终点为逆时针。 |
| center-x         | \<length\> | -      | 否   | 弧形进度条中心位置，（坐标原点为组件左上角顶点）。该样式需要和center-y和radius一起。 |
| center-y         | \<length\> | -      | 否   | 弧形进度条中心位置，（坐标原点为组件左上角顶点）。该样式需要和center-x和radius一起。 |
| radius           | \<length\> | -      | 否   | 弧形进度条半径，该样式需要和center-x和center-y一起。         |

除上述样式之外，所有type还支持如下样式：

|  名称   | 类型  |  默认值   | 必填  | 描述  |
|  ----  | ----  |  ----  | ----  | ----  |
| display | string | flex  | 否 | 确定该元素视图框的类型，该值暂不支持动态修改。可选值为：<br/>**flex**：弹性布局<br/>**none**：不渲染此元素 |
| width | \<length\> | - | 否 | 设置组件自身的宽度。未设置时组件宽度默认为0。 |
| height | \<length\> | - | 否 | 设置组件自身的宽度。未设置时组件宽度默认为0。 |
| padding | \<length\> | 0 | 否 | 使用简写属性设置所有的内边距属性。 |
| margin | \<length\> | 0 | 否 | 使用简写属性设置所有的外边距属性，该属性可以有1到4个值。是<br/>只有一个值时，这个值会被指定给全部的四个边。<br/>两个值时，第一个值被匹配给上和下，第二个值被匹配给左和右。<br/>三个值时，第一个值被匹配给上, 第二个值被匹配给左和右，第三个值被匹配给下。<br/>四个值时，会依次按上、右、下、左的顺序匹配 (即顺时针顺序)。 |
| margin-[left\|top\|right\|bottom] | \<length\> | 0 | 否 | 设置左、上、右、下外边距属性。 |
| border-width | \<length\> | 0 | 否 | 使用简写属性设置元素的所有边框宽度。 |
| border-color | \<color\> | black | 否 | 使用简写属性设置元素的所有边框颜色。 |
| border-radius | \<length\> | - | 否 | border-radius属性是设置元素的外边框圆角半径。 |
| background-color | \<color\> | - | 否 | 设置背景颜色。 |
| [left\|top] | \<length\> | - | 否 | left|

# DEMO

构成一个页面的三个部分，`index.hml`,`index.css`,`index.js`。

>  请注意默认还有一个[app.js](/zh-cn/js-file "app.js")文件。

代码仓库地址：`http://gitlab.evmiot.com:12306/wzedmund/evm-jsfwk-littlevgl-qt/tree/dev/test/test-progress`

**index.hml**

```html
<div class="container">
    <list class="list-container">
        <list-item class="listitem">
            <progress type="horizontal" percent="30"></progress>
            <progress type="arc" percent="30" style="padding: 5px;
                                                     width: 80px;
                                                     height: 80px;
                                                     stroke-width: 10px;
                                                     ">
            </progress>
        </list-item>
        <list-item class="listitem">
            <progress type="horizontal" percent="50"></progress>
            <progress percent="50" style="padding: 5px; 
                                          width: 80px;
                                          height: 80px;
                                          margin-top: 2px;
                                          color: red;">
            </progress>
        </list-item>
        <list-item class="listitem">
            <progress type="horizontal" percent="80"></progress>
            <progress percent="80" style="padding: 5px;
                                          width: 80px;
                                          height: 80px;
                                          border-width: 1px;
                                          border-color: red;
                                          border-radius: 50%;">
            </progress>
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
    height: 350px;
    left: 75px;
    top: 50px;
    background-color: yellow;
}

.listitem {
    flex-direction: column;
    align-items: center;
    width: 330px;
    height: 100px;
    margin: 0px;
    padding: 5px;
}
```

**index.js**

```javascript
export default {
    data: {
        title: 'HelloWorld'
    }
}
```

## 执行命令

下面可以在命令行输入以下命令，体验下DEMO，请根据自己实际的目录以及操作系统输入命令：

**Linux**

```shell
wanli@wanli-PC:~/projects/evm-jsfwk-littlevgl-qt/bin/x86_64-linux-gnu$
./evue ../../test/test-progress/
```

**Windows**

```powershell
PS D:~/projects/evm-jsfwk-littlevgl-qt/bin/x86_64-window-mingw>
evue.exe ../../test/test-progress/
```

## 运行截图

一切顺利的话，你将会看到如下页面：

![](http://statics.evmiot.com/evue_20201031221344.jpg)