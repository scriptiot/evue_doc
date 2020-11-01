> 子组件  
> 属性  
> 事件  
> 样式  
> DEMO  

滑动容器，提供切换子组件显示的能力。

# 子组件
支持除\<list\>之外的子组件。

# 属性
|  名称   | 类型  |  默认值   | 必填  | 描述  |
|  ----  | ----  |  ----  | ----  | ----  |
| id  | string | -  | 否 | 组件的唯一标识。 |
| style  | string | -  | 否 | 组件的样式声明。 |
| class  | string | -  | 否 | 组件的样式类，用于引用样式表。 |
| ref  | string | -  | 否 | 用来指定指向子元素的引用信息，该引用将注册到父组件的$refs 属性对象上。 |
| index  | number | 0 | 否 | 当前在容器中显示的子组件的索引值。 |
| loop  | boolean | true | 否 | 是否开启循环轮播。<br/>不支持动态修改。<br/> **说明：**loop参数生效需要满足以下两个条件：<br/>1. 除第一个子组件之外，剩余子组件的总长度大于等于swiper的长度；<br/>2. 除最后一个子组件之外，剩余子组件的总长度大于等于swiper的长度。 |
| duration | number | - | 否 | 子组件切换的动画时长。 |
| vertical | boolean | false | 否 | 是否为纵向滑动，纵向滑动时采用纵向的指示器。不支持动态修改。 |

# 事件
|  名称   | 参数  | 描述  |
|  ----  | ----  | ----  |
| change  | { index: currentIndex } | 当前显示的组件索引变化时触发该事件。 |
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

> 说明：由于绝对定位不支持设置百分比，所以也不支持stack组件的子组件上设置margin。

# DEMO

构成一个页面的三个部分，`index.hml`,`index.css`,`index.js`。

> 请注意默认还有一个[app.js](/zh-cn/js-file "app.js")文件。

代码仓库地址：`http://gitlab.evmiot.com:12306/wzedmund/evm-jsfwk-littlevgl-qt/tree/dev/test/test-swiper`

**index.hml**

```html
<swiper autoplay=true interval=1000 vertical=true duration=100 style="
    width: 350px;height: 350px;border-width: 1px;border-style: solid;
    border-color: black;left: 50px;top: 50px;margin: 50px;">
    <div style="width: 350px;height: 350px;background-color: red;">
        <text>box 1</text>
    </div>
    <div style="width: 350px;height: 350px;background-color: green;">
        <text>box 2</text>
    </div>
    <div style="width: 350px;height: 350px;background-color: yellow;">
        <text>box 3</text>
    </div>
    <div style="width: 350px;height: 350px;background-color: blue;">
        <text>box 4</text>
    </div>
</swiper>
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
        title: 'show-test-swiper'
    }
}
```

## 执行命令

下面可以在命令行输入以下命令，体验下DEMO，请根据自己实际的目录以及操作系统输入命令：

**Linux**

```shell
wanli@wanli-PC:~/projects/evm-jsfwk-littlevgl-qt/bin/x86_64-linux-gnu$
./evue ../../test/test-swiper/
```

**Windows**

```powershell
PS D:~/projects/evm-jsfwk-littlevgl-qt/bin/x86_64-window-mingw>
evue.exe ../../test/swiper/
```

## 运行截图

一切顺利的话，你将会看到如下页面：

![](http://statics.evmiot.com/Peek-2020-10-31-22-01.gif)