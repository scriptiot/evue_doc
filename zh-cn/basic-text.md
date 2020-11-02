> 子组件  
> 属性  
> 事件  
> 样式  
> DEMO

文本，用于呈现一段信息。

# 子组件
不支持。

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
|  名称   | 类型  |  默认值   | 必填  | 描述  |
|  ----  | ----  |  ----  | ----  | ----  |
| display | string | flex  | 否 | 确定该元素视图框的类型，该值暂不支持动态修改。可选值为：<br/>*flex*弹性布局<br/>*none*：不渲染此元素 |
| width | \<length\> | - | 否 | 设置组件自身的宽度。未设置时组件宽度默认为0。 |
| height | \<length\> | - | 否 | 设置组件自身的宽度。未设置时组件宽度默认为0。 |
| padding | \<length\> | 0 | 否 | 使用简写属性设置所有的内边距属性。 |
| margin | \<length\> | 0 | 否 | 使用简写属性设置所有的外边距属性，该属性可以有1到4个值。<br/>只有一个值时，这个值会被指定给全部的四个边。<br>两个值时，第一个值被匹配给上和下，第二个值被匹配给左和右<br/>三个值时，第一个值被匹配给上, 第二个值被匹配给左和右，第三个值被匹配给下。<br/>四个值时，会依次按上、右、下、左的顺序匹配 (即顺时针顺序)。 |
| margin-[left\|top\|right\|bottom] | \<length\> | 0           | 否 | 设置左、上、右、下外边距属性。 |
| border-width | \<length\> | 0 | 否 | 使用简写属性设置元素的所有边框宽度。 |
| border-color | \<color\> | black | 否 | 使用简写属性设置元素的所有边框颜色。 |
| border-radius | \<length\> | - | 否 | border-radius属性是设置元素的外边框圆角半径。 |
| background-color | \<color\> | - | 否 | 设置背景颜色。 |
| [left\|top] | \<length\> | - | 否 | left|
| color | \<color\> | \#ffffff | 否 | 设置文本的颜色。 |
| font-size | \<length\> | 30px | 否 | 设置文本的尺寸。<br/>目前仅支持30px和38px 两个字体大小。 |
| letter-spacing | \<length\> | 2px | 否 | 设置文本的字符间距。                                         |
| text-align | string | left | 否 | 设置文本的文本对齐方式，可选值为：<br/>**left：**文本左对齐；<br/>**center：**文本居中对齐；<br/>**right：**文本右对齐； |
| text-overflow | string | clip | 否 | 可选值为：<br/>clip：将文本根据父容器大小进行裁剪显示；<br/>ellipsis：根据父容器大小显示，显示不下的文本用省略号代替。 |
| font-family | string | HYQiHei-65S | 否 | 字体。目前仅支持HYQiHei-65S 字体。 |

# DEMO

构成一个页面的三个部分，`index.hml`,`index.css`,`index.js`。

>  请注意默认还有一个[app.js](/zh-cn/js-file "app.js")文件。

代码仓库地址：`http://gitlab.evmiot.com:12306/wzedmund/evm-jsfwk-littlevgl-qt/tree/dev/test/test-text`

**index.hml**

```html
<div style="left: 0px;
            top: 0px;
            width: 455px;
            height: 455px;
            border-width: 1px;
            border-style: solid;
            border-color: white;
            margin: 50px;
            background-color: black;">
    <text style="left: 70px;
                 top: 70px;
                 width: 100px;
                 height: 30px;
                 font-size: 20px;
                 color: white;
                 border-width: 1px;
                 border-style: solid;
                 border-color: white;">text</text>
    <text style="left: 70px;
                 top: 110px;
                 width: 150px;
                 height: 30px;
                 font-size: 20px;
                 color: white;
                 border-width: 1px;
                 border-style: solid;
                 border-color: white;
                 letter-spacing: 5px;">letter space</text>
    <text style="left: 70px;
                 top: 150px;
                 width: 150px;
                 height: 30px;
                 font-size: 20px;
                 color: white;
                 border-width: 1px;
                 border-style: solid;
                 border-color: white;
                 text-align: center;">text align</text>
    <text style="left: 70px;
                 top: 190px;
                 width: 150px;
                 height: 30px;
                 font-size: 20px;
                 color: white;
                 border-width: 1px;
                 border-style: solid;
                 border-color: white;
                 text-overflow: clip;">text overflow hello world</text>
    <text style="left: 70px;
                 top: 230px;
                 width: 100px;
                 height: 30px;
                 font-size: 20px;
                 color: white;
                 border-width: 1px;
                 border-style: solid;
                 border-color: white;
                 text-decoration: underline;">text decoration</text>
    <text style="left: 70px;
                 top: 270px;
                 width: 100px;
                 height: 30px;
                 font-size: 20px;
                 color: white;
                 border-width: 1px;
                 border-style: solid;
                 border-color: white;
                 line-height: 20px;">line height</text>
    <text style="left: 70px;
                 top: 310px;
                 font-size: 20px;
                 color: white;">display none</text>
    <text style="left: 70px;
                 top: 330px;
                 background-color: red;
                 opacity: 0.5;">opacity</text>
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
        title: 'show-test-text'
    }
}
```

## 执行命令

下面可以在命令行输入以下命令，体验下DEMO，请根据自己实际的目录以及操作系统输入命令：

**Linux**

```shell
cd evuesimulator-linux-v2.0
./evuesimulator test/test-text/
```

**Windows**

```powershell
cd evuesimulator-windows-v2.0
<<<<<<< Updated upstream
evuesimulator.exe test/test-text/
=======
evuesimulator.exe ../../test/test-text/
>>>>>>> Stashed changes
```

## 运行截图

一切顺利的话，你将会看到如下页面：

![](http://statics.evmiot.com/evue_20201031221653.jpg)

