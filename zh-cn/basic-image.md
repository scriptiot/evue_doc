> 子组件  
> 属性  
> 事件  
> 样式  
> DEMO

图片组件，用来渲染展示图片。

# 子组件
不支持。

# 属性
|  名称   | 类型  |  默认值   | 必填  | 描述  |
|  ----  | ----  |  ----  | ----  | ----  |
| src | string | -  | 否 | 图片的路径，支持的图片格式包括png、jpg。 |
| id | string | -  | 否 | 组件的唯一标识。 |
| style | string | -  | 否 | 组件的样式声明。 |
| class | string | -  | 否 | 组件的样式类，用于引用样式表。 |
| ref | string | -  | 否 | 用来指定指向子元素的引用信息，该引用将注册到父组件的$refs 属性对象上。 |

> **说明：** 轻量级智能穿戴上，单个应用所有的图片资源总大小不得超过8M。

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

代码仓库地址：`http://gitlab.evmiot.com:12306/wzedmund/evm-jsfwk-littlevgl-qt/tree/dev/test/test-image`

**index.hml**

```html
<div class="container">
    <text style="left: 140px;
                 top:30px;
                 width: 180px;
                 height: 60px;
                 text-align: center;
                 font-size: 30px;
                 font-family: simsun;
    "> 演示Demo </text>
    <image src="./common/images/microphone565.bin"
           style="left: 80px;top: 120px;text-align: center;
                  padding-left: 40px;padding-top: 40px;
                  border-width: 1px;border-color:red;">
    </image>
    <image src="./common/images/phone565.bin"
    style="left: 80px;top: 248px;text-align: center;margin: 10px;"/>
    <image src="./common/images/voice565.bin"
    style="left: 80px;top: 366px;text-align: center;margin: 10px;" />
</div>
```

**index.css**

```css
body {
    /* background-image: "./images/phone565.bin"; */
    background-color: #345678;
    opacity: 255;
}

.container {
    width: 454px;
    height: 454px;
    border-width: 0px;
    opacity: 0;
}
```

**index.js**

```javascript
export default {
    data: {
        title: 'show-test-image'
    }
}
```

## 执行命令

下面可以在命令行输入以下命令，体验下DEMO，请根据自己实际的目录以及操作系统输入命令：

**Linux**

```shell
cd evuesimulator-linux-v2.0
./evuesimulator test/test-image/
```

**Windows**

```powershell
cd evuesimulator-windows-v2.0
evuesimulator.exe test/test-image/
```

## 运行截图

一切顺利的话，你将会看到如下页面：

![](http://statics.evmiot.com/evue_20201031220758.jpg)