> 子组件  
> 属性  
> 事件  
> 样式  
> DEMO  

基础容器，用作页面结构的根节点或将内容进行分组。

> 真的是个容器，无法直接在标签内输入字符串，输入字符串必须使用\<text\>标签。同时也不支持font-size属性。

# 子组件

支持。

# 属性
|  名称   | 类型  |  默认值   | 必填  | 描述  |
|  ----  | ----  |  ----  | ----  | ----  |
| id  | string | -  | 否 | 组件的唯一标识。 |
| style  | string | -  | 否 | 组件的样式声明。 |
| class  | string | -  | 否 | 组件的样式类，用于引用样式表。 |
| ref  | string | -  | 否 | 用来指定指向子元素的引用信息，该引用将注册到父组件的$refs 属性对象上。 |

# 事件
|  名称   | 参数  | 描述  |
|  ----  | ----  | ----  |
| click  | - | 点击动作触发该事件。 |
| longpress  | - | 长按动作触发该事件。 |
| swipe  | SwipeEvent | 组件上快速滑动后触发。 |

# 样式

样式类似Web的CSS，可以将样式写在元素的style属性内，也可以写到`.css`后缀的文件中，框架会自动引用该样式文件。

如果同一个元素，既写了style，又在css里面写了id样式，还写了class样式，则style优先级 > id优先级 > class优先级；同一个元素多个class，css文件中靠后的样式覆盖前面同属性样式。

> css有!important提升优先级，鸿蒙是否支持？

> 注意：`.hml`,`.css`,`.js`三个文件名必须一致，框架才会自动关联，否则无法实现预期效果。

![微信截图_20201022234730.png](https://i.loli.net/2020/10/23/3rxnRsVcmuaHEjT.png) ![微信截图_20201022234814.png](https://i.loli.net/2020/10/23/o5wyNtsEkzXVfPj.png)

**错误方式**														**正确方式**

|  名称   | 类型  |  默认值   | 必填  | 描述  |
|  ----  | ----  |  ----  | ----  | ----  |
| flex-direction | string | row  | 否 | flex容器主轴方向。可选项有：<br/>*column*：垂直方向从上到下<br/>*row*：水平方向从左到右 |
| flex-wrap  | string | nowrap  | 否 | flex容器是单行还是多行显示，该值暂不支持动态修改。可选项有：<br/>*nowrap*：不换行，单行显示。<br/>*wrap*：换行，多行显示。 |
| justify-content  | string | flex-start  | 否 | flex容器当前行的主轴对齐格式。可选项有：<br/*>flex-start*：项目位于容器的开头。<br/>*flex-end*：项目位于容器的结尾。<br/>*center*：项目位于容器的中心。<br/>*space-between*：项目位于各行之间留有空白的容器内。<br/>*space-around*：项目位于各行之前、之间、之后都留有空白的容器内。 |
| align-items  | string | flex-start | 否 | flex容器当前行的交叉轴对齐格式，可选值为：<br/>*flex-start*：元素向交叉轴起点对齐。<br/>*flex-end*：元素向交叉轴终点对齐。<br/>*center*：元素在交叉轴居中。 |
| display | string | flex  | 否 | 确定该元素视图框的类型，该值暂不支持动态修改。可选值为：<br/>*flex*：弹性布局<br/>*none*：不渲染此元素 |
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

**注意事项：**

1. 父元素width和height不能为0，否则父元素以及所有子元素不显示；也不支持设置百分比；
2. 根元素只能为一个，多个根元素会导致所有元素不显示，想想HTML里面只能有一个`<body></body>`元素；
3. border属性暂不支持`border: 1px solid red;`这种写法，必须分开写：`border-width: 1px;border-style: solid;border-color: red;`;



# DEMO

构成一个页面的三个部分，`index.hml`,`index.css`,`index.js`。

>  请注意默认还有一个[app.js](/zh-cn/js-file "app.js")文件。

代码仓库地址：`http://gitlab.evmiot.com:12306/wzedmund/evm-jsfwk-littlevgl-qt/tree/dev/test/test-div`

**index.hml**

```html
<div style="width: 350px;
            height: 350px;
            border-width: 1px;
            border-style: solid;
            border-color: green;
            left: 50px;
            top: 50px;
            margin: 50px;
            padding: 10px;">
    <div style="width: 100px;height: 100px;">
        <text>helloworld</text>
    </div>
    <div style="left: 100px;
                width: 100px;
                height: 100px;
                background-color: red;
                opacity: 0.5;">
        <text>opacity</text>
    </div>
    <div style="left: 200px;
                width: 100px;
                height: 100px;
                background-color: red;
                display: none;">
        <text>display none</text>
    </div>
    <div style="left: 0px;
                top: 100px;
                width: 100px;
                height: 100px;
                border-width: 1px;
                border-style: solid;
                border-color: yellow;">
        <text>border</text>
    </div>
    <div style="left: 100px;
                top: 100px;
                width: 100px;
                height: 100px;
                background-color: blue;
                visibility: hidden;
                color: white;">
        <text>visibility</text>
    </div>
</div>
```

**index.css**

```css
.container {
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    /*flex-wrap: wrap;*/
}
```

**index.js**

```javascript
export default {
    data: {
        title: 'show-test-div'
    }
}
```

## 执行命令

下面可以在命令行输入以下命令，体验下DEMO，请根据自己实际的目录以及操作系统输入命令：

**Linux**

```shell
wanli@wanli-PC:~/projects/evm-jsfwk-littlevgl-qt/bin/x86_64-linux-gnu$
./evue ../../test/test-div/
```

**Windows**

```powershell
PS D:~/projects/evm-jsfwk-littlevgl-qt/bin/x86_64-window-mingw>
evue.exe ../../test/test-div/
```

## 运行截图

一切顺利的话，你将会看到如下页面：

![](http://statics.evmiot.com/evue_20201031192000.png)

